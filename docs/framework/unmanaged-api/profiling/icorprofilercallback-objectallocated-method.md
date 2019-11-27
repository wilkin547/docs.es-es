---
title: ICorProfilerCallback::ObjectAllocated (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectAllocated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type:
- apiref
ms.openlocfilehash: 66643bbb8dbc914b2e0e48a7f0c87630fe95e5d3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445855"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="24ceb-102">ICorProfilerCallback::ObjectAllocated (Método)</span><span class="sxs-lookup"><span data-stu-id="24ceb-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="24ceb-103">Notifica al generador de perfiles que se ha asignado memoria en el montón para un objeto.</span><span class="sxs-lookup"><span data-stu-id="24ceb-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24ceb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24ceb-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24ceb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="24ceb-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="24ceb-106">de IDENTIFICADOR del objeto para el que se asignó la memoria.</span><span class="sxs-lookup"><span data-stu-id="24ceb-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="24ceb-107">de IDENTIFICADOR de la clase de la que el objeto es una instancia de.</span><span class="sxs-lookup"><span data-stu-id="24ceb-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24ceb-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="24ceb-108">Remarks</span></span>  
 <span data-ttu-id="24ceb-109">No se llama al método `ObjectedAllocated` para las asignaciones de la pila o la memoria no administrada.</span><span class="sxs-lookup"><span data-stu-id="24ceb-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="24ceb-110">El parámetro `classId` puede hacer referencia a una clase de código administrado que todavía no se ha cargado.</span><span class="sxs-lookup"><span data-stu-id="24ceb-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="24ceb-111">El generador de perfiles recibirá una devolución de llamada de carga de clase para esa clase inmediatamente después de la devolución de llamada `ObjectAllocated`.</span><span class="sxs-lookup"><span data-stu-id="24ceb-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24ceb-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24ceb-112">Requirements</span></span>  
 <span data-ttu-id="24ceb-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24ceb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24ceb-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="24ceb-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="24ceb-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24ceb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24ceb-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24ceb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24ceb-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="24ceb-117">See also</span></span>

- [<span data-ttu-id="24ceb-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="24ceb-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="24ceb-119">ClassLoadStarted (método)</span><span class="sxs-lookup"><span data-stu-id="24ceb-119">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="24ceb-120">ClassLoadFinished (método)</span><span class="sxs-lookup"><span data-stu-id="24ceb-120">ClassLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
