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
ms.openlocfilehash: 0bf17e7c9d8ff16dc8f07e4a386f599284828f40
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682255"
---
# <a name="cor_prf_jit_cache-enumeration"></a><span data-ttu-id="8f1f6-102">COR_PRF_JIT_CACHE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="8f1f6-102">COR_PRF_JIT_CACHE Enumeration</span></span>

<span data-ttu-id="8f1f6-103">Indica el resultado de una búsqueda de función en caché.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8f1f6-104">`COR_PRF_CACHED_FUNCTION_FOUND` tiene un valor de cero, por lo que `COR_PRF_JIT_CACHE` no se puede usar como suplente booleano.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f1f6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f1f6-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="8f1f6-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="8f1f6-106">Members</span></span>  
  
|<span data-ttu-id="8f1f6-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="8f1f6-107">Member</span></span>|<span data-ttu-id="8f1f6-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="8f1f6-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="8f1f6-109">La búsqueda encontró la función.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="8f1f6-110">La búsqueda no encontró la función.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8f1f6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f1f6-111">Requirements</span></span>  

 <span data-ttu-id="8f1f6-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f1f6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f1f6-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8f1f6-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8f1f6-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f1f6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f1f6-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f1f6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f1f6-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8f1f6-116">See also</span></span>

- [<span data-ttu-id="8f1f6-117">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="8f1f6-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
