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
ms.openlocfilehash: 5e718d05f033cc46fa460a81f6816a13ec32476d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428348"
---
# <a name="cor_prf_finalizer_flags-enumeration"></a><span data-ttu-id="069af-102">COR_PRF_FINALIZER_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="069af-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="069af-103">Describe el finalizador de un objeto.</span><span class="sxs-lookup"><span data-stu-id="069af-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="069af-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="069af-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="069af-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="069af-105">Members</span></span>  
  
|<span data-ttu-id="069af-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="069af-106">Member</span></span>|<span data-ttu-id="069af-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="069af-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="069af-108">El finalizador es crítico.</span><span class="sxs-lookup"><span data-stu-id="069af-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="069af-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="069af-109">Remarks</span></span>  
 <span data-ttu-id="069af-110">El método [ICorProfilerCallback2:: finalizeableobjectqueued (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) usa la enumeración `COR_PRF_FINALIZER_FLAGS` para describir el finalizador de un objeto.</span><span class="sxs-lookup"><span data-stu-id="069af-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="069af-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="069af-111">Requirements</span></span>  
 <span data-ttu-id="069af-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="069af-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="069af-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="069af-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="069af-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="069af-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="069af-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="069af-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="069af-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="069af-116">See also</span></span>

- [<span data-ttu-id="069af-117">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="069af-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
