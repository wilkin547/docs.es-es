---
title: ICorProfilerCallback::COMClassicVTableCreated (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.COMClassicVTableCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableCreated
helpviewer_keywords:
- COMClassicVTableCreated method [.NET Framework profiling]
- ICorProfilerCallback::COMClassicVTableCreated method [.NET Framework profiling]
ms.assetid: 6e1834ab-c359-498a-b10b-984ae23cdda4
topic_type:
- apiref
ms.openlocfilehash: 6c9ec6af90cc47c3c01621563a9813789c25aa1d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500343"
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="59b20-102">ICorProfilerCallback::COMClassicVTableCreated (Método)</span><span class="sxs-lookup"><span data-stu-id="59b20-102">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>
<span data-ttu-id="59b20-103">Notifica al generador de perfiles que se ha creado una vtable de interoperabilidad COM para el IID y la clase especificados.</span><span class="sxs-lookup"><span data-stu-id="59b20-103">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59b20-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59b20-104">Syntax</span></span>  
  
```cpp  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59b20-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="59b20-105">Parameters</span></span>

- `wrappedClasId`

  <span data-ttu-id="59b20-106">\[in] identificador de la clase para la que se ha creado la tabla vtable.</span><span class="sxs-lookup"><span data-stu-id="59b20-106">\[in] The ID of the class for which the vtable has been created.</span></span>

- `implementedIID`

  <span data-ttu-id="59b20-107">\[in] identificador de la interfaz implementada por la clase.</span><span class="sxs-lookup"><span data-stu-id="59b20-107">\[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="59b20-108">Este valor puede ser NULL si la interfaz solo es interna.</span><span class="sxs-lookup"><span data-stu-id="59b20-108">This value may be NULL if the interface is internal only.</span></span>

- `pVTable`

  <span data-ttu-id="59b20-109">\[in] un puntero al inicio de vtable.</span><span class="sxs-lookup"><span data-stu-id="59b20-109">\[in] A pointer to the start of the vtable.</span></span>

- `cSlots`

  <span data-ttu-id="59b20-110">\[en] el número de ranuras que se encuentran en la tabla vtable.</span><span class="sxs-lookup"><span data-stu-id="59b20-110">\[in] The number of slots that are in the vtable.</span></span>

## <a name="remarks"></a><span data-ttu-id="59b20-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="59b20-111">Remarks</span></span>  
 <span data-ttu-id="59b20-112">El generador de perfiles no debe bloquear en su implementación de este método porque la pila puede no estar en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="59b20-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="59b20-113">Si el generador de perfiles se bloquea aquí y se intenta la recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.</span><span class="sxs-lookup"><span data-stu-id="59b20-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="59b20-114">La implementación del generador de perfiles de este método no debe llamar a código administrado ni provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="59b20-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59b20-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59b20-115">Requirements</span></span>  
 <span data-ttu-id="59b20-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59b20-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59b20-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="59b20-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="59b20-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59b20-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59b20-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59b20-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59b20-120">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="59b20-120">See also</span></span>

- [<span data-ttu-id="59b20-121">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="59b20-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="59b20-122">Método COMClassicVTableDestroyed</span><span class="sxs-lookup"><span data-stu-id="59b20-122">COMClassicVTableDestroyed Method</span></span>](icorprofilercallback-comclassicvtabledestroyed-method.md)
