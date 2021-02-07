---
description: 'Más información sobre: ICorDebugValueEnum:: Next (método)'
title: ICorDebugValueEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum::Next
helpviewer_keywords:
- ICorDebugValueEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: f5ef94dd-dfee-49d3-a398-b110f8906dd8
topic_type:
- apiref
ms.openlocfilehash: 9a02c769f69651227669eb4b3f8c5ce41b670a73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690111"
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="72cd1-103">ICorDebugValueEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="72cd1-103">ICorDebugValueEnum::Next Method</span></span>

<span data-ttu-id="72cd1-104">Obtiene el número especificado de instancias de "ICorDebugValue" de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="72cd1-104">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72cd1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72cd1-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72cd1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="72cd1-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="72cd1-107">de El número de `ICorDebugValue` instancias que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="72cd1-107">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="72cd1-108">enuncia Matriz de punteros, cada uno de los cuales señala a un `ICorDebugValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="72cd1-108">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="72cd1-109">enuncia Puntero al número de `ICorDebugValue` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="72cd1-109">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="72cd1-110">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="72cd1-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72cd1-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72cd1-111">Requirements</span></span>  

 <span data-ttu-id="72cd1-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72cd1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72cd1-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72cd1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72cd1-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72cd1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72cd1-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72cd1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72cd1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="72cd1-116">See also</span></span>
