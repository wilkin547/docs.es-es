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
ms.openlocfilehash: 234705e4495a1a582f3801ad1e645f923cd6f4b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727697"
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
 de Establezca en `true` para entrar en una función a la que se llama en el subproceso. Establezca en `false` para recorrer la función.  
  
## <a name="remarks"></a>Comentarios  

 El paso se completa cuando el Common Language Runtime realiza la siguiente instrucción administrada en el marco de este stepper. Si `Step` se llama a en un stepper, que no está en el código administrado, el paso se completará cuando el subproceso ejecute la siguiente instrucción de código administrado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
