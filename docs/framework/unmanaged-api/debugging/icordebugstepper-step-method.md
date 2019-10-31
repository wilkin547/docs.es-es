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
ms.openlocfilehash: 43f86e704e4a52a702b8f563e3c613806eb061b5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137531"
---
# <a name="icordebugstepperstep-method"></a>ICorDebugStepper::Step (Método)
Hace que este objeto ICorDebugStepper tenga un solo paso a través de su subproceso contenedor y, opcionalmente, continúe con el paso a través de las funciones a las que se llama en el subproceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `bStepIn`  
 de Establezca en `true` para entrar en una función a la que se llama en el subproceso. Establezca en `false` para pasar por la función.  
  
## <a name="remarks"></a>Comentarios  
 El paso se completa cuando el Common Language Runtime realiza la siguiente instrucción administrada en el marco de este stepper. Si se llama a `Step` en un stepper, que no está en código administrado, el paso se completará cuando el subproceso ejecute la siguiente instrucción de código administrado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
