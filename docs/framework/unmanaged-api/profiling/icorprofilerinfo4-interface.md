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
ms.openlocfilehash: 58d11e9084f53c69f2656b4f0ee6bc7d2cc4ae21
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495871"
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="c448d-102">ICorProfilerInfo4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c448d-102">ICorProfilerInfo4 Interface</span></span>
<span data-ttu-id="c448d-103">Proporciona métodos que los perfiles de código usan para comunicarse con el Common Language Runtime (CLR) para controlar la supervisión de eventos y la información de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="c448d-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="c448d-104">.</span><span class="sxs-lookup"><span data-stu-id="c448d-104">.</span></span> <span data-ttu-id="c448d-105">La `ICorProfilerInfo4` interfaz es una extensión de las otras `ICorProfilerInfo` interfaces.</span><span class="sxs-lookup"><span data-stu-id="c448d-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="c448d-106">Proporciona nuevos métodos para admitir la recompilación Just-in-Time (JIT), agregada en el .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="c448d-106">It provides new methods to support just-in-time (JIT) recompilation, added in the .NET Framework 4.5.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c448d-107">Métodos</span><span class="sxs-lookup"><span data-stu-id="c448d-107">Methods</span></span>  
  
|<span data-ttu-id="c448d-108">Método</span><span class="sxs-lookup"><span data-stu-id="c448d-108">Method</span></span>|<span data-ttu-id="c448d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c448d-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c448d-110">Método EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="c448d-110">EnumJITedFunctions2 Method</span></span>](icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="c448d-111">Devuelve un enumerador para todas las funciones compiladas previamente y compiladas con JIT.</span><span class="sxs-lookup"><span data-stu-id="c448d-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="c448d-112">Método EnumThreads</span><span class="sxs-lookup"><span data-stu-id="c448d-112">EnumThreads Method</span></span>](icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="c448d-113">Obtiene un enumerador que proporciona métodos para recorrer secuencialmente en iteración la colección de todos los subprocesos administrados en el proceso de la que se van a realizar perfiles.</span><span class="sxs-lookup"><span data-stu-id="c448d-113">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="c448d-114">Método GetCodeInfo3</span><span class="sxs-lookup"><span data-stu-id="c448d-114">GetCodeInfo3 Method</span></span>](icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="c448d-115">Obtiene las extensiones de código nativo asociadas con la versión recompilada con JIT de la función especificada.</span><span class="sxs-lookup"><span data-stu-id="c448d-115">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="c448d-116">Método GetFunctionFromIP2</span><span class="sxs-lookup"><span data-stu-id="c448d-116">GetFunctionFromIP2 Method</span></span>](icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="c448d-117">Asigna un puntero de instrucción de código administrado a la versión recompilada con JIT de una función especificada.</span><span class="sxs-lookup"><span data-stu-id="c448d-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="c448d-118">Método GetILToNativeMapping2</span><span class="sxs-lookup"><span data-stu-id="c448d-118">GetILToNativeMapping2 Method</span></span>](icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="c448d-119">Obtiene una asignación de los desplazamientos del lenguaje intermedio de Microsoft (MSIL) a los desplazamientos nativos para el código contenido en la versión recompilada con JIT de la función especificada.</span><span class="sxs-lookup"><span data-stu-id="c448d-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="c448d-120">Método GetObjectSize2</span><span class="sxs-lookup"><span data-stu-id="c448d-120">GetObjectSize2 Method</span></span>](icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="c448d-121">Devuelve el tamaño de un objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="c448d-121">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="c448d-122">Método GetReJITIDs</span><span class="sxs-lookup"><span data-stu-id="c448d-122">GetReJITIDs Method</span></span>](icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="c448d-123">Devuelve una matriz de identificadores que identifican todas las versiones compiladas con JIT de la función especificada que se siguen asignando.</span><span class="sxs-lookup"><span data-stu-id="c448d-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="c448d-124">Método InitializeCurrentThread</span><span class="sxs-lookup"><span data-stu-id="c448d-124">InitializeCurrentThread Method</span></span>](icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="c448d-125">Inicializa el subproceso actual antes de las llamadas posteriores a la API del generador de perfiles en el mismo subproceso, de modo que se pueda evitar el interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="c448d-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="c448d-126">Método RequestReJIT</span><span class="sxs-lookup"><span data-stu-id="c448d-126">RequestReJIT Method</span></span>](icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="c448d-127">Solicita una recompilación con JIT de todas las instancias de las funciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="c448d-127">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="c448d-128">Método RequestRevert</span><span class="sxs-lookup"><span data-stu-id="c448d-128">RequestRevert Method</span></span>](icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="c448d-129">Revierte todas las instancias de las funciones especificadas a sus versiones originales.</span><span class="sxs-lookup"><span data-stu-id="c448d-129">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c448d-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c448d-130">Remarks</span></span>  
 <span data-ttu-id="c448d-131">El CLR implementa los métodos de la interfaz `ICorProfilerInfo4` usando el modelo de subprocesamiento libre.</span><span class="sxs-lookup"><span data-stu-id="c448d-131">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="c448d-132">Cada método devuelve un valor HRESULT para indicar un resultado correcto o erróneo.</span><span class="sxs-lookup"><span data-stu-id="c448d-132">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="c448d-133">Para obtener una lista de los posibles códigos devueltos, consulte el archivo CorError.h.</span><span class="sxs-lookup"><span data-stu-id="c448d-133">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c448d-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c448d-134">Requirements</span></span>  
 <span data-ttu-id="c448d-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c448d-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c448d-136">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c448d-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c448d-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c448d-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c448d-138">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c448d-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c448d-139">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="c448d-139">See also</span></span>

- [<span data-ttu-id="c448d-140">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="c448d-140">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="c448d-141">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c448d-141">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
