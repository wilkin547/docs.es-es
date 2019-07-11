---
title: ICorDebugStepper::Step (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Step
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d0f601c4b454b55edc5fa25eb2ee33d491009b9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760574"
---
# <a name="icordebugstepperstep-method"></a>ICorDebugStepper::Step (Método)
Hace que este ICorDebugStepper paso a paso a través del subproceso que la contiene y, opcionalmente, para continuar pasando solo a través de funciones que se llaman dentro del subproceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `bStepIn`  
 [in] Establecido en `true` para adentrarse en una función que se llama dentro del subproceso. Establecido en `false` al paso a través de la función.  
  
## <a name="remarks"></a>Comentarios  
 El paso finaliza cuando common language runtime ejecuta la siguiente instrucción administrada en el marco de este motor de paso a paso. Si `Step` es llamado en un motor paso a paso, que no está en código administrado, el paso finalizará cuando se ejecuta la siguiente instrucción de código administrado por el subproceso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
