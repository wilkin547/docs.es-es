---
title: "Agregar una referencia de servicio en una solución de flujo de trabajo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee974ee5a9f4564b0e44256bc4773f9898d89fc6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="adding-a-service-reference-in-a-workflow-solution"></a>Agregar una referencia de servicio en una solución de flujo de trabajo
Si se agrega una referencia de servicio en una aplicación de flujo de trabajo, el resultado es ligeramente distinto que una aplicación WCF normal. Cuando seleccione Agregar referencia de servicio y especifique la dirección URL en el servicio, se descargan los metadatos y se generan las actividades personalizadas que le permiten llamar al servicio WCF o al servicio de flujo de trabajo WCF al que agregó una referencia. Después de agregar una referencia de servicio, recompile la solución para que se compilen las actividades generadas. Aparecerán en el cuadro de herramientas del diseñador de flujo de trabajo. Tenga en cuenta, no obstante, que esto solo funcionará si agrega una referencia de servicio en una solución de flujo de trabajo. La difusión por web siguiente muestra cómo agregar una referencia de servicio en otros tipos de proyectos: [llamar a un servicio WCF desde un flujo de trabajo en un proyecto Web](http://go.microsoft.com/fwlink/?LinkId=207725).  
  
 Si agrega dos o más referencias de servicio a servicios que contengan el mismo nombre de operación, se producirá un problema. Las actividades generadas llamarán solo a la primera operación de servicio. Para solucionar este problema cambie el nombre de las operaciones de servicio para que sean distintas o cambie el nombre de la configuración de punto de conexión de cada actividad generada.  
  
## <a name="see-also"></a>Vea también  
 [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [Creación de un servicio de flujo de trabajo que llame a otro servicio de flujo de trabajo](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-that-calls-another-workflow-service.md)  
 [Llamar a un servicio WCF desde un flujo de trabajo en un proyecto Web](http://go.microsoft.com/fwlink/?LinkId=207725)
