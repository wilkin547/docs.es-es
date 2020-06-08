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
ms.openlocfilehash: 527e48d02d5267d6ae41214686c2e8c997d85dca
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499550"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a><span data-ttu-id="6a024-102">ICorProfilerCallback4::GetReJITParameters (Método)</span><span class="sxs-lookup"><span data-stu-id="6a024-102">ICorProfilerCallback4::GetReJITParameters Method</span></span>
<span data-ttu-id="6a024-103">Permite que el generador de perfiles de código establezca marcas de generación de código alternativas para un nuevo cuerpo de método recompilado.</span><span class="sxs-lookup"><span data-stu-id="6a024-103">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a024-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a024-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a024-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6a024-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="6a024-106">de Módulo que contiene el método para el que CLR necesita parámetros de recompilación JIT.</span><span class="sxs-lookup"><span data-stu-id="6a024-106">[in] The module that contains the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `methodId`  
 <span data-ttu-id="6a024-107">de `MethodDef`Del método para el que CLR necesita parámetros de recompilación JIT.</span><span class="sxs-lookup"><span data-stu-id="6a024-107">[in] The `MethodDef` of the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `pFunctionControl`  
 <span data-ttu-id="6a024-108">de Puntero a una interfaz [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) que el generador de perfiles puede usar para proporcionar información de recompilación JIT para el método que se va a volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="6a024-108">[in] A pointer to an [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) interface that the profiler can use to provide JIT recompilation information for the method being recompiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a024-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6a024-109">Remarks</span></span>  
 <span data-ttu-id="6a024-110">CLR emite una `GetReJITParameters` devolución de llamada para que el generador de perfiles pueda especificar los parámetros para volver a compilar un método determinado.</span><span class="sxs-lookup"><span data-stu-id="6a024-110">The CLR issues a `GetReJITParameters` callback so that the profiler can specify the parameters for recompiling a given method.</span></span> <span data-ttu-id="6a024-111">La `GetReJITParameters` devolución de llamada se emite solo una vez por función; los parámetros proporcionados por el generador de perfiles se aplican a todas las instancias de esa función.</span><span class="sxs-lookup"><span data-stu-id="6a024-111">The `GetReJITParameters` callback is issued only once per function; the parameters supplied by the profiler apply to all instances of that function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a024-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6a024-112">Requirements</span></span>  
 <span data-ttu-id="6a024-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a024-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a024-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6a024-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6a024-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a024-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a024-116">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a024-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a024-117">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="6a024-117">See also</span></span>

- [<span data-ttu-id="6a024-118">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6a024-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="6a024-119">ICorProfilerCallback4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6a024-119">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="6a024-120">Método JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="6a024-120">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="6a024-121">Método ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="6a024-121">ReJITCompilationStarted Method</span></span>](icorprofilercallback4-rejitcompilationstarted-method.md)
