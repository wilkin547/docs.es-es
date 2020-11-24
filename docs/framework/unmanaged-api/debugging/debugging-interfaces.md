---
title: Interfaces para depuración
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
ms.openlocfilehash: a3dd81ceaab2ba467d4c8ca091c1c2219040a273
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676301"
---
# <a name="debugging-interfaces"></a><span data-ttu-id="274f6-102">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="274f6-102">Debugging Interfaces</span></span>

<span data-ttu-id="274f6-103">En esta sección se describen las interfaces no administradas que controlan la depuración de un programa que se ejecuta en Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="274f6-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="274f6-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="274f6-104">In This Section</span></span>  

 <span data-ttu-id="274f6-105">[ICLRDataEnumMemoryRegions (interfaz)](iclrdataenummemoryregions-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-105">[ICLRDataEnumMemoryRegions Interface](iclrdataenummemoryregions-interface.md)</span></span>\
 <span data-ttu-id="274f6-106">Proporciona un método para enumerar las regiones de memoria especificadas por los llamadores.</span><span class="sxs-lookup"><span data-stu-id="274f6-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 <span data-ttu-id="274f6-107">[Interfaz ICLRDataEnumMemoryRegionsCallback (](iclrdataenummemoryregionscallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-107">[ICLRDataEnumMemoryRegionsCallback Interface](iclrdataenummemoryregionscallback-interface.md)</span></span>\
 <span data-ttu-id="274f6-108">Proporciona un método de devolución de llamada para que `EnumMemoryRegions` notifique al depurador el resultado de un intento de enumerar un área de memoria concreta.</span><span class="sxs-lookup"><span data-stu-id="274f6-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 <span data-ttu-id="274f6-109">[ICLRDataTarget (interfaz)](iclrdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-109">[ICLRDataTarget Interface](iclrdatatarget-interface.md)</span></span>\
 <span data-ttu-id="274f6-110">Proporciona métodos para la interacción con un proceso de CLR de destino.</span><span class="sxs-lookup"><span data-stu-id="274f6-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 <span data-ttu-id="274f6-111">[Interfaz ICLRDataTarget2](iclrdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-111">[ICLRDataTarget2 Interface](iclrdatatarget2-interface.md)</span></span>\
 <span data-ttu-id="274f6-112">Subclase de `ICLRDataTarget` que se utiliza la capa de servicios de acceso a datos para manipular las áreas de la memoria virtual en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="274f6-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 <span data-ttu-id="274f6-113">[Interfaz ICLRDataTarget3](iclrdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-113">[ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)</span></span>\
 <span data-ttu-id="274f6-114">Subclase de [ICLRDataTarget2](iclrdatatarget2-interface.md) que proporciona acceso a la información de la excepción.</span><span class="sxs-lookup"><span data-stu-id="274f6-114">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 <span data-ttu-id="274f6-115">[Interfaz ICLRDebugging](iclrdebugging-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-115">[ICLRDebugging Interface](iclrdebugging-interface.md)</span></span>\
 <span data-ttu-id="274f6-116">Proporciona métodos que controlan la carga y descarga de módulos para depuración.</span><span class="sxs-lookup"><span data-stu-id="274f6-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 <span data-ttu-id="274f6-117">[Interfaz ICLRDebuggingLibraryProvider (](iclrdebugginglibraryprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-117">[ICLRDebuggingLibraryProvider Interface](iclrdebugginglibraryprovider-interface.md)</span></span>\
 <span data-ttu-id="274f6-118">Incluye el método del [método ProvideLibrary (](iclrdebugginglibraryprovider-providelibrary-method.md) , que obtiene una interfaz de devolución de llamada del proveedor de bibliotecas que permite buscar y cargar a petición bibliotecas de depuración específicas de la versión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="274f6-118">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 <span data-ttu-id="274f6-119">[Interfaz Iclrmetadatalocator (](iclrmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-119">[ICLRMetadataLocator Interface](iclrmetadatalocator-interface.md)</span></span>\
 <span data-ttu-id="274f6-120">Interfaz utilizada por la capa de servicios de acceso a datos para buscar los metadatos de los ensamblados en un proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="274f6-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 <span data-ttu-id="274f6-121">[ICorDebug (interfaz)](icordebug-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-121">[ICorDebug Interface](icordebug-interface.md)</span></span>\
 <span data-ttu-id="274f6-122">Proporciona métodos que permiten a los desarrolladores depurar las aplicaciones en el entorno de CLR.</span><span class="sxs-lookup"><span data-stu-id="274f6-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="274f6-123">[ICorDebugAppDomain (interfaz)](icordebugappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-123">[ICorDebugAppDomain Interface](icordebugappdomain-interface.md)</span></span>\
 <span data-ttu-id="274f6-124">Proporciona métodos para depurar dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="274f6-124">Provides methods for debugging application domains.</span></span>  
  
 <span data-ttu-id="274f6-125">[Interfaz ICorDebugAppDomain2](icordebugappdomain2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-125">[ICorDebugAppDomain2 Interface](icordebugappdomain2-interface.md)</span></span>\
 <span data-ttu-id="274f6-126">Proporciona métodos para trabajar con matrices, punteros, punteros a función y tipos ByRef.</span><span class="sxs-lookup"><span data-stu-id="274f6-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="274f6-127">Esta interfaz es una extensión de la interfaz `ICorDebugAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="274f6-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 <span data-ttu-id="274f6-128">[Interfaz ICorDebugAppDomain3](icordebugappdomain3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-128">[ICorDebugAppDomain3 Interface](icordebugappdomain3-interface.md)</span></span>\
 <span data-ttu-id="274f6-129">Proporciona métodos para trabajar con los tipos de Windows Runtime en un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="274f6-129">Provides methods to work with the Windows Runtime types in an application domain.</span></span> <span data-ttu-id="274f6-130">Esta interfaz es una extensión de las interfaces `ICorDebugAppDomain` e `ICorDebugAppDomain2`.</span><span class="sxs-lookup"><span data-stu-id="274f6-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 <span data-ttu-id="274f6-131">[Interfaz ICorDebugAppDomain4](icordebugappdomain4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-131">[ICorDebugAppDomain4 Interface](icordebugappdomain4-interface.md)</span></span>\
 <span data-ttu-id="274f6-132">Extiende lógicamente la interfaz [ICorDebugAppDomain](icordebugappdomain-interface.md) para obtener un objeto administrado desde un contenedor com invocable.</span><span class="sxs-lookup"><span data-stu-id="274f6-132">Logically extends the [ICorDebugAppDomain](icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 <span data-ttu-id="274f6-133">[Interfaz ICorDebugAppDomainEnum (](icordebugappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-133">[ICorDebugAppDomainEnum Interface](icordebugappdomainenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-134">Proporciona un método que devuelve un número especificado de valores de `ICorDebugAppDomain` que comienzan en la siguiente posición de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="274f6-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 <span data-ttu-id="274f6-135">[ICorDebugArrayValue (interfaz)](icordebugarrayvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-135">[ICorDebugArrayValue Interface](icordebugarrayvalue-interface.md)</span></span>\
 <span data-ttu-id="274f6-136">Subclase de `ICorDebugHeapValue` que representa una matriz unidimensional o multidimensional.</span><span class="sxs-lookup"><span data-stu-id="274f6-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 <span data-ttu-id="274f6-137">[ICorDebugAssembly (interfaz)](icordebugassembly-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-137">[ICorDebugAssembly Interface](icordebugassembly-interface.md)</span></span>\
 <span data-ttu-id="274f6-138">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="274f6-138">Represents an assembly.</span></span>  
  
 <span data-ttu-id="274f6-139">[Interfaz Icordebugassembly2 (](icordebugassembly2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-139">[ICorDebugAssembly2 Interface](icordebugassembly2-interface.md)</span></span>\
 <span data-ttu-id="274f6-140">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="274f6-140">Represents an assembly.</span></span> <span data-ttu-id="274f6-141">Esta interfaz es una extensión de la interfaz `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="274f6-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 <span data-ttu-id="274f6-142">[Interfaz método icordebugassembly3](icordebugassembly3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-142">[ICorDebugAssembly3 Interface](icordebugassembly3-interface.md)</span></span>\
 <span data-ttu-id="274f6-143">Extiende lógicamente la interfaz [ICorDebugAssembly](icordebugassembly-interface.md) para proporcionar compatibilidad con los ensamblados de contenedor y sus ensamblados incluidos.</span><span class="sxs-lookup"><span data-stu-id="274f6-143">Logically extends the [ICorDebugAssembly](icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="274f6-144">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="274f6-144">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="274f6-145">[Interfaz ICorDebugAssemblyEnum](icordebugassemblyenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-145">[ICorDebugAssemblyEnum Interface](icordebugassemblyenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-146">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="274f6-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 <span data-ttu-id="274f6-147">[Interfaz ICorDebugBlockingObjectEnum](icordebugblockingobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-147">[ICorDebugBlockingObjectEnum Interface](icordebugblockingobjectenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-148">Proporciona un enumerador para una lista de estructuras [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="274f6-148">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
 <span data-ttu-id="274f6-149">[Interfaz ICorDebugBoxValue (](icordebugboxvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-149">[ICorDebugBoxValue Interface](icordebugboxvalue-interface.md)</span></span>\
 <span data-ttu-id="274f6-150">Subclase de `ICorDebugHeapValue` que representa un objeto de clase de valor al que se ha aplicado la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="274f6-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 <span data-ttu-id="274f6-151">[ICorDebugBreakpoint (interfaz)](icordebugbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-151">[ICorDebugBreakpoint Interface](icordebugbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="274f6-152">Representa un punto de interrupción en una función o un punto de inspección en un valor.</span><span class="sxs-lookup"><span data-stu-id="274f6-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 <span data-ttu-id="274f6-153">[Interfaz ICorDebugBreakpointEnum (](icordebugbreakpointenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-153">[ICorDebugBreakpointEnum Interface](icordebugbreakpointenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-154">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="274f6-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 <span data-ttu-id="274f6-155">[ICorDebugChain (interfaz)](icordebugchain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-155">[ICorDebugChain Interface](icordebugchain-interface.md)</span></span>\
 <span data-ttu-id="274f6-156">Representa un segmento de una pila de llamadas física o lógica.</span><span class="sxs-lookup"><span data-stu-id="274f6-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 <span data-ttu-id="274f6-157">[Interfaz ICorDebugChainEnum (](icordebugchainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-157">[ICorDebugChainEnum Interface](icordebugchainenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-158">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugChain`.</span><span class="sxs-lookup"><span data-stu-id="274f6-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 <span data-ttu-id="274f6-159">[ICorDebugClass (interfaz)](icordebugclass-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-159">[ICorDebugClass Interface](icordebugclass-interface.md)</span></span>\
 <span data-ttu-id="274f6-160">Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="274f6-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="274f6-161">Si el tipo es genérico, `ICorDebugClass` representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="274f6-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 <span data-ttu-id="274f6-162">[Interfaz ICorDebugClass2](icordebugclass2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-162">[ICorDebugClass2 Interface](icordebugclass2-interface.md)</span></span>\
 <span data-ttu-id="274f6-163">Representa una clase genérica o una clase con un parámetro de método de tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="274f6-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="274f6-164">Esta interfaz extiende `ICorDebugClass`.</span><span class="sxs-lookup"><span data-stu-id="274f6-164">This interface extends `ICorDebugClass`.</span></span>  
  
 <span data-ttu-id="274f6-165">[ICorDebugCode (interfaz)](icordebugcode-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-165">[ICorDebugCode Interface](icordebugcode-interface1.md)</span></span>\
 <span data-ttu-id="274f6-166">Representa un segmento de código de lenguaje intermedio de Microsoft (MSIL) o código nativo.</span><span class="sxs-lookup"><span data-stu-id="274f6-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 <span data-ttu-id="274f6-167">[Interfaz ICorDebugCode2](icordebugcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-167">[ICorDebugCode2 Interface](icordebugcode2-interface.md)</span></span>\
 <span data-ttu-id="274f6-168">Proporciona métodos que amplían las funciones de `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="274f6-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 <span data-ttu-id="274f6-169">[Interfaz ICorDebugCode3](icordebugcode3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-169">[ICorDebugCode3 Interface](icordebugcode3-interface.md)</span></span>\
 <span data-ttu-id="274f6-170">Proporciona un método que extiende [ICorDebugCode](icordebugcode-interface1.md) y [ICorDebugCode2](icordebugcode2-interface.md) para proporcionar información sobre un valor devuelto administrado.</span><span class="sxs-lookup"><span data-stu-id="274f6-170">Provides a method that extends [ICorDebugCode](icordebugcode-interface1.md) and [ICorDebugCode2](icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 <span data-ttu-id="274f6-171">[Interfaz interfaces icordebugcode4](icordebugcode4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-171">[ICorDebugCode4 Interface](icordebugcode4-interface.md)</span></span>\
 <span data-ttu-id="274f6-172">Proporciona un método que permite a un depurador enumerar las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="274f6-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="274f6-173">[Interfaz ICorDebugCodeEnum (](icordebugcodeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-173">[ICorDebugCodeEnum Interface](icordebugcodeenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-174">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="274f6-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 <span data-ttu-id="274f6-175">[Interfaz ICorDebugComObjectValue](icordebugcomobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-175">[ICorDebugComObjectValue Interface](icordebugcomobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="274f6-176">Proporciona métodos para recuperar objetos de la interfaz en caché.</span><span class="sxs-lookup"><span data-stu-id="274f6-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 <span data-ttu-id="274f6-177">[Interfaz Icordebugcontext (](icordebugcontext-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-177">[ICorDebugContext Interface](icordebugcontext-interface.md)</span></span>\
 <span data-ttu-id="274f6-178">Representa un objeto de contexto.</span><span class="sxs-lookup"><span data-stu-id="274f6-178">Represents a context object.</span></span> <span data-ttu-id="274f6-179">Esta interfaz no se ha implementado todavía.</span><span class="sxs-lookup"><span data-stu-id="274f6-179">This interface has not been implemented yet.</span></span>  
  
 <span data-ttu-id="274f6-180">[ICorDebugController (interfaz)](icordebugcontroller-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-180">[ICorDebugController Interface](icordebugcontroller-interface.md)</span></span>\
 <span data-ttu-id="274f6-181">Representa un ámbito, <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, en el que se puede controlar el contexto de ejecución de código.</span><span class="sxs-lookup"><span data-stu-id="274f6-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 <span data-ttu-id="274f6-182">[Interfaz ICorDebugDataTarget](icordebugdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-182">[ICorDebugDataTarget Interface](icordebugdatatarget-interface.md)</span></span>\
 <span data-ttu-id="274f6-183">Proporciona una interfaz de devolución de llamada que brinda acceso a un proceso de destino determinado.</span><span class="sxs-lookup"><span data-stu-id="274f6-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 <span data-ttu-id="274f6-184">[Interfaz método icordebugdatatarget2](icordebugdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-184">[ICorDebugDataTarget2 Interface](icordebugdatatarget2-interface.md)</span></span>\
 <span data-ttu-id="274f6-185">Extiende lógicamente la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="274f6-185">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="274f6-186">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="274f6-186">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="274f6-187">[Interfaz ICorDebugDataTarget3](icordebugdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-187">[ICorDebugDataTarget3 Interface](icordebugdatatarget3-interface.md)</span></span>\
 <span data-ttu-id="274f6-188">Extiende lógicamente la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md) para proporcionar información sobre los módulos cargados.</span><span class="sxs-lookup"><span data-stu-id="274f6-188">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="274f6-189">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="274f6-189">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="274f6-190">[Interfaz ICorDebugDebugEvent](icordebugdebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-190">[ICorDebugDebugEvent Interface](icordebugdebugevent-interface.md)</span></span>\
 <span data-ttu-id="274f6-191">Define la interfaz base de la que derivan todos los eventos de depuración `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="274f6-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="274f6-192">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="274f6-192">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="274f6-193">[Interfaz ICorDebugEditAndContinueErrorInfo](icordebugeditandcontinueerrorinfo-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-193">[ICorDebugEditAndContinueErrorInfo Interface](icordebugeditandcontinueerrorinfo-interface.md)</span></span>\
 <span data-ttu-id="274f6-194">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="274f6-194">Obsolete.</span></span> <span data-ttu-id="274f6-195">No utilice esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="274f6-195">Do not use this interface.</span></span>  
  
 <span data-ttu-id="274f6-196">[Interfaz ICorDebugEditAndContinueSnapshot](icordebugeditandcontinuesnapshot-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-196">[ICorDebugEditAndContinueSnapshot Interface](icordebugeditandcontinuesnapshot-interface.md)</span></span>\
 <span data-ttu-id="274f6-197">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="274f6-197">Obsolete.</span></span> <span data-ttu-id="274f6-198">No utilice esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="274f6-198">Do not use this interface.</span></span>  
  
 <span data-ttu-id="274f6-199">[ICorDebugEnum (interfaz)](icordebugenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-199">[ICorDebugEnum Interface](icordebugenum-interface1.md)</span></span>\
 <span data-ttu-id="274f6-200">Actúa como la interfaz base abstracta para la depuración de enumeradores.</span><span class="sxs-lookup"><span data-stu-id="274f6-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 <span data-ttu-id="274f6-201">[Interfaz Icordebugerrorinfoenum (](icordebugerrorinfoenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-201">[ICorDebugErrorInfoEnum Interface](icordebugerrorinfoenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-202">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="274f6-202">Obsolete.</span></span> <span data-ttu-id="274f6-203">No utilice esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="274f6-203">Do not use this interface.</span></span>  
  
 <span data-ttu-id="274f6-204">[ICorDebugEval (interfaz)](icordebugeval-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-204">[ICorDebugEval Interface](icordebugeval-interface.md)</span></span>\
 <span data-ttu-id="274f6-205">Proporciona métodos que permiten al depurador ejecutar código en el contexto del código que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="274f6-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 <span data-ttu-id="274f6-206">[Interfaz ICorDebugEval2](icordebugeval2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-206">[ICorDebugEval2 Interface](icordebugeval2-interface.md)</span></span>\
 <span data-ttu-id="274f6-207">Extiende `ICorDebugEval` para proporcionar compatibilidad con los tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="274f6-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 <span data-ttu-id="274f6-208">[Interfaz ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-208">[ICorDebugExceptionDebugEvent Interface](icordebugexceptiondebugevent-interface.md)</span></span>\
 <span data-ttu-id="274f6-209">Extiende la interfaz [ICorDebugDebugEvent](icordebugdebugevent-interface.md) para admitir eventos de excepción.</span><span class="sxs-lookup"><span data-stu-id="274f6-209">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="274f6-210">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="274f6-210">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="274f6-211">[Interfaz Icordebugexceptionobjectcallstackenum (](icordebugexceptionobjectcallstackenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-211">[ICorDebugExceptionObjectCallStackEnum Interface](icordebugexceptionobjectcallstackenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-212">Proporciona un enumerador para la información de la pila de llamadas que está incrustada en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="274f6-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 <span data-ttu-id="274f6-213">[Interfaz Icordebugexceptionobjectvalue (](icordebugexceptionobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-213">[ICorDebugExceptionObjectValue Interface](icordebugexceptionobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="274f6-214">Extiende la interfaz [ICorDebugObjectValue](icordebugobjectvalue-interface.md) para proporcionar información de seguimiento de la pila de un objeto de excepción administrado.</span><span class="sxs-lookup"><span data-stu-id="274f6-214">Extends the [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 <span data-ttu-id="274f6-215">[ICorDebugFrame (interfaz)](icordebugframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-215">[ICorDebugFrame Interface](icordebugframe-interface.md)</span></span>\
 <span data-ttu-id="274f6-216">Representa un marco en la pila actual.</span><span class="sxs-lookup"><span data-stu-id="274f6-216">Represents a frame on the current stack.</span></span>  
  
 <span data-ttu-id="274f6-217">[Interfaz ICorDebugFrameEnum (](icordebugframeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-217">[ICorDebugFrameEnum Interface](icordebugframeenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-218">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="274f6-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 <span data-ttu-id="274f6-219">[ICorDebugFunction (interfaz)](icordebugfunction-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-219">[ICorDebugFunction Interface](icordebugfunction-interface1.md)</span></span>\
 <span data-ttu-id="274f6-220">Representa una función o un método administrado.</span><span class="sxs-lookup"><span data-stu-id="274f6-220">Represents a managed function or method.</span></span>  
  
 <span data-ttu-id="274f6-221">[ICorDebugFunction2 (interfaz)](icordebugfunction2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-221">[ICorDebugFunction2 Interface](icordebugfunction2-interface.md)</span></span>\
 <span data-ttu-id="274f6-222">Extiende `ICorDebugFunction` de manera lógica para ofrecer compatibilidad con la depuración paso a paso de "Sólo mi código".</span><span class="sxs-lookup"><span data-stu-id="274f6-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 <span data-ttu-id="274f6-223">[Interfaz Icordebugfunction3 (](icordebugfunction3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-223">[ICorDebugFunction3 Interface](icordebugfunction3-interface.md)</span></span>\
 <span data-ttu-id="274f6-224">Extiende lógicamente la interfaz [ICorDebugFunction](icordebugfunction-interface1.md) para proporcionar acceso al código desde una solicitud ReJIT.</span><span class="sxs-lookup"><span data-stu-id="274f6-224">Logically extends the [ICorDebugFunction](icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 <span data-ttu-id="274f6-225">[Interfaz ICorDebugFunctionBreakpoint](icordebugfunctionbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-225">[ICorDebugFunctionBreakpoint Interface](icordebugfunctionbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="274f6-226">Amplía `ICorDebugBreakpoint` para admitir los puntos de interrupción dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="274f6-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 <span data-ttu-id="274f6-227">[Interfaz Icordebuggcreferenceenum (](icordebuggcreferenceenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-227">[ICorDebugGCReferenceEnum Interface](icordebuggcreferenceenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-228">Proporciona un enumerador para los objetos que se recolectarán como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="274f6-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 <span data-ttu-id="274f6-229">[Interfaz ICorDebugGenericValue](icordebuggenericvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-229">[ICorDebugGenericValue Interface](icordebuggenericvalue-interface.md)</span></span>\
 <span data-ttu-id="274f6-230">Subclase de `ICorDebugValue` que se aplica a todos los valores.</span><span class="sxs-lookup"><span data-stu-id="274f6-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="274f6-231">Esta interfaz proporciona métodos Get y Set para el valor.</span><span class="sxs-lookup"><span data-stu-id="274f6-231">This interface provides Get and Set methods for the value.</span></span>  
  
 <span data-ttu-id="274f6-232">[Interfaz Icordebugguidtotypeenum (](icordebugguidtotypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-232">[ICorDebugGuidToTypeEnum Interface](icordebugguidtotypeenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-233">Proporciona un enumerador para un objeto que asigna GUID y sus objetos `ICorDebugType` correspondientes.</span><span class="sxs-lookup"><span data-stu-id="274f6-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 <span data-ttu-id="274f6-234">[ICorDebugHandleValue (interfaz)](icordebughandlevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-234">[ICorDebugHandleValue Interface](icordebughandlevalue-interface.md)</span></span>\
 <span data-ttu-id="274f6-235">Subclase de `ICorDebugReferenceValue` que representa un valor de referencia para el cual el depurador ha creado un identificador para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="274f6-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 <span data-ttu-id="274f6-236">[Interfaz Icordebugheapenum (](icordebugheapenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-236">[ICorDebugHeapEnum Interface](icordebugheapenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-237">Proporciona un enumerador para los objetos del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="274f6-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 <span data-ttu-id="274f6-238">[Interfaz Icordebugheapsegmentenum (](icordebugheapsegmentenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-238">[ICorDebugHeapSegmentEnum Interface](icordebugheapsegmentenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-239">Proporciona un enumerador para las regiones de memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="274f6-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 <span data-ttu-id="274f6-240">[ICorDebugHeapValue (interfaz)](icordebugheapvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-240">[ICorDebugHeapValue Interface](icordebugheapvalue-interface.md)</span></span>\
 <span data-ttu-id="274f6-241">Subclase de `ICorDebugValue` que representa un objeto que ha sido recopilado por el recolector de elementos no utilizados de CLR.</span><span class="sxs-lookup"><span data-stu-id="274f6-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 <span data-ttu-id="274f6-242">[Interfaz Icordebugheapvalue2 (](icordebugheapvalue2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-242">[ICorDebugHeapValue2 Interface](icordebugheapvalue2-interface1.md)</span></span>\
 <span data-ttu-id="274f6-243">Extensión de `ICorDebugHeapValue` que proporciona compatibilidad con los identificadores del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="274f6-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 <span data-ttu-id="274f6-244">[Interfaz ICorDebugHeapValue3](icordebugheapvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-244">[ICorDebugHeapValue3 Interface](icordebugheapvalue3-interface.md)</span></span>\
 <span data-ttu-id="274f6-245">Expone las propiedades de bloqueo de monitor de objetos.</span><span class="sxs-lookup"><span data-stu-id="274f6-245">Exposes the monitor lock properties of objects.</span></span>  
  
 <span data-ttu-id="274f6-246">[Interfaz ICorDebugILCode](icordebugilcode-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-246">[ICorDebugILCode Interface](icordebugilcode-interface.md)</span></span>\
 <span data-ttu-id="274f6-247">Representa un segmento de código de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="274f6-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 <span data-ttu-id="274f6-248">[Interfaz ICorDebugILCode2](icordebugilcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-248">[ICorDebugILCode2 Interface](icordebugilcode2-interface.md)</span></span>\
 <span data-ttu-id="274f6-249">Extiende lógicamente la interfaz [ICorDebugILCode](icordebugilcode-interface.md) para proporcionar métodos que devuelven el token de la firma de variable local de una función y que asignan los desplazamientos del lenguaje intermedio INSTRUMENTADO (IL) del generador de perfiles a los desplazamientos de Il del método original.</span><span class="sxs-lookup"><span data-stu-id="274f6-249">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 <span data-ttu-id="274f6-250">[ICorDebugILFrame (interfaz)](icordebugilframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-250">[ICorDebugILFrame Interface](icordebugilframe-interface.md)</span></span>\
 <span data-ttu-id="274f6-251">Representa un marco de pila de código de MSIL.</span><span class="sxs-lookup"><span data-stu-id="274f6-251">Represents a stack frame of MSIL code.</span></span>  
  
 <span data-ttu-id="274f6-252">[Interfaz ICorDebugILFrame2](icordebugilframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-252">[ICorDebugILFrame2 Interface](icordebugilframe2-interface.md)</span></span>\
 <span data-ttu-id="274f6-253">Extensión lógica de `ICorDebugILFrame`.</span><span class="sxs-lookup"><span data-stu-id="274f6-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 <span data-ttu-id="274f6-254">[Interfaz ICorDebugILFrame3](icordebugilframe3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-254">[ICorDebugILFrame3 Interface](icordebugilframe3-interface.md)</span></span>\
 <span data-ttu-id="274f6-255">Proporciona un método que encapsula el valor devuelto de una función.</span><span class="sxs-lookup"><span data-stu-id="274f6-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 <span data-ttu-id="274f6-256">[Interfaz ICorDebugILFrame4](icordebugilframe4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-256">[ICorDebugILFrame4 Interface](icordebugilframe4-interface.md)</span></span>\
 <span data-ttu-id="274f6-257">Proporciona métodos que permiten acceder a las variables locales y al código en un marco de pila de código de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="274f6-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="274f6-258">Un parámetro especifica si el depurador tiene acceso a las variables y al código agregados en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="274f6-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 <span data-ttu-id="274f6-259">[Interfaz ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-259">[ICorDebugInstanceFieldSymbol Interface](icordebuginstancefieldsymbol-interface.md)</span></span>\
 <span data-ttu-id="274f6-260">Representa la información de símbolos de depuración para un campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="274f6-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="274f6-261">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="274f6-261">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="274f6-262">[Interfaz ICorDebugInternalFrame (](icordebuginternalframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-262">[ICorDebugInternalFrame Interface](icordebuginternalframe-interface.md)</span></span>\
 <span data-ttu-id="274f6-263">Identifica los tipos de marco del depurador.</span><span class="sxs-lookup"><span data-stu-id="274f6-263">Identifies frame types for the debugger.</span></span>  
  
 <span data-ttu-id="274f6-264">[Interfaz ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-264">[ICorDebugInternalFrame2 Interface](icordebuginternalframe2-interface.md)</span></span>\
 <span data-ttu-id="274f6-265">Proporciona información sobre los marcos internos, incluida la dirección de pila y la posición en relación con los objetos [ICorDebugFrame](icordebugframe-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="274f6-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](icordebugframe-interface.md) objects.</span></span>  
  
 <span data-ttu-id="274f6-266">[Interfaz ICorDebugLoadedModule](icordebugloadedmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-266">[ICorDebugLoadedModule Interface](icordebugloadedmodule-interface.md)</span></span>\
 <span data-ttu-id="274f6-267">Proporciona información acerca de un módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="274f6-267">Provides information about a loaded module.</span></span> <span data-ttu-id="274f6-268">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="274f6-268">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="274f6-269">[ICorDebugManagedCallback (interfaz)](icordebugmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-269">[ICorDebugManagedCallback Interface](icordebugmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="274f6-270">Proporciona métodos que permiten procesar las devoluciones de llamada del depurador.</span><span class="sxs-lookup"><span data-stu-id="274f6-270">Provides methods to process debugger callbacks.</span></span>  
  
 <span data-ttu-id="274f6-271">[Interfaz ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-271">[ICorDebugManagedCallback2 Interface](icordebugmanagedcallback2-interface.md)</span></span>\
 <span data-ttu-id="274f6-272">Proporciona métodos para admitir el control de excepciones del depurador y asistentes para depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="274f6-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="274f6-273">`ICorDebugManagedCallback2` es una extensión lógica de `ICorDebugManagedCallback`.</span><span class="sxs-lookup"><span data-stu-id="274f6-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 <span data-ttu-id="274f6-274">[Interfaz Icordebugmanagedcallback3 (](icordebugmanagedcallback3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-274">[ICorDebugManagedCallback3 Interface](icordebugmanagedcallback3-interface.md)</span></span>\
 <span data-ttu-id="274f6-275">Proporciona un método de devolución de llamada que indica que se ha producido una notificación del depurador personalizada habilitada.</span><span class="sxs-lookup"><span data-stu-id="274f6-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 <span data-ttu-id="274f6-276">[ICorDebugMDA (interfaz)](icordebugmda-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-276">[ICorDebugMDA Interface](icordebugmda-interface.md)</span></span>\
 <span data-ttu-id="274f6-277">Representa un mensaje del asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="274f6-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 <span data-ttu-id="274f6-278">[Interfaz ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-278">[ICorDebugMemoryBuffer Interface](icordebugmemorybuffer-interface.md)</span></span>\
 <span data-ttu-id="274f6-279">Representa un búfer en memoria.</span><span class="sxs-lookup"><span data-stu-id="274f6-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="274f6-280">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="274f6-280">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="274f6-281">[Interfaz ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-281">[ICorDebugMergedAssemblyRecord Interface](icordebugmergedassemblyrecord-interface.md)</span></span>\
 <span data-ttu-id="274f6-282">Proporciona información acerca de un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="274f6-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="274f6-283">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="274f6-283">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="274f6-284">[Interfaz ICorDebugMetaDataLocator (](icordebugmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-284">[ICorDebugMetaDataLocator Interface](icordebugmetadatalocator-interface.md)</span></span>\
 <span data-ttu-id="274f6-285">Proporciona información de metadatos al depurador.</span><span class="sxs-lookup"><span data-stu-id="274f6-285">Provides metadata information to the debugger.</span></span>  
  
 <span data-ttu-id="274f6-286">[ICorDebugModule (interfaz)](icordebugmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-286">[ICorDebugModule Interface](icordebugmodule-interface.md)</span></span>\
 <span data-ttu-id="274f6-287">Representa un módulo de CLR, que es un archivo ejecutable o una biblioteca de vínculos dinámicos (DLL).</span><span class="sxs-lookup"><span data-stu-id="274f6-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 <span data-ttu-id="274f6-288">[Interfaz ICorDebugModule2](icordebugmodule2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-288">[ICorDebugModule2 Interface](icordebugmodule2-interface.md)</span></span>\
 <span data-ttu-id="274f6-289">Actúa como una extensión lógica de `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="274f6-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 <span data-ttu-id="274f6-290">[Interfaz ICorDebugModule3](icordebugmodule3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-290">[ICorDebugModule3 Interface](icordebugmodule3-interface.md)</span></span>\
 <span data-ttu-id="274f6-291">Crea un lector de símbolos para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="274f6-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 <span data-ttu-id="274f6-292">[Interfaz ICorDebugModuleBreakpoint (](icordebugmodulebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-292">[ICorDebugModuleBreakpoint Interface](icordebugmodulebreakpoint-interface.md)</span></span>\
 <span data-ttu-id="274f6-293">Extiende `ICorDebugBreakpoint` para proporcionar acceso a módulos específicos.</span><span class="sxs-lookup"><span data-stu-id="274f6-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 <span data-ttu-id="274f6-294">[Interfaz ICorDebugModuleDebugEvent](icordebugmoduledebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-294">[ICorDebugModuleDebugEvent Interface](icordebugmoduledebugevent-interface.md)</span></span>\
 <span data-ttu-id="274f6-295">Extiende la interfaz [ICorDebugDebugEvent](icordebugdebugevent-interface.md) para admitir eventos de nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="274f6-295">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="274f6-296">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="274f6-296">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="274f6-297">[Interfaz ICorDebugModuleEnum (](icordebugmoduleenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-297">[ICorDebugModuleEnum Interface](icordebugmoduleenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-298">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="274f6-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 <span data-ttu-id="274f6-299">[Interfaz ICorDebugMutableDataTarget](icordebugmutabledatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-299">[ICorDebugMutableDataTarget Interface](icordebugmutabledatatarget-interface.md)</span></span>\
 <span data-ttu-id="274f6-300">Extiende la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md) para admitir destinos de datos mutables.</span><span class="sxs-lookup"><span data-stu-id="274f6-300">Extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 <span data-ttu-id="274f6-301">[ICorDebugNativeFrame (interfaz)](icordebugnativeframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-301">[ICorDebugNativeFrame Interface](icordebugnativeframe-interface.md)</span></span>\
 <span data-ttu-id="274f6-302">Implementación especializada de `ICorDebugFrame` que se utiliza para los marcos nativos.</span><span class="sxs-lookup"><span data-stu-id="274f6-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 <span data-ttu-id="274f6-303">[Interfaz ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-303">[ICorDebugNativeFrame2 Interface](icordebugnativeframe2-interface.md)</span></span>\
 <span data-ttu-id="274f6-304">Proporciona métodos que comprueban las relaciones entre marcos primarios y secundarios.</span><span class="sxs-lookup"><span data-stu-id="274f6-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 <span data-ttu-id="274f6-305">[Interfaz ICorDebugObjectEnum (](icordebugobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-305">[ICorDebugObjectEnum Interface](icordebugobjectenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-306">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de objetos según sus direcciones virtuales relativas (RVA).</span><span class="sxs-lookup"><span data-stu-id="274f6-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 <span data-ttu-id="274f6-307">[ICorDebugObjectValue (interfaz)](icordebugobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-307">[ICorDebugObjectValue Interface](icordebugobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="274f6-308">Subclase de `ICorDebugValue` que representa un valor que contiene un objeto.</span><span class="sxs-lookup"><span data-stu-id="274f6-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 <span data-ttu-id="274f6-309">[Interfaz Icordebugobjectvalue2 (](icordebugobjectvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-309">[ICorDebugObjectValue2 Interface](icordebugobjectvalue2-interface.md)</span></span>\
 <span data-ttu-id="274f6-310">Extiende `ICorDebugObjectValue` para ofrecer compatibilidad con la herencia y los reemplazos.</span><span class="sxs-lookup"><span data-stu-id="274f6-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 <span data-ttu-id="274f6-311">[ICorDebugProcess (interfaz)](icordebugprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-311">[ICorDebugProcess Interface](icordebugprocess-interface.md)</span></span>\
 <span data-ttu-id="274f6-312">Representa un proceso que ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="274f6-312">Represents a process that is executing managed code.</span></span>  
  
 <span data-ttu-id="274f6-313">[Interfaz ICorDebugProcess2](icordebugprocess2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-313">[ICorDebugProcess2 Interface](icordebugprocess2-interface1.md)</span></span>\
 <span data-ttu-id="274f6-314">Extensión lógica de `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="274f6-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 <span data-ttu-id="274f6-315">[Interfaz Icordebugprocess3 (](icordebugprocess3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-315">[ICorDebugProcess3 Interface](icordebugprocess3-interface.md)</span></span>\
 <span data-ttu-id="274f6-316">Controla las notificaciones del depurador personalizadas.</span><span class="sxs-lookup"><span data-stu-id="274f6-316">Controls custom debugger notifications.</span></span>

 <span data-ttu-id="274f6-317">[Interfaz ICorDebugProcess4](icordebugprocess4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-317">[ICorDebugProcess4 Interface](icordebugprocess4-interface.md)</span></span>\
 <span data-ttu-id="274f6-318">Proporciona compatibilidad para el control de ejecución fuera de proceso.</span><span class="sxs-lookup"><span data-stu-id="274f6-318">Provides support for out of process execution control.</span></span>
  
 <span data-ttu-id="274f6-319">[Interfaz ICorDebugProcess5](icordebugprocess5-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-319">[ICorDebugProcess5 Interface](icordebugprocess5-interface.md)</span></span>\
 <span data-ttu-id="274f6-320">Extiende la interfaz [ICorDebugProcess](icordebugprocess-interface.md) para admitir el acceso al montón administrado, para proporcionar información sobre la recolección de elementos no utilizados de objetos administrados y para determinar si un depurador carga imágenes desde la memoria caché de imágenes nativas local de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="274f6-320">Extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 <span data-ttu-id="274f6-321">[Interfaz método icordebugprocess6](icordebugprocess6-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-321">[ICorDebugProcess6 Interface](icordebugprocess6-interface.md)</span></span>\
 <span data-ttu-id="274f6-322">Extiende lógicamente la interfaz [ICorDebugProcess](icordebugprocess-interface.md) para habilitar características como la descodificación de eventos de depuración administrados codificados en eventos de depuración de excepción nativa y la división de módulos virtuales.</span><span class="sxs-lookup"><span data-stu-id="274f6-322">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="274f6-323">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="274f6-323">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="274f6-324">[Interfaz Icordebugprocess7 (](icordebugprocess7-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-324">[ICorDebugProcess7 Interface](icordebugprocess7-interface.md)</span></span>\
 <span data-ttu-id="274f6-325">Proporciona un método que configura el depurador para controlar las actualizaciones en memoria de los metadatos en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="274f6-325">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 <span data-ttu-id="274f6-326">[Interfaz ICorDebugProcess8](icordebugprocess8-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-326">[ICorDebugProcess8 Interface](icordebugprocess8-interface.md)</span></span>\
 <span data-ttu-id="274f6-327">Extiende lógicamente la interfaz [ICorDebugProcess](icordebugprocess-interface.md) para habilitar o deshabilitar determinados tipos de devoluciones de llamada de excepción [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="274f6-327">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 <span data-ttu-id="274f6-328">[Interfaz Icordebugprocessenum (](icordebugprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-328">[ICorDebugProcessEnum Interface](icordebugprocessenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-329">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="274f6-329">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 <span data-ttu-id="274f6-330">[ICorDebugReferenceValue (interfaz)](icordebugreferencevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-330">[ICorDebugReferenceValue Interface](icordebugreferencevalue-interface.md)</span></span>\
 <span data-ttu-id="274f6-331">Subclase de `ICorDebugValue` que admite tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="274f6-331">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 <span data-ttu-id="274f6-332">[ICorDebugRegisterSet (interfaz)](icordebugregisterset-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-332">[ICorDebugRegisterSet Interface](icordebugregisterset-interface.md)</span></span>\
 <span data-ttu-id="274f6-333">Representa el conjunto de registros disponibles en el equipo que está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="274f6-333">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 <span data-ttu-id="274f6-334">[Interfaz ICorDebugRegisterSet2](icordebugregisterset2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-334">[ICorDebugRegisterSet2 Interface](icordebugregisterset2-interface.md)</span></span>\
 <span data-ttu-id="274f6-335">Extiende la funcionalidad de `ICorDebugRegisterSet` para plataformas hardware que tienen más de 64 registros.</span><span class="sxs-lookup"><span data-stu-id="274f6-335">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 <span data-ttu-id="274f6-336">[Interfaz ICorDebugRemote](icordebugremote-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-336">[ICorDebugRemote Interface](icordebugremote-interface.md)</span></span>\
 <span data-ttu-id="274f6-337">Proporciona la capacidad de iniciar o de adjuntar un depurador administrado a un proceso remoto de destino.</span><span class="sxs-lookup"><span data-stu-id="274f6-337">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 <span data-ttu-id="274f6-338">[Interfaz ICorDebugRemoteTarget](icordebugremotetarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-338">[ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md)</span></span>\
 <span data-ttu-id="274f6-339">Proporciona métodos que permiten depurar aplicaciones basadas en Silverlight en el entorno de CLR.</span><span class="sxs-lookup"><span data-stu-id="274f6-339">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="274f6-340">[Interfaz Icordebugruntimeunwindableframe (](icordebugruntimeunwindableframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-340">[ICorDebugRuntimeUnwindableFrame Interface](icordebugruntimeunwindableframe-interface.md)</span></span>\
 <span data-ttu-id="274f6-341">Proporciona compatibilidad para métodos no administrados que necesitan que Common Language Runtime (CLR) desenrede un marco.</span><span class="sxs-lookup"><span data-stu-id="274f6-341">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 <span data-ttu-id="274f6-342">[ICorDebugStackWalk (interfaz)](icordebugstackwalk-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-342">[ICorDebugStackWalk Interface](icordebugstackwalk-interface.md)</span></span>\
 <span data-ttu-id="274f6-343">Proporciona métodos para obtener los métodos administrados, o marcos, de la pila de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="274f6-343">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 <span data-ttu-id="274f6-344">[Interfaz ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-344">[ICorDebugStaticFieldSymbol Interface](icordebugstaticfieldsymbol-interface.md)</span></span>\
 <span data-ttu-id="274f6-345">Representa la información de símbolos de depuración para un campo estático.</span><span class="sxs-lookup"><span data-stu-id="274f6-345">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="274f6-346">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="274f6-346">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="274f6-347">[ICorDebugStepper (interfaz)](icordebugstepper-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-347">[ICorDebugStepper Interface](icordebugstepper-interface.md)</span></span>\
 <span data-ttu-id="274f6-348">Representa un paso en la ejecución del código realizado por un depurador, actúa como identificador entre la emisión y la finalización de un comando, y proporciona un modo de cancelar un paso.</span><span class="sxs-lookup"><span data-stu-id="274f6-348">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 <span data-ttu-id="274f6-349">[Interfaz Icordebugstepper2 (](icordebugstepper2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-349">[ICorDebugStepper2 Interface](icordebugstepper2-interface1.md)</span></span>\
 <span data-ttu-id="274f6-350">Proporciona compatibilidad con la depuración de "Sólo mi código" (JMC).</span><span class="sxs-lookup"><span data-stu-id="274f6-350">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 <span data-ttu-id="274f6-351">[Interfaz ICorDebugStepperEnum (](icordebugstepperenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-351">[ICorDebugStepperEnum Interface](icordebugstepperenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-352">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugStepper`.</span><span class="sxs-lookup"><span data-stu-id="274f6-352">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 <span data-ttu-id="274f6-353">[ICorDebugStringValue (interfaz)](icordebugstringvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-353">[ICorDebugStringValue Interface](icordebugstringvalue-interface.md)</span></span>\
 <span data-ttu-id="274f6-354">Subclase de `ICorDebugHeapValue` que se aplica a los valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="274f6-354">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 <span data-ttu-id="274f6-355">[Interfaz ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-355">[ICorDebugSymbolProvider Interface](icordebugsymbolprovider-interface.md)</span></span>\
 <span data-ttu-id="274f6-356">Proporciona métodos que pueden utilizarse para recuperar información de símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="274f6-356">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="274f6-357">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="274f6-357">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="274f6-358">[Interfaz Icordebugsymbolprovider2 (](icordebugsymbolprovider2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-358">[ICorDebugSymbolProvider2 Interface](icordebugsymbolprovider2-interface.md)</span></span>\
 <span data-ttu-id="274f6-359">Extiende lógicamente la interfaz [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) para recuperar información de símbolos de depuración adicional.</span><span class="sxs-lookup"><span data-stu-id="274f6-359">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="274f6-360">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="274f6-360">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="274f6-361">[ICorDebugThread (interfaz)](icordebugthread-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-361">[ICorDebugThread Interface](icordebugthread-interface.md)</span></span>\
 <span data-ttu-id="274f6-362">Representa un subproceso de un proceso.</span><span class="sxs-lookup"><span data-stu-id="274f6-362">Represents a thread in a process.</span></span> <span data-ttu-id="274f6-363">El período de duración de una instancia de `ICorDebugThread` es el mismo que el del subproceso que representa.</span><span class="sxs-lookup"><span data-stu-id="274f6-363">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 <span data-ttu-id="274f6-364">[Interfaz ICorDebugThread2](icordebugthread2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-364">[ICorDebugThread2 Interface](icordebugthread2-interface.md)</span></span>\
 <span data-ttu-id="274f6-365">Actúa como una extensión lógica de `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="274f6-365">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 <span data-ttu-id="274f6-366">[Interfaz ICorDebugThread3](icordebugthread3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-366">[ICorDebugThread3 Interface](icordebugthread3-interface.md)</span></span>\
 <span data-ttu-id="274f6-367">Proporciona el punto de entrada a [ICorDebugStackWalk](icordebugstackwalk-interface.md) y las interfaces correspondientes.</span><span class="sxs-lookup"><span data-stu-id="274f6-367">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 <span data-ttu-id="274f6-368">[Interfaz ICorDebugThread4](icordebugthread4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-368">[ICorDebugThread4 Interface](icordebugthread4-interface.md)</span></span>\
 <span data-ttu-id="274f6-369">Proporciona información de bloqueo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="274f6-369">Provides thread blocking information.</span></span>  
  
 <span data-ttu-id="274f6-370">[Interfaz ICorDebugThreadEnum (](icordebugthreadenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-370">[ICorDebugThreadEnum Interface](icordebugthreadenum-interface1.md)</span></span>\
 <span data-ttu-id="274f6-371">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="274f6-371">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 <span data-ttu-id="274f6-372">[ICorDebugType (interfaz)](icordebugtype-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-372">[ICorDebugType Interface](icordebugtype-interface.md)</span></span>\
 <span data-ttu-id="274f6-373">Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="274f6-373">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="274f6-374">Si el tipo es genérico, `ICorDebugType` representa el tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="274f6-374">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 <span data-ttu-id="274f6-375">[Interfaz ICorDebugType2](icordebugtype2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-375">[ICorDebugType2 Interface](icordebugtype2-interface.md)</span></span>\
 <span data-ttu-id="274f6-376">Extiende la interfaz [ICorDebugType](icordebugtype-interface.md) para recuperar el identificador de tipo de un tipo base o un tipo complejo (definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="274f6-376">Extends the [ICorDebugType](icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 <span data-ttu-id="274f6-377">[ICorDebugTypeEnum (interfaz)](icordebugtypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-377">[ICorDebugTypeEnum Interface](icordebugtypeenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-378">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="274f6-378">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 <span data-ttu-id="274f6-379">[Interfaz ICorDebugUnmanagedCallback (](icordebugunmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-379">[ICorDebugUnmanagedCallback Interface](icordebugunmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="274f6-380">Proporciona notificación de eventos nativos no relacionados directamente con CLR.</span><span class="sxs-lookup"><span data-stu-id="274f6-380">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="274f6-381">[ICorDebugValue](icordebugvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-381">[ICorDebugValue](icordebugvalue-interface.md)</span></span>\
 <span data-ttu-id="274f6-382">Representa un valor de escritura o lectura en el proceso que se va a depurar.</span><span class="sxs-lookup"><span data-stu-id="274f6-382">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="274f6-383">[ICorDebugValue2](icordebugvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-383">[ICorDebugValue2](icordebugvalue2-interface.md)</span></span>\
 <span data-ttu-id="274f6-384">Extiende `ICorDebugValue` para proporcionar compatibilidad con `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="274f6-384">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="274f6-385">[Interfaz Icordebugvalue3 (](icordebugvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-385">[ICorDebugValue3 Interface](icordebugvalue3-interface.md)</span></span>\
 <span data-ttu-id="274f6-386">Extiende las interfaces "ICorDebugValue" y "ICorDebugValue2" para proporcionar compatibilidad con matrices mayores de 2 GB.</span><span class="sxs-lookup"><span data-stu-id="274f6-386">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="274f6-387">[Icordebugvaluebreakpoint (](icordebugvaluebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)</span></span>\
 <span data-ttu-id="274f6-388">Extiende `ICorDebugBreakpoint` para proporcionar acceso a valores concretos.</span><span class="sxs-lookup"><span data-stu-id="274f6-388">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="274f6-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-390">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="274f6-390">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 <span data-ttu-id="274f6-391">[Interfaz ICorDebugVariableHome](icordebugvariablehome-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-391">[ICorDebugVariableHome Interface](icordebugvariablehome-interface.md)</span></span>\
 <span data-ttu-id="274f6-392">Representa una variable local o un argumento de una función.</span><span class="sxs-lookup"><span data-stu-id="274f6-392">Represents a local variable or argument of a function.</span></span>  
  
 <span data-ttu-id="274f6-393">[Interfaz ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-393">[ICorDebugVariableHomeEnum Interface](icordebugvariablehomeenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-394">Proporciona un enumerador para las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="274f6-394">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="274f6-395">[Interfaz ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-395">[ICorDebugVariableSymbol Interface](icordebugvariablesymbol-interface.md)</span></span>\
 <span data-ttu-id="274f6-396">Recupera la información de símbolos de depuración para una variable.</span><span class="sxs-lookup"><span data-stu-id="274f6-396">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="274f6-397">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="274f6-397">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="274f6-398">[Interfaz ICorDebugVirtualUnwinder](icordebugvirtualunwinder-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-398">[ICorDebugVirtualUnwinder Interface](icordebugvirtualunwinder-interface.md)</span></span>\
 <span data-ttu-id="274f6-399">Proporciona métodos que ayudan al desenredo de la pila.</span><span class="sxs-lookup"><span data-stu-id="274f6-399">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="274f6-400">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="274f6-400">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="274f6-401">[ICorPublish (interfaz)](icorpublish-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-401">[ICorPublish Interface](icorpublish-interface.md)</span></span>\
 <span data-ttu-id="274f6-402">Actúa como interfaz general para los procesos de publicación.</span><span class="sxs-lookup"><span data-stu-id="274f6-402">Serves as the general interface for the publishing processes.</span></span>  
  
 <span data-ttu-id="274f6-403">[ICorPublishAppDomain (interfaz)](icorpublishappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-403">[ICorPublishAppDomain Interface](icorpublishappdomain-interface.md)</span></span>\
 <span data-ttu-id="274f6-404">Representa y proporciona información sobre un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="274f6-404">Represents and provides information about an application domain.</span></span>  
  
 <span data-ttu-id="274f6-405">[Interfaz ICorPublishAppDomainEnum (](icorpublishappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-405">[ICorPublishAppDomainEnum Interface](icorpublishappdomainenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-406">Proporciona métodos que atraviesan una colección de objetos `ICorPublishAppDomain` que actualmente existen dentro de un proceso.</span><span class="sxs-lookup"><span data-stu-id="274f6-406">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 <span data-ttu-id="274f6-407">[ICorPublishEnum (interfaz)](icorpublishenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-407">[ICorPublishEnum Interface](icorpublishenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-408">Actúa como la base abstracta para los enumeradores de publicación.</span><span class="sxs-lookup"><span data-stu-id="274f6-408">Serves as the abstract base for publishing enumerators.</span></span>  
  
 <span data-ttu-id="274f6-409">[ICorPublishProcess (interfaz)](icorpublishprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-409">[ICorPublishProcess Interface](icorpublishprocess-interface.md)</span></span>\
 <span data-ttu-id="274f6-410">Proporciona métodos que tienen acceso a información de un proceso.</span><span class="sxs-lookup"><span data-stu-id="274f6-410">Provides methods that access information about a process.</span></span>  
  
 <span data-ttu-id="274f6-411">[Interfaz ICorPublishProcessEnum (](icorpublishprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-411">[ICorPublishProcessEnum Interface](icorpublishprocessenum-interface.md)</span></span>\
 <span data-ttu-id="274f6-412">Proporciona métodos que atraviesan una colección de objetos `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="274f6-412">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  

 <span data-ttu-id="274f6-413">[Interfaz ISOSDacInterface](isosdacinterface-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-413">[ISOSDacInterface Interface](isosdacinterface-interface.md)</span></span>\
 <span data-ttu-id="274f6-414">Proporciona métodos auxiliares para tener acceso a los datos de `SOS` .</span><span class="sxs-lookup"><span data-stu-id="274f6-414">Provides helper methods to access data from `SOS`.</span></span>

 <span data-ttu-id="274f6-415">[Interfaz IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-415">[IXCLRDataMethodDefinition Interface](ixclrdatamethoddefinition-interface.md)</span></span>\
 <span data-ttu-id="274f6-416">Proporciona métodos para consultar información sobre una definición de método.</span><span class="sxs-lookup"><span data-stu-id="274f6-416">Provides methods for querying information about a method definition.</span></span>

 <span data-ttu-id="274f6-417">[Interfaz IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-417">[IXCLRDataMethodInstance Interface](ixclrdatamethodinstance-interface.md)</span></span>\
 <span data-ttu-id="274f6-418">Proporciona métodos para consultar información sobre una instancia de método.</span><span class="sxs-lookup"><span data-stu-id="274f6-418">Provides methods for querying information about a method instance.</span></span>

 <span data-ttu-id="274f6-419">[Interfaz IXCLRDataModule](ixclrdatamodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-419">[IXCLRDataModule Interface](ixclrdatamodule-interface.md)</span></span>\
 <span data-ttu-id="274f6-420">Proporciona métodos para consultar información sobre un módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="274f6-420">Provides methods for querying information about a loaded module.</span></span>

 <span data-ttu-id="274f6-421">[Interfaz IXCLRDataProcess](ixclrdataprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-421">[IXCLRDataProcess Interface](ixclrdataprocess-interface.md)</span></span>\
 <span data-ttu-id="274f6-422">Proporciona métodos para consultar información sobre un proceso.</span><span class="sxs-lookup"><span data-stu-id="274f6-422">Provides methods for querying information about a process.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="274f6-423">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="274f6-423">Related Sections</span></span>  

 <span data-ttu-id="274f6-424">[Coclases de depuración](debugging-coclasses.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-424">[Debugging Coclasses](debugging-coclasses.md)</span></span>\
 <span data-ttu-id="274f6-425">[Funciones estáticas globales de depuración](debugging-global-static-functions.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-425">[Debugging Global Static Functions](debugging-global-static-functions.md)</span></span>\
 <span data-ttu-id="274f6-426">[Enumeraciones de depuración](debugging-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-426">[Debugging Enumerations](debugging-enumerations.md)</span></span>\
 <span data-ttu-id="274f6-427">[Estructuras de depuración](debugging-structures.md)</span><span class="sxs-lookup"><span data-stu-id="274f6-427">[Debugging Structures](debugging-structures.md)</span></span>\
