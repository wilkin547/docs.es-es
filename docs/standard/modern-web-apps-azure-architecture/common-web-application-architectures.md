---
title: "Arquitecturas de aplicación web comunes"
description: "Diseñar aplicaciones web modernas con ASP.NET Core y Microsoft Azure | arquitecturas de aplicación web comunes"
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: b6236cfab290211f930d6a1987075abeade4fd6d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
#<a name="common-web-application-architectures"></a>Arquitecturas de aplicación Web comunes

> "Si cree de buena arquitectura es caro, intente arquitectura incorrecta".  
> _-Brian PI y Joseph Yoder_

## <a name="summary"></a>Resumen

Las aplicaciones de .NET más tradicionales se implementan como unidades solo corresponde a un archivo ejecutable o una aplicación web única que se ejecuta dentro de un único dominio de aplicación IIS. Este es el modelo de implementación más sencillo y actúa muy bien muchas aplicaciones más pequeñas públicas e internas. Sin embargo, incluso con esta unidad única de implementación, mayoría de las aplicaciones de negocio no trivial aprovechar cierta separación lógica en varias capas.

## <a name="what-is-a-monolithic-application"></a>¿Qué es una aplicación monolítica?

Una aplicación monolítica es aquel que son completamente independientes entre sí, en términos de su comportamiento. Puede interactuar con otros almacenes de datos o servicios en el transcurso de sus operaciones, pero el núcleo de su comportamiento se ejecuta dentro de su propio proceso y toda la aplicación normalmente se implementa como una sola unidad. Si este tipo de aplicación debe escalar horizontalmente, normalmente se duplica toda la aplicación en varios servidores o máquinas virtuales.

## <a name="all-in-one-applications"></a>Aplicaciones de All-in-One

El menor número posible de proyectos para una arquitectura de aplicación es uno. En esta arquitectura, toda la lógica de la aplicación está contenida en un solo proyecto, compilada en un único ensamblado e implementada como una sola unidad.

Un nuevo proyecto de ASP.NET Core, creados en Visual Studio o desde la línea de comandos empieza como un simple monolito "all-in-one". Contiene todo el comportamiento de la aplicación, incluida la lógica de acceso de presentación, empresarial y datos. Figura 5-1 muestra la estructura de archivos de aplicación de una solo proyecto.

**Figura 5-1.** Un único proyecto de aplicación de ASP.NET Core

![](./media/image5-1.png)

En un escenario de proyecto único, la separación de intereses se logra mediante el uso de carpetas. La plantilla predeterminada incluye carpetas independientes para las responsabilidades de patrón MVC de modelos, vistas y controladores, así como las carpetas adicionales para los datos y servicios. En esta disposición, detalles de presentación deben estar limitados tanto como sea posible a la carpeta Views y detalles de implementación de acceso a datos deben limitarse a las clases que se mantiene en la carpeta de datos. Lógica de negocios debe residir en servicios y las clases dentro de la carpeta de modelos.

