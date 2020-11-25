---
title: ICorProfilerInfo3::SetFunctionIDMapper2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetFunctionIDMapper2 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetFunctionIDMapper2
helpviewer_keywords:
- SetFunctionIDMapper2 method [.NET Framework profiling]
- ICorProfilerInfo3::SetFunctionIDMapper2 method [.NET Framework profiling]
ms.assetid: 8cdb1188-952a-4ba8-9f05-bfebc18cdd29
topic_type:
- apiref
ms.openlocfilehash: 26c26cf204f1a2743f46cfcfdfadbf2c3e3df38e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721574"
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a><span data-ttu-id="047c9-102">ICorProfilerInfo3::SetFunctionIDMapper2 (Método)</span><span class="sxs-lookup"><span data-stu-id="047c9-102">ICorProfilerInfo3::SetFunctionIDMapper2 Method</span></span>

<span data-ttu-id="047c9-103">Especifica la función implementada por el generador de perfiles a la que se llamará para asignar los valores `FunctionID` a valores alternativos, que se pasan los enlaces de entrada y salida de función del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="047c9-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span> <span data-ttu-id="047c9-104">Este método extiende el método [ICorProfilerInfo:: setfunctionidmapper (](icorprofilerinfo-setfunctionidmapper-method.md) con un parámetro de datos adicional, que los perfiles pueden utilizar para eliminar la ambigüedad entre los tiempos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="047c9-104">This method extends the [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) method with an additional data parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="047c9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="047c9-105">Syntax</span></span>  
  
```cpp  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="047c9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="047c9-106">Parameters</span></span>  

 `pFunc`  
 <span data-ttu-id="047c9-107">de Puntero a una implementación de [functionidmapper2 (](functionidmapper2-function.md) a la que se llamará para asignar los `FunctionID` valores a sus valores alternativos.</span><span class="sxs-lookup"><span data-stu-id="047c9-107">[in] A pointer to a [FunctionIDMapper2](functionidmapper2-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
 `clientData`  
 <span data-ttu-id="047c9-108">de Puntero que se pasa a cada llamada de función [functionidmapper2 (](functionidmapper2-function.md) realizada por el tiempo de ejecución actual.</span><span class="sxs-lookup"><span data-stu-id="047c9-108">[in] A pointer that is passed to every [FunctionIDMapper2](functionidmapper2-function.md) function call made by the current runtime.</span></span> <span data-ttu-id="047c9-109">El generador de perfiles puede utilizar esta información para eliminar la ambigüedad entre los tiempos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="047c9-109">The profiler can use this information to disambiguate among runtimes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="047c9-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="047c9-110">Return Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="047c9-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="047c9-111">Remarks</span></span>  

 <span data-ttu-id="047c9-112">Las alternativas para los valores de FunctionID se pasarán a los enlaces de entrada y salida de función del generador de perfiles ([FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)y [FunctionTailcall3](functiontailcall3-function.md); o [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)y [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)) especificados por el método [SetEnterLeaveFunctionHooks3 (](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) o [SetEnterLeaveFunctionHooks3WithInfo (](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) .</span><span class="sxs-lookup"><span data-stu-id="047c9-112">The alternatives for the FunctionID values will be passed to the profiler's function entry/exit hooks ([FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md); or [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)) that are specified by the [SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) or [SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method.</span></span>  
  
 <span data-ttu-id="047c9-113">El `FunctionIDMapper2` método solo se puede establecer una vez; se recomienda establecerlo en la devolución de llamada [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="047c9-113">The `FunctionIDMapper2` method can be set only once; we recommend that you set it in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="047c9-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="047c9-114">Requirements</span></span>  

 <span data-ttu-id="047c9-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="047c9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="047c9-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="047c9-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="047c9-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="047c9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="047c9-118">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="047c9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="047c9-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="047c9-119">See also</span></span>

- [<span data-ttu-id="047c9-120">Setfunctionidmapper (</span><span class="sxs-lookup"><span data-stu-id="047c9-120">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="047c9-121">ICorProfilerInfo3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="047c9-121">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="047c9-122">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="047c9-122">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="047c9-123">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="047c9-123">Profiling</span></span>](index.md)
