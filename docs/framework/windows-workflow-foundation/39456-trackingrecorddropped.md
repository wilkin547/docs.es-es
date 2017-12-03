---
title: 39456 - TrackingRecordDropped
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: da13d5bc-1736-47a4-b3fd-064ca8040326
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: de056ffcdfeb3ea5dee9eaca213fe96ee991d067
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="39456---trackingrecorddropped"></a>39456 - TrackingRecordDropped
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|39456|  
|Palabras clave|WFTracking|  
|Nivel|Advertencia|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  
 Indica que se ha quitado un registro de seguimiento porque su tamaño supera el máximo permitido por el proveedor de sesión ETW.  
  
## <a name="message"></a>Mensaje  
 El tamaño del registro de seguimiento %1 excede el máximo permitido por la sesión de ETW para el proveedor %2  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Excepción|xs:string|Detalles de la excepción para la excepción|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