Aunque es simple, la solución monolítica solo proyecto tiene algunas desventajas. A medida que aumenta el tamaño y la complejidad del proyecto, el número de archivos y carpetas continuará creciendo así. Problemas de la interfaz de usuario (modelos, vistas, controladores) residen en varias carpetas, que no están agrupadas juntos alfabéticamente. Este problema solo empeora cuando se agregan las estructuras de nivel de interfaz de usuario adicionales, como los filtros o ModelBinders, en sus propias carpetas. Lógica de negocios está repartida entre las carpetas de modelos y servicios, y no hay ninguna indicación clara de que las clases en las carpetas que deben dependen de otros. Esta falta de organización en el nivel de proyecto suele dar lugar a [código spaghetti](http://deviq.com/spaghetti-code/).

Para resolver estos problemas, las aplicaciones evolucionan a menudo en soluciones de varios proyectos, donde se considera cada proyecto que resida en un determinado *capa* de la aplicación.

## <a name="what-are-layers"></a>¿Cuáles son las capas?

Cuando las aplicaciones crezcan en complejidad, una manera de administrar esta complejidad es dividir la aplicación según sus responsabilidades o necesita aclaraciones. Esto sigue la separación de entidad de seguridad de las preocupaciones y puede ayudar a mantener un código base creciente organizado de forma que los desarrolladores pueden encontrar fácilmente donde se implementa una funcionalidad determinada. Arquitectura por niveles ofrece una serie de ventajas más allá de simplemente organización del código, aunque.

Organizan código en capas, se puede reutilizar la funcionalidad común de bajo nivel a lo largo de la aplicación. Volver a utilizar este es beneficioso significa que menos código deba escribir y que puede permitir que la aplicación normalizar en una sola implementación, sigue el principio seco.

Con una arquitectura en capas, las aplicaciones pueden exigir restricciones en el que las capas pueden comunicarse con otras capas. Esto ayuda a lograr encapsulación. Cuando se cambia o reemplaza una capa, deberían verse afectadas únicamente aquellas capas que funcionan con él. Mediante la limitación de que dependen de capas en el que se pueden mitigar otras capas, el impacto de los cambios para que un solo cambio no afecta a toda la aplicación.

Capas (y encapsulación) sea mucho más fácil reemplazar la funcionalidad dentro de la aplicación. Por ejemplo, una aplicación inicialmente puede usar su propia base de datos de SQL Server para la persistencia, pero más adelante podría optar por usar una estrategia de persistencia en la nube, o uno detrás de una API web. Si la aplicación ha encapsulado correctamente su implementación de persistencia dentro de una capa lógica, esa capa específica de SQL Server puede sustituirse por una nueva implementación de la misma interfaz pública.

Además de la posibilidad de intercambio de las implementaciones en respuesta a cambios futuros en los requisitos, niveles de la aplicación también facilitan intercambiar las implementaciones con fines de prueba. En lugar de tener que escribir las pruebas que funcionan en la capa de datos reales o de la capa de interfaz de usuario de la aplicación, estos niveles pueden reemplazarse en tiempo de prueba con implementaciones falsas que proporcionan conocidas respuestas a las solicitudes. Esto normalmente hace que las pruebas son mucho más fáciles de escribir y mucho más rápido en comparación con la duración de ejecución comprueba de nuevo infraestructura real de la aplicación.

Capas lógicas son una técnica común para mejorar la organización del código en las aplicaciones de software de empresa, y hay varias formas en el que se puede organizar el código en capas.

> [!NOTE]
> *Capas* representan una separación lógica dentro de la aplicación. En caso de que la lógica de la aplicación se distribuye físicamente para servidores o procesos independientes, estos destinos de implementación física independiente se conocen como *niveles*. Es posible y es bastante habitual, que tiene una aplicación de N capas que se implementa en un solo nivel.

## <a name="traditional-n-layer-architecture-applications"></a>Aplicaciones tradicionales de arquitectura de "Nivel N"

La organización más comunes de lógica de la aplicación en niveles que se muestra en la figura 5-2.

**Figura 5-2.** Capas de aplicación típica.

![](./media/image5-2.png)

Estas capas con frecuencia se abrevia como interfaz de usuario, BLL (capa de lógica de negocios) y la capa DAL (capa de acceso a datos). Con esta arquitectura, los usuarios realizan solicitudes a través de la capa de interfaz de usuario, que interactúa con la capa BLL. BLL, a su vez, puede llamar a la capa DAL para las solicitudes de acceso de datos. La capa de interfaz de usuario no debe realizar las solicitudes a la capa DAL directamente, ni debe interactuar con persistencia directamente a través de otros medios. Del mismo modo, la capa BLL solo debe interactuar con persistencia yendo a través de la capa DAL. De este modo, cada nivel tiene su propia responsabilidad conocido.

Una desventaja de este enfoque de distribución en capas tradicional es que las dependencias de tiempo de compilación se ejecutan desde la parte superior a la parte inferior. Es decir, la capa de interfaz de usuario depende de la capa BLL, que depende de la capa DAL. Esto significa que la capa BLL, que normalmente contiene la lógica más importante en la aplicación, es dependiente en detalles de implementación de acceso a datos (y a menudo en la existencia de una base de datos). Probar la lógica de negocios en una arquitectura tan a menudo es difícil, que requieren una base de datos de prueba. El principio de la inversión de dependencia puede utilizarse para resolver este problema, como verá en la siguiente sección.

Figura 5-3 muestra una solución de ejemplo, dividir la aplicación en tres proyectos responsabilidad (o capa).

**Figura 5-3.** Una aplicación sencilla monolítica con tres proyectos.

![](./media/image5-3.png)

Aunque esta aplicación usa varios proyectos por motivos organizativos, todavía se implementa como una sola unidad y sus clientes interactúan con ella como una aplicación web solo. Esto permite que el proceso de implementación muy simple. Figura 5-4 se muestra cómo podría ser dicha aplicación hospeda mediante Windows Azure.

![](./media/image5-4.png)

**Figura 5-4.** Implementación simple de aplicación Web de Azure

Como aplicación crezca, soluciones de implementación más sólida y complejo pueden ser necesarias. Figura 5-5 se muestra un ejemplo de un plan de implementación más complejo que admite capacidades adicionales.

![](./media/image5-5.png)

**Figura 5-5.** Implementar una aplicación web a un servicio de aplicación de Azure

Internamente, organización de este proyecto en varios proyectos en función de responsabilidad mejora la facilidad de mantenimiento de la aplicación.

Esta unidad se puede escalar vertical u horizontalmente para aprovechar las ventajas de escalabilidad de petición basada en la nube. El escalado significa agregar más CPU, memoria, espacio en disco u otros recursos en el servidor que hospeda la aplicación. Escalado horizontal significa agregar instancias adicionales de este tipo de servidores, si se trata de servidores físicos o máquinas virtuales. Cuando la aplicación se hospeda en varias instancias, se utiliza un equilibrador de carga para asignar solicitudes a instancias de aplicaciones individuales.

El enfoque más sencillo a la escala de una aplicación web en Azure consiste en configurar manualmente el ajuste de escala en el Plan de servicio de aplicaciones de la aplicación. Figura 5-6 se muestra la pantalla de panel de Azure adecuada para configurar el número de instancias prestan servicio a una aplicación.

![](./media/image5-6.png)

**Figura 5-6.** Plan de servicio de aplicación escala en Azure.

## <a name="clean-architecture"></a>Arquitectura de limpieza

Las aplicaciones que siguen el principio de la inversión de dependencia, así como los principios de diseño de Domain-Driven (DDD) tienden a llegar a una arquitectura similar. Esta arquitectura ha pasado por muchos nombres durante los años. Uno de los nombres era Hexagonal arquitectura, seguido de adaptadores y puertos. Más recientemente, ha citado como el [cebolla arquitectura](http://jeffreypalermo.com/blog/the-onion-architecture-part-1/) o [arquitectura limpia](https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html). Es el apellido, arquitectura limpia, que se usa como base para describir la arquitectura de este libro electrónico.

> [!NOTE]
> El término que limpia arquitectura puede aplicarse a las aplicaciones que se compilan con DDD principios así como para los que no se compilan con DDD. En el caso de la primera, esta combinación puede puede denominarse "Arquitectura DDD limpia".

Arquitectura limpia coloca el modelo de lógica y aplicación de negocios en el centro de la aplicación. En lugar de tener lógica de negocios dependen de otros problemas de infraestructura o de acceso a datos, se invierte esta dependencia: detalles de infraestructura e implementación dependen el núcleo de la aplicación. Esto se logra mediante la definición de abstracciones u otras interfaces, en el núcleo de la aplicación, que, a continuación, se implementan mediante tipos definidos en el nivel de infraestructura. Una forma habitual de visualizar esta arquitectura es usar una serie de círculos concéntricos, similares a una cebolla. Figura 5-X muestra un ejemplo de este tipo de representación en forma de arquitectura.

![](./media/image5-7.png)

**Figura 5-7.** Arquitectura limpia; vista de cebolla

En este diagrama de flujo de dependencias hacia el círculo más interno. Por lo tanto, puede ver que el núcleo de la aplicación (que toma su nombre de su posición en el núcleo de este diagrama) no tiene dependencias en otros niveles de la aplicación. En el centro de muy son entidades e interfaces de la aplicación. Justo fuera, pero todavía en el núcleo de la aplicación, son servicios de dominio, que normalmente se implementan interfaces definidas en el círculo interior. El núcleo de la aplicación fuera de la interfaz de usuario y las capas de infraestructura dependen de en el núcleo de la aplicación, pero no en otros (necesariamente).

Figura 5-X muestra un diagrama de capas horizontal más tradicional que refleja mejor la dependencia entre la interfaz de usuario y otras capas.

![](./media/image5-8.png)

**Figura 5-8.** Arquitectura limpia; vista de nivel horizontal

Tenga en cuenta que las flechas sólidas representan las dependencias de tiempo de compilación, mientras que la flecha discontinua representa una dependencia de solo en tiempo de ejecución. Uso de la arquitectura limpia, la capa de interfaz de usuario funciona con interfaces definidas en el núcleo de la aplicación en tiempo de compilación y lo ideal es que debe no tener ningún conocimiento de los tipos de implementación definidos en el nivel de infraestructura. En tiempo de ejecución, sin embargo, estos tipos de implementación será necesarios para la aplicación para su ejecución, por lo que deberá estar presente y conectado las interfaces principales de la aplicación a través de la inyección de dependencia.

Figura 5-9 se muestra una vista más detallada de la arquitectura de la aplicación ASP.NET Core cuando compila siguiendo estas recomendaciones.

![Arquitectura ASPNET principal](./media/image5-9.png)

**Figura 5-9.** Diagrama de arquitectura de ASP.NET Core después arquitectura limpia.

Dado que el núcleo de la aplicación no depende de infraestructura, es muy fácil de escribir pruebas unitarias automatizadas para esta capa. Cifras de entre 5 y 10 y 11 de 5 muestran cómo encajan las pruebas en esta arquitectura.

![UnitTestCore](./media/image5-10.png)

**Figura 5-10.** Pruebas unitarias de núcleo de la aplicación de forma aislada.

![IntegrationTests](./media/image5-11.png)

**Figura 5-11.** Las implementaciones de infraestructura con dependencias externas de pruebas de integración.

Puesto que la capa de interfaz de usuario no tiene ninguna dependencia directa en tipos definidos en el proyecto de infraestructura, del mismo modo es muy fácil intercambiar las implementaciones, ya sea para facilitar la prueba o en respuesta a los cambiantes requerimientos de la aplicación. Uso integrada de ASP.NET Core y la compatibilidad con inserción de dependencias hace que esta arquitectura de la forma más adecuada para estructurar aplicaciones monolítico no trivial.

Para las aplicaciones monolíticas los proyectos de aplicación principal, la infraestructura y la interfaz de usuario se ejecutan como una sola aplicación. La arquitectura de la aplicación en tiempo de ejecución podría ser algo como la figura 5-12.

![Arquitectura de núcleo ASPNET 2](./media/image5-12.png)

**Figura 5-12.** Arquitectura en tiempo de ejecución de la aplicación de ASP.NET Core de ejemplo.

### <a name="organizing-code-in-clean-architecture"></a>Organizar el código en la arquitectura limpia

En una solución de arquitectura limpia, cada proyecto tiene responsabilidades claras. Por lo tanto, ciertos tipos pertenecerá en cada proyecto y con frecuencia encontrará las carpetas correspondientes a estos tipos en el proyecto adecuado.

El núcleo de la aplicación contiene el modelo de negocio, que incluye las entidades, servicios e interfaces. Estas interfaces incluyen abstracciones para las operaciones que se llevará a cabo mediante la infraestructura, como el acceso de datos, acceso al sistema de archivos, llamadas de red, etcetera. A veces será necesario servicios o interfaces definidas en este nivel trabajar con tipos sin entidad que no tienen ninguna dependencia en la interfaz de usuario o de infraestructura. Estos se pueden definir como objetos simple de transferencia de datos (dto).

> ### <a name="application-core-types"></a>Tipos de aplicaciones principales
> -   Entidades (se conservan las clases de modelo de negocio)
> -   Interfaces
> -   Servicios
> -   Dto

El proyecto de infraestructura incluirá, normalmente, las implementaciones de acceso de datos. En una aplicación web de ASP.NET Core típica, esto incluye DbContext Entity Framework, las migraciones de EF principales que se han definido y las clases de implementación de acceso a datos. Es la manera más común para abstraer el código de implementación de acceso a datos mediante el uso de la [modelo de diseño de repositorio](http://deviq.com/repository-pattern/).

Además de las implementaciones de acceso de datos, el proyecto de infraestructura debe contener las implementaciones de servicios que deben interactuar con problemas de infraestructura. Estos servicios deben implementar interfaces definidas en el núcleo de la aplicación y, por lo que la infraestructura debe tener una referencia al proyecto de aplicación principal.

> ### <a name="infrastructure-types"></a>Tipos de infraestructura
> -   Tipos principales EF (DbContext, migraciones)
> -   Tipos de implementación de acceso de datos (repositorios)
> -   Servicios de infraestructura específicos (FileLogger, SmtpNotifier, etcetera.)

La capa de interfaz de usuario en una aplicación MVC de ASP.NET Core será el punto de entrada para la aplicación y será un proyecto de MVC de ASP.NET Core. Este proyecto debe hacer referencia al proyecto de aplicación principal y sus tipos deben interactuar con la infraestructura estrictamente a través de interfaces definidas en el núcleo de la aplicación. Ninguna creación directa de instancias de (o estáticas llamadas a) en la capa de interfaz de usuario se le deberían permitir tipos de capa de infraestructura.

> ### <a name="ui-layer-types"></a>Tipos de la capa de interfaz de usuario
> -   Controladores
> -   Filtros
> -   Vistas
> -   ViewModels
> -   Inicio

La clase de inicio es responsable de configurar la aplicación y para la conexión de los tipos de implementación a las interfaces, lo que permite la inserción de dependencias para que funcione correctamente en tiempo de ejecución.

> [!NOTE]
> Para conectarlo inyección de dependencia en ConfigureServices en el archivo Startup.cs del proyecto de interfaz de usuario, el proyecto que necesite hacer referencia al proyecto de infraestructura. Elimina esta dependencia, más fácilmente mediante el uso de un contenedor de DI personalizado. Para los fines de este ejemplo, el enfoque más sencillo es permitir que el proyecto de interfaz de usuario para que hagan referencia al proyecto de infraestructura.

## <a name="monolithic-applications-and-containers"></a>Contenedores y aplicaciones monolíticas 

También puede generar un único y monolítico de implementación basado en aplicación o servicio Web e implementarlo como un contenedor. Dentro de la aplicación, no podría ser monolítico pero organizada en varias bibliotecas, componentes o capas. Externamente es un único contenedor como un proceso único, sola aplicación web o servicio único.

Para administrar este modelo, implementa un único contenedor para representar la aplicación. Para escalar, basta con agregar copias adicionales con un equilibrador de carga en la parte frontal. La simplicidad proviene de administrar una única implementación en un único contenedor o la máquina virtual.

![](./media/image5-13.png)

Puede incluir varios componentes/bibliotecas o capas internas dentro de cada contenedor, como se muestra en la figura 5-X. Sin embargo, después de la entidad de seguridad del contenedor de *"un contenedor realiza una acción y lo hace en un proceso*", el patrón monolítico puede surgir un conflicto.

El inconveniente de este enfoque se incluye si/cuando crece la aplicación, que requiere una ampliación. Si toda la aplicación distribuida, no es realmente un problema. Sin embargo, en la mayoría de los casos, algunas partes de la aplicación son los puntos de retracción necesidad de ajuste de escala, mientras que otros componentes son utilizar menos.

En el ejemplo típico de comercio electrónico; ¿Qué es probable que necesite escalar es el componente de información de producto. Muchos clientes más examinar productos de adquirirlas. Más clientes utilice su cesta de usar la canalización de pago. Los clientes menos agreguen comentarios o ver su historial de compras. Y es probable que sólo tenga una serie de empleados en una única región, que necesita para administrar el contenido y las campañas de marketing. Escalando el diseño monolítico, todo el código se implementa varias veces.

Además de la escala todo problemas, los cambios en un único componente requieren al volver a examinar completa de toda la aplicación y una implementación completa de todas las instancias.

El enfoque monolítico es bastante habitual y muchas organizaciones están desarrollando con este enfoque de diseño. Muchos están experimentando bueno suficientes resultados, mientras que otros usuarios están alcanzando límites. Muchos diseñados sus aplicaciones en este modelo, ya que la infraestructura y herramientas eran demasiado difíciles crear arquitecturas orientadas a servicios (SOA) y no verán la necesidad - hasta que la aplicación ha crecido. Si encuentra que están cumpliendo los límites del enfoque monolítico, interrumpa la aplicación para que pueda aprovechar mejor contenedores y microservicios puede ser el siguiente paso lógico.

![](./media/image5-14.png)

Implementar aplicaciones monolíticas en Microsoft Azure puede lograrse mediante máquinas virtuales dedicadas para cada instancia. Usar [conjuntos de escalas de VM de Azure](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), puede escalar fácilmente las máquinas virtuales. [Servicios de aplicaciones de Azure](https://azure.microsoft.com/services/app-service/) puede ejecutar aplicaciones monolíticas y escalar fácilmente instancias sin tener que administrar las máquinas virtuales. Servicios de aplicaciones de Azure puede ejecutar instancias únicas de contenedores de Docker, simplificar la implementación. Puede implementar una sola máquina virtual como un host Docker con Docker y puede ejecutar varias instancias. Con el equilibrador de Azure, tal como se muestra en la figura 5-14, puede administrar el ajuste de escala.

La implementación a los distintos hosts puede administrarse con técnicas de implementación tradicionales. Los hosts de Docker se pueden administrar con comandos como **docker ejecutar** realizar manualmente o mediante automatización, como canalizaciones de entrega continua (CD).

### <a name="monolithic-application-deployed-as-a-container"></a>Aplicación monolítico implementada como un contenedor

Existen ventajas del uso de contenedores para administrar las implementaciones de aplicaciones monolítico. Las instancias de contenedores de ajuste de escala es mucho más rápido y fácil de implementar máquinas virtuales adicionales. Incluso cuando se usa conjuntos de escalas de VM para escalar las máquinas virtuales, tardan tiempo en la instancia. Cuando se implementa como instancias de aplicación, la configuración de la aplicación se administra como parte de la máquina virtual.

Implementación de actualizaciones como imágenes de Docker es mucho más rápido y eficaz de la red. Imágenes de docker se inician normalmente en segundos, lo que acelera la implementación. Anular una instancia de Docker es tan fácil como emitir un **stop docker** comando, normalmente se realizan en menos de un segundo.

Como contenedores son intrínsecamente inmutables por diseño, nunca debe preocuparse de las máquinas virtuales están dañadas, mientras que las secuencias de comandos de actualización podrían olvidar para tener en cuenta algunas configuración concreta o la izquierda del archivo en disco.

Aunque monolíticas aplicaciones pueden beneficiarse de Docker, interrumpa la aplicación monolítica en subsistemas que se puede escalar, desarrollado e implementado de forma individual puede ser el punto de entrada en el dominio Kerberos de microservicios.

> ### <a name="references--common-web-architectures"></a>Referencias: arquitecturas de Web comunes
> - **La arquitectura de limpieza**  
> <https://8thlight.com/blog/Uncle-Bob/2012/08/13/the-Clean-Architecture.HTML>
> - **La arquitectura de cebolla**  
> <http://jeffreypalermo.com/blog/the-Onion-Architecture-Part-1/>
> - **El modelo de repositorio**  
> <http://deviq.com/Repository-Pattern/>
> - **Limpiar solución de arquitectura de ejemplo**  
> <https://github.com/ardalis/cleanarchitecture>
> - **Diseñar libros electrónicos Microservicios** <http://aka.ms/MicroservicesEbook>

>[!div class="step-by-step"]
[Anterior] (arquitectura principles.md) [siguiente] (común-client-lado-web-technologies.md)
