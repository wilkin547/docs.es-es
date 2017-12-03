---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eabc6a6915560d8c49e695d5d681f1544689cb07
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
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
  
## <a name="message"></a>Mensaje  
 La operación '%1' no se puede realizar en este momento. Se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|OperationName|xs:string|Nombre de la operación.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
