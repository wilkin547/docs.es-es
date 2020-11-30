---
title: Arquitecturas de aplicaciones web comunes
description: Diseño de aplicaciones web modernas con ASP.NET Core y Azure | Explorar las arquitecturas de aplicaciones web comunes
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: 86d2e931e6462fb9f6ff5e3cd31b8d3fd188dd5a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682047"
---
# <a name="common-web-application-architectures"></a>Arquitecturas de aplicaciones web comunes

> "Si cree que la buena arquitectura es cara, pruebe la mala".  
> _- Brian Foote y Joseph Yoder_

La mayoría de aplicaciones .NET tradicionales se implementan como unidades únicas que corresponden a un archivo ejecutable o una sola aplicación web que se ejecuta dentro de un único dominio de aplicación de IIS. Este es el modelo de implementación más sencillo y sirve muy bien a muchas aplicaciones internas y públicas más pequeñas. Pero incluso con esta única unidad de implementación, la mayoría de las aplicaciones de negocio importantes se aprovechan de cierta separación lógica en varias capas.

## <a name="what-is-a-monolithic-application"></a>¿Qué es una aplicación monolítica?

Una aplicación monolítica es aquella completamente independiente, en términos de su comportamiento. Puede interactuar con otros servicios o almacenes de datos en el transcurso de sus operaciones, pero el núcleo de su comportamiento se ejecuta dentro de su propio proceso y toda la aplicación normalmente se implementa como una única unidad. Si es necesario escalar horizontalmente este tipo de aplicación, normalmente la aplicación completa se duplica en varios servidores o máquinas virtuales.

## <a name="all-in-one-applications"></a>Aplicaciones todo en uno

El menor número posible de proyectos para una arquitectura de aplicación es uno. En esta arquitectura, toda la lógica de la aplicación está contenida en un solo proyecto, se compila en un único ensamblado y se implementa como una sola unidad.

Un proyecto nuevo de ASP.NET Core, independientemente de que se cree en Visual Studio o desde la línea de comandos, empieza como un simple monolito "todo en uno". Contiene todo el comportamiento de la aplicación, incluida la lógica de presentación, de negocios y de acceso a datos. En la figura 5-1 se muestra la estructura de archivos de una aplicación de un solo proyecto.

![Una aplicación ASP.NET Core de un solo proyecto.](./media/image5-1.png)

**Figura 5-1**. Una aplicación ASP.NET Core de un solo proyecto.

En un escenario de un solo proyecto, la separación de intereses se logra mediante el uso de carpetas. La plantilla predeterminada incluye carpetas independientes para las responsabilidades del patrón MVC de modelos, vistas y controladores, así como carpetas adicionales para los datos y servicios. En esta disposición, los detalles de presentación deben estar limitados tanto como sea posible a la carpeta Vistas y los detalles de implementación del acceso a datos se deben limitar a las clases de la carpeta Datos. La lógica de negocios debe residir en los servicios y las clases de la carpeta Modelos.

