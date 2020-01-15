---
title: Agregar una referencia de servicio en una solución de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
ms.openlocfilehash: 7197ae991207efd60ea398794c7c23f427f6b0cc
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964214"
---
# <a name="adding-a-service-reference-in-a-workflow-solution"></a>Agregar una referencia de servicio en una solución de flujo de trabajo

Si se agrega una referencia de servicio en una aplicación de flujo de trabajo, el resultado es ligeramente distinto que una aplicación WCF normal. Al seleccionar **agregar > referencia de servicio** y especificar la dirección URL del servicio, se descargan los metadatos y se generan actividades personalizadas que le permiten llamar al servicio WCF o al servicio de flujo de trabajo WCF al que ha agregado una referencia. Después de agregar una referencia de servicio, recompile la solución para que se compilen las actividades generadas. Aparecerán en el cuadro de herramientas del diseñador de flujo de trabajo. Tenga en cuenta, no obstante, que esto solo funcionará si agrega una referencia de servicio en una solución de flujo de trabajo. En la difusión Web siguiente se muestra cómo agregar una referencia de servicio en otros tipos de proyectos: [llamar a un servicio WCF desde un flujo de trabajo en un proyecto web](https://docs.microsoft.com/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow).

Si agrega dos o más referencias de servicio a servicios que contengan el mismo nombre de operación, se producirá un problema. Las actividades generadas llamarán solo a la primera operación de servicio. Para solucionar este problema cambie el nombre de las operaciones de servicio para que sean distintas o cambie el nombre de la configuración de punto de conexión de cada actividad generada.

## <a name="see-also"></a>Vea también

- [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Llamar a un servicio WCF desde un flujo de trabajo en un proyecto web](https://docs.microsoft.com/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow)
