---
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 94c7ce231df241778f7c6ec5fe5998eae364750d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755576"
---
# <a name="3508---trackingprofilenotfound"></a>3508 - TrackingProfileNotFound
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|3508|  
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
