---
title: Modernizar las aplicaciones de .NET existentes con Azure Cloud y contenedores de Windows (2nd edition)
description: Aprenda a elevación y desplazamiento y modernizar aplicaciones existentes a la nube de Azure y contenedores con este libro electrónico.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 4/28/2018
ms.openlocfilehash: b22ddd8a63d183571f9ca3a63fb7ae84ebb88510
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2018
ms.locfileid: "48873510"
---
# <a name="modernize-existing-net-applications-with-azure-cloud-and-windows-containers-2nd-edition"></a>Modernizar aplicaciones .NET existentes con la nube de Azure y contenedores de Windows (2nd edition)

![imagen de portada](./media/cover.png)

PUBLICADO POR  
Microsoft Press y Microsoft DevDiv  
Divisiones de Microsoft Corporation  
One Microsoft Way  
Redmond, Washington 98052-6399  

Copyright © 2018 de Microsoft Corporation  

Todos los derechos reservados. No se puede reproducir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.

Este libro está disponible gratuitamente en forma de libro electrónico (eBook) disponible a través de varios canales de Microsoft, como <http://dot.net/architecture>.

Si tiene preguntas relacionadas con este libro, envíe un correo electrónico a [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book).

Este libro se proporciona “tal cual” y expresa las opiniones del autor. Las vistas, opiniones e información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios Web de Internet, pueden cambiar sin previo aviso.

Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios. No debe deducirse ninguna asociación ni conexión reales.

Microsoft y las marcas comerciales indicadas en <https://www.microsoft.com> en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft. El resto de marcas pertenecen a sus respectivos propietarios.

Autor:
> **Cesar de la Torre**, administrador de programas sénior del equipo del producto de .NET, Microsoft Corp.

Participantes y revisores:
> **Scott Hunter**, director asociado de administración de programas del equipo de .NET, Microsoft  
> **Paul Yuknewicz**, director principal de administración de programas del equipo de Visual Studio Tools, Microsoft  
> **Lisa Guthrie**, administradora de programas del equipo de Visual Studio Tools, Microsoft  
> **Ankit Asthana**, director principal de administración de programas del equipo de .NET, Microsoft  
> **Unai Zorrilla**, responsable de desarrollo de Plain Concepts  
> **Javier Valero**, director de operaciones de Grupo Solutio  

## <a name="introduction"></a>Introducción

Si decide modernizar sus aplicaciones o servicios web y moverlas a la nube, no necesariamente deben totalmente rediseñar sus aplicaciones. Cambio de arquitectura de una aplicación mediante el uso de un enfoque avanzado como microservicios no siempre es una opción debido a restricciones de costos y tiempo. Según el tipo de aplicación, cambio de arquitectura de una aplicación también es posible que no sea necesario. Para optimizar la rentabilidad de la estrategia de migración a la nube de su organización, es importante tener en cuenta las necesidades de su negocio y los requisitos de las aplicaciones. Debe determinar:

- Las aplicaciones que requieren una transformación o cambio de la arquitectura.

- Qué aplicaciones necesitan modernizarse solo parcialmente.

- Qué aplicaciones se pueden "elevar y desplazar" directamente a la nube.

## <a name="about-this-guide"></a>Acerca de esta guía

Esta guía se centra principalmente en la modernización inicial de web de Microsoft .NET Framework existentes o las aplicaciones orientadas a servicios, lo que significa que la acción de mover una carga de trabajo a un entorno más reciente o más moderno sin modificar significativamente el código de la aplicación y la arquitectura básica. 

Esta guía también resalta las ventajas de mover las aplicaciones a la nube y modernizarlas parcialmente mediante el uso de un conjunto específico de nuevas tecnologías y enfoques, como los contenedores de Windows y plataformas de proceso relacionadas en Azure se admiten contenedores de Windows.

## <a name="path-to-the-cloud-for-existing-net-applications"></a>Ruta de acceso a la nube para aplicaciones .NET existentes

Las organizaciones suelen elegir la migración a la nube por la agilidad y velocidad que pueden obtener para sus aplicaciones. Puede configurar miles de servidores (VM) en la nube en cuestión de minutos, en comparación con las semanas que suele llevar la configuración de los servidores locales.

