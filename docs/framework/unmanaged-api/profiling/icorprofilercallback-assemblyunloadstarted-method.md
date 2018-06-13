---
title: ICorProfilerCallback::AssemblyUnloadStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted method [.NET Framework profiling]
- AssemblyUnloadStarted method [.NET Framework profiling]
ms.assetid: 6e47b7e5-0335-4dd3-8c42-d3c07d62b102
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 10475831be02bd4a958da84b7b75409cf3ad4097
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450530"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="94cb7-102">ICorProfilerCallback::AssemblyUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="94cb7-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="94cb7-103">Notifica al generador de perfiles que se está descargando un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="94cb7-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94cb7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94cb7-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="94cb7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="94cb7-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="94cb7-106">[in] Identifica el ensamblado que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="94cb7-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94cb7-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="94cb7-107">Remarks</span></span>  
 <span data-ttu-id="94cb7-108">El valor de `assemblyId` no es válido para una solicitud de información después de la `AssemblyUnloadStarted` devuelve del método: se trata de última oportunidad del generador de perfiles para obtener información acerca de este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="94cb7-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94cb7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94cb7-109">Requirements</span></span>  
 <span data-ttu-id="94cb7-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94cb7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94cb7-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="94cb7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="94cb7-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94cb7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94cb7-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94cb7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94cb7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="94cb7-114">See Also</span></span>  
 [<span data-ttu-id="94cb7-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="94cb7-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="94cb7-116">AssemblyUnloadFinished (método)</span><span class="sxs-lookup"><span data-stu-id="94cb7-116">AssemblyUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)
