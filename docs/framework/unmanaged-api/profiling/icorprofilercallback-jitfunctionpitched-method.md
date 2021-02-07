---
description: 'Más información sobre: ICorProfilerCallback:: Jitfunctionpitched ((método)'
title: ICorProfilerCallback::JITFunctionPitched (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
ms.openlocfilehash: 11729de2188fe2f2cec7ec16ff7a5d1928cbd75d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705725"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="fc56b-103">ICorProfilerCallback::JITFunctionPitched (Método)</span><span class="sxs-lookup"><span data-stu-id="fc56b-103">ICorProfilerCallback::JITFunctionPitched Method</span></span>

<span data-ttu-id="fc56b-104">Notifica al generador de perfiles que se ha quitado de la memoria una función que se ha compilado Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="fc56b-104">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc56b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc56b-105">Syntax</span></span>  
  
```cpp  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc56b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fc56b-106">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="fc56b-107">de IDENTIFICADOR de la función que se ha quitado.</span><span class="sxs-lookup"><span data-stu-id="fc56b-107">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc56b-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fc56b-108">Remarks</span></span>  

 <span data-ttu-id="fc56b-109">Si se llama a la función que se quita, el generador de perfiles recibirá nuevos eventos de compilación JIT cuando se vuelva a compilar la función.</span><span class="sxs-lookup"><span data-stu-id="fc56b-109">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="fc56b-110">Actualmente, el compilador JIT de Common Language Runtime (CLR) no quita funciones de la memoria, por lo que esta devolución de llamada no se utiliza actualmente y el generador de perfiles no las recibirá.</span><span class="sxs-lookup"><span data-stu-id="fc56b-110">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="fc56b-111">El valor de `functionId` no es válido hasta que se vuelva a compilar la función.</span><span class="sxs-lookup"><span data-stu-id="fc56b-111">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="fc56b-112">Cuando se vuelva a compilar la función, se usará el mismo `functionId` valor.</span><span class="sxs-lookup"><span data-stu-id="fc56b-112">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc56b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc56b-113">Requirements</span></span>  

 <span data-ttu-id="fc56b-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc56b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc56b-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fc56b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fc56b-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc56b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc56b-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc56b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc56b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc56b-118">See also</span></span>

- [<span data-ttu-id="fc56b-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc56b-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
