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
ms.openlocfilehash: c287b630aee58c6795ef405cc1801149e220fd51
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868426"
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="840e8-102">ICorProfilerInfo4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="840e8-102">ICorProfilerInfo4 Interface</span></span>
<span data-ttu-id="840e8-103">Proporciona métodos que los perfiles de código usan para comunicarse con el Common Language Runtime (CLR) para controlar la supervisión de eventos y la información de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="840e8-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="840e8-104">.</span><span class="sxs-lookup"><span data-stu-id="840e8-104">.</span></span> <span data-ttu-id="840e8-105">La interfaz de `ICorProfilerInfo4` es una extensión de las otras interfaces de `ICorProfilerInfo`.</span><span class="sxs-lookup"><span data-stu-id="840e8-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="840e8-106">Proporciona nuevos métodos para admitir la recompilación Just-in-Time (JIT), agregada en el .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="840e8-106">It provides new methods to support just-in-time (JIT) recompilation, added in the .NET Framework 4.5.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="840e8-107">Métodos</span><span class="sxs-lookup"><span data-stu-id="840e8-107">Methods</span></span>  
  
|<span data-ttu-id="840e8-108">Método</span><span class="sxs-lookup"><span data-stu-id="840e8-108">Method</span></span>|<span data-ttu-id="840e8-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="840e8-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="840e8-110">EnumJITedFunctions2 (método)</span><span class="sxs-lookup"><span data-stu-id="840e8-110">EnumJITedFunctions2 Method</span></span>](icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="840e8-111">Devuelve un enumerador para todas las funciones compiladas previamente y compiladas con JIT.</span><span class="sxs-lookup"><span data-stu-id="840e8-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="840e8-112">EnumThreads (método)</span><span class="sxs-lookup"><span data-stu-id="840e8-112">EnumThreads Method</span></span>](icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="840e8-113">Obtiene un enumerador que proporciona métodos para recorrer secuencialmente en iteración la colección de todos los subprocesos administrados en el proceso de la que se van a realizar perfiles.</span><span class="sxs-lookup"><span data-stu-id="840e8-113">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="840e8-114">GetCodeInfo3 (método)</span><span class="sxs-lookup"><span data-stu-id="840e8-114">GetCodeInfo3 Method</span></span>](icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="840e8-115">Obtiene las extensiones de código nativo asociadas con la versión recompilada con JIT de la función especificada.</span><span class="sxs-lookup"><span data-stu-id="840e8-115">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="840e8-116">GetFunctionFromIP2 (método)</span><span class="sxs-lookup"><span data-stu-id="840e8-116">GetFunctionFromIP2 Method</span></span>](icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="840e8-117">Asigna un puntero de instrucción de código administrado a la versión recompilada con JIT de una función especificada.</span><span class="sxs-lookup"><span data-stu-id="840e8-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="840e8-118">GetILToNativeMapping2 (método)</span><span class="sxs-lookup"><span data-stu-id="840e8-118">GetILToNativeMapping2 Method</span></span>](icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="840e8-119">Obtiene una asignación de los desplazamientos del lenguaje intermedio de Microsoft (MSIL) a los desplazamientos nativos para el código contenido en la versión recompilada con JIT de la función especificada.</span><span class="sxs-lookup"><span data-stu-id="840e8-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="840e8-120">GetObjectSize2 (método)</span><span class="sxs-lookup"><span data-stu-id="840e8-120">GetObjectSize2 Method</span></span>](icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="840e8-121">Devuelve el tamaño de un objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="840e8-121">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="840e8-122">GetReJITIDs (método)</span><span class="sxs-lookup"><span data-stu-id="840e8-122">GetReJITIDs Method</span></span>](icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="840e8-123">Devuelve una matriz de identificadores que identifican todas las versiones compiladas con JIT de la función especificada que se siguen asignando.</span><span class="sxs-lookup"><span data-stu-id="840e8-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="840e8-124">InitializeCurrentThread (método)</span><span class="sxs-lookup"><span data-stu-id="840e8-124">InitializeCurrentThread Method</span></span>](icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="840e8-125">Inicializa el subproceso actual antes de las llamadas posteriores a la API del generador de perfiles en el mismo subproceso, de modo que se pueda evitar el interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="840e8-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="840e8-126">RequestReJIT (método)</span><span class="sxs-lookup"><span data-stu-id="840e8-126">RequestReJIT Method</span></span>](icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="840e8-127">Solicita una recompilación con JIT de todas las instancias de las funciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="840e8-127">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="840e8-128">RequestRevert (método)</span><span class="sxs-lookup"><span data-stu-id="840e8-128">RequestRevert Method</span></span>](icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="840e8-129">Revierte todas las instancias de las funciones especificadas a sus versiones originales.</span><span class="sxs-lookup"><span data-stu-id="840e8-129">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="840e8-130">Notas</span><span class="sxs-lookup"><span data-stu-id="840e8-130">Remarks</span></span>  
 <span data-ttu-id="840e8-131">El CLR implementa los métodos de la interfaz `ICorProfilerInfo4` usando el modelo de subprocesamiento libre.</span><span class="sxs-lookup"><span data-stu-id="840e8-131">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="840e8-132">Cada método devuelve un valor HRESULT para indicar un resultado correcto o erróneo.</span><span class="sxs-lookup"><span data-stu-id="840e8-132">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="840e8-133">Para obtener una lista de los posibles códigos devueltos, consulte el archivo CorError.h.</span><span class="sxs-lookup"><span data-stu-id="840e8-133">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="840e8-134">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="840e8-134">Requirements</span></span>  
 <span data-ttu-id="840e8-135">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="840e8-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="840e8-136">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="840e8-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="840e8-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="840e8-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="840e8-138">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="840e8-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="840e8-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="840e8-139">See also</span></span>

- [<span data-ttu-id="840e8-140">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="840e8-140">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="840e8-141">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="840e8-141">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
