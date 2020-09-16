---
title: Patrones de observación
description: Patrones de observación para aplicaciones nativas de la nube
ms.date: 08/10/2020
ms.openlocfilehash: 2a6ef0e58f1e20667167042614768b099f640858
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539858"
---
# <a name="observability-patterns"></a>Patrones de observación

Al igual que los patrones se han desarrollado para ayudar en el diseño del código de las aplicaciones, hay patrones para las aplicaciones operativas de una forma confiable. Han surgido tres patrones útiles para el mantenimiento de las aplicaciones: **registro**, **supervisión**y **alertas**.

## <a name="when-to-use-logging"></a>Cuándo usar el registro

Sea cual sea el cuidado que tengamos, las aplicaciones casi siempre se comportan de maneras inesperadas en producción. Cuando los usuarios informan de problemas con una aplicación, resulta útil poder ver lo que estaba ocurriendo con la aplicación cuando se produjo el problema. Una de las formas más probadas y verdaderas de capturar información sobre lo que hace una aplicación mientras se está ejecutando es hacer que la aplicación anote lo que está haciendo. Este proceso se conoce como registro. En cualquier momento en que se produzcan errores o problemas en la producción, el objetivo debe ser reproducir las condiciones en las que se produjeron los errores, en un entorno que no sea de producción. Tener un buen registro en su lugar proporciona una guía básica para que los desarrolladores puedan seguir con el fin de duplicar problemas en un entorno que se pueda probar y experimentar con.

### <a name="challenges-when-logging-with-cloud-native-applications"></a>Desafíos al registrar con aplicaciones nativas de la nube

En las aplicaciones tradicionales, los archivos de registro se almacenan normalmente en el equipo local. De hecho, en sistemas operativos similares a Unix, hay una estructura de carpetas definida para contener los registros, normalmente en `/var/log` .

![Registro en un archivo en una aplicación monolítica. ](./media/single-monolith-logging.png)
 **Figura 7-1**. Registro en un archivo en una aplicación monolítica.

La utilidad del registro en un archivo plano en un solo equipo se reduce enormemente en un entorno de nube. Es posible que las aplicaciones que producen registros no tengan acceso al disco local o que el disco local sea muy transitorio, ya que los contenedores se ordenan en torno a las máquinas físicas. Incluso un simple escalado vertical de aplicaciones monolíticas en varios nodos puede hacer que sea difícil encontrar el archivo de registro basado en archivos adecuado.

![Registro en archivos en una aplicación monolítica escalada. ](./media/multiple-node-monolith-logging.png)
 **Figura 7-2**. Registro en archivos en una aplicación monolítica escalada.

Las aplicaciones nativas en la nube desarrolladas mediante una arquitectura de microservicios también presentan algunos desafíos para los registradores basados en archivos. Las solicitudes de usuario ahora pueden abarcar varios servicios que se ejecutan en equipos diferentes y pueden incluir funciones sin servidor sin acceso a un sistema de archivos local. Sería muy difícil poner en correlación los registros de un usuario o una sesión en estos muchos servicios y máquinas.

![Registro en archivos locales en una aplicación de microservicios. ](./media/local-log-file-per-service.png)
 **Figura 7-3**. Registro en archivos locales en una aplicación de microservicios.

Por último, el número de usuarios en algunas aplicaciones nativas de la nube es alto. Imagine que cada usuario genera cien líneas de mensajes de registro cuando inicia sesión en una aplicación. En aislamiento, que es administrable, pero que se multiplican por más de 100.000 usuarios y el volumen de registros es lo suficientemente grande como para admitir el uso eficaz de los registros.

### <a name="logging-in-cloud-native-applications"></a>Inicio de sesión en aplicaciones nativas en la nube

