---
title: "ICorProfilerCallback::COMClassicVTableCreated (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.COMClassicVTableCreated
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::COMClassicVTableCreated
helpviewer_keywords:
- COMClassicVTableCreated method [.NET Framework profiling]
- ICorProfilerCallback::COMClassicVTableCreated method [.NET Framework profiling]
ms.assetid: 6e1834ab-c359-498a-b10b-984ae23cdda4
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 43fb447393e1d34ca53fbb62ecdc456a97452bc4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="17469-102">ICorProfilerCallback::COMClassicVTableCreated (Método)</span><span class="sxs-lookup"><span data-stu-id="17469-102">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>
<span data-ttu-id="17469-103">Notifica al generador de perfiles que se ha creado un vtable de interoperabilidad COM para el IID y la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="17469-103">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17469-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17469-104">Syntax</span></span>  
  
```  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="17469-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="17469-105">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="17469-106">[in] El identificador de la clase para la que se ha creado la vtable.</span><span class="sxs-lookup"><span data-stu-id="17469-106">[in] The ID of the class for which the vtable has been created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="17469-107">[in] El identificador de la interfaz implementada por la clase.</span><span class="sxs-lookup"><span data-stu-id="17469-107">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="17469-108">Este valor puede ser NULL si la interfaz es solo interna.</span><span class="sxs-lookup"><span data-stu-id="17469-108">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="17469-109">[in] Un puntero al principio de la tabla vtable.</span><span class="sxs-lookup"><span data-stu-id="17469-109">[in] A pointer to the start of the vtable.</span></span>  
  
 `cSlots`  
 <span data-ttu-id="17469-110">[in] El número de espacios que se encuentran en la tabla vtable.</span><span class="sxs-lookup"><span data-stu-id="17469-110">[in] The number of slots that are in the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17469-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="17469-111">Remarks</span></span>  
 <span data-ttu-id="17469-112">El generador de perfiles no debe bloquearse en su implementación de este método porque la pila no puede estar en un estado que permita la recopilación de elementos no utilizados y, por lo tanto, no se puede habilitar la colección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="17469-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="17469-113">Si el generador de perfiles se bloquea aquí y se intenta realizar la recolección de elementos, el tiempo de ejecución se bloqueará hasta que devuelve esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="17469-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="17469-114">Implementación del generador de perfiles de este método no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="17469-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17469-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17469-115">Requirements</span></span>  
 <span data-ttu-id="17469-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17469-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17469-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="17469-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="17469-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17469-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17469-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17469-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17469-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="17469-120">See Also</span></span>  
 [<span data-ttu-id="17469-121">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="17469-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="17469-122">COMClassicVTableDestroyed (método)</span><span class="sxs-lookup"><span data-stu-id="17469-122">COMClassicVTableDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)
