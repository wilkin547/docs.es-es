---
title: Hospedaje de recomendaciones para las aplicaciones web de ASP.NET Core de Azure
description: "Diseñar aplicaciones Web modernas con ASP.NET Core y Azure | Hospedaje de recomendaciones para las aplicaciones web ASP.NET de Azure"
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
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="azure-hosting-recommendations-for-aspnet-core-web-apps"></a>Hospedaje de recomendaciones para las aplicaciones Web de ASP.NET Core de Azure

> "Líderes de la línea de negocio en todas partes son omitiendo los departamentos de TI para obtener aplicaciones de la nube (también conocido como SaaS) y pagar por ellos como haría con una suscripción revista. Y cuando el servicio ya no es necesario, puede cancelar la suscripción con ningún equipo restante no se utiliza en la esquina."  
> _\- Daryl Plummer, analista de Gartner_

## <a name="summary"></a>Resumen

La arquitectura y las necesidades de su aplicación, Windows Azure sea compatible con él. Sus necesidades de hospedaje pueden ser tan simples como un sitio web estático a una aplicación muy sofisticado consta de decenas de servicios. Para las aplicaciones de ASP.NET Core monolítico web y servicios de soporte técnico, hay varias configuraciones conocidas que se recomiendan. Las siguientes recomendaciones se agrupan según el tipo de recurso para hospedarse, si completas aplicaciones, los procesos individuales o los datos.

## <a name="web-applications"></a>Aplicaciones Web

Pueden hospedar aplicaciones Web con:

-   Aplicaciones de servicio de aplicaciones Web

-   Contenedores

-   Azure Service Fabric.

-   Máquinas virtuales (VM)

De estos, las aplicaciones de servicio Web de aplicación son el método recomendado para la mayoría de los escenarios. Para crear arquitecturas de microservicio, considere la posibilidad de un enfoque basado en el contenedor o del tejido de servicio. Si necesita más control sobre los equipos que ejecutan la aplicación, considere la posibilidad de máquinas virtuales de Azure.

### <a name="app-service-web-apps"></a>Aplicaciones de servicio de aplicaciones Web

Aplicaciones de servicio de aplicaciones Web proporciona una plataforma completamente administrada optimizada para el hospedaje de aplicaciones web. Es un platform-as-a-service(PaaS) que le permite que centrarse en la lógica de negocios, mientras Azure se encarga de la infraestructura necesaria para ejecutar y escalar la aplicación de la oferta. Algunas características claves de aplicación del servicio de aplicaciones Web:

-   Optimización de DevOps (integración continua y la entrega, varios entornos A / B realizar pruebas, compatibilidad con scripting)

-   Alta disponibilidad y escala global

-   Conexiones a los datos locales y de plataformas SaaS

-   Seguridad y cumplimiento

-   integración de Visual Studio

Servicio de aplicaciones de Azure es la mejor opción para la mayoría de las aplicaciones web. Implementación y administración se integran en la plataforma, sitios pueden escalar rápidamente para controlar grandes cargas de tráfico y el Administrador de tráfico y equilibrio de carga integrados proporcionan alta disponibilidad. Puede mover los sitios existentes al servicio de aplicaciones de Azure fácilmente con una herramienta de migración en línea, usa una aplicación de código abierto de la Galería de aplicaciones Web o crear un sitio nuevo con el marco y las herramientas de generación de su elección. La característica WebJobs facilita la Agregar trabajo en segundo plano de procesamiento a la aplicación de servicio de aplicaciones web.

### <a name="containers-and-azure-container-service"></a>Contenedores y el servicio de contenedor de Azure

Servicio de contenedor de Azure simplifica la tarea crear, configurar y administrar un clúster de máquinas virtuales que están preconfigurados para ejecutar aplicaciones en contenedores. Usa una configuración optimizada de herramientas de programación y la orquestación de código abierto populares. Esto le permite utilizar sus conocimientos existentes o dibujar en un cuerpo elevado y creciente de conocimientos de la Comunidad, implementar y administrar aplicaciones basadas en el contenedor en Microsoft Azure.

