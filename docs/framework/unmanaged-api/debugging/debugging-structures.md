---
title: Estructuras de depuración
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
ms.openlocfilehash: a18094fb2621478dbdb4bbf672df436234112ed0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793755"
---
# <a name="debugging-structures"></a><span data-ttu-id="22a6d-102">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="22a6d-102">Debugging Structures</span></span>

<span data-ttu-id="22a6d-103">En esta sección se describen las estructuras no administradas que utiliza la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="22a6d-103">This section describes the unmanaged structures that the debugging API uses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="22a6d-104">Esta sección</span><span class="sxs-lookup"><span data-stu-id="22a6d-104">In This Section</span></span>
 <span data-ttu-id="22a6d-105">[Estructura de CLRDATA_ADDRESS_RANGE](clrdata-address-range-structure.md) Define un intervalo de direcciones.</span><span class="sxs-lookup"><span data-stu-id="22a6d-105">[CLRDATA_ADDRESS_RANGE Structure](clrdata-address-range-structure.md) Defines an address range.</span></span>

 <span data-ttu-id="22a6d-106">[Estructura de CLRDATA_IL_ADDRESS_MAP](clrdata-il-address-map-structure.md) Define una asignación de IL a dirección</span><span class="sxs-lookup"><span data-stu-id="22a6d-106">[CLRDATA_IL_ADDRESS_MAP Structure](clrdata-il-address-map-structure.md) Defines an IL to address mapping</span></span>

 <span data-ttu-id="22a6d-107">[Estructura de CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md) Define la versión del producto del Common Language Runtime (CLR) para fines de depuración.</span><span class="sxs-lookup"><span data-stu-id="22a6d-107">[CLR_DEBUGGING_VERSION Structure](clr-debugging-version-structure.md) Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>

 <span data-ttu-id="22a6d-108">[Estructura CodeChunkInfo (](codechunkinfo-structure.md) Representa un único fragmento de código en memoria.</span><span class="sxs-lookup"><span data-stu-id="22a6d-108">[CodeChunkInfo Structure](codechunkinfo-structure.md) Represents a single chunk of code in memory.</span></span>

 <span data-ttu-id="22a6d-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Contiene información sobre las funciones que están activas actualmente en los marcos de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="22a6d-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Contains information about the functions that are currently active in a thread's frames.</span></span>

 <span data-ttu-id="22a6d-110">[Estructura de COR_ARRAY_LAYOUT](cor-array-layout-structure.md) Proporciona información sobre el diseño de un objeto de matriz en la memoria.</span><span class="sxs-lookup"><span data-stu-id="22a6d-110">[COR_ARRAY_LAYOUT Structure](cor-array-layout-structure.md) Provides information about the layout of an array object in memory.</span></span>

 <span data-ttu-id="22a6d-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Contiene los desplazamientos que se usan para asignar código de lenguaje intermedio de Microsoft (MSIL) a código nativo.</span><span class="sxs-lookup"><span data-stu-id="22a6d-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>

 <span data-ttu-id="22a6d-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Contiene la información de desplazamiento para un intervalo de código.</span><span class="sxs-lookup"><span data-stu-id="22a6d-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Contains the offset information for a range of code.</span></span>

 <span data-ttu-id="22a6d-113">[Estructura de COR_FIELD](cor-field-structure.md) Proporciona información sobre un campo de un objeto.</span><span class="sxs-lookup"><span data-stu-id="22a6d-113">[COR_FIELD Structure](cor-field-structure.md) Provides information about a field in an object.</span></span>

 <span data-ttu-id="22a6d-114">[Estructura de COR_GC_REFERENCE](cor-gc-reference-structure.md) Contiene información sobre un objeto que se va a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="22a6d-114">[COR_GC_REFERENCE Structure](cor-gc-reference-structure.md) Contains information about an object that is to be garbage-collected.</span></span>

 <span data-ttu-id="22a6d-115">[Estructura de COR_HEAPINFO](cor-heapinfo-structure.md) Proporciona información general sobre el montón de recolección de elementos no utilizados, incluido si es Enumerable.</span><span class="sxs-lookup"><span data-stu-id="22a6d-115">[COR_HEAPINFO Structure](cor-heapinfo-structure.md) Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>

 <span data-ttu-id="22a6d-116">[Estructura de COR_HEAPOBJECT](cor-heapobject-structure.md) Proporciona información sobre un objeto en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="22a6d-116">[COR_HEAPOBJECT Structure](cor-heapobject-structure.md) Provides information about an object on the managed heap.</span></span>

 <span data-ttu-id="22a6d-117">[COR_IL_MAP](cor-il-map-structure.md) Especifica los cambios en el desplazamiento relativo de una función.</span><span class="sxs-lookup"><span data-stu-id="22a6d-117">[COR_IL_MAP](cor-il-map-structure.md) Specifies changes in the relative offset of a function.</span></span>

 <span data-ttu-id="22a6d-118">[Estructura de COR_SEGMENT](cor-segment-structure.md) Contiene información sobre una región de memoria en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="22a6d-118">[COR_SEGMENT Structure](cor-segment-structure.md) Contains information about a region of memory in the managed heap.</span></span>

 <span data-ttu-id="22a6d-119">[Estructura de COR_TYPEID](cor-typeid-structure.md) Contiene un identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="22a6d-119">[COR_TYPEID Structure](cor-typeid-structure.md) Contains a type identifier.</span></span>

 <span data-ttu-id="22a6d-120">[Estructura de COR_TYPE_LAYOUT](cor-type-layout-structure.md) Proporciona información sobre el diseño de un objeto en la memoria.</span><span class="sxs-lookup"><span data-stu-id="22a6d-120">[COR_TYPE_LAYOUT Structure](cor-type-layout-structure.md) Provides information about the layout of an object in memory.</span></span>

 <span data-ttu-id="22a6d-121">[COR_VERSION](cor-version-structure.md) Almacena el número de versión de cuatro partes estándar del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="22a6d-121">[COR_VERSION](cor-version-structure.md) Stores the standard four-part version number of the common language runtime.</span></span>

 <span data-ttu-id="22a6d-122">[CorDebugBlockingObject (estructura](cordebugblockingobject-structure.md) ) Define un objeto que está bloqueando un subproceso y el motivo por el que el subproceso está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="22a6d-122">[CorDebugBlockingObject Structure](cordebugblockingobject-structure.md) Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>

 <span data-ttu-id="22a6d-123">[Estructura cordebugehclause (](cordebugehclause-structure.md) Representa una cláusula de control de excepciones (EH) para una parte determinada del lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="22a6d-123">[CorDebugEHClause Structure](cordebugehclause-structure.md) Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>

 <span data-ttu-id="22a6d-124">[Estructura cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) Representa la información del marco de pila de un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="22a6d-124">[CorDebugExceptionObjectStackFrame Structure](cordebugexceptionobjectstackframe-structure.md) Represents stack frame information from an exception object.</span></span>

 <span data-ttu-id="22a6d-125">[Estructura cordebugguidtotypemapping (](cordebugguidtotypemapping-structure.md) Asigna un GUID de Windows Runtime a su objeto [ICorDebugType](icordebugtype-interface.md) correspondiente.</span><span class="sxs-lookup"><span data-stu-id="22a6d-125">[CorDebugGuidToTypeMapping Structure](cordebugguidtotypemapping-structure.md) Maps a Windows Runtime GUID to its corresponding [ICorDebugType](icordebugtype-interface.md) object.</span></span>

 <span data-ttu-id="22a6d-126">[Estructura DacpGetModuleAddress](dacpgetmoduleaddress-structure.md) Define el contenedor para una solicitud de dirección del módulo.</span><span class="sxs-lookup"><span data-stu-id="22a6d-126">[DacpGetModuleAddress Structure](dacpgetmoduleaddress-structure.md) Defines the container for a module address request.</span></span>

 <span data-ttu-id="22a6d-127">[Estructura DacpMethodDescData](dacpmethoddescdata-structure.md) Define un búfer de transporte para la información de tiempo de ejecución de un método.</span><span class="sxs-lookup"><span data-stu-id="22a6d-127">[DacpMethodDescData Structure](dacpmethoddescdata-structure.md) Defines a transport buffer for a method's runtime information.</span></span>

 <span data-ttu-id="22a6d-128">[Estructura DacpModuleData](dacpmoduledata-structure.md) Define un búfer de transporte para la información de tiempo de ejecución de un módulo.</span><span class="sxs-lookup"><span data-stu-id="22a6d-128">[DacpModuleData Structure](dacpmoduledata-structure.md) Defines a transport buffer for a module's runtime information.</span></span>

 <span data-ttu-id="22a6d-129">[Estructura DacpReJitData](dacprejitdata-structure.md) Define la información básica sobre un método instrumentado del generador de perfiles determinado.</span><span class="sxs-lookup"><span data-stu-id="22a6d-129">[DacpReJitData Structure](dacprejitdata-structure.md) Defines the basic information about a given profiler-instrumented method.</span></span>

 <span data-ttu-id="22a6d-130">[Estructura de StackTrace_SimpleContext](stacktrace-simplecontext-structure.md) Proporciona un contexto simple que se puede utilizar en lugar de una estructura de `CONTEXT` completa.</span><span class="sxs-lookup"><span data-stu-id="22a6d-130">[StackTrace_SimpleContext Structure](stacktrace-simplecontext-structure.md) Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>

## <a name="related-sections"></a><span data-ttu-id="22a6d-131">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="22a6d-131">Related Sections</span></span>

 [<span data-ttu-id="22a6d-132">Coclases para la depuración</span><span class="sxs-lookup"><span data-stu-id="22a6d-132">Debugging Coclasses</span></span>](debugging-coclasses.md)

 [<span data-ttu-id="22a6d-133">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="22a6d-133">Debugging Interfaces</span></span>](debugging-interfaces.md)

 [<span data-ttu-id="22a6d-134">Funciones estáticas globales de depuración</span><span class="sxs-lookup"><span data-stu-id="22a6d-134">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)

 [<span data-ttu-id="22a6d-135">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="22a6d-135">Debugging Enumerations</span></span>](debugging-enumerations.md)

 [<span data-ttu-id="22a6d-136">Depuración</span><span class="sxs-lookup"><span data-stu-id="22a6d-136">Debugging</span></span>](index.md)
