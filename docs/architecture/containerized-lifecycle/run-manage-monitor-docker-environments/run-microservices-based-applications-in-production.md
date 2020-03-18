---
title: Ejecución de aplicaciones basadas en microservicios y compuestas en entornos de producción
description: Conozca los componentes clave para ejecutar aplicaciones basadas en contenedores en producción
ms.date: 02/15/2019
ms.openlocfilehash: 69df3d39a00b91cbe59c96e5fcab841a60943bcc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "68672922"
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a>Ejecución de aplicaciones basadas en microservicios y compuestas en entornos de producción

Las aplicaciones compuestas por varios microservicios deben implementarse en clústeres de orquestador con el fin de simplificar la complejidad de la implementación y hacer que sea viable desde el punto de vista de la TI. Sin un clúster de orchestrator, sería difícil de implementar y escalar horizontalmente una aplicación de microservicios compleja.

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a>Introducción a orquestadores, programadores y clústeres de contenedores

Anteriormente en este libro electrónico, se presentaron los *clústeres* y *programadores* como parte de la discusión sobre arquitectura y desarrollo de software. Kubernetes y Service Fabric son ejemplos de clústeres de Docker. Estos dos orquestadores pueden ejecutarse como parte de la infraestructura proporcionada por Microsoft Azure Kubernetes Service.

Cuando las aplicaciones se escalan horizontalmente en varios sistemas de host, la posibilidad de administrar cada sistema host y abstraer la complejidad de la plataforma subyacente se vuelve atractiva. Eso es precisamente lo que ofrecen los orquestadores y programadores. Vamos a echarles un vistazo aquí:

- **Programadores**. El término "programación" hace referencia a la posibilidad de que un administrador cargue un archivo de servicio en un sistema host que establezca cómo ejecutar un contenedor específico. El inicio de contenedores en un clúster de Docker suele conocerse como programación. Aunque la programación se refiere al acto específico de cargar la definición de servicio, en un sentido más general, los programadores son responsables de conectarse al sistema de inicio de un host para administrar los servicios en la medida en que sea necesario.

   Un programador de clústeres tiene varios objetivos: usar de forma eficaz los recursos del clúster, trabajar con restricciones de selección de ubicación proporcionadas por el usuario, programar aplicaciones rápidamente para no dejarlas en un estado pendiente, tener un grado de "imparcialidad", ser sistemáticos ante los errores y estar siempre disponible.

- **Orquestadores**. Las plataformas amplían las funcionalidades de administración del ciclo de vida a cargas de trabajo complejas y de varios contenedores, implementadas en un clúster de hosts. Mediante la abstracción de la infraestructura del host, las herramientas de orquestación ofrecen a los usuarios una forma de tratar todo el clúster como un único destino de implementación.

   El proceso de orquestación implica herramientas y una plataforma que pueda automatizar todos los aspectos de la administración de aplicaciones desde la selección de ubicación o implementación iniciales por contenedor; el traslado de contenedores a diferentes hosts según el mantenimiento o rendimiento del host; el control de versiones y actualizaciones graduales, y funciones de supervisión del mantenimiento que admitan escalabilidad y conmutación por error, y mucho más.

   Orquestación es un término amplio que hace referencia a la programación de contenedores, la administración del clúster y, posiblemente, el aprovisionamiento de hosts adicionales.

Las funcionalidades proporcionadas por los orquestadores y los programadores son difíciles de desarrollar y crear desde cero, por lo tanto, normalmente preferirá usar soluciones de orquestación ofrecidas por proveedores.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](manage-production-docker-environments.md)
