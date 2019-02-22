---
title: Flujo de trabajo de DevOps para aplicaciones de Docker con herramientas de Microsoft
description: En contenedores ciclo de vida de aplicaciones de Docker con el flujo de trabajo de Microsoft Platform y herramientas de DevOps con herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
---

# <a name="docker-application-devops-workflow-with-microsoft-tools"></a>Flujo de trabajo de DevOps para aplicaciones de Docker con herramientas de Microsoft

*Microsoft Visual Studio, servicios de Azure DevOps, Team Foundation Server y Application Insights proporcionan un ecosistema completo para el desarrollo y operaciones de TI que proporcione a su equipo las herramientas para administrar proyectos y compilar, probar e implementar rápidamente aplicaciones en contenedores.*

Con Visual Studio y servicios de Azure DevOps en la nube, junto con Team Foundation Server local, los equipos de desarrollo productiva pueden compilar, probar y publicar aplicaciones en contenedor que tienen como destino Windows o Linux.

Herramientas de Microsoft pueden automatizar la canalización para implementaciones específicas de aplicaciones en contenedores, Docker, .NET Core o cualquier combinación con otras plataformas, desde compilaciones globales y la integración continua (CI) y pruebas con Azure DevOps Services o Team Foundation Server, para implementación continua (CD) para entornos de Docker (desarrollo, ensayo, producción) y para transmitir información de análisis sobre los servicios al equipo de desarrollo a través de Application Insights. Cada confirmación de código puede iniciar una compilación (CI) e implementar automáticamente los servicios en entornos en contenedores específicos (CD).

Los desarrolladores y evaluadores pueden aprovisionar con facilidad y rapidez entornos de prueba y desarrollo tipo producción basados en Docker con el uso de plantillas de Microsoft Azure.

La complejidad del desarrollo de aplicaciones en contenedores aumenta de forma constante según las necesidades empresariales de complejidad y escalabilidad. Un buen ejemplo de esta complejidad son las aplicaciones basadas en arquitecturas de microservicios. Para tener éxito en un entorno, el proyecto debe automatizar todo el ciclo de vida, no solo la compilación y desarrollo, sino que también debe administrar versiones junto con la recopilación de telemetría. Servicios de DevOps de Azure y Azure ofrecen las siguientes funcionalidades:

- Azure administración de código fuente DevOps Services/Team Foundation Server (basada en Git o Team Foundation Version Control), planeación de Agile (Agile, Scrum y CMMI son compatibles), integración continua, administración de versiones y otras herramientas para los equipos ágiles.

- Azure DevOps Services y Team Foundation Server incluyen un eficaz y creciente ecosistema de extensiones de primera y de otros fabricantes que fácilmente puede construir un elemento de configuración, compilación, prueba, entrega y liberar la canalización de administración de microservicios.

- Ejecutar pruebas automatizadas como parte de la canalización integrada en servicios de Azure DevOps.

- Servicios de Azure DevOps puede reforzar el ciclo de vida de DevOps con entrega en varios entornos, no solo para entornos de producción, sino también para las pruebas, incluidos A / experimentación B, [lanzamientos](https://martinfowler.com/bliki/CanaryRelease.html), y así sucesivamente.

- Las organizaciones pueden aprovisionar fácilmente contenedores de Docker desde imágenes privadas almacenadas en Azure Container Registry junto con cualquier dependencia de componentes de Azure (Data, PaaS, etc.) mediante plantillas de Azure Resource Manager con las herramientas que ya están familiarizados con.

>[!div class="step-by-step"]
>[Anterior](../design-develop-containerized-apps/build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
>[Siguiente](docker-application-outer-loop-devops-workflow.md)
