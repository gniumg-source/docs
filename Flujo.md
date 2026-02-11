Flujo de GitHub
Siga el flujo de GitHub para colaborar en proyectos.

En este artículo
Introducción
El flujo de GitHub es un flujo de trabajo ligero basado en ramas. Es útil para todos, no solo para desarrolladores. Por ejemplo, en GitHub, lo usamos para la política del sitio , la documentación y la hoja de ruta .

Prerrequisitos
Para seguir el flujo de trabajo de GitHub, necesitarás una cuenta de GitHub y un repositorio. Para obtener información sobre cómo crear una cuenta, consulta " Crear una cuenta en GitHub" . Para obtener información sobre cómo crear un repositorio, consulta "Guía rápida para repositorios" . Para obtener información sobre cómo encontrar un repositorio al que contribuir, consulta " Cómo contribuir al código abierto en GitHub" .

Siguiendo el flujo de GitHub
Consejo

Puedes completar todos los pasos del flujo de GitHub a través de la interfaz web, la línea de comandos y la CLI de GitHub , o GitHub Desktop . Para obtener más información sobre las herramientas que puedes usar para conectarte a GitHub, consulta Conectarse a GitHub .

Crear una rama
Crea una rama en tu repositorio. Un nombre de rama corto y descriptivo permite a tus colaboradores ver el trabajo en curso de un vistazo. Por ejemplo, increase-test-timeouto add-code-of-conduct. Para más información, consulta Crear y eliminar ramas en tu repositorio .

Al crear una rama, creas un espacio para trabajar sin afectar la rama predeterminada. Además, les das a tus colaboradores la oportunidad de revisar tu trabajo.

Realizar cambios
En tu rama, realiza los cambios que desees en el repositorio. Para más información, consulta Crear archivos , Editar archivos , Cambiar el nombre de un archivo , Mover un archivo a una nueva ubicación o Eliminar archivos de un repositorio .

Tu rama es un lugar seguro para realizar cambios. Si cometes un error, puedes revertir los cambios o enviar cambios adicionales para corregirlo. Tus cambios no se incluirán en la rama predeterminada hasta que fusiones tu rama.

Confirma y envía tus cambios a tu rama. Asigna a cada confirmación un mensaje descriptivo para que tú y tus futuros colaboradores comprendan qué cambios contiene. Por ejemplo, fix typoo increase rate limit.

Idealmente, cada confirmación contiene un cambio completo e independiente. Esto facilita revertir los cambios si se decide adoptar un enfoque diferente. Por ejemplo, si se desea renombrar una variable y añadir pruebas, se debe incluir el cambio de nombre en una confirmación y las pruebas en otra. Posteriormente, si se desea conservar las pruebas pero revertir el cambio de nombre de la variable, se puede revertir la confirmación específica que contenía dicho cambio. Si se incluye el cambio de nombre de la variable y las pruebas en la misma confirmación o se distribuye el cambio de nombre en varias confirmaciones, se invertirá más esfuerzo en revertir los cambios.

Al confirmar y enviar tus cambios, respaldas tu trabajo en un almacenamiento remoto. Esto significa que puedes acceder a tu trabajo desde cualquier dispositivo. También significa que tus colaboradores pueden verlo, responder preguntas y hacer sugerencias o contribuciones.

Continúe realizando, confirmando y enviando cambios a su rama hasta que esté listo para solicitar comentarios.

Consejo

Crea una rama independiente para cada conjunto de cambios no relacionados. Esto facilita que los revisores den su opinión. También facilita que tú y tus futuros colaboradores comprendan los cambios y los reviertan o desarrollen. Además, si hay un retraso en un conjunto de cambios, los demás no se retrasan.

Crear una solicitud de extracción
Crea una solicitud de extracción para solicitar comentarios de los colaboradores sobre tus cambios. La revisión de las solicitudes de extracción es tan importante que algunos repositorios requieren una aprobación antes de fusionarlas. Si deseas recibir comentarios o consejos antes de completar los cambios, puedes marcar tu solicitud de extracción como borrador. Para más información, consulta Crear una solicitud de extracción .

Al crear una solicitud de extracción, incluya un resumen de los cambios y el problema que resuelven. Puede incluir imágenes, enlaces y tablas para facilitar la comunicación. Si su solicitud de extracción aborda una incidencia, vincúlela para que los interesados ​​la conozcan y viceversa. Si la vincula con una palabra clave, la incidencia se cerrará automáticamente al fusionar la solicitud de extracción. Para obtener más información, consulte Sintaxis básica de escritura y formato y Vincular una solicitud de extracción a una incidencia .

Además de completar el cuerpo de la solicitud de extracción, puede agregar comentarios a líneas específicas de la solicitud de extracción para señalar algo explícitamente a los revisores.

Tu repositorio puede estar configurado para solicitar automáticamente una revisión a equipos o usuarios específicos al crear una solicitud de incorporación de cambios. También puedes @mencionar o solicitar manualmente una revisión a personas o equipos específicos.

Si su repositorio tiene comprobaciones configuradas para ejecutarse en las solicitudes de extracción, verá las comprobaciones que fallaron en su solicitud. Esto le ayuda a detectar errores antes de fusionar su rama. Para más información, consulte Acerca de las comprobaciones de estado .

Comentarios de revisión de direcciones
Los revisores pueden dejar preguntas, comentarios y sugerencias. Pueden comentar sobre toda la solicitud de incorporación de cambios o añadir comentarios a líneas o archivos específicos. Tanto usted como los revisores pueden insertar imágenes o sugerencias de código para aclarar los comentarios. Para más información, consulte Revisión de cambios en las solicitudes de incorporación de cambios .

Puedes seguir confirmando y enviando cambios según las revisiones. Tu solicitud de incorporación de cambios se actualizará automáticamente.

Fusionar su solicitud de extracción
Una vez aprobada tu solicitud de extracción, fusiona tu solicitud. Esto fusionará automáticamente tu rama para que los cambios aparezcan en la rama predeterminada. GitHub conserva el historial de comentarios y confirmaciones en la solicitud de extracción para que los futuros colaboradores puedan comprender tus cambios. Para más información, consulta " Fusionar una solicitud de extracción" .

GitHub te indicará si tu solicitud de incorporación de cambios tiene conflictos que deben resolverse antes de fusionarla. Para más información, consulta " Abordar conflictos de fusión" .

La configuración de protección de ramas puede bloquear la fusión si la solicitud de incorporación de cambios no cumple ciertos requisitos. Por ejemplo, necesita un número determinado de revisiones de aprobación o una revisión de aprobación de un equipo específico. Para obtener más información, consulte Acerca de las ramas protegidas .

Eliminar tu sucursal
Después de fusionar tu solicitud de extracción, elimina tu rama. Esto indica que el trabajo en la rama ha finalizado y evita que tú u otros usuarios usen ramas antiguas por accidente. Para más información, consulta Eliminar y restaurar ramas en una solicitud de extracción .

No te preocupes por perder información. Tus solicitudes de extracción y tu historial de commits no se eliminarán. Siempre puedes restaurar la rama eliminada o revertir tu solicitud de extracción si es necesario.
