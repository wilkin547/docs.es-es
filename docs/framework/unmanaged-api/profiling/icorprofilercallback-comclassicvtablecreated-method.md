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
ms.openlocfilehash: 79be2572f52ec509d9551261074204bf62ad5388
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445052"
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="f3a2e-102">ICorProfilerCallback::COMClassicVTableCreated (Método)</span><span class="sxs-lookup"><span data-stu-id="f3a2e-102">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>
<span data-ttu-id="f3a2e-103">Notifica al generador de perfiles que se ha creado una vtable de interoperabilidad COM para el IID y la clase especificados.</span><span class="sxs-lookup"><span data-stu-id="f3a2e-103">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3a2e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3a2e-104">Syntax</span></span>  
  
```cpp  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3a2e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f3a2e-105">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="f3a2e-106">de IDENTIFICADOR de la clase para la que se ha creado la tabla vtable.</span><span class="sxs-lookup"><span data-stu-id="f3a2e-106">[in] The ID of the class for which the vtable has been created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="f3a2e-107">de IDENTIFICADOR de la interfaz implementada por la clase.</span><span class="sxs-lookup"><span data-stu-id="f3a2e-107">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="f3a2e-108">Este valor puede ser NULL si la interfaz solo es interna.</span><span class="sxs-lookup"><span data-stu-id="f3a2e-108">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="f3a2e-109">de Puntero al principio de la tabla vtable.</span><span class="sxs-lookup"><span data-stu-id="f3a2e-109">[in] A pointer to the start of the vtable.</span></span>  
  
 `cSlots`  
 <span data-ttu-id="f3a2e-110">de Número de ranuras que se encuentran en la tabla vtable.</span><span class="sxs-lookup"><span data-stu-id="f3a2e-110">[in] The number of slots that are in the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3a2e-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f3a2e-111">Remarks</span></span>  
 <span data-ttu-id="f3a2e-112">El generador de perfiles no debe bloquear en su implementación de este método porque la pila puede no estar en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="f3a2e-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="f3a2e-113">Si el generador de perfiles se bloquea aquí y se intenta la recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.</span><span class="sxs-lookup"><span data-stu-id="f3a2e-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="f3a2e-114">La implementación del generador de perfiles de este método no debe llamar a código administrado ni provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="f3a2e-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3a2e-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3a2e-115">Requirements</span></span>  
 <span data-ttu-id="f3a2e-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3a2e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3a2e-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f3a2e-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f3a2e-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3a2e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3a2e-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3a2e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3a2e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3a2e-120">See also</span></span>

- [<span data-ttu-id="f3a2e-121">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3a2e-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="f3a2e-122">COMClassicVTableDestroyed (método)</span><span class="sxs-lookup"><span data-stu-id="f3a2e-122">COMClassicVTableDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)
