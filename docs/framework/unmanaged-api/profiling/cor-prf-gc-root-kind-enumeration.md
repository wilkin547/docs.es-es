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
ms.openlocfilehash: 0ea584bfff4340e5e9635d6c31e177e88765b582
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500876"
---
# <a name="cor_prf_gc_root_kind-enumeration"></a><span data-ttu-id="a490f-102">COR_PRF_GC_ROOT_KIND (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a490f-102">COR_PRF_GC_ROOT_KIND Enumeration</span></span>
<span data-ttu-id="a490f-103">Indica el tipo de raíz de recolección de elementos no utilizados expuesta por la devolución de llamada [ICorProfilerCallback2:: RootReferences2 (](icorprofilercallback2-rootreferences2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a490f-103">Indicates the kind of garbage collection root that is exposed by the [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a490f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a490f-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_STACK = 1,  
    COR_PRF_GC_ROOT_FINALIZER = 2,  
    COR_PRF_GC_ROOT_HANDLE = 3,  
    COR_PRF_GC_ROOT_OTHER = 0  
} COR_PRF_GC_ROOT_KIND;  
```  
  
## <a name="members"></a><span data-ttu-id="a490f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a490f-105">Members</span></span>  
  
|<span data-ttu-id="a490f-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a490f-106">Member</span></span>|<span data-ttu-id="a490f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a490f-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_STACK`|<span data-ttu-id="a490f-108">La raíz es una variable de la pila.</span><span class="sxs-lookup"><span data-stu-id="a490f-108">The root is a variable on the stack.</span></span>|  
|`COR_PRF_GC_ROOT_FINALIZER`|<span data-ttu-id="a490f-109">La raíz es una entrada en la cola del finalizador.</span><span class="sxs-lookup"><span data-stu-id="a490f-109">The root is an entry in the finalizer queue.</span></span>|  
|`COR_PRF_GC_ROOT_HANDLE`|<span data-ttu-id="a490f-110">La raíz es un identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a490f-110">The root is a garbage collection handle.</span></span>|  
|`COR_PRF_GC_ROOT_OTHER`|<span data-ttu-id="a490f-111">No se ha especificado el tipo de raíz.</span><span class="sxs-lookup"><span data-stu-id="a490f-111">The kind of root is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a490f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a490f-112">Requirements</span></span>  
 <span data-ttu-id="a490f-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a490f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a490f-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a490f-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a490f-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a490f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a490f-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a490f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a490f-117">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="a490f-117">See also</span></span>

- [<span data-ttu-id="a490f-118">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a490f-118">Profiling Enumerations</span></span>](profiling-enumerations.md)
