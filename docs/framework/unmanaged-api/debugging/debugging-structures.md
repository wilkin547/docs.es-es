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
ms.openlocfilehash: 23aa619d666f2e0b9eb67ab4cf8d4f92761865d3
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415330"
---
# <a name="debugging-structures"></a><span data-ttu-id="91ee0-102">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="91ee0-102">Debugging Structures</span></span>
<span data-ttu-id="91ee0-103">En esta sección se describen las estructuras no administradas que utiliza la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="91ee0-103">This section describes the unmanaged structures that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91ee0-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="91ee0-104">In This Section</span></span>  
 [<span data-ttu-id="91ee0-105">CLR_DEBUGGING_VERSION (estructura)</span><span class="sxs-lookup"><span data-stu-id="91ee0-105">CLR_DEBUGGING_VERSION Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md)  
 <span data-ttu-id="91ee0-106">Define la versión de producto de Common Language Runtime (CLR) con fines de depuración.</span><span class="sxs-lookup"><span data-stu-id="91ee0-106">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
 [<span data-ttu-id="91ee0-107">CodeChunkInfo (estructura1)</span><span class="sxs-lookup"><span data-stu-id="91ee0-107">CodeChunkInfo Structure1</span></span>](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md)  
 <span data-ttu-id="91ee0-108">Representa un único fragmento de código en la memoria.</span><span class="sxs-lookup"><span data-stu-id="91ee0-108">Represents a single chunk of code in memory.</span></span>  
  
 [<span data-ttu-id="91ee0-109">CorDebugBlockingObject (estructura)</span><span class="sxs-lookup"><span data-stu-id="91ee0-109">CorDebugBlockingObject Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)  
 <span data-ttu-id="91ee0-110">Define un objeto que está bloqueando un subproceso y el motivo por el que el subproceso está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="91ee0-110">Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>  
  
 [<span data-ttu-id="91ee0-111">CorDebugEHClause (estructura)</span><span class="sxs-lookup"><span data-stu-id="91ee0-111">CorDebugEHClause Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)  
 <span data-ttu-id="91ee0-112">Representa una cláusula de control de excepciones (EH) para una parte determinada de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="91ee0-112">Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>  
  
 [<span data-ttu-id="91ee0-113">CorDebugExceptionObjectStackFrame (estructura)</span><span class="sxs-lookup"><span data-stu-id="91ee0-113">CorDebugExceptionObjectStackFrame Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 <span data-ttu-id="91ee0-114">Representa información del marco de pila de un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="91ee0-114">Represents stack frame information from an exception object.</span></span>  
  
 [<span data-ttu-id="91ee0-115">CorDebugExceptionObjectStackFrame (estructura)</span><span class="sxs-lookup"><span data-stu-id="91ee0-115">CorDebugExceptionObjectStackFrame Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 <span data-ttu-id="91ee0-116">Se asigna un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID correspondiente [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="91ee0-116">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) object.</span></span>  
  
 <span data-ttu-id="91ee0-117">COR_ACTIVE_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="91ee0-117">COR_ACTIVE_FUNCTION</span></span>  
 <span data-ttu-id="91ee0-118">Contiene información sobre las funciones que están actualmente activas en los marcos de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="91ee0-118">Contains information about the functions that are currently active in a thread's frames.</span></span>  
  
 [<span data-ttu-id="91ee0-119">COR_ARRAY_LAYOUT (estructura)</span><span class="sxs-lookup"><span data-stu-id="91ee0-119">COR_ARRAY_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md)  
 <span data-ttu-id="91ee0-120">Proporciona información sobre la distribución de un objeto de matriz en la memoria.</span><span class="sxs-lookup"><span data-stu-id="91ee0-120">Provides information about the layout of an array object in memory.</span></span>  
  
 <span data-ttu-id="91ee0-121">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="91ee0-121">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
 <span data-ttu-id="91ee0-122">Contiene los desplazamientos que se usan para asignar código de lenguaje intermedio de Microsoft (MSIL) a código nativo.</span><span class="sxs-lookup"><span data-stu-id="91ee0-122">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
 <span data-ttu-id="91ee0-123">COR_DEBUG_STEP_RANGE</span><span class="sxs-lookup"><span data-stu-id="91ee0-123">COR_DEBUG_STEP_RANGE</span></span>  
 <span data-ttu-id="91ee0-124">Contiene información de desplazamiento para un intervalo de código.</span><span class="sxs-lookup"><span data-stu-id="91ee0-124">Contains the offset information for a range of code.</span></span>  
  
 [<span data-ttu-id="91ee0-125">COR_FIELD (estructura)</span><span class="sxs-lookup"><span data-stu-id="91ee0-125">COR_FIELD Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)  
 <span data-ttu-id="91ee0-126">Proporciona información sobre un campo en un objeto.</span><span class="sxs-lookup"><span data-stu-id="91ee0-126">Provides information about a field in an object.</span></span>  
  
 [<span data-ttu-id="91ee0-127">COR_GC_REFERENCE (estructura)</span><span class="sxs-lookup"><span data-stu-id="91ee0-127">COR_GC_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)  
 <span data-ttu-id="91ee0-128">Contiene información sobre un objeto que se va a recolectar con elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="91ee0-128">Contains information about an object that is to be garbage-collected.</span></span>  
  
 [<span data-ttu-id="91ee0-129">COR_HEAPINFO (estructura)</span><span class="sxs-lookup"><span data-stu-id="91ee0-129">COR_HEAPINFO Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)  
 <span data-ttu-id="91ee0-130">Proporciona información general sobre el montón de recolección de elementos no utilizados, incluido si es enumerable.</span><span class="sxs-lookup"><span data-stu-id="91ee0-130">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
 [<span data-ttu-id="91ee0-131">COR_HEAPOBJECT (estructura)</span><span class="sxs-lookup"><span data-stu-id="91ee0-131">COR_HEAPOBJECT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)  
 <span data-ttu-id="91ee0-132">Proporciona información sobre un objeto del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="91ee0-132">Provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="91ee0-133">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="91ee0-133">COR_IL_MAP</span></span>  
 <span data-ttu-id="91ee0-134">Especifica los cambios en el desplazamiento relativo de una función.</span><span class="sxs-lookup"><span data-stu-id="91ee0-134">Specifies changes in the relative offset of a function.</span></span>  
  
 [<span data-ttu-id="91ee0-135">COR_SEGMENT (estructura)</span><span class="sxs-lookup"><span data-stu-id="91ee0-135">COR_SEGMENT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)  
 <span data-ttu-id="91ee0-136">Contiene información sobre una región de memoria en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="91ee0-136">Contains information about a region of memory in the managed heap.</span></span>  
  
 [<span data-ttu-id="91ee0-137">COR_TYPEID (estructura)</span><span class="sxs-lookup"><span data-stu-id="91ee0-137">COR_TYPEID Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)  
 <span data-ttu-id="91ee0-138">Contiene un identificador de tipos.</span><span class="sxs-lookup"><span data-stu-id="91ee0-138">Contains a type identifier.</span></span>  
  
 [<span data-ttu-id="91ee0-139">COR_TYPE_LAYOUT (estructura)</span><span class="sxs-lookup"><span data-stu-id="91ee0-139">COR_TYPE_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)  
 <span data-ttu-id="91ee0-140">Proporciona información sobre la distribución de un objeto en la memoria.</span><span class="sxs-lookup"><span data-stu-id="91ee0-140">Provides information about the layout of an object in memory.</span></span>  
  
 <span data-ttu-id="91ee0-141">COR_VERSION</span><span class="sxs-lookup"><span data-stu-id="91ee0-141">COR_VERSION</span></span>  
 <span data-ttu-id="91ee0-142">Almacena la versión estándar en cuatro partes de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="91ee0-142">Stores the standard four-part version number of the common language runtime.</span></span>  
  
 [<span data-ttu-id="91ee0-143">StackTrace_SimpleContext (estructura)</span><span class="sxs-lookup"><span data-stu-id="91ee0-143">StackTrace_SimpleContext Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md)  
 <span data-ttu-id="91ee0-144">Proporciona un contexto simple que se puede usar en lugar de una estructura `CONTEXT` completa.</span><span class="sxs-lookup"><span data-stu-id="91ee0-144">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>

 <span data-ttu-id="91ee0-145">[Estructura CLRDATA_ADDRESS_RANGE](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) define un intervalo de direcciones.</span><span class="sxs-lookup"><span data-stu-id="91ee0-145">[CLRDATA_ADDRESS_RANGE Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) Defines an address range.</span></span>
 
 <span data-ttu-id="91ee0-146">[Estructura CLRDATA_IL_ADDRESS_MAP](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) define un IL para asignación de direcciones</span><span class="sxs-lookup"><span data-stu-id="91ee0-146">[CLRDATA_IL_ADDRESS_MAP Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) Defines an IL to address mapping</span></span>
 
 <span data-ttu-id="91ee0-147">[Estructura DacpGetModuleAddress](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) define el contenedor para una solicitud de dirección del módulo.</span><span class="sxs-lookup"><span data-stu-id="91ee0-147">[DacpGetModuleAddress Structure](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) Defines the container for a module address request.</span></span>

  
## <a name="related-sections"></a><span data-ttu-id="91ee0-148">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="91ee0-148">Related Sections</span></span>  
 [<span data-ttu-id="91ee0-149">Coclases para la depuración</span><span class="sxs-lookup"><span data-stu-id="91ee0-149">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="91ee0-150">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="91ee0-150">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [<span data-ttu-id="91ee0-151">Funciones estáticas globales de depuración</span><span class="sxs-lookup"><span data-stu-id="91ee0-151">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="91ee0-152">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="91ee0-152">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [<span data-ttu-id="91ee0-153">Depuración</span><span class="sxs-lookup"><span data-stu-id="91ee0-153">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
