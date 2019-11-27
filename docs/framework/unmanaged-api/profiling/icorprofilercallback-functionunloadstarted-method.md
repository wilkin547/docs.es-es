---
title: ICorProfilerCallback::FunctionUnloadStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.FunctionUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type:
- apiref
ms.openlocfilehash: f57a3ed70267de65daed85305ad7d623b4ca0337
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448020"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="a09f1-102">ICorProfilerCallback::FunctionUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="a09f1-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="a09f1-103">Notifica al generador de perfiles que el tiempo de ejecución ha empezado a descargar una función.</span><span class="sxs-lookup"><span data-stu-id="a09f1-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a09f1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a09f1-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="a09f1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a09f1-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a09f1-106">de IDENTIFICADOR de la función que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="a09f1-106">[in] The ID of the function that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a09f1-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a09f1-107">Remarks</span></span>  
 <span data-ttu-id="a09f1-108">El valor del parámetro `functionId` ya no es válido después de que este método vuelva al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a09f1-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a09f1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a09f1-109">Requirements</span></span>  
 <span data-ttu-id="a09f1-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a09f1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a09f1-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a09f1-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a09f1-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a09f1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a09f1-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a09f1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a09f1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a09f1-114">See also</span></span>

- [<span data-ttu-id="a09f1-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a09f1-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
