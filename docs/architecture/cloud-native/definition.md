---
title: Definición de nativo en la nube
description: Obtenga información sobre los pilares básicos que proporcionan el cimientos para sistemas nativos en la nube.
author: robvet
ms.date: 01/19/2021
ms.openlocfilehash: 180b32d753fea5071174830be4ff3b8a81527a75
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506219"
---
# <a name="defining-cloud-native"></a>Definir nativo en la nube

Detenga lo que está haciendo y el texto 10 de sus compañeros. Pídales que definan el término "Cloud Native". Buena oportunidad obtendrá diez respuestas diferentes.

La nube nativa es todo lo que se trata de cambiar la forma en que piensa crear sistemas empresariales críticos.

Los sistemas nativos de la nube están diseñados para adoptar un cambio rápido, gran escala y resistencia.

Cloud Native Computing Foundation proporciona una [definición oficial](https://github.com/cncf/foundation/blob/master/charter.md):

> *Las tecnologías nativas de la nube permiten a las organizaciones crear y ejecutar aplicaciones escalables en entornos modernos y dinámicos, como nubes públicas, privadas y híbridas. Los contenedores, las mallas de servicio, los microservicios, la infraestructura inmutable y las API declarativas ejemplifican este enfoque.*

> *Estas técnicas permiten sistemas de acoplamiento flexible que son resistentes, administrables y observables. Combinado con una automatización sólida, permite a los ingenieros realizar cambios de gran impacto con frecuencia y de forma predecible con TOIL mínimos.*

Las aplicaciones se han vuelto cada vez más complejas con usuarios que requieren más y más. Los usuarios esperan una capacidad de respuesta rápida, características innovadoras y sin tiempo de inactividad. Los problemas de rendimiento, los errores periódicos y la incapacidad de moverse rápidamente ya no son aceptables. Se trasladarán fácilmente a su competidor.

La nube nativa es la *velocidad* y la *agilidad*. Los sistemas empresariales están evolucionando desde la habilitación de las capacidades empresariales hasta las armas de transformación estratégica que aceleran la velocidad y el crecimiento de la empresa. Es imperativo obtener ideas al mercado inmediatamente.

Estas son algunas compañías que han implementado estas técnicas. Piense en la velocidad, la agilidad y la escalabilidad que han logrado.

| Compañía | Experiencia |
| :-------- | :-------- |
| [Netflix](https://www.infoq.com/news/2013/06/netflix/) | Tiene 600 y servicios en producción. Implementa cientos de veces al día. |
| [Uber](https://eng.uber.com/micro-deploy/) | Tiene más de 1000 servicios en producción. Implementa varios miles de veces cada semana. |
| [WeChat](https://www.cs.columbia.edu/~ruigu/papers/socc18-final100.pdf) | Tiene más de 3000 servicios en producción. Implementa 1.000 veces al día. |

Como puede ver, Netflix, Uber y WeChat exponen sistemas que se componen de cientos de microservicios independientes. Este estilo arquitectónico les permite responder rápidamente a las condiciones de mercado. Pueden actualizar de forma instantánea pequeñas áreas de una aplicación dinámica y compleja, y escalarlas individualmente según sea necesario.

La velocidad y la agilidad de la nube nativa proceden de una serie de factores. Lo más importante es la infraestructura de la nube. Cinco pilares básicos adicionales que se muestran en la figura 1-3 también proporcionan cimientos para sistemas nativos en la nube.

![Pilares básicos de la nube nativos](./media/cloud-native-foundational-pillars.png)

**Figura 1-3**. Pilares básicos de la nube nativos

Vamos a tomar un tiempo para comprender mejor la importancia de cada pilar.

## <a name="the-cloud"></a>La nube...

Los sistemas nativos en la nube sacan el máximo partido del modelo de servicio en la nube.

Diseñado para prosperar en un entorno de nube dinámico y virtualizado, estos sistemas hacen un uso extensivo de la infraestructura de proceso de [plataforma como servicio (PaaS)](https://azure.microsoft.com/overview/what-is-paas/) y los servicios administrados. Tratan la infraestructura subyacente como *descartable* : aprovisionada en minutos y cambiado de tamaño, escalada, movida o destruida a petición, a través de la automatización.

Tenga en cuenta el concepto DevOps ampliamente aceptado de [mascotas frente a bovinos](https://medium.com/@Joachim8675309/devops-concepts-pets-vs-cattle-2380b5aab313). En un centro de datos tradicional, los servidores se tratan como *mascotas*: una máquina física, un nombre descriptivo y el tratamiento de los mismos. Puede escalar agregando más recursos a la misma máquina (escalar verticalmente). Si el servidor está enfermo, se vuelve de la enfermera al estado. Si el servidor deja de estar disponible, todos los usuarios se ponen en aviso.

El modelo de servicio de la *vacuno* es diferente. Aprovisiona cada instancia como una máquina virtual o un contenedor. Son idénticos y se les asigna un identificador de sistema como Service-01, Service-02, etc. El escalado se realiza mediante la creación de más (escalado horizontal). Cuando uno deja de estar disponible, nadie lo notifica.

El modelo de ganado vacuno adopta una *infraestructura inmutable*. Los servidores no se reparan ni modifican. Si se produce un error en uno o es necesario actualizarlo, se destruye y se aprovisiona uno nuevo; todo ello se realiza mediante la automatización.

Los sistemas nativos en la nube adoptan el modelo de servicio de la ganado vacuno. Continúan ejecutándose a medida que la infraestructura se escala dentro o fuera con independencia de los equipos en los que se ejecutan.

La plataforma en la nube de Azure admite este tipo de infraestructura muy elástica con capacidades de escalado automático, recuperación automática y supervisión.

## <a name="modern-design"></a>Diseño moderno

¿Cómo se diseña una aplicación nativa en la nube? ¿Cuál sería la apariencia de la arquitectura? ¿A qué principios, patrones y procedimientos recomendados cumpliría? ¿Qué problemas de infraestructura y de funcionamiento serían importantes?

### <a name="the-twelve-factor-application"></a>La aplicación Twelve-Factor

Una metodología ampliamente aceptada para construir aplicaciones basadas en la nube es la [aplicación de doce factores](https://12factor.net/). Describe un conjunto de principios y prácticas que los desarrolladores siguen para crear aplicaciones optimizadas para entornos modernos en la nube. Se presta especial atención a la portabilidad entre entornos y la automatización declarativa.

Aunque es aplicable a cualquier aplicación basada en Web, muchos profesionales consideran Twelve-Factor como una base sólida para la creación de aplicaciones nativas en la nube. Los sistemas basados en estos principios pueden implementar y escalar rápidamente y agregar características para reaccionar rápidamente a los cambios de mercado.

En la tabla siguiente se resalta la metodología de Twelve-Factor:

|    |  Factor | Explicación  |
| :-------- | :-------- | :-------- |
| 1 | Código base | Una única base de código para cada microservicio, almacenada en su propio repositorio. Con el control de versiones, se puede implementar en varios entornos (QA, ensayo, producción). |
| 2 | Dependencias | Cada microservicio aísla y empaqueta sus propias dependencias, y adopta los cambios sin afectar a todo el sistema. |
| 3 | Configurations  | La información de configuración se mueve fuera del microservicio y se externaliza a través de una herramienta de administración de configuración fuera del código. La misma implementación se puede propagar entre entornos con la configuración correcta aplicada.  |
| 4 | Servicios de respaldo | Los recursos auxiliares (almacenes de datos, memorias caché, agentes de mensajes) deben exponerse a través de una dirección URL direccionable. Al hacerlo, se desacopla el recurso de la aplicación, lo que permite que sea intercambiable.  |
| 5 | Compilación, lanzamiento, ejecución | Cada versión debe exigir una separación estricta entre las fases de compilación, lanzamiento y ejecución. Cada una debe etiquetarse con un identificador único y admitir la capacidad de revertir. Los sistemas de CI/CD modernos ayudan a completar este principio. |
| 6 | Procesos | Cada microservicio debe ejecutarse en su propio proceso, aislado de otros servicios en ejecución. Externalizar el estado necesario para un servicio de respaldo, como una caché distribuida o un almacén de datos. |
| 7 | Enlace de puerto | Cada microservicio debe ser independiente con las interfaces y la funcionalidad expuestas en su propio puerto. Esto proporciona aislamiento de otros microservicios. |
| 8 | Simultaneidad | Los servicios se escalan horizontalmente en un gran número de pequeños procesos (copias) idénticos en lugar de escalar verticalmente una única instancia grande en el equipo más eficaz disponible. |
| 9 | Eliminación | Las instancias de servicio deben ser descartables, con lo que se favorece el inicio rápido para aumentar las oportunidades de escalabilidad y cierres correctos para dejar el sistema en un estado correcto. Los contenedores de Docker junto con un orquestador cumplen de forma inherente este requisito. |
| 10 | Paridad de desarrollo y producción | Mantenga entornos a lo largo del ciclo de vida de la aplicación lo más similar posible, evitando accesos directos costosos. En este caso, la adopción de contenedores puede contribuir en gran medida a la promoción del mismo entorno de ejecución. |
| 11 | Registro | Tratar los registros generados por los microservicios como flujos de eventos. Procesarlos con un agregador de eventos y propagar los datos a herramientas de administración de datos y minería de datos, como Azure Monitor o Splunk y, finalmente, el archivo a largo plazo. |
| 12 | Procesos de administración | Ejecutar tareas administrativas o de administración como procesos de un solo uso. Las tareas pueden incluir la limpieza de datos y el análisis de extracción de un informe. Las herramientas que ejecutan estas tareas deben invocarse desde el entorno de producción, pero independientemente de la aplicación. |

En el libro, [más allá de la aplicación Twelve-Factor](https://content.pivotal.io/blog/beyond-the-twelve-factor-app), el autor Kevin Hoffman detalla cada uno de los 12 factores originales (escritos en 2011). Además, comenta tres factores adicionales que reflejan el diseño de la aplicación en la nube actual de hoy en día.

|    |  Nuevo factor | Explicación  |
| :-------- | :-------- | :-------- |
| 13 | Primera API | Haga todo un servicio. Suponga que el código lo utilizará un cliente front-end, una puerta de enlace u otro servicio. |
| 14 | Telemetría | En una estación de trabajo, tiene una visibilidad profunda de la aplicación y su comportamiento. En la nube, no. Asegúrese de que el diseño incluye la recopilación de datos de supervisión, específicos del dominio y del estado o del sistema. |
| 15 | Autenticación/autorización  | Implemente la identidad desde el principio. Tenga en cuenta las características de [RBAC (control de acceso basado en roles)](/azure/role-based-access-control/overview) disponibles en nubes públicas.  |

Haremos referencia a muchos de los 12 factores de este capítulo y a lo largo del libro.

### <a name="critical-design-considerations"></a>Consideraciones de diseño críticas

Además de las instrucciones proporcionadas en la metodología de doce factores, hay varias decisiones de diseño críticas que debe tomar al construir sistemas distribuidos.

*Comunicación*

¿Cómo se comunican las aplicaciones cliente front-end con los servicios principales de back-end? ¿Permitirá la comunicación directa? O bien, ¿puede abstraer los servicios back-end con una fachada de puerta de enlace que proporcione flexibilidad, control y seguridad?

¿Cómo se comunican los servicios principales de back-end entre sí? ¿Permitirá llamadas HTTP directas que conducen al acoplamiento y el impacto en el rendimiento y la agilidad? ¿O puede considerar la mensajería desacoplada con tecnologías de colas y temas?

La comunicación se trata en el capítulo 4 de detalles, *patrones de comunicación nativa en la nube*.

*Resistencia*

Una arquitectura de microservicios mueve el sistema desde el proceso a la comunicación de red fuera de proceso. En una arquitectura distribuida, ¿qué ocurre cuando el servicio B no responde a una llamada de red del servicio A? O bien, ¿qué ocurre cuando el servicio C deja de estar disponible temporalmente y se bloquean otros servicios que lo llaman?

La resistencia se trata en el capítulo 6 de detalles, *resistencia nativa en la nube*.

*Datos distribuidos*

Por diseño, cada microservicio encapsula sus propios datos y expone las operaciones a través de su interfaz pública. Si es así, ¿cómo se consultan los datos o se implementa una transacción en varios servicios?

Los datos distribuidos se describen en el capítulo 5 de detalles, *patrones de datos nativos de la nube*.

*Identidad*

¿Cómo identificará el servicio quién tiene acceso a él y qué permisos tiene?

La identidad se trata en el capítulo 8 de detalles, *identidad*.

## <a name="microservices"></a>Microservicios

Los sistemas nativos en la nube adoptan microservicios, un estilo arquitectónico popular para construir aplicaciones modernas.

Creado como un conjunto distribuido de servicios pequeños e independientes que interactúan a través de un tejido compartido, los microservicios comparten las siguientes características:

- Cada implementa una funcionalidad empresarial específica dentro de un contexto de dominio mayor.

- Cada se desarrolla de manera autónoma y se puede implementar de forma independiente.

- Cada una de ellas encapsula su propia tecnología de almacenamiento de datos (SQL, NoSQL) y plataforma de programación.

- Cada una de ellas se ejecuta en su propio proceso y se comunica con otros mediante protocolos de comunicación estándar como HTTP/HTTPS, WebSockets o [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol).

- Se componen conjuntamente para formar una aplicación.

La figura 1-4 contrasta un enfoque de aplicación monolítica con un enfoque de microservicios. Observe cómo el monolítico se compone de una arquitectura en capas, que se ejecuta en un único proceso. Normalmente utiliza una base de datos relacional. Sin embargo, el enfoque de microservicios segrega la funcionalidad en servicios independientes que incluyen lógica y datos. Cada microservicio hospeda su propio almacén de almacenes de los mismos.

![Implementación monolítica frente a microservicios](./media/monolithic-vs-microservices.png)

**Figura 1-4.** Implementación monolítica frente a microservicios

Tenga en cuenta cómo los microservicios promocionan el principio de "un código base, una aplicación" de la [aplicación de doce factores](https://12factor.net/), descrito anteriormente en el capítulo.

> *Factor \# 1 especifica "un único código base para cada microservicio, almacenado en su propio repositorio. Con el control de versiones, se puede implementar en varios entornos.*

### <a name="why-microservices"></a>¿Por qué microservicios?

Los microservicios proporcionan agilidad.

Anteriormente en el capítulo, se comparaba una aplicación de comercio electrónico compilada como un monolito con microservicios. En el ejemplo, vimos algunas ventajas claras:

- Cada microservicio tiene un ciclo de vida autónomo y puede evolucionar de forma independiente e implementar con frecuencia. No tiene que esperar a una versión trimestral para implementar nuevas características o actualizaciones. Puede actualizar un área pequeña de una aplicación compleja con menos riesgo de interrumpir todo el sistema.

- Cada microservicio se puede escalar de manera independiente. En lugar de escalar toda la aplicación como una sola unidad, solo se escalan horizontalmente los servicios que requieren más potencia de procesamiento o ancho de banda de red. Este enfoque específico del escalado proporciona un mayor control del sistema y ayuda a reducir los costos generales a medida que se escalan partes del sistema, no todo.

Una excelente guía de referencia para comprender los microservicios es [microservicios de .net: arquitectura para aplicaciones .net en contenedor](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook). El libro profundiza en el diseño y la arquitectura de los microservicios. Es un complemento para una [arquitectura de referencia de microservicios de pila completa](https://github.com/dotnet-architecture/eShopOnContainers) disponible como descarga gratuita de Microsoft.

### <a name="developing-microservices"></a>Desarrollo de microservicios

Los microservicios se pueden crear con cualquier plataforma de desarrollo moderna.

La plataforma Microsoft .NET es una excelente opción. Gratis y de código abierto, tiene muchas características integradas para simplificar el desarrollo de microservicios. .NET es multiplataforma. Las aplicaciones se pueden compilar y ejecutar en Windows, macOS y la mayoría de los tipos de Linux.

.NET tiene un alto rendimiento y ha puntuado bien en comparación con Node.js y otras plataformas de la competencia. Curiosamente, [TechEmpower](https://www.techempower.com/) llevó a cabo un amplio conjunto de pruebas comparativas de [rendimiento](https://www.techempower.com/benchmarks/#section=data-r17&hw=ph&test=plaintext) en muchas plataformas y marcos de aplicaciones Web. .NET puntuado en las 10 mejores Node.js y otras plataformas de la competencia.

.NET es mantenido por Microsoft y la comunidad de .NET en GitHub.

## <a name="containers"></a>Contenedores

En la actualidad, es natural oír el término *contenedor* mencionado en cualquier conversación con respecto a la *nube nativa*. En el libro, los [modelos nativos](https://www.manning.com/books/cloud-native-patterns)en la nube, Author Cornelia Davis observa que "los contenedores son un excelente habilitador del software nativo de la nube". Cloud Native Computing Foundation coloca la inclusión de microservicios como primer paso en su [mapa final nativo de la nube](https://raw.githubusercontent.com/cncf/trailmap/master/CNCF_TrailMap_latest.png) para las empresas que comienzan su viaje nativo en la nube.

El contenedor de un microservicio es sencillo y sencillo. El código, sus dependencias y el tiempo de ejecución se empaquetan en un archivo binario denominado [imagen de contenedor](https://docs.docker.com/glossary/?term=image). Las imágenes se almacenan en un [registro de contenedor](https://caylent.com/container-registries/), que actúa como un repositorio o una biblioteca de imágenes. Un registro puede encontrarse en el equipo de desarrollo, en el centro de datos o en una nube pública. Docker mantiene un registro público a través de [Docker Hub](https://hub.docker.com/). La nube de Azure incluye un [registro de contenedor](https://azure.microsoft.com/services/container-registry/) para almacenar imágenes de contenedor cerca de las aplicaciones en la nube que las ejecutarán.

Cuando sea necesario, transforme la imagen en una instancia de contenedor en ejecución. La instancia de se ejecuta en cualquier equipo que tenga instalado un motor de [tiempo de ejecución de contenedor](https://kubernetes.io/docs/setup/production-environment/container-runtimes/) . Puede tener tantas instancias del servicio en contenedor como sea necesario.

En la figura 1-5 se muestran tres microservicios diferentes, cada uno en su propio contenedor, que se ejecuta en un solo host.

![Varios contenedores ejecutándose en un host de contenedor.](./media/hosting-mulitple-containers.png)

**Figura 1-5**. Varios contenedores ejecutándose en un host de contenedor.

Observe cómo cada contenedor mantiene su propio conjunto de dependencias y tiempo de ejecución, que puede ser diferente. Aquí vemos diferentes versiones del microservicio de producto que se ejecutan en el mismo host. Cada contenedor comparte un segmento del sistema operativo host, la memoria y el procesador subyacentes, pero está aislado entre sí.

Tenga en cuenta que el modelo de contenedor adopta el principio "dependencias" de la [aplicación de doce factores](https://12factor.net/).

> *Factor \# 2 especifica que "cada microservicio aísla y empaqueta sus propias dependencias, adoptando cambios sin afectar al sistema completo".*

Los contenedores admiten cargas de trabajo de Windows y Linux. La nube de Azure adopta ambos. Curiosamente, es Linux, no Windows Server, que se ha convertido en el sistema operativo más popular de Azure.

Aunque existen varios proveedores de contenedores, Docker ha capturado el recurso compartido del León. La compañía ha estado llevando el movimiento del contenedor de software. Se ha convertido en el estándar de facto para empaquetar, implementar y ejecutar aplicaciones nativas en la nube.

### <a name="why-containers"></a>¿Por qué contenedores?

Los contenedores proporcionan una portabilidad y garantizan la coherencia entre entornos. Al encapsular todo en un único paquete, *aísla* el microservicio y sus dependencias de la infraestructura subyacente.

Puede implementar el mismo contenedor en cualquier entorno que tenga el motor de tiempo de ejecución de Docker. Las cargas de trabajo en contenedor también eliminan los gastos de la configuración previa de cada entorno con Marcos, bibliotecas de software y motores en tiempo de ejecución.

Al compartir el sistema operativo subyacente y los recursos de host, los contenedores tienen una superficie mucho menor que una máquina virtual completa. El tamaño más pequeño aumenta la *densidad*, o el número de microservicios, que un host determinado puede ejecutar al mismo tiempo.

### <a name="container-orchestration"></a>Orquestación de contenedores

Aunque herramientas como Docker crean imágenes y ejecutan contenedores, también se necesitan herramientas para administrarlas. La administración de contenedores se realiza con un programa de software especial denominado orquestador de contenedores. Cuando se trabaja a escala, la orquestación de contenedores es fundamental.

En la figura 1-6 se muestran las tareas de administración que proporcionan los orquestadores de contenedores.

![Qué hacen los orquestadores de contenedor](./media/what-container-orchestrators-do.png)

**Figura 1-6**. Qué hacen los orquestadores de contenedor

En la tabla siguiente se describen las tareas comunes de orquestación.

|  Tareas | Explicación  |
| :-------- | :-------- |
| Programación | Aprovisionar automáticamente las instancias de contenedor.|
| Afinidad/antiafinidad | Aprovisione contenedores cercanos o alejados entre sí, ayudando a la disponibilidad y al rendimiento. |
| Seguimiento de estado | Detectar y corregir errores automáticamente.|
| Conmutación por error | Reaprovisionamiento automático de la instancia con errores en máquinas correctas.|
| Ampliación | Agregue o quite automáticamente la instancia de contenedor para satisfacer la demanda.|
| Redes | Administrar una superposición de redes para la comunicación del contenedor.|
| Detección de servicios | Permite que los contenedores se localicen entre sí.|
| Actualizaciones sucesivas | Coordine actualizaciones incrementales con una implementación sin tiempo de inactividad. Revertir cambios problemáticos automáticamente.|

Tenga en cuenta cómo los orquestadores adoptan los principios de eliminación y simultaneidad de la [aplicación de doce factores](https://12factor.net/), descritos anteriormente en el capítulo.

> *Factor \# 9 especifica que "las instancias de servicio deben ser descartables, lo que favorece el inicio rápido para aumentar las oportunidades de escalabilidad y cierres correctos para dejar el sistema en un estado correcto. Los contenedores de Docker junto con un orquestador satisfacen de forma inherente este requisito ".*

> *Factor \# 8 especifica que "los servicios se escalan horizontalmente en un gran número de pequeños procesos idénticos (copias) en lugar de escalar verticalmente una única instancia grande en el equipo más eficaz disponible".*

Aunque existen varios orquestadores de contenedor, [Kubernetes](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/) se ha convertido en el estándar de facto para el mundo nativo de la nube. Es una plataforma portátil, extensible y de código abierto para administrar cargas de trabajo en contenedores.

Podría hospedar su propia instancia de Kubernetes, pero entonces debería ser responsable de aprovisionar y administrar sus recursos, lo que puede ser complejo. Las características de la nube de Azure Kubernetes como un servicio administrado, [Azure Kubernetes Service (AKS)](https://azure.microsoft.com/services/kubernetes-service/). Un servicio administrado le permite sacar el máximo partido de sus características, sin tener que instalarlas y mantenerlas.

Azure Kubernetes Services se describe en el capítulo 2 sobre el *escalado de Cloud-Native aplicaciones*.

## <a name="backing-services"></a>Servicios de respaldo

Los sistemas nativos en la nube dependen de muchos recursos auxiliares distintos, como almacenes de datos, agentes de mensajes, supervisión y servicios de identidad. Estos servicios se conocen como [servicios de respaldo](https://12factor.net/backing-services).

 En la figura 1-7 se muestran muchos servicios de respaldo comunes que consumen los sistemas nativos en la nube.

![Servicios comunes de respaldo](./media/common-backing-services.png)

**Figura 1-7**. Servicios comunes de respaldo

Los servicios de respaldo promocionan el principio "Estados" de la [aplicación de doce factores](https://12factor.net/), que se explicó anteriormente en el capítulo.

>*Factor \# 6* especifica que "cada microservicio debe ejecutarse en su propio proceso, aislado de otros servicios en ejecución. Externalizar el estado necesario para un servicio de respaldo, como una caché distribuida o un almacén de datos ".

Podría hospedar sus propios servicios de respaldo, pero a continuación se responsabilizaría de la concesión de licencias, el aprovisionamiento y la administración de esos recursos.

Los proveedores de nube ofrecen una amplia variedad de *servicios de respaldo administrados.* En lugar de poseer el servicio, simplemente se usa. El proveedor opera el recurso a escala y asume la responsabilidad del rendimiento, la seguridad y el mantenimiento. La supervisión, la redundancia y la disponibilidad están integradas en el servicio. Los proveedores son totalmente compatibles con sus servicios administrados. Abra un vale y solucione el problema.

Los sistemas nativos en la nube favorecen los servicios de respaldo administrados de los proveedores de la nube. El ahorro en el tiempo y la mano de obra son excelentes. El riesgo operativo de hospedar el suyo propio y experimentar problemas puede resultar caro.

Un procedimiento recomendado consiste en tratar un servicio de respaldo como un *recurso adjunto*, enlazado dinámicamente a un microservicio con información (una dirección URL y credenciales) almacenada en una configuración externa. Esta guía se ha escrito en la [aplicación de doce factores](https://12factor.net/), descrita anteriormente en el capítulo.

>*Factor \# 4* especifica que los servicios de respaldo deben exponerse a través de una dirección URL direccionable. Al hacerlo, se desacopla el recurso de la aplicación, lo que permite que sea intercambiable. "

>*Factor \# 3* especifica que "la información de configuración se mueve fuera del microservicio y se externaliza a través de una herramienta de administración de configuración fuera del código".

Con este patrón, un servicio de respaldo se puede adjuntar y separar sin cambios de código. Puede promover un microservicio de QA a un entorno de ensayo. Actualice la configuración del microservicio para que apunte a los servicios de respaldo en el almacenamiento provisional e inserte la configuración en el contenedor a través de una variable de entorno.

Los proveedores de nube proporcionan las API para que pueda comunicarse con sus servicios de respaldo. Estas bibliotecas encapsulan la infraestructura y la complejidad. La comunicación directa con estas API acoplará estrechamente el código al servicio de respaldo. Es aconsejable aislar los detalles de implementación de la API del proveedor. Introduzca una capa de intermediación, o una API intermedia, que exponga las operaciones genéricas en el código de servicio. Este acoplamiento flexible le permite intercambiar un servicio de respaldo para otro o trasladar el código a una nube pública diferente sin tener que realizar cambios en el código del servicio principal.

Los servicios de respaldo se describen en el capítulo 5 de detalle, *patrones de datos nativos de la nube* y el capítulo 4, *patrones de comunicación nativa en la nube*.

## <a name="automation"></a>Automation

Como ha visto, los sistemas nativos en la nube adoptan microservicios, contenedores y un diseño moderno del sistema para lograr la velocidad y la agilidad. Pero eso es solo parte de la historia. ¿Cómo se aprovisionan los entornos de nube en los que se ejecutan estos sistemas? ¿Cómo se implementan rápidamente características y actualizaciones de aplicaciones? ¿Cómo se redondea la imagen completa?

Escriba la práctica ampliamente aceptada de [infraestructura como código](/azure/devops/learn/what-is-infrastructure-as-code)o IaC.

Con IaC, puede automatizar el aprovisionamiento de plataforma y la implementación de aplicaciones. Esencialmente, aplica prácticas de ingeniería de software, como pruebas y control de versiones a las prácticas de DevOps. La infraestructura y las implementaciones son automatizadas, coherentes y repetibles.

### <a name="automating-infrastructure"></a>Automatización de la infraestructura

Herramientas como [Azure Resource Manager](/azure/azure-resource-manager/management/overview), terraform y el [CLI de Azure](/cli/azure/)le permiten crear un script de la infraestructura de la nube que necesita mediante declaración. Los nombres de los recursos, las ubicaciones, las capacidades y los secretos son parametrizados y dinámicos. El script tiene versiones y se protege en el control de código fuente como un artefacto del proyecto. El script se invoca para aprovisionar una infraestructura coherente y repetible entre entornos del sistema, como el QA, el ensayo y la producción.

En el capó, IaC es idempotente, lo que significa que puede ejecutar el mismo script una y otra vez sin efectos secundarios. Si el equipo necesita efectuar un cambio, edite y vuelva a ejecutar el script. Solo se ven afectados los recursos actualizados.

En el artículo [¿Qué es la infraestructura como código](/azure/devops/learn/what-is-infrastructure-as-code)? Author Sam Guckenheimer describe cómo "los equipos que implementan IaC pueden ofrecer entornos estables rápidamente y a escala. Los equipos evitan la configuración manual de los entornos y aplican la coherencia al representar el estado deseado de sus entornos a través del código. Las implementaciones de infraestructura con IaC se pueden repetir y evitan problemas en tiempo de ejecución causados por el desfase de la configuración o las dependencias que faltan. Los equipos de DevOps pueden trabajar junto con un conjunto unificado de prácticas y herramientas para ofrecer aplicaciones y su infraestructura de soporte de forma rápida, confiable y a escala ".

### <a name="automating-deployments"></a>Automatizar implementaciones

La [aplicación de doce factores](https://12factor.net/), descrita anteriormente, llama a pasos independientes al transformar el código completado en una aplicación en ejecución.

> *Factor \# 5* especifica que "cada versión debe exigir una separación estricta entre las fases de compilación, lanzamiento y ejecución. Cada una debe etiquetarse con un identificador único y admitir la capacidad de revertir ".

Los sistemas de CI/CD modernos ayudan a completar este principio. Proporcionan pasos de implementación independientes y ayudan a garantizar un código coherente y de calidad que esté disponible para los usuarios.

En la figura 1-8 se muestra la separación en todo el proceso de implementación.

![Pasos de las implementaciones en la canalización de CI/CD](./media/build-release-run-pipeline.png)

**Figura 1-8**. Pasos de implementación en una canalización de CI/CD

En la ilustración anterior, preste especial atención a la separación de tareas.

El desarrollador crea una característica en su entorno de desarrollo, que recorre en iteración lo que se denomina "bucle interno" del código, la ejecución y la depuración. Cuando haya finalizado, ese código se *inserta* en un repositorio de código, como github, Azure DevOps o BitBucket.

La inserciones desencadena una fase de compilación que transforma el código en un artefacto binario. El trabajo se implementa con una canalización de [integración continua (CI)](https://martinfowler.com/articles/continuousIntegration.html) . Compila, prueba y empaqueta la aplicación automáticamente.

En la fase de lanzamiento se recoge el artefacto binario, se aplica la información de configuración del entorno y la aplicación externa, y se genera una versión inmutable. La versión se implementa en un entorno especificado. El trabajo se implementa con una canalización de [entrega continua (CD)](https://martinfowler.com/bliki/ContinuousDelivery.html) . Cada versión debe ser identificable. Puede decir que "esta implementación está ejecutando la versión 2.1.1 de la aplicación".

Por último, la característica publicada se ejecuta en el entorno de ejecución de destino. Las versiones son inmutables, lo que significa que cualquier cambio debe crear una nueva versión.

Al aplicar estos procedimientos, las organizaciones han evolucionado radicalmente el modo en que envían el software. Muchos se han pasado de las versiones trimestrales a las actualizaciones a petición. El objetivo es detectar los problemas al principio del ciclo de desarrollo cuando son menos costosos de corregir. Cuanto mayor sea la duración entre integraciones, más caros serán los problemas que se resuelvan.  Con coherencia en el proceso de integración, los equipos pueden confirmar los cambios de código con más frecuencia, con lo que se mejora la colaboración y la calidad del software.

### <a name="azure-pipelines"></a>Azure Pipelines

La nube de Azure incluye un nuevo servicio de CI/CD titulado [Azure pipelines](https://azure.microsoft.com/services/devops/pipelines/), que forma parte de la oferta [DevOps de Azure](https://azure.microsoft.com/services/devops/) que se muestra en la figura 1-9.

![Azure Pipelines en DevOps](./media/devops-components.png)

**Figura 1-9**. Ofertas de Azure DevOps

Azure Pipelines es un servicio en la nube que combina la integración continua (CI) y la entrega continua (CD). Puede probar, compilar y enviar automáticamente el código a cualquier destino.

La canalización se define en el código de un archivo YAML junto con el resto del código de la aplicación.

- La versión de la canalización tiene el código y sigue la misma estructura de bifurcación.
- La validación de los cambios se obtiene a través de revisiones de código en solicitudes de extracción y directivas de compilación de rama.
- Cada rama que use puede personalizar la Directiva de compilación modificando el archivo Azure-pipelines. yml.
- El archivo de canalización se protege en el control de versiones y se puede investigar si hay un problema.

El servicio Azure Pipelines es compatible con la mayoría de los proveedores de Git y puede generar canalizaciones de implementación para aplicaciones escritas en las plataformas Linux, macOS o Windows. Incluye compatibilidad con Java, .NET, JavaScript, Python, PHP, Go, XCode y C++.

>[!div class="step-by-step"]
>[Anterior](introduction.md)
>[Siguiente](candidate-apps.md)
