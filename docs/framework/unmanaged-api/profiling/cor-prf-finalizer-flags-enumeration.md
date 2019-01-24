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
ms.openlocfilehash: 7800567f51196154f49c93dbbbe819f77cefdfe8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499043"
---
# <a name="corprffinalizerflags-enumeration"></a><span data-ttu-id="02cd0-102">COR_PRF_FINALIZER_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="02cd0-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="02cd0-103">Describe el finalizador de un objeto.</span><span class="sxs-lookup"><span data-stu-id="02cd0-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02cd0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02cd0-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="02cd0-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="02cd0-105">Members</span></span>  
  
|<span data-ttu-id="02cd0-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="02cd0-106">Member</span></span>|<span data-ttu-id="02cd0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="02cd0-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="02cd0-108">El finalizador es crítico.</span><span class="sxs-lookup"><span data-stu-id="02cd0-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02cd0-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="02cd0-109">Remarks</span></span>  
 <span data-ttu-id="02cd0-110">El `COR_PRF_FINALIZER_FLAGS` enumeración la utiliza el [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) método para describir el finalizador de un objeto.</span><span class="sxs-lookup"><span data-stu-id="02cd0-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02cd0-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02cd0-111">Requirements</span></span>  
 <span data-ttu-id="02cd0-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02cd0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02cd0-113">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="02cd0-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="02cd0-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02cd0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02cd0-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02cd0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02cd0-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="02cd0-116">See also</span></span>
- [<span data-ttu-id="02cd0-117">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="02cd0-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
