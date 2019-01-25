---
title: ICorProfilerInfo4::RequestRevert (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.RequestRevert
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::RequestRevert
helpviewer_keywords:
- RequestRevert method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::RequestRevert method [.NET Framework profiling]
ms.assetid: 70261da5-5933-4e25-9de0-ddf51cba56cc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9578b8148efed1cac2ee25c86054c3507b84b254
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718759"
---
# <a name="icorprofilerinfo4requestrevert-method"></a><span data-ttu-id="ac309-102">ICorProfilerInfo4::RequestRevert (Método)</span><span class="sxs-lookup"><span data-stu-id="ac309-102">ICorProfilerInfo4::RequestRevert Method</span></span>
<span data-ttu-id="ac309-103">Revierte todas las instancias de las funciones especificadas a sus versiones originales.</span><span class="sxs-lookup"><span data-stu-id="ac309-103">Reverts all instances of the specified functions to their original versions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac309-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac309-104">Syntax</span></span>  
  
```  
HRESULT RequestRevert (  
   [in] ULONG    cFunctions,  
   [in, size_is(cFunctions)]  ModuleID    moduleIds[],  
   [in, size_is(cFunctions)]  mdMethodDef methodIds[],  
   [out, size_is(cFunctions)]  HRESULT status[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac309-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac309-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="ac309-106">[in] Número de funciones que se va a revertir.</span><span class="sxs-lookup"><span data-stu-id="ac309-106">[in] The number of functions to revert.</span></span>  
  
 `moduleIds`  
 <span data-ttu-id="ac309-107">[in] Especifica la parte `moduleId` de los pares (`module`, `methodDef`) que identifican las funciones que se van a revertir.</span><span class="sxs-lookup"><span data-stu-id="ac309-107">[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be reverted.</span></span>  
  
 `methodIds`  
 <span data-ttu-id="ac309-108">[in] Especifica la parte `methodId` de los pares (`module`, `methodDef`) que identifican las funciones que se van a revertir.</span><span class="sxs-lookup"><span data-stu-id="ac309-108">[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be reverted.</span></span>  
  
 `status`  
 <span data-ttu-id="ac309-109">[out] Matriz de valores HRESULT enumerados en la sección "HRESULT de estado" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="ac309-109">[out] An array of HRESULTs listed in the "Status HRESULTs" section later in this topic.</span></span> <span data-ttu-id="ac309-110">Cada HRESULT indica el intento correcto o erróneo de revertir cada función especificada en las matrices paralelas `moduleIds` y `methodIds`.</span><span class="sxs-lookup"><span data-stu-id="ac309-110">Each HRESULT indicates the success or failure of trying to revert each function specified in the parallel arrays `moduleIds` and `methodIds`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac309-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ac309-111">Return Value</span></span>  
 <span data-ttu-id="ac309-112">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="ac309-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ac309-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac309-113">HRESULT</span></span>|<span data-ttu-id="ac309-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac309-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac309-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac309-115">S_OK</span></span>|<span data-ttu-id="ac309-116">Se intentaron revertir todas las solicitudes; sin embargo, se debe comprobar la matriz de estados devueltos para determinar qué funciones se han revertido correctamente.</span><span class="sxs-lookup"><span data-stu-id="ac309-116">An attempt was made to revert all requests; however, the returned status array must be checked to determine which functions were successfully reverted.</span></span>|  
|<span data-ttu-id="ac309-117">CORPROF_E_CALLBACK4_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="ac309-117">CORPROF_E_CALLBACK4_REQUIRED</span></span>|<span data-ttu-id="ac309-118">El generador de perfiles debe implementar la [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interfaz para esta llamada que se deben admitir.</span><span class="sxs-lookup"><span data-stu-id="ac309-118">The profiler must implement the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interface for this call to be supported.</span></span>|  
|<span data-ttu-id="ac309-119">CORPROF_E_REJIT_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="ac309-119">CORPROF_E_REJIT_NOT_ENABLED</span></span>|<span data-ttu-id="ac309-120">No se habilitó la recompilación con JIT.</span><span class="sxs-lookup"><span data-stu-id="ac309-120">JIT recompilation has not been enabled.</span></span> <span data-ttu-id="ac309-121">Debe habilitar recompilación con JIT durante la inicialización mediante el [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) método para establecer el `COR_PRF_ENABLE_REJIT` marca.</span><span class="sxs-lookup"><span data-stu-id="ac309-121">You must enable JIT recompilation during initialization by using the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the `COR_PRF_ENABLE_REJIT` flag.</span></span>|  
|<span data-ttu-id="ac309-122">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ac309-122">E_INVALIDARG</span></span>|<span data-ttu-id="ac309-123">`cFunctions` es 0, o `moduleIds` o `methodIds` es `NULL`.</span><span class="sxs-lookup"><span data-stu-id="ac309-123">`cFunctions` is 0, or `moduleIds` or `methodIds` is `NULL`.</span></span>|  
|<span data-ttu-id="ac309-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ac309-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ac309-125">El CLR no pudo completar la solicitud porque se quedó sin memoria.</span><span class="sxs-lookup"><span data-stu-id="ac309-125">The CLR was unable to complete the request because it ran out of memory.</span></span>|  
  
## <a name="status-hresults"></a><span data-ttu-id="ac309-126">HRESULT de estado</span><span class="sxs-lookup"><span data-stu-id="ac309-126">Status HRESULTS</span></span>  
  
|<span data-ttu-id="ac309-127">HRESULT de la matriz de estados</span><span class="sxs-lookup"><span data-stu-id="ac309-127">Status array HRESULT</span></span>|<span data-ttu-id="ac309-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac309-128">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="ac309-129">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac309-129">S_OK</span></span>|<span data-ttu-id="ac309-130">La función correspondiente se revirtió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ac309-130">The corresponding function was successfully reverted.</span></span>|  
|<span data-ttu-id="ac309-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ac309-131">E_INVALIDARG</span></span>|<span data-ttu-id="ac309-132">El parámetro `moduleID` o `methodDef` es `NULL`.</span><span class="sxs-lookup"><span data-stu-id="ac309-132">The `moduleID` or `methodDef` parameter is `NULL`.</span></span>|  
|<span data-ttu-id="ac309-133">CORPROF_E_DATAINCOMPLETE</span><span class="sxs-lookup"><span data-stu-id="ac309-133">CORPROF_E_DATAINCOMPLETE</span></span>|<span data-ttu-id="ac309-134">El módulo no está totalmente cargado aún o está en proceso de descarga.</span><span class="sxs-lookup"><span data-stu-id="ac309-134">The module is not fully loaded yet, or it is in the process of being unloaded.</span></span>|  
|<span data-ttu-id="ac309-135">CORPROF_E_MODULE_IS_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="ac309-135">CORPROF_E_MODULE_IS_DYNAMIC</span></span>|<span data-ttu-id="ac309-136">El módulo especificado se genera dinámicamente (por ejemplo, mediante `Reflection.Emit`).</span><span class="sxs-lookup"><span data-stu-id="ac309-136">The specified module was dynamically generated (for example by `Reflection.Emit`).</span></span> <span data-ttu-id="ac309-137">Por lo tanto, este método no lo admite.</span><span class="sxs-lookup"><span data-stu-id="ac309-137">Therefore, it is not supported by this method.</span></span>|  
|<span data-ttu-id="ac309-138">CORPROF_E_ACTIVE_REJIT_REQUEST_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="ac309-138">CORPROF_E_ACTIVE_REJIT_REQUEST_NOT_FOUND</span></span>|<span data-ttu-id="ac309-139">El CLR no pudo revertir la función especificada porque no se encontró la solicitud de recompilación activa correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ac309-139">The CLR could not revert the specified function, because a corresponding active recompilation request was not found.</span></span> <span data-ttu-id="ac309-140">La recompilación nunca se solicitó o la función ya se había revertido.</span><span class="sxs-lookup"><span data-stu-id="ac309-140">Either the recompilation was never requested or the function was already reverted.</span></span>|  
|<span data-ttu-id="ac309-141">Otros</span><span class="sxs-lookup"><span data-stu-id="ac309-141">Other</span></span>|<span data-ttu-id="ac309-142">El sistema operativo devolvió un error fuera del control del CLR.</span><span class="sxs-lookup"><span data-stu-id="ac309-142">The operating system returned a failure outside the control of the CLR.</span></span> <span data-ttu-id="ac309-143">Por ejemplo, si se produce un error en una llamada del sistema para cambiar la protección de acceso de una página de memoria, se mostrará el error del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ac309-143">For example, if a system call to change the access protection of a page of memory fails, the operating system error will be displayed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac309-144">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac309-144">Remarks</span></span>  
 <span data-ttu-id="ac309-145">La próxima vez que se llame a cualquiera de las instancias de la función revertida, se ejecutarán las versiones originales de las funciones.</span><span class="sxs-lookup"><span data-stu-id="ac309-145">The next time any of the revereted function instances are called, the original versions of the functions will be run.</span></span> <span data-ttu-id="ac309-146">Si ya se está ejecutando una función, finalizará la ejecución de la versión que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="ac309-146">If a function is already running, it will finish executing the version that is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac309-147">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac309-147">Requirements</span></span>  
 <span data-ttu-id="ac309-148">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac309-148">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac309-149">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ac309-149">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ac309-150">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac309-150">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac309-151">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac309-151">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac309-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac309-152">See also</span></span>
- [<span data-ttu-id="ac309-153">ICorProfilerInfo4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac309-153">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="ac309-154">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ac309-154">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="ac309-155">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ac309-155">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
