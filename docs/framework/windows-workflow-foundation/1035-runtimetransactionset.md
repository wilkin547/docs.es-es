---
description: 'Más información acerca de: 1035-RuntimeTransactionSet'
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: 513ba49962a8f02ab47b8e5b762949cd09154a3c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667907"
---
# <a name="1035---runtimetransactionset"></a>1035 - RuntimeTransactionSet

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1035|  
|Palabras clave|WFRuntime|  
|Nivel|Verbose|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que una actividad ha establecido la transacción en tiempo ejecución.  
  
## <a name="message"></a>Message  

 La actividad ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 ' estableció la transacción en tiempo de ejecución.  Ejecución aislada de la actividad ' %4 ', DisplayName: ' %5 ', InstanceId: ' %6 '.  
  
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