Aunque es simple, la solución monolítica de un solo proyecto tiene algunas desventajas. A medida que aumenta el tamaño y la complejidad del proyecto, el número de archivos y carpetas también seguirá creciendo. Los intereses de la interfaz de usuario (IU) (modelos, vistas, controladores) residen en varias carpetas, que no están agrupadas alfabéticamente. Este problema empeora cuando se agregan otras construcciones de nivel de la interfaz de usuario, como filtros o ModelBinders, en sus propias carpetas. La lógica de negocios se distribuye entre las carpetas Modelos y Servicios, y no hay ninguna indicación clara de qué clases de qué carpetas deben depender de otras. Esta falta de organización en el nivel del proyecto suele dar lugar a [código espagueti](https://deviq.com/spaghetti-code/).

Para resolver estos problemas, las aplicaciones suelen evolucionar a soluciones de varios proyectos, donde se considera que cada proyecto reside en una determinada _capa_ de la aplicación.

## <a name="what-are-layers"></a>¿Qué son las capas?

Cuando aumenta la complejidad de las aplicaciones, una manera de administrarla consiste en dividir la aplicación según sus responsabilidades o intereses. Esto sigue el principio de separación de intereses y puede ayudar a mantener organizado un código base que crece para que los desarrolladores puedan encontrar fácilmente donde se implementa una funcionalidad determinada. Pero la arquitectura en capas ofrece una serie de ventajas que van más allá de la simple organización del código.

Al organizar el código en capas, la funcionalidad común de bajo nivel se puede reutilizar en toda la aplicación. Esta reutilización es beneficiosa ya que significa escribir menos código y puede permitir que la aplicación se estandarice en una sola implementación, siguiendo el principio [Una vez y solo una (DRY)](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself).

Con una arquitectura en capas, las aplicaciones pueden aplicar restricciones sobre qué capas se pueden comunicar con otras capas. Esto ayuda a lograr la encapsulación. Cuando se cambia o reemplaza una capa, solo deberían verse afectadas aquellas capas que funcionan con ella. Mediante la limitación de qué capas dependen de otras, se puede mitigar el impacto de los cambios para que un único cambio no afecte a toda la aplicación.

Las capas (y la encapsulación) facilitan considerablemente el reemplazo de funcionalidad dentro de la aplicación. Por ejemplo, es posible que una aplicación use inicialmente su propia base de datos de SQL Server para la persistencia, pero más adelante podría optar por usar una estrategia de persistencia basada en la nube, o situada detrás de una API web. Si la aplicación ha encapsulado correctamente su implementación de persistencia dentro de una capa lógica, esa capa específica de SQL Server se podría sustituir por una nueva que implementara la misma interfaz pública.

Además de la posibilidad de intercambiar las implementaciones en respuesta a cambios futuros en los requisitos, las capas de aplicación también facilitan el intercambio de implementaciones con fines de prueba. En lugar de tener que escribir pruebas que funcionan en la capa de datos reales o de la interfaz de usuario de la aplicación, estas capas se pueden reemplazar en tiempo de prueba con implementaciones falsas que proporcionen respuestas conocidas a las solicitudes. Esto normalmente hace que las pruebas sean mucho más fáciles de escribir y mucho más rápidas de ejecutar en comparación con la ejecución de pruebas sobre la infraestructura real de la aplicación.

Las capas lógicas son una técnica común para mejorar la organización del código en las aplicaciones de software empresarial, y hay varias formas de organizar el código en capas.

> [!NOTE]
 > Las _capas_ representan una separación lógica dentro de la aplicación. En caso de que la lógica de la aplicación se distribuya físicamente en servidores o procesos independientes, estos destinos de implementación físicos independientes se conocen como _niveles_. Es posible, y bastante habitual, tener una aplicación de N capas que se implemente en un solo nivel.

## <a name="traditional-n-layer-architecture-applications"></a>Aplicaciones tradicionales de arquitectura de "N capas"

En la figura 5-2 se muestra la organización más común de la lógica de la aplicación en capas.

![Capas de aplicación típicas](./media/image5-2.png)

**Figura 5-2.** Capas de aplicación típicas.

Estas capas se suelen abreviar como UI (interfaz de usuario), BLL (capa de lógica de negocios) y DAL (capa de acceso a datos). Con esta arquitectura, los usuarios realizan solicitudes a través de la capa de interfaz de usuario, que interactúa con la capa BLL. BLL, a su vez, puede llamar a DAL para las solicitudes de acceso de datos. La capa de interfaz de usuario no debe realizar solicitudes directamente a DAL, ni debe interactuar con la persistencia de forma directa a través de otros medios. Del mismo modo, BLL solo debe interactuar con la persistencia a través de DAL. De este modo, cada capa tiene su propia responsabilidad conocida.

Una desventaja de este enfoque de distribución en capas tradicional es que las dependencias de tiempo de compilación se ejecutan desde la parte superior a la inferior. Es decir, la capa de interfaz de usuario depende de BLL, que depende de DAL. Esto significa que BLL, que normalmente contiene la lógica más importante de la aplicación, depende de los detalles de implementación del acceso a datos (y a menudo de la existencia de una base de datos). Probar la lógica de negocios en este tipo de arquitectura suele ser difícil, y requiere una base de datos de prueba. Se puede usar el principio de inversión de dependencias para resolver este problema, como se verá en la sección siguiente.

En la figura 5-3 se muestra una solución de ejemplo, en la que se divide la aplicación en tres proyectos por responsabilidad (o capa).

![Una aplicación monolítica sencilla con tres proyectos](./media/image5-3.png)

**Figura 5-3.** Una aplicación monolítica sencilla con tres proyectos.

Aunque en esta aplicación se usan varios proyectos por motivos organizativos, se sigue implementando como una sola unidad y sus clientes interactúan con ella como una sola aplicación web. Esto permite que el proceso de implementación sea muy simple. En la figura 5-4 se muestra cómo se podría hospedar este tipo de aplicación con Azure.

![Implementación simple de una aplicación web de Azure](./media/image5-4.png)

**Figura 5-4.** Implementación simple de una aplicación web de Azure

Cuando aumenten las necesidades de la aplicación, se pueden necesitar soluciones de implementación más sólidas y complejas. En la figura 5-5 se muestra un ejemplo de un plan de implementación más complejo que admite funciones adicionales.

![Implementación de una aplicación web en Azure App Service](./media/image5-5.png)

**Figura 5-5.** Implementación de una aplicación web en Azure App Service

Internamente, la organización de este proyecto en varios en función de la responsabilidad mejora la facilidad de mantenimiento de la aplicación.

Esta unidad se puede escalar vertical u horizontalmente para aprovechar la escalabilidad a petición basada en la nube. El escalado vertical significa agregar más CPU, memoria, espacio en disco u otros recursos al servidor en el que se hospeda la aplicación. El escalado horizontal significa agregar instancias adicionales de estos servidores, con independencia de que sean servidores físicos, máquinas virtuales o contenedores. Cuando la aplicación se hospeda en varias instancias, se usa un equilibrador de carga para asignar solicitudes a instancias individuales de la aplicación.

El enfoque más sencillo para escalar una aplicación web en Azure consiste en configurar manualmente el escalado en el plan de App Service de la aplicación. En la figura 5-6 se muestra la pantalla de panel de Azure adecuada para configurar el número de instancias que prestan servicio a una aplicación.

![Escalado del plan de App Service en Azure](./media/image5-6.png)

**Figura 5-6**. Escalado de plan de App Service en Azure.

## <a name="clean-architecture"></a>Arquitectura limpia

Las aplicaciones que siguen el principio de inversión de dependencias, así como los principios de diseño controlado por dominios (DDD), tienden a llegar a una arquitectura similar. Esta arquitectura ha pasado por muchos nombres con los años. Uno de los primeros nombres fue Arquitectura hexagonal, seguido por Puertos y adaptadores. Más recientemente, se ha citado como [arquitectura cebolla](https://jeffreypalermo.com/blog/the-onion-architecture-part-1/) o [arquitectura limpia](https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html). Este último nombre, Arquitectura limpia, es el que se usa para esta arquitectura en este libro electrónico.

La aplicación de referencia eShopOnWeb utiliza el enfoque de arquitectura limpia para organizar su código en proyectos. Puede encontrar una plantilla de solución que puede usar como punto de partida para su propio ASP.NET Core en el repositorio de GitHub [ardalis/cleanarchitecture](https://github.com/ardalis/cleanarchitecture).

La arquitectura limpia coloca el modelo de lógica de negocios y aplicación en el centro de la aplicación. En lugar de tener lógica de negocios que depende del acceso a datos o de otros aspectos de infraestructura, esta dependencia se invierte: los detalles de la infraestructura y la implementación dependen del núcleo de la aplicación. Esto se logra mediante la definición de abstracciones o interfaces, en el núcleo de la aplicación, que después se implementan mediante tipos definidos en el nivel de infraestructura. Una forma habitual de visualizar esta arquitectura es usar una serie de círculos concéntricos, similares a una cebolla. En la figura 5-7 se muestra un ejemplo de este estilo de representación de la arquitectura.

![Arquitectura limpia; vista de cebolla](./media/image5-7.png)

**Figura 5-7.** Arquitectura limpia; vista de cebolla

En este diagrama, las dependencias fluyen hacia el círculo más interno. El núcleo de la aplicación toma su nombre de su posición en el núcleo de este diagrama. Y en el diagrama puede ver que el núcleo de la aplicación no tiene dependencias de otros niveles de la aplicación. Las entidades e interfaces de la aplicación se encuentran justo en el centro. En el exterior, pero todavía en el núcleo de la aplicación, están los servicios de dominio, que normalmente implementan interfaces definidas en el círculo interior. Fuera del núcleo de la aplicación, las capas de la interfaz de usuario y la infraestructura dependen del núcleo de la aplicación, pero no una de la otra (necesariamente).

En la figura 5-8 se muestra un diagrama de capas horizontal más tradicional que refleja mejor la dependencia entre la interfaz de usuario y otras capas.

![Arquitectura limpia; vista de capas horizontal](./media/image5-8.png)

**Figura 5-8.** Arquitectura limpia; vista de capas horizontal

Tenga en cuenta que las flechas sólidas representan las dependencias de tiempo de compilación, mientras que la flecha discontinua representa una dependencia solo de tiempo de ejecución. Con la arquitectura limpia, la capa de interfaz de usuario funciona con las interfaces definidas en el núcleo de la aplicación en tiempo de compilación y lo ideal es que no conozca los tipos de implementación definidos en el nivel de infraestructura. Pero en tiempo de ejecución, estos tipos de implementación son necesarios para ejecutar la aplicación, por lo que deben estar presentes y conectados a las interfaces del núcleo de la aplicación a través de la inserción de dependencias.

En la figura 5-9 se muestra una vista más detallada de la arquitectura de la aplicación ASP.NET Core cuando se compila siguiendo estas recomendaciones.

![Diagrama de arquitectura de ASP.NET Core en el que se sigue la arquitectura limpia](./media/image5-9.png)

**Figura 5-9.** Diagrama de arquitectura de ASP.NET Core en el que se sigue la arquitectura limpia.

Como el núcleo de la aplicación no depende de la infraestructura, es muy fácil escribir pruebas unitarias automatizadas para esta capa. En las figuras 5-10 y 5-11 se muestra cómo encajan las pruebas en esta arquitectura.

![UnitTestCore](./media/image5-10.png)

**Figura 5-10.** Pruebas unitarias del núcleo de la aplicación de forma aislada.

![IntegrationTests](./media/image5-11.png)

**Figura 5-11.** Pruebas de integración de las implementaciones de infraestructura con dependencias externas.

Como la capa de interfaz de usuario no tiene ninguna dependencia directa de los tipos definidos en el proyecto de infraestructura, también es muy fácil intercambiar las implementaciones, ya sea para facilitar las pruebas o en respuesta a los requisitos cambiantes de la aplicación. El uso y la compatibilidad integrados de ASP.NET Core con la inserción de dependencias hace que esta arquitectura sea la forma más adecuada de estructurar aplicaciones monolíticas no triviales.

Para las aplicaciones monolíticas, los proyectos de núcleo de la aplicación, infraestructura e interfaz de usuario se ejecutan como una sola aplicación. La arquitectura de la aplicación en tiempo de ejecución podría ser similar a la de la figura 5-12.

![Arquitectura 2 de ASP.NET Core](./media/image5-12.png)

**Figura 5-12.** Ejemplo de arquitectura en tiempo de ejecución de la aplicación ASP.NET Core.

### <a name="organizing-code-in-clean-architecture"></a>Organización del código en la arquitectura limpia

En una solución de arquitectura limpia, cada proyecto tiene responsabilidades claras. Por tanto, algunos tipos pertenecen a cada proyecto y con frecuencia encontrará las carpetas correspondientes a estos tipos en el proyecto adecuado.

#### <a name="application-core"></a>Núcleo de aplicación

El núcleo de la aplicación contiene el modelo de negocio, que incluye entidades, servicios e interfaces. Estas interfaces incluyen abstracciones para las operaciones que se llevarán a cabo mediante la infraestructura, como el acceso a datos, el acceso al sistema de archivos, las llamadas de red, etc. En ocasiones los servicios o interfaces definidos en este nivel tendrán que trabajar con tipos sin entidad que no tienen dependencias en la interfaz de usuario o la infraestructura. Estos se pueden definir como Objetos de transferencia de datos (DTO) simples.

##### <a name="application-core-types"></a>Tipos de núcleo de la aplicación

- Entidades (las clases de modelo de negocio que se conservan)
- Interfaces
- Servicios
- DTO

#### <a name="infrastructure"></a>Infraestructura

El proyecto de infraestructura incluye normalmente las implementaciones de acceso a datos. En una aplicación web ASP.NET Core típica, estas implementaciones incluyen DbContext de Entity Framework (EF), todos los objetos `Migration` de EF Core que se hayan definido y las clases de implementación de acceso a datos. La manera más común de abstraer el código de implementación de acceso a datos consiste en usar el [modelo de diseño de repositorio](https://deviq.com/repository-pattern/).

Además de las implementaciones de acceso a datos, el proyecto de infraestructura debe contener las implementaciones de los servicios que tienen que interactuar con los intereses de infraestructura. Estos servicios deben implementar interfaces definidas en el núcleo de la aplicación, por lo que la infraestructura deberá tener una referencia al proyecto del núcleo de la aplicación.

##### <a name="infrastructure-types"></a>Tipos de infraestructura

- Tipos de EF Core (`DbContext`, `Migration`)
- Tipos de implementación de acceso a datos (Repositorios)
- Servicios específicos de la infraestructura (por ejemplo, `FileLogger` o `SmtpNotifier`)

#### <a name="ui-layer"></a>Capa de interfaz de usuario

La capa de interfaz de usuario en una aplicación ASP.NET Core MVC es el punto de entrada para la aplicación. Este proyecto debe hacer referencia al proyecto Application Core y sus tipos deben interactuar con la infraestructura estrictamente a través de las interfaces definidas en Application Core. En la capa de interfaz de usuario no se debe permitir la creación de instancias directas o llamadas estáticas a los tipos de la capa de infraestructura.

##### <a name="ui-layer-types"></a>Tipos de capa de interfaz de usuario

- Controladores
- Filtros
- Vistas
- ViewModels
- Inicio

La clase Startup es responsable de configurar la aplicación y de conectar los tipos de implementación a las interfaces, lo que permite que la inserción de dependencias funcione correctamente en tiempo de ejecución.

> [!NOTE]
> Para conectar la inserción de dependencias de ConfigureServices al archivo Startup.cs del proyecto de interfaz de usuario, el proyecto tiene que hacer referencia al proyecto de infraestructura. Esta dependencia se puede eliminar con facilidad mediante un contenedor de DI personalizado. Para los fines de este ejemplo, el enfoque más sencillo consiste en permitir que el proyecto de interfaz de usuario haga referencia al proyecto de infraestructura.

## <a name="monolithic-applications-and-containers"></a>Aplicaciones monolíticas y contenedores

Puede compilar una aplicación o un servicio web único basado en una implementación monolítica e implementarlos como un contenedor. Dentro de la aplicación, es posible que no sean de tipo monolítico, sino que se organicen en varias bibliotecas, componentes o capas. Externamente, es un contenedor único como un proceso único, una aplicación web única o un servicio único.

Para administrar este modelo, debe implementar un único contenedor para representar la aplicación. Para escalar, solo tiene que agregar más copias con un equilibrador de carga delante. La simplicidad proviene de administrar una única implementación en un solo contenedor o máquina virtual.

![Figura 5-13](./media/image5-13.png)

Puede incluir varios componentes, bibliotecas o capas internas en cada contenedor, como se muestra en la figura 5-13. Pero, al seguir el principio de contenedor "_un contenedor realiza una acción y lo hace en un proceso_", es posible que el patrón monolítico entre en conflicto.

El inconveniente de este enfoque aparece si o cuando la aplicación aumenta y debe escalarse. Si se escala toda la aplicación, realmente no es un problema. Pero en la mayoría de los casos, solo algunos elementos de la aplicación son los puntos de obstrucción que deben escalarse, mientras que otros componentes se usan menos.

En el ejemplo típico de comercio electrónico, lo que probablemente sea necesario escalar es el componente de información del producto. Hay muchos más clientes que buscan productos de los que los compran. Más clientes usan la cesta en lugar de usar la canalización de pago. Menos clientes publican comentarios o consultan su historial de compras. Y es probable que solo tenga un grupo reducido de empleados, en una única región, que tenga que administrar las campañas de contenido y marketing. Al escalar el diseño monolítico, todo el código se implementa varias veces.

Además del problema de "escalarlo todo", los cambios en un único componente requieren volver a probar por completo toda la aplicación e implementar por completo todas las instancias.

El enfoque monolítico es habitual y muchas organizaciones realizan el desarrollo con este enfoque de diseño. Muchas obtienen resultados bastante positivos, mientras que otras alcanzan los límites. Muchas diseñaron sus aplicaciones con este modelo, ya que crear arquitecturas orientadas a servicios (SOA) con infraestructura y herramientas resultaba demasiado difícil, y no vieron la necesidad hasta que la aplicación creció. Si comprueba que está alcanzando los límites del enfoque monolítico, dividir la aplicación para que pueda aprovechar mejor los contenedores y microservicios puede ser el siguiente paso lógico.

![Figura 5-14](./media/image5-14.png)

La implementación de aplicaciones monolíticas en Microsoft Azure se puede conseguir con máquinas virtuales dedicadas para cada instancia. Con [Azure Virtual Machine Scale Sets](/azure/virtual-machine-scale-sets/), las máquinas virtuales se pueden escalar fácilmente. [Azure App Services](https://azure.microsoft.com/services/app-service/) puede ejecutar aplicaciones monolíticas y escalar fácilmente instancias sin necesidad de administrar las máquinas virtuales. Azure App Services también puede ejecutar instancias únicas de contenedores de Docker, lo que simplifica la implementación. Con Docker, se puede implementar una única máquina virtual como un host de Docker y ejecutar varias instancias. Con el equilibrador de Azure, como se muestra en la figura 5-14, se puede administrar el escalado.

La implementación en los distintos hosts se puede administrar con técnicas de implementación tradicionales. Los hosts de Docker se pueden administrar con comandos como **docker run** ejecutados manualmente o a través de la automatización como canalizaciones de entrega continua (CD).

### <a name="monolithic-application-deployed-as-a-container"></a>Una aplicación monolítica implementada como un contenedor

El uso de contenedores para administrar las implementaciones de aplicaciones monolíticas tiene una serie de ventajas. Escalar las instancias de los contenedores es mucho más rápido y fácil que implementar máquinas virtuales adicionales. Incluso cuando se usan conjuntos de escalado de máquinas virtuales para escalar las máquinas virtuales, se tarda tiempo en crear las instancias. Cuando se implementa como instancias de aplicación, la configuración de la aplicación se administra como parte de la máquina virtual.

Implementar las actualizaciones como imágenes de Docker es mucho más rápido y eficaz en la red. Normalmente, las imágenes de Docker se inician en segundos, lo que acelera las implementaciones. Anular una instancia de Docker es tan fácil como ejecutar un comando `docker stop`, que normalmente se completa en menos de un segundo.

Como por diseño los contenedores son intrínsecamente inmutables, no tendrá que preocuparse de que las máquinas virtuales resulten dañadas, mientras que es posible que los scripts de actualización olviden tener en cuenta alguna configuración concreta o archivo que se conserve en disco.

Puede usar contenedores de Docker para la implementación monolítica de aplicaciones web más sencillas. Esto mejora la integración continua y las canalizaciones de implementación continua y ayuda a llevar a cabo correctamente el proceso desde la implementación hasta la producción. Ya no tendrá que pensar en por qué no funciona en producción, aunque sí que funcione en su equipo.

Una arquitectura basada en microservicios tiene muchas ventajas, pero a costa de una mayor complejidad. En algunos casos, los costos superan las ventajas, por lo que es una opción mejor utilizar una aplicación de implementación monolítica que se ejecute en un solo contenedor o en unos pocos contenedores.

Es posible que una aplicación monolítica no se pueda descomponer fácilmente en microservicios bien separados. Los microservicios deberían funcionar de manera independiente para proporcionar una aplicación más resistente. Si no puede proporcionar sectores de características independientes de la aplicación, el hecho de separarla solo conlleva más complejidad.

Una aplicación podría no necesitar inicialmente el escalado de las características por separado. Cuando es necesario escalar una aplicación más allá de una única instancia, muchas aplicaciones pueden hacerlo a través del proceso relativamente sencillo de clonación de esa instancia completa. El trabajo adicional de separar la aplicación en servicios discretos apenas proporciona beneficios, mientras que el escalado de instancias completas de la aplicación es simple y rentable.

En las fases tempranas del desarrollo de una aplicación, es posible que no se tenga una idea clara de dónde están los límites funcionales naturales. Mientras desarrolla un producto mínimamente viable, puede que todavía no sea evidente la separación natural. Algunas de estas condiciones pueden ser temporales. Podría empezar creando una aplicación monolítica y, más adelante, separar algunas características para desarrollarlas e implementarlas como microservicios. Otras condiciones podrían ser básicas para el espacio de problemas de la aplicación y, en consecuencia, tal vez no se pueda dividir nunca en varios microservicios.

La separación de una aplicación en varios procesos diferenciados también introduce una sobrecarga. La separación de funciones en procesos diferentes conlleva una mayor complejidad. Los protocolos de comunicación se vuelven más complejos. En lugar de llamadas a métodos, debe usar comunicaciones asincrónicas entre servicios. Cuando cambie a una arquitectura de microservicios, deberá agregar muchos de los bloques de creación que se implementan en la versión de microservicios de la aplicación eShopOnContainers: control de bus de eventos, reintentos y resistencia de mensajes, coherencia eventual y mucho más.

La [aplicación de referencia eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb), mucho más sencilla, admite el uso de un único contenedor monolítico. La aplicación incluye una aplicación web con vistas MVC tradicionales, API web y Razor Pages. Esta aplicación se puede iniciar desde la raíz de la solución mediante los comandos `docker-compose build` y `docker-compose up`. Este comando configura un contenedor para la instancia web mediante el elemento `Dockerfile` que se encuentra en la raíz de cada proyecto web y ejecuta el contenedor en un puerto específico. Puede descargar de GitHub el código fuente para esta aplicación y ejecutarlo de forma local. Incluso esta aplicación monolítica se beneficia de la implementación en un entorno de contenedor.

Ante todo, la implementación en contenedor implica que cada instancia de la aplicación se ejecuta en el mismo entorno. Esto incluye el entorno de desarrollo donde tienen lugar las pruebas y el desarrollo iniciales. El equipo de desarrollo puede ejecutar la aplicación en un entorno en contenedor que coincida con el entorno de producción.

Además, las aplicaciones en contenedor se escalan horizontalmente con un costo menor. La utilización de un entorno de contenedor permite un mayor uso compartido de los recursos que los entornos de máquina virtual tradicionales.

Por último, el hecho de incluir la aplicación en un contenedor fuerza la separación entre la lógica de negocios y el servidor de almacenamiento. Cuando la aplicación se escala horizontalmente, los diversos contenedores se basan en un único medio de almacenamiento físico. Normalmente este medio de almacenamiento es un servidor de alta disponibilidad que ejecuta una base de datos de SQL Server.

## <a name="docker-support"></a>Compatibilidad con Docker

El proyecto `eShopOnWeb` se ejecuta en .NET Core. Por lo tanto, se puede ejecutar en contenedores basados en Linux o en Windows. Tenga en cuenta que, para la implementación de Docker, le interesa usar el mismo tipo de host para SQL Server. Los contenedores basados en Linux permiten una superficie menor y son preferibles.

Puede usar Visual Studio 2017 o versiones posteriores para agregar compatibilidad con Docker a una aplicación existente haciendo clic con el botón derecho en **Explorador de soluciones** y seleccionando **Agregar** > **Compatibilidad con Docker**. Esto agrega los archivos necesarios y modifica el proyecto para poder usarlos. En el ejemplo `eShopOnWeb` actual ya se incluyen estos archivos.

El archivo `docker-compose.yml` de nivel de solución contiene información sobre qué imágenes se van a compilar y qué contenedores se van a iniciar. El archivo le permite usar el comando `docker-compose` para iniciar varias aplicaciones al mismo tiempo. En este caso, solo está iniciando el proyecto web. También se puede usar para configurar las dependencias, como un contenedor de base de datos independiente.

```yml
version: '3'

services:
  eshopwebmvc:
    image: eshopwebmvc
    build:
      context: .
      dockerfile: src/Web/Dockerfile
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
    ports:
      - "5106:5106"

networks:
  default:
    external:
      name: nat
```

El archivo `docker-compose.yml` hace referencia a `Dockerfile` en el proyecto `Web`. El `Dockerfile` se usa para especificar qué contenedor base se va a utilizar y cómo se configurará la aplicación en él. El `Dockerfile` de `Web`:

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:3.1 AS build
WORKDIR /app

COPY *.sln .
COPY . .
WORKDIR /app/src/Web
RUN dotnet restore

RUN dotnet publish -c Release -o out

FROM mcr.microsoft.com/dotnet/aspnet:3.1 AS runtime
WORKDIR /app
COPY --from=build /app/src/Web/out ./

ENTRYPOINT ["dotnet", "Web.dll"]
```

### <a name="troubleshooting-docker-problems"></a>Solución de problemas de Docker

Una vez que se ejecute la aplicación en contenedores, se sigue ejecutando hasta que se detenga. Con el comando `docker ps` puede ver qué contenedores se están ejecutando. Puede detener un contenedor en ejecución si usa el comando `docker stop` y especifica el identificador del contenedor.

Tenga en cuenta que los contenedores de Docker en ejecución pueden estar enlazados a puertos que, en otros casos, es posible que intentara usar en el entorno de desarrollo. Si intenta ejecutar o depurar una aplicación con el mismo puerto que un contenedor de Docker en ejecución, obtendrá un error que indica que el servidor no se puede enlazar a ese puerto. Una vez más, detener el contenedor debería resolver el problema.

Si quiere agregar compatibilidad con Docker a la aplicación mediante Visual Studio, asegúrese de que Docker Desktop se esté ejecutando. Si Docker Desktop no está funcionando cuando se inicia el asistente, el asistente no se ejecutará correctamente. Además, el asistente examinará el contenedor que ha elegido actualmente para agregar la compatibilidad correcta con Docker. Si quiere agregar compatibilidad con contenedores de Windows, debe ejecutar el asistente mientras Docker Desktop se ejecuta con contenedores de Windows configurados. Si quiere agregar compatibilidad con contenedores de Linux, ejecute el asistente mientras Docker se ejecuta con contenedores de Linux configurados.

### <a name="references--common-web-architectures"></a>Referencias: arquitecturas web comunes

- **The Clean Architecture** (La arquitectura limpia)  
  <https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html>
- **The Onion Architecture** (La arquitectura cebolla)  
  <https://jeffreypalermo.com/blog/the-onion-architecture-part-1/>
- **The Repository Pattern** (El modelo de repositorio)  
  <https://deviq.com/repository-pattern/>
- **Plantilla de solución de arquitectura limpia**  
  <https://github.com/ardalis/cleanarchitecture>
- **Architecting Microservices e-book** (Libro electrónico de arquitectura de microservicios)  
  <https://aka.ms/MicroservicesEbook>
- **DDD (diseño guiado por el dominio)**  
  <https://docs.microsoft.com/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/>

>[!div class="step-by-step"]
>[Anterior](architectural-principles.md)
>[Siguiente](common-client-side-web-technologies.md)
