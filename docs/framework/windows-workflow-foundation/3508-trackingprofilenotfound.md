---
description: 'Más información acerca de: 3508-TrackingProfileNotFound'
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 3e97af1689a868fb103b06413a0c4f28b0c1f652
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778014"
---
# <a name="3508---trackingprofilenotfound"></a>3508 - TrackingProfileNotFound

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|3508|  
|Palabras clave|WFServices|  
|Nivel|Verbose|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  

 Indica que no se encontró un TrackingProfile en el archivo de configuración o que ActivityDefinitionId no coincide con el perfil.  
  
## <a name="message"></a>Message  

 No se encontró TrackingProfile '%1' para ActivityDefinitionId '%2'. No se encontró TrackingProfile en el archivo de configuración o no coincide el ActivityDefinitionId.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|TrackingProfile|xs:string|El nombre del perfil de seguimiento.|  
|ActivityDefinitionId|xs:string|Identificador de definición de actividad.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
