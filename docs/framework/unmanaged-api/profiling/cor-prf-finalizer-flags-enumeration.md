---
title: COR_PRF_FINALIZER_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_FINALIZER_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FINALIZER_FLAGS
helpviewer_keywords:
- COR_PRF_FINALIZER_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 297d7721-3911-4f36-9e34-d9da0c33e22a
topic_type:
- apiref
ms.openlocfilehash: 2b766715d6d87ab17a7cdabf721bbebf67e1ff13
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718584"
---
# <a name="cor_prf_finalizer_flags-enumeration"></a><span data-ttu-id="a24fa-102">COR_PRF_FINALIZER_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a24fa-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>

<span data-ttu-id="a24fa-103">Describe el finalizador de un objeto.</span><span class="sxs-lookup"><span data-stu-id="a24fa-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a24fa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a24fa-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="a24fa-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a24fa-105">Members</span></span>  
  
|<span data-ttu-id="a24fa-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a24fa-106">Member</span></span>|<span data-ttu-id="a24fa-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a24fa-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="a24fa-108">El finalizador es crítico.</span><span class="sxs-lookup"><span data-stu-id="a24fa-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a24fa-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a24fa-109">Remarks</span></span>  

 <span data-ttu-id="a24fa-110">El `COR_PRF_FINALIZER_FLAGS` método [ICorProfilerCallback2:: finalizeableobjectqueued (](icorprofilercallback2-finalizeableobjectqueued-method.md) usa la enumeración para describir el finalizador de un objeto.</span><span class="sxs-lookup"><span data-stu-id="a24fa-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a24fa-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a24fa-111">Requirements</span></span>  

 <span data-ttu-id="a24fa-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a24fa-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a24fa-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a24fa-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a24fa-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a24fa-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a24fa-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a24fa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a24fa-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a24fa-116">See also</span></span>

- [<span data-ttu-id="a24fa-117">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a24fa-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
