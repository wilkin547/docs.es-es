---
title: Funciones estáticas globales para generación de perfiles
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
ms.openlocfilehash: 1b0ad42e6b34e99212e112f6a594b0a36b6715e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723082"
---
# <a name="profiling-global-static-functions"></a><span data-ttu-id="f1155-102">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f1155-102">Profiling Global Static Functions</span></span>

<span data-ttu-id="f1155-103">En esta sección se describen las funciones de la API no administradas que utiliza la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="f1155-103">This section describes the unmanaged API functions that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f1155-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f1155-104">In This Section</span></span>  
  
## <a name="net-framework-version-1-profiling-functions"></a><span data-ttu-id="f1155-105">Funciones de generación de perfiles de .NET Framework versión 1</span><span class="sxs-lookup"><span data-stu-id="f1155-105">.NET Framework version 1 Profiling Functions</span></span>  

 [<span data-ttu-id="f1155-106">FunctionEnter (Función)</span><span class="sxs-lookup"><span data-stu-id="f1155-106">FunctionEnter Function</span></span>](functionenter-function.md)  
 <span data-ttu-id="f1155-107">Notifica al generador de perfiles que el control se pasa a una función.</span><span class="sxs-lookup"><span data-stu-id="f1155-107">Notifies the profiler that control is being passed to a function.</span></span> <span data-ttu-id="f1155-108">En desuso en el .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="f1155-108">Deprecated in the .NET Framework 2.0.</span></span>  
  
 [<span data-ttu-id="f1155-109">FunctionLeave (Función)</span><span class="sxs-lookup"><span data-stu-id="f1155-109">FunctionLeave Function</span></span>](functionleave-function.md)  
 <span data-ttu-id="f1155-110">Notifica al generador de perfiles que una función está a punto de volver al llamador.</span><span class="sxs-lookup"><span data-stu-id="f1155-110">Notifies the profiler that a function is about to return to the caller.</span></span> <span data-ttu-id="f1155-111">En desuso en el .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="f1155-111">Deprecated in the .NET Framework 2.0.</span></span>  
  
 [<span data-ttu-id="f1155-112">FunctionTailcall (Función)</span><span class="sxs-lookup"><span data-stu-id="f1155-112">FunctionTailcall Function</span></span>](functiontailcall-function.md)  
 <span data-ttu-id="f1155-113">Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función.</span><span class="sxs-lookup"><span data-stu-id="f1155-113">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span> <span data-ttu-id="f1155-114">En desuso en el .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="f1155-114">Deprecated in the .NET Framework 2.0.</span></span>  
  
