---
title: 452 - MessageLogWarning
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22a9f6ea-5b5f-4110-8a4e-9be9c983fbbb
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4bc2b5a77a32e2209ef9ce0621d898486da3bc3e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="452---messagelogwarning"></a>452 - MessageLogWarning
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|452|  
|Palabras clave|Solución de problemas, WCFMessageLogging|  
|Nivel|Advertencia|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  
 Este evento se genera cuando se envía la advertencia del registro de mensajes.  
  
## <a name="message"></a>Mensaje  
 %1  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|data1|`xs:string`||  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
