---
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
ms.openlocfilehash: 6fbd009b5785c5dc78df81e4411fbdf8e8eadf71
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730342"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="a3fd1-102">ICorProfilerCallback::ModuleLoadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="a3fd1-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>

<span data-ttu-id="a3fd1-103">Notifica al generador de perfiles que se está cargando un módulo.</span><span class="sxs-lookup"><span data-stu-id="a3fd1-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3fd1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3fd1-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3fd1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a3fd1-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="a3fd1-106">de IDENTIFICADOR del módulo que se está cargando.</span><span class="sxs-lookup"><span data-stu-id="a3fd1-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3fd1-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a3fd1-107">Remarks</span></span>  

 <span data-ttu-id="a3fd1-108">El valor de `moduleId` no es válido para una solicitud de información hasta que se llama al método [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a3fd1-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3fd1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3fd1-109">Requirements</span></span>  

 <span data-ttu-id="a3fd1-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3fd1-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3fd1-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a3fd1-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a3fd1-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3fd1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3fd1-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3fd1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3fd1-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3fd1-114">See also</span></span>

- [<span data-ttu-id="a3fd1-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3fd1-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