## <a name="net-framework-version-2-profiling-functions"></a><span data-ttu-id="f1155-115">Funciones de generación de perfiles de .NET Framework versión 2</span><span class="sxs-lookup"><span data-stu-id="f1155-115">.NET Framework version 2 Profiling Functions</span></span>  

 [<span data-ttu-id="f1155-116">FunctionIDMapper (Función)</span><span class="sxs-lookup"><span data-stu-id="f1155-116">FunctionIDMapper Function</span></span>](functionidmapper-function.md)  
 <span data-ttu-id="f1155-117">Notifica al generador de perfiles que el identificador especificado de una función puede reasignarse a un identificador alternativo que se va a usar en las devoluciones de llamada [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)y [FunctionTailcall2](functiontailcall2-function.md) para esa función.</span><span class="sxs-lookup"><span data-stu-id="f1155-117">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="f1155-118">También permite al generador de perfiles indicar si desea recibir devoluciones de llamada para esa función.</span><span class="sxs-lookup"><span data-stu-id="f1155-118">Also enables the profiler to indicate whether it wants to receive callbacks for that function</span></span>  
  
 [<span data-ttu-id="f1155-119">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="f1155-119">FunctionEnter2 Function</span></span>](functionenter2-function.md)  
 <span data-ttu-id="f1155-120">Notifica al generador de perfiles que el control se pasa a una función y proporciona información sobre el marco de pila y los argumentos de la función.</span><span class="sxs-lookup"><span data-stu-id="f1155-120">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="f1155-121">En desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f1155-121">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="f1155-122">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="f1155-122">FunctionLeave2 Function</span></span>](functionleave2-function.md)  
 <span data-ttu-id="f1155-123">Notifica al generador de perfiles que una función está a punto de volver al autor de la llamada y proporciona información sobre el marco de pila y el valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="f1155-123">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span> <span data-ttu-id="f1155-124">En desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f1155-124">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="f1155-125">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="f1155-125">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)  
 <span data-ttu-id="f1155-126">Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función y proporciona información sobre el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="f1155-126">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span> <span data-ttu-id="f1155-127">En desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f1155-127">Deprecated in the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="f1155-128">StackSnapshotCallback (Función)</span><span class="sxs-lookup"><span data-stu-id="f1155-128">StackSnapshotCallback Function</span></span>](stacksnapshotcallback-function.md)  
 <span data-ttu-id="f1155-129">Proporciona al generador de perfiles información sobre cada marco administrado y cada ejecución de marcos no administrados en la pila durante un recorrido de pila, iniciado por el método [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f1155-129">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="net-framework-version-4-profiling-functions"></a><span data-ttu-id="f1155-130">Funciones de generación de perfiles de .NET Framework versión 4</span><span class="sxs-lookup"><span data-stu-id="f1155-130">.NET Framework version 4 Profiling Functions</span></span>  

 [<span data-ttu-id="f1155-131">FunctionIDMapper2 (Función)</span><span class="sxs-lookup"><span data-stu-id="f1155-131">FunctionIDMapper2 Function</span></span>](functionidmapper2-function.md)  
 <span data-ttu-id="f1155-132">Notifica al generador de perfiles que el identificador especificado de una función puede reasignarse a un identificador alternativo que se va a usar en las devoluciones de llamada [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), [FunctionTailcall3](functiontailcall3-function.md)o[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)y [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) de esa función.</span><span class="sxs-lookup"><span data-stu-id="f1155-132">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md), or[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="f1155-133">También permite al generador de perfiles indicar si desea recibir devoluciones de llamada para esa función.</span><span class="sxs-lookup"><span data-stu-id="f1155-133">Also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
 <span data-ttu-id="f1155-134">`FunctionIDMapper2` extiende la función [FunctionIDMapper](functionidmapper-function.md) con un `clientData` parámetro, que los subarchivos pueden usar para eliminar la ambigüedad entre los tiempos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f1155-134">`FunctionIDMapper2` extends the [FunctionIDMapper](functionidmapper-function.md) function with a `clientData` parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
 [<span data-ttu-id="f1155-135">FunctionEnter3 (Función)</span><span class="sxs-lookup"><span data-stu-id="f1155-135">FunctionEnter3 Function</span></span>](functionenter3-function.md)  
 <span data-ttu-id="f1155-136">Notifica al generador de perfiles que el control se pasa a una función.</span><span class="sxs-lookup"><span data-stu-id="f1155-136">Notifies the profiler that control is being passed to a function.</span></span>  
  
 [<span data-ttu-id="f1155-137">FunctionEnter3WithInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="f1155-137">FunctionEnter3WithInfo Function</span></span>](functionenter3withinfo-function.md)  
 <span data-ttu-id="f1155-138">Notifica al generador de perfiles que el control se pasa a una función y proporciona un identificador que se puede pasar a [ICorProfilerInfo3:: GetFunctionEnter3Info (](icorprofilerinfo3-getfunctionenter3info-method.md) para recuperar el marco de pila y los argumentos de la función.</span><span class="sxs-lookup"><span data-stu-id="f1155-138">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
 [<span data-ttu-id="f1155-139">FunctionLeave3 (Función)</span><span class="sxs-lookup"><span data-stu-id="f1155-139">FunctionLeave3 Function</span></span>](functionleave3-function.md)  
 <span data-ttu-id="f1155-140">Notifica al generador de perfiles que el control se devuelve desde una función.</span><span class="sxs-lookup"><span data-stu-id="f1155-140">Notifies the profiler that control is being returned from a function.</span></span>  
  
 [<span data-ttu-id="f1155-141">FunctionLeave3WithInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="f1155-141">FunctionLeave3WithInfo Function</span></span>](functionleave3withinfo-function.md)  
 <span data-ttu-id="f1155-142">Notifica al generador de perfiles que el control se devuelve desde una función y proporciona un identificador que se puede pasar a [ICorProfilerInfo3:: GetFunctionLeave3Info (](icorprofilerinfo3-getfunctionleave3info-method.md) para recuperar el marco de pila y el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="f1155-142">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
 [<span data-ttu-id="f1155-143">FunctionTailcall3 (Función)</span><span class="sxs-lookup"><span data-stu-id="f1155-143">FunctionTailcall3 Function</span></span>](functiontailcall3-function.md)  
 <span data-ttu-id="f1155-144">Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función.</span><span class="sxs-lookup"><span data-stu-id="f1155-144">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
 [<span data-ttu-id="f1155-145">FunctionTailcall3WithInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="f1155-145">FunctionTailcall3WithInfo Function</span></span>](functiontailcall3withinfo-function.md)  
 <span data-ttu-id="f1155-146">Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función y proporciona un identificador que se puede pasar a [ICorProfilerInfo3:: GetFunctionTailcall3Info (](icorprofilerinfo3-getfunctiontailcall3info-method.md) para recuperar el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="f1155-146">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to [ICorProfilerInfo3::GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f1155-147">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="f1155-147">Related Sections</span></span>  

 [<span data-ttu-id="f1155-148">Información general sobre la generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f1155-148">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="f1155-149">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f1155-149">Profiling Interfaces</span></span>](profiling-interfaces.md)  
  
 [<span data-ttu-id="f1155-150">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f1155-150">Profiling Enumerations</span></span>](profiling-enumerations.md)  
  
 [<span data-ttu-id="f1155-151">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f1155-151">Profiling Structures</span></span>](profiling-structures.md)
