---
title: ICorDebugStepperEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStepperEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepperEnum::Next
helpviewer_keywords:
- Next method, ICorDebugStepperEnum interface [.NET Framework debugging]
- ICorDebugStepperEnum::Next method [.NET Framework debugging]
ms.assetid: d0ea0f30-e8d2-48b0-8477-e1a029ceb4dd
topic_type:
- apiref
ms.openlocfilehash: 11d9c7393827b613d49e23972b4896bfe657a544
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138983"
---
# <a name="icordebugstepperenumnext-method"></a>ICorDebugStepperEnum::Next (Método)
Obtiene el número especificado de instancias de ICorDebugStepper de la enumeración, comenzando en la posición actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Next(  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugStepper *steppers[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `celt`  
 de Número de instancias de `ICorDebugStepper` que se van a recuperar.  
  
 `steppers`  
 enuncia Matriz de punteros, cada uno de los cuales señala a un objeto `ICorDebugStepper`.  
  
 `pceltFetched`  
 enuncia Puntero al número de instancias de `ICorDebugStepper` devueltas realmente. Este valor puede ser null si `celt` es uno.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
