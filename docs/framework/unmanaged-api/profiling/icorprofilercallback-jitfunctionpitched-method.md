---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91bc626e2c75cd7eb2eafad0fc26d343e5b278e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530737"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="9e81d-102">ICorProfilerCallback::JITFunctionPitched (Método)</span><span class="sxs-lookup"><span data-stu-id="9e81d-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="9e81d-103">Notifica al generador de perfiles que una función que ha sido just-in-time (JIT)-compilado se ha quitado de la memoria.</span><span class="sxs-lookup"><span data-stu-id="9e81d-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e81d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9e81d-104">Syntax</span></span>  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9e81d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9e81d-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="9e81d-106">[in] El identificador de la función que se ha quitado.</span><span class="sxs-lookup"><span data-stu-id="9e81d-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e81d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9e81d-107">Remarks</span></span>  
 <span data-ttu-id="9e81d-108">Si se llama a la función quitada, el generador de perfiles recibirá nuevos eventos de compilación JIT cuando se vuelve a compilar la función.</span><span class="sxs-lookup"><span data-stu-id="9e81d-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="9e81d-109">Actualmente, el compilador JIT de common language runtime (CLR) no quita las funciones de la memoria, por lo que esta devolución de llamada no se utiliza actualmente y no se recibirán el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="9e81d-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="9e81d-110">El valor de `functionId` no es válido hasta que se vuelve a compilar la función.</span><span class="sxs-lookup"><span data-stu-id="9e81d-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="9e81d-111">Cuando se vuelve a compilar la función, el mismo `functionId` se usará el valor.</span><span class="sxs-lookup"><span data-stu-id="9e81d-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e81d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9e81d-112">Requirements</span></span>  
 <span data-ttu-id="9e81d-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e81d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e81d-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9e81d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9e81d-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e81d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e81d-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e81d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e81d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e81d-117">See also</span></span>
- [<span data-ttu-id="9e81d-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9e81d-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
