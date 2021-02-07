---
description: 'Más información sobre: ICorProfilerCallback:: Moduleloadstarted ((método)'
title: ICorProfilerCallback::ModuleLoadStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadStarted
helpviewer_keywords:
- ModuleLoadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadStarted method [.NET Framework profiling]
ms.assetid: 9cd2fe75-408a-400f-a6b1-9979624a2fe2
topic_type:
- apiref
ms.openlocfilehash: e8d15bece7baf82f69162663da00d331c7904837
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745273"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="cb2b8-103">ICorProfilerCallback::ModuleLoadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="cb2b8-103">ICorProfilerCallback::ModuleLoadStarted Method</span></span>

<span data-ttu-id="cb2b8-104">Notifica al generador de perfiles que se está cargando un módulo.</span><span class="sxs-lookup"><span data-stu-id="cb2b8-104">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb2b8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb2b8-105">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb2b8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cb2b8-106">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="cb2b8-107">de IDENTIFICADOR del módulo que se está cargando.</span><span class="sxs-lookup"><span data-stu-id="cb2b8-107">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb2b8-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cb2b8-108">Remarks</span></span>  

 <span data-ttu-id="cb2b8-109">El valor de `moduleId` no es válido para una solicitud de información hasta que se llama al método [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cb2b8-109">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb2b8-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb2b8-110">Requirements</span></span>  

 <span data-ttu-id="cb2b8-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb2b8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb2b8-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cb2b8-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cb2b8-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb2b8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb2b8-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb2b8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb2b8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb2b8-115">See also</span></span>

- [<span data-ttu-id="cb2b8-116">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb2b8-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
