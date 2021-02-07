---
description: 'Más información sobre: ICorProfilerInfo4:: Requestrevert ((método)'
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
ms.openlocfilehash: 24a6a86f32bb9657e62a4433edcb5835e16b9754
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737314"
---
# <a name="icorprofilerinfo4requestrevert-method"></a><span data-ttu-id="d59da-103">ICorProfilerInfo4::RequestRevert (Método)</span><span class="sxs-lookup"><span data-stu-id="d59da-103">ICorProfilerInfo4::RequestRevert Method</span></span>

<span data-ttu-id="d59da-104">Revierte todas las instancias de las funciones especificadas a sus versiones originales.</span><span class="sxs-lookup"><span data-stu-id="d59da-104">Reverts all instances of the specified functions to their original versions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d59da-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d59da-105">Syntax</span></span>  
  
```cpp  
HRESULT RequestRevert (  
   [in] ULONG    cFunctions,  
   [in, size_is(cFunctions)]  ModuleID    moduleIds[],  
   [in, size_is(cFunctions)]  mdMethodDef methodIds[],  
   [out, size_is(cFunctions)]  HRESULT status[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d59da-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d59da-106">Parameters</span></span>  

 `cFunctions`  
 <span data-ttu-id="d59da-107">[in] Número de funciones que se va a revertir.</span><span class="sxs-lookup"><span data-stu-id="d59da-107">[in] The number of functions to revert.</span></span>  
  
 `moduleIds`  
 <span data-ttu-id="d59da-108">[in] Especifica la parte `moduleId` de los pares (`module`, `methodDef`) que identifican las funciones que se van a revertir.</span><span class="sxs-lookup"><span data-stu-id="d59da-108">[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be reverted.</span></span>  
  
 `methodIds`  
 <span data-ttu-id="d59da-109">[in] Especifica la parte `methodId` de los pares (`module`, `methodDef`) que identifican las funciones que se van a revertir.</span><span class="sxs-lookup"><span data-stu-id="d59da-109">[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be reverted.</span></span>  
  
 `status`  
 <span data-ttu-id="d59da-110">[out] Matriz de valores HRESULT enumerados en la sección "HRESULT de estado" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="d59da-110">[out] An array of HRESULTs listed in the "Status HRESULTs" section later in this topic.</span></span> <span data-ttu-id="d59da-111">Cada HRESULT indica el intento correcto o erróneo de revertir cada función especificada en las matrices paralelas `moduleIds` y `methodIds`.</span><span class="sxs-lookup"><span data-stu-id="d59da-111">Each HRESULT indicates the success or failure of trying to revert each function specified in the parallel arrays `moduleIds` and `methodIds`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d59da-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d59da-112">Return Value</span></span>  

 <span data-ttu-id="d59da-113">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="d59da-113">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d59da-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d59da-114">HRESULT</span></span>|<span data-ttu-id="d59da-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="d59da-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d59da-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="d59da-116">S_OK</span></span>|<span data-ttu-id="d59da-117">Se intentaron revertir todas las solicitudes; sin embargo, se debe comprobar la matriz de estados devueltos para determinar qué funciones se han revertido correctamente.</span><span class="sxs-lookup"><span data-stu-id="d59da-117">An attempt was made to revert all requests; however, the returned status array must be checked to determine which functions were successfully reverted.</span></span>|  
|<span data-ttu-id="d59da-118">CORPROF_E_CALLBACK4_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="d59da-118">CORPROF_E_CALLBACK4_REQUIRED</span></span>|<span data-ttu-id="d59da-119">El generador de perfiles debe implementar la interfaz [ICorProfilerCallback4](icorprofilercallback4-interface.md) para que se admita esta llamada.</span><span class="sxs-lookup"><span data-stu-id="d59da-119">The profiler must implement the [ICorProfilerCallback4](icorprofilercallback4-interface.md) interface for this call to be supported.</span></span>|  
|<span data-ttu-id="d59da-120">CORPROF_E_REJIT_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="d59da-120">CORPROF_E_REJIT_NOT_ENABLED</span></span>|<span data-ttu-id="d59da-121">No se habilitó la recompilación con JIT.</span><span class="sxs-lookup"><span data-stu-id="d59da-121">JIT recompilation has not been enabled.</span></span> <span data-ttu-id="d59da-122">Debe habilitar la recompilación JIT durante la inicialización mediante el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer la `COR_PRF_ENABLE_REJIT` marca.</span><span class="sxs-lookup"><span data-stu-id="d59da-122">You must enable JIT recompilation during initialization by using the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the `COR_PRF_ENABLE_REJIT` flag.</span></span>|  
|<span data-ttu-id="d59da-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d59da-123">E_INVALIDARG</span></span>|<span data-ttu-id="d59da-124">`cFunctions` es 0, o `moduleIds` o `methodIds` es `NULL`.</span><span class="sxs-lookup"><span data-stu-id="d59da-124">`cFunctions` is 0, or `moduleIds` or `methodIds` is `NULL`.</span></span>|  
|<span data-ttu-id="d59da-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d59da-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d59da-126">El CLR no pudo completar la solicitud porque se quedó sin memoria.</span><span class="sxs-lookup"><span data-stu-id="d59da-126">The CLR was unable to complete the request because it ran out of memory.</span></span>|  
  
## <a name="status-hresults"></a><span data-ttu-id="d59da-127">HRESULT de estado</span><span class="sxs-lookup"><span data-stu-id="d59da-127">Status HRESULTS</span></span>  
  
|<span data-ttu-id="d59da-128">HRESULT de la matriz de estados</span><span class="sxs-lookup"><span data-stu-id="d59da-128">Status array HRESULT</span></span>|<span data-ttu-id="d59da-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="d59da-129">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="d59da-130">S_OK</span><span class="sxs-lookup"><span data-stu-id="d59da-130">S_OK</span></span>|<span data-ttu-id="d59da-131">La función correspondiente se revirtió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d59da-131">The corresponding function was successfully reverted.</span></span>|  
|<span data-ttu-id="d59da-132">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d59da-132">E_INVALIDARG</span></span>|<span data-ttu-id="d59da-133">El parámetro `moduleID` o `methodDef` es `NULL`.</span><span class="sxs-lookup"><span data-stu-id="d59da-133">The `moduleID` or `methodDef` parameter is `NULL`.</span></span>|  
|<span data-ttu-id="d59da-134">CORPROF_E_DATAINCOMPLETE</span><span class="sxs-lookup"><span data-stu-id="d59da-134">CORPROF_E_DATAINCOMPLETE</span></span>|<span data-ttu-id="d59da-135">El módulo no está totalmente cargado aún o está en proceso de descarga.</span><span class="sxs-lookup"><span data-stu-id="d59da-135">The module is not fully loaded yet, or it is in the process of being unloaded.</span></span>|  
|<span data-ttu-id="d59da-136">CORPROF_E_MODULE_IS_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="d59da-136">CORPROF_E_MODULE_IS_DYNAMIC</span></span>|<span data-ttu-id="d59da-137">El módulo especificado se genera dinámicamente (por ejemplo, mediante `Reflection.Emit`).</span><span class="sxs-lookup"><span data-stu-id="d59da-137">The specified module was dynamically generated (for example by `Reflection.Emit`).</span></span> <span data-ttu-id="d59da-138">Por lo tanto, este método no lo admite.</span><span class="sxs-lookup"><span data-stu-id="d59da-138">Therefore, it is not supported by this method.</span></span>|  
|<span data-ttu-id="d59da-139">CORPROF_E_ACTIVE_REJIT_REQUEST_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="d59da-139">CORPROF_E_ACTIVE_REJIT_REQUEST_NOT_FOUND</span></span>|<span data-ttu-id="d59da-140">El CLR no pudo revertir la función especificada porque no se encontró la solicitud de recompilación activa correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d59da-140">The CLR could not revert the specified function, because a corresponding active recompilation request was not found.</span></span> <span data-ttu-id="d59da-141">La recompilación nunca se solicitó o la función ya se había revertido.</span><span class="sxs-lookup"><span data-stu-id="d59da-141">Either the recompilation was never requested or the function was already reverted.</span></span>|  
|<span data-ttu-id="d59da-142">Otros</span><span class="sxs-lookup"><span data-stu-id="d59da-142">Other</span></span>|<span data-ttu-id="d59da-143">El sistema operativo devolvió un error fuera del control del CLR.</span><span class="sxs-lookup"><span data-stu-id="d59da-143">The operating system returned a failure outside the control of the CLR.</span></span> <span data-ttu-id="d59da-144">Por ejemplo, si se produce un error en una llamada del sistema para cambiar la protección de acceso de una página de memoria, se mostrará el error del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d59da-144">For example, if a system call to change the access protection of a page of memory fails, the operating system error will be displayed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d59da-145">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d59da-145">Remarks</span></span>  

 <span data-ttu-id="d59da-146">La próxima vez que se llame a cualquiera de las instancias de la función revertida, se ejecutarán las versiones originales de las funciones.</span><span class="sxs-lookup"><span data-stu-id="d59da-146">The next time any of the revereted function instances are called, the original versions of the functions will be run.</span></span> <span data-ttu-id="d59da-147">Si ya se está ejecutando una función, finalizará la ejecución de la versión que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="d59da-147">If a function is already running, it will finish executing the version that is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d59da-148">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d59da-148">Requirements</span></span>  

 <span data-ttu-id="d59da-149">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d59da-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d59da-150">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d59da-150">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d59da-151">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d59da-151">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d59da-152">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d59da-152">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d59da-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="d59da-153">See also</span></span>

- [<span data-ttu-id="d59da-154">ICorProfilerInfo4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d59da-154">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="d59da-155">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d59da-155">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="d59da-156">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d59da-156">Profiling</span></span>](index.md)
