---
description: 'Más información acerca de: interfaz ICorProfilerInfo4'
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
ms.openlocfilehash: 94e33be74ccffea3fa9a0e51e317a6888596606d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794512"
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="180d9-103">ICorProfilerInfo4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="180d9-103">ICorProfilerInfo4 Interface</span></span>

<span data-ttu-id="180d9-104">Proporciona métodos que los perfiles de código usan para comunicarse con el Common Language Runtime (CLR) para controlar la supervisión de eventos y la información de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="180d9-104">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="180d9-105">.</span><span class="sxs-lookup"><span data-stu-id="180d9-105">.</span></span> <span data-ttu-id="180d9-106">La `ICorProfilerInfo4` interfaz es una extensión de las otras `ICorProfilerInfo` interfaces.</span><span class="sxs-lookup"><span data-stu-id="180d9-106">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="180d9-107">Proporciona nuevos métodos para admitir la recompilación Just-in-Time (JIT), agregada en el .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="180d9-107">It provides new methods to support just-in-time (JIT) recompilation, added in the .NET Framework 4.5.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="180d9-108">Métodos</span><span class="sxs-lookup"><span data-stu-id="180d9-108">Methods</span></span>  
  
|<span data-ttu-id="180d9-109">Método</span><span class="sxs-lookup"><span data-stu-id="180d9-109">Method</span></span>|<span data-ttu-id="180d9-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="180d9-110">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="180d9-111">Método EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="180d9-111">EnumJITedFunctions2 Method</span></span>](icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="180d9-112">Devuelve un enumerador para todas las funciones compiladas previamente y compiladas con JIT.</span><span class="sxs-lookup"><span data-stu-id="180d9-112">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="180d9-113">Método EnumThreads</span><span class="sxs-lookup"><span data-stu-id="180d9-113">EnumThreads Method</span></span>](icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="180d9-114">Obtiene un enumerador que proporciona métodos para recorrer secuencialmente en iteración la colección de todos los subprocesos administrados en el proceso de la que se van a realizar perfiles.</span><span class="sxs-lookup"><span data-stu-id="180d9-114">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="180d9-115">Método GetCodeInfo3</span><span class="sxs-lookup"><span data-stu-id="180d9-115">GetCodeInfo3 Method</span></span>](icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="180d9-116">Obtiene las extensiones de código nativo asociadas con la versión recompilada con JIT de la función especificada.</span><span class="sxs-lookup"><span data-stu-id="180d9-116">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="180d9-117">Método GetFunctionFromIP2</span><span class="sxs-lookup"><span data-stu-id="180d9-117">GetFunctionFromIP2 Method</span></span>](icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="180d9-118">Asigna un puntero de instrucción de código administrado a la versión recompilada con JIT de una función especificada.</span><span class="sxs-lookup"><span data-stu-id="180d9-118">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="180d9-119">Método GetILToNativeMapping2</span><span class="sxs-lookup"><span data-stu-id="180d9-119">GetILToNativeMapping2 Method</span></span>](icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="180d9-120">Obtiene una asignación de los desplazamientos del lenguaje intermedio de Microsoft (MSIL) a los desplazamientos nativos para el código contenido en la versión recompilada con JIT de la función especificada.</span><span class="sxs-lookup"><span data-stu-id="180d9-120">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="180d9-121">Método GetObjectSize2</span><span class="sxs-lookup"><span data-stu-id="180d9-121">GetObjectSize2 Method</span></span>](icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="180d9-122">Devuelve el tamaño de un objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="180d9-122">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="180d9-123">Método GetReJITIDs</span><span class="sxs-lookup"><span data-stu-id="180d9-123">GetReJITIDs Method</span></span>](icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="180d9-124">Devuelve una matriz de identificadores que identifican todas las versiones compiladas con JIT de la función especificada que se siguen asignando.</span><span class="sxs-lookup"><span data-stu-id="180d9-124">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="180d9-125">Método InitializeCurrentThread</span><span class="sxs-lookup"><span data-stu-id="180d9-125">InitializeCurrentThread Method</span></span>](icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="180d9-126">Inicializa el subproceso actual antes de las llamadas posteriores a la API del generador de perfiles en el mismo subproceso, de modo que se pueda evitar el interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="180d9-126">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="180d9-127">Método RequestReJIT</span><span class="sxs-lookup"><span data-stu-id="180d9-127">RequestReJIT Method</span></span>](icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="180d9-128">Solicita una recompilación con JIT de todas las instancias de las funciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="180d9-128">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="180d9-129">Método RequestRevert</span><span class="sxs-lookup"><span data-stu-id="180d9-129">RequestRevert Method</span></span>](icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="180d9-130">Revierte todas las instancias de las funciones especificadas a sus versiones originales.</span><span class="sxs-lookup"><span data-stu-id="180d9-130">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="180d9-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="180d9-131">Remarks</span></span>  

 <span data-ttu-id="180d9-132">El CLR implementa los métodos de la interfaz `ICorProfilerInfo4` usando el modelo de subprocesamiento libre.</span><span class="sxs-lookup"><span data-stu-id="180d9-132">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="180d9-133">Cada método devuelve un valor HRESULT para indicar un resultado correcto o erróneo.</span><span class="sxs-lookup"><span data-stu-id="180d9-133">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="180d9-134">Para obtener una lista de los posibles códigos devueltos, consulte el archivo CorError.h.</span><span class="sxs-lookup"><span data-stu-id="180d9-134">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="180d9-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="180d9-135">Requirements</span></span>  

 <span data-ttu-id="180d9-136">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="180d9-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="180d9-137">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="180d9-137">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="180d9-138">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="180d9-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="180d9-139">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="180d9-139">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="180d9-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="180d9-140">See also</span></span>

- [<span data-ttu-id="180d9-141">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="180d9-141">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="180d9-142">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="180d9-142">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
