---
title: "ICorProfilerCallback::JITFunctionPitched (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITFunctionPitched
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a5b14bc5735c83897e818ca2038455e0c6510e27
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="af1fb-102">ICorProfilerCallback::JITFunctionPitched (Método)</span><span class="sxs-lookup"><span data-stu-id="af1fb-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="af1fb-103">Notifica al generador de perfiles que una función que ha sido just-in-time (JIT)-compilado se ha quitado de la memoria.</span><span class="sxs-lookup"><span data-stu-id="af1fb-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af1fb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af1fb-104">Syntax</span></span>  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af1fb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="af1fb-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="af1fb-106">[in] El identificador de la función que se quitó.</span><span class="sxs-lookup"><span data-stu-id="af1fb-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af1fb-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="af1fb-107">Remarks</span></span>  
 <span data-ttu-id="af1fb-108">Si se llama a la función quitada, el generador de perfiles recibirá nuevos eventos de compilación JIT cuando se vuelve a compilar la función.</span><span class="sxs-lookup"><span data-stu-id="af1fb-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="af1fb-109">Actualmente, el compilador JIT de common language runtime (CLR) no quita funciones de la memoria, por lo que esta devolución de llamada no se utiliza actualmente y no se recibirán el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="af1fb-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="af1fb-110">El valor de `functionId` no es válido hasta que se vuelve a compilar la función.</span><span class="sxs-lookup"><span data-stu-id="af1fb-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="af1fb-111">Cuando se vuelve a compilar la función, el mismo `functionId` se usará el valor.</span><span class="sxs-lookup"><span data-stu-id="af1fb-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af1fb-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af1fb-112">Requirements</span></span>  
 <span data-ttu-id="af1fb-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af1fb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af1fb-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="af1fb-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="af1fb-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af1fb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af1fb-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af1fb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af1fb-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="af1fb-117">See Also</span></span>  
 [<span data-ttu-id="af1fb-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="af1fb-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
