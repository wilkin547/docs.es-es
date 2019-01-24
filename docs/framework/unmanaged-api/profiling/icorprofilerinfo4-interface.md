---
title: ICorProfilerInfo4 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4
helpviewer_keywords:
- ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 78f9645ad31e7421e239089c5610f6523918228b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536634"
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="06a6e-102">ICorProfilerInfo4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="06a6e-102">ICorProfilerInfo4 Interface</span></span>
<span data-ttu-id="06a6e-103">Proporciona métodos que los generadores de perfiles de código usan para comunicarse con el common language runtime (CLR) para controlar la supervisión de eventos e información de solicitud.</span><span class="sxs-lookup"><span data-stu-id="06a6e-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="06a6e-104">.</span><span class="sxs-lookup"><span data-stu-id="06a6e-104">.</span></span> <span data-ttu-id="06a6e-105">El `ICorProfilerInfo4` interfaz es una extensión de la otra `ICorProfilerInfo` interfaces.</span><span class="sxs-lookup"><span data-stu-id="06a6e-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="06a6e-106">Proporciona nuevos métodos para admitir la nueva compilación just-in-time (JIT), agregada en el [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06a6e-106">It provides new methods to support just-in-time (JIT) recompilation, added in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
## <a name="methods"></a><span data-ttu-id="06a6e-107">Métodos</span><span class="sxs-lookup"><span data-stu-id="06a6e-107">Methods</span></span>  
  
|<span data-ttu-id="06a6e-108">Método</span><span class="sxs-lookup"><span data-stu-id="06a6e-108">Method</span></span>|<span data-ttu-id="06a6e-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="06a6e-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="06a6e-110">EnumJITedFunctions2 (método)</span><span class="sxs-lookup"><span data-stu-id="06a6e-110">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="06a6e-111">Devuelve un enumerador para todas las funciones que antes estaban compilados JIT y recompilada con JIT.</span><span class="sxs-lookup"><span data-stu-id="06a6e-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="06a6e-112">EnumThreads (método)</span><span class="sxs-lookup"><span data-stu-id="06a6e-112">EnumThreads Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="06a6e-113">Obtiene un enumerador que proporciona métodos para iterar secuencialmente por la colección de todos los subprocesos administrados en el proceso de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="06a6e-113">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="06a6e-114">GetCodeInfo3 (método)</span><span class="sxs-lookup"><span data-stu-id="06a6e-114">GetCodeInfo3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="06a6e-115">Obtiene las extensiones de código nativo asociadas con la versión recompilada con JIT de la función especificada.</span><span class="sxs-lookup"><span data-stu-id="06a6e-115">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="06a6e-116">GetFunctionFromIP2 (método)</span><span class="sxs-lookup"><span data-stu-id="06a6e-116">GetFunctionFromIP2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="06a6e-117">Asigna un puntero de instrucción de código administrado a la versión recompilada con JIT de una función especificada.</span><span class="sxs-lookup"><span data-stu-id="06a6e-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="06a6e-118">GetILToNativeMapping2 (método)</span><span class="sxs-lookup"><span data-stu-id="06a6e-118">GetILToNativeMapping2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="06a6e-119">Obtiene una asignación de desplazamientos del lenguaje intermedio (MSIL) a los desplazamientos nativos para el código incluido en la versión recompilada con JIT de la función especificada de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="06a6e-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="06a6e-120">GetObjectSize2 (método)</span><span class="sxs-lookup"><span data-stu-id="06a6e-120">GetObjectSize2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="06a6e-121">Devuelve el tamaño de un objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="06a6e-121">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="06a6e-122">GetReJITIDs (método)</span><span class="sxs-lookup"><span data-stu-id="06a6e-122">GetReJITIDs Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="06a6e-123">Devuelve una matriz de identificadores que identifican todas recompilada con JIT las versiones de la función especificada que todavía se asignan.</span><span class="sxs-lookup"><span data-stu-id="06a6e-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="06a6e-124">InitializeCurrentThread (método)</span><span class="sxs-lookup"><span data-stu-id="06a6e-124">InitializeCurrentThread Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="06a6e-125">Inicializa el subproceso actual antes del generador de perfiles posteriores llamadas de API en el mismo subproceso, por lo que se puede evitar que un interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="06a6e-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="06a6e-126">RequestReJIT (método)</span><span class="sxs-lookup"><span data-stu-id="06a6e-126">RequestReJIT Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="06a6e-127">Solicita una recompilación con JIT de todas las instancias de las funciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="06a6e-127">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="06a6e-128">RequestRevert (método)</span><span class="sxs-lookup"><span data-stu-id="06a6e-128">RequestRevert Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="06a6e-129">Revierte todas las instancias de las funciones especificadas a sus versiones originales.</span><span class="sxs-lookup"><span data-stu-id="06a6e-129">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06a6e-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="06a6e-130">Remarks</span></span>  
 <span data-ttu-id="06a6e-131">El CLR implementa los métodos de la interfaz `ICorProfilerInfo4` usando el modelo de subprocesamiento libre.</span><span class="sxs-lookup"><span data-stu-id="06a6e-131">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="06a6e-132">Cada método devuelve un valor HRESULT para indicar un resultado correcto o erróneo.</span><span class="sxs-lookup"><span data-stu-id="06a6e-132">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="06a6e-133">Para obtener una lista de los posibles códigos devueltos, consulte el archivo CorError.h.</span><span class="sxs-lookup"><span data-stu-id="06a6e-133">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06a6e-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06a6e-134">Requirements</span></span>  
 <span data-ttu-id="06a6e-135">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06a6e-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06a6e-136">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="06a6e-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="06a6e-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06a6e-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06a6e-138">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06a6e-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06a6e-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="06a6e-139">See also</span></span>
- [<span data-ttu-id="06a6e-140">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="06a6e-140">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="06a6e-141">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="06a6e-141">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
