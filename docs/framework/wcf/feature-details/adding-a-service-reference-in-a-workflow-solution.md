---
title: Agregar una referencia de servicio en una solución de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
ms.openlocfilehash: 641d401fb85ea156f35134f54e54840f20fa4c9d
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116703"
---
# <a name="add-a-service-reference-in-a-workflow-solution"></a>Agregar una referencia de servicio en una solución de flujo de trabajo

Si se agrega una referencia de servicio en una aplicación de flujo de trabajo, el resultado es ligeramente distinto que una aplicación WCF normal. Al seleccionar **agregar** > **referencia de servicio** y especificar la dirección URL del servicio, se descargan los metadatos y se generan actividades personalizadas que le permiten llamar a ese servicio WCF o servicio de flujo de trabajo WCF. Después de agregar una referencia de servicio, recompile la solución para que se compilen las actividades generadas. Aparecerán en el cuadro de herramientas del diseñador de flujo de trabajo. Esto solo funcionará si va a agregar una referencia de servicio dentro de una solución de flujo de trabajo. En la difusión Web siguiente se muestra cómo agregar una referencia de servicio en otros tipos de proyectos: [llamar a un servicio WCF desde un flujo de trabajo en un proyecto web](https://docs.microsoft.com/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow).

Si agrega dos o más referencias de servicio a servicios que contengan el mismo nombre de operación, se producirá un problema. Las actividades generadas llamarán solo a la primera operación de servicio. Para solucionar este problema, cambie el nombre de las operaciones de servicio para que sean distintas o cambie el nombre de la configuración de extremo dentro de cada actividad generada.

## <a name="see-also"></a>Vea también

- [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Llamar a un servicio WCF desde un flujo de trabajo en un proyecto web](https://docs.microsoft.com/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow)
