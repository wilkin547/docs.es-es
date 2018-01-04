---
title: "ICorProfilerCallback::AssemblyLoadStarted (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AssemblyLoadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AssemblyLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadStarted method [.NET Framework profiling]
- AssemblyLoadStarted method [.NET Framework profiling]
ms.assetid: 67e8209d-a0ca-4118-a6e6-c1ee0abc2221
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 48453532177b1e619f4f863e7297345566637d4f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="a5707-102">ICorProfilerCallback::AssemblyLoadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="a5707-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>
<span data-ttu-id="a5707-103">Notifica el generador de perfiles que se va a cargar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a5707-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5707-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5707-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5707-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a5707-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="a5707-106">[in] Identifica el ensamblado que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="a5707-106">[in] Identifies the assembly that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5707-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a5707-107">Remarks</span></span>  
 <span data-ttu-id="a5707-108">El valor de `assemblyId` no es válido para una solicitud de información hasta que el [ICorProfilerCallback:: AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) se llama al método.</span><span class="sxs-lookup"><span data-stu-id="a5707-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5707-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5707-109">Requirements</span></span>  
 <span data-ttu-id="a5707-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5707-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5707-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a5707-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a5707-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5707-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5707-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5707-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5707-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5707-114">See Also</span></span>  
 [<span data-ttu-id="a5707-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5707-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
