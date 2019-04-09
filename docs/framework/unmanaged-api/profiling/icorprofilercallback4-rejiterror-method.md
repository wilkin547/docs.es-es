---
title: ICorProfilerCallback4::ReJITError (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITError
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66f152279a21f28b54acebbf0be7c65bb73efa70
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150597"
---
# <a name="icorprofilercallback4rejiterror-method"></a><span data-ttu-id="e6aea-102">ICorProfilerCallback4::ReJITError (Método)</span><span class="sxs-lookup"><span data-stu-id="e6aea-102">ICorProfilerCallback4::ReJITError Method</span></span>
<span data-ttu-id="e6aea-103">Notifica al generador de perfiles que el compilador de just-in-time (JIT) detectó un error en el proceso de recompilación.</span><span class="sxs-lookup"><span data-stu-id="e6aea-103">Notifies the profiler that the just-in-time (JIT) compiler encountered an error in the recompilation process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6aea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6aea-104">Syntax</span></span>  
  
```  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6aea-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e6aea-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="e6aea-106">[in] El `ModuleID` en que se realizara el intento de volver a compilar con errores.</span><span class="sxs-lookup"><span data-stu-id="e6aea-106">[in] The `ModuleID` in which the failed recompilation attempt was made.</span></span>  
  
 `methodId`  
 <span data-ttu-id="e6aea-107">[in] El `MethodDef` del método en el que se ha intentado la recompilación con errores.</span><span class="sxs-lookup"><span data-stu-id="e6aea-107">[in] The `MethodDef` of the method on which the failed recompilation attempt was made.</span></span>  
  
 `functionId`  
 <span data-ttu-id="e6aea-108">[in] La instancia de la función que se ha vuelto a compilar o está marcado para volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="e6aea-108">[in] The function instance that is being recompiled or marked for recompilation.</span></span> <span data-ttu-id="e6aea-109">Este valor puede ser `NULL` si se produjo el error según el método en lugar de una base de cada instancia (por ejemplo, si el generador de perfiles especifica un token de metadatos no válidos para el método que se vuelva a compilar).</span><span class="sxs-lookup"><span data-stu-id="e6aea-109">This value may be `NULL` if the failure occurred on a per-method basis instead of a per-instantiation basis (for example, if the profiler specified an invalid metadata token for the method to be recompiled).</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="e6aea-110">[in] Un HRESULT que indica la naturaleza del error.</span><span class="sxs-lookup"><span data-stu-id="e6aea-110">[in] An HRESULT that indicates the nature of the failure.</span></span> <span data-ttu-id="e6aea-111">Consulte la sección de valores HRESULT de estado para obtener una lista de valores.</span><span class="sxs-lookup"><span data-stu-id="e6aea-111">See the Status HRESULTS section for a list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6aea-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e6aea-112">Return Value</span></span>  
 <span data-ttu-id="e6aea-113">Los valores devueltos de esta devolución de llamada se pasan por alto.</span><span class="sxs-lookup"><span data-stu-id="e6aea-113">Return values from this callback are ignored.</span></span>  
  
## <a name="status-hresults"></a><span data-ttu-id="e6aea-114">HRESULT de estado</span><span class="sxs-lookup"><span data-stu-id="e6aea-114">Status HRESULTS</span></span>  
  
|<span data-ttu-id="e6aea-115">HRESULT de la matriz de estados</span><span class="sxs-lookup"><span data-stu-id="e6aea-115">Status array HRESULT</span></span>|<span data-ttu-id="e6aea-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6aea-116">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="e6aea-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e6aea-117">E_INVALIDARG</span></span>|<span data-ttu-id="e6aea-118">El `moduleID` o `methodDef` token es `NULL`.</span><span class="sxs-lookup"><span data-stu-id="e6aea-118">The `moduleID` or `methodDef` token is `NULL`.</span></span>|  
|<span data-ttu-id="e6aea-119">CORPROF_E_DATAINCOMPLETE</span><span class="sxs-lookup"><span data-stu-id="e6aea-119">CORPROF_E_DATAINCOMPLETE</span></span>|<span data-ttu-id="e6aea-120">El módulo no está totalmente cargado aún o está en proceso de descarga.</span><span class="sxs-lookup"><span data-stu-id="e6aea-120">The module is not fully loaded yet, or it is in the process of being unloaded.</span></span>|  
|<span data-ttu-id="e6aea-121">CORPROF_E_MODULE_IS_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="e6aea-121">CORPROF_E_MODULE_IS_DYNAMIC</span></span>|<span data-ttu-id="e6aea-122">El módulo especificado se genera dinámicamente (por ejemplo, si `Reflection.Emit`) y, por tanto, no se admite este método.</span><span class="sxs-lookup"><span data-stu-id="e6aea-122">The specified module was dynamically generated (for example, by `Reflection.Emit`), and is thus not supported by this method.</span></span>|  
|<span data-ttu-id="e6aea-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span><span class="sxs-lookup"><span data-stu-id="e6aea-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span></span>|<span data-ttu-id="e6aea-124">El método se crea una instancia en un ensamblado recopilable y, por lo tanto, no puede volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="e6aea-124">The method is instantiated into a collectible assembly, and is therefore not able to be recompiled.</span></span> <span data-ttu-id="e6aea-125">Tenga en cuenta que los tipos y funciones definidas en un contexto no reflexión (por ejemplo, `List<MyCollectibleStruct>`) se pueden crear instancias en un ensamblado recopilable.</span><span class="sxs-lookup"><span data-stu-id="e6aea-125">Note that types and functions defined in a non-reflection context (for example, `List<MyCollectibleStruct>`) can be instantiated into a collectible assembly.</span></span>|  
|<span data-ttu-id="e6aea-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="e6aea-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="e6aea-127">El CLR se quedó sin memoria al intentar marcar el método especificado para la recompilación con JIT.</span><span class="sxs-lookup"><span data-stu-id="e6aea-127">The CLR ran out of memory while trying to mark the specified method for JIT recompilation.</span></span>|  
|<span data-ttu-id="e6aea-128">Otros</span><span class="sxs-lookup"><span data-stu-id="e6aea-128">Other</span></span>|<span data-ttu-id="e6aea-129">El sistema operativo devolvió un error fuera del control del CLR.</span><span class="sxs-lookup"><span data-stu-id="e6aea-129">The operating system returned a failure outside the control of the CLR.</span></span> <span data-ttu-id="e6aea-130">Por ejemplo, si se produce un error en una llamada del sistema para cambiar la protección de acceso de una página de memoria, se muestra el error del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e6aea-130">For example, if a system call to change the access protection of a page of memory fails, the operating system error is displayed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e6aea-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6aea-131">Requirements</span></span>  
 <span data-ttu-id="e6aea-132">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6aea-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6aea-133">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e6aea-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e6aea-134">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6aea-134">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e6aea-135">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e6aea-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e6aea-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6aea-136">See also</span></span>

- [<span data-ttu-id="e6aea-137">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6aea-137">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="e6aea-138">ICorProfilerCallback4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6aea-138">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
