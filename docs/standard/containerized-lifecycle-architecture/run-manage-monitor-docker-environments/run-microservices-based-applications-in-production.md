---
title: "Ejecutar aplicaciones basadas en microservicios y compuestas en entornos de producción"
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0d7611d07c9995984269e3f7b071154d9b861367
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a>Ejecutar aplicaciones basadas en microservicios y compuestas en entornos de producción

Aplicaciones compuestas por varios microservicios deben implementarse en clústeres de orchestrator con el fin de simplificar la complejidad de implementación y que sea viable desde un punto de vista de TI. Sin un clúster de orchestrator, sería muy difícil de implementar y escalado horizontal de una aplicación compleja microservicios.

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a>Introducción a orchestrators, programadores y clústeres de contenedor

Anteriormente en este libro electrónico, introdujimos *clústeres* y *programadores* como parte de la explicación de la arquitectura de software y de desarrollo. Ejemplos de clústeres de Docker son Docker Swarm y sistema operativo de centro de datos Mesosphere (controlador de dominio/OS). Ambos pueden ejecutar como parte de la infraestructura proporcionada por el servicio de contenedor de Microsoft Azure.

Cuando las aplicaciones se escalado horizontal entre varios sistemas de host, la capacidad de administrar cada sistema host y condensan y eliminan la complejidad de la plataforma subyacente pasa a ser atractiva. Eso es precisamente lo que proporcionan orchestrators y programadores. ¡Eche un vistazo a ellos aquí:

-   **Los programadores*** *"Programación" hace referencia a la capacidad de un administrador que se va a cargar un archivo de servicio en un sistema host que establece cómo ejecutar un contenedor específico. Iniciar contenedores en un clúster de Docker suele conocerse como la programación. Aunque la programación se refiere a la acción específica de la carga de la definición de servicio, en un sentido más general, los programadores son responsables de enlazar con el sistema de inicialización de un host para administrar servicios en la capacidad necesaria.

Un programador de clúster tiene varios objetivos: usar de forma eficaz los recursos del clúster, trabajar con restricciones de selección de ubicación proporcionada por el usuario, la programación de aplicaciones rápidamente en no o dejarlos en un estado pendiente, tener un grado de "equidad", que se va a sólida a errores, y estar siempre disponible.

-   **Orquestación*** *plataformas amplían las capacidades de administración de ciclo de vida para cargas de trabajo complejos y multicontainer implementadas en un clúster de hosts. Mediante la abstracción de la infraestructura del host, herramientas de orquestación proporcionar a los usuarios una manera de tratar todo el clúster como un destino de implementación único.

El proceso de orquestación implica una plataforma que puede automatizar todos los aspectos de la administración de aplicaciones desde la posición inicial o la implementación por contenedor; y herramientas mover contenedores a hosts diferentes dependiendo de su host estado o rendimiento; actualizaciones y las funciones que admiten la conmutación por error; y ajuste de escala de supervisión de estado de control de versiones y gradual y mucho más.

Orquestación es un término amplio que hace referencia al contenedor de programación, administración del clúster y posiblemente el aprovisionamiento de hosts adicionales.

Las capacidades proporcionadas por orchestrators y programadores son muy complejas para desarrollar y crear desde cero y, por lo tanto, normalmente se desea hacer uso de soluciones de orquestación que ofrecen los proveedores.


>[!div class="step-by-step"]
[Previous] (index.md) [Next] (manage-production-docker-environments.md)
