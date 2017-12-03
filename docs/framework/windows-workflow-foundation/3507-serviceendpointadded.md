---
title: 3507 - ServiceEndpointAdded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 68689e1694ac594467e11fabe44773b766af2b25
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="3507---serviceendpointadded"></a>3507 - ServiceEndpointAdded
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|3507|  
|Palabras clave|WFServices|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  
 Indica que se ha agregado un extremo de servicio.  
  
## <a name="message"></a>Mensaje  
 Se ha agregado un extremo de servicio a la dirección '%1', enlace '%2', y contrato '%3'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Dirección|xs:string|Dirección del extremo.|  
|Enlaces|xs:string|El enlace del extremo.|  
|Contrato|xs:string|Contrato del extremo.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
