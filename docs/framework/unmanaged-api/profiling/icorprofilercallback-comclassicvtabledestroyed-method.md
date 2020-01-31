---
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
ms.openlocfilehash: 98d5dcf3b691f16f63390851e207f518bf26ab11
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866525"
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a><span data-ttu-id="b3622-102">ICorProfilerCallback::COMClassicVTableDestroyed (Método)</span><span class="sxs-lookup"><span data-stu-id="b3622-102">ICorProfilerCallback::COMClassicVTableDestroyed Method</span></span>
<span data-ttu-id="b3622-103">Notifica al generador de perfiles que se está destruyendo una vtable de interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="b3622-103">Notifies the profiler that a COM interop vtable is being destroyed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3622-104">Es probable que esta devolución de llamada nunca se produzca, porque la destrucción de vtables se produce muy cerca del cierre.</span><span class="sxs-lookup"><span data-stu-id="b3622-104">This callback is likely never to occur, because the destruction of vtables occurs very close to shutdown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3622-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b3622-105">Syntax</span></span>  
  
```cpp  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3622-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="b3622-106">Parameters</span></span>

- `wrappedClassId`

  <span data-ttu-id="b3622-107">\[en] identificador de la clase para la que se creó esta vtable.</span><span class="sxs-lookup"><span data-stu-id="b3622-107">\[in] The ID of the class for which this vtable was created.</span></span>

- `implementedIID`

  <span data-ttu-id="b3622-108">\[en] identificador de la interfaz implementada por la clase.</span><span class="sxs-lookup"><span data-stu-id="b3622-108">\[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="b3622-109">Este valor puede ser NULL si la interfaz solo es interna.</span><span class="sxs-lookup"><span data-stu-id="b3622-109">This value may be NULL if the interface is internal only.</span></span>

- `pVTable`

  <span data-ttu-id="b3622-110">\[en] un puntero al inicio de vtable.</span><span class="sxs-lookup"><span data-stu-id="b3622-110">\[in] A pointer to the start of the vtable.</span></span>

## <a name="remarks"></a><span data-ttu-id="b3622-111">Notas</span><span class="sxs-lookup"><span data-stu-id="b3622-111">Remarks</span></span>  
 <span data-ttu-id="b3622-112">El generador de perfiles no debe bloquear en su implementación de este método porque la pila puede no estar en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="b3622-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="b3622-113">Si el generador de perfiles se bloquea aquí y se intenta la recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.</span><span class="sxs-lookup"><span data-stu-id="b3622-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="b3622-114">La implementación del generador de perfiles de este método no debe llamar a código administrado ni provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="b3622-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3622-115">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="b3622-115">Requirements</span></span>  
 <span data-ttu-id="b3622-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3622-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3622-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b3622-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b3622-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3622-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3622-119">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3622-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3622-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3622-120">See also</span></span>

- [<span data-ttu-id="b3622-121">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b3622-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="b3622-122">COMClassicVTableCreated (método)</span><span class="sxs-lookup"><span data-stu-id="b3622-122">COMClassicVTableCreated Method</span></span>](icorprofilercallback-comclassicvtablecreated-method.md)
