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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a66b2b94765c3d59327e500f1e208dc93cd8e231
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781933"
---
# <a name="corprffinalizerflags-enumeration"></a><span data-ttu-id="bba99-102">COR_PRF_FINALIZER_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="bba99-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="bba99-103">Describe el finalizador de un objeto.</span><span class="sxs-lookup"><span data-stu-id="bba99-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bba99-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bba99-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="bba99-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="bba99-105">Members</span></span>  
  
|<span data-ttu-id="bba99-106">Member</span><span class="sxs-lookup"><span data-stu-id="bba99-106">Member</span></span>|<span data-ttu-id="bba99-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bba99-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="bba99-108">El finalizador es crítico.</span><span class="sxs-lookup"><span data-stu-id="bba99-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bba99-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bba99-109">Remarks</span></span>  
 <span data-ttu-id="bba99-110">El `COR_PRF_FINALIZER_FLAGS` enumeración la utiliza el [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) método para describir el finalizador de un objeto.</span><span class="sxs-lookup"><span data-stu-id="bba99-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bba99-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bba99-111">Requirements</span></span>  
 <span data-ttu-id="bba99-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bba99-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bba99-113">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bba99-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bba99-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bba99-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bba99-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bba99-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bba99-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="bba99-116">See also</span></span>

- [<span data-ttu-id="bba99-117">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="bba99-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
