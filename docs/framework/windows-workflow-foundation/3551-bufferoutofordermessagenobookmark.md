---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6dc505a4e0e79b37f9adff41b80dcba55215576f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="3551---bufferoutofordermessagenobookmark"></a>3551 - BufferOutOfOrderMessageNoBookmark
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|3551|  
|Palabras clave|WFServices|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  
 Indica que se ha producido un error en la reanudación de marcador. La operación de recepción almacenada en búfer se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.  
  
## <a name="message"></a>Mensaje  
 La operación '%2' en la instancia del servicio '%1' no se puede realizar en este momento. Se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|OperationName|xs:string|Nombre de la operación.|  
|ServiceInstanceId|xs:string|Identificador de la instancia del servicio.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
