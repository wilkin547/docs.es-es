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
ms.openlocfilehash: f628bd1270b529264c14236ca7cdc03bf7afd9d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454211"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a><span data-ttu-id="ea1a5-102">ICorProfilerCallback4::GetReJITParameters (Método)</span><span class="sxs-lookup"><span data-stu-id="ea1a5-102">ICorProfilerCallback4::GetReJITParameters Method</span></span>
<span data-ttu-id="ea1a5-103">Permite que el generador de perfiles de código establecer las marcas de generación de código alternativo para un nuevo cuerpo de método ha vuelto a compilar.</span><span class="sxs-lookup"><span data-stu-id="ea1a5-103">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea1a5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea1a5-104">Syntax</span></span>  
  
```  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea1a5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ea1a5-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="ea1a5-106">[in] El módulo que contiene el método para que el CLR debe parámetros de recompilación JIT.</span><span class="sxs-lookup"><span data-stu-id="ea1a5-106">[in] The module that contains the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `methodId`  
 <span data-ttu-id="ea1a5-107">[in] El `MethodDef` del método para que el CLR debe parámetros de recompilación JIT.</span><span class="sxs-lookup"><span data-stu-id="ea1a5-107">[in] The `MethodDef` of the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `pFunctionControl`  
 <span data-ttu-id="ea1a5-108">[in] Un puntero a un [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interfaz que puede usar el generador de perfiles para proporcionar información de recompilación JIT para el método que se va a volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="ea1a5-108">[in] A pointer to an [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interface that the profiler can use to provide JIT recompilation information for the method being recompiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea1a5-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ea1a5-109">Remarks</span></span>  
 <span data-ttu-id="ea1a5-110">Los problemas CLR un `GetReJITParameters` devolución de llamada para que el generador de perfiles puede especificar los parámetros para volver a compilar un método determinado.</span><span class="sxs-lookup"><span data-stu-id="ea1a5-110">The CLR issues a `GetReJITParameters` callback so that the profiler can specify the parameters for recompiling a given method.</span></span> <span data-ttu-id="ea1a5-111">El `GetReJITParameters` devolución de llamada se emite una sola vez por cada función; los parámetros proporcionados por el generador de perfiles se aplican a todas las instancias de esa función.</span><span class="sxs-lookup"><span data-stu-id="ea1a5-111">The `GetReJITParameters` callback is issued only once per function; the parameters supplied by the profiler apply to all instances of that function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea1a5-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea1a5-112">Requirements</span></span>  
 <span data-ttu-id="ea1a5-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea1a5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea1a5-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ea1a5-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ea1a5-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea1a5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea1a5-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea1a5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea1a5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea1a5-117">See Also</span></span>  
 [<span data-ttu-id="ea1a5-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ea1a5-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="ea1a5-119">ICorProfilerCallback4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ea1a5-119">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [<span data-ttu-id="ea1a5-120">JITCompilationStarted (método)</span><span class="sxs-lookup"><span data-stu-id="ea1a5-120">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)  
 [<span data-ttu-id="ea1a5-121">ReJITCompilationStarted (método)</span><span class="sxs-lookup"><span data-stu-id="ea1a5-121">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
