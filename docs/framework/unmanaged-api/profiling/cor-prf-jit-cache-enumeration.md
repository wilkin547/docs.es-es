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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0cdbe36403f830926d611ffdc655d82ea25ddeef
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144799"
---
# <a name="corprfjitcache-enumeration"></a><span data-ttu-id="1843a-102">COR_PRF_JIT_CACHE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="1843a-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="1843a-103">Indica el resultado de una búsqueda de función en caché.</span><span class="sxs-lookup"><span data-stu-id="1843a-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
>  `COR_PRF_CACHED_FUNCTION_FOUND` <span data-ttu-id="1843a-104">tiene un valor de cero, por lo que `COR_PRF_JIT_CACHE` no se puede usar como un suplente booleano.</span><span class="sxs-lookup"><span data-stu-id="1843a-104">has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1843a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1843a-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="1843a-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="1843a-106">Members</span></span>  
  
|<span data-ttu-id="1843a-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="1843a-107">Member</span></span>|<span data-ttu-id="1843a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="1843a-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="1843a-109">La búsqueda encuentra la función.</span><span class="sxs-lookup"><span data-stu-id="1843a-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="1843a-110">La búsqueda no encontró la función.</span><span class="sxs-lookup"><span data-stu-id="1843a-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1843a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1843a-111">Requirements</span></span>  
 <span data-ttu-id="1843a-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1843a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1843a-113">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1843a-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1843a-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1843a-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1843a-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1843a-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1843a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1843a-116">See also</span></span>

- [<span data-ttu-id="1843a-117">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1843a-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
