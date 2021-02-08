---
description: 'Más información sobre: ICorProfilerCallback4:: Getrejitparameters ((método)'
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
ms.openlocfilehash: f8dbf2c6ae80e41b8427fdaf0ef617a83138bb14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788766"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a><span data-ttu-id="983f6-103">ICorProfilerCallback4::GetReJITParameters (Método)</span><span class="sxs-lookup"><span data-stu-id="983f6-103">ICorProfilerCallback4::GetReJITParameters Method</span></span>

<span data-ttu-id="983f6-104">Permite que el generador de perfiles de código establezca marcas de generación de código alternativas para un nuevo cuerpo de método recompilado.</span><span class="sxs-lookup"><span data-stu-id="983f6-104">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="983f6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="983f6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a><span data-ttu-id="983f6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="983f6-106">Parameters</span></span>  

 `moduleID`  
 <span data-ttu-id="983f6-107">de Módulo que contiene el método para el que CLR necesita parámetros de recompilación JIT.</span><span class="sxs-lookup"><span data-stu-id="983f6-107">[in] The module that contains the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `methodId`  
 <span data-ttu-id="983f6-108">de `MethodDef` Del método para el que CLR necesita parámetros de recompilación JIT.</span><span class="sxs-lookup"><span data-stu-id="983f6-108">[in] The `MethodDef` of the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `pFunctionControl`  
 <span data-ttu-id="983f6-109">de Puntero a una interfaz [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) que el generador de perfiles puede usar para proporcionar información de recompilación JIT para el método que se va a volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="983f6-109">[in] A pointer to an [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) interface that the profiler can use to provide JIT recompilation information for the method being recompiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="983f6-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="983f6-110">Remarks</span></span>  

 <span data-ttu-id="983f6-111">CLR emite una `GetReJITParameters` devolución de llamada para que el generador de perfiles pueda especificar los parámetros para volver a compilar un método determinado.</span><span class="sxs-lookup"><span data-stu-id="983f6-111">The CLR issues a `GetReJITParameters` callback so that the profiler can specify the parameters for recompiling a given method.</span></span> <span data-ttu-id="983f6-112">La `GetReJITParameters` devolución de llamada se emite solo una vez por función; los parámetros proporcionados por el generador de perfiles se aplican a todas las instancias de esa función.</span><span class="sxs-lookup"><span data-stu-id="983f6-112">The `GetReJITParameters` callback is issued only once per function; the parameters supplied by the profiler apply to all instances of that function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="983f6-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="983f6-113">Requirements</span></span>  

 <span data-ttu-id="983f6-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="983f6-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="983f6-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="983f6-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="983f6-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="983f6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="983f6-117">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="983f6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="983f6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="983f6-118">See also</span></span>

- [<span data-ttu-id="983f6-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="983f6-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="983f6-120">ICorProfilerCallback4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="983f6-120">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="983f6-121">Método JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="983f6-121">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="983f6-122">Método ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="983f6-122">ReJITCompilationStarted Method</span></span>](icorprofilercallback4-rejitcompilationstarted-method.md)
