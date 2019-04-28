---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: 198e11dd94b0ad5cdc1e01c3611280754ca081d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924857"
---
# <a name="1035---runtimetransactionset"></a>1035 - RuntimeTransactionSet
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|1035|  
|Palabras clave|WFRuntime|  
|Nivel|Detallado|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  
 Indica que una actividad ha establecido la transacción en tiempo ejecución.  
  
## <a name="message"></a>Mensaje  
 Se ha establecido la transacción en tiempo de ejecución mediante la actividad '%1', DisplayName: '%2', InstanceId: '%3'.  Ejecución aislada para la actividad '%4', DisplayName: '%5', InstanceId: '%6'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Actividad|xs:string|El nombre de tipo de la actividad.|  
|DisplayName|xs:string|El nombre para mostrar de la actividad.|  
|InstanceId|xs:string|La identificación de instancia de la actividad.|  
|IsolatedActivity|xs:string|El nombre de tipo para mostrar de la actividad en la que la transacción está aislada.|  
|IsolatedActivityDisplayName|xs:string|El nombre para mostrar de la actividad en la que la transacción está aislada.|  
|IsolatedActivityInstanceId|xs:string|El identificador de la instancia de la actividad en la que la transacción está aislada.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
