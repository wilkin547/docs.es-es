---
title: ICorProfilerCallback4::GetReJITParameters (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.GetReJITParameters
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::GetReJITParameters
helpviewer_keywords:
- ICorProfilerCallback4::GetReJITParameters method [.NET Framework profiling]
- GetReJITParameters method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 0e9bfe07-9f20-498c-b568-9017c8f6056c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ca176be93b92e44228d9b4063e87a62263e83e04
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184878"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a><span data-ttu-id="c71f3-102">ICorProfilerCallback4::GetReJITParameters (Método)</span><span class="sxs-lookup"><span data-stu-id="c71f3-102">ICorProfilerCallback4::GetReJITParameters Method</span></span>
<span data-ttu-id="c71f3-103">Permite al analizador de código establecer las marcas de generación de código alternativa para un nuevo cuerpo de método ha vuelto a compilar.</span><span class="sxs-lookup"><span data-stu-id="c71f3-103">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c71f3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c71f3-104">Syntax</span></span>  
  
```  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c71f3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c71f3-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="c71f3-106">[in] El módulo que contiene el método para que el CLR debe parámetros de recompilación JIT.</span><span class="sxs-lookup"><span data-stu-id="c71f3-106">[in] The module that contains the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `methodId`  
 <span data-ttu-id="c71f3-107">[in] El `MethodDef` del método para que el CLR debe parámetros de recompilación JIT.</span><span class="sxs-lookup"><span data-stu-id="c71f3-107">[in] The `MethodDef` of the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `pFunctionControl`  
 <span data-ttu-id="c71f3-108">[in] Un puntero a un [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interfaz que puede usar el generador de perfiles para proporcionar información de recompilación JIT del método que se están volviendo a compilar.</span><span class="sxs-lookup"><span data-stu-id="c71f3-108">[in] A pointer to an [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interface that the profiler can use to provide JIT recompilation information for the method being recompiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c71f3-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c71f3-109">Remarks</span></span>  
 <span data-ttu-id="c71f3-110">Los problemas CLR un `GetReJITParameters` devolución de llamada para que el generador de perfiles puede especificar los parámetros para volver a compilar un método determinado.</span><span class="sxs-lookup"><span data-stu-id="c71f3-110">The CLR issues a `GetReJITParameters` callback so that the profiler can specify the parameters for recompiling a given method.</span></span> <span data-ttu-id="c71f3-111">El `GetReJITParameters` devolución de llamada se emite solo una vez por cada función, los parámetros proporcionados por el generador de perfiles se aplican a todas las instancias de esa función.</span><span class="sxs-lookup"><span data-stu-id="c71f3-111">The `GetReJITParameters` callback is issued only once per function; the parameters supplied by the profiler apply to all instances of that function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c71f3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c71f3-112">Requirements</span></span>  
 <span data-ttu-id="c71f3-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c71f3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c71f3-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c71f3-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c71f3-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c71f3-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c71f3-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c71f3-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c71f3-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c71f3-117">See also</span></span>

- [<span data-ttu-id="c71f3-118">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c71f3-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="c71f3-119">ICorProfilerCallback4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c71f3-119">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="c71f3-120">Método JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="c71f3-120">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="c71f3-121">Método ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="c71f3-121">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
