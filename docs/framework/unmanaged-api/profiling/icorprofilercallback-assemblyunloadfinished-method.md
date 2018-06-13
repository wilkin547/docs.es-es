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
ms.openlocfilehash: 0d757a0455992bc82ead922a5fbf4c71f11a9085
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450874"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="53ffe-102">ICorProfilerCallback::AssemblyUnloadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="53ffe-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="53ffe-103">Notifica al generador de perfiles que se ha descargado un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="53ffe-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53ffe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53ffe-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53ffe-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="53ffe-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="53ffe-106">[in] Identifica el ensamblado que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="53ffe-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="53ffe-107">[in] Un valor HRESULT que indica si el ensamblado se descargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="53ffe-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53ffe-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="53ffe-108">Remarks</span></span>  
 <span data-ttu-id="53ffe-109">El valor de `assemblyId` no es válido para una solicitud de información después de la [ICorProfilerCallback:: AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) devuelve del método.</span><span class="sxs-lookup"><span data-stu-id="53ffe-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="53ffe-110">Algunas partes de la descarga del ensamblado podrían continuar después de la `AssemblyUnloadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="53ffe-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="53ffe-111">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="53ffe-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="53ffe-112">Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de la descarga del ensamblado se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="53ffe-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53ffe-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53ffe-113">Requirements</span></span>  
 <span data-ttu-id="53ffe-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53ffe-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53ffe-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="53ffe-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="53ffe-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53ffe-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53ffe-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53ffe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53ffe-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="53ffe-118">See Also</span></span>  
 [<span data-ttu-id="53ffe-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53ffe-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
