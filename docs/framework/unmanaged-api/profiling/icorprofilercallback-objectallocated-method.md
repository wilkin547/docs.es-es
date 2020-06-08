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
ms.openlocfilehash: 9a402b7dfc3ece9d38994ed897162fe0d81ff0b9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503307"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="a5a86-102">ICorProfilerCallback::ObjectAllocated (Método)</span><span class="sxs-lookup"><span data-stu-id="a5a86-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="a5a86-103">Notifica al generador de perfiles que se ha asignado memoria en el montón para un objeto.</span><span class="sxs-lookup"><span data-stu-id="a5a86-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5a86-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5a86-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5a86-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a5a86-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="a5a86-106">de IDENTIFICADOR del objeto para el que se asignó la memoria.</span><span class="sxs-lookup"><span data-stu-id="a5a86-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="a5a86-107">de IDENTIFICADOR de la clase de la que el objeto es una instancia de.</span><span class="sxs-lookup"><span data-stu-id="a5a86-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5a86-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a5a86-108">Remarks</span></span>  
 <span data-ttu-id="a5a86-109">`ObjectedAllocated`No se llama al método para las asignaciones de la pila o la memoria no administrada.</span><span class="sxs-lookup"><span data-stu-id="a5a86-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="a5a86-110">El `classId` parámetro puede hacer referencia a una clase de código administrado que todavía no se ha cargado.</span><span class="sxs-lookup"><span data-stu-id="a5a86-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="a5a86-111">El generador de perfiles recibirá una devolución de llamada de carga de clase para esa clase inmediatamente después de la `ObjectAllocated` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="a5a86-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5a86-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5a86-112">Requirements</span></span>  
 <span data-ttu-id="a5a86-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5a86-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5a86-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a5a86-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a5a86-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5a86-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5a86-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5a86-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5a86-117">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="a5a86-117">See also</span></span>

- [<span data-ttu-id="a5a86-118">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5a86-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="a5a86-119">Método ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="a5a86-119">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="a5a86-120">Método ClassLoadFinished</span><span class="sxs-lookup"><span data-stu-id="a5a86-120">ClassLoadFinished Method</span></span>](icorprofilercallback-classloadfinished-method.md)
