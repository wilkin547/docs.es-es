---
title: 440 - StartSignpostEvent1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27b551b5-ae76-49f8-bab8-6300009eb4c1
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5e1674dc7d242a89498360c3e285fa77a08a9004
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="440---startsignpostevent1"></a>440 - StartSignpostEvent1
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|440|  
|Palabras clave|Solución de problemas|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  
 En el seguimiento de la actividad, indica que un mensaje ha empezado a cruzar el límite de la actividad para enviar o recibir.  
  
## <a name="message"></a>Mensaje  
 Límite de la actividad.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|ExtendedData|`xs:string`|El nombre de la actividad.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
