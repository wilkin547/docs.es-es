---
title: Recomendaciones de hospedaje en Azure de aplicaciones web ASP.NET Core
description: Aplicaciones web modernas con ASP.NET Core y Azure | Recomendaciones de hospedaje en Azure de aplicaciones web ASP.NET Core
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 868f1b7ce452be9e29b921888f90d128e074ba13
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="azure-hosting-recommendations-for-aspnet-core-web-apps"></a>Recomendaciones de hospedaje en Azure de aplicaciones web ASP.NET Core

> "Los líderes de línea de negocio en todas partes evitan a los departamentos de TI para obtener aplicaciones de la nube (también conocidas como SaaS) y pagar por ellas como harían con la suscripción a una revista. Y cuando el servicio ya no es necesario, pueden cancelar la suscripción sin dejar ningún equipo sin usar en un rincón".  
> _\- Daryl Plummer, analista de Gartner_

## <a name="summary"></a>Resumen

Windows Azure es capaz de admitir las necesidades y la arquitectura de la aplicación. Las necesidades de hospedaje pueden ser tan simples como un sitio web estático a una aplicación muy sofisticada formada por decenas de servicios. Para las aplicaciones web monolíticas de ASP.NET Core y los servicios complementarios, se recomiendan varias configuraciones conocidas. Las recomendaciones siguientes se agrupan según el tipo de recurso que se va a hospedar, ya sean aplicaciones completas, procesos individuales o datos.

## <a name="web-applications"></a>Aplicaciones Web

Las aplicaciones web se pueden hospedar con:

-   App Service Web Apps

-   Contenedores

-   Azure Service Fabric

-   Máquinas virtuales (VM)

De estas, App Service Web Apps son el enfoque recomendado para la mayoría de los escenarios. Para las arquitecturas de microservicios, considere la posibilidad de un enfoque basado en contenedores, o bien	Service Fabric. Si necesita más control sobre los equipos que ejecutan la aplicación, considere la posibilidad de Azure Virtual Machines.

### <a name="app-service-web-apps"></a>App Service Web Apps

App Service Web Apps proporciona una plataforma totalmente administrada optimizada para el hospedaje de aplicaciones web. Es una oferta de plataforma como servicio (PaaS) que permite centrarse en la lógica de negocios, mientras Azure se encarga de la infraestructura necesaria para ejecutar y escalar la aplicación. Algunas características clave de App Service Web Apps son estas:

-   Optimización de DevOps (integración y entrega continuas, varios entornos, pruebas A/B, compatibilidad con scripting)

-   Escala global y alta disponibilidad

-   Conexiones a plataformas SaaS y datos locales

-   Seguridad y cumplimiento

-   integración de Visual Studio

Azure App Service es la mejor opción para la mayoría de las aplicaciones web. La implementación y la administración se integran en la plataforma, los sitios se pueden escalar rápidamente para controlar grandes cargas de tráfico y el administrador de tráfico y equilibrio de carga integrado proporcionan alta disponibilidad. Puede mover fácilmente los sitios existentes a Azure App Service con una herramienta de migración en línea, usar una aplicación de código abierto de la Galería de aplicaciones web o crear un sitio con el marco y las herramientas que elija. La característica WebJobs facilita agregar el procesamiento de trabajos en segundo plano a la aplicación web de App Service.

### <a name="containers-and-azure-container-service"></a>Contenedores y Azure Container Service

Azure Container Service simplifica la creación, configuración y administración de un clúster de máquinas virtuales preconfiguradas para ejecutar aplicaciones en contenedores. Usa una configuración optimizada de herramientas de orquestación y programación de código abierto populares. Esto permite usar habilidades existentes o aprovechar un gran corpus creciente de conocimientos de la comunidad para implementar y administrar aplicaciones basadas en contenedor en Microsoft Azure.

Azure Container Service simplifica la creación, configuración y administración de un clúster de máquinas virtuales preconfiguradas para ejecutar aplicaciones en contenedores. Usa una configuración optimizada de herramientas de orquestación y programación de código abierto populares. Esto permite usar habilidades existentes o aprovechar un gran corpus creciente de conocimientos de la comunidad para implementar y administrar aplicaciones basadas en contenedor en Microsoft Azure.

Un objetivo de Azure Container Service es proporcionar un entorno de hospedaje de contenedores mediante tecnologías y herramientas de código abierto populares en la actualidad entre los clientes de Microsoft. Con este objetivo, Azure Container Service expone los puntos de conexión de API estándar para el orquestador elegido (DC/OS, Docker Swarm o Kubernetes). Mediante el uso de estos puntos de conexión, se puede aprovechar cualquier software que sea capaz de comunicarse con esos puntos de conexión. Por ejemplo, en el caso del punto de conexión de Docker Swarm, se puede utilizar la interfaz de línea de comandos (CLI) de Docker. Para DC/OS, podría elegir la CLI de DC/OS. Para Kubernetes, podría elegir kubectl. En la figura 11-1 se muestra cómo se podrían usar estos puntos de conexión para administrar los clústeres de contenedor.

![](./media/image11-1.png)

**Figura 11-1.** Administración de Azure Container Service con puntos de conexión de Docker, Kubernetes o DC/OS.

### <a name="azure-service-fabric"></a>Azure Service Fabric

