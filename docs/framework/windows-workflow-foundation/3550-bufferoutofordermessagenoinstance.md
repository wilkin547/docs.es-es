---
description: 'Más información acerca de: 3550-BufferOutOfOrderMessageNoInstance'
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.date: 03/30/2017
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
ms.openlocfilehash: cb51f9fa32de1b56560f9593dae2ec82c100dc65
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631455"
---
# <a name="3550---bufferoutofordermessagenoinstance"></a>3550 - BufferOutOfOrderMessageNoInstance

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|3550|  
|Palabras clave|WFServices|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  

 Indica que se ha producido un error en la recepción almacenada en el búfer. La operación se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.  
  
## <a name="message"></a>Message  

 La operación '%1' no se puede realizar en este momento. Se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|OperationName|xs:string|Nombre de la operación.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
