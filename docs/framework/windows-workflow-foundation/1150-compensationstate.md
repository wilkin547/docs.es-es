---
description: 'Más información acerca de: 1150-CompensationState'
title: 1150 - CompensationState
ms.date: 03/30/2017
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
ms.openlocfilehash: 4adc246cbe46dee3594bc6c0330c8e0306489219
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703346"
---
# <a name="1150---compensationstate"></a>1150 - CompensationState

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1150|  
|Palabras clave|WFActivities|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica un cambio de estado en un CompensableActivity.  
  
## <a name="message"></a>Message  

 CompensableActivity '%1' no tiene el estado '%2'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|DisplayName|xs:string|El nombre para mostrar de la actividad.|  
|Estado|xs:string|Estado de compensación.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
