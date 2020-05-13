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
ms.openlocfilehash: 293d1a9cd93b5ce45105427e7df864ad8bfbe77a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379191"
---
# <a name="icordebugstepperenumnext-method"></a><span data-ttu-id="27db0-102">ICorDebugStepperEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="27db0-102">ICorDebugStepperEnum::Next Method</span></span>
<span data-ttu-id="27db0-103">Obtiene el número especificado de instancias de ICorDebugStepper de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="27db0-103">Gets the specified number of ICorDebugStepper instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27db0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27db0-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugStepper *steppers[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27db0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="27db0-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="27db0-106">de El número de `ICorDebugStepper` instancias que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="27db0-106">[in] The number of `ICorDebugStepper` instances to be retrieved.</span></span>  
  
 `steppers`  
 <span data-ttu-id="27db0-107">enuncia Matriz de punteros, cada uno de los cuales señala a un `ICorDebugStepper` objeto.</span><span class="sxs-lookup"><span data-stu-id="27db0-107">[out] An array of pointers, each of which points to an `ICorDebugStepper` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="27db0-108">enuncia Puntero al número de `ICorDebugStepper` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="27db0-108">[out] Pointer to the number of `ICorDebugStepper` instances actually returned.</span></span> <span data-ttu-id="27db0-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="27db0-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27db0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27db0-110">Requirements</span></span>  
 <span data-ttu-id="27db0-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27db0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27db0-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27db0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27db0-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27db0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27db0-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27db0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
