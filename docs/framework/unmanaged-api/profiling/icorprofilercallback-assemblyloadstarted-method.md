---
title: ICorProfilerCallback::AssemblyLoadStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadStarted method [.NET Framework profiling]
- AssemblyLoadStarted method [.NET Framework profiling]
ms.assetid: 67e8209d-a0ca-4118-a6e6-c1ee0abc2221
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fbb9a48fc4795f2e5f074369318fec6d4152d9d5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468759"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="3e5c5-102">ICorProfilerCallback::AssemblyLoadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="3e5c5-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>
<span data-ttu-id="3e5c5-103">Notifica al generador de perfiles que se está cargando un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3e5c5-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e5c5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e5c5-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e5c5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3e5c5-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="3e5c5-106">[in] Identifica el ensamblado que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="3e5c5-106">[in] Identifies the assembly that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e5c5-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3e5c5-107">Remarks</span></span>  
 <span data-ttu-id="3e5c5-108">El valor de `assemblyId` no es válido para una solicitud de información hasta la [AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) se llama al método.</span><span class="sxs-lookup"><span data-stu-id="3e5c5-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e5c5-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e5c5-109">Requirements</span></span>  
 <span data-ttu-id="3e5c5-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e5c5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e5c5-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3e5c5-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3e5c5-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e5c5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e5c5-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e5c5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e5c5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e5c5-114">See also</span></span>
- [<span data-ttu-id="3e5c5-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3e5c5-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
