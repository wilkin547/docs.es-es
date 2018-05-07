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
ms.openlocfilehash: c2d282e27ec5068fa6fe7f58ba95458fdc219972
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugstepperstep-method"></a>ICorDebugStepper::Step (Método)
Hace que esta instancia de ICorDebugStepper paso a paso a través de un subproceso que lo contiene y, opcionalmente, para seguir paso único a través de funciones que se llaman desde el subproceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `bStepIn`  
 [in] Establecido en `true` para ir a una función que se llama desde el subproceso. Establecido en `false` para pasar por alto la función.  
  
## <a name="remarks"></a>Comentarios  
 El paso finaliza cuando common language runtime ejecuta la siguiente instrucción administrada en el marco del este paso a paso desencadene. Si `Step` es llamar en un paso a paso desencadene, que no está en código administrado, el paso finalizará cuando se ejecuta la siguiente instrucción de código administrado en el subproceso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
