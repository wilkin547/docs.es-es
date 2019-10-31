---
title: ICorDebugStepper::Deactivate (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Deactivate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Deactivate
helpviewer_keywords:
- Deactivate method [.NET Framework debugging]
- ICorDebugStepper::Deactivate method [.NET Framework debugging]
ms.assetid: 855f4199-b62d-40ce-998e-1eb4a1772142
topic_type:
- apiref
ms.openlocfilehash: 1d75897e00c36bd5c484e837ee68e54443168e77
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131764"
---
# <a name="icordebugstepperdeactivate-method"></a>ICorDebugStepper::Deactivate (Método)
Hace que este ICorDebugStepper cancele el último comando de paso que recibió.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a>Comentarios  
 Es posible que se emita un nuevo comando de paso A paso después de que se haya cancelado el comando de paso recibido más recientemente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
