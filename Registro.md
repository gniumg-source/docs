Documentación de GitHub
GitHub Packages/Trabajar con un registro de Paquetes de GitHub/Registro de Apache maven
Trabajar con el registro de Apache Maven
Puedes configurar Apache Maven para publicar paquetes para GitHub Packages y utilizar paquetes almacenados en GitHub Packages como dependencias en un proyecto Java.

En este artículo
Autenticar a GitHub Packages
Nota:

GitHub Packages solo admite la autenticación mediante un personal access token (classic). Para más información, consulta Administración de tokens de acceso personal.

Necesitas un token de acceso para publicar, instalar y eliminar paquetes privados, internos y públicos.

Puedes utilizar un personal access token (classic) para autenticarte en el GitHub Packages o en la API de GitHub. Cuando creas un personal access token (classic), puedes asignar al token diferentes ámbitos en función de tus necesidades. Para más información sobre los ámbitos relacionados con paquetes para un personal access token (classic), consulta Acerca de los permisos para los Paquetes de GitHub.

Para autenticarte en un registro del GitHub Packages dentro de un flujo de trabajo de GitHub Actions, puedes utilizar:

GITHUB_TOKEN para publicar los paquetes asociados con el repositorio del flujo de trabajo.
Un personal access token (classic) con al menos alcance read:packages para instalar los paquetes asociados con otros repositorios privados (GITHUB_TOKEN puede utilizarse si el repositorio tiene acceso de lectura al paquete. Consulta Configurar la visibilidad y el control de accesos de un paquete).
Para más información sobre el uso de GITHUB_TOKEN en flujos de trabajo de GitHub Actions, consulta Uso de GITHUB_TOKEN para la autenticación en flujos de trabajo.

Autenticación con un personal access token
Debes utilizar un personal access token (classic) con los ámbitos adecuados para publicar e instalar paquetes en GitHub Packages. Para más información, consulta Introducción a los paquetes de GitHub.

Si quieres autenticar en GitHub Packages con Apache Maven, edita el archivo ~/.m2/settings.xml para incluir tu personal access token (classic). Crea un nuevo archivo ~/.m2/settings.xml si no existe uno.

En la etiqueta servers, agrega una etiqueta secundaria server con id. Reemplaza USERNAME por tu nombre de usuario de GitHub y TOKEN por tu personal access token.

En la etiqueta repositories, configura un repositorio asignando el id del repositorio al id que has agregado en la etiqueta server que contiene las credenciales. Reemplace PROPIETARIO por el nombre de la cuenta personal o de la organización que posee el repositorio. Dado que las letras mayúsculas no son compatibles, debes usar minúsculas para el propietario del repositorio si el nombre de usuario o el nombre de la organización de GitHub contiene letras mayúsculas.

Si quieres interactuar con varios repositorios, puedes agregar cada repositorio a un elemento secundario repository independiente en la etiqueta repositories, asignando el id de cada uno a las credenciales de la etiqueta servers.

GitHub Packages admite las versiones SNAPSHOT de Apache Maven. A fin de usar el repositorio de GitHub Packagespara descargar artefactos de SNAPSHOT, habilite SNAPSHOTS en el POM del proyecto consumidor o en el archivo ~/.m2/settings.xml.

<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0
                      http://maven.apache.org/xsd/settings-1.0.0.xsd">

  <activeProfiles>
    <activeProfile>github</activeProfile>
  </activeProfiles>

  <profiles>
    <profile>
      <id>github</id>
      <repositories>
        <repository>
          <id>central</id>
          <url>https://repo.maven.apache.org/maven2</url>
        </repository>
        <repository>
          <id>github</id>
          <url>https://maven.pkg.github.com/OWNER/REPOSITORY</url>
          <snapshots>
            <enabled>true</enabled>
          </snapshots>
        </repository>
      </repositories>
    </profile>
  </profiles>

  <servers>
    <server>
      <id>github</id>
      <username>USERNAME</username>
      <password>TOKEN</password>
    </server>
  </servers>
</settings>
Publicación de un paquete
Predeterminadamente, GitHub publica el paquete en un repositorio existente con el mismo nombre que éste. Por ejemplo, GitHub publicará un paquete denominado com.example:test en un repositorio denominado OWNER/test.

Advertencia

El paquete de Apache Maven debe seguir la convención de nomenclatura y, por tanto, el campo artifactId solo debe contener letras minúsculas, dígitos o guiones. Para obtener más información, consulta Convención de nomenclatura de coordenadas de Maven en la documentación de maven.apache.org. Si usas letras en mayúsculas en el nombre del artefacto, obtendrás una respuesta 422 Unprocessable Entity.

Si quieres publicar varios paquetes en el mismo repositorio, puedes incluir la dirección URL del repositorio en el elemento <distributionManagement> del archivo pom.xml. GitHub coincidirá con el repositorio según ese campo. Dado que el nombre del repositorio también forma parte del elemento distributionManagement, no hay pasos adicionales para publicar varios paquetes en el mismo repositorio.

Para obtener más información sobre cómo crear un paquete, consulta la documentación de maven.apache.org.

Edite el elemento distributionManagement del archivo pom.xml ubicado en el directorio del paquete y reemplace OWNER por el nombre de la cuenta personal o de la organización que posee el repositorio y REPOSITORY por el nombre del repositorio que contiene el proyecto.

<distributionManagement>
   <repository>
     <id>github</id>
     <name>GitHub OWNER Apache Maven Packages</name>
     <url>https://maven.pkg.github.com/OWNER/REPOSITORY</url>
   </repository>
</distributionManagement>
Publish the package.

mvn deploy
Después de que publiques un paquete, puedes verlo en GitHub. Para más información, consulta Visualizar paquetes.

Instalación de un paquete
Para instalar un paquete de Apache Maven desde GitHub Packages, edita el archivo pom.xml para incluir el paquete como una dependencia. Si desea instalar paquetes desde cualquier repositorio para el propietario de un repositorio especificado, usa una dirección URL de repositorio como https://maven.pkg.github.com/OWNER/*. Para obtener más información sobre el uso de un archivo pom.xml en el proyecto, consulta Introducción a POM en la documentación de Apache Maven.

Autentícate en GitHub Packages. Para obtener más información, consulta Autenticación en GitHub Packages.

Agrega las dependencias del paquete al elemento dependencies del archivo pom.xml del proyecto, reemplazando com.example:test por el paquete.

<dependencies>
 <dependency>
    <groupId>com.example</groupId>
    <artifactId>test</artifactId>
    <version>1.0.0-SNAPSHOT</version>
  </dependency>
</dependencies>
Instala el paquete.

mvn install
Información adicional
Trabajar con el registro de Gradle
Borrar y restablecer un paquete
