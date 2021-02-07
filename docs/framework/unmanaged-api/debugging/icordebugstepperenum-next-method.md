---
description: 'Más información sobre: ICorDebugStepperEnum (:: Next (método)'
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
ms.openlocfilehash: e0c17fbc570d5ea8a4a56c89a5a2c855ed045bd7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717477"
---
# <a name="icordebugstepperenumnext-method"></a><span data-ttu-id="6ddee-103">ICorDebugStepperEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="6ddee-103">ICorDebugStepperEnum::Next Method</span></span>

<span data-ttu-id="6ddee-104">Obtiene el número especificado de instancias de ICorDebugStepper de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="6ddee-104">Gets the specified number of ICorDebugStepper instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ddee-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ddee-105">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugStepper *steppers[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ddee-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6ddee-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="6ddee-107">de El número de `ICorDebugStepper` instancias que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="6ddee-107">[in] The number of `ICorDebugStepper` instances to be retrieved.</span></span>  
  
 `steppers`  
 <span data-ttu-id="6ddee-108">enuncia Matriz de punteros, cada uno de los cuales señala a un `ICorDebugStepper` objeto.</span><span class="sxs-lookup"><span data-stu-id="6ddee-108">[out] An array of pointers, each of which points to an `ICorDebugStepper` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="6ddee-109">enuncia Puntero al número de `ICorDebugStepper` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="6ddee-109">[out] Pointer to the number of `ICorDebugStepper` instances actually returned.</span></span> <span data-ttu-id="6ddee-110">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="6ddee-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ddee-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ddee-111">Requirements</span></span>  

 <span data-ttu-id="6ddee-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ddee-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ddee-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ddee-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ddee-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ddee-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ddee-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ddee-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
