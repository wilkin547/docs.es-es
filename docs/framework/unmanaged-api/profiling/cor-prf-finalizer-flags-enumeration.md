---
title: "COR_PRF_FINALIZER_FLAGS (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_FINALIZER_FLAGS
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_FINALIZER_FLAGS
helpviewer_keywords: COR_PRF_FINALIZER_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 297d7721-3911-4f36-9e34-d9da0c33e22a
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 63707ca18be29555919264f9aa3a0f143efdd374
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corprffinalizerflags-enumeration"></a><span data-ttu-id="de2ae-102">COR_PRF_FINALIZER_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="de2ae-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="de2ae-103">Describe el finalizador de un objeto.</span><span class="sxs-lookup"><span data-stu-id="de2ae-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de2ae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de2ae-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="de2ae-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="de2ae-105">Members</span></span>  
  
|<span data-ttu-id="de2ae-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="de2ae-106">Member</span></span>|<span data-ttu-id="de2ae-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="de2ae-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="de2ae-108">El finalizador es crítico.</span><span class="sxs-lookup"><span data-stu-id="de2ae-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de2ae-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de2ae-109">Remarks</span></span>  
 <span data-ttu-id="de2ae-110">El `COR_PRF_FINALIZER_FLAGS` enumeración es utilizada por la [ICorProfilerCallback2:: FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) método para describir el finalizador de un objeto.</span><span class="sxs-lookup"><span data-stu-id="de2ae-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de2ae-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de2ae-111">Requirements</span></span>  
 <span data-ttu-id="de2ae-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de2ae-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de2ae-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="de2ae-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="de2ae-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de2ae-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de2ae-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de2ae-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de2ae-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="de2ae-116">See Also</span></span>  
 [<span data-ttu-id="de2ae-117">Enumeraciones de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="de2ae-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
