---
title: Definición de nativo en la nube
description: Conozca los pilares fundamentales que proporcionan la base para los sistemas nativos de la nube
author: robvet
ms.date: 08/20/2019
ms.openlocfilehash: 756a2565bd77fcef19a5f15579987836ff0e75a4
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989095"
---
# <a name="defining-cloud-native"></a>Definición de la nube nativa

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Deja de hacer lo que estás haciendo y envía un mensaje de texto a diez de tus colegas. Pídales que definan el término "Nativo de la nube". Es muy probable que obtengas ocho respuestas diferentes.

Cloud native consiste en cambiar la forma en que pensamos en la construcción de sistemas empresariales críticos.

Los sistemas nativos de la nube están diseñados para adoptar cambios rápidos, a gran escala y resiliencia.

Cloud Native Computing Foundation proporciona una [definición oficial:](https://github.com/cncf/foundation/blob/master/charter.md)

> *Las tecnologías nativas de la nube permiten a las organizaciones crear y ejecutar aplicaciones escalables en entornos modernos y dinámicos, como nubes públicas, privadas e híbridas. Los contenedores, las mallas de servicio, los microservicios, la infraestructura inmutable y las API declarativas ejemplifican este enfoque.*

> *Estas técnicas permiten sistemas acoplados libremente que son resistentes, manejables y observables. En combinación con una automatización robusta, permiten a los ingenieros realizar cambios de alto impacto con frecuencia y predicción con un mínimo trabajo.*

Las aplicaciones se han vuelto cada vez más complejas con los usuarios que exigen cada vez más. Los usuarios esperan una rápida capacidad de respuesta, características innovadoras y cero tiempo de inactividad. Los problemas de rendimiento, los errores recurrentes y la incapacidad de moverse rápido ya no son aceptables. Se moverán fácilmente a su competidor.

Nube nativa es mucho acerca de *la velocidad* y *la agilidad.* Los sistemas empresariales están evolucionando desde la habilitación de capacidades empresariales hasta las armas de transformación estratégica, la aceleración de la velocidad del negocio y el crecimiento. Es imperativo llevar las ideas al mercado de inmediato.

Estas son algunas empresas que han implementado estas técnicas. Piense en la velocidad, agilidad y escalabilidad que han logrado.

| Compañía | Experiencia |
| :-------- | :-------- |
| [Netflix](https://www.infoq.com/news/2013/06/netflix/) | Tiene más de 600 servicios en producción. Se despliega cien veces al día. |
| [Uber](https://eng.uber.com/micro-deploy/) | Tiene más de 1.000 servicios almacenados en producción. Implementa varios miles de compilaciones cada semana. |
| [WeChat](https://www.cs.columbia.edu/~ruigu/papers/socc18-final100.pdf) | Tiene más de 300 servicios en producción. Realiza casi 1.000 cambios al día. |

Como puede ver, Netflix, Uber y WeChat exponen sistemas que constan de cientos de microservicios independientes. Este estilo arquitectónico les permite responder rápidamente a las condiciones del mercado. Pueden actualizar instantáneamente áreas pequeñas de una aplicación en vivo y compleja, y escalar individualmente esas áreas según sea necesario.

La velocidad y agilidad de la nube nativa provienede una serie de factores. En su mayoría, la infraestructura en la nube. Cinco pilares fundamentales adicionales que se muestran en la Figura 1-3 también proporcionan la base para los sistemas nativos de la nube.

![Pilares fundamentales nativos de la nube](./media/cloud-native-foundational-pillars.png)

**Figura 1-3**. Pilares fundamentales nativos de la nube

Tomemos un tiempo para entender mejor la importancia de cada pilar.

## <a name="the-cloud"></a>La nube...

Los sistemas nativos de la nube aprovechan al máximo el modelo de servicio en la nube.

Diseñados para prosperar en un entorno de nube dinámico y virtualizado, estos sistemas hacen un uso extensivo de la infraestructura informática de [plataforma como servicio (PaaS)](https://azure.microsoft.com/overview/what-is-paas/) y los servicios administrados. Tratan la infraestructura subyacente como *desechable* - aprovisionada en minutos y redimensionada, escalada, movida o destruida a petición – a través de la automatización.

Considere el concepto de DevOps ampliamente aceptado de [Mascotas vs.](https://medium.com/@Joachim8675309/devops-concepts-pets-vs-cattle-2380b5aab313) En un centro de datos tradicional, los servidores se tratan como *mascotas:* una máquina física, con un nombre significativo, y cuidado. Puede escalar agregando más recursos a la misma máquina (escalado vertical). Si el servidor se enferma, vuelve a cuidarlo. Si el servidor deja de estar disponible, todos se dan cuenta.

El modelo de servicio *de ganado* es diferente. Aprovisione cada instancia como una máquina virtual o un contenedor. Son idénticos y se les asigna un identificador del sistema como Service-01, Service-02, etc. Puede escalar creando más de ellos (escalado hacia fuera). Cuando uno deja de estar disponible, nadie se da cuenta.

El modelo ganadero abarca una *infraestructura inmutable.* Los servidores no se reparan ni modifican. Si uno falla o requiere actualización, se destruye y se aprovisiona uno nuevo, todo hecho a través de la automatización.

Los sistemas nativos de la nube adoptan el modelo de servicio de ganado. Siguen ejecutándose a medida que la infraestructura se escala dentro o fuera sin tener en cuenta las máquinas en las que se ejecutan.

La plataforma en la nube de Azure admite este tipo de infraestructura altamente elástica con capacidades de escalado automático, recuperación automática y supervisión.

## <a name="modern-design"></a>Diseño moderno

¿Cómo diseñaría una aplicación nativa de la nube? ¿Cómo sería su arquitectura? ¿A qué principios, patrones y mejores prácticas se adherirían? ¿Qué preocupaciones operativas y de infraestructura serían importantes?

### <a name="the-twelve-factor-application"></a>La aplicación de doce factores

Una metodología ampliamente aceptada para la construcción de aplicaciones basadas en la nube es la [aplicación de doce factores.](https://12factor.net/) Describe un conjunto de principios y prácticas que los desarrolladores siguen para construir aplicaciones optimizadas para entornos de nube modernos. Se presta especial atención a la portabilidad en todos los entornos y a la automatización declarativa.

Aunque es aplicable a cualquier aplicación basada en web, muchos profesionales la consideran como una base sólida para crear aplicaciones nativas de la nube. Los sistemas basados en estos principios pueden implementarse y escalar rápidamente y agregar características para reaccionar rápidamente a los cambios del mercado.

La siguiente tabla destaca la metodología Twelve-Factor:

|    |  Factor | Explicación  |
| :-------- | :-------- | :-------- |
| 1 | Base de código | Una única base de código para cada microservicio, almacenada en su propio repositorio. Rastreado con control de versiones, se puede implementar en varios entornos (QA, Staging, Production). |
| 2 | Dependencias | Cada microservicio aísla y empaqueta sus propias dependencias, abarcando los cambios sin afectar a todo el sistema. |
| 3 | Configurations  | La información de configuración se mueve fuera del microservicio y se externaliza a través de una herramienta de administración de configuración fuera del código. La misma implementación puede propagarse entre entornos con la configuración correcta aplicada.  |
| 4 | Servicios de respaldo | Los recursos auxiliares (almacenes de datos, cachés, agentes de mensajes) deben exponerse a través de una dirección URL direccionable. Al hacerlo, se desacopla el recurso de la aplicación, lo que permite que sea intercambiable.  |
| 5 | Construir, Liberar, Ejecutar | Cada versión debe aplicar una separación estricta entre las etapas de compilación, versión y ejecución. Cada uno debe ser etiquetado con un identificador único y apoyar la capacidad de revertir. Los sistemas CI/CD modernos ayudan a cumplir este principio. |
| 6 | Procesos | Cada microservicio debe ejecutarse en su propio proceso, aislado de otros servicios en ejecución. Externalice el estado necesario a un servicio de respaldo, como una caché distribuida o un almacén de datos. |
| 7 | Enlace de puerto | Cada microservicio debe ser independiente con sus interfaces y funcionalidad expuestas en su propio puerto. Al hacerlo, se proporciona aislamiento de otros microservicios. |
| 8 | Simultaneidad | Los servicios se escalan horizontalmente en un gran número de pequeños procesos idénticos (copias) en lugar de escalar verticalmente una sola instancia grande en la máquina más potente disponible. |
| 9 | Disipabilidad | Las instancias de servicio deben ser desechables, lo que favorece las startups rápidas para aumentar las oportunidades de escalabilidad y los cierres correctos para dejar el sistema en un estado correcto. Los contenedores de Docker junto con un orquestador satisfacen intrínsecamente este requisito. |
| 10 | Paridad de desarrollo/prod | Mantenga los entornos a lo largo del ciclo de vida de la aplicación de la forma más similar posible, evitando costosos accesos directos. Aquí, la adopción de contenedores puede contribuir en gran medida promoviendo el mismo entorno de ejecución. |
| 11 | Registro | Tratar los registros generados por microservicios como secuencias de eventos. Procéselos con un agregador de eventos y propague los datos a herramientas de administración de registros y minería de datos como Azure Monitor o Splunk y, finalmente, al archivo a largo plazo. |
| 12 | Procesos de administración | Ejecute tareas administrativas/administrativas como procesos únicos. Las tareas pueden incluir la limpieza de datos y el análisis de extracción de un informe. Las herramientas que ejecutan estas tareas deben invocarse desde el entorno de producción, pero por separado de la aplicación. |

En el libro, [Beyond the Twelve-Factor App](https://content.pivotal.io/blog/beyond-the-twelve-factor-app), el autor Kevin Hoffman detalla cada uno de los 12 factores originales (escritos en 2011). Además, el libro proporciona tres factores adicionales que reflejan el diseño moderno de aplicaciones en la nube de hoy en día.

|    |  Nuevo factor | Explicación  |
| :-------- | :-------- | :-------- |
| 13 | API Primero | Haz de todo un servicio. Supongamos que el código lo consumirá un cliente front-end, una puerta de enlace u otro servicio. |
| 14 | Telemetría | En una estación de trabajo, tiene una visibilidad profunda de la aplicación y su comportamiento. En la nube, no lo haces. Asegúrese de que el diseño incluye la recopilación de datos de supervisión, específicos del dominio y de estado/sistema. |
| 15 | Autenticación/Autorización  | Implemente la identidad desde el principio. Considere las características [RBAC (control](https://docs.microsoft.com/azure/role-based-access-control/overview) de acceso basado en roles) disponibles en las nubes públicas.  |

Nos referiremos a muchos de los más de 12 factores de este capítulo y a lo largo del libro.

### <a name="critical-design-considerations"></a>Consideraciones de diseño crítico

Más allá de la orientación proporcionada a partir de la metodología de doce factores, hay varias decisiones de diseño críticas que debe tomar al construir sistemas distribuidos.

*Comunicación*

¿Cómo se comunicarán las aplicaciones de cliente front-end con los servicios principales de backed-end? ¿Permitirá la comunicación directa? O bien, ¿podría abstraer los servicios back-end con una fachada de puerta de enlace que proporcione flexibilidad, control y seguridad?

¿Cómo se comunicarán los servicios básicos back-end entre sí? ¿Permitirá llamadas HTTP directas que conduzcan al acoplamiento y al impacto del rendimiento y la agilidad? ¿O podría considerar la mensajería desacoplada con tecnologías de colas y temas?

La comunicación se trata en detalle Capítulo 4, *Patrones de comunicación nativos de la nube.*

*Resistencia*

Una arquitectura de microservicios mueve el sistema de la comunicación en proceso a la red. En un entorno distribuido, ¿qué hará cuando el Servicio B no responda a una llamada del Servicio A? ¿Qué sucede cuando el servicio C deja de estar disponible temporalmente y otros servicios que lo llaman apilar y degradar el rendimiento del sistema?

La resistencia se trata en detalle el Capítulo 6, *Resiliencia nativa de*la nube.

*Datos distribuidos*

Por diseño, cada microservicio encapsula sus propios datos, exponiendo las operaciones a través de su interfaz pública. Si es así, ¿cómo consulta datos o implementa una transacción en varios servicios?

Los datos distribuidos se tratan en detalle El Capítulo 5, *Patrones de datos nativos*de la nube.

*Identidad*

¿Cómo identificará su servicio quién accede a él y qué permisos tienen?

La identidad se trata en detalle Capítulo 8, *Identidad*.

## <a name="microservices"></a>Microservicios

Los sistemas nativos de la nube adoptan microservicios, un estilo arquitectónico popular para la construcción de aplicaciones modernas.

Creados como un conjunto distribuido de servicios pequeños e independientes que interactúan a través de un tejido compartido, los microservicios comparten las siguientes características:

- Cada uno implementa una capacidad de negocio específica dentro de un contexto de dominio más grande.

- Cada uno se desarrolla de forma autónoma y se puede desplegar de forma independiente.

- Cada uno es independiente encapsulando su propia tecnología de almacenamiento de datos (SQL, NoSQL) y la plataforma de programación.

- Cada uno se ejecuta en su propio proceso y se comunica con otros usuarios mediante protocolos de comunicación estándar como HTTP/HTTPS, WebSockets o [AMQP.](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol)

- Se componen juntos para formar una aplicación.

La figura 1-4 contrasta un enfoque de aplicación monolítico con un enfoque de microservicios. Observe cómo el monolito se compone de una arquitectura en capas, que se ejecuta en un único proceso. Normalmente consume una base de datos relacional. Sin embargo, el enfoque de microservicios segrega la funcionalidad en servicios independientes que incluyen lógica y datos. Cada microservicio hospeda su propio almacén de datos.

![Implementación monolítica frente a microservicios](./media/monolithic-vs-microservices.png)

**Figura 1-4.** Implementación monolítica frente a microservicios

Observe cómo los microservicios promueven el principio "Una base de código, una aplicación" de la [aplicación de doce factores](https://12factor.net/), que se describe anteriormente en el capítulo.

> *El \#factor 1 especifica "un único código base para cada microservicio, almacenado en su propio repositorio. Rastreado con control de versiones, se puede implementar en varios entornos."*

### <a name="why-microservices"></a>¿Por qué microservicios?

Los microservicios proporcionan agilidad.

Anteriormente en el capítulo, comparamos una aplicación de comercio electrónico creada como un monolito con la de los microservicios. En el ejemplo, vimos algunos beneficios claros:

- Cada microservicio tiene un ciclo de vida autónomo y puede evolucionar de forma independiente e implementarse con frecuencia. No tiene que esperar a que una versión trimestral implemente una nueva característica o actualización. Puede actualizar un área pequeña de una aplicación compleja con menos riesgo de interrumpir todo el sistema.

- Cada microservicio puede escalar de forma independiente. En lugar de escalar toda la aplicación como una sola unidad, escale horizontalmente solo aquellos servicios que requieren más potencia de procesamiento o ancho de banda de red. Este enfoque detallado para el escalado proporciona un mayor control de su sistema y ayuda a reducir los costos generales a medida que escala partes de su sistema, no todo.

Una excelente guía de referencia para comprender los microservicios es [.NET Microservices: Architecture for Containerized .NET Applications](https://docs.microsoft.com/dotnet/standard/microservices-architecture/). El libro profundiza en el diseño y la arquitectura de los microservicios. Es un complemento para una arquitectura de referencia de [microservicio de pila completa](https://github.com/dotnet-architecture/eShopOnContainers) disponible como descarga gratuita de Microsoft.

### <a name="developing-microservices"></a>Desarrollo de microservicios

Los microservicios se pueden crear con cualquier plataforma de desarrollo moderna.

La plataforma Microsoft .NET Core es una excelente opción. Libre y de código abierto, tiene muchas características integradas para simplificar el desarrollo de microservicios. .NET Core es multiplataforma. Las aplicaciones se pueden compilar y ejecutar en Windows, macOS y la mayoría de los sabores de Linux.

.NET Core es de alto rendimiento y ha puntuado bien en comparación con Node.js y otras plataformas de la competencia. Curiosamente, [TechEmpower](https://www.techempower.com/) llevó a cabo un amplio conjunto de [puntos](https://www.techempower.com/benchmarks/#section=data-r17&hw=ph&test=plaintext) de referencia de rendimiento en muchas plataformas y marcos de aplicaciones web. .NET Core obtuvo una puntuación en el top 10, muy por encima de Node.js y otras plataformas de la competencia.

Microsoft y la comunidad de .NET manteniendo .NET Core en GitHub.

## <a name="containers"></a>Contenedores

Hoy en día, es natural escuchar el término *contenedor* mencionado en cualquier conversación sobre *la nube nativa.* En el libro, [Cloud Native Patterns](https://www.manning.com/books/cloud-native-patterns), la autora Cornelia Davis observa que "Los contenedores son un gran facilitador del software nativo de la nube." Cloud Native Computing Foundation coloca la contenedorización de microservicios como el primer paso de su mapa de [seguimiento nativo](https://raw.githubusercontent.com/cncf/trailmap/master/CNCF_TrailMap_latest.png) de la nube: guía para las empresas que comienzan su viaje nativo de la nube.

El contenedor de un microservicio es simple y sencillo. El código, sus dependencias y el tiempo de ejecución se empaquetan en un binario denominado imagen de [contenedor.](https://docs.docker.com/glossary/?term=image) Las imágenes se almacenan en un registro de [contenedor,](https://caylent.com/container-registries/)que actúa como repositorio o biblioteca para imágenes. Un registro se puede encontrar en el equipo de desarrollo, en el centro de datos o en una nube pública. Docker mantiene un registro público a través de [Docker Hub.](https://hub.docker.com/) La nube de Azure cuenta con un registro de [contenedor](https://azure.microsoft.com/services/container-registry/) para almacenar imágenes de contenedor cerca de las aplicaciones en la nube que las ejecutarán.

Cuando sea necesario, transforme la imagen en una instancia de contenedor en ejecución. La instancia se ejecuta en cualquier equipo que tenga instalado un motor de tiempo de ejecución de [contenedor.](https://kubernetes.io/docs/setup/production-environment/container-runtimes/) Puede tener tantas instancias del servicio en contenedores como sea necesario.

En la figura 1-5 se muestran tres microservicios diferentes, cada uno en su propio contenedor, que se ejecutan en un único host.

![Varios contenedores ejecutándose en un host de contenedor.](./media/hosting-mulitple-containers.png)

**Figura 1-5**. Varios contenedores ejecutándose en un host de contenedor.

Observe cómo cada contenedor mantiene su propio conjunto de dependencias y tiempo de ejecución, que puede ser diferente. Aquí, vemos diferentes versiones del microservicio de producto que se ejecutan en el mismo host. Cada contenedor comparte un segmento del sistema operativo, la memoria y el procesador del host subyacente, pero está aislado entre sí.

Observe lo bien que el modelo de contenedor adopta el principio "Dependencias" de la [aplicación de doce factores.](https://12factor.net/)

> *El \#factor 2 especifica que "cada microservicio aísla y empaqueta sus propias dependencias, abarcando los cambios sin afectar a todo el sistema."*

Los contenedores admiten cargas de trabajo de Linux y Windows. La nube de Azure abarca abiertamente ambas. Curiosamente, es Linux, no Windows Server, el que se ha convertido en el sistema operativo más popular de Azure.

Mientras existen varios proveedores de contenedores, Docker ha capturado la mayor parte del mercado. La compañía ha estado impulsando el movimiento de contenedores de software. Se ha convertido en el estándar de facto para empaquetar, implementar y ejecutar aplicaciones nativas de la nube.

### <a name="why-containers"></a>¿Por qué contenedores?

Los contenedores proporcionan portabilidad y garantizan la coherencia en todos los entornos. Al encapsular todo en un único paquete, *se aísla* el microservicio y sus dependencias de la infraestructura subyacente.

Puede implementar ese mismo contenedor en cualquier entorno que tenga el motor en tiempo de ejecución de Docker. Las cargas de trabajo en contenedores también eliminan el gasto de preconfigurar cada entorno con marcos de trabajo, bibliotecas de software y motores en tiempo de ejecución.

Al compartir el sistema operativo subyacente y los recursos de host, los contenedores tienen un espacio mucho menor que una máquina virtual completa. El tamaño más pequeño aumenta la *densidad*o el número de microservicios que un host determinado puede ejecutar a la vez.

### <a name="container-orchestration"></a>Orquestación de contenedores

Aunque herramientas como Docker crean imágenes y ejecutan contenedores, también necesita herramientas para administrarlas. La gestión de contenedores se realiza con un programa de software especial llamado orquestador de contenedores. Cuando se opera a escala, la orquestación de contenedores es esencial.

En la figura 1-6 se muestran las tareas de administración que proporcionan los orquestadores de contenedores.

![Qué hacen los orquestadores de contenedores](./media/what-container-orchestrators-do.png)

**Figura 1-6**. Qué hacen los orquestadores de contenedores

En la tabla siguiente se describen las tareas de orquestación comunes.

|  Tareas | Explicación  |
| :-------- | :-------- |
| Scheduling | Aprovisione automáticamente instancias de contenedor.|
| Afinidad/antiafinidad | Aprovisione contenedores cerca o lejos entre sí, lo que ayuda a la disponibilidad y el rendimiento. |
| Supervisión del estado | Detecte y corrija automáticamente los errores.|
| Conmutación por error | Reaprovisionar automáticamente la instancia con errores en las máquinas en buen estado.|
| Ampliación | Agregue o quite automáticamente la instancia de contenedor para satisfacer la demanda.|
| Redes | Gestione una superposición de redes para la comunicación de contenedores.|
| Detección de servicios | Habilite los contenedores para localizarse entre sí.|
| Actualizaciones sucesivas | Coordine las actualizaciones incrementales con la implementación sin tiempo de inactividad. Revierta automáticamente los cambios problemáticos.|

Observe cómo los orquestadores adoptan los principios de dispensabilidad y simultaneidad de la aplicación de factor esdoce-factor, que se describen anteriormente en el capítulo. [Twelve-Factor Application](https://12factor.net/)

> *El \#factor 9 especifica que "las instancias de servicio deben ser desechables, favoreciendo a las startups rápidas para aumentar las oportunidades de escalabilidad y los cierres correctos para dejar el sistema en un estado correcto. Los contenedores de Docker junto con un orquestador satisfacen intrínsecamente este requisito."*

> *El \#factor 8 especifica que "los servicios se escalan horizontalmente en un gran número de pequeños procesos idénticos (copias) en lugar de escalar verticalmente una sola instancia grande en la máquina más potente disponible."*

Mientras existen varios orquestadores de [contenedores, Kubernetes](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/) se ha convertido en el estándar de facto para el mundo nativo de la nube. Es una plataforma portátil, extensible y de código abierto para administrar cargas de trabajo en contenedores.

Podría hospedar su propia instancia de Kubernetes, pero entonces sería responsable de aprovisionar y administrar sus recursos, lo que puede ser complejo. La nube de Azure incluye Kubernetes como un servicio administrado, [Azure Kubernetes Service (AKS)](https://azure.microsoft.com/services/kubernetes-service/). Un servicio administrado le permite aprovechar plenamente sus características, sin tener que instalarlo y mantenerlo.

Azure Kubernetes Services se describe en detalle en el Capítulo 2, Escalado de *aplicaciones nativas de la nube.*

## <a name="backing-services"></a>Servicios de respaldo

Los sistemas nativos de la nube dependen de muchos recursos auxiliares diferentes, como almacenes de datos, agentes de mensajes, supervisión y servicios de identidad. Estos servicios se conocen como [servicios de respaldo.](https://12factor.net/backing-services)

 La figura 1-7 muestra muchos servicios de respaldo comunes que consumen los sistemas nativos de la nube.

![Servicios comunes de apoyo](./media/common-backing-services.png)

**Figura 1-7**. Servicios comunes de apoyo

Los servicios de respaldo promueven el principio de "apátrida" de la [Aplicación de Doce Factores,](https://12factor.net/)que se discutió anteriormente en el capítulo.

>*El \#factor 6* especifica que "cada microservicio debe ejecutarse en su propio proceso, aislado de otros servicios en ejecución. Externalice el estado requerido a un servicio de respaldo, como una memoria caché distribuida o un almacén de datos."

Puede hospedar sus propios servicios de respaldo, pero entonces sería responsable de la concesión de licencias, el aprovisionamiento y la administración de esos recursos.

Los proveedores de nube ofrecen una amplia variedad de servicios de *respaldo administrado.* En lugar de poseer el servicio, simplemente lo consume. El proveedor opera el recurso a escala y asume la responsabilidad de rendimiento, seguridad y mantenimiento. La supervisión, la redundancia y la disponibilidad están integradas en el servicio. Los proveedores son totalmente compatibles con sus servicios administrados: abra un ticket y solucione el problema.

Los sistemas nativos de la nube favorecen los servicios de respaldo administrados de los proveedores de la nube. El ahorro de tiempo y mano de obra es grande. El riesgo operativo de alojar los suyos y experimentar problemas puede ser costoso rápidamente.

Una práctica recomendada es tratar un servicio de respaldo como un *recurso adjunto,* enlazado dinámicamente a un microservicio con información (una dirección URL y credenciales) almacenada en una configuración externa. Esta guía se describe en la [Aplicación de Doce Factores,](https://12factor.net/)que se describe anteriormente en el capítulo.

>*El \#factor 4* especifica que los servicios de respaldo "deben exponerse a través de una dirección URL direccionable. Al hacerlo, se desacopla el recurso de la aplicación, lo que permite que sea intercambiable."

>*El \#factor 3* especifica que "la información de configuración se mueve fuera del microservicio y se externaliza a través de una herramienta de administración de configuración fuera del código."

Con este patrón, se puede adjuntar y desasociar un servicio de respaldo sin cambios de código. Puede promover un microservicio desde QA a un entorno de ensayo. Actualice la configuración de microservicio para que apunte a los servicios de respaldo en el almacenamiento provisional e inserte la configuración en el contenedor a través de una variable de entorno.

Los proveedores de nube proporcionan API para que pueda comunicarse con sus servicios de respaldo propietarios. Estas bibliotecas encapsulan la fontanería y la complejidad. La comunicación directa con estas API acoplará estrechamente el código al servicio de respaldo. Es una mejor práctica aislar los detalles de implementación de la API del proveedor. Introducir una capa de intermediación, o API intermedia, que exponga operaciones genéricas al código de servicio. Este acoplamiento flexible le permite intercambiar un servicio de respaldo por otro o mover el código a una nube pública diferente sin tener que realizar cambios en el código de servicio de la línea principal.

Los servicios de respaldo se describen en detalle el Capítulo 5, *Los patrones de datos nativos*de la nube y el Capítulo 4, Patrones de *comunicación nativos*de la nube.

## <a name="automation"></a>Automation

Como ha visto, los sistemas nativos de la nube adoptan microservicios, contenedores y diseño de sistemas modernos para lograr velocidad y agilidad. Pero, eso es sólo una parte de la historia. ¿Cómo aprovisiona los entornos en la nube en los que se ejecutan estos sistemas? ¿Cómo se implementan rápidamente las características y actualizaciones de la aplicación? ¿Cómo redondeas el panorama completo?

Ingrese la práctica ampliamente aceptada de [la Infraestructura como Código,](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)o IaC.

Con IaC, automatiza el aprovisionamiento de plataformas y la implementación de aplicaciones. En esencia, aplica prácticas de ingeniería de software, como pruebas y control de versiones, a las prácticas de DevOps. Su infraestructura e implementaciones son automatizadas, coherentes y repetibles.

### <a name="automating-infrastructure"></a>Automatización de la infraestructura

Herramientas como [Azure Resource Manager](https://azure.microsoft.com/documentation/articles/resource-group-overview/), Terraform y la CLI de [Azure,](https://docs.microsoft.com/cli/azure/)le permiten crear scripts mediante declaración de la infraestructura en la nube que necesita. Los nombres de recursos, las ubicaciones, las capacidades y los secretos están parametrizados y dinámicos. El script se versiona y se protege en el control de código fuente como un artefacto del proyecto. El script se invoca para aprovisionar una infraestructura coherente y repetible en entornos de sistema, como control de calidad, ensayo y producción.

Bajo el capó, IaC es idempotente, lo que significa que se puede ejecutar el mismo script una y otra vez sin efectos secundarios. Si el equipo necesita realizar un cambio, editan y vuelven a ejecutar el script. Solo se ven afectados los recursos actualizados.

En el artículo, [What is Infrastructure as Code](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code), el autor Sam Guckenheimer describe cómo, "Los equipos que implementan IaC pueden ofrecer entornos estables rápidamente y a escala. Los equipos evitan la configuración manual de los entornos y aplican la coherencia al representar el estado deseado de sus entornos a través del código. Las implementaciones de infraestructura con IaC son repetibles y evitan problemas en tiempo de ejecución causados por la deriva de configuración o la falta de dependencias. Los equipos de DevOps pueden trabajar junto con un conjunto unificado de prácticas y herramientas para ofrecer aplicaciones y su infraestructura de soporte de forma rápida, fiable y a escala."

### <a name="automating-deployments"></a>Automatización de las implementaciones

La [aplicación de doce factores](https://12factor.net/), discutida anteriormente, requiere pasos independientes al transformar el código completado en una aplicación en ejecución.

> *El \#factor 5* especifica que "Cada versión debe aplicar una separación estricta entre las etapas de compilación, versión y ejecución. Cada uno debe ser etiquetado con un ID único y apoyar la capacidad de revertir."

Los sistemas CI/CD modernos ayudan a cumplir este principio. Proporcionan pasos de implementación independientes y ayudan a garantizar un código coherente y de calidad que está fácilmente disponible para los usuarios.

La figura 1-8 muestra la separación en todo el proceso de implementación.

![Pasos de implementaciones en ci/CD Pipeline](./media/build-release-run-pipeline.png)

**Figura 1-8**. Pasos de implementación en una canalización de CI/CD

En la figura anterior, preste especial atención a la separación de tareas.

El desarrollador construye una característica en su entorno de desarrollo, iterando a través de lo que se denomina el "bucle interno" de código, ejecución y depuración. Cuando se completa, ese código se *inserta* en un repositorio de código, como GitHub, VSTS o BitBucket.

La inserción desencadena una fase de compilación que transforma el código en un artefacto binario. El trabajo se implementa con una canalización de [integración continua (CI).](https://martinfowler.com/articles/continuousIntegration.html) Compila, prueba y empaqueta automáticamente la aplicación.

La etapa de lanzamiento recoge el artefacto binario, aplica información de configuración de aplicaciones y entornos externos y genera una versión inmutable. La versión se implementa en un entorno especificado. El trabajo se implementa con una canalización de [entrega continua (CD).](https://martinfowler.com/bliki/ContinuousDelivery.html) Cada versión debe ser identificable. Puede decir: "Esta implementación está ejecutando la versión 2.1.1 de la aplicación."

Por último, la característica liberada se ejecuta en el entorno de ejecución de destino. Las versiones son inmutables, lo que significa que cualquier cambio debe crear una nueva versión.

Aplicando estas prácticas, las organizaciones han evolucionado radicalmente la forma en que envían software. Muchos han pasado de las versiones trimestrales a las actualizaciones bajo demanda. El objetivo es detectar problemas al principio del ciclo de desarrollo cuando son menos costosos de solucionar. Cuanto más larga sea la duración entre integraciones, más costosos serán los problemas para resolverse.  Con coherencia en el proceso de integración, los equipos pueden confirmar los cambios de código con más frecuencia, lo que conduce a una mejor colaboración y calidad de software.

### <a name="azure-pipelines"></a>Azure Pipelines

La nube de Azure incluye un nuevo servicio de CI/CD titulado [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/), que forma parte de la oferta de [VSTS](https://azure.microsoft.com/services/devops/) que se muestra en la figura 1-9.

![Canalizaciones de Azure en DevOps](./media/devops-components.png)

**Figura 1-9**. Ofertas de DEvOps de Azure

Azure Pipelines es un servicio en la nube que combina la integración continua (CI) y la entrega continua (CD). Puede probar, compilar y enviar automáticamente el código a cualquier destino.

La canalización se define en el código en un archivo YAML junto con el resto del código de la aplicación.

- La canalización se versiona con el código y sigue la misma estructura de bifurcación.
- Puede validar los cambios mediante revisiones de código en solicitudes de extracción y directivas de compilación de sucursales.
- Cada rama que use puede personalizar la directiva de compilación modificando el archivo azure-pipelines.yml.
- El archivo de canalización se registra en el control de versiones y se puede investigar si hay un problema.

El servicio Azure Pipelines admite la mayoría de los proveedores de Git y puede generar canalizaciones de implementación para aplicaciones escritas en plataformas Linux, macOS o Windows. Incluye soporte para Java, .NET, JavaScript, Python, PHP, Go, XCode y C++.

>[!div class="step-by-step"]
>[Anterior](introduction.md)
>[Siguiente](candidate-apps.md)