Servicio de contenedor de Azure simplifica la tarea crear, configurar y administrar un clúster de máquinas virtuales que están preconfigurados para ejecutar aplicaciones en contenedores. Usa una configuración optimizada de herramientas de programación y la orquestación de código abierto populares. Esto le permite utilizar sus conocimientos existentes o dibujar en un cuerpo elevado y creciente de conocimientos de la Comunidad, implementar y administrar aplicaciones basadas en el contenedor en Microsoft Azure.

Un objetivo de servicio de contenedor de Azure consiste en proporcionar un entorno de hospedaje de contenedor mediante herramientas de código abierto y tecnologías que son populares entre los clientes de Microsoft de hoy en día. Con este objetivo, el servicio de contenedor de Azure expone los extremos de API estándar para su orchestrator elegido (controlador de dominio/OS, Docker Swarm o Kubernetes). Mediante el uso de estos puntos de conexión, puede aprovechar cualquier software que es capaz de comunicarse con esos puntos de conexión. Por ejemplo, en el caso extremo de Docker Swarm, puede utilizar la interfaz de línea de comandos de Docker (CLI). Para DC/OS, puede elegir la CLI DCOS. Para Kubernetes, puede elegir kubectl. Figura 11-1 muestra cómo podría utilizar estos extremos para administrar los clústeres de contenedor.

![](./media/image11-1.png)

**Figura 11-1.** Administración de servicio de contenedor de Azure con Docker, Kubernetes o DC/OS puntos de conexión.

### <a name="azure-service-fabric"></a>Azure Service Fabric.

Service Fabric es una buena opción si va a crear una nueva aplicación o volver a escribir una aplicación existente para utilizar una arquitectura de microservicio. Las aplicaciones, que se ejecutan en un grupo compartido de máquinas, pueden empezar siendo pequeñas y aumentar su capacidad y escala masiva con cientos o miles de equipos según sea necesario. Servicios con estado que sean fáciles de forma coherente y confiable almacenar el estado de la aplicación y Service Fabric administra automáticamente la partición de servicio, la escala y la disponibilidad en su nombre. Service Fabric también admite WebAPI con interfaz Web abierta para .NET (OWIN) y ASP.NET Core. En comparación con el servicio de aplicaciones, Service Fabric también proporciona más control sobre o acceso directo a la infraestructura subyacente. Puede remoto en los servidores o configurar las tareas de inicio del servidor.

### <a name="azure-virtual-machines"></a>Azure Virtual Machines

Si tiene una aplicación existente que requeriría sustanciales modificaciones para que se ejecute en el servicio de aplicaciones o del tejido de servicio, puede elegir las máquinas virtuales con el fin de simplificar la migración a la nube. Sin embargo, correctamente configurar, proteger y mantener las máquinas virtuales requiere mucho más tiempo y experiencia en TI en comparación con el servicio de aplicaciones de Azure y el tejido de servicio. Si está pensando en máquinas virtuales de Azure, asegúrese de que tener en cuenta la intervención de un mantenimiento continuado necesaria para aplicar la revisión, actualizar y administrar su entorno de máquinas virtuales. Máquinas virtuales de Azure es la infraestructura como-servicio (IaaS), mientras que el servicio de aplicación y el tejido de servicio son plataforma como-servicio (Paas).

#### <a name="feature-comparison"></a>Comparación de características

