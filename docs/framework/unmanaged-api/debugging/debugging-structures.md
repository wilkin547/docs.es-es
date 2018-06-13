---
title: Estructuras de depuración
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c7415920d34fc231bf82dd00199c7e01eec7a73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408117"
---
# <a name="debugging-structures"></a><span data-ttu-id="c54d8-102">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="c54d8-102">Debugging Structures</span></span>
<span data-ttu-id="c54d8-103">En esta sección se describen las estructuras no administradas que utiliza la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="c54d8-103">This section describes the unmanaged structures that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c54d8-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c54d8-104">In This Section</span></span>  
 [<span data-ttu-id="c54d8-105">CLR_DEBUGGING_VERSION (estructura)</span><span class="sxs-lookup"><span data-stu-id="c54d8-105">CLR_DEBUGGING_VERSION Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md)  
 <span data-ttu-id="c54d8-106">Define la versión de producto de Common Language Runtime (CLR) con fines de depuración.</span><span class="sxs-lookup"><span data-stu-id="c54d8-106">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
 [<span data-ttu-id="c54d8-107">CodeChunkInfo (estructura1)</span><span class="sxs-lookup"><span data-stu-id="c54d8-107">CodeChunkInfo Structure1</span></span>](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md)  
 <span data-ttu-id="c54d8-108">Representa un único fragmento de código en la memoria.</span><span class="sxs-lookup"><span data-stu-id="c54d8-108">Represents a single chunk of code in memory.</span></span>  
  
 [<span data-ttu-id="c54d8-109">CorDebugBlockingObject (estructura)</span><span class="sxs-lookup"><span data-stu-id="c54d8-109">CorDebugBlockingObject Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)  
 <span data-ttu-id="c54d8-110">Define un objeto que está bloqueando un subproceso y el motivo por el que el subproceso está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="c54d8-110">Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>  
  
 [<span data-ttu-id="c54d8-111">CorDebugEHClause (estructura)</span><span class="sxs-lookup"><span data-stu-id="c54d8-111">CorDebugEHClause Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)  
 <span data-ttu-id="c54d8-112">Representa una cláusula de control de excepciones (EH) para una parte determinada de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="c54d8-112">Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>  
  
 [<span data-ttu-id="c54d8-113">CorDebugExceptionObjectStackFrame (estructura)</span><span class="sxs-lookup"><span data-stu-id="c54d8-113">CorDebugExceptionObjectStackFrame Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 <span data-ttu-id="c54d8-114">Representa información del marco de pila de un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="c54d8-114">Represents stack frame information from an exception object.</span></span>  
  
 [<span data-ttu-id="c54d8-115">CorDebugExceptionObjectStackFrame (estructura)</span><span class="sxs-lookup"><span data-stu-id="c54d8-115">CorDebugExceptionObjectStackFrame Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 <span data-ttu-id="c54d8-116">Se asigna un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID para el correspondiente [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="c54d8-116">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) object.</span></span>  
  
 <span data-ttu-id="c54d8-117">COR_ACTIVE_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="c54d8-117">COR_ACTIVE_FUNCTION</span></span>  
 <span data-ttu-id="c54d8-118">Contiene información sobre las funciones que están actualmente activas en los marcos de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="c54d8-118">Contains information about the functions that are currently active in a thread's frames.</span></span>  
  
 [<span data-ttu-id="c54d8-119">COR_ARRAY_LAYOUT (estructura)</span><span class="sxs-lookup"><span data-stu-id="c54d8-119">COR_ARRAY_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md)  
 <span data-ttu-id="c54d8-120">Proporciona información sobre la distribución de un objeto de matriz en la memoria.</span><span class="sxs-lookup"><span data-stu-id="c54d8-120">Provides information about the layout of an array object in memory.</span></span>  
  
 <span data-ttu-id="c54d8-121">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="c54d8-121">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
 <span data-ttu-id="c54d8-122">Contiene los desplazamientos que se usan para asignar código de lenguaje intermedio de Microsoft (MSIL) a código nativo.</span><span class="sxs-lookup"><span data-stu-id="c54d8-122">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
 <span data-ttu-id="c54d8-123">COR_DEBUG_STEP_RANGE</span><span class="sxs-lookup"><span data-stu-id="c54d8-123">COR_DEBUG_STEP_RANGE</span></span>  
 <span data-ttu-id="c54d8-124">Contiene información de desplazamiento para un intervalo de código.</span><span class="sxs-lookup"><span data-stu-id="c54d8-124">Contains the offset information for a range of code.</span></span>  
  
 [<span data-ttu-id="c54d8-125">COR_FIELD (estructura)</span><span class="sxs-lookup"><span data-stu-id="c54d8-125">COR_FIELD Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)  
 <span data-ttu-id="c54d8-126">Proporciona información sobre un campo en un objeto.</span><span class="sxs-lookup"><span data-stu-id="c54d8-126">Provides information about a field in an object.</span></span>  
  
 [<span data-ttu-id="c54d8-127">COR_GC_REFERENCE (estructura)</span><span class="sxs-lookup"><span data-stu-id="c54d8-127">COR_GC_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)  
 <span data-ttu-id="c54d8-128">Contiene información sobre un objeto que se va a recolectar con elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="c54d8-128">Contains information about an object that is to be garbage-collected.</span></span>  
  
 [<span data-ttu-id="c54d8-129">COR_HEAPINFO (estructura)</span><span class="sxs-lookup"><span data-stu-id="c54d8-129">COR_HEAPINFO Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)  
 <span data-ttu-id="c54d8-130">Proporciona información general sobre el montón de recolección de elementos no utilizados, incluido si es enumerable.</span><span class="sxs-lookup"><span data-stu-id="c54d8-130">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
 [<span data-ttu-id="c54d8-131">COR_HEAPOBJECT (estructura)</span><span class="sxs-lookup"><span data-stu-id="c54d8-131">COR_HEAPOBJECT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)  
 <span data-ttu-id="c54d8-132">Proporciona información sobre un objeto del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="c54d8-132">Provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="c54d8-133">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="c54d8-133">COR_IL_MAP</span></span>  
 <span data-ttu-id="c54d8-134">Especifica los cambios en el desplazamiento relativo de una función.</span><span class="sxs-lookup"><span data-stu-id="c54d8-134">Specifies changes in the relative offset of a function.</span></span>  
  
 [<span data-ttu-id="c54d8-135">COR_SEGMENT (estructura)</span><span class="sxs-lookup"><span data-stu-id="c54d8-135">COR_SEGMENT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)  
 <span data-ttu-id="c54d8-136">Contiene información sobre una región de memoria en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="c54d8-136">Contains information about a region of memory in the managed heap.</span></span>  
  
 [<span data-ttu-id="c54d8-137">COR_TYPEID (estructura)</span><span class="sxs-lookup"><span data-stu-id="c54d8-137">COR_TYPEID Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)  
 <span data-ttu-id="c54d8-138">Contiene un identificador de tipos.</span><span class="sxs-lookup"><span data-stu-id="c54d8-138">Contains a type identifier.</span></span>  
  
 [<span data-ttu-id="c54d8-139">COR_TYPE_LAYOUT (estructura)</span><span class="sxs-lookup"><span data-stu-id="c54d8-139">COR_TYPE_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)  
 <span data-ttu-id="c54d8-140">Proporciona información sobre la distribución de un objeto en la memoria.</span><span class="sxs-lookup"><span data-stu-id="c54d8-140">Provides information about the layout of an object in memory.</span></span>  
  
 <span data-ttu-id="c54d8-141">COR_VERSION</span><span class="sxs-lookup"><span data-stu-id="c54d8-141">COR_VERSION</span></span>  
 <span data-ttu-id="c54d8-142">Almacena la versión estándar en cuatro partes de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="c54d8-142">Stores the standard four-part version number of the common language runtime.</span></span>  
  
 [<span data-ttu-id="c54d8-143">StackTrace_SimpleContext (estructura)</span><span class="sxs-lookup"><span data-stu-id="c54d8-143">StackTrace_SimpleContext Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md)  
 <span data-ttu-id="c54d8-144">Proporciona un contexto simple que se puede usar en lugar de una estructura `CONTEXT` completa.</span><span class="sxs-lookup"><span data-stu-id="c54d8-144">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c54d8-145">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c54d8-145">Related Sections</span></span>  
 [<span data-ttu-id="c54d8-146">Coclases para la depuración</span><span class="sxs-lookup"><span data-stu-id="c54d8-146">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="c54d8-147">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c54d8-147">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [<span data-ttu-id="c54d8-148">Funciones estáticas globales de depuración</span><span class="sxs-lookup"><span data-stu-id="c54d8-148">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="c54d8-149">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="c54d8-149">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [<span data-ttu-id="c54d8-150">Depuración</span><span class="sxs-lookup"><span data-stu-id="c54d8-150">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
