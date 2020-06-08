---
title: ICorProfilerInfo::SetFunctionIDMapper (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetFunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetFunctionIDMapper
helpviewer_keywords:
- ICorProfilerInfo::SetFunctionIDMapper method [.NET Framework profiling]
- SetFunctionIDMapper method [.NET Framework profiling]
ms.assetid: 1a6e5dae-d366-4497-9c02-7b5b1f43f9ec
topic_type:
- apiref
ms.openlocfilehash: 5272c5bf256f6e21a83470db094ab79317932018
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497483"
---
# <a name="icorprofilerinfosetfunctionidmapper-method"></a><span data-ttu-id="0afc9-102">ICorProfilerInfo::SetFunctionIDMapper (Método)</span><span class="sxs-lookup"><span data-stu-id="0afc9-102">ICorProfilerInfo::SetFunctionIDMapper Method</span></span>
<span data-ttu-id="0afc9-103">Especifica la función implementada por el generador de perfiles a la que se llamará para asignar los valores `FunctionID` a valores alternativos, que se pasan los enlaces de entrada y salida de función del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="0afc9-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0afc9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0afc9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFunctionIDMapper (  
    [in] FunctionIDMapper *pFunc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0afc9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0afc9-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="0afc9-106">de Puntero a la implementación de [FunctionIDMapper](functionidmapper-function.md) a la que se llamará para asignar los `FunctionID` valores a sus valores alternativos.</span><span class="sxs-lookup"><span data-stu-id="0afc9-106">[in] A pointer to the [FunctionIDMapper](functionidmapper-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0afc9-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0afc9-107">Remarks</span></span>  
 <span data-ttu-id="0afc9-108">Las alternativas para los `FunctionID` valores se pasarán a los enlaces de entrada y salida de función del generador de perfiles ([FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)y [FunctionTailcall2](functiontailcall2-function.md)) especificados por el método [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2 (](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0afc9-108">The alternatives for the `FunctionID` values will be passed to the profiler's function entry/exit hooks ([FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md)) that are specified by the [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) method.</span></span>  
  
 <span data-ttu-id="0afc9-109">`FunctionIDMapper`Solo se puede establecer una vez y se recomienda establecerlo en la devolución de llamada [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0afc9-109">The `FunctionIDMapper` can be set only once and it is recommended that you set it in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0afc9-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0afc9-110">Requirements</span></span>  
 <span data-ttu-id="0afc9-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0afc9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0afc9-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0afc9-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0afc9-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0afc9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0afc9-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0afc9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0afc9-115">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="0afc9-115">See also</span></span>

- [<span data-ttu-id="0afc9-116">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0afc9-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
