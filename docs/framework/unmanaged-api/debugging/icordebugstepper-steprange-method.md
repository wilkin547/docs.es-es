---
title: ICorDebugStepper::StepRange (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type:
- apiref
ms.openlocfilehash: 21b8bf618e197372e301d5f56e7592c20710014d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791708"
---
# <a name="icordebugsteppersteprange-method"></a>ICorDebugStepper::StepRange (Método)
Hace que este objeto ICorDebugStepper tenga un solo paso a través de su subproceso contenedor y que devuelva cuando llegue al código que se encuentra más allá del último de los intervalos especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `bStepIn`  
 de Establezca en `true` para entrar en una función a la que se llama en el subproceso. Establezca en `false` para pasar por la función.  
  
 `ranges`  
 de Matriz de estructuras de COR_DEBUG_STEP_RANGE, cada una de las cuales especifica un intervalo.  
  
 `cRangeCount`  
 [in] Tamaño de la matriz `ranges`.  
  
## <a name="remarks"></a>Notas  
 El método `StepRange` funciona como el método [ICorDebugStepper:: Step](icordebugstepper-step-method.md) , salvo que no se completa hasta que se alcanza el código fuera del intervalo especificado.  
  
 Esto puede ser más eficaz que ejecutar una instrucción cada vez. Los intervalos se especifican como una lista de pares de desplazamiento desde el inicio del marco del stepper.  
  
 Los intervalos son relativos al código del lenguaje intermedio de Microsoft (MSIL) de un método. Llame a [ICorDebugStepper:: SetRangeIL (](icordebugstepper-setrangeil-method.md) con `false` para que los intervalos sean relativos al código nativo de un método.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
