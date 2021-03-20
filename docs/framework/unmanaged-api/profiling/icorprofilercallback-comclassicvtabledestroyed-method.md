---
description: 'Más información sobre: ICorProfilerCallback:: Comclassicvtabledestroyed ((método)'
title: ICorProfilerCallback::COMClassicVTableDestroyed (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.COMClassicVTableDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed
helpviewer_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed method [.NET Framework profiling]
- COMClassicVTableDestroyed method [.NET Framework profiling]
ms.assetid: 29da20ca-bf39-4356-8099-d9c3ac3423a9
topic_type:
- apiref
ms.openlocfilehash: e8ed6be2519a9f8959ac4f59313f73f13d6c569b
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760566"
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a><span data-ttu-id="532c7-103">ICorProfilerCallback::COMClassicVTableDestroyed (Método)</span><span class="sxs-lookup"><span data-stu-id="532c7-103">ICorProfilerCallback::COMClassicVTableDestroyed Method</span></span>

<span data-ttu-id="532c7-104">Notifica al generador de perfiles que se está destruyendo una vtable de interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="532c7-104">Notifies the profiler that a COM interop vtable is being destroyed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="532c7-105">Es probable que esta devolución de llamada nunca se produzca, porque la destrucción de vtables se produce muy cerca del cierre.</span><span class="sxs-lookup"><span data-stu-id="532c7-105">This callback is likely never to occur, because the destruction of vtables occurs very close to shutdown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="532c7-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="532c7-106">Syntax</span></span>  
  
```cpp  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="532c7-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="532c7-107">Parameters</span></span>

<span data-ttu-id="532c7-108">`wrappedClassId` de IDENTIFICADOR de la clase para la que se creó esta vtable.</span><span class="sxs-lookup"><span data-stu-id="532c7-108">`wrappedClassId` [in] The ID of the class for which this vtable was created.</span></span>

<span data-ttu-id="532c7-109">`implementedIID` de IDENTIFICADOR de la interfaz implementada por la clase.</span><span class="sxs-lookup"><span data-stu-id="532c7-109">`implementedIID` [in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="532c7-110">Este valor puede ser NULL si la interfaz solo es interna.</span><span class="sxs-lookup"><span data-stu-id="532c7-110">This value may be NULL if the interface is internal only.</span></span>

<span data-ttu-id="532c7-111">`pVTable` de Puntero al principio de la tabla vtable.</span><span class="sxs-lookup"><span data-stu-id="532c7-111">`pVTable` [in] A pointer to the start of the vtable.</span></span>

## <a name="remarks"></a><span data-ttu-id="532c7-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="532c7-112">Remarks</span></span>  

 <span data-ttu-id="532c7-113">El generador de perfiles no debe bloquear en su implementación de este método porque la pila puede no estar en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="532c7-113">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="532c7-114">Si el generador de perfiles se bloquea aquí y se intenta la recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.</span><span class="sxs-lookup"><span data-stu-id="532c7-114">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="532c7-115">La implementación del generador de perfiles de este método no debe llamar a código administrado ni provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="532c7-115">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="532c7-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="532c7-116">Requirements</span></span>  

 <span data-ttu-id="532c7-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="532c7-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="532c7-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="532c7-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="532c7-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="532c7-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="532c7-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="532c7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="532c7-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="532c7-121">See also</span></span>

- [<span data-ttu-id="532c7-122">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="532c7-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="532c7-123">Método COMClassicVTableCreated</span><span class="sxs-lookup"><span data-stu-id="532c7-123">COMClassicVTableCreated Method</span></span>](icorprofilercallback-comclassicvtablecreated-method.md)
