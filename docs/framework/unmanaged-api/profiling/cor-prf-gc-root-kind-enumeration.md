---
description: 'Más información acerca de: enumeración COR_PRF_GC_ROOT_KIND'
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
ms.openlocfilehash: 148d48458c906974d76b9e0ec0cb6b4d15ee49ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648784"
---
# <a name="cor_prf_gc_root_kind-enumeration"></a><span data-ttu-id="bfb09-103">COR_PRF_GC_ROOT_KIND (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="bfb09-103">COR_PRF_GC_ROOT_KIND Enumeration</span></span>

<span data-ttu-id="bfb09-104">Indica el tipo de raíz de recolección de elementos no utilizados expuesta por la devolución de llamada [ICorProfilerCallback2:: RootReferences2 (](icorprofilercallback2-rootreferences2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bfb09-104">Indicates the kind of garbage collection root that is exposed by the [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfb09-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bfb09-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_STACK = 1,  
    COR_PRF_GC_ROOT_FINALIZER = 2,  
    COR_PRF_GC_ROOT_HANDLE = 3,  
    COR_PRF_GC_ROOT_OTHER = 0  
} COR_PRF_GC_ROOT_KIND;  
```  
  
## <a name="members"></a><span data-ttu-id="bfb09-106">Members</span><span class="sxs-lookup"><span data-stu-id="bfb09-106">Members</span></span>  
  
|<span data-ttu-id="bfb09-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="bfb09-107">Member</span></span>|<span data-ttu-id="bfb09-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="bfb09-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_STACK`|<span data-ttu-id="bfb09-109">La raíz es una variable de la pila.</span><span class="sxs-lookup"><span data-stu-id="bfb09-109">The root is a variable on the stack.</span></span>|  
|`COR_PRF_GC_ROOT_FINALIZER`|<span data-ttu-id="bfb09-110">La raíz es una entrada en la cola del finalizador.</span><span class="sxs-lookup"><span data-stu-id="bfb09-110">The root is an entry in the finalizer queue.</span></span>|  
|`COR_PRF_GC_ROOT_HANDLE`|<span data-ttu-id="bfb09-111">La raíz es un identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="bfb09-111">The root is a garbage collection handle.</span></span>|  
|`COR_PRF_GC_ROOT_OTHER`|<span data-ttu-id="bfb09-112">No se ha especificado el tipo de raíz.</span><span class="sxs-lookup"><span data-stu-id="bfb09-112">The kind of root is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bfb09-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bfb09-113">Requirements</span></span>  

 <span data-ttu-id="bfb09-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfb09-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfb09-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bfb09-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bfb09-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bfb09-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfb09-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfb09-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfb09-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfb09-118">See also</span></span>

- [<span data-ttu-id="bfb09-119">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="bfb09-119">Profiling Enumerations</span></span>](profiling-enumerations.md)
