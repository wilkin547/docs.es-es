---
description: Más información acerca de cómo agregar una referencia de servicio en una solución de flujo de trabajo
title: Agregar una referencia de servicio en una solución de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
ms.openlocfilehash: ff54235ce2925bd2596bae68333ce98dc7a2f009
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705322"
---
# <a name="add-a-service-reference-in-a-workflow-solution"></a>Agregar una referencia de servicio en una solución de flujo de trabajo

Si se agrega una referencia de servicio en una aplicación de flujo de trabajo, el resultado es ligeramente distinto que una aplicación WCF normal. Al seleccionar **Agregar**  >  **referencia de servicio** y especificar la dirección URL del servicio, los metadatos se descargan y se generan actividades personalizadas que le permiten llamar a ese servicio WCF o servicio de flujo de trabajo WCF. Después de agregar una referencia de servicio, recompile la solución para que se compilen las actividades generadas. Aparecerán en el cuadro de herramientas del diseñador de flujo de trabajo. Esto solo funcionará si va a agregar una referencia de servicio dentro de una solución de flujo de trabajo. En la difusión Web siguiente se muestra cómo agregar una referencia de servicio en otros tipos de proyectos: [llamar a un servicio WCF desde un flujo de trabajo en un proyecto web](/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow).

Si agrega dos o más referencias de servicio a servicios que contengan el mismo nombre de operación, se producirá un problema. Las actividades generadas llamarán solo a la primera operación de servicio. Para solucionar este problema, cambie el nombre de las operaciones de servicio para que sean distintas o cambie el nombre de la configuración de extremo dentro de cada actividad generada.

## <a name="see-also"></a>Vea también

- [Servicios de flujo de trabajo](workflow-services.md)
- [Llamar a un servicio WCF desde un flujo de trabajo de un proyecto web](/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow)
