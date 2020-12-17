---
title: Recomendaciones de hospedaje en Azure de aplicaciones web ASP.NET Core
description: Aplicaciones web modernas con ASP.NET Core y Azure | Recomendaciones de hospedaje en Azure de aplicaciones web ASP.NET Core
author: ardalis
ms.author: wiwagn
ms.date: 12/01/2020
ms.openlocfilehash: c209a7fa9ce89e12466424f750d5583a59f8b980
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851723"
---
# <a name="azure-hosting-recommendations-for-aspnet-core-web-apps"></a>Recomendaciones de hospedaje en Azure de aplicaciones web ASP.NET Core

> "Los líderes de línea de negocio en todas partes evitan que los departamentos de TI tengan que obtener aplicaciones de la nube (también conocidas como SaaS) y pagar por ellas como harían con la suscripción a una revista. Y cuando el servicio ya no es necesario, pueden cancelar la suscripción sin dejar ningún equipo sin usar en un rincón".  
> _\- Daryl Plummer, analista de Gartner_

Sean cuales sean las necesidades y la arquitectura de la aplicación, Microsoft Azure puede darle servicio. Las necesidades de hospedaje pueden ser tan simples como un sitio web estático o una aplicación sofisticada formada por decenas de servicios. Para las aplicaciones web monolíticas de ASP.NET Core y los servicios complementarios, se recomiendan varias configuraciones conocidas. Las recomendaciones de este artículo se agrupan según el tipo de recurso que se va a hospedar, ya sean aplicaciones completas, procesos individuales o datos.

## <a name="web-applications"></a>Aplicaciones web

Las aplicaciones web se pueden hospedar con:

- App Service Web Apps

- Contenedores (varias opciones)

- Máquinas virtuales (VM)

De estas, App Service Web Apps es el enfoque recomendado para la mayoría de los escenarios, incluidas las aplicaciones sencillas basadas en contenedores. Para las arquitecturas de microservicios, considere la posibilidad de un enfoque basado en contenedores. Si necesita más control sobre los equipos que ejecutan la aplicación, considere la posibilidad de Azure Virtual Machines.

### <a name="app-service-web-apps"></a>App Service Web Apps

App Service Web Apps proporciona una plataforma totalmente administrada optimizada para el hospedaje de aplicaciones web. Es una oferta de plataforma como servicio (PaaS) que permite centrarse en la lógica de negocios, mientras Azure se encarga de la infraestructura necesaria para ejecutar y escalar la aplicación. Algunas características clave de App Service Web Apps son estas:

- Optimización de DevOps (integración y entrega continuas, varios entornos, pruebas A/B, compatibilidad con scripting).

- Escala global y alta disponibilidad.

- Conexiones a plataformas SaaS y datos locales.

- Seguridad y cumplimiento.

- Integración de Visual Studio.

Azure App Service es la mejor opción para la mayoría de las aplicaciones web. La implementación y la administración se integran en la plataforma, los sitios se pueden escalar rápidamente para controlar grandes cargas de tráfico y el administrador de tráfico y equilibrio de carga integrado proporcionan alta disponibilidad. Puede trasladar sitios existentes a Azure App Service de forma sencilla con una herramienta de migración en línea. Puede usar una aplicación de código abierto de la Galería de aplicaciones web, o crear un sitio con el marco y las herramientas que elija. La característica WebJobs facilita agregar el procesamiento de trabajos en segundo plano a la aplicación web de App Service. Si tiene una aplicación de ASP.NET existente hospedada en el entorno local mediante una base de datos local, existe una ruta de acceso clara para la migración. Puede usar una aplicación web de App Service con una base de datos de Azure SQL Database (o un acceso seguro al servidor de la base de datos local, si lo prefiere).

![Estrategia de migración recomendada para aplicaciones de .NET locales a Azure App Service](./media/image1-6.png)

En la mayoría de los casos, el traslado de una aplicación ASP.NET hospedada localmente a una aplicación web de App Service es un proceso sencillo. Se requiere poca o ninguna modificación de la propia aplicación, y puede comenzar rápidamente a aprovechar las muchas características que ofrece Azure App Service Web Apps.

