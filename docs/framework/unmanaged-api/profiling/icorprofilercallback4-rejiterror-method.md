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
ms.openlocfilehash: 66195ea9df4c8e9ce847b38f7d020a3bebffcd37
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865186"
---
# <a name="icorprofilercallback4rejiterror-method"></a><span data-ttu-id="0d1b8-102">ICorProfilerCallback4::ReJITError (Método)</span><span class="sxs-lookup"><span data-stu-id="0d1b8-102">ICorProfilerCallback4::ReJITError Method</span></span>
<span data-ttu-id="0d1b8-103">Notifica al generador de perfiles que el compilador Just-in-Time (JIT) encontró un error en el proceso de recompilación.</span><span class="sxs-lookup"><span data-stu-id="0d1b8-103">Notifies the profiler that the just-in-time (JIT) compiler encountered an error in the recompilation process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d1b8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d1b8-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d1b8-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="0d1b8-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="0d1b8-106">de `ModuleID` en el que se realizó el intento de recompilación con errores.</span><span class="sxs-lookup"><span data-stu-id="0d1b8-106">[in] The `ModuleID` in which the failed recompilation attempt was made.</span></span>  
  
 `methodId`  
 <span data-ttu-id="0d1b8-107">de `MethodDef` del método en el que se realizó el intento de recompilación con errores.</span><span class="sxs-lookup"><span data-stu-id="0d1b8-107">[in] The `MethodDef` of the method on which the failed recompilation attempt was made.</span></span>  
  
 `functionId`  
 <span data-ttu-id="0d1b8-108">de Instancia de la función que se va a compilar o marcar para volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="0d1b8-108">[in] The function instance that is being recompiled or marked for recompilation.</span></span> <span data-ttu-id="0d1b8-109">Este valor puede ser `NULL` si el error se produjo por cada método en lugar de por cada instancia (por ejemplo, si el generador de perfiles especificó un token de metadatos no válido para el método que se va a volver a compilar).</span><span class="sxs-lookup"><span data-stu-id="0d1b8-109">This value may be `NULL` if the failure occurred on a per-method basis instead of a per-instantiation basis (for example, if the profiler specified an invalid metadata token for the method to be recompiled).</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="0d1b8-110">de HRESULT que indica la naturaleza del error.</span><span class="sxs-lookup"><span data-stu-id="0d1b8-110">[in] An HRESULT that indicates the nature of the failure.</span></span> <span data-ttu-id="0d1b8-111">Vea la sección Estados HRESULTs para obtener una lista de valores.</span><span class="sxs-lookup"><span data-stu-id="0d1b8-111">See the Status HRESULTS section for a list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d1b8-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0d1b8-112">Return Value</span></span>  
 <span data-ttu-id="0d1b8-113">Los valores devueltos de esta devolución de llamada se pasan por alto.</span><span class="sxs-lookup"><span data-stu-id="0d1b8-113">Return values from this callback are ignored.</span></span>  
  
## <a name="status-hresults"></a><span data-ttu-id="0d1b8-114">HRESULT de estado</span><span class="sxs-lookup"><span data-stu-id="0d1b8-114">Status HRESULTS</span></span>  
  
|<span data-ttu-id="0d1b8-115">HRESULT de la matriz de estados</span><span class="sxs-lookup"><span data-stu-id="0d1b8-115">Status array HRESULT</span></span>|<span data-ttu-id="0d1b8-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d1b8-116">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="0d1b8-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0d1b8-117">E_INVALIDARG</span></span>|<span data-ttu-id="0d1b8-118">El token de `moduleID` o `methodDef` es `NULL`.</span><span class="sxs-lookup"><span data-stu-id="0d1b8-118">The `moduleID` or `methodDef` token is `NULL`.</span></span>|  
|<span data-ttu-id="0d1b8-119">CORPROF_E_DATAINCOMPLETE</span><span class="sxs-lookup"><span data-stu-id="0d1b8-119">CORPROF_E_DATAINCOMPLETE</span></span>|<span data-ttu-id="0d1b8-120">El módulo no está totalmente cargado aún o está en proceso de descarga.</span><span class="sxs-lookup"><span data-stu-id="0d1b8-120">The module is not fully loaded yet, or it is in the process of being unloaded.</span></span>|  
|<span data-ttu-id="0d1b8-121">CORPROF_E_MODULE_IS_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="0d1b8-121">CORPROF_E_MODULE_IS_DYNAMIC</span></span>|<span data-ttu-id="0d1b8-122">El módulo especificado se generó dinámicamente (por ejemplo, por `Reflection.Emit`) y, por lo tanto, este método no lo admite.</span><span class="sxs-lookup"><span data-stu-id="0d1b8-122">The specified module was dynamically generated (for example, by `Reflection.Emit`), and is thus not supported by this method.</span></span>|  
|<span data-ttu-id="0d1b8-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span><span class="sxs-lookup"><span data-stu-id="0d1b8-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span></span>|<span data-ttu-id="0d1b8-124">Se crea una instancia del método en un ensamblado recopilable y, por tanto, no se puede volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="0d1b8-124">The method is instantiated into a collectible assembly, and is therefore not able to be recompiled.</span></span> <span data-ttu-id="0d1b8-125">Tenga en cuenta que se pueden crear instancias de los tipos y funciones definidos en un contexto de reflexión no (por ejemplo, `List<MyCollectibleStruct>`) en un ensamblado recopilable.</span><span class="sxs-lookup"><span data-stu-id="0d1b8-125">Note that types and functions defined in a non-reflection context (for example, `List<MyCollectibleStruct>`) can be instantiated into a collectible assembly.</span></span>|  
|<span data-ttu-id="0d1b8-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0d1b8-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0d1b8-127">El CLR se quedó sin memoria al intentar marcar el método especificado para la recompilación JIT.</span><span class="sxs-lookup"><span data-stu-id="0d1b8-127">The CLR ran out of memory while trying to mark the specified method for JIT recompilation.</span></span>|  
|<span data-ttu-id="0d1b8-128">Otro</span><span class="sxs-lookup"><span data-stu-id="0d1b8-128">Other</span></span>|<span data-ttu-id="0d1b8-129">El sistema operativo devolvió un error fuera del control del CLR.</span><span class="sxs-lookup"><span data-stu-id="0d1b8-129">The operating system returned a failure outside the control of the CLR.</span></span> <span data-ttu-id="0d1b8-130">Por ejemplo, si se produce un error en una llamada del sistema para cambiar la protección de acceso de una página de memoria, se muestra el error del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0d1b8-130">For example, if a system call to change the access protection of a page of memory fails, the operating system error is displayed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0d1b8-131">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="0d1b8-131">Requirements</span></span>  
 <span data-ttu-id="0d1b8-132">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d1b8-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d1b8-133">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0d1b8-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0d1b8-134">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d1b8-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d1b8-135">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d1b8-135">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d1b8-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d1b8-136">See also</span></span>

- [<span data-ttu-id="0d1b8-137">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d1b8-137">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="0d1b8-138">ICorProfilerCallback4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d1b8-138">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
