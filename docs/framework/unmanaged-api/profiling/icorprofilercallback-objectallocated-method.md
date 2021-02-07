---
description: 'Más información acerca de: ICorProfilerCallback:: ObjectAllocated (método)'
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
ms.openlocfilehash: 58b58aeb4bb88d0df32cebc32440317a4d23632d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745169"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="7a51a-103">ICorProfilerCallback::ObjectAllocated (Método)</span><span class="sxs-lookup"><span data-stu-id="7a51a-103">ICorProfilerCallback::ObjectAllocated Method</span></span>

<span data-ttu-id="7a51a-104">Notifica al generador de perfiles que se ha asignado memoria en el montón para un objeto.</span><span class="sxs-lookup"><span data-stu-id="7a51a-104">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a51a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a51a-105">Syntax</span></span>  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a51a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7a51a-106">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="7a51a-107">de IDENTIFICADOR del objeto para el que se asignó la memoria.</span><span class="sxs-lookup"><span data-stu-id="7a51a-107">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="7a51a-108">de IDENTIFICADOR de la clase de la que el objeto es una instancia de.</span><span class="sxs-lookup"><span data-stu-id="7a51a-108">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a51a-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7a51a-109">Remarks</span></span>  

 <span data-ttu-id="7a51a-110">`ObjectedAllocated`No se llama al método para las asignaciones de la pila o la memoria no administrada.</span><span class="sxs-lookup"><span data-stu-id="7a51a-110">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="7a51a-111">El `classId` parámetro puede hacer referencia a una clase de código administrado que todavía no se ha cargado.</span><span class="sxs-lookup"><span data-stu-id="7a51a-111">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="7a51a-112">El generador de perfiles recibirá una devolución de llamada de carga de clase para esa clase inmediatamente después de la `ObjectAllocated` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="7a51a-112">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a51a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7a51a-113">Requirements</span></span>  

 <span data-ttu-id="7a51a-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a51a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a51a-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7a51a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7a51a-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a51a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a51a-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a51a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a51a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a51a-118">See also</span></span>

- [<span data-ttu-id="7a51a-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7a51a-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="7a51a-120">Método ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="7a51a-120">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="7a51a-121">Método ClassLoadFinished</span><span class="sxs-lookup"><span data-stu-id="7a51a-121">ClassLoadFinished Method</span></span>](icorprofilercallback-classloadfinished-method.md)
