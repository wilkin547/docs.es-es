---
title: COR_PRF_GC_ROOT_KIND (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_KIND
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_KIND
helpviewer_keywords:
- COR_PRF_GC_ROOT_KIND enumeration [.NET Framework profiling]
ms.assetid: b9fb1c03-417f-41d4-aed4-02cb4ade8def
topic_type:
- apiref
ms.openlocfilehash: e86074031b8fc2c82636e7aef2177eaf04a9db14
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682372"
---
# <a name="cor_prf_gc_root_kind-enumeration"></a><span data-ttu-id="78e7a-102">COR_PRF_GC_ROOT_KIND (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="78e7a-102">COR_PRF_GC_ROOT_KIND Enumeration</span></span>

<span data-ttu-id="78e7a-103">Indica el tipo de raíz de recolección de elementos no utilizados expuesta por la devolución de llamada [ICorProfilerCallback2:: RootReferences2 (](icorprofilercallback2-rootreferences2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="78e7a-103">Indicates the kind of garbage collection root that is exposed by the [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78e7a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78e7a-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_STACK = 1,  
    COR_PRF_GC_ROOT_FINALIZER = 2,  
    COR_PRF_GC_ROOT_HANDLE = 3,  
    COR_PRF_GC_ROOT_OTHER = 0  
} COR_PRF_GC_ROOT_KIND;  
```  
  
## <a name="members"></a><span data-ttu-id="78e7a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="78e7a-105">Members</span></span>  
  
|<span data-ttu-id="78e7a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="78e7a-106">Member</span></span>|<span data-ttu-id="78e7a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="78e7a-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_STACK`|<span data-ttu-id="78e7a-108">La raíz es una variable de la pila.</span><span class="sxs-lookup"><span data-stu-id="78e7a-108">The root is a variable on the stack.</span></span>|  
|`COR_PRF_GC_ROOT_FINALIZER`|<span data-ttu-id="78e7a-109">La raíz es una entrada en la cola del finalizador.</span><span class="sxs-lookup"><span data-stu-id="78e7a-109">The root is an entry in the finalizer queue.</span></span>|  
|`COR_PRF_GC_ROOT_HANDLE`|<span data-ttu-id="78e7a-110">La raíz es un identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="78e7a-110">The root is a garbage collection handle.</span></span>|  
|`COR_PRF_GC_ROOT_OTHER`|<span data-ttu-id="78e7a-111">No se ha especificado el tipo de raíz.</span><span class="sxs-lookup"><span data-stu-id="78e7a-111">The kind of root is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="78e7a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78e7a-112">Requirements</span></span>  

 <span data-ttu-id="78e7a-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78e7a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78e7a-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="78e7a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="78e7a-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78e7a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78e7a-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78e7a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78e7a-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="78e7a-117">See also</span></span>

- [<span data-ttu-id="78e7a-118">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="78e7a-118">Profiling Enumerations</span></span>](profiling-enumerations.md)
