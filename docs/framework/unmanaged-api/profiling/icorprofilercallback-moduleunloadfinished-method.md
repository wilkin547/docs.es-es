---
title: ICorProfilerCallback::ModuleUnloadFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadFinished
helpviewer_keywords:
- ModuleUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadFinished method [.NET Framework profiling]
ms.assetid: 185e3327-9f9c-44bc-8a5c-febea9a6bb5b
topic_type:
- apiref
ms.openlocfilehash: b13573d19ab4d8bb655c1e153530dc70173abe82
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866148"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="172fe-102">ICorProfilerCallback::ModuleUnloadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="172fe-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="172fe-103">Notifica al generador de perfiles que un módulo ha terminado de descargarse.</span><span class="sxs-lookup"><span data-stu-id="172fe-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="172fe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="172fe-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="172fe-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="172fe-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="172fe-106">de IDENTIFICADOR del módulo que se ha descargado.</span><span class="sxs-lookup"><span data-stu-id="172fe-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="172fe-107">de HRESULT que indica si el módulo se ha descargado correctamente.</span><span class="sxs-lookup"><span data-stu-id="172fe-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="172fe-108">Notas</span><span class="sxs-lookup"><span data-stu-id="172fe-108">Remarks</span></span>  
 <span data-ttu-id="172fe-109">El valor de `moduleId` no es válido para una solicitud de información después de que se devuelva el método [ICorProfilerCallback:: ModuleUnloadStarted (](icorprofilercallback-moduleunloadstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="172fe-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="172fe-110">Algunas partes de la descarga de la clase podrían continuar después de la devolución de llamada de `ModuleUnloadFinished`.</span><span class="sxs-lookup"><span data-stu-id="172fe-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="172fe-111">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="172fe-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="172fe-112">Sin embargo, un valor HRESULT correcto en `hrStatus` solo indica que la primera parte de la descarga del módulo se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="172fe-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="172fe-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="172fe-113">Requirements</span></span>  
 <span data-ttu-id="172fe-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="172fe-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="172fe-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="172fe-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="172fe-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="172fe-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="172fe-117">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="172fe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="172fe-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="172fe-118">See also</span></span>

- [<span data-ttu-id="172fe-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="172fe-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
