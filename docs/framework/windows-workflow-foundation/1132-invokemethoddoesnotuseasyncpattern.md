---
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 321d8c6185c8d24b7a3b6e255e235c36c119ff21
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a>1132 - InvokeMethodDoesNotUseAsyncPattern
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1132|  
|Palabras clave|WFRuntime|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  
 Durante el paso CacheMetadata, la actividad InvokeMethod indica que no está usando el patrón asincrónico al invocar el método.  
  
## <a name="message"></a>Mensaje  
 InvokeMethod '%1': el método no usa un patrón asincrónico.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|xs:string|Identificación y nombre para mostrar de la actividad InvokeMethod.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
