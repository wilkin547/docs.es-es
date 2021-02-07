---
description: 'Más información acerca de: 1036-RuntimeTransactionCompletionRequested'
title: 1036 - RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: e07400902d5c3e08732385ab30e1be0d72d3e997
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667894"
---
# <a name="1036---runtimetransactioncompletionrequested"></a>1036 - RuntimeTransactionCompletionRequested

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1036|  
|Palabras clave|WFRuntime|  
|Nivel|Verbose|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que una actividad ha programado la finalización de la transacción en runtime.  
  
## <a name="message"></a>Message  

 La actividad '%1', DisplayName: '%2', InstanceId: '%3' ha programado la finalización de la transacción en runtime.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Actividad|xs:string|El nombre de tipo de la actividad.|  
|DisplayName|xs:string|El nombre para mostrar de la actividad.|  
|InstanceId|xs:string|La identificación de instancia de la actividad.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
