---
title: Modernización de las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows
description: Obtenga información sobre cómo elevar, desplazar y modernizar las aplicaciones existentes en la nube de Azure y en los contenedores con este e-book.
ms.date: 01/07/2021
ms.openlocfilehash: bf6e6dff75c939508947aabeda14955b880f5a89
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025482"
---
# <a name="modernize-existing-net-applications-with-azure-cloud-and-windows-containers"></a>Modernización de aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows

![Imagen de portada de la guía Modernización de las aplicaciones .NET](./media/index/web-application-guide-cover-image.png)

**EDICIÓN 5.0**

Consulte el [registro de cambios](https://aka.ms/modernize-ebook-changelog) para ver las modificaciones del libro y las colaboraciones para la comunidad.

PUBLICADO POR las divisiones Microsoft Press y Microsoft DevDiv de Microsoft Corporation, One Microsoft Way, Redmond Washington, 98052-6399

Copyright © 2021 de Microsoft Corporation

Todos los derechos reservados. No se puede reproducir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.

Este libro está disponible de forma gratuita en formato de libro electrónico (e-book) a través de varios canales de Microsoft, como <https://dot.net/architecture>.

Si tiene preguntas relacionadas con este libro, envíe un correo electrónico a [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book).

Este libro se proporciona “tal cual” y expresa las opiniones del autor. Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.

Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios. No debe deducirse ninguna asociación ni conexión reales.

Microsoft y las marcas comerciales indicadas en <https://www.microsoft.com> en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft. El resto de marcas pertenecen a sus respectivos propietarios.

Autor:
> **Cesar de la Torre**, administrador de programas sénior del equipo de producto de .NET, Microsoft Corp.

Participantes y revisores:
> **Scott Hunter**, director asociado de administrador de programas del equipo de .NET, Microsoft **Paul Yuknewicz**, director principal de administración de programas del equipo de Visual Studio Tools, Microsoft **Lisa Guthrie**, administradora de programas del equipo de Visual Studio Tools, Microsoft **Ankit Asthana**, director principal de administración de programas del equipo de .NET, Microsoft **Unai Zorrilla**, responsable de desarrollo de Plain Concepts **Javier Valero**, director de operaciones de Grupo Solutio

## <a name="introduction"></a>Introducción

Si decide modernizar las aplicaciones web o los servicios, y moverlos a la nube, no tiene necesariamente que rediseñar por completo las aplicaciones. Rediseñar una aplicación con un enfoque avanzado como los microservicios no siempre es posible por las restricciones de costos y tiempo. Según el tipo de aplicación, rediseñar una aplicación podría no ser necesario. Para optimizar la rentabilidad de la estrategia de migración a la nube de su organización, conviene tener en cuenta las necesidades de la empresa y los requisitos de las aplicaciones. Debe determinar:

- Qué aplicaciones requieren una transformación o un cambio de diseño.

- Qué aplicaciones necesitan modernizarse solo parcialmente.

- Qué aplicaciones se pueden "elevar y desplazar" directamente a la nube.

## <a name="about-this-guide"></a>Acerca de esta guía

Esta guía se centra principalmente en la modernización inicial de las aplicaciones orientadas a servicios o aplicaciones web de Microsoft .NET Framework, es decir, en la acción de mover una carga de trabajo a un entorno más moderno y nuevo sin alterar significativamente la arquitectura básica ni el código de la aplicación.

En esta guía también se destacan las ventajas derivadas de mover las aplicaciones a la nube y modernizarlas parcialmente con el uso de un conjunto específico de nuevas tecnologías y enfoques, como los contenedores de Windows y las plataformas de procesos en Azure que admiten los contenedores de Windows.

## <a name="path-to-the-cloud-for-existing-net-applications"></a>Ruta de acceso a la nube para aplicaciones .NET existentes

Las organizaciones suelen elegir la migración a la nube por la agilidad y velocidad que pueden obtener para sus aplicaciones. Puede configurar miles de servidores (VM) en la nube en cuestión de minutos, en comparación con las semanas que suele llevar la configuración de los servidores locales.

No hay una estrategia única y general para migrar las aplicaciones a la nube. La estrategia de migración adecuada para su caso dependerá de las necesidades y prioridades de la organización y del tipo de aplicaciones que se vayan a migrar. No todas las aplicaciones garantizan la inversión que conlleva la migración a un modelo de plataforma como servicio ([PaaS](https://azure.microsoft.com/overview/what-is-paas/)) o el desarrollo de un modelo de aplicación [nativa de la nube](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications). En muchos casos, puede adoptar un enfoque por fases o incremental para invertir en la migración de los recursos a la nube, en función de las necesidades de su negocio.

Para aplicaciones modernas con la mejor agilidad y el mejor valor a largo plazo para la organización, puede beneficiarse de la inversión en arquitecturas de aplicaciones *nativas de la nube*. Sin embargo, para las aplicaciones que son recursos existentes o heredados, la clave está en emplear el mínimo tiempo y dinero (sin tener que rediseñar ni cambiar el código) para migrarlas a la nube, a fin de obtener importantes ventajas.

En la figura 1-1 se muestran las posibles rutas de acceso que puede usar para migrar las aplicaciones .NET existentes a la nube en fases incrementales.

 ![Rutas de acceso de modernización de servicios y aplicaciones .NET existentes](./media/image1-1.png)

**Figura 1-1**. Rutas de acceso de modernización de servicios y aplicaciones .NET existentes

Cada método de migración tiene distintas ventajas y motivos para su uso. Puede elegir un único enfoque para migrar las aplicaciones a la nube o seleccionar determinados componentes de varios enfoques. Las aplicaciones individuales no están limitadas a un único enfoque o a un solo estado de madurez. Por ejemplo, un enfoque híbrido común tendría ciertos componentes locales y otros componentes en la nube.

A continuación se definen y explican brevemente los distintos niveles de madurez de una aplicación:

**Nivel 1: aplicaciones de infraestructura lista para la nube**: en este enfoque de migración, solo tiene que migrar o volver a hospedar las aplicaciones locales actuales a una plataforma de infraestructura como servicio ([IaaS](https://azure.microsoft.com/overview/what-is-iaas/)). Las aplicaciones tienen casi la misma composición que antes, pero ahora se implementan en máquinas virtuales en la nube.
Este sencillo tipo de migración se suele conocer en el sector como "elevar y desplazar".

**Nivel 2: aplicaciones optimizadas para la nube**: En este nivel y sin tener que rediseñar o modificar código significativo, puede obtener ventajas adicionales de la ejecución de la aplicación en la nube con tecnologías modernas como contenedores y otros servicios administrados en la nube. Se mejora la agilidad de las aplicaciones para distribuirlas con más rapidez al perfeccionar los procesos de las operaciones de desarrollo empresariales (DevOps). Esta funcionalidad se consigue mediante el uso de tecnologías como son los contenedores de Windows, que se basan en el motor de Docker. Los contenedores eliminan la fricción causada por las dependencias de la aplicación al implementarla en varias fases. En este modelo de madurez, puede implementar contenedores en IaaS o PaaS, a la vez que usa otros servicios administrados en la nube relacionados con las bases de datos, la memoria caché como servicio, la supervisión y las canalizaciones de integración continua e implementación continua (CI/CD).

El tercer nivel de madurez es el objetivo final de la nube, pero es opcional para muchas aplicaciones y no el enfoque principal de esta guía:

**Nivel 3: aplicaciones nativas para la nube**: este enfoque de migración suele basarse en las necesidades y los objetivos empresariales de modernización de las aplicaciones críticas. En este nivel, debe usar los servicios PaaS para migrar las aplicaciones a plataformas informáticas PaaS. Debe implementar la arquitectura de microservicios y aplicaciones [nativas de la nube](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) para desarrollar aplicaciones con una agilidad a largo plazo y para escalar a nuevos límites. Este tipo de modernización suele requerir un diseño específico para la nube. A menudo puede ser necesario escribir código nuevo, sobre todo, al migrar a modelos basados en microservicios y en aplicaciones nativas de la nube. Este enfoque puede ayudar a obtener ventajas que son difíciles de conseguir en un entorno de aplicaciones locales y monolíticas.

En la tabla 1-1 se describen las principales ventajas y motivos para elegir cada enfoque de migración o modernización.

| **Infraestructura preparada para la nube** <br /> *Elevación y desplazamiento* | **Optimizado para la nube** <br /> *Modernización* | **Nativo en la nube** <br /> *Modernización, rediseño y reescritura* |
|---|---|---|
| **Destino de cálculo de la aplicación** |
| Aplicaciones implementadas en las máquinas virtuales de Azure | Aplicaciones monolíticas o de n niveles implementadas en Azure App Service, Azure Container Instances (ACI), máquinas virtuales con contenedores o AKS (Azure Kubernetes Service) | Microservicios en contenedores de Azure Kubernetes Service (AKS) o microservicios sin servidor basados en Azure Functions. |
| **Destino de datos** |
| SQL o cualquier base de datos relacional en una máquina virtual | Instancia administrada de Azure SQL Database u otra base de datos administrada en la nube. | Bases de datos específicas por microservicio basadas en Azure SQL Database, Azure Cosmos DB u otra base de datos administrada en la nube |
| **Ventajas**|
| <li>Sin rediseños ni código nuevo <li> Mínimo esfuerzo para una migración rápida <li> Mínimo común denominador compatible con Azure <li> Garantías de disponibilidad básicas <li> Después de la migración a la nube, todavía es más fácil modernizar | <li> Sin rediseños <li> Cambios mínimos en el código o la configuración <li> Desarrollo y agilidad de DevOps mejorados para publicar debido a los contenedores <li> Mayor densidad y costos de implementación más bajos <li> Portabilidad de aplicaciones y dependencias <li> Flexibilidad de destinos de host: Enfoques de PaaS o IaaS | <li> Arquitecto de la nube, obtiene los mejores beneficios de la nube, pero se necesita nuevo código. <li> Enfoques nativos de la nube de los microservicios <li> Aplicaciones críticas modernas, muy escalables y resistentes en la nube <li> Servicios totalmente administrados <li> Optimizado para escalado <li> Optimizado para la agilidad autónoma por subsistema <li> Basado en implementaciones y DevOps |
| **Desafíos** |
| <li> Menor inferior de la nube, más allá del cambio en los gastos operativos o en el cierre de los centros de datos <li> Muy poca administración: sin aplicación de revisiones del SO o del software intermedio, con posibles soluciones de infraestructura, como Terraform, Spinnaker o Puppet | <li> La inclusión en contenedores es un paso adicional de la curva de aprendizaje para los desarrolladores y las operaciones de TI <li> Las canalizaciones de DevOps y CI/CD suelen ser imprescindibles en este enfoque. Si no están presentes actualmente en la cultura de la organización, podría ser un desafío adicional| <li> Es necesario volver a diseñar para las aplicaciones nativas en la nube y las arquitecturas de microservicios. Además, normalmente se requiere la reescritura o refactorización de código importante durante la modernización (mayor tiempo y presupuesto)|
> **Tabla 1-1.** Ventajas y desafíos de la modernización de rutas de los servicios y las aplicaciones .NET existentes

### <a name="key-technologies-and-architectures-by-maturity-level"></a>Arquitecturas y tecnologías clave por nivel de madurez

Las aplicaciones .NET Framework se iniciaron por primera vez con .NET Framework 1.0, que se publicó a finales de 2001. Después, las empresas cambian a nuevas versiones (como 2.0, 3.5 y .NET Framework 4.x). La mayoría de esas aplicaciones se ejecutaron en Windows Server y Internet Information Server (IIS) y usaron una base de datos relacional, como SQL Server, Oracle, MySQL o cualquier otra instancia de RDBMS.

La mayoría de las aplicaciones .NET existentes pueden basarse actualmente en .NET Framework 4.x o incluso en .NET Framework 3.5 y usar marcos de trabajo web, como ASP.NET MVC, Formularios web ASP.NET, ASP.NET Web API, Windows Communication Foundation (WCF), ASP.NET SignalR y ASP.NET Web Pages. Estas tecnologías de .NET Framework establecidas dependen de Windows. Es importante tener en cuenta esa dependencia si solo se van a migrar aplicaciones heredadas y solo se desea realizar cambios mínimos en la infraestructura de las aplicaciones.

En la figura 1-2 se muestran los estilos de arquitectura y las tecnologías principales utilizados en cada uno de los tres niveles de madurez de la nube:

![Tecnologías principales de cada nivel de madurez para modernizar las aplicaciones web .NET existentes](./media/image1-2.png)

**Figura 1-2.** Tecnologías principales de cada nivel de madurez para modernizar las aplicaciones web .NET existentes

En la figura 1-2 se destacan los escenarios más comunes, pero se pueden presentar muchas variaciones híbridas y mixtas en relación con la arquitectura. Por ejemplo, los modelos de madurez no solo se aplican a arquitecturas monolíticas de las aplicaciones web existentes, sino también a la orientación del servicio, a variaciones de n niveles y a otras variaciones de estilo de la arquitectura. El foco o porcentaje más alto en uno u otro tipo de arquitectura y las tecnologías relacionadas determina el nivel de madurez general de las aplicaciones.

Cada nivel de madurez del proceso de modernización está asociado con los siguientes enfoques y tecnologías clave:

- **Infraestructura lista para la nube** (rehospedaje o elevación y desplazamiento básicos): como primer paso, muchas organizaciones solo desean ejecutar una estrategia de migración a la nube con rapidez. En este caso, lo que se hace es rehospedar las aplicaciones. La mayoría del rehospedaje puede automatizarse mediante [Azure Migrate](https://aka.ms/azuremigrate), un servicio que ofrece la orientación, la información y los mecanismos necesarios para facilitar la migración a Azure basada en herramientas de la nube, como [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/) y [Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/). También puede configurar el rehospedaje manualmente, para poder aprender los detalles de los recursos de la infraestructura al mover las aplicaciones heredadas a la nube. Por ejemplo, puede mover las aplicaciones a las máquinas virtuales de Azure con pocas modificaciones, probablemente, solo con cambios de configuración menores. En este caso, el servicio de red es similar a un entorno local, sobre todo, si crea redes virtuales en Azure.

- **Optimizado para la nube** (servicios administrados y contenedores de Windows): este modelo consiste en hacer algunas optimizaciones importantes en la implementación para obtener algunas ventajas importantes de la nube, sin cambiar la arquitectura básica de la aplicación. El paso fundamental aquí es agregar la compatibilidad con los [contenedores de Windows](/virtualization/windowscontainers/about/) a las aplicaciones .NET Framework existentes. Este paso importante (creación de contenedores) no requiere modificar el código, por lo que el esfuerzo general de elevación y desplazamiento es bajo. Puede usar también herramientas como [Image2Docker](https://github.com/docker/communitytools-image2docker-win) o Visual Studio con sus herramientas para [Docker](https://www.docker.com/). Visual Studio elige automáticamente valores predeterminados inteligentes para aplicaciones ASP.NET e imágenes de contenedores de Windows. Estas herramientas ofrecen un bucle interior rápido y una ruta rápida para obtener los contenedores en Azure. La agilidad se mejora al implementar en varios entornos.
Después, al pasar a producción, puede implementar los contenedores de Windows en [Azure Web App for Containers](https://azure.microsoft.com/services/app-service/containers/), [Azure Container Instances (ACI)](https://azure.microsoft.com/services/container-instances/) y máquinas virtuales de Azure con Windows Server 2016 y contenedores, si prefiere un enfoque de IaaS. En el caso de las aplicaciones de varios contenedores más complejas, le recomendamos usar orquestadores como [Azure Kubernetes Service (AKS/ACS)](https://azure.microsoft.com/services/container-service/).

Durante esta modernización inicial, también puede agregar recursos desde la nube, como la supervisión con herramientas como [Azure Application Insights](/azure/application-insights/app-insights-overview); canalizaciones de CI/CD para los ciclos de vida de la aplicación con [Azure DevOps Services](https://azure.microsoft.com/services/devops/) y muchos más servicios de recursos de datos que están disponibles en Azure. Por ejemplo, puede modificar una aplicación web monolítica desarrollada originalmente con las herramientas [Web Forms ASP.NET](https://www.asp.net/web-forms) o [ASP.NET MVC](https://www.asp.net/mvc) tradicionales, pero ahora se implementa con los contenedores de Windows. Si usa los contenedores de Windows, también debe migrar los datos a una base de datos en la [Instancia administrada de Azure SQL Database](/azure/sql-database/), y todo sin tener que modificar la arquitectura de código de la aplicación.

- **Nativo en la nube**: tal como se ha explicado en la introducción, debe considerar la posibilidad de volver a diseñar aplicaciones [nativas de la nube](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) cuando su objetivo son aplicaciones grandes y complejas con varios equipos de desarrollo independientes que trabajan en diferentes microservicios que se pueden desarrollar e implementar de forma autónoma. Además, debido a la escalabilidad independiente y granular por microservicio. Estos enfoques arquitectónicos se enfrentan a desafíos y complejidades muy importantes, pero se pueden simplificar en gran medida mediante PaaS de nube y orquestadores como [Azure Kubernetes Service (AKS/ACS)](https://azure.microsoft.com/services/container-service/) (Kubernetes administrado) y [Azure Functions](https://azure.microsoft.com/services/functions/) para un enfoque sin servidor. Todos estos enfoques (por ejemplo, microservicios y sin servidor) normalmente requieren que se diseñe la aplicación para la nube y se escriba código nuevo que se adapte a determinadas plataformas PaaS o código que se adapte a arquitecturas específicas, como microservicios.

En la figura 1-3 se muestran las tecnologías internas que se pueden usar para cada nivel de madurez:

![Tecnologías internas para cada nivel de madurez de la modernización](./media/image1-3.png)

**Figura 1-3.** Tecnologías internas para cada nivel de madurez de la modernización

## <a name="lift-and-shift-scenario"></a>Escenario de elevación y desplazamiento

Para las migraciones de elevación y desplazamiento, tenga en cuenta que puede usar muchas variaciones distintas de elevación y desplazamiento en los escenarios de aplicaciones. Si solo rehospeda la aplicación, puede tener un escenario como el que se muestra en la figura 1-4, donde se usan máquinas virtuales en la nube solo para la aplicación y el servidor de base de datos.

![Ejemplo de un escenario IaaS puro en la nube](./media/image1-4.png)

**Figura 1-4**. Ejemplo de un escenario IaaS puro en la nube

## <a name="modernization-scenarios"></a>Escenarios de modernización

Para los escenarios de modernización, puede disponer de una aplicación pura optimizada para la nube que usa elementos solo de dicho nivel de madurez. También puede tener una aplicación de estado intermedio con algunos elementos de la infraestructura lista para la nube y otros elementos de operaciones optimizadas para la nube (un modelo de elección o mixto), como el que se muestra en la figura 1-5.

![Ejemplo de escenario de elección, con base de datos IaaS, DevOps y recursos incluidos en contenedores](./media/image1-5.png)

**Figura 1-5.** Ejemplo de escenario de elección, con base de datos IaaS, DevOps y recursos incluidos en contenedores

A continuación, como el escenario ideal para muchas aplicaciones .NET Framework existentes que se van a migrar, podría migrar a una aplicación optimizada para la nube para obtener importantes ventajas por el hecho de tener que realizar poco trabajo. Este enfoque también lo prepara para la opción de nativo en la nube como un posible paso posterior. En la figura 1-6 se muestra un ejemplo.

![Ejemplo de escenario de aplicaciones optimizadas para la nube, con contenedores de Windows y servicios administrados](./media/image1-6.png)

**Figura 1-6.** Ejemplo de escenario de aplicaciones optimizadas para la nube, con contenedores de Windows y servicios administrados

Para ir incluso más allá, puede extender la aplicación optimizada para la nube existente con la adición de algunos microservicios para escenarios específicos. De esta forma, pasaría parcialmente al nivel de aplicación nativa de la nube, que no es el enfoque principal de esta guía.

## <a name="what-this-guide-does-not-cover"></a>Aspectos no tratados en esta guía

En esta guía se incluye un subconjunto específico de los escenarios de ejemplo, como se muestra en la figura 1-7. Esta guía se centra solo en los escenarios de elevación y desplazamiento y, en última instancia, en el modelo de operaciones optimizadas para la nube. En el modelo de operaciones optimizadas para la nube, una aplicación .NET Framework se moderniza mediante contenedores de Windows, así como con componentes adicionales, como la supervisión y las canalizaciones de CI/CD. Cada componente es fundamental para implementar aplicaciones en la nube más rápido y con agilidad.

![Las aplicaciones nativas de la nube no se tratarán en esta guía.](./media/image1-7.png)

**Figura 1-7.** Las aplicaciones nativas de la nube no se tratarán en esta guía.

El objetivo de esta guía es específico. Se muestra la ruta que se puede adoptar para conseguir una elevación y un desplazamiento de las aplicaciones .NET existentes, sin rediseñar ni cambiar el código. En última instancia, se explica cómo hacer que la aplicación tenga operaciones optimizadas para la nube.

En esta guía no se explica cómo crear aplicaciones nativas de la nube, como la forma de evolucionar a una arquitectura de microservicios. Para rediseñar las aplicaciones o crear otras basadas en microservicios, consulte el libro electrónico [Microservicios de .NET: Arquitectura para aplicaciones .NET en contenedor](https://aka.ms/microservicesebook).

### <a name="additional-resources"></a>Recursos adicionales

- **Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft;** (libro electrónico descargable) \
  <https://aka.ms/dockerlifecycleebook>

- **Microservicios de .NET. Arquitectura para aplicaciones .NET en contenedor** (libro electrónico descargable) \
  <https://aka.ms/microservicesebook>

- **Diseño de aplicaciones web modernas con ASP.NET Core y Azure** (libro electrónico descargable) \
  <https://aka.ms/webappebook>

## <a name="who-should-use-this-guide"></a>Destinatarios de esta guía

Esta guía se escribió para desarrolladores y arquitectos de soluciones que quieren modernizar aplicaciones web ASP.NET o servicios WCF existentes basados en .NET Framework, para mejorar la agilidad de distribución y publicación de aplicaciones.

Esta guía puede resultar útil también si es responsable de toma de decisiones, como un arquitecto empresarial o un jefe o director de desarrollo que solo desea obtener información general de las ventajas que se pueden obtener con el uso de los contenedores de Windows y con la implementación en la nube mediante Microsoft Azure.

## <a name="how-to-use-this-guide"></a>Cómo usar esta guía

En esta guía se aborda el motivo por el que modernizar las aplicaciones existentes y las ventajas específicas derivadas del uso de los contenedores de Windows al mover las aplicaciones a la nube. El contenido de los primeros capítulos de la guía está diseñado para arquitectos y responsables de tomar decisiones técnicas que desean obtener información general, pero que no necesitan centrarse en información detallada de carácter técnico ni en la implementación.

En el último capítulo de esta guía se presentan varios tutoriales centrados en escenarios de implementación específicos. En esta guía, se ofrecen versiones más cortas de los tutoriales, para resumir los escenarios y destacar sus ventajas. Los tutoriales completos profundizan en los detalles de configuración e implementación y se publican como una serie de [entradas de wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki) en el mismo [repositorio de GitHub](https://github.com/dotnet-architecture/eShopModernizing) público en el que se encuentran aplicaciones de ejemplo relacionadas (tratadas en la siguiente sección). El último capítulo y los tutoriales detallados de la wiki de GitHub resultarán más interesantes para los desarrolladores y arquitectos que desean centrarse en los detalles de implementación.

## <a name="sample-apps-for-modernizing-legacy-apps-eshopmodernizing"></a>Aplicaciones de ejemplo para modernizar aplicaciones heredadas: eShopModernizing

En el repositorio [eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing) de GitHub se ofrecen dos aplicaciones de ejemplo que simulan aplicaciones web monolíticas heredadas. Una aplicación web se desarrolla mediante ASP.NET MVC; la segunda aplicación web se desarrolla mediante ASP.NET Web Forms y la tercera aplicación es una aplicación de n niveles con una aplicación de escritorio cliente de WinForms que consume un back-end de servicio WCF. Todas estas aplicaciones se basan en el marco .NET Framework tradicional. Estas aplicaciones de ejemplo no usan .NET Core, .NET 5.0 o ASP.NET Core, ya que se supone que se van a modernizar aplicaciones .NET Framework existentes o heredadas.

Estas aplicaciones de ejemplo tienen una segunda versión, con código modernizado, y son bastante sencillas. La diferencia más importante entre las versiones de las aplicaciones es que las segundas versiones usan los contenedores de Windows como opción de implementación. También hay algunas adiciones en las segundas versiones, como Azure Storage Blob para administrar imágenes, Azure Active Directory para administrar la seguridad y Azure Application Insights para supervisar y auditar las aplicaciones.

## <a name="send-your-feedback"></a>Envíe sus comentarios

Esta guía se escribió para ayudar a entender las opciones para mejorar y modernizar las aplicaciones web .NET existentes. La guía y las aplicaciones de ejemplo relacionadas evolucionan. Le agradecemos sus comentarios. Si tiene comentarios sobre cómo esta guía podría resultar más útil, envíelos a [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book).

>[!div class="step-by-step"]
>[Siguiente](lift-and-shift-existing-apps-azure-iaas.md) <!-- Next Chapter -->
