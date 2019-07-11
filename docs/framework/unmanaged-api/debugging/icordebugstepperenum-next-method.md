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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58f148eb4c3206ba12eed41df670846d7beab77a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771635"
---
# <a name="icordebugstepperenumnext-method"></a><span data-ttu-id="0b8dc-102">ICorDebugStepperEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="0b8dc-102">ICorDebugStepperEnum::Next Method</span></span>
<span data-ttu-id="0b8dc-103">Obtiene el número de instancias de ICorDebugStepper especificado de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="0b8dc-103">Gets the specified number of ICorDebugStepper instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b8dc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b8dc-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugStepper *steppers[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b8dc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0b8dc-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="0b8dc-106">[in] El número de `ICorDebugStepper` instancias va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="0b8dc-106">[in] The number of `ICorDebugStepper` instances to be retrieved.</span></span>  
  
 `steppers`  
 <span data-ttu-id="0b8dc-107">[out] Una matriz de punteros, cada uno de los cuales señala a una `ICorDebugStepper` objeto.</span><span class="sxs-lookup"><span data-stu-id="0b8dc-107">[out] An array of pointers, each of which points to an `ICorDebugStepper` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="0b8dc-108">[out] Puntero al número de `ICorDebugStepper` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="0b8dc-108">[out] Pointer to the number of `ICorDebugStepper` instances actually returned.</span></span> <span data-ttu-id="0b8dc-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="0b8dc-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b8dc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0b8dc-110">Requirements</span></span>  
 <span data-ttu-id="0b8dc-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b8dc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b8dc-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b8dc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b8dc-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b8dc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b8dc-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b8dc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
