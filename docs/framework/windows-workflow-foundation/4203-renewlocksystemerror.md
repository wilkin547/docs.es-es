---
title: 4203 - RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 984f7ddae8797cba17753a618d0820d21bde5eef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774353"
---
# <a name="4203---renewlocksystemerror"></a>4203 - RenewLockSystemError
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|ID|4203|  
|Palabras clave|WFInstanceStore|  
|Nivel|Error|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  
 Indica que el proveedor de SQL no ha ampliado la expiración de bloqueo, debido a que la expiración de bloqueo ya se superó o el propietario de bloqueo se eliminó. SqlWorkflowInstanceStore se anulará.  
  
## <a name="message"></a>Mensaje  
 Error al extender la expiración de bloqueo, la expiración de bloqueo ya se superó o el propietario de bloqueo se eliminó. Anulando SqlWorkflowInstanceStore.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