| Característica Servicio de aplicaciones | Service Fabric. | Máquina virtual |
|---------|----------|----------|
| Implementación casi instantánea | X | X | |
| Escalado a máquinas más grandes sin volver a implementar | X | X | |
| Instancias comparten contenido y configuración. No hay necesidad de volver a implementar o reconfigure al escalar | X | X | |
| Varios entornos de implementación (producción, ensayo) | X | X | |
| Administración automática de actualización de sistema operativo | X | | |
| Sin problemas al cambiar entre plataformas de 32 y 64 bits | X | | |
| Implementar código con Git, FTP | X | | X |
| Implementar código con WebDeploy | X | | X |
| Implementar código con TFS | X | X | X |
| Host web o nivel de servicio web de arquitectura de varios nivel | X | X | X |
| Obtener acceso a los servicios de Azure como base de datos de SQL de Bus de servicio, almacenamiento, | X | X | X |
| Instalar cualquier MSI personalizado | | X | X |

## <a name="logical-processes"></a>Procesos lógicos

Procesos individuales de lógicos que pueden desacoplados del resto de la aplicación se pueden implementar por separado a las funciones de Azure de forma "sin servidor". Las funciones de Azure le permite escribir simplemente el código que necesita para un problema determinado, sin preocuparse por la aplicación o la infraestructura para ejecutarlo. Puede elegir entre una variedad de lenguajes de programación, incluyendo C\#, F\#, Node.js, Python y PHP, lo que le permite elegir el lenguaje más productivo para la tarea en cuestión. Al igual que la mayoría de las soluciones en la nube, se paga solo para la cantidad de tiempo de su uso y se pueden confiar en las funciones de Azure para escalar verticalmente según sea necesario.

## <a name="data"></a>Datos

Azure ofrece una amplia variedad de opciones de almacenamiento de datos, por lo que la aplicación puede utilizar el proveedor de datos adecuado para los datos en cuestión.

Para los datos transaccionales y relacionales, bases de datos de SQL Azure son la mejor opción. Para los datos principalmente de solo lectura de alto rendimiento, una caché en Redis respaldada por una base de datos de SQL Azure es una buena solución.

Los datos no estructurados de JSON se pueden almacenar en una variedad de formas, de las columnas de base de datos SQL para Blobs o tablas de almacenamiento de Azure, de documentos. De estos, documentos ofrece la mejor funcionalidad de consulta y es la opción recomendada para un gran número de documentos basada en JSON que deben admitir la consulta.

Datos transitorio basado en eventos o comando que usa para coordinar el comportamiento de la aplicación pueden utilizar Service Bus de Azure o colas de almacenamiento de Azure. Bus de almacenamiento de Azure ofrece más flexibilidad y es el servicio recomendado para dentro y entre las aplicaciones de mensajería no trivial.

## <a name="architecture-recommendations"></a>Recomendaciones de arquitectura

Requisitos de su aplicación deben dictar su arquitectura. Hay muchos servicios de Azure diferentes disponibles, elegir que el derecho es una decisión importante. Microsoft ofrece una galería de arquitecturas de referencia para ayudar a identificar típicas arquitecturas optimizadas para escenarios comunes. Puede enlazar una arquitectura de referencia que se asigna estrechamente a los requisitos de su aplicación o en menos ofrece un punto de partida.

Figura 11-2 muestra una arquitectura de referencia de ejemplo. Este diagrama describe un enfoque de arquitectura recomendada para un sitio Web del sistema de administración de contenido del Sitecore optimizado para marketing.

![](./media/image11-2.png)

**Figura 11-2.** Arquitectura de referencia de sitio Web marketing Sitecore.

**Referencias: recomendaciones de hospedaje de Azure**

-   Solución de Azure Architectures\
    <https://azure.microsoft.com/solutions/architecture/>

-   Guide\ para desarrolladores de Azure
    <https://azure.microsoft.com/campaigns/developer-guide/>

-   ¿Qué es el servicio de aplicaciones de Azure? \
    <https://docs.microsoft.com/azure/app-service/app-service-value-prop-what-is>

-   Servicio de aplicaciones de Azure, máquinas virtuales, Service Fabric y Comparison\ de servicios de nube
    <https://docs.microsoft.com/azure/app-service-web/choose-web-site-cloud-service-vm>

>[!div class="step-by-step"]
[Previous] (development-process-for-azure.md)
