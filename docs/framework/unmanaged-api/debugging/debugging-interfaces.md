---
title: Interfaces para depuración
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff589285d81a3febf887bba976b62a9ae4a573c8
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025947"
---
# <a name="debugging-interfaces"></a><span data-ttu-id="20025-102">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="20025-102">Debugging Interfaces</span></span>
<span data-ttu-id="20025-103">En esta sección se describen las interfaces no administradas que controlan la depuración de un programa que se ejecuta en Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="20025-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20025-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="20025-104">In This Section</span></span>  
 <span data-ttu-id="20025-105">[ICLRDataEnumMemoryRegions (interfaz)](iclrdataenummemoryregions-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-105">[ICLRDataEnumMemoryRegions Interface](iclrdataenummemoryregions-interface.md)</span></span>\
 <span data-ttu-id="20025-106">Proporciona un método para enumerar las regiones de memoria especificadas por los llamadores.</span><span class="sxs-lookup"><span data-stu-id="20025-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 <span data-ttu-id="20025-107">[ICLRDataEnumMemoryRegionsCallback (interfaz)](iclrdataenummemoryregionscallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-107">[ICLRDataEnumMemoryRegionsCallback Interface](iclrdataenummemoryregionscallback-interface.md)</span></span>\
 <span data-ttu-id="20025-108">Proporciona un método de devolución de llamada para que `EnumMemoryRegions` notifique al depurador el resultado de un intento de enumerar un área de memoria concreta.</span><span class="sxs-lookup"><span data-stu-id="20025-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 <span data-ttu-id="20025-109">[ICLRDataTarget (interfaz)](iclrdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-109">[ICLRDataTarget Interface](iclrdatatarget-interface.md)</span></span>\
 <span data-ttu-id="20025-110">Proporciona métodos para la interacción con un proceso de CLR de destino.</span><span class="sxs-lookup"><span data-stu-id="20025-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 <span data-ttu-id="20025-111">[ICLRDataTarget2 Interface](iclrdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-111">[ICLRDataTarget2 Interface](iclrdatatarget2-interface.md)</span></span>\
 <span data-ttu-id="20025-112">Subclase de `ICLRDataTarget` que se utiliza la capa de servicios de acceso a datos para manipular las áreas de la memoria virtual en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="20025-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 <span data-ttu-id="20025-113">[ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-113">[ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)</span></span>\
 <span data-ttu-id="20025-114">Una subclase de [ICLRDataTarget2](iclrdatatarget2-interface.md) que proporciona acceso a información de excepción.</span><span class="sxs-lookup"><span data-stu-id="20025-114">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 <span data-ttu-id="20025-115">[ICLRDebugging (interfaz)](iclrdebugging-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-115">[ICLRDebugging Interface](iclrdebugging-interface.md)</span></span>\
 <span data-ttu-id="20025-116">Proporciona métodos que controlan la carga y descarga de módulos para depuración.</span><span class="sxs-lookup"><span data-stu-id="20025-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 <span data-ttu-id="20025-117">[ICLRDebuggingLibraryProvider (interfaz)](iclrdebugginglibraryprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-117">[ICLRDebuggingLibraryProvider Interface](iclrdebugginglibraryprovider-interface.md)</span></span>\
 <span data-ttu-id="20025-118">Incluye el [ProvideLibrary (método)](iclrdebugginglibraryprovider-providelibrary-method.md) método, que obtiene un proveedor de la biblioteca de interfaz de devolución de llamada que permite a common language runtime bibliotecas de depuración específica de la versión a buscar y cargar a petición.</span><span class="sxs-lookup"><span data-stu-id="20025-118">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 <span data-ttu-id="20025-119">[ICLRMetadataLocator (interfaz)](iclrmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-119">[ICLRMetadataLocator Interface](iclrmetadatalocator-interface.md)</span></span>\
 <span data-ttu-id="20025-120">Interfaz utilizada por la capa de servicios de acceso a datos para buscar los metadatos de los ensamblados en un proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="20025-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 <span data-ttu-id="20025-121">[ICorDebug (interfaz)](icordebug-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-121">[ICorDebug Interface](icordebug-interface.md)</span></span>\
 <span data-ttu-id="20025-122">Proporciona métodos que permiten a los desarrolladores depurar las aplicaciones en el entorno de CLR.</span><span class="sxs-lookup"><span data-stu-id="20025-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="20025-123">[ICorDebugAppDomain (interfaz)](icordebugappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-123">[ICorDebugAppDomain Interface](icordebugappdomain-interface.md)</span></span>\
 <span data-ttu-id="20025-124">Proporciona métodos para depurar dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="20025-124">Provides methods for debugging application domains.</span></span>  
  
 <span data-ttu-id="20025-125">[ICorDebugAppDomain2 (interfaz)](icordebugappdomain2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-125">[ICorDebugAppDomain2 Interface](icordebugappdomain2-interface.md)</span></span>\
 <span data-ttu-id="20025-126">Proporciona métodos para trabajar con matrices, punteros, punteros a función y tipos ByRef.</span><span class="sxs-lookup"><span data-stu-id="20025-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="20025-127">Esta interfaz es una extensión de la interfaz `ICorDebugAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="20025-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 <span data-ttu-id="20025-128">[ICorDebugAppDomain3 (interfaz)](icordebugappdomain3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-128">[ICorDebugAppDomain3 Interface](icordebugappdomain3-interface.md)</span></span>\
 <span data-ttu-id="20025-129">Proporciona métodos para trabajar con los tipos en tiempo de ejecución de Windows en un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="20025-129">Provides methods to work with the Windows Runtime types in an application domain.</span></span> <span data-ttu-id="20025-130">Esta interfaz es una extensión de las interfaces `ICorDebugAppDomain` e `ICorDebugAppDomain2`.</span><span class="sxs-lookup"><span data-stu-id="20025-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 <span data-ttu-id="20025-131">[ICorDebugAppDomain4 (interfaz)](icordebugappdomain4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-131">[ICorDebugAppDomain4 Interface](icordebugappdomain4-interface.md)</span></span>\
 <span data-ttu-id="20025-132">Extiende lógicamente la [ICorDebugAppDomain](icordebugappdomain-interface.md) interfaz para obtener un objeto administrado desde un contenedor CCW.</span><span class="sxs-lookup"><span data-stu-id="20025-132">Logically extends the [ICorDebugAppDomain](icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 <span data-ttu-id="20025-133">[ICorDebugAppDomainEnum (interfaz)](icordebugappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-133">[ICorDebugAppDomainEnum Interface](icordebugappdomainenum-interface.md)</span></span>\
 <span data-ttu-id="20025-134">Proporciona un método que devuelve un número especificado de valores de `ICorDebugAppDomain` que comienzan en la siguiente posición de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="20025-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 <span data-ttu-id="20025-135">[ICorDebugArrayValue (interfaz)](icordebugarrayvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-135">[ICorDebugArrayValue Interface](icordebugarrayvalue-interface.md)</span></span>\
 <span data-ttu-id="20025-136">Subclase de `ICorDebugHeapValue` que representa una matriz unidimensional o multidimensional.</span><span class="sxs-lookup"><span data-stu-id="20025-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 <span data-ttu-id="20025-137">[ICorDebugAssembly (interfaz)](icordebugassembly-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-137">[ICorDebugAssembly Interface](icordebugassembly-interface.md)</span></span>\
 <span data-ttu-id="20025-138">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="20025-138">Represents an assembly.</span></span>  
  
 <span data-ttu-id="20025-139">[ICorDebugAssembly2 (interfaz)](icordebugassembly2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-139">[ICorDebugAssembly2 Interface](icordebugassembly2-interface.md)</span></span>\
 <span data-ttu-id="20025-140">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="20025-140">Represents an assembly.</span></span> <span data-ttu-id="20025-141">Esta interfaz es una extensión de la interfaz `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="20025-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 <span data-ttu-id="20025-142">[ICorDebugAssembly3 (interfaz)](icordebugassembly3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-142">[ICorDebugAssembly3 Interface](icordebugassembly3-interface.md)</span></span>\
 <span data-ttu-id="20025-143">Extiende lógicamente la [ICorDebugAssembly](icordebugassembly-interface.md) interfaz para proporcionar compatibilidad con los ensamblados de contenedor y los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="20025-143">Logically extends the [ICorDebugAssembly](icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="20025-144">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="20025-144">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="20025-145">[ICorDebugAssemblyEnum (interfaz)](icordebugassemblyenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-145">[ICorDebugAssemblyEnum Interface](icordebugassemblyenum-interface.md)</span></span>\
 <span data-ttu-id="20025-146">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="20025-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 <span data-ttu-id="20025-147">[ICorDebugBlockingObjectEnum (interfaz)](icordebugblockingobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-147">[ICorDebugBlockingObjectEnum Interface](icordebugblockingobjectenum-interface.md)</span></span>\
 <span data-ttu-id="20025-148">Proporciona un enumerador para una lista de [CorDebugBlockingObject](cordebugblockingobject-structure.md) estructuras.</span><span class="sxs-lookup"><span data-stu-id="20025-148">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
 <span data-ttu-id="20025-149">[ICorDebugBoxValue (interfaz)](icordebugboxvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-149">[ICorDebugBoxValue Interface](icordebugboxvalue-interface.md)</span></span>\
 <span data-ttu-id="20025-150">Subclase de `ICorDebugHeapValue` que representa un objeto de clase de valor al que se ha aplicado la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="20025-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 <span data-ttu-id="20025-151">[ICorDebugBreakpoint (interfaz)](icordebugbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-151">[ICorDebugBreakpoint Interface](icordebugbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="20025-152">Representa un punto de interrupción en una función o un punto de inspección en un valor.</span><span class="sxs-lookup"><span data-stu-id="20025-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 <span data-ttu-id="20025-153">[ICorDebugBreakpointEnum (interfaz)](icordebugbreakpointenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-153">[ICorDebugBreakpointEnum Interface](icordebugbreakpointenum-interface.md)</span></span>\
 <span data-ttu-id="20025-154">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="20025-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 <span data-ttu-id="20025-155">[ICorDebugChain (interfaz)](icordebugchain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-155">[ICorDebugChain Interface](icordebugchain-interface.md)</span></span>\
 <span data-ttu-id="20025-156">Representa un segmento de una pila de llamadas física o lógica.</span><span class="sxs-lookup"><span data-stu-id="20025-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 <span data-ttu-id="20025-157">[ICorDebugChainEnum (interfaz)](icordebugchainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-157">[ICorDebugChainEnum Interface](icordebugchainenum-interface.md)</span></span>\
 <span data-ttu-id="20025-158">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugChain`.</span><span class="sxs-lookup"><span data-stu-id="20025-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 <span data-ttu-id="20025-159">[ICorDebugClass (interfaz)](icordebugclass-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-159">[ICorDebugClass Interface](icordebugclass-interface.md)</span></span>\
 <span data-ttu-id="20025-160">Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="20025-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="20025-161">Si el tipo es genérico, `ICorDebugClass` representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="20025-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 <span data-ttu-id="20025-162">[ICorDebugClass2 (interfaz)](icordebugclass2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-162">[ICorDebugClass2 Interface](icordebugclass2-interface.md)</span></span>\
 <span data-ttu-id="20025-163">Representa una clase genérica o una clase con un parámetro de método de tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="20025-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="20025-164">Esta interfaz extiende `ICorDebugClass`.</span><span class="sxs-lookup"><span data-stu-id="20025-164">This interface extends `ICorDebugClass`.</span></span>  
  
 <span data-ttu-id="20025-165">[ICorDebugCode (interfaz)](icordebugcode-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="20025-165">[ICorDebugCode Interface](icordebugcode-interface1.md)</span></span>\
 <span data-ttu-id="20025-166">Representa un segmento de código de lenguaje intermedio de Microsoft (MSIL) o código nativo.</span><span class="sxs-lookup"><span data-stu-id="20025-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 <span data-ttu-id="20025-167">[ICorDebugCode2 (interfaz)](icordebugcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-167">[ICorDebugCode2 Interface](icordebugcode2-interface.md)</span></span>\
 <span data-ttu-id="20025-168">Proporciona métodos que amplían las funciones de `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="20025-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 <span data-ttu-id="20025-169">[ICorDebugCode3 (interfaz)](icordebugcode3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-169">[ICorDebugCode3 Interface](icordebugcode3-interface.md)</span></span>\
 <span data-ttu-id="20025-170">Proporciona un método que extiende [ICorDebugCode](icordebugcode-interface1.md) y [ICorDebugCode2](icordebugcode2-interface.md) para proporcionar información sobre un valor devuelto administrado.</span><span class="sxs-lookup"><span data-stu-id="20025-170">Provides a method that extends [ICorDebugCode](icordebugcode-interface1.md) and [ICorDebugCode2](icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 <span data-ttu-id="20025-171">[ICorDebugCode4 (interfaz)](icordebugcode4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-171">[ICorDebugCode4 Interface](icordebugcode4-interface.md)</span></span>\
 <span data-ttu-id="20025-172">Proporciona un método que permite a un depurador enumerar las variables locales y los argumentos en una función.</span><span class="sxs-lookup"><span data-stu-id="20025-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="20025-173">[ICorDebugCodeEnum (interfaz)](icordebugcodeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-173">[ICorDebugCodeEnum Interface](icordebugcodeenum-interface.md)</span></span>\
 <span data-ttu-id="20025-174">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="20025-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 <span data-ttu-id="20025-175">[ICorDebugComObjectValue (interfaz)](icordebugcomobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-175">[ICorDebugComObjectValue Interface](icordebugcomobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="20025-176">Proporciona métodos para recuperar objetos de la interfaz en caché.</span><span class="sxs-lookup"><span data-stu-id="20025-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 <span data-ttu-id="20025-177">[ICorDebugContext (interfaz)](icordebugcontext-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-177">[ICorDebugContext Interface](icordebugcontext-interface.md)</span></span>\
 <span data-ttu-id="20025-178">Representa un objeto de contexto.</span><span class="sxs-lookup"><span data-stu-id="20025-178">Represents a context object.</span></span> <span data-ttu-id="20025-179">Esta interfaz no se ha implementado todavía.</span><span class="sxs-lookup"><span data-stu-id="20025-179">This interface has not been implemented yet.</span></span>  
  
 <span data-ttu-id="20025-180">[ICorDebugController (interfaz)](icordebugcontroller-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-180">[ICorDebugController Interface](icordebugcontroller-interface.md)</span></span>\
 <span data-ttu-id="20025-181">Representa un ámbito, <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, en el que se puede controlar el contexto de ejecución de código.</span><span class="sxs-lookup"><span data-stu-id="20025-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 <span data-ttu-id="20025-182">[ICorDebugDataTarget (interfaz)](icordebugdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-182">[ICorDebugDataTarget Interface](icordebugdatatarget-interface.md)</span></span>\
 <span data-ttu-id="20025-183">Proporciona una interfaz de devolución de llamada que brinda acceso a un proceso de destino determinado.</span><span class="sxs-lookup"><span data-stu-id="20025-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 <span data-ttu-id="20025-184">[ICorDebugDataTarget2 (interfaz)](icordebugdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-184">[ICorDebugDataTarget2 Interface](icordebugdatatarget2-interface.md)</span></span>\
 <span data-ttu-id="20025-185">Extiende lógicamente la [ICorDebugDataTarget](icordebugdatatarget-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="20025-185">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="20025-186">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="20025-186">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="20025-187">[ICorDebugDataTarget3 (interfaz)](icordebugdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-187">[ICorDebugDataTarget3 Interface](icordebugdatatarget3-interface.md)</span></span>\
 <span data-ttu-id="20025-188">Extiende lógicamente la [ICorDebugDataTarget](icordebugdatatarget-interface.md) interfaz para proporcionar información sobre los módulos cargados.</span><span class="sxs-lookup"><span data-stu-id="20025-188">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="20025-189">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="20025-189">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="20025-190">[ICorDebugDebugEvent (interfaz)](icordebugdebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-190">[ICorDebugDebugEvent Interface](icordebugdebugevent-interface.md)</span></span>\
 <span data-ttu-id="20025-191">Define la interfaz base de la que derivan todos los eventos de depuración `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="20025-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="20025-192">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="20025-192">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="20025-193">[ICorDebugEditAndContinueErrorInfo (interfaz)](icordebugeditandcontinueerrorinfo-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-193">[ICorDebugEditAndContinueErrorInfo Interface](icordebugeditandcontinueerrorinfo-interface.md)</span></span>\
 <span data-ttu-id="20025-194">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="20025-194">Obsolete.</span></span> <span data-ttu-id="20025-195">No utilice esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="20025-195">Do not use this interface.</span></span>  
  
 <span data-ttu-id="20025-196">[ICorDebugEditAndContinueSnapshot (interfaz)](icordebugeditandcontinuesnapshot-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-196">[ICorDebugEditAndContinueSnapshot Interface](icordebugeditandcontinuesnapshot-interface.md)</span></span>\
 <span data-ttu-id="20025-197">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="20025-197">Obsolete.</span></span> <span data-ttu-id="20025-198">No utilice esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="20025-198">Do not use this interface.</span></span>  
  
 <span data-ttu-id="20025-199">[ICorDebugEnum (interfaz)](icordebugenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="20025-199">[ICorDebugEnum Interface](icordebugenum-interface1.md)</span></span>\
 <span data-ttu-id="20025-200">Actúa como la interfaz base abstracta para la depuración de enumeradores.</span><span class="sxs-lookup"><span data-stu-id="20025-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 <span data-ttu-id="20025-201">[ICorDebugErrorInfoEnum (interfaz)](icordebugerrorinfoenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-201">[ICorDebugErrorInfoEnum Interface](icordebugerrorinfoenum-interface.md)</span></span>\
 <span data-ttu-id="20025-202">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="20025-202">Obsolete.</span></span> <span data-ttu-id="20025-203">No utilice esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="20025-203">Do not use this interface.</span></span>  
  
 <span data-ttu-id="20025-204">[ICorDebugEval (interfaz)](icordebugeval-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-204">[ICorDebugEval Interface](icordebugeval-interface.md)</span></span>\
 <span data-ttu-id="20025-205">Proporciona métodos que permiten al depurador ejecutar código en el contexto del código que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="20025-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 <span data-ttu-id="20025-206">[ICorDebugEval2 (interfaz)](icordebugeval2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-206">[ICorDebugEval2 Interface](icordebugeval2-interface.md)</span></span>\
 <span data-ttu-id="20025-207">Extiende `ICorDebugEval` para proporcionar compatibilidad con los tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="20025-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 <span data-ttu-id="20025-208">[ICorDebugExceptionDebugEvent (interfaz)](icordebugexceptiondebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-208">[ICorDebugExceptionDebugEvent Interface](icordebugexceptiondebugevent-interface.md)</span></span>\
 <span data-ttu-id="20025-209">Extiende la [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interfaz para admitir eventos de excepción.</span><span class="sxs-lookup"><span data-stu-id="20025-209">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="20025-210">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="20025-210">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="20025-211">[ICorDebugExceptionObjectCallStackEnum (interfaz)](icordebugexceptionobjectcallstackenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-211">[ICorDebugExceptionObjectCallStackEnum Interface](icordebugexceptionobjectcallstackenum-interface.md)</span></span>\
 <span data-ttu-id="20025-212">Proporciona un enumerador para la información de la pila de llamadas que está incrustada en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="20025-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 <span data-ttu-id="20025-213">[ICorDebugExceptionObjectValue (interfaz)](icordebugexceptionobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-213">[ICorDebugExceptionObjectValue Interface](icordebugexceptionobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="20025-214">Extiende la [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interfaz para proporcionar información de seguimiento de pila de un objeto de excepción administrado.</span><span class="sxs-lookup"><span data-stu-id="20025-214">Extends the [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 <span data-ttu-id="20025-215">[ICorDebugFrame (interfaz)](icordebugframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-215">[ICorDebugFrame Interface](icordebugframe-interface.md)</span></span>\
 <span data-ttu-id="20025-216">Representa un marco en la pila actual.</span><span class="sxs-lookup"><span data-stu-id="20025-216">Represents a frame on the current stack.</span></span>  
  
 <span data-ttu-id="20025-217">[ICorDebugFrameEnum (interfaz)](icordebugframeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-217">[ICorDebugFrameEnum Interface](icordebugframeenum-interface.md)</span></span>\
 <span data-ttu-id="20025-218">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="20025-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 <span data-ttu-id="20025-219">[ICorDebugFunction (interfaz)](icordebugfunction-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="20025-219">[ICorDebugFunction Interface](icordebugfunction-interface1.md)</span></span>\
 <span data-ttu-id="20025-220">Representa una función o un método administrado.</span><span class="sxs-lookup"><span data-stu-id="20025-220">Represents a managed function or method.</span></span>  
  
 <span data-ttu-id="20025-221">[ICorDebugFunction2 (interfaz)](icordebugfunction2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-221">[ICorDebugFunction2 Interface](icordebugfunction2-interface.md)</span></span>\
 <span data-ttu-id="20025-222">Extiende `ICorDebugFunction` de manera lógica para ofrecer compatibilidad con la depuración paso a paso de "Sólo mi código".</span><span class="sxs-lookup"><span data-stu-id="20025-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 <span data-ttu-id="20025-223">[ICorDebugFunction3 (interfaz)](icordebugfunction3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-223">[ICorDebugFunction3 Interface](icordebugfunction3-interface.md)</span></span>\
 <span data-ttu-id="20025-224">Extiende lógicamente la [ICorDebugFunction](icordebugfunction-interface1.md) interfaz para proporcionar acceso a código desde una solicitud ReJIT.</span><span class="sxs-lookup"><span data-stu-id="20025-224">Logically extends the [ICorDebugFunction](icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 <span data-ttu-id="20025-225">[ICorDebugFunctionBreakpoint (interfaz)](icordebugfunctionbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-225">[ICorDebugFunctionBreakpoint Interface](icordebugfunctionbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="20025-226">Amplía `ICorDebugBreakpoint` para admitir los puntos de interrupción dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="20025-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 <span data-ttu-id="20025-227">[ICorDebugGCReferenceEnum (interfaz)](icordebuggcreferenceenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-227">[ICorDebugGCReferenceEnum Interface](icordebuggcreferenceenum-interface.md)</span></span>\
 <span data-ttu-id="20025-228">Proporciona un enumerador para los objetos que se recolectarán como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="20025-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 <span data-ttu-id="20025-229">[ICorDebugGenericValue (interfaz)](icordebuggenericvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-229">[ICorDebugGenericValue Interface](icordebuggenericvalue-interface.md)</span></span>\
 <span data-ttu-id="20025-230">Subclase de `ICorDebugValue` que se aplica a todos los valores.</span><span class="sxs-lookup"><span data-stu-id="20025-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="20025-231">Esta interfaz proporciona métodos Get y Set para el valor.</span><span class="sxs-lookup"><span data-stu-id="20025-231">This interface provides Get and Set methods for the value.</span></span>  
  
 <span data-ttu-id="20025-232">[ICorDebugGuidToTypeEnum (interfaz)](icordebugguidtotypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-232">[ICorDebugGuidToTypeEnum Interface](icordebugguidtotypeenum-interface.md)</span></span>\
 <span data-ttu-id="20025-233">Proporciona un enumerador para un objeto que asigna GUID y sus objetos `ICorDebugType` correspondientes.</span><span class="sxs-lookup"><span data-stu-id="20025-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 <span data-ttu-id="20025-234">[ICorDebugHandleValue (interfaz)](icordebughandlevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-234">[ICorDebugHandleValue Interface](icordebughandlevalue-interface.md)</span></span>\
 <span data-ttu-id="20025-235">Subclase de `ICorDebugReferenceValue` que representa un valor de referencia para el cual el depurador ha creado un identificador para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="20025-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 <span data-ttu-id="20025-236">[ICorDebugHeapEnum (interfaz)](icordebugheapenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-236">[ICorDebugHeapEnum Interface](icordebugheapenum-interface.md)</span></span>\
 <span data-ttu-id="20025-237">Proporciona un enumerador para los objetos del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="20025-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 <span data-ttu-id="20025-238">[ICorDebugHeapSegmentEnum (interfaz)](icordebugheapsegmentenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-238">[ICorDebugHeapSegmentEnum Interface](icordebugheapsegmentenum-interface.md)</span></span>\
 <span data-ttu-id="20025-239">Proporciona un enumerador para las regiones de memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="20025-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 <span data-ttu-id="20025-240">[ICorDebugHeapValue (interfaz)](icordebugheapvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-240">[ICorDebugHeapValue Interface](icordebugheapvalue-interface.md)</span></span>\
 <span data-ttu-id="20025-241">Subclase de `ICorDebugValue` que representa un objeto que ha sido recopilado por el recolector de elementos no utilizados de CLR.</span><span class="sxs-lookup"><span data-stu-id="20025-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 <span data-ttu-id="20025-242">[ICorDebugHeapValue2 (interfaz)](icordebugheapvalue2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="20025-242">[ICorDebugHeapValue2 Interface](icordebugheapvalue2-interface1.md)</span></span>\
 <span data-ttu-id="20025-243">Extensión de `ICorDebugHeapValue` que proporciona compatibilidad con los identificadores del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="20025-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 <span data-ttu-id="20025-244">[ICorDebugHeapValue3 (interfaz)](icordebugheapvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-244">[ICorDebugHeapValue3 Interface](icordebugheapvalue3-interface.md)</span></span>\
 <span data-ttu-id="20025-245">Expone las propiedades de bloqueo de monitor de objetos.</span><span class="sxs-lookup"><span data-stu-id="20025-245">Exposes the monitor lock properties of objects.</span></span>  
  
 <span data-ttu-id="20025-246">[ICorDebugILCode (interfaz)](icordebugilcode-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-246">[ICorDebugILCode Interface](icordebugilcode-interface.md)</span></span>\
 <span data-ttu-id="20025-247">Representa un segmento de código de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="20025-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 <span data-ttu-id="20025-248">[ICorDebugILCode2 (interfaz)](icordebugilcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-248">[ICorDebugILCode2 Interface](icordebugilcode2-interface.md)</span></span>\
 <span data-ttu-id="20025-249">Extiende lógicamente la [ICorDebugILCode](icordebugilcode-interface.md) interfaz para proporcionar métodos que devuelven el token de firma de variable local de una función, e instrumentada un lenguaje intermedio del generador de perfiles (IL) que asignan los desplazamientos al IL del método original desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="20025-249">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 <span data-ttu-id="20025-250">[ICorDebugILFrame (interfaz)](icordebugilframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-250">[ICorDebugILFrame Interface](icordebugilframe-interface.md)</span></span>\
 <span data-ttu-id="20025-251">Representa un marco de pila de código de MSIL.</span><span class="sxs-lookup"><span data-stu-id="20025-251">Represents a stack frame of MSIL code.</span></span>  
  
 <span data-ttu-id="20025-252">[ICorDebugILFrame2 (interfaz)](icordebugilframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-252">[ICorDebugILFrame2 Interface](icordebugilframe2-interface.md)</span></span>\
 <span data-ttu-id="20025-253">Extensión lógica de `ICorDebugILFrame`.</span><span class="sxs-lookup"><span data-stu-id="20025-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 <span data-ttu-id="20025-254">[ICorDebugILFrame3 (interfaz)](icordebugilframe3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-254">[ICorDebugILFrame3 Interface](icordebugilframe3-interface.md)</span></span>\
 <span data-ttu-id="20025-255">Proporciona un método que encapsula el valor devuelto de una función.</span><span class="sxs-lookup"><span data-stu-id="20025-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 <span data-ttu-id="20025-256">[ICorDebugILFrame4 (interfaz)](icordebugilframe4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-256">[ICorDebugILFrame4 Interface](icordebugilframe4-interface.md)</span></span>\
 <span data-ttu-id="20025-257">Proporciona métodos que permiten acceder a las variables locales y al código en un marco de pila de código de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="20025-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="20025-258">Un parámetro especifica si el depurador tiene acceso a las variables y al código agregados en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="20025-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 <span data-ttu-id="20025-259">[ICorDebugInstanceFieldSymbol (interfaz)](icordebuginstancefieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-259">[ICorDebugInstanceFieldSymbol Interface](icordebuginstancefieldsymbol-interface.md)</span></span>\
 <span data-ttu-id="20025-260">Representa la información de símbolos de depuración para un campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="20025-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="20025-261">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="20025-261">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="20025-262">[ICorDebugInternalFrame (interfaz)](icordebuginternalframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-262">[ICorDebugInternalFrame Interface](icordebuginternalframe-interface.md)</span></span>\
 <span data-ttu-id="20025-263">Identifica los tipos de marco del depurador.</span><span class="sxs-lookup"><span data-stu-id="20025-263">Identifies frame types for the debugger.</span></span>  
  
 <span data-ttu-id="20025-264">[ICorDebugInternalFrame2 (interfaz)](icordebuginternalframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-264">[ICorDebugInternalFrame2 Interface](icordebuginternalframe2-interface.md)</span></span>\
 <span data-ttu-id="20025-265">Proporciona información sobre los marcos internos, incluyendo la dirección de la pila y la posición en relación con [ICorDebugFrame](icordebugframe-interface.md) objetos.</span><span class="sxs-lookup"><span data-stu-id="20025-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](icordebugframe-interface.md) objects.</span></span>  
  
 <span data-ttu-id="20025-266">[ICorDebugLoadedModule (interfaz)](icordebugloadedmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-266">[ICorDebugLoadedModule Interface](icordebugloadedmodule-interface.md)</span></span>\
 <span data-ttu-id="20025-267">Proporciona información acerca de un módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="20025-267">Provides information about a loaded module.</span></span> <span data-ttu-id="20025-268">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="20025-268">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="20025-269">[ICorDebugManagedCallback (interfaz)](icordebugmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-269">[ICorDebugManagedCallback Interface](icordebugmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="20025-270">Proporciona métodos que permiten procesar las devoluciones de llamada del depurador.</span><span class="sxs-lookup"><span data-stu-id="20025-270">Provides methods to process debugger callbacks.</span></span>  
  
 <span data-ttu-id="20025-271">[ICorDebugManagedCallback2 (interfaz)](icordebugmanagedcallback2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-271">[ICorDebugManagedCallback2 Interface](icordebugmanagedcallback2-interface.md)</span></span>\
 <span data-ttu-id="20025-272">Proporciona métodos para admitir el control de excepciones del depurador y asistentes para depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="20025-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="20025-273">`ICorDebugManagedCallback2` es una extensión lógica de `ICorDebugManagedCallback`.</span><span class="sxs-lookup"><span data-stu-id="20025-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 <span data-ttu-id="20025-274">[ICorDebugManagedCallback3 (interfaz)](icordebugmanagedcallback3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-274">[ICorDebugManagedCallback3 Interface](icordebugmanagedcallback3-interface.md)</span></span>\
 <span data-ttu-id="20025-275">Proporciona un método de devolución de llamada que indica que se ha producido una notificación del depurador personalizada habilitada.</span><span class="sxs-lookup"><span data-stu-id="20025-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 <span data-ttu-id="20025-276">[ICorDebugMDA (interfaz)](icordebugmda-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-276">[ICorDebugMDA Interface](icordebugmda-interface.md)</span></span>\
 <span data-ttu-id="20025-277">Representa un mensaje del asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="20025-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 <span data-ttu-id="20025-278">[ICorDebugMemoryBuffer (interfaz)](icordebugmemorybuffer-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-278">[ICorDebugMemoryBuffer Interface](icordebugmemorybuffer-interface.md)</span></span>\
 <span data-ttu-id="20025-279">Representa un búfer en memoria.</span><span class="sxs-lookup"><span data-stu-id="20025-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="20025-280">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="20025-280">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="20025-281">[ICorDebugMergedAssemblyRecord (interfaz)](icordebugmergedassemblyrecord-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-281">[ICorDebugMergedAssemblyRecord Interface](icordebugmergedassemblyrecord-interface.md)</span></span>\
 <span data-ttu-id="20025-282">Proporciona información acerca de un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="20025-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="20025-283">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="20025-283">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="20025-284">[ICorDebugMetaDataLocator (interfaz)](icordebugmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-284">[ICorDebugMetaDataLocator Interface](icordebugmetadatalocator-interface.md)</span></span>\
 <span data-ttu-id="20025-285">Proporciona información de metadatos al depurador.</span><span class="sxs-lookup"><span data-stu-id="20025-285">Provides metadata information to the debugger.</span></span>  
  
 <span data-ttu-id="20025-286">[ICorDebugModule (interfaz)](icordebugmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-286">[ICorDebugModule Interface](icordebugmodule-interface.md)</span></span>\
 <span data-ttu-id="20025-287">Representa un módulo de CLR, que es un archivo ejecutable o una biblioteca de vínculos dinámicos (DLL).</span><span class="sxs-lookup"><span data-stu-id="20025-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 <span data-ttu-id="20025-288">[ICorDebugModule2 (interfaz)](icordebugmodule2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-288">[ICorDebugModule2 Interface](icordebugmodule2-interface.md)</span></span>\
 <span data-ttu-id="20025-289">Actúa como una extensión lógica de `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="20025-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 <span data-ttu-id="20025-290">[ICorDebugModule3 (interfaz)](icordebugmodule3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-290">[ICorDebugModule3 Interface](icordebugmodule3-interface.md)</span></span>\
 <span data-ttu-id="20025-291">Crea un lector de símbolos para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="20025-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 <span data-ttu-id="20025-292">[ICorDebugModuleBreakpoint (interfaz)](icordebugmodulebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-292">[ICorDebugModuleBreakpoint Interface](icordebugmodulebreakpoint-interface.md)</span></span>\
 <span data-ttu-id="20025-293">Extiende `ICorDebugBreakpoint` para proporcionar acceso a módulos específicos.</span><span class="sxs-lookup"><span data-stu-id="20025-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 <span data-ttu-id="20025-294">[ICorDebugModuleDebugEvent (interfaz)](icordebugmoduledebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-294">[ICorDebugModuleDebugEvent Interface](icordebugmoduledebugevent-interface.md)</span></span>\
 <span data-ttu-id="20025-295">Extiende la [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interfaz para admitir los eventos de nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="20025-295">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="20025-296">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="20025-296">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="20025-297">[ICorDebugModuleEnum (interfaz)](icordebugmoduleenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-297">[ICorDebugModuleEnum Interface](icordebugmoduleenum-interface.md)</span></span>\
 <span data-ttu-id="20025-298">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="20025-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 <span data-ttu-id="20025-299">[ICorDebugMutableDataTarget (interfaz)](icordebugmutabledatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-299">[ICorDebugMutableDataTarget Interface](icordebugmutabledatatarget-interface.md)</span></span>\
 <span data-ttu-id="20025-300">Extiende la [ICorDebugDataTarget](icordebugdatatarget-interface.md) interfaz para admitir destinos de datos mutables.</span><span class="sxs-lookup"><span data-stu-id="20025-300">Extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 <span data-ttu-id="20025-301">[ICorDebugNativeFrame (interfaz)](icordebugnativeframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-301">[ICorDebugNativeFrame Interface](icordebugnativeframe-interface.md)</span></span>\
 <span data-ttu-id="20025-302">Implementación especializada de `ICorDebugFrame` que se utiliza para los marcos nativos.</span><span class="sxs-lookup"><span data-stu-id="20025-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 <span data-ttu-id="20025-303">[ICorDebugNativeFrame2 (interfaz)](icordebugnativeframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-303">[ICorDebugNativeFrame2 Interface](icordebugnativeframe2-interface.md)</span></span>\
 <span data-ttu-id="20025-304">Proporciona métodos que comprueban las relaciones entre marcos primarios y secundarios.</span><span class="sxs-lookup"><span data-stu-id="20025-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 <span data-ttu-id="20025-305">[ICorDebugObjectEnum (interfaz)](icordebugobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-305">[ICorDebugObjectEnum Interface](icordebugobjectenum-interface.md)</span></span>\
 <span data-ttu-id="20025-306">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de objetos según sus direcciones virtuales relativas (RVA).</span><span class="sxs-lookup"><span data-stu-id="20025-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 <span data-ttu-id="20025-307">[ICorDebugObjectValue (interfaz)](icordebugobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-307">[ICorDebugObjectValue Interface](icordebugobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="20025-308">Subclase de `ICorDebugValue` que representa un valor que contiene un objeto.</span><span class="sxs-lookup"><span data-stu-id="20025-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 <span data-ttu-id="20025-309">[ICorDebugObjectValue2 (interfaz)](icordebugobjectvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-309">[ICorDebugObjectValue2 Interface](icordebugobjectvalue2-interface.md)</span></span>\
 <span data-ttu-id="20025-310">Extiende `ICorDebugObjectValue` para ofrecer compatibilidad con la herencia y los reemplazos.</span><span class="sxs-lookup"><span data-stu-id="20025-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 <span data-ttu-id="20025-311">[ICorDebugProcess (interfaz)](icordebugprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-311">[ICorDebugProcess Interface](icordebugprocess-interface.md)</span></span>\
 <span data-ttu-id="20025-312">Representa un proceso que ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="20025-312">Represents a process that is executing managed code.</span></span>  
  
 <span data-ttu-id="20025-313">[ICorDebugProcess2 (interfaz)](icordebugprocess2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="20025-313">[ICorDebugProcess2 Interface](icordebugprocess2-interface1.md)</span></span>\
 <span data-ttu-id="20025-314">Extensión lógica de `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="20025-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 <span data-ttu-id="20025-315">[ICorDebugProcess3 (interfaz)](icordebugprocess3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-315">[ICorDebugProcess3 Interface](icordebugprocess3-interface.md)</span></span>\
 <span data-ttu-id="20025-316">Controla las notificaciones del depurador personalizadas.</span><span class="sxs-lookup"><span data-stu-id="20025-316">Controls custom debugger notifications.</span></span>

 <span data-ttu-id="20025-317">[Interfaz ICorDebugProcess4](icordebugprocess4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-317">[ICorDebugProcess4 Interface](icordebugprocess4-interface.md)</span></span>\
 <span data-ttu-id="20025-318">Proporciona compatibilidad para fuera del control de ejecución del proceso.</span><span class="sxs-lookup"><span data-stu-id="20025-318">Provides support for out of process execution control.</span></span>
  
 <span data-ttu-id="20025-319">[ICorDebugProcess5 (interfaz)](icordebugprocess5-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-319">[ICorDebugProcess5 Interface](icordebugprocess5-interface.md)</span></span>\
 <span data-ttu-id="20025-320">Extiende la [ICorDebugProcess](icordebugprocess-interface.md) de la interfaz para admitir el acceso al montón administrado, para proporcionar información sobre la recolección de objetos administrados y para determinar si un depurador carga imágenes desde la aplicación local caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="20025-320">Extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 <span data-ttu-id="20025-321">[ICorDebugProcess6 (interfaz)](icordebugprocess6-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-321">[ICorDebugProcess6 Interface](icordebugprocess6-interface.md)</span></span>\
 <span data-ttu-id="20025-322">Extiende lógicamente la [ICorDebugProcess](icordebugprocess-interface.md) interfaz para habilitar características como la descodificación de eventos de depuración administrados que están codificados en eventos de depuración de excepción nativos y división de módulos virtuales.</span><span class="sxs-lookup"><span data-stu-id="20025-322">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="20025-323">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="20025-323">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="20025-324">[ICorDebugProcess7 (interfaz)](icordebugprocess7-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-324">[ICorDebugProcess7 Interface](icordebugprocess7-interface.md)</span></span>\
 <span data-ttu-id="20025-325">Proporciona un método que configura el depurador para controlar las actualizaciones en memoria de los metadatos en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="20025-325">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 <span data-ttu-id="20025-326">[ICorDebugProcess8 (interfaz)](icordebugprocess8-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-326">[ICorDebugProcess8 Interface](icordebugprocess8-interface.md)</span></span>\
 <span data-ttu-id="20025-327">Extiende lógicamente la [ICorDebugProcess](icordebugprocess-interface.md) interfaz para habilitar o deshabilitar ciertos tipos de [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) devoluciones de llamada de excepción.</span><span class="sxs-lookup"><span data-stu-id="20025-327">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 <span data-ttu-id="20025-328">[ICorDebugProcessEnum (interfaz)](icordebugprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-328">[ICorDebugProcessEnum Interface](icordebugprocessenum-interface.md)</span></span>\
 <span data-ttu-id="20025-329">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="20025-329">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 <span data-ttu-id="20025-330">[ICorDebugReferenceValue (interfaz)](icordebugreferencevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-330">[ICorDebugReferenceValue Interface](icordebugreferencevalue-interface.md)</span></span>\
 <span data-ttu-id="20025-331">Subclase de `ICorDebugValue` que admite tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="20025-331">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 <span data-ttu-id="20025-332">[ICorDebugRegisterSet (interfaz)](icordebugregisterset-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-332">[ICorDebugRegisterSet Interface](icordebugregisterset-interface.md)</span></span>\
 <span data-ttu-id="20025-333">Representa el conjunto de registros disponibles en el equipo que está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="20025-333">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 <span data-ttu-id="20025-334">[ICorDebugRegisterSet2 (interfaz)](icordebugregisterset2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-334">[ICorDebugRegisterSet2 Interface](icordebugregisterset2-interface.md)</span></span>\
 <span data-ttu-id="20025-335">Extiende la funcionalidad de `ICorDebugRegisterSet` para plataformas hardware que tienen más de 64 registros.</span><span class="sxs-lookup"><span data-stu-id="20025-335">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 <span data-ttu-id="20025-336">[ICorDebugRemote (interfaz)](icordebugremote-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-336">[ICorDebugRemote Interface](icordebugremote-interface.md)</span></span>\
 <span data-ttu-id="20025-337">Proporciona la capacidad de iniciar o de adjuntar un depurador administrado a un proceso remoto de destino.</span><span class="sxs-lookup"><span data-stu-id="20025-337">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 <span data-ttu-id="20025-338">[ICorDebugRemoteTarget (interfaz)](icordebugremotetarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-338">[ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md)</span></span>\
 <span data-ttu-id="20025-339">Proporciona métodos que permiten depurar aplicaciones basadas en Silverlight en el entorno de CLR.</span><span class="sxs-lookup"><span data-stu-id="20025-339">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="20025-340">[ICorDebugRuntimeUnwindableFrame (interfaz)](icordebugruntimeunwindableframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-340">[ICorDebugRuntimeUnwindableFrame Interface](icordebugruntimeunwindableframe-interface.md)</span></span>\
 <span data-ttu-id="20025-341">Proporciona compatibilidad para métodos no administrados que necesitan que Common Language Runtime (CLR) desenrede un marco.</span><span class="sxs-lookup"><span data-stu-id="20025-341">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 <span data-ttu-id="20025-342">[ICorDebugStackWalk (interfaz)](icordebugstackwalk-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-342">[ICorDebugStackWalk Interface](icordebugstackwalk-interface.md)</span></span>\
 <span data-ttu-id="20025-343">Proporciona métodos para obtener los métodos administrados, o marcos, de la pila de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="20025-343">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 <span data-ttu-id="20025-344">[ICorDebugStaticFieldSymbol (interfaz)](icordebugstaticfieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-344">[ICorDebugStaticFieldSymbol Interface](icordebugstaticfieldsymbol-interface.md)</span></span>\
 <span data-ttu-id="20025-345">Representa la información de símbolos de depuración para un campo estático.</span><span class="sxs-lookup"><span data-stu-id="20025-345">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="20025-346">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="20025-346">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="20025-347">[ICorDebugStepper (interfaz)](icordebugstepper-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-347">[ICorDebugStepper Interface](icordebugstepper-interface.md)</span></span>\
 <span data-ttu-id="20025-348">Representa un paso en la ejecución del código realizado por un depurador, actúa como identificador entre la emisión y la finalización de un comando, y proporciona un modo de cancelar un paso.</span><span class="sxs-lookup"><span data-stu-id="20025-348">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 <span data-ttu-id="20025-349">[ICorDebugStepper2 (interfaz)](icordebugstepper2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="20025-349">[ICorDebugStepper2 Interface](icordebugstepper2-interface1.md)</span></span>\
 <span data-ttu-id="20025-350">Proporciona compatibilidad con la depuración de "Sólo mi código" (JMC).</span><span class="sxs-lookup"><span data-stu-id="20025-350">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 <span data-ttu-id="20025-351">[ICorDebugStepperEnum (interfaz)](icordebugstepperenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-351">[ICorDebugStepperEnum Interface](icordebugstepperenum-interface.md)</span></span>\
 <span data-ttu-id="20025-352">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugStepper`.</span><span class="sxs-lookup"><span data-stu-id="20025-352">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 <span data-ttu-id="20025-353">[ICorDebugStringValue (interfaz)](icordebugstringvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-353">[ICorDebugStringValue Interface](icordebugstringvalue-interface.md)</span></span>\
 <span data-ttu-id="20025-354">Subclase de `ICorDebugHeapValue` que se aplica a los valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="20025-354">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 <span data-ttu-id="20025-355">[ICorDebugSymbolProvider (interfaz)](icordebugsymbolprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-355">[ICorDebugSymbolProvider Interface](icordebugsymbolprovider-interface.md)</span></span>\
 <span data-ttu-id="20025-356">Proporciona métodos que pueden utilizarse para recuperar información de símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="20025-356">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="20025-357">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="20025-357">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="20025-358">[ICorDebugSymbolProvider2 (interfaz)](icordebugsymbolprovider2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-358">[ICorDebugSymbolProvider2 Interface](icordebugsymbolprovider2-interface.md)</span></span>\
 <span data-ttu-id="20025-359">Extiende lógicamente la [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interfaz para recuperar información de símbolos de depuración adicional.</span><span class="sxs-lookup"><span data-stu-id="20025-359">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="20025-360">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="20025-360">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="20025-361">[ICorDebugThread (interfaz)](icordebugthread-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-361">[ICorDebugThread Interface](icordebugthread-interface.md)</span></span>\
 <span data-ttu-id="20025-362">Representa un subproceso de un proceso.</span><span class="sxs-lookup"><span data-stu-id="20025-362">Represents a thread in a process.</span></span> <span data-ttu-id="20025-363">El período de duración de una instancia de `ICorDebugThread` es el mismo que el del subproceso que representa.</span><span class="sxs-lookup"><span data-stu-id="20025-363">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 <span data-ttu-id="20025-364">[ICorDebugThread2 (interfaz)](icordebugthread2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-364">[ICorDebugThread2 Interface](icordebugthread2-interface.md)</span></span>\
 <span data-ttu-id="20025-365">Actúa como una extensión lógica de `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="20025-365">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 <span data-ttu-id="20025-366">[ICorDebugThread3 (interfaz)](icordebugthread3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-366">[ICorDebugThread3 Interface](icordebugthread3-interface.md)</span></span>\
 <span data-ttu-id="20025-367">Proporciona el punto de entrada a la [ICorDebugStackWalk](icordebugstackwalk-interface.md) y las interfaces correspondientes.</span><span class="sxs-lookup"><span data-stu-id="20025-367">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 <span data-ttu-id="20025-368">[ICorDebugThread4 (interfaz)](icordebugthread4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-368">[ICorDebugThread4 Interface](icordebugthread4-interface.md)</span></span>\
 <span data-ttu-id="20025-369">Proporciona información de bloqueo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="20025-369">Provides thread blocking information.</span></span>  
  
 <span data-ttu-id="20025-370">[ICorDebugThreadEnum (interfaz)](icordebugthreadenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="20025-370">[ICorDebugThreadEnum Interface](icordebugthreadenum-interface1.md)</span></span>\
 <span data-ttu-id="20025-371">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="20025-371">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 <span data-ttu-id="20025-372">[ICorDebugType (interfaz)](icordebugtype-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-372">[ICorDebugType Interface](icordebugtype-interface.md)</span></span>\
 <span data-ttu-id="20025-373">Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="20025-373">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="20025-374">Si el tipo es genérico, `ICorDebugType` representa el tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="20025-374">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 <span data-ttu-id="20025-375">[ICorDebugType2 (interfaz)](icordebugtype2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-375">[ICorDebugType2 Interface](icordebugtype2-interface.md)</span></span>\
 <span data-ttu-id="20025-376">Extiende la [ICorDebugType](icordebugtype-interface.md) interfaz para recuperar el identificador de tipo de un tipo base o un tipo complejo (definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="20025-376">Extends the [ICorDebugType](icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 <span data-ttu-id="20025-377">[ICorDebugTypeEnum (interfaz)](icordebugtypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-377">[ICorDebugTypeEnum Interface](icordebugtypeenum-interface.md)</span></span>\
 <span data-ttu-id="20025-378">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="20025-378">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 <span data-ttu-id="20025-379">[ICorDebugUnmanagedCallback (interfaz)](icordebugunmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-379">[ICorDebugUnmanagedCallback Interface](icordebugunmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="20025-380">Proporciona notificación de eventos nativos no relacionados directamente con CLR.</span><span class="sxs-lookup"><span data-stu-id="20025-380">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="20025-381">[ICorDebugValue](icordebugvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-381">[ICorDebugValue](icordebugvalue-interface.md)</span></span>\
 <span data-ttu-id="20025-382">Representa un valor de escritura o lectura en el proceso que se va a depurar.</span><span class="sxs-lookup"><span data-stu-id="20025-382">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="20025-383">[ICorDebugValue2](icordebugvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-383">[ICorDebugValue2](icordebugvalue2-interface.md)</span></span>\
 <span data-ttu-id="20025-384">Extiende `ICorDebugValue` para proporcionar compatibilidad con `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="20025-384">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="20025-385">[ICorDebugValue3 (interfaz)](icordebugvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-385">[ICorDebugValue3 Interface](icordebugvalue3-interface.md)</span></span>\
 <span data-ttu-id="20025-386">Extiende las interfaces "ICorDebugValue" y "ICorDebugValue2" para proporcionar compatibilidad para matrices que son superiores a 2 GB.</span><span class="sxs-lookup"><span data-stu-id="20025-386">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="20025-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)</span></span>\
 <span data-ttu-id="20025-388">Extiende `ICorDebugBreakpoint` para proporcionar acceso a valores concretos.</span><span class="sxs-lookup"><span data-stu-id="20025-388">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="20025-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)</span></span>\
 <span data-ttu-id="20025-390">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="20025-390">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 <span data-ttu-id="20025-391">[ICorDebugVariableHome (interfaz)](icordebugvariablehome-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-391">[ICorDebugVariableHome Interface](icordebugvariablehome-interface.md)</span></span>\
 <span data-ttu-id="20025-392">Representa una variable local o argumento de una función.</span><span class="sxs-lookup"><span data-stu-id="20025-392">Represents a local variable or argument of a function.</span></span>  
  
 <span data-ttu-id="20025-393">[ICorDebugVariableHomeEnum (interfaz)](icordebugvariablehomeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-393">[ICorDebugVariableHomeEnum Interface](icordebugvariablehomeenum-interface.md)</span></span>\
 <span data-ttu-id="20025-394">Proporciona un enumerador para los argumentos en una función y las variables locales.</span><span class="sxs-lookup"><span data-stu-id="20025-394">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="20025-395">[ICorDebugVariableSymbol (interfaz)](icordebugvariablesymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-395">[ICorDebugVariableSymbol Interface](icordebugvariablesymbol-interface.md)</span></span>\
 <span data-ttu-id="20025-396">Recupera la información de símbolos de depuración para una variable.</span><span class="sxs-lookup"><span data-stu-id="20025-396">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="20025-397">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="20025-397">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="20025-398">[ICorDebugVirtualUnwinder (interfaz)](icordebugvirtualunwinder-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-398">[ICorDebugVirtualUnwinder Interface](icordebugvirtualunwinder-interface.md)</span></span>\
 <span data-ttu-id="20025-399">Proporciona métodos que ayudan al desenredo de la pila.</span><span class="sxs-lookup"><span data-stu-id="20025-399">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="20025-400">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="20025-400">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="20025-401">[ICorPublish (interfaz)](icorpublish-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-401">[ICorPublish Interface](icorpublish-interface.md)</span></span>\
 <span data-ttu-id="20025-402">Actúa como interfaz general para los procesos de publicación.</span><span class="sxs-lookup"><span data-stu-id="20025-402">Serves as the general interface for the publishing processes.</span></span>  
  
 <span data-ttu-id="20025-403">[ICorPublishAppDomain (interfaz)](icorpublishappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-403">[ICorPublishAppDomain Interface](icorpublishappdomain-interface.md)</span></span>\
 <span data-ttu-id="20025-404">Representa y proporciona información sobre un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="20025-404">Represents and provides information about an application domain.</span></span>  
  
 <span data-ttu-id="20025-405">[ICorPublishAppDomainEnum (interfaz)](icorpublishappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-405">[ICorPublishAppDomainEnum Interface](icorpublishappdomainenum-interface.md)</span></span>\
 <span data-ttu-id="20025-406">Proporciona métodos que atraviesan una colección de objetos `ICorPublishAppDomain` que actualmente existen dentro de un proceso.</span><span class="sxs-lookup"><span data-stu-id="20025-406">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 <span data-ttu-id="20025-407">[ICorPublishEnum (interfaz)](icorpublishenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-407">[ICorPublishEnum Interface](icorpublishenum-interface.md)</span></span>\
 <span data-ttu-id="20025-408">Actúa como la base abstracta para los enumeradores de publicación.</span><span class="sxs-lookup"><span data-stu-id="20025-408">Serves as the abstract base for publishing enumerators.</span></span>  
  
 <span data-ttu-id="20025-409">[ICorPublishProcess (interfaz)](icorpublishprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-409">[ICorPublishProcess Interface](icorpublishprocess-interface.md)</span></span>\
 <span data-ttu-id="20025-410">Proporciona métodos que tienen acceso a información de un proceso.</span><span class="sxs-lookup"><span data-stu-id="20025-410">Provides methods that access information about a process.</span></span>  
  
 <span data-ttu-id="20025-411">[ICorPublishProcessEnum (interfaz)](icorpublishprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-411">[ICorPublishProcessEnum Interface](icorpublishprocessenum-interface.md)</span></span>\
 <span data-ttu-id="20025-412">Proporciona métodos que atraviesan una colección de objetos `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="20025-412">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  

 <span data-ttu-id="20025-413">[Interfaz ISOSDacInterface](isosdacinterface-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-413">[ISOSDacInterface Interface](isosdacinterface-interface.md)</span></span>\
 <span data-ttu-id="20025-414">Proporciona métodos auxiliares para acceder a ellos desde `SOS`.</span><span class="sxs-lookup"><span data-stu-id="20025-414">Provides helper methods to access data from `SOS`.</span></span>

 <span data-ttu-id="20025-415">[Interfaz IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-415">[IXCLRDataMethodDefinition Interface](ixclrdatamethoddefinition-interface.md)</span></span>\
 <span data-ttu-id="20025-416">Proporciona métodos para consultar información sobre una definición de método.</span><span class="sxs-lookup"><span data-stu-id="20025-416">Provides methods for querying information about a method definition.</span></span>
 
 <span data-ttu-id="20025-417">[Interfaz IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-417">[IXCLRDataMethodInstance Interface](ixclrdatamethodinstance-interface.md)</span></span>\
 <span data-ttu-id="20025-418">Proporciona métodos para consultar información sobre una instancia de método.</span><span class="sxs-lookup"><span data-stu-id="20025-418">Provides methods for querying information about a method instance.</span></span>
 
 <span data-ttu-id="20025-419">[Interfaz IXCLRDataModule](ixclrdatamodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-419">[IXCLRDataModule Interface](ixclrdatamodule-interface.md)</span></span>\
 <span data-ttu-id="20025-420">Proporciona métodos para consultar información acerca de un módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="20025-420">Provides methods for querying information about a loaded module.</span></span>
 
 <span data-ttu-id="20025-421">[Interfaz IXCLRDataProcess](ixclrdataprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="20025-421">[IXCLRDataProcess Interface](ixclrdataprocess-interface.md)</span></span>\
 <span data-ttu-id="20025-422">Proporciona métodos para consultar información sobre un proceso.</span><span class="sxs-lookup"><span data-stu-id="20025-422">Provides methods for querying information about a process.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="20025-423">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="20025-423">Related Sections</span></span>  
 <span data-ttu-id="20025-424">[Coclases para la depuración](debugging-coclasses.md)</span><span class="sxs-lookup"><span data-stu-id="20025-424">[Debugging Coclasses](debugging-coclasses.md)</span></span>\
 <span data-ttu-id="20025-425">[Funciones estáticas globales de depuración](debugging-global-static-functions.md)</span><span class="sxs-lookup"><span data-stu-id="20025-425">[Debugging Global Static Functions](debugging-global-static-functions.md)</span></span>\
 <span data-ttu-id="20025-426">[Enumeraciones de depuración](debugging-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="20025-426">[Debugging Enumerations](debugging-enumerations.md)</span></span>\
 <span data-ttu-id="20025-427">[Estructuras de depuración](debugging-structures.md)</span><span class="sxs-lookup"><span data-stu-id="20025-427">[Debugging Structures](debugging-structures.md)</span></span>\
