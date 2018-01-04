---
title: 3508 - TrackingProfileNotFound
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 34812b6ddefb69c053cfefa91d7227a7bf15f42e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="3508---trackingprofilenotfound"></a>3508 - TrackingProfileNotFound
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|3508|  
|Palabras clave|WFServices|  
|Nivel|Detallado|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  
 Indica que no se encontró un TrackingProfile en el archivo de configuración o que ActivityDefinitionId no coincide con el perfil.  
  
## <a name="message"></a>Mensaje  
 No se encontró TrackingProfile '%1' para ActivityDefinitionId '%2'. No se encontró TrackingProfile en el archivo de configuración o no coincide el ActivityDefinitionId.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|TrackingProfile|xs:string|El nombre del perfil de seguimiento.|  
|ActivityDefinitionId|xs:string|Identificador de definición de actividad.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
