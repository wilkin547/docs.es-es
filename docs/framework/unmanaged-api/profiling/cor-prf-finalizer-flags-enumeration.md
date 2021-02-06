---
description: 'Más información acerca de: enumeración COR_PRF_FINALIZER_FLAGS'
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
ms.openlocfilehash: 96430b1ba3a38cce2801ed55f030395154c78dab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649202"
---
# <a name="cor_prf_finalizer_flags-enumeration"></a><span data-ttu-id="caf47-103">COR_PRF_FINALIZER_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="caf47-103">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>

<span data-ttu-id="caf47-104">Describe el finalizador de un objeto.</span><span class="sxs-lookup"><span data-stu-id="caf47-104">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caf47-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="caf47-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="caf47-106">Members</span><span class="sxs-lookup"><span data-stu-id="caf47-106">Members</span></span>  
  
|<span data-ttu-id="caf47-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="caf47-107">Member</span></span>|<span data-ttu-id="caf47-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="caf47-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="caf47-109">El finalizador es crítico.</span><span class="sxs-lookup"><span data-stu-id="caf47-109">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="caf47-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="caf47-110">Remarks</span></span>  

 <span data-ttu-id="caf47-111">El `COR_PRF_FINALIZER_FLAGS` método [ICorProfilerCallback2:: finalizeableobjectqueued (](icorprofilercallback2-finalizeableobjectqueued-method.md) usa la enumeración para describir el finalizador de un objeto.</span><span class="sxs-lookup"><span data-stu-id="caf47-111">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caf47-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="caf47-112">Requirements</span></span>  

 <span data-ttu-id="caf47-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="caf47-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caf47-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="caf47-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="caf47-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="caf47-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="caf47-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caf47-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caf47-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="caf47-117">See also</span></span>

- [<span data-ttu-id="caf47-118">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="caf47-118">Profiling Enumerations</span></span>](profiling-enumerations.md)
