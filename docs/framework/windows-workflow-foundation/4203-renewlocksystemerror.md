---
description: 'Más información acerca de: 4203-RenewLockSystemError'
title: 4203 - RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 0e62c501391fcaec56f2016631707832170775ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792783"
---
# <a name="4203---renewlocksystemerror"></a>4203 - RenewLockSystemError

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|4203|  
|Palabras clave|WFInstanceStore|  
|Nivel|Error|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que el proveedor de SQL no ha ampliado la expiración de bloqueo, debido a que la expiración de bloqueo ya se superó o el propietario de bloqueo se eliminó. SqlWorkflowInstanceStore se anulará.  
  
## <a name="message"></a>Message  

 Error al extender la expiración de bloqueo, la expiración de bloqueo ya se superó o el propietario de bloqueo se eliminó. Anulando SqlWorkflowInstanceStore.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
