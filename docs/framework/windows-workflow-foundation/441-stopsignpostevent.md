---
title: 441- StopSignpostEvent1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc9850a5-0dc3-4b84-a09a-744301c7c18e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bc1ae0450513e1abbb832a53bc72f82ccd999580
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="441--stopsignpostevent1"></a>441- StopSignpostEvent1
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|441|  
|Palabras clave|Solución de problemas|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  
 En el seguimiento de la actividad, indica que un mensaje ha terminado de cruzar el límite de la actividad para enviar o recibir.  
  
## <a name="message"></a>Mensaje  
 Límite de la actividad.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Extended Data|`xs:string`|El nombre de la actividad.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