Cada lenguaje de programación tiene herramientas que permiten escribir registros y, por lo general, la sobrecarga de escribir estos registros es baja. Muchas de las bibliotecas de registro de proporcionan el registro de diferentes tipos de críticas, que se pueden optimizar en tiempo de ejecución. Por ejemplo, la [biblioteca Serilog](https://serilog.net/) es una conocida biblioteca de registro estructurado para .net que proporciona los siguientes niveles de registro:

* Verbose
* Depurar
* Information
* Advertencia
* Error
* Crítico

Estos niveles de registro diferentes proporcionan granularidad en el registro. Cuando la aplicación funciona correctamente en producción, puede estar configurada para que solo se registren mensajes importantes. Cuando el comportamiento de la aplicación es correcto, se puede aumentar el nivel de registro para que se recopilen registros más detallados. Esto equilibra el rendimiento frente a la facilidad de depuración.

El alto rendimiento de las herramientas de registro y el tunability de nivel de detalle deben animar a los desarrolladores a registrar con frecuencia. Muchos favorecen un patrón de registro de la entrada y la salida de cada método. Este enfoque puede parecer un exceso de carga, pero es poco frecuente que los desarrolladores quieran menos registro. De hecho, no es raro realizar implementaciones con el único fin de agregar el registro en torno a un método problemático. Error en el lado de un registro demasiado grande y no en demasiado pequeño. Se pueden usar algunas herramientas para proporcionar automáticamente este tipo de registro.

Debido a los desafíos asociados al uso de registros basados en archivos en aplicaciones nativas en la nube, se prefieren registros centralizados. Las aplicaciones recopilan los registros y se envían a una aplicación de registro central que indexa y almacena los registros. Esta clase de sistema puede introducir decenas de gigabytes de registros todos los días.

También resulta útil seguir algunas prácticas estándar al compilar el registro que abarca muchos servicios. Por ejemplo, la generación de un [identificador de correlación](https://blog.rapid7.com/2016/12/23/the-value-of-correlation-ids/) al principio de una interacción larga y, a continuación, su registro en cada mensaje relacionado con dicha interacción, facilita la búsqueda de todos los mensajes relacionados. Una solo necesita buscar un único mensaje y extraer el identificador de correlación para buscar todos los mensajes relacionados. Otro ejemplo es asegurarse de que el formato del registro es el mismo para todos los servicios, sea cual sea el lenguaje o la biblioteca de registro que usa. Esta estandarización hace que la lectura de registros sea mucho más sencilla. En la figura 7-4 se muestra cómo una arquitectura de microservicios puede aprovechar el registro centralizado como parte de su flujo de trabajo.

![Los registros de varios orígenes se ingestan en un almacén de registro centralizado. ](./media/centralized-logging.png)
 **Figura 7-4**. Los registros de varios orígenes se ingestan en un almacén de registro centralizado.

## <a name="challenges-with-detecting-and-responding-to-potential-app-health-issues"></a>Desafíos con la detección y respuesta a posibles problemas de estado de las aplicaciones

Algunas aplicaciones no son críticas. Quizás solo se usan internamente y, cuando se produce un problema, el usuario puede ponerse en contacto con el equipo responsable y se puede reiniciar la aplicación. Sin embargo, los clientes a menudo tienen mayores expectativas para las aplicaciones que consumen. Debe saber cuándo se producen problemas en la aplicación *antes* de que los usuarios realicen la notificación. De lo contrario, lo primero que conoce sobre un problema puede ser cuando observa una avalancha enfadada de publicaciones de medios sociales que desactivan su aplicación o incluso su organización.

Algunos escenarios que es posible que tenga que tener en cuenta son:

- Un servicio de la aplicación sigue produciendo errores y reiniciando, lo que da lugar a respuestas lentas intermitentes.
- En algunas ocasiones del día, el tiempo de respuesta de la aplicación es lento.
- Después de una implementación reciente, se ha recorrido la carga en la base de datos.

La supervisión, que se implementa correctamente, puede permitirle conocer las condiciones que provocarán problemas, lo que le permitirá abordar las condiciones subyacentes antes de que se produzca un impacto significativo en el usuario.

### <a name="monitoring-cloud-native-apps"></a>Supervisión de aplicaciones nativas en la nube

Algunos sistemas de registro centralizados adoptan un rol adicional para recopilar la telemetría fuera de los registros puros. Pueden recopilar métricas, como el tiempo para ejecutar una consulta de base de datos, el tiempo medio de respuesta de un servidor Web, e incluso los promedios de carga de la CPU y la presión de memoria que muestra el sistema operativo. Junto con los registros, estos sistemas pueden proporcionar una vista holística del estado de los nodos del sistema y de la aplicación en su conjunto.

Las capacidades de recopilación de métricas de las herramientas de supervisión también se pueden alimentar manualmente desde dentro de la aplicación. Los flujos de negocio que son de especial interés, como los nuevos usuarios que se suscriben o los pedidos que se colocan, se pueden instrumentar de forma que incrementen un contador en el sistema de supervisión central. Esto desbloquea las herramientas de supervisión para no solo supervisar el estado de la aplicación, sino también el estado de la empresa.

Las consultas se pueden construir en las herramientas de agregación de registros para buscar determinadas estadísticas o patrones, que se pueden mostrar en forma gráfica en los paneles personalizados. Con frecuencia, los equipos invertirán en pantallas grandes montadas en pared que giran por las estadísticas relacionadas con una aplicación. De este modo, es fácil ver los problemas a medida que se producen.

Las herramientas de supervisión nativas de la nube proporcionan telemetría en tiempo real e información sobre las aplicaciones, independientemente de si son aplicaciones monolíticas de un solo proceso o arquitecturas de microservicios distribuidas. Incluyen herramientas que permiten la recopilación de datos de la aplicación, así como herramientas para consultar y Mostrar información sobre el estado de la aplicación.

## <a name="challenges-with-reacting-to-critical-problems-in-cloud-native-apps"></a>Desafíos relacionados con la reacción ante problemas críticos en aplicaciones nativas en la nube

Si necesita reaccionar ante problemas con la aplicación, necesita alguna manera de alertar al personal adecuado. Este es el tercer patrón de observación de aplicaciones nativas en la nube y depende del registro y la supervisión. La aplicación debe tener el inicio de sesión para permitir que se diagnostiquen los problemas y, en algunos casos, para alimentar en las herramientas de supervisión. Necesita supervisión para agregar métricas de aplicación y datos de mantenimiento en un solo lugar. Una vez que se ha establecido, se pueden crear reglas que desencadenarán alertas cuando determinadas métricas se encuentren fuera de los niveles aceptables.

Por lo general, las alertas se superponen por encima de la supervisión de modo que determinadas condiciones desencadenen las alertas adecuadas para notificar a los miembros del equipo de problemas urgentes. Algunos escenarios que pueden requerir alertas son los siguientes:

- Uno de los servicios de la aplicación no responde después de un tiempo de inactividad.
- La aplicación devuelve respuestas HTTP incorrectas a más del 1% de las solicitudes.
- El tiempo medio de respuesta de la aplicación para los puntos de conexión de clave supera los 2000 ms.

### <a name="alerts-in-cloud-native-apps"></a>Alertas en aplicaciones nativas de la nube

Puede crear consultas en las herramientas de supervisión para buscar condiciones de error conocidas. Por ejemplo, las consultas podrían buscar en los registros entrantes indicaciones del código de Estado HTTP 500, que indica un problema en un servidor Web. En cuanto se detecta uno de estos, se puede enviar un mensaje de correo electrónico o un SMS al propietario del servicio de origen que puede comenzar a investigar.

Sin embargo, normalmente, un solo error 500 no es suficiente para determinar que se ha producido un problema. Podría significar que un usuario escribió incorrectamente su contraseña o escribió algunos datos mal formados. Las consultas de alerta se pueden diseñar para que solo se activen cuando se detecte un número mayor que el promedio de errores 500.

Uno de los patrones más dañinos en las alertas es activar demasiadas alertas para que los usuarios lo investiguen. Los propietarios de servicios se Desensitized rápidamente a los errores que se han investigado anteriormente y se han descubierto que son benignos. A continuación, cuando se produzcan errores verdaderos, se perderán en el ruido de cientos de falsos positivos. El Parable del [chico que Cried Wolf](https://en.wikipedia.org/wiki/The_Boy_Who_Cried_Wolf) se suele indicar a los niños para advertirles de este riesgo. Es importante asegurarse de que las alertas que se activan son indicativas de un problema real.

>[!div class="step-by-step"]
>[Anterior](monitoring-health.md)
>[Siguiente](logging-with-elastic-stack.md)