Además de las aplicaciones que no están optimizadas para la nube, las aplicaciones de Azure App Service Web Apps son una excelente solución para muchas aplicaciones sencillas monolíticas (no distribuidas); por ejemplo, muchas aplicaciones de ASP.NET Core. En este enfoque, la arquitectura es básica y fácil de comprender y administrar:

![Arquitectura básica de Azure](./media/image1-5.png)

Un número pequeño de recursos en un único grupo de recursos es normalmente suficiente para administrar este tipo de aplicación. Las aplicaciones que se implementan normalmente como una sola unidad, en lugar de las aplicaciones que se componen de muchos procesos independientes, son buenas candidatas para este [enfoque arquitectónico básico](/azure/architecture/reference-architectures/app-service-web-app/basic-web-app). A pesar de su arquitectura sencilla, este enfoque permite a la aplicación hospedada escalarse de manera vertical (más recursos por nodo) y horizontal (más nodos hospedados) para satisfacer cualquier aumento en la demanda. Con el escalado automático, la aplicación puede configurarse para ajustar automáticamente el número de nodos que hospedan la aplicación según la demanda y la carga media entre los nodos.

### <a name="app-service-web-apps-for-containers"></a>App Service Web Apps for Containers

Además de para brindar compatibilidad para hospedar aplicaciones web directamente, [App Service Web Apps for Containers](https://azure.microsoft.com/services/app-service/containers/) puede usarse para ejecutar aplicaciones en contenedores en Windows y Linux. Con este servicio, puede implementar y ejecutar fácilmente aplicaciones en contenedores que se pueden escalar con su negocio. Las aplicaciones tienen todas las características de App Service Web Apps mencionadas anteriormente. Además, Web Apps for Containers admite CI/CD simplificadas con Docker Hub, Azure Container Registry y GitHub. Puede usar Azure DevOps para definir las canalizaciones de compilación e implementación que publican los cambios en un registro. Estos cambios pueden probarse entonces en un entorno de ensayo e implementarse automáticamente en producción mediante ranuras de implementación, permitiendo así actualizaciones sin tiempo de inactividad. La reversión a versiones anteriores puede hacerse fácilmente.

Hay algunos escenarios donde Web­ Apps for Containers es la solución más conveniente. Si tiene aplicaciones que puede incluir en contenedores, ya sean de Windows o Linux, puede hospedarlas fácilmente con este conjunto de herramientas. Simplemente publique su contenedor y, después, configure Web­ Apps for Containers para extraer la versión más reciente de esa imagen del registro de su elección. Este es un enfoque de "elevación y desplazamiento" para migrar desde los modelos de hospedaje de aplicaciones clásicos a un modelo optimizado para la nube.

![Migración de una aplicación .NET local en contenedor a Azure Web­ Apps for Containers](./media/image1-8.png)

Este enfoque también funciona bien si el equipo de desarrollo puede pasarse a un proceso de desarrollo basado en contenedores. El "bucle interno" del desarrollo de aplicaciones con contenedores incluye la creación de la aplicación con contenedores. Los cambios realizados en el código, así como en la configuración del contenedor, se insertan en el control de código fuente, y una compilación automatizada es responsable de la publicación de nuevas imágenes del contenedor en un registro, como Docker Hub o Azure Container Registry. Estas imágenes, a continuación, sirven como base para el desarrollo adicional, así como para las implementaciones en producción, tal como se muestra en el diagrama siguiente:

![Flujo de trabajo del ciclo de vida de DevOps de Docker de un extremo a otro](./media/image1-7.png)

El desarrollo con contenedores ofrece muchas ventajas, especialmente cuando se usan contenedores en producción. Se usa la misma configuración de los contenedores para hospedar la aplicación en cada entorno en el que se ejecuta, desde la máquina de desarrollo local hasta la compilación y prueba de sistemas en producción. Este enfoque reduce en gran medida la probabilidad de que surjan defectos resultantes de las diferencias en la configuración de la máquina o las versiones de software. Los desarrolladores también pueden usar las herramientas con las que sean más productivos, incluido el sistema operativo, ya que los contenedores pueden ejecutarse en cualquier sistema operativo. En algunos casos, las aplicaciones distribuidas que implican muchos contenedores pueden requerir una gran cantidad de recursos para ejecutarse en una sola máquina de desarrollo. En este escenario, puede ser conveniente actualizar para utilizar Kubernetes y Azure Dev Spaces, que se describen en la siguiente sección.

A medida que partes de aplicaciones más grandes se dividen en sus propios *microservicios* más pequeños e independientes, se pueden usar patrones de diseño adicionales para mejorar el comportamiento de la aplicación. En lugar de trabajar directamente con los servicios individuales, una *puerta de enlace API* puede simplificar el acceso y desacoplar el cliente desde su back-end. El hecho de contar con back-end de servicio independientes para diferentes front-end permite también que los servicios evolucionen junto con sus consumidores. Se puede acceder a los servicios comunes a través de un contenedor *asociado* independiente, que puede incluir bibliotecas de conectividad de clientes comunes mediante el patrón de *embajador*.

![Arquitectura de ejemplo de microservicios con varios patrones de diseño comunes observados.](./media/image1-10.png)

[Más información sobre los patrones de diseño que se deben considerar al crear sistemas basados en microservicios.](/azure/architecture/microservices/design/patterns)

### <a name="azure-kubernetes-service"></a>Azure Kubernetes Service

Azure Kubernetes Service (AKS) administra el entorno hospedado de Kubernetes, lo que acelera y facilita la implementación y administración de aplicaciones en contenedores sin necesidad de tener conocimientos de orquestación de contenedores. También se elimina la carga de las operaciones en curso y el mantenimiento mediante el aprovisionamiento, la actualización y el escalado de los recursos a petición, sin tener que desconectar las aplicaciones.

AKS reduce la complejidad y la sobrecarga operativa de la administración de un clúster de Kubernetes mediante la descarga de gran parte de esa responsabilidad en Azure. Como un servicio de Kubernetes hospedado, Azure controla de forma automática tareas críticas como el seguimiento de estado y el mantenimiento. Además, solo se paga por los nodos de agente en los clústeres, no por los nodos principales. Como servicio de Kubernetes administrado, AKS proporciona lo siguiente:

- Actualizaciones de la versión de Kubernetes automatizadas y aplicación de revisiones.
- Escalado de clústeres sencillo.
- Plano de control hospedado de recuperación automática (nodos principales).
- Ahorro de costos: pague solo por los nodos de grupo de agentes en ejecución.

Como Azure controla la administración de los nodos del clúster de AKS, ya no es necesario realizar muchas tareas manualmente, como las actualizaciones del clúster. Como Azure controla estas tareas de mantenimiento críticas de forma automática, AKS no proporciona acceso directo al clúster (por ejemplo con SSH).

Los equipos que están aprovechando AKS también pueden sacar partido de Azure Dev Spaces. Azure Dev Spaces ayuda a los equipos a centrarse en el desarrollo y la iteración rápida de su aplicación de microservicio, ya que permite a los equipos trabajar directamente con su aplicación o arquitectura de microservicios completa que se ejecuta en AKS. Azure Dev Spaces también proporciona una manera de actualizar independientemente partes de la arquitectura de microservicios de forma aislada sin afectar al resto del clúster de AKS o de otros desarrolladores.

![Ejemplo de flujo de trabajo de Azure Dev Spaces](./media/image1-9.gif)

Azure Dev Spaces:

- Minimizar los requisitos de recursos y el tiempo de configuración de la máquina local
- Permitir que los equipos iteren de manera más rápida
- Reducir el número de entornos de integración que requiere un equipo
- Eliminar la necesidad de simular determinados servicios en un sistema distribuido para desarrollo y pruebas

[Más información sobre Azure Dev Spaces](/azure/dev-spaces/about).

### <a name="azure-virtual-machines"></a>Azure Virtual Machines

Si tiene una aplicación existente que requeriría modificaciones importantes para ejecutarse en App Service, podría elegir Virtual Machines con el fin de simplificar la migración a la nube. Aunque la configuración, la protección y el mantenimiento correctos de las máquinas virtuales requiere mucho más tiempo y experiencia en TI en comparación con Azure App Service. Si está pensando en Azure Virtual Machines, asegúrese de tener en cuenta el esfuerzo de mantenimiento continuado necesario para aplicar revisiones, actualizar y administrar el entorno de máquinas virtuales. Azure Virtual Machines es una infraestructura como servicio (IaaS), mientras que App Service es PaaS. También debe considerar si la implementación de la aplicación como un contenedor de Windows en Web App for Containers podría ser una opción viable para su escenario.

## <a name="logical-processes"></a>Procesos lógicos

Los procesos lógicos individuales que se pueden desacoplar del resto de la aplicación se pueden implementar por separado en Azure Functions de forma "sin servidor". Azure Functions permite escribir simplemente el código que se necesita para un problema determinado, sin preocuparse por la aplicación o infraestructura para ejecutarlo. Se puede elegir entre una variedad de lenguajes de programación, incluyendo C\#, F\#, Node.js, Python y PHP, lo que permite elegir el lenguaje más productivo para la tarea en cuestión. Al igual que la mayoría de las soluciones basadas en la nube, solo se paga por la cantidad de tiempo que se usa y se puede confiar en Azure Functions para escalar verticalmente según sea necesario.

## <a name="data"></a>data

Azure ofrece una amplia variedad de opciones de almacenamiento de datos, por lo que la aplicación puede usar el proveedor de datos adecuado para los datos en cuestión.

Para los datos transaccionales y relacionales, Azure SQL Database es la mejor opción. Para los datos de alto rendimiento y principalmente de solo lectura, una caché en Redis respaldada por Azure SQL Database es una buena solución.

Los datos JSON no estructurados se pueden almacenar de diferentes formas, desde columnas de SQL Database a blobs o tablas de Azure Storage, a Azure Cosmos DB. De todos estos, Azure Cosmos DB ofrece la mejor funcionalidad de consulta y es la opción recomendada para un gran número de documentos basados en JSON que deben admitir las consultas.

Los datos transitorios basados en eventos o comandos que se usan para coordinar el comportamiento de la aplicación pueden usar Azure Service Bus o Azure Storage Queue. Azure Storage Bus ofrece más flexibilidad y es el servicio recomendado para mensajería no trivial dentro y entre las aplicaciones.

## <a name="architecture-recommendations"></a>Recomendaciones de arquitectura

Los requisitos de la aplicación deben dictar su arquitectura. Hay muchos servicios de Azure diferentes disponibles. Elegir el adecuado es una decisión importante. Microsoft ofrece una galería de arquitecturas de referencia para ayudar a identificar arquitecturas típicas optimizadas para escenarios comunes. Es posible que encuentre una arquitectura de referencia estrechamente relacionada con los requisitos de la aplicación o, que al menos, ofrezca un punto de partida.

En la figura 11-1 se muestra una arquitectura de referencia de ejemplo. En este diagrama se describe un enfoque de arquitectura recomendada para un sitio web del sistema de administración de contenido de Sitecore optimizado para marketing.

![Figura 11-1](./media/image11-2.png)

**Figura 11-1.** Arquitectura de referencia del sitio web de marketing Sitecore.

**Referencias: recomendaciones de hospedaje de Azure**

- Arquitecturas de soluciones de Azure\
  <https://azure.microsoft.com/solutions/architecture/>

- Arquitectura de aplicación web básica de Azure\
  <https://docs.microsoft.com/azure/architecture/reference-architectures/app-service-web-app/basic-web-app>

- Patrones de diseño para microservicios\
  <https://docs.microsoft.com/azure/architecture/microservices/design/patterns>

- Guía para desarrolladores de Microsoft Azure\
  <https://azure.microsoft.com/campaigns/developer-guide/>

- Información general de Web Apps\
  <https://docs.microsoft.com/azure/app-service/app-service-web-overview>

- Web App for Containers\
  <https://azure.microsoft.com/services/app-service/containers/>

- Introducción a Azure Kubernetes Service (AKS)\
  <https://docs.microsoft.com/azure/aks/intro-kubernetes>

>[!div class="step-by-step"]
>[Anterior](development-process-for-azure.md)
