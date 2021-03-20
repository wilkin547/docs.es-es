---
description: 'Más información sobre: ICorProfilerCallback:: Comclassicvtablecreated ((método)'
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
ms.openlocfilehash: 04ba37b9c1307539c9fdf299f4667e7026d571be
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760579"
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="014d4-103">ICorProfilerCallback::COMClassicVTableCreated (Método)</span><span class="sxs-lookup"><span data-stu-id="014d4-103">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>

<span data-ttu-id="014d4-104">Notifica al generador de perfiles que se ha creado una vtable de interoperabilidad COM para el IID y la clase especificados.</span><span class="sxs-lookup"><span data-stu-id="014d4-104">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="014d4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="014d4-105">Syntax</span></span>  
  
```cpp  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
## <a name="parameters"></a><span data-ttu-id="014d4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="014d4-106">Parameters</span></span>

<span data-ttu-id="014d4-107">`wrappedClasId` de IDENTIFICADOR de la clase para la que se ha creado la tabla vtable.</span><span class="sxs-lookup"><span data-stu-id="014d4-107">`wrappedClasId` [in] The ID of the class for which the vtable has been created.</span></span>

<span data-ttu-id="014d4-108">`implementedIID` de IDENTIFICADOR de la interfaz implementada por la clase.</span><span class="sxs-lookup"><span data-stu-id="014d4-108">`implementedIID` [in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="014d4-109">Este valor puede ser NULL si la interfaz solo es interna.</span><span class="sxs-lookup"><span data-stu-id="014d4-109">This value may be NULL if the interface is internal only.</span></span>

<span data-ttu-id="014d4-110">`pVTable` de Puntero al principio de la tabla vtable.</span><span class="sxs-lookup"><span data-stu-id="014d4-110">`pVTable` [in] A pointer to the start of the vtable.</span></span>

<span data-ttu-id="014d4-111">`cSlots` de Número de ranuras que se encuentran en la tabla vtable.</span><span class="sxs-lookup"><span data-stu-id="014d4-111">`cSlots` [in] The number of slots that are in the vtable.</span></span>

## <a name="remarks"></a><span data-ttu-id="014d4-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="014d4-112">Remarks</span></span>  

 <span data-ttu-id="014d4-113">El generador de perfiles no debe bloquear en su implementación de este método porque la pila puede no estar en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="014d4-113">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="014d4-114">Si el generador de perfiles se bloquea aquí y se intenta la recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.</span><span class="sxs-lookup"><span data-stu-id="014d4-114">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="014d4-115">La implementación del generador de perfiles de este método no debe llamar a código administrado ni provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="014d4-115">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="014d4-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="014d4-116">Requirements</span></span>  

 <span data-ttu-id="014d4-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="014d4-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="014d4-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="014d4-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="014d4-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="014d4-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="014d4-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="014d4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="014d4-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="014d4-121">See also</span></span>

- [<span data-ttu-id="014d4-122">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="014d4-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="014d4-123">Método COMClassicVTableDestroyed</span><span class="sxs-lookup"><span data-stu-id="014d4-123">COMClassicVTableDestroyed Method</span></span>](icorprofilercallback-comclassicvtabledestroyed-method.md)
