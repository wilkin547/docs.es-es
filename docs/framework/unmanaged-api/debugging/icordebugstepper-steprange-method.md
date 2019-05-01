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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b18474aeaa79224de5371df3ff0cac5ed9bf4ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994292"
---
# <a name="icordebugsteppersteprange-method"></a>ICorDebugStepper::StepRange (Método)
Hace que este ICorDebugStepper paso a paso a través del subproceso que la contiene y devolver cuando llegue al código más allá del último de los intervalos especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `bStepIn`  
 [in] Establecido en `true` para adentrarse en una función que se llama dentro del subproceso. Establecido en `false` al paso a través de la función.  
  
 `ranges`  
 [in] Una matriz de estructuras COR_DEBUG_STEP_RANGE, cada uno de los cuales especifica un intervalo.  
  
 `cRangeCount`  
 [in] Tamaño de la matriz `ranges`.  
  
## <a name="remarks"></a>Comentarios  
 El `StepRange` método funciona igual que el [ICorDebugStepper](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) se alcanza el método, salvo que no se completa hasta que el código fuera del intervalo especificado.  
  
 Esto puede ser más eficaz que la ejecución paso a paso una instrucción a la vez. Los intervalos se especifican como una lista de pares de desplazamiento desde el principio del marco del componente.  
  
 Los intervalos son relativos al código de lenguaje intermedio (MSIL) de Microsoft de un método. Llame a [SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) con `false` para hacer que los intervalos en relación con el código nativo de un método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
