---
title: Implementación de aplicaciones resistentes
description: Obtenga información sobre la resistencia, un concepto básico en una arquitectura de microservicios. Debe saber cómo administrar errores transitorios correctamente cuando se produzcan.
ms.date: 01/30/2020
ms.openlocfilehash: ccdb2470c727ad4bd89c4e0634da8564b8010e63
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77502650"
---
# <a name="implement-resilient-applications"></a>Implementación de aplicaciones resistentes

*Sus aplicaciones basadas en microservicios y en la nube deben estar preparadas para los errores parciales que seguramente se acabarán produciendo en algún momento. Debe diseñar su aplicación de modo que sea resistente a estos errores parciales.*

Resistencia es la capacidad de recuperarse de los errores y seguir funcionando. No se trata de evitar los errores, sino de aceptar el hecho de que se producirán errores y responder a ellos para evitar el tiempo de inactividad o la pérdida de datos. El objetivo de la resistencia consiste en que la aplicación vuelva a un estado totalmente operativo después de un error.

Es todo un desafío diseñar e implementar una aplicación basada en microservicios. Pero también necesita mantener la aplicación en ejecución en un entorno en el que con seguridad se producirá algún tipo de error. Por lo tanto, la aplicación debe ser resistente. Debe estar diseñada para hacer frente a errores parciales, como las interrupciones de red o el bloqueo de nodos o máquinas virtuales en la nube. Incluso los microservicios (contenedores) que se mueven a otro nodo dentro de un clúster pueden causar breves errores intermitentes dentro de la aplicación.

Los numerosos componentes individuales de la aplicación también deberían incorporar características de seguimiento de estado. Mediante las directrices descritas en este capítulo, podrá crear una aplicación que funcione sin problemas aunque se produzcan tiempos de inactividad transitorios o las interrupciones típicas de las implementaciones complejas y basadas en la nube.

>[!IMPORTANT]
> eShopOnContainer ha estado usando la [biblioteca de Polly](http://www.thepollyproject.org/) para implementar resistencia mediante [clientes con tipo](./use-httpclientfactory-to-implement-resilient-http-requests.md) hasta la versión 3.0.0.
>
> A partir de la versión 3.0.0, la resistencia de las llamadas HTTP se implementa con una [malla de Linkerd](https://linkerd.io/), que administra los reintentos de forma transparente y configurable dentro de un clúster de Kubernetes, sin tener que controlar esos problemas en el código.
>
> La biblioteca de Polly todavía se usa para agregar resistencia a las conexiones de base de datos, en especial al iniciar los servicios.

>[!WARNING]
> Todos los ejemplos de código de esta sección eran válidos antes de usar Linkerd y no se han actualizado para reflejar el código real actual. Por lo que tienen sentido en el contexto de esta sección.

>[!div class="step-by-step"]
>[Anterior](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
>[Siguiente](handle-partial-failure.md)
