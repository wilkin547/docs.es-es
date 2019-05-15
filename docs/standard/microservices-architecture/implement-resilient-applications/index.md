---
title: Implementar aplicaciones resistentes
description: Obtenga información sobre la resistencia, un concepto básico en una arquitectura de microservicios. Debe saber cómo controlar errores transitorios correctamente porque se producirán.
ms.date: 10/16/2018
ms.openlocfilehash: 766349e72389f848b0a741b020707cc7acf3410d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65639858"
---
# <a name="implement-resilient-applications"></a>Implementación de aplicaciones resistentes

*Sus aplicaciones basadas en microservicios y en la nube deben estar preparadas para los errores parciales que seguramente se acabarán produciendo en algún momento. Debe diseñar su aplicación de modo que sea resistente a estos errores parciales.*

La resistencia es la capacidad de recuperarse de errores y seguir funcionando. No se trata de evitar los errores, sino de aceptar el hecho de que se producirán errores y responder a ellos para evitar el tiempo de inactividad o la pérdida de datos. El objetivo de la resistencia consiste en que la aplicación vuelva a un estado totalmente operativo después de un error.

Es todo un desafío diseñar e implementar una aplicación basada en microservicios. Pero también necesita mantener la aplicación en ejecución en un entorno en el que con seguridad se producirá algún tipo de error. Por lo tanto, la aplicación debe ser resistente. Debe estar diseñada para hacer frente a errores parciales, como las interrupciones de red o el bloqueo de nodos o máquinas virtuales en la nube. Incluso los microservicios (contenedores) que se mueven a otro nodo dentro de un clúster pueden causar breves errores intermitentes dentro de la aplicación.

Los numerosos componentes individuales de la aplicación también deberían incorporar características de seguimiento de estado. Mediante las directrices descritas en este capítulo, podrá crear una aplicación que funcione sin problemas aunque se produzcan tiempos de inactividad transitorios o las interrupciones típicas de las implementaciones complejas y basadas en la nube.

>[!div class="step-by-step"]
>[Anterior](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
>[Siguiente](handle-partial-failure.md)
