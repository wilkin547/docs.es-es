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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f60c4373410c46c5d1ea284b2cacd4b5c070ed9d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54682828"
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a><span data-ttu-id="5d5be-102">ICorProfilerCallback::COMClassicVTableDestroyed (Método)</span><span class="sxs-lookup"><span data-stu-id="5d5be-102">ICorProfilerCallback::COMClassicVTableDestroyed Method</span></span>
<span data-ttu-id="5d5be-103">Notifica al generador de perfiles que se está destruyendo un vtable de interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="5d5be-103">Notifies the profiler that a COM interop vtable is being destroyed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d5be-104">Esta devolución de llamada es probable que nunca se producen, ya que se produce la destrucción de vtables muy cerca de apagado.</span><span class="sxs-lookup"><span data-stu-id="5d5be-104">This callback is likely never to occur, because the destruction of vtables occurs very close to shutdown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d5be-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d5be-105">Syntax</span></span>  
  
```  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d5be-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5d5be-106">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="5d5be-107">[in] El identificador de la clase para el que se creó esta tabla virtual.</span><span class="sxs-lookup"><span data-stu-id="5d5be-107">[in] The ID of the class for which this vtable was created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="5d5be-108">[in] El identificador de la interfaz implementada por la clase.</span><span class="sxs-lookup"><span data-stu-id="5d5be-108">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="5d5be-109">Este valor puede ser NULL si la interfaz es solo interna.</span><span class="sxs-lookup"><span data-stu-id="5d5be-109">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="5d5be-110">[in] Un puntero al principio de la tabla vtable.</span><span class="sxs-lookup"><span data-stu-id="5d5be-110">[in] A pointer to the start of the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d5be-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5d5be-111">Remarks</span></span>  
 <span data-ttu-id="5d5be-112">El generador de perfiles no debe bloquearse en su implementación de este método porque la pila no puede estar en un estado que permita la recolección de elementos y, por lo tanto, no se puede habilitar la recolección preferente.</span><span class="sxs-lookup"><span data-stu-id="5d5be-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="5d5be-113">Si el generador de perfiles se bloquea aquí y se intenta realizar la recolección de elementos, el tiempo de ejecución se bloqueará hasta que devuelve esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="5d5be-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="5d5be-114">Implementación del generador de perfiles de este método no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="5d5be-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d5be-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d5be-115">Requirements</span></span>  
 <span data-ttu-id="5d5be-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d5be-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d5be-117">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5d5be-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5d5be-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d5be-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d5be-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d5be-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d5be-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d5be-120">See also</span></span>
- [<span data-ttu-id="5d5be-121">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d5be-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="5d5be-122">COMClassicVTableCreated (método)</span><span class="sxs-lookup"><span data-stu-id="5d5be-122">COMClassicVTableCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)
