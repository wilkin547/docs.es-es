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
ms.openlocfilehash: 2cee763674da7472ca48355e7eaba3b7dfb7adbe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730310"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a><span data-ttu-id="d798d-102">ICorProfilerCallback4::GetReJITParameters (Método)</span><span class="sxs-lookup"><span data-stu-id="d798d-102">ICorProfilerCallback4::GetReJITParameters Method</span></span>

<span data-ttu-id="d798d-103">Permite que el generador de perfiles de código establezca marcas de generación de código alternativas para un nuevo cuerpo de método recompilado.</span><span class="sxs-lookup"><span data-stu-id="d798d-103">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d798d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d798d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d798d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d798d-105">Parameters</span></span>  

 `moduleID`  
 <span data-ttu-id="d798d-106">de Módulo que contiene el método para el que CLR necesita parámetros de recompilación JIT.</span><span class="sxs-lookup"><span data-stu-id="d798d-106">[in] The module that contains the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `methodId`  
 <span data-ttu-id="d798d-107">de `MethodDef` Del método para el que CLR necesita parámetros de recompilación JIT.</span><span class="sxs-lookup"><span data-stu-id="d798d-107">[in] The `MethodDef` of the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `pFunctionControl`  
 <span data-ttu-id="d798d-108">de Puntero a una interfaz [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) que el generador de perfiles puede usar para proporcionar información de recompilación JIT para el método que se va a volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="d798d-108">[in] A pointer to an [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) interface that the profiler can use to provide JIT recompilation information for the method being recompiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d798d-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d798d-109">Remarks</span></span>  

 <span data-ttu-id="d798d-110">CLR emite una `GetReJITParameters` devolución de llamada para que el generador de perfiles pueda especificar los parámetros para volver a compilar un método determinado.</span><span class="sxs-lookup"><span data-stu-id="d798d-110">The CLR issues a `GetReJITParameters` callback so that the profiler can specify the parameters for recompiling a given method.</span></span> <span data-ttu-id="d798d-111">La `GetReJITParameters` devolución de llamada se emite solo una vez por función; los parámetros proporcionados por el generador de perfiles se aplican a todas las instancias de esa función.</span><span class="sxs-lookup"><span data-stu-id="d798d-111">The `GetReJITParameters` callback is issued only once per function; the parameters supplied by the profiler apply to all instances of that function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d798d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d798d-112">Requirements</span></span>  

 <span data-ttu-id="d798d-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d798d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d798d-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d798d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d798d-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d798d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d798d-116">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d798d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d798d-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d798d-117">See also</span></span>

- [<span data-ttu-id="d798d-118">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d798d-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="d798d-119">ICorProfilerCallback4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d798d-119">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="d798d-120">Método JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="d798d-120">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="d798d-121">Método ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="d798d-121">ReJITCompilationStarted Method</span></span>](icorprofilercallback4-rejitcompilationstarted-method.md)
