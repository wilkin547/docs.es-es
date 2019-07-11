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
ms.openlocfilehash: 4ace66630176149a18a174fad24f782a289b0e9d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763003"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="c8039-102">ICorProfilerCallback::AssemblyLoadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="c8039-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>
<span data-ttu-id="c8039-103">Notifica al generador de perfiles que se está cargando un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c8039-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8039-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8039-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8039-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c8039-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="c8039-106">[in] Identifica el ensamblado que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="c8039-106">[in] Identifies the assembly that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8039-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c8039-107">Remarks</span></span>  
 <span data-ttu-id="c8039-108">El valor de `assemblyId` no es válido para una solicitud de información hasta la [AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) se llama al método.</span><span class="sxs-lookup"><span data-stu-id="c8039-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8039-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8039-109">Requirements</span></span>  
 <span data-ttu-id="c8039-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8039-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8039-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c8039-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c8039-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8039-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8039-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8039-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8039-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8039-114">See also</span></span>

- [<span data-ttu-id="c8039-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c8039-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
