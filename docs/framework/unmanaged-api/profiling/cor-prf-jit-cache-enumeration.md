---
title: COR_PRF_JIT_CACHE (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_JIT_CACHE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_JIT_CACHE
helpviewer_keywords:
- COR_PRF_JIT_CACHE enumeration [.NET Framework profiling]
ms.assetid: e7b8f6b4-95bc-4ba5-b9eb-f5590a7326a4
topic_type:
- apiref
ms.openlocfilehash: d19d7ed2262db6d3c6e7f15db0e96da52f86db4a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500863"
---
# <a name="cor_prf_jit_cache-enumeration"></a><span data-ttu-id="1061c-102">COR_PRF_JIT_CACHE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="1061c-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="1061c-103">Indica el resultado de una búsqueda de función en caché.</span><span class="sxs-lookup"><span data-stu-id="1061c-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1061c-104">`COR_PRF_CACHED_FUNCTION_FOUND`tiene un valor de cero, por lo que `COR_PRF_JIT_CACHE` no se puede usar como suplente booleano.</span><span class="sxs-lookup"><span data-stu-id="1061c-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1061c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1061c-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="1061c-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="1061c-106">Members</span></span>  
  
|<span data-ttu-id="1061c-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="1061c-107">Member</span></span>|<span data-ttu-id="1061c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="1061c-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="1061c-109">La búsqueda encontró la función.</span><span class="sxs-lookup"><span data-stu-id="1061c-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="1061c-110">La búsqueda no encontró la función.</span><span class="sxs-lookup"><span data-stu-id="1061c-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1061c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1061c-111">Requirements</span></span>  
 <span data-ttu-id="1061c-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1061c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1061c-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1061c-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1061c-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1061c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1061c-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1061c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1061c-116">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="1061c-116">See also</span></span>

- [<span data-ttu-id="1061c-117">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1061c-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
