---
title: Ejecución de aplicaciones basadas en microservicios y compuestas en entornos de producción
description: Conozca los componentes clave para ejecutar aplicaciones basadas en contenedores en producción
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 52cf273194bff10192b06d236bda7c1cbea1abd8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921594"
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a>Ejecución de aplicaciones basadas en microservicios y compuestas en entornos de producción

Aplicaciones compuestas por varios microservicios deben implementarse en clústeres de orchestrator con el fin de simplificar la complejidad de implementación y hacerla viable desde un punto de vista de TI. Sin un clúster de orchestrator, sería difícil de implementar y escalar horizontalmente una aplicación de microservicios complejos.

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a>Introducción a los clústeres de contenedor, los programadores y orquestadores

Anteriormente en este libro electrónico, *clústeres* y *programadores* se incluyeron como parte de la discusión de arquitectura de software y de desarrollo. Kubernetes y Service Fabric son ejemplos de clústeres de Docker. Ambos de estos orquestadores pueden ejecutar como parte de la infraestructura proporcionada por Microsoft Azure Kubernetes Service.

Cuando las aplicaciones están escaladas horizontalmente en varios sistemas de host, la capacidad de administrar cada sistema host y abstraer la complejidad de la plataforma subyacente se convierte en atractiva. Eso es precisamente lo que proporcionan los orquestadores y los programadores. Echemos un vistazo a ellos aquí:

- **Programadores**. "Programación" hace referencia a la capacidad para que un administrador cargar un archivo de servicio en un sistema host que establece cómo ejecutar un contenedor específico. Iniciando contenedores en un clúster de Docker suele conocerse como la programación. Aunque la programación se refiere a la ley específica de la carga de la definición de servicio, en un sentido más general, los programadores son responsables de enlace en el sistema de inicio de un host para administrar servicios en cualquier capacidad necesaria.

   Un programador de clúster tiene varios objetivos: usar de forma eficaz los recursos del clúster, trabajar con restricciones de selección de ubicación proporcionada por el usuario, la programación de aplicaciones rápidamente a no dejarlos en un estado pendiente, tener un grado de "imparcialidad", que se va a sólida a errores, y siempre estarán disponibles.

- **Los orquestadores**. Plataformas amplían las capacidades de administración de ciclo de vida a cargas de trabajo complejas y de varios contenedores, implementadas en un clúster de hosts. Mediante la abstracción de la infraestructura del host, las herramientas de orquestación dar a los usuarios una manera de tratar todo el clúster como un destino de implementación único.

   El proceso de orquestación implica las herramientas y una plataforma que puede automatizar todos los aspectos de administración de aplicaciones desde la ubicación inicial o la implementación por contenedor; mover contenedores a hosts diferentes dependiendo de su host estado o rendimiento; actualizaciones y las funciones que admiten el escalado y la conmutación por error; la supervisión de estado de control de versiones y gradual y mucho más.

   Orquestación es un término amplio que hace referencia al contenedor de programación, administración del clúster y, posiblemente, el aprovisionamiento de hosts adicionales.

Las funcionalidades proporcionadas por los orquestadores y los programadores son difíciles de desarrollar y crear desde cero, por lo tanto, normalmente desearía usar ofrecidas por proveedores de soluciones de orquestación.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](manage-production-docker-environments.md)