No hay una estrategia única y general para migrar las aplicaciones a la nube. La estrategia de migración adecuada para su caso dependerá de las necesidades y prioridades de la organización y del tipo de aplicaciones que se vayan a migrar. No todas las aplicaciones garantizan la inversión que conlleva la migración a un modelo de plataforma como servicio ([PaaS](https://azure.microsoft.com/overview/what-is-paas/)) o el desarrollo de un modelo de aplicación [nativa de la nube](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications). En muchos casos, puede adoptar un enfoque por fases o incremental para invertir en la migración de los recursos a la nube, en función de las necesidades de su negocio.

Aplicaciones modernas con la agilidad a largo plazo y el valor para la organización, puede beneficiarse de la inversión en *nativas de la nube* arquitecturas de aplicaciones. Sin embargo, para las aplicaciones existentes o heredados activos, la clave es dedicar un tiempo mínimo y dinero (sin necesidad de rediseñar ni cambiar el código) mientras se mueven a la nube, para obtener importantes ventajas.

En la figura 1-1 se muestran las posibles rutas de acceso que puede usar para migrar las aplicaciones .NET existentes a la nube en fases incrementales.

 ![Rutas de acceso de modernización de servicios y aplicaciones .NET existentes](./media/image1-1.png)

> **Figura 1-1**. Rutas de acceso de modernización de servicios y aplicaciones .NET existentes

Cada método de migración tiene distintas ventajas y motivos para su uso. Puede elegir un único enfoque para migrar las aplicaciones a la nube o seleccionar determinados componentes de varios enfoques. Las aplicaciones individuales no están limitadas a un único enfoque o a un solo estado de madurez. Por ejemplo, un enfoque híbrido común tendría ciertos componentes locales y otros componentes en la nube.

La definición y una breve explicación de cada nivel de madurez de la aplicación son los siguientes:

**Nivel 1: En la nube infraestructura-listo** aplicaciones: en este enfoque de migración, puede simplemente migrar o rehospedar las aplicaciones locales actuales a una infraestructura como servicio ([IaaS](https://azure.microsoft.com/overview/what-is-iaas/)) plataforma. Las aplicaciones tienen casi la misma composición que antes, pero ahora se implementan en máquinas virtuales en la nube.
Este tipo simple de migración normalmente se conoce en la industria como "Elevar y desplazar".

**Nivel 2: En la nube optimizado** aplicaciones: en este nivel y sin necesidad de diseñar la arquitectura ni modificar el código importante, puede obtener ventajas adicionales al ejecutar la aplicación en la nube con modernas tecnologías como los contenedores y adicionales servicios administrados en la nube. Se mejora la agilidad de las aplicaciones para distribuirlas con más rapidez al perfeccionar los procesos de las operaciones de desarrollo empresariales (DevOps). Para lograrlo, usando tecnologías como contenedores de Windows, que se basa en el motor de Docker. Los contenedores eliminan la fricción causada por las dependencias de aplicación cuando se implementa en varias fases. En este modelo de madurez, puede implementar contenedores en IaaS o PaaS al uso adicionales relacionadas con servicios administrados en la nube para bases de datos, almacenar en caché como un servicio, supervisión e implementación continua e integración continua canalizaciones (CI/CD).

El tercer nivel de madurez es el objetivo final de la nube, pero es opcional para muchas aplicaciones y no el enfoque principal de esta guía:

**Nivel 3: Nativo en la nube** aplicaciones: este enfoque de migración suele basarse en las necesidades del negocio y modernización de las aplicaciones de misión crítica de destinos. En este nivel, debe usar los servicios PaaS para migrar las aplicaciones a plataformas informáticas PaaS. Debe implementar la arquitectura de microservicios y aplicaciones [nativas de la nube](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) para desarrollar aplicaciones con una agilidad a largo plazo y para escalar a nuevos límites. Este tipo de modernización suele requerir un diseño específico para la nube. A menudo puede ser necesario escribir código nuevo, sobre todo, al migrar a modelos basados en microservicios y en aplicaciones nativas de la nube. Este enfoque puede ayudar a obtener ventajas que son difíciles de conseguir en un entorno de aplicaciones locales y monolíticas.

En la tabla 1-1 se describen las principales ventajas y motivos para elegir cada enfoque de migración o modernización.

| **Infraestructura preparada para la nube** <br /> *Elevación y desplazamiento* | **Optimizada para la nube** <br /> *Modernizar* | **En la nube nativas** <br /> *Modernizar, rediseñar y volver a escribir* |
|---|---|---|
| **Destino de cálculo de la aplicación** |
| Aplicaciones implementadas en las máquinas virtuales de Azure | Monolítica o las aplicaciones de N niveles implementado en Azure App Service, instancia de contenedor de Azure (ACI), las máquinas virtuales con contenedores, Azure Service Fabric o AKS (Azure Kubernetes Service) | Microservicios en contenedores en Azure Kubernetes Service (AKS), Service Fabric o microservicios sin servidor basadas en funciones de Azure. |
| **Destino de datos** |
| SQL o cualquier base de datos relacional en una máquina virtual | Instancia administrada de Azure SQL Database o en otra base de datos administrado en la nube. | Bases de datos de grano multas por microservicio, en función de otra base de datos administrado en la nube, Azure Cosmos DB o Azure SQL Database |
| **Ventajas**|
| <li>Ningún código de cambio de la arquitectura, no hay nuevo <li> Mínimo esfuerzo para una migración rápida <li> Mínimo común denominador compatible con Azure <li> Garantías de disponibilidad básicas <li> Después de la migración a la nube, todavía es más fácil modernizar | <li> Ningún cambio de la arquitectura <li> Cambios de código/configuración mínima <li> Desarrollo y agilidad de DevOps mejorados para publicar debido a los contenedores <li> Mayor densidad y costos de implementación más bajos <li> Portabilidad de aplicaciones y dependencias <li> Flexibilidad de destinos host: PaaS enfoques o IaaS | <li> Arquitecto de la nube, obtener los mejores beneficios de la nube pero se requiere nuevo código <li> Enfoques nativos de la nube de los microservicios <li> Aplicaciones modernas de misión crítica, resistente en la nube muy escalable <li> Servicios totalmente administrados <li> Optimizado para escalado <li> Optimizado para la agilidad autónoma por subsistema <li> Basado en implementaciones y DevOps |
| **Desafíos** |
| <li> Valor menor de la nube, aparte del cambio en gastos operativos o en el cierre de los centros de datos <li> Poca administración: No del sistema operativo o aplicación de revisiones de software intermedio; Puede usar soluciones de infraestructura, como Terraform, Spinnaker o Puppet | <li> Inclusión en contenedores es un paso adicional en la curva de aprendizaje para desarrolladores y las operaciones de TI <li> Las canalizaciones de DevOps y CI/CD suele ser 'obligatorio' para este enfoque. Si no se encuentra actualmente en la referencia cultural de la organización, podría ser un desafío adicional| <li> Requiere rediseño de aplicaciones nativas en la nube y las arquitecturas de microservicios y normalmente no requiere código significativa refactorización o reescribir cuando Modernice (un aumento del tiempo y presupuesto) <li> Las canalizaciones de DevOps y CI/CD suele ser 'obligatorio' para este enfoque. Si no se encuentra actualmente en la referencia cultural de la organización, podría ser un desafío adicional|
> **Tabla 1-1.** Ventajas y desafíos de la modernización de rutas de los servicios y las aplicaciones .NET existentes

### <a name="key-technologies-and-architectures-by-maturity-level"></a>Arquitecturas y tecnologías clave por nivel de madurez

Las aplicaciones .NET Framework se iniciaron por primera vez con .NET Framework 1.0, que se publicó a finales de 2001. Después, las empresas cambian a nuevas versiones (como 2.0, 3.5 y .NET 4.x). La mayoría de esas aplicaciones se ejecutaba en Windows Server y de Internet Information Server (IIS) y usa una base de datos relacional como SQL Server, Oracle, MySQL o cualquier otro servicio RDBMS.

La mayoría de las aplicaciones .NET existentes pueden basarse actualmente en .NET Framework 4.x o incluso en .NET Framework 3.5 y usar marcos de trabajo web, como ASP.NET MVC, Formularios web ASP.NET, ASP.NET Web API, Windows Communication Foundation (WCF), ASP.NET SignalR y ASP.NET Web Pages. Estas tecnologías de .NET Framework establecidas dependen de Windows. Es importante tener en cuenta esa dependencia si solo se van a migrar aplicaciones heredadas y solo se desea realizar cambios mínimos en la infraestructura de las aplicaciones.

En la figura 1-2 se muestran los estilos de arquitectura y las tecnologías principales utilizados en cada uno de los tres niveles de madurez de la nube:

![Tecnologías principales de cada nivel de madurez para modernizar las aplicaciones web .NET existentes](./media/image1-2.png)

> **Figura 1-2.** Tecnologías principales de cada nivel de madurez para modernizar las aplicaciones web .NET existentes

En la figura 1-2 se destacan los escenarios más comunes, pero se pueden presentar muchas variaciones híbridas y mixtas en relación con la arquitectura. Por ejemplo, los modelos de madurez no solo se aplican a arquitecturas monolíticas de las aplicaciones web existentes, sino también a la orientación del servicio, a variaciones de n niveles y a otras variaciones de estilo de la arquitectura. El foco o el porcentaje en el tipo de arquitectura de uno u otro y las tecnologías relacionadas superior determina el nivel de madurez general de las aplicaciones.

Cada nivel de madurez del proceso de modernización está asociado con los siguientes enfoques y tecnologías clave:

- **En la nube listos para la infraestructura** (rehospedaje o basic elevar y desplazar): como primer paso, muchas organizaciones desean solo ejecutar rápidamente una estrategia de migración a la nube. En este caso, las aplicaciones se rehospedados. La mayoría del rehospedaje puede automatizarse mediante [Azure Migrate](https://aka.ms/azuremigrate), un servicio que ofrece la orientación, la información y los mecanismos necesarios para facilitar la migración a Azure basada en herramientas de la nube, como [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/) y [Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/). También puede configurar el rehospedaje manualmente, para poder aprender los detalles de los recursos de la infraestructura al mover las aplicaciones heredadas a la nube. Por ejemplo, puede mover sus aplicaciones a las máquinas virtuales en Azure con una pequeña modificación probablemente con solo los cambios de configuración menores. En este caso, el servicio de red es similar a un entorno local, sobre todo, si crea redes virtuales en Azure.

- **Optimizada para la nube** (servicios administrados y los contenedores de Windows): este modelo consiste en hacer algunas optimizaciones importantes de implementación para obtener algunas ventajas importantes de la nube, sin tener que cambiar la arquitectura básica de la aplicación. El paso fundamental aquí es agregar la compatibilidad con los [contenedores de Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) a las aplicaciones .NET Framework existentes. Este paso importante (creación de contenedores) no requiere modificar el código, por lo que el esfuerzo general de migración mediante lift- and -shift es claro. Puede usar también herramientas como [Image2Docker](https://github.com/docker/communitytools-image2docker-win) o Visual Studio con sus herramientas para [Docker](https://www.docker.com/). Visual Studio elige automáticamente valores predeterminados inteligentes para aplicaciones ASP.NET e imágenes de contenedores de Windows. Estas herramientas ofrecen un bucle interior rápido y una ruta rápida para obtener los contenedores en Azure. La agilidad se mejora al implementar en varios entornos. A continuación, pasar a producción, puede implementar los contenedores de Windows a [Azure Web Apps for Containers](https://azure.microsoft.com/en-us/services/app-service/containers/), [Azure Container Instances (ACI) y máquinas virtuales de Azure con Windows Server 2016 y contenedores si prefiere un enfoque de IaaS. Para las aplicaciones de varios contenedores ligeramente más complejas, en orquestadores como [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/) o [Azure Kubernetes Service (AKS/ACS)](https://azure.microsoft.com/en-us/services/container-service/). Durante esta Modernización inicial, también puede agregar recursos de la nube, como la supervisión con herramientas como [Azure Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview); Las canalizaciones de CI/CD para los ciclos de vida de la aplicación con [servicios de Azure DevOps](https://visualstudio.microsoft.com/team-services/); y muchos otros servicios de recursos de datos que están disponibles en Azure. Por ejemplo, puede modificar una aplicación web monolítica desarrollada originalmente con las herramientas [Web Forms ASP.NET](https://www.asp.net/web-forms) o [ASP.NET MVC](https://www.asp.net/mvc) tradicionales, pero ahora se implementa con los contenedores de Windows. Si usa los contenedores de Windows, también debe migrar los datos a una base de datos en la [Instancia administrada de Azure SQL Database](https://docs.microsoft.com/azure/sql-database/), y todo sin tener que modificar la arquitectura de código de la aplicación.

- **Nativo en la nube**: como se mencionó, debería pensar en diseño [nativas de la nube](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) cuando tiene como destino aplicaciones grandes y complejas con varios equipos de desarrollo independiente trabajando en las aplicaciones diferentes microservicios que se pueden desarrollar e implementar de forma autónoma. Además, debido a la escalabilidad granularized e independiente por microservicio. Estos enfoques de arquitectura enfrentan a muy importantes dificultades y complejidades, pero se pueden simplificar en gran medida mediante el uso de la nube PaaS y orquestadores como [Azure Kubernetes Service (AKS/ACS)](https://azure.microsoft.com/en-us/services/container-service/) (managed Kubernetes), [servicio de Azure Tejido, y [Azure Functions](https://azure.microsoft.com/services/functions/) adoptar un enfoque sin servidor. Todos estos enfoques (por ejemplo, microservicios y sin servidor) normalmente requieren diseñar para la nube y escribir código nuevo, el código que se ha adaptado a determinadas plataformas PaaS o código que se adapte a arquitecturas específicas, tales como microservicios.

En la figura 1-3 se muestran las tecnologías internas que se pueden usar para cada nivel de madurez:

![Tecnologías internas para cada nivel de madurez de la modernización](./media/image1-3.png)

> **Figura 1-3.** Tecnologías internas para cada nivel de madurez de la modernización

## <a name="lift-and-shift-scenario"></a>Escenario de migración mediante lift- and -shift

Para las migraciones de elevación y desplazamiento, tenga en cuenta que puede usar muchas variaciones distintas de elevación y desplazamiento en los escenarios de aplicaciones. Si solo rehospeda la aplicación, puede tener un escenario como el que se muestra en la figura 1-4, donde se usan máquinas virtuales en la nube solo para la aplicación y el servidor de base de datos.

![Ejemplo de un escenario IaaS puro en la nube](./media/image1-4.png)

> **Figura 1-4**. Ejemplo de un escenario IaaS puro en la nube

## <a name="modernization-scenarios"></a>Escenarios de Modernización

Para escenarios de modernización, podría tener una aplicación optimizada para la nube pura que usa elementos solo de ese nivel de madurez. O bien, puede que tenga una aplicación de estado intermedio con algunos elementos de la infraestructura de nube listos y otros elementos de optimizada para la nube (un "elegir" o un modelo mixto), al igual que en la figura 1-5.

![Ejemplo de escenario de elección, con base de datos IaaS, DevOps y recursos incluidos en contenedores](./media/image1-5.png)

> **Figura 1-5.** Ejemplo de escenario de elección, con base de datos IaaS, DevOps y recursos incluidos en contenedores

A continuación, como el escenario ideal para muchas aplicaciones existentes de .NET Framework migrar, podría migrar a una aplicación optimizada para la nube, para obtener ventajas significativas de poco trabajo. Este enfoque también establece la configuración para nativas de la nube como una evolución posibles futuras. En la figura 1-6 se muestra un ejemplo.

![Ejemplo de escenario de aplicaciones optimizadas para la nube, con contenedores de Windows y los servicios administrados](./media/image1-6.png)

> **Figura 1-6.** Ejemplo de escenario de aplicaciones optimizadas para la nube, con contenedores de Windows y los servicios administrados

Va aún más, puede ampliar la aplicación optimizada para la nube existente mediante la adición de algunos microservicios para escenarios específicos. Esto, pasaría parcialmente al nivel de modelo de nativas de la nube, que no es el enfoque principal de esta guía.


## <a name="what-this-guide-does-not-cover"></a>Aspectos no tratados en esta guía

En esta guía se incluye un subconjunto específico de los escenarios de ejemplo, como se muestra en la figura 1-7. Esta guía se centra sólo en escenarios de migración mediante lift- and -shift y, en última instancia, en el modelo optimizado para la nube. En el modelo optimizado para la nube, una aplicación de .NET Framework se moderniza mediante contenedores de Windows, además de componentes adicionales, como la supervisión y canalizaciones de CI/CD. Cada componente es fundamental para implementar aplicaciones en la nube más rápido y con agilidad.

![Nativo en la nube no se trata en esta guía](./media/image1-7.png)

> **Figura 1-7.** Nativo en la nube no se trata en esta guía

El objetivo de esta guía es específico. Muestra la ruta de acceso que puede seguir para lograr una migración mediante lift- and -shift de las aplicaciones .NET existentes, sin necesidad de rediseñar y sin cambios de código. En última instancia, se muestra cómo hacer que su aplicación optimizada para la nube.

Esta guía no muestra cómo crear aplicaciones nativas de la nube, por ejemplo, cómo evolucionan a una arquitectura de microservicios. Para rediseñar las aplicaciones o crear otras basadas en microservicios, consulte el libro electrónico [Microservicios de. NET: arquitectura para aplicaciones .NET en contenedor](https://aka.ms/microservicesebook).

### <a name="additional-resources"></a>Recursos adicionales

- **En el contenedor de ciclo de vida de aplicaciones de Docker con la plataforma de Microsoft y herramientas** (libro electrónico descargable): [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)

- **Microservicios de. NET: Arquitectura para aplicaciones .NET en contenedor** (libro electrónico descargable): [*https://aka.ms/microservicesebook*](https://aka.ms/microservicesebook)

- **Arquitectura de aplicaciones web modernas con ASP.NET Core y Azure** (libro electrónico descargable): [*https://aka.ms/webappebook*](https://aka.ms/webappebook)

## <a name="who-should-use-this-guide"></a>Destinatarios de esta guía

Esta guía se escribió para desarrolladores y arquitectos de soluciones que desean modernizar las aplicaciones web ASP.NET existentes o los servicios WCF que se basan en .NET Framework, para mejorar la agilidad de distribución y publicación de aplicaciones.

Esta guía puede resultar útil también si es responsable de toma de decisiones, como un arquitecto empresarial o un jefe o director de desarrollo que solo desea obtener información general de las ventajas que se pueden obtener con el uso de los contenedores de Windows y con la implementación en la nube mediante Microsoft Azure.

## <a name="how-to-use-this-guide"></a>Cómo usar esta guía

En esta guía se aborda el motivo por el que modernizar las aplicaciones existentes y las ventajas específicas derivadas del uso de los contenedores de Windows al mover las aplicaciones a la nube. El contenido de los primeros capítulos de la guía está diseñado para arquitectos y responsables de tomar decisiones técnicas que desean obtener información general, pero que no necesitan centrarse en información detallada de carácter técnico ni en la implementación.

En el último capítulo de esta guía se presentan varios tutoriales centrados en escenarios de implementación específicos. Esta guía ofrece versiones más cortas de los tutoriales, para resumir los escenarios y destacar sus ventajas. Los tutoriales completos profundizan en los detalles de configuración e implementación y se publican como una serie de [entradas de wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki) en el mismo [repositorio de GitHub](https://github.com/dotnet-architecture/eShopModernizing) público en el que se encuentran aplicaciones de ejemplo relacionadas (tratadas en la siguiente sección). El último capítulo y los tutoriales detallados de la wiki de GitHub resultarán más interesantes para los desarrolladores y arquitectos que desean centrarse en los detalles de implementación.

## <a name="sample-apps-for-modernizing-legacy-apps-eshopmodernizing"></a>Aplicaciones de ejemplo para modernizar aplicaciones heredadas: eShopModernizing

En el repositorio [eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing) de GitHub se ofrecen dos aplicaciones de ejemplo que simulan aplicaciones web monolíticas heredadas. Una aplicación web se desarrolla con ASP.NET MVC; la segunda aplicación web se desarrolla con ASP.NET Web Forms y la tercera aplicación es una aplicación de N niveles con una aplicación de escritorio de cliente de WinForms consumir un servicio WCF back-end. Todas estas aplicaciones se basan en .NET Framework tradicional. Estas aplicaciones de ejemplo no usan .NET Core o ASP.NET Core, ya que se supone que se van a modernizar aplicaciones .NET Framework existentes/heredadas.

Estas aplicaciones de ejemplo tienen una segunda versión, con código modernizado, y que son bastante sencillas. La diferencia más importante entre las versiones de las aplicaciones es que las segundas versiones usan los contenedores de Windows como opción de implementación. También hay algunas adiciones en las segundas versiones, como Azure Storage Blob para administrar imágenes, Azure Active Directory para administrar la seguridad y Azure Application Insights para supervisar y auditar las aplicaciones.

## <a name="send-your-feedback"></a>Envíe sus comentarios

Esta guía se escribió para ayudarle a entender las opciones para mejorar y modernizar las aplicaciones web .NET existentes. La guía y las aplicaciones de ejemplo relacionadas evolucionan. ¡Sus comentarios son Bienvenidos! Si tiene comentarios sobre cómo esta guía podría resultar más útil, envíelos a [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book).

>[!div class="step-by-step"]
[Siguiente](lift-and-shift-existing-apps-azure-iaas.md)
