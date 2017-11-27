---
title: "ICorProfilerCallback4::ReJITError (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.ReJITError
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c8b1f3c5b206b2e6a108e784a206d597b69fd662
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback4rejiterror-method"></a><span data-ttu-id="537ac-102">ICorProfilerCallback4::ReJITError (Método)</span><span class="sxs-lookup"><span data-stu-id="537ac-102">ICorProfilerCallback4::ReJITError Method</span></span>
<span data-ttu-id="537ac-103">Notifica al generador de perfiles que el compilador de just-in-time (JIT) encontró un error en el proceso de recompilación.</span><span class="sxs-lookup"><span data-stu-id="537ac-103">Notifies the profiler that the just-in-time (JIT) compiler encountered an error in the recompilation process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="537ac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="537ac-104">Syntax</span></span>  
  
```  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="537ac-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="537ac-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="537ac-106">[in] El `ModuleID` en que se realizara el intento de volver a compilar errores.</span><span class="sxs-lookup"><span data-stu-id="537ac-106">[in] The `ModuleID` in which the failed recompilation attempt was made.</span></span>  
  
 `methodId`  
 <span data-ttu-id="537ac-107">[in] El `MethodDef` del método en el que se realizara el intento de volver a compilar errores.</span><span class="sxs-lookup"><span data-stu-id="537ac-107">[in] The `MethodDef` of the method on which the failed recompilation attempt was made.</span></span>  
  
 `functionId`  
 <span data-ttu-id="537ac-108">[in] La instancia de la función que se ha vuelto a compilar o está marcado para volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="537ac-108">[in] The function instance that is being recompiled or marked for recompilation.</span></span> <span data-ttu-id="537ac-109">Este valor puede ser `NULL` si se produjo el error en una base por cada método en lugar de una base de cada instancia (por ejemplo, si el generador de perfiles especifica un token de metadatos no válidos para el método se vuelvan a compilar).</span><span class="sxs-lookup"><span data-stu-id="537ac-109">This value may be `NULL` if the failure occurred on a per-method basis instead of a per-instantiation basis (for example, if the profiler specified an invalid metadata token for the method to be recompiled).</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="537ac-110">[in] Un valor HRESULT que indica la naturaleza del error.</span><span class="sxs-lookup"><span data-stu-id="537ac-110">[in] An HRESULT that indicates the nature of the failure.</span></span> <span data-ttu-id="537ac-111">Vea la sección de valores HRESULT de estado para obtener una lista de valores.</span><span class="sxs-lookup"><span data-stu-id="537ac-111">See the Status HRESULTS section for a list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="537ac-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="537ac-112">Return Value</span></span>  
 <span data-ttu-id="537ac-113">Los valores devueltos de esta devolución de llamada se pasan por alto.</span><span class="sxs-lookup"><span data-stu-id="537ac-113">Return values from this callback are ignored.</span></span>  
  
## <a name="status-hresults"></a><span data-ttu-id="537ac-114">HRESULT de estado</span><span class="sxs-lookup"><span data-stu-id="537ac-114">Status HRESULTS</span></span>  
  
|<span data-ttu-id="537ac-115">HRESULT de la matriz de estados</span><span class="sxs-lookup"><span data-stu-id="537ac-115">Status array HRESULT</span></span>|<span data-ttu-id="537ac-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="537ac-116">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="537ac-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="537ac-117">E_INVALIDARG</span></span>|<span data-ttu-id="537ac-118">El `moduleID` o `methodDef` token es `NULL`.</span><span class="sxs-lookup"><span data-stu-id="537ac-118">The `moduleID` or `methodDef` token is `NULL`.</span></span>|  
|<span data-ttu-id="537ac-119">CORPROF_E_DATAINCOMPLETE</span><span class="sxs-lookup"><span data-stu-id="537ac-119">CORPROF_E_DATAINCOMPLETE</span></span>|<span data-ttu-id="537ac-120">El módulo no está totalmente cargado aún o está en proceso de descarga.</span><span class="sxs-lookup"><span data-stu-id="537ac-120">The module is not fully loaded yet, or it is in the process of being unloaded.</span></span>|  
|<span data-ttu-id="537ac-121">CORPROF_E_MODULE_IS_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="537ac-121">CORPROF_E_MODULE_IS_DYNAMIC</span></span>|<span data-ttu-id="537ac-122">El módulo especificado se genera dinámicamente (por ejemplo, `Reflection.Emit`) y, por tanto, no se admite este método.</span><span class="sxs-lookup"><span data-stu-id="537ac-122">The specified module was dynamically generated (for example, by `Reflection.Emit`), and is thus not supported by this method.</span></span>|  
|<span data-ttu-id="537ac-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span><span class="sxs-lookup"><span data-stu-id="537ac-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span></span>|<span data-ttu-id="537ac-124">El método se crea una instancia en un ensamblado recopilable y, por lo tanto, no puede volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="537ac-124">The method is instantiated into a collectible assembly, and is therefore not able to be recompiled.</span></span> <span data-ttu-id="537ac-125">Tenga en cuenta que los tipos y funciones definidas en un contexto de reflexión no (por ejemplo, `List<MyCollectibleStruct>`) se pueden crear instancias en un ensamblado recopilable.</span><span class="sxs-lookup"><span data-stu-id="537ac-125">Note that types and functions defined in a non-reflection context (for example, `List<MyCollectibleStruct>`) can be instantiated into a collectible assembly.</span></span>|  
|<span data-ttu-id="537ac-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="537ac-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="537ac-127">El CLR se quedó sin memoria al intentar marcar el método especificado para la recompilación con JIT.</span><span class="sxs-lookup"><span data-stu-id="537ac-127">The CLR ran out of memory while trying to mark the specified method for JIT recompilation.</span></span>|  
|<span data-ttu-id="537ac-128">Otros</span><span class="sxs-lookup"><span data-stu-id="537ac-128">Other</span></span>|<span data-ttu-id="537ac-129">El sistema operativo devolvió un error fuera del control del CLR.</span><span class="sxs-lookup"><span data-stu-id="537ac-129">The operating system returned a failure outside the control of the CLR.</span></span> <span data-ttu-id="537ac-130">Por ejemplo, si se produce un error en una llamada del sistema para cambiar la protección de acceso de una página de memoria, se muestra el error del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="537ac-130">For example, if a system call to change the access protection of a page of memory fails, the operating system error is displayed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="537ac-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="537ac-131">Requirements</span></span>  
 <span data-ttu-id="537ac-132">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="537ac-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="537ac-133">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="537ac-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="537ac-134">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="537ac-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="537ac-135">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="537ac-135">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="537ac-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="537ac-136">See Also</span></span>  
 [<span data-ttu-id="537ac-137">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="537ac-137">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="537ac-138">ICorProfilerCallback4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="537ac-138">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