Service Fabric es una buena opción si se va a crear una aplicación o volver a escribir una aplicación existente para usar una arquitectura de microservicio. Las aplicaciones, que se ejecutan en un grupo compartido de equipos, pueden empezar siendo pequeñas y aumentar a escala masiva con cientos o miles de equipos según sea necesario. Los servicios con estado facilitan el almacenamiento del estado de la aplicación de forma coherente y confiable, y Service Fabric administra automáticamente la partición, escala y disponibilidad de los servicios en su nombre. Service Fabric también admite WebAPI con Interfaz web abierta para .NET (OWIN) y ASP.NET Core. En comparación con App Service, Service Fabric también proporciona más control sobre la infraestructura subyacente, o bien acceso directo a ella. Se puede tener acceso remoto a los servidores o configurar las tareas de inicio del servidor.

### <a name="azure-virtual-machines"></a>Azure Virtual Machines

Si tiene una aplicación existente que requeriría modificaciones importantes para ejecutarse en App Service o Service Fabric, podría elegir Virtual Machines con el fin de simplificar la migración a la nube. Pero la configuración, protección y mantenimiento correctos de las máquinas virtuales requiere mucho más tiempo y experiencia en TI en comparación con Azure App Service y Service Fabric. Si está pensando en Azure Virtual Machines, asegúrese de tener en cuenta el esfuerzo de mantenimiento continuado necesario para aplicar revisiones, actualizar y administrar el entorno de máquinas virtuales. Azure Virtual Machines es infraestructura como servicio (IaaS), mientras que App Service y Service Fabric son plataformas como servicio (Paas).

#### <a name="feature-comparison"></a>Comparación de características

| Azure App Service | Service Fabric | Máquina virtual |
|---------|----------|----------|
| Implementación casi instantánea | X | X | |
| Escalar verticalmente a máquinas más grandes sin volver a implementar | X | X | |
| Las instancias comparten contenido y configuración; no es necesario volver a implementar o configurar al escalar | X | X | |
| Varios entornos de implementación (producción, ensayo) | X | X | |
| Administración automática de actualizaciones del sistema operativo | X | | |
| Intercambio sin problemas entre plataformas de 32 y 64 bits | X | | |
| Implementar código con Git, FTP | X | | X |
| Implementar código con WebDeploy | X | | X |
| Implementar código con TFS | X | X | X |
| Host web o nivel de servicio web de una arquitectura de varios niveles | X | X | X |
| Acceso a servicios de Azure como Service Bus, Storage, SQL Database | X | X | X |
| Instalar cualquier MSI personalizado | | X | X |

## <a name="logical-processes"></a>Procesos lógicos

Los procesos lógicos individuales que se pueden desacoplar del resto de la aplicación se pueden implementar por separado en Azure Functions de forma "sin servidor". Azure Functions permite escribir simplemente el código que se necesita para un problema determinado, sin preocuparse por la aplicación o infraestructura para ejecutarlo. Se puede elegir entre una variedad de lenguajes de programación, incluyendo C\#, F\#, Node.js, Python y PHP, lo que permite elegir el lenguaje más productivo para la tarea en cuestión. Al igual que la mayoría de las soluciones basadas en la nube, solo se paga por la cantidad de tiempo que se usa y se puede confiar en Azure Functions para escalar verticalmente según sea necesario.

## <a name="data"></a>Datos

Azure ofrece una amplia variedad de opciones de almacenamiento de datos, por lo que la aplicación puede usar el proveedor de datos adecuado para los datos en cuestión.

Para los datos transaccionales y relacionales, Azure SQL Database es la mejor opción. Para los datos de alto rendimiento y principalmente de solo lectura, una caché en Redis respaldada por Azure SQL Database es una buena solución.

Los datos JSON no estructurados se pueden almacenar de diferentes formas, desde columnas de SQL Database a Blobs o Tablas de Azure Storage, a DocumentDB. De todos estos, DocumentDB ofrece la mejor funcionalidad de consulta y es la opción recomendada para un gran número de documentos basados en JSON que deben admitir las consultas.

Los datos transitorios basados en eventos o comandos que se usan para coordinar el comportamiento de la aplicación pueden usar Azure Service Bus o Azure Storage Queue. Azure Storage Bus ofrece más flexibilidad y es el servicio recomendado para mensajería no trivial dentro y entre las aplicaciones.

## <a name="architecture-recommendations"></a>Recomendaciones de arquitectura

Los requisitos de la aplicación deben dictar su arquitectura. Hay muchos servicios de Azure diferentes disponibles, y elegir el adecuado es una decisión importante. Microsoft ofrece una galería de arquitecturas de referencia para ayudar a identificar arquitecturas típicas optimizadas para escenarios comunes. Se puede enlazar una arquitectura de referencia que se asigne estrechamente a los requisitos de la aplicación o, que al menos, ofrezca un punto de partida.

En la figura 11-2 se muestra una arquitectura de referencia de ejemplo. En este diagrama se describe un enfoque de arquitectura recomendada para un sitio web del sistema de administración de contenido de Sitecore optimizado para marketing.

![](./media/image11-2.png)

**Figura 11-2.** Arquitectura de referencia del sitio web de marketing Sitecore.

**Referencias: recomendaciones de hospedaje de Azure**

-   Arquitecturas de soluciones de Azure\
    <https://azure.microsoft.com/es-es/solutions/architecture/>

-   Guía para desarrolladores de Microsoft Azure\
    <https://azure.microsoft.com/es-es/campaigns/developer-guide/>

-   Introducción a Web Apps\
    <https://docs.microsoft.com/es-es/azure/app-service/app-service-web-overview>

-   Comparación de Azure App Service, Virtual Machines, Service Fabric y Cloud Services\
    <https://docs.microsoft.com/es-es/azure/app-service/choose-web-site-cloud-service-vm>

>[!div class="step-by-step"]
[Anterior] (development-process-for-azure.md)
