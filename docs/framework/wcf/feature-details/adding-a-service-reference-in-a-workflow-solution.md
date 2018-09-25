---
title: Agregar una referencia de servicio en una solución de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
ms.openlocfilehash: 9dcbf779d948f6d295c2a23f5a09efc5ac989cdd
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2018
ms.locfileid: "47027669"
---
# <a name="adding-a-service-reference-in-a-workflow-solution"></a>Agregar una referencia de servicio en una solución de flujo de trabajo

Si se agrega una referencia de servicio en una aplicación de flujo de trabajo, el resultado es ligeramente distinto que una aplicación WCF normal. Al seleccionar **Agregar > referencia de servicio** y especifique la dirección URL del servicio, se descargan los metadatos y se generan las actividades personalizadas que le llame al servicio WCF o servicio de flujo de trabajo WCF agregó una referencia a. Después de agregar una referencia de servicio, recompile la solución para que se compilen las actividades generadas. Aparecerán en el cuadro de herramientas del diseñador de flujo de trabajo. Tenga en cuenta, no obstante, que esto solo funcionará si agrega una referencia de servicio en una solución de flujo de trabajo. La difusión por web siguiente muestra cómo agregar una referencia de servicio en otros tipos de proyectos: [llamar a un servicio WCF desde un flujo de trabajo en un proyecto Web](https://go.microsoft.com/fwlink/?LinkId=207725).

Si agrega dos o más referencias de servicio a servicios que contengan el mismo nombre de operación, se producirá un problema. Las actividades generadas llamarán solo a la primera operación de servicio. Para solucionar este problema cambie el nombre de las operaciones de servicio para que sean distintas o cambie el nombre de la configuración de punto de conexión de cada actividad generada.

## <a name="see-also"></a>Vea también

- [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Creación de un servicio de flujo de trabajo que llame a otro servicio de flujo de trabajo](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-that-calls-another-workflow-service.md)
- [Llamar a un servicio WCF desde un flujo de trabajo en un proyecto Web](https://go.microsoft.com/fwlink/?LinkId=207725)
