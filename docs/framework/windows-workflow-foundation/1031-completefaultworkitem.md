---
title: 1031 - CompleteFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5173e61b2479d02dc35c5fcf9ae55634cc8dc7ba
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1031---completefaultworkitem"></a>1031 - CompleteFaultWorkItem
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1031|  
|Palabras clave|WFRuntime|  
|Nivel|Detallado|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  
 Indica que se ha completado un FaultWorkItem.  
  
## <a name="message"></a>Mensaje  
 Un FaultWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'. La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|FaultActivity|xs:string|Nombre de tipo de la actividad que generó el error.|  
|FaultActivityDisplayName|xs:string|Nombre para mostrar de la actividad que generó el error.|  
|FaultActivityInstanceId|xs:string|Identificador de la actividad que generó el error.|  
|ExceptionActivity|xs:string|El nombre de tipo para mostrar de la actividad que produjo la excepción.|  
|ExceptionActivityDisplayName|xs:string|El nombre para mostrar de la actividad que produjo la excepción.|  
|ExceptionActivityInstanceId|xs:string|Identificador de instancia de la actividad que generó la excepción.|  
|Excepción|xs:string|Detalles de la excepción para la excepción|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
