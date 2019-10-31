---
title: ICorDebugStepper::IsActive (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::IsActive method [.NET Framework debugging]
ms.assetid: 8b35e7a9-b40e-40a9-8d8e-b82e823fc575
topic_type:
- apiref
ms.openlocfilehash: a242764710d92e81e8089bc2919734bfac4bcdb2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137574"
---
# <a name="icordebugstepperisactive-method"></a>ICorDebugStepper::IsActive (Método)
Obtiene un valor que indica si esta ICorDebugStepper está ejecutando actualmente un paso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pbActive`  
 enuncia Devuelve `true` si el stepper está ejecutando actualmente un paso; de lo contrario, devuelve `false`.  
  
## <a name="remarks"></a>Comentarios  
 Cualquier acción de paso permanece activa hasta que el depurador recibe una llamada [ICorDebugManagedCallback:: StepComplete (](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) , que desactiva automáticamente el stepper. Un stepper también se puede desactivar prematuramente si se llama a [ICorDebugStepper::D eactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) antes de que se alcance la condición de devolución de llamada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
