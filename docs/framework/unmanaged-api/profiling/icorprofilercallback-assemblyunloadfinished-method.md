---
title: ICorProfilerCallback::AssemblyUnloadFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b9ee87c926d2377ff8eef53f930fe75251b28ceb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137779"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="66038-102">ICorProfilerCallback::AssemblyUnloadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="66038-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="66038-103">Notifica al generador de perfiles que se ha descargado un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="66038-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66038-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66038-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66038-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="66038-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="66038-106">[in] Identifica el ensamblado que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="66038-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="66038-107">[in] Un HRESULT que indica si el ensamblado se descargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="66038-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66038-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="66038-108">Remarks</span></span>  
 <span data-ttu-id="66038-109">El valor de `assemblyId` no es válido para una solicitud de información después de la [AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) devuelve del método.</span><span class="sxs-lookup"><span data-stu-id="66038-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="66038-110">Algunas partes de la descarga del ensamblado podrían continuar después de la `AssemblyUnloadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="66038-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="66038-111">Un error HRESULT en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="66038-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="66038-112">Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de la descarga del ensamblado se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="66038-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66038-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66038-113">Requirements</span></span>  
 <span data-ttu-id="66038-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66038-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66038-115">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="66038-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="66038-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66038-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="66038-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="66038-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="66038-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="66038-118">See also</span></span>

- [<span data-ttu-id="66038-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="66038-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
