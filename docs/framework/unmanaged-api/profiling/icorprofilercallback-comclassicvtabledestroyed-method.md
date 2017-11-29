---
title: "ICorProfilerCallback::COMClassicVTableDestroyed (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.COMClassicVTableDestroyed
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::COMClassicVTableDestroyed
helpviewer_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed method [.NET Framework profiling]
- COMClassicVTableDestroyed method [.NET Framework profiling]
ms.assetid: 29da20ca-bf39-4356-8099-d9c3ac3423a9
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ebff8297a708b130a0d3983fd75b76c3aeaeceaf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a><span data-ttu-id="af332-102">ICorProfilerCallback::COMClassicVTableDestroyed (Método)</span><span class="sxs-lookup"><span data-stu-id="af332-102">ICorProfilerCallback::COMClassicVTableDestroyed Method</span></span>
<span data-ttu-id="af332-103">Notifica al generador de perfiles que se está destruyendo un vtable de interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="af332-103">Notifies the profiler that a COM interop vtable is being destroyed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af332-104">Esta devolución de llamada es probable que nunca se produzca, ya que la destrucción de tablas virtuales se produce muy poco antes del cierre.</span><span class="sxs-lookup"><span data-stu-id="af332-104">This callback is likely never to occur, because the destruction of vtables occurs very close to shutdown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af332-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af332-105">Syntax</span></span>  
  
```  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af332-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="af332-106">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="af332-107">[in] El identificador de la clase para la que se creó este vtable.</span><span class="sxs-lookup"><span data-stu-id="af332-107">[in] The ID of the class for which this vtable was created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="af332-108">[in] El identificador de la interfaz implementada por la clase.</span><span class="sxs-lookup"><span data-stu-id="af332-108">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="af332-109">Este valor puede ser NULL si la interfaz es solo interna.</span><span class="sxs-lookup"><span data-stu-id="af332-109">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="af332-110">[in] Un puntero al principio de la tabla vtable.</span><span class="sxs-lookup"><span data-stu-id="af332-110">[in] A pointer to the start of the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af332-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="af332-111">Remarks</span></span>  
 <span data-ttu-id="af332-112">El generador de perfiles no debe bloquearse en su implementación de este método porque la pila no puede estar en un estado que permita la recopilación de elementos no utilizados y, por lo tanto, no se puede habilitar la colección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="af332-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="af332-113">Si el generador de perfiles se bloquea aquí y se intenta realizar la recolección de elementos, el tiempo de ejecución se bloqueará hasta que devuelve esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="af332-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="af332-114">Implementación del generador de perfiles de este método no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="af332-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af332-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af332-115">Requirements</span></span>  
 <span data-ttu-id="af332-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af332-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af332-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="af332-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="af332-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af332-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af332-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af332-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af332-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="af332-120">See Also</span></span>  
 [<span data-ttu-id="af332-121">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="af332-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="af332-122">COMClassicVTableCreated (método)</span><span class="sxs-lookup"><span data-stu-id="af332-122">COMClassicVTableCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)
