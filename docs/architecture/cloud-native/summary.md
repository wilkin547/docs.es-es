---
title: Resumen
description: Un resumen de las conclusiones principales del libro electrónico guía de arquitectura de aplicaciones .NET nativas en la nube para Azure.
ms.date: 04/29/2020
ms.openlocfilehash: 97f20771aae73ed88d2dadefa7ba89d64eb62fcd
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82899711"
---
# <a name="summary"></a>Resumen

En Resumen, estas son algunas conclusiones importantes de esta guía:

- **Cloud-Native es el** diseño de aplicaciones modernas que adoptan un cambio rápido, gran escala y resistencia, en entornos modernos y dinámicos como nubes públicas, privadas y híbridas.

- ** [Cloud Native Computing Foundation](https://www.cncf.io/) (CNCF)** es un consorcio de código abierto influyente de más de 300 grandes corporaciones. Es responsable de impulsar la adopción de la informática nativa en la nube a través de pilas de tecnología y en la nube.

- Las **instrucciones de CNCF** recomiendan que las aplicaciones nativas de la nube adopten seis pilares importantes, como se muestra en la figura 12-1:

  ![Pilares básicos de la nube nativos](./media/cloud-native-foundational-pillars.png)

  **Figura 12-1**. Pilares básicos de la nube nativos

- Estos pilares nativos de la nube incluyen:
  - La nube y su modelo de servicio subyacente
  - Principios de diseño modernos
  - Microservicios
  - Contenedores y orquestación de contenedores
  - Servicios de respaldo basados en la nube, como bases de datos y agentes de mensajes
  - Automatización, incluida la infraestructura como código y la implementación de código

- **Kubernetes** es el entorno de hospedaje que se elige para la mayoría de las aplicaciones nativas de la nube. Los servicios simples más pequeños se hospedan a veces en plataformas sin servidor, como Azure Functions. Entre muchas características clave de automatización, ambos entornos proporcionan escalado automático para controlar los volúmenes de carga de trabajo fluctuantes.

- La **comunicación del servicio** se convierte en una decisión de diseño importante al construir una aplicación nativa en la nube. Normalmente, las aplicaciones exponen una puerta de enlace de API para administrar la comunicación de cliente front-end. A continuación, los microservicios de back-end esfuerzan a comunicarse entre sí que implementan patrones de comunicación asincrónica, siempre que sea posible.

- **gRPC** es un marco de trabajo moderno y de alto rendimiento que evoluciona el protocolo de llamada a procedimiento remoto (RPC) de edad antiguo. Las aplicaciones nativas de la nube a menudo adoptan gRPC para simplificar la mensajería entre los servicios back-end. gRPC usa HTTP/2 para su Protocolo de transporte. Puede ser hasta 8X más rápido que la serialización de JSON con tamaños de mensaje 60-80% más pequeños. gRPC es de código abierto y está administrado por Cloud Native Computing Foundation (CNCF).

- Los **datos distribuidos** son un modelo a menudo implementado por aplicaciones nativas de la nube. Las aplicaciones segregan la funcionalidad empresarial en microservicios pequeños e independientes. Cada microservicio encapsula sus propias dependencias, datos y estado. El modelo de base de datos compartido clásico evoluciona en una de muchas bases de datos más pequeñas, cada una de las cuales se alinea con un microservicio. Cuando el humo se borra, surge un diseño que expone un `database-per-microservice` modelo.

- **Las bases de datos no-SQL** hacen referencia a almacenes de datos no relacionales de alto rendimiento. Excel en sus características de facilidad de uso, escalabilidad, resistencia y disponibilidad. Los servicios de gran volumen que requieren un tiempo de respuesta de subsegundo favorecen los almacenes de los mismos. La proliferación de tecnologías NoSQL para sistemas nativos en la nube distribuida no puede ser inestable.

- **NewSQL** es una tecnología de base de datos emergente que combina la escalabilidad distribuida de NoSQL y las garantías acid de una base de datos relacional. Las bases de datos de NewSQL se dirigen a sistemas empresariales que deben procesar grandes volúmenes de datos, en entornos distribuidos, con compatibilidad total con la transacción o el ácido. Cloud Native Computing Foundation (CNCF) incluye varios proyectos de base de datos NewSQL.

- La **resistencia** es la capacidad del sistema de reaccionar ante errores y seguir siendo funcional. Los sistemas nativos en la nube adoptan una arquitectura distribuida en la que el error es inevitable. Las aplicaciones deben construirse para responder a los errores de forma elegante y volver rápidamente a un estado totalmente funcional.

- Las **mallas de servicio** son una capa de infraestructura configurable con capacidades integradas para controlar la comunicación del servicio y otros desafíos transversales. Desacoplan responsabilidades transversales del código de negocio. Estas responsabilidades se trasladan a un proxy de servicio. Al que se hace `Sidecar pattern`referencia como, el proxy se implementa en un proceso independiente para proporcionar aislamiento del código de negocio.

- La **observación** es una consideración de diseño clave para las aplicaciones nativas en la nube. A medida que los servicios se distribuyen a través de un clúster de nodos, el registro, la supervisión y las alertas centralizados, se convierten en obligatorios. Azure Monitor es una colección de herramientas basadas en la nube diseñadas para proporcionar visibilidad sobre el estado del sistema.

- La **infraestructura como código** es una práctica ampliamente aceptada que automatiza el aprovisionamiento de plataforma. La infraestructura y las implementaciones son automatizadas, coherentes y repetibles. Herramientas como Azure Resource Manager, terraform y el CLI de Azure le permiten crear un script de la infraestructura de la nube que necesita mediante declaración.

- La **automatización de código** es un requisito para las aplicaciones nativas de la nube. Los sistemas de CI/CD modernos ayudan a completar este principio. Proporcionan pasos de compilación e implementación independientes que ayudan a garantizar un código coherente y de calidad. La fase de compilación transforma el código en un artefacto binario. La fase de versión recoge el artefacto binario, aplica la configuración del entorno externo y lo implementa en un entorno especificado. Azure DevOps y GitHub son entornos de DevOps con todas las características.

>[!div class="step-by-step"]
>[Anterior](application-bundles.md)
