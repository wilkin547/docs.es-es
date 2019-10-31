---
title: Interfaces para depuración
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
ms.openlocfilehash: 07b39666637628102e9ffafd2c059ba0d4b51b92
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097192"
---
# <a name="debugging-interfaces"></a><span data-ttu-id="28d73-102">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="28d73-102">Debugging Interfaces</span></span>
<span data-ttu-id="28d73-103">En esta sección se describen las interfaces no administradas que controlan la depuración de un programa que se ejecuta en Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="28d73-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="28d73-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="28d73-104">In This Section</span></span>  
 <span data-ttu-id="28d73-105">[ICLRDataEnumMemoryRegions (interfaz](iclrdataenummemoryregions-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-105">[ICLRDataEnumMemoryRegions Interface](iclrdataenummemoryregions-interface.md)</span></span>\
 <span data-ttu-id="28d73-106">Proporciona un método para enumerar las regiones de memoria especificadas por los llamadores.</span><span class="sxs-lookup"><span data-stu-id="28d73-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 <span data-ttu-id="28d73-107">\ de la [interfaz ICLRDataEnumMemoryRegionsCallback (](iclrdataenummemoryregionscallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-107">[ICLRDataEnumMemoryRegionsCallback Interface](iclrdataenummemoryregionscallback-interface.md)\</span></span>
 <span data-ttu-id="28d73-108">Proporciona un método de devolución de llamada para que `EnumMemoryRegions` notifique al depurador el resultado de un intento de enumerar un área de memoria concreta.</span><span class="sxs-lookup"><span data-stu-id="28d73-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 <span data-ttu-id="28d73-109">[ICLRDataTarget (interfaz](iclrdatatarget-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-109">[ICLRDataTarget Interface](iclrdatatarget-interface.md)</span></span>\
 <span data-ttu-id="28d73-110">Proporciona métodos para la interacción con un proceso de CLR de destino.</span><span class="sxs-lookup"><span data-stu-id="28d73-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 <span data-ttu-id="28d73-111">\ de la [interfaz ICLRDataTarget2](iclrdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-111">[ICLRDataTarget2 Interface](iclrdatatarget2-interface.md)\</span></span>
 <span data-ttu-id="28d73-112">Subclase de `ICLRDataTarget` que se utiliza la capa de servicios de acceso a datos para manipular las áreas de la memoria virtual en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="28d73-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 <span data-ttu-id="28d73-113">\ de la [interfaz ICLRDataTarget3](iclrdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-113">[ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)\</span></span>
 <span data-ttu-id="28d73-114">Subclase de [ICLRDataTarget2](iclrdatatarget2-interface.md) que proporciona acceso a la información de la excepción.</span><span class="sxs-lookup"><span data-stu-id="28d73-114">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 <span data-ttu-id="28d73-115">\ de la [interfaz ICLRDebugging](iclrdebugging-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-115">[ICLRDebugging Interface](iclrdebugging-interface.md)\</span></span>
 <span data-ttu-id="28d73-116">Proporciona métodos que controlan la carga y descarga de módulos para depuración.</span><span class="sxs-lookup"><span data-stu-id="28d73-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 <span data-ttu-id="28d73-117">\ de la [interfaz ICLRDebuggingLibraryProvider (](iclrdebugginglibraryprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-117">[ICLRDebuggingLibraryProvider Interface](iclrdebugginglibraryprovider-interface.md)\</span></span>
 <span data-ttu-id="28d73-118">Incluye el método del [método ProvideLibrary (](iclrdebugginglibraryprovider-providelibrary-method.md) , que obtiene una interfaz de devolución de llamada del proveedor de bibliotecas que permite buscar y cargar a petición bibliotecas de depuración específicas de la versión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="28d73-118">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 <span data-ttu-id="28d73-119">\ de la [interfaz iclrmetadatalocator (](iclrmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-119">[ICLRMetadataLocator Interface](iclrmetadatalocator-interface.md)\</span></span>
 <span data-ttu-id="28d73-120">Interfaz utilizada por la capa de servicios de acceso a datos para buscar los metadatos de los ensamblados en un proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="28d73-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 <span data-ttu-id="28d73-121">[ICorDebug (interfaz](icordebug-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-121">[ICorDebug Interface](icordebug-interface.md)</span></span>\
 <span data-ttu-id="28d73-122">Proporciona métodos que permiten a los desarrolladores depurar las aplicaciones en el entorno de CLR.</span><span class="sxs-lookup"><span data-stu-id="28d73-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="28d73-123">[ICorDebugAppDomain (interfaz](icordebugappdomain-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-123">[ICorDebugAppDomain Interface](icordebugappdomain-interface.md)</span></span>\
 <span data-ttu-id="28d73-124">Proporciona métodos para depurar dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="28d73-124">Provides methods for debugging application domains.</span></span>  
  
 <span data-ttu-id="28d73-125">\ de la [interfaz ICorDebugAppDomain2](icordebugappdomain2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-125">[ICorDebugAppDomain2 Interface](icordebugappdomain2-interface.md)\</span></span>
 <span data-ttu-id="28d73-126">Proporciona métodos para trabajar con matrices, punteros, punteros a función y tipos ByRef.</span><span class="sxs-lookup"><span data-stu-id="28d73-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="28d73-127">Esta interfaz es una extensión de la interfaz `ICorDebugAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="28d73-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 <span data-ttu-id="28d73-128">\ de la [interfaz ICorDebugAppDomain3](icordebugappdomain3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-128">[ICorDebugAppDomain3 Interface](icordebugappdomain3-interface.md)\</span></span>
 <span data-ttu-id="28d73-129">Proporciona métodos para trabajar con los tipos de Windows Runtime en un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="28d73-129">Provides methods to work with the Windows Runtime types in an application domain.</span></span> <span data-ttu-id="28d73-130">Esta interfaz es una extensión de las interfaces `ICorDebugAppDomain` e `ICorDebugAppDomain2`.</span><span class="sxs-lookup"><span data-stu-id="28d73-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 <span data-ttu-id="28d73-131">\ de la [interfaz ICorDebugAppDomain4](icordebugappdomain4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-131">[ICorDebugAppDomain4 Interface](icordebugappdomain4-interface.md)\</span></span>
 <span data-ttu-id="28d73-132">Extiende lógicamente la interfaz [ICorDebugAppDomain](icordebugappdomain-interface.md) para obtener un objeto administrado desde un contenedor com invocable.</span><span class="sxs-lookup"><span data-stu-id="28d73-132">Logically extends the [ICorDebugAppDomain](icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 <span data-ttu-id="28d73-133">\ de la [interfaz ICorDebugAppDomainEnum (](icordebugappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-133">[ICorDebugAppDomainEnum Interface](icordebugappdomainenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-134">Proporciona un método que devuelve un número especificado de valores de `ICorDebugAppDomain` que comienzan en la siguiente posición de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="28d73-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 <span data-ttu-id="28d73-135">[ICorDebugArrayValue (interfaz](icordebugarrayvalue-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-135">[ICorDebugArrayValue Interface](icordebugarrayvalue-interface.md)</span></span>\
 <span data-ttu-id="28d73-136">Subclase de `ICorDebugHeapValue` que representa una matriz unidimensional o multidimensional.</span><span class="sxs-lookup"><span data-stu-id="28d73-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 <span data-ttu-id="28d73-137">[ICorDebugAssembly (interfaz](icordebugassembly-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-137">[ICorDebugAssembly Interface](icordebugassembly-interface.md)</span></span>\
 <span data-ttu-id="28d73-138">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="28d73-138">Represents an assembly.</span></span>  
  
 <span data-ttu-id="28d73-139">\ de la [interfaz icordebugassembly2 (](icordebugassembly2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-139">[ICorDebugAssembly2 Interface](icordebugassembly2-interface.md)\</span></span>
 <span data-ttu-id="28d73-140">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="28d73-140">Represents an assembly.</span></span> <span data-ttu-id="28d73-141">Esta interfaz es una extensión de la interfaz `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="28d73-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 <span data-ttu-id="28d73-142">\ de la [interfaz método icordebugassembly3](icordebugassembly3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-142">[ICorDebugAssembly3 Interface](icordebugassembly3-interface.md)\</span></span>
 <span data-ttu-id="28d73-143">Extiende lógicamente la interfaz [ICorDebugAssembly](icordebugassembly-interface.md) para proporcionar compatibilidad con los ensamblados de contenedor y sus ensamblados incluidos.</span><span class="sxs-lookup"><span data-stu-id="28d73-143">Logically extends the [ICorDebugAssembly](icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="28d73-144">**Solo está disponible en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="28d73-144">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="28d73-145">\ de la [interfaz ICorDebugAssemblyEnum](icordebugassemblyenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-145">[ICorDebugAssemblyEnum Interface](icordebugassemblyenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-146">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="28d73-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 <span data-ttu-id="28d73-147">\ de la [interfaz ICorDebugBlockingObjectEnum](icordebugblockingobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-147">[ICorDebugBlockingObjectEnum Interface](icordebugblockingobjectenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-148">Proporciona un enumerador para una lista de estructuras [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="28d73-148">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
 <span data-ttu-id="28d73-149">\ de la [interfaz ICorDebugBoxValue (](icordebugboxvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-149">[ICorDebugBoxValue Interface](icordebugboxvalue-interface.md)\</span></span>
 <span data-ttu-id="28d73-150">Subclase de `ICorDebugHeapValue` que representa un objeto de clase de valor al que se ha aplicado la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="28d73-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 <span data-ttu-id="28d73-151">[ICorDebugBreakpoint (interfaz](icordebugbreakpoint-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-151">[ICorDebugBreakpoint Interface](icordebugbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="28d73-152">Representa un punto de interrupción en una función o un punto de inspección en un valor.</span><span class="sxs-lookup"><span data-stu-id="28d73-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 <span data-ttu-id="28d73-153">\ de la [interfaz ICorDebugBreakpointEnum (](icordebugbreakpointenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-153">[ICorDebugBreakpointEnum Interface](icordebugbreakpointenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-154">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="28d73-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 <span data-ttu-id="28d73-155">[ICorDebugChain (interfaz](icordebugchain-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-155">[ICorDebugChain Interface](icordebugchain-interface.md)</span></span>\
 <span data-ttu-id="28d73-156">Representa un segmento de una pila de llamadas física o lógica.</span><span class="sxs-lookup"><span data-stu-id="28d73-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 <span data-ttu-id="28d73-157">\ de la [interfaz ICorDebugChainEnum (](icordebugchainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-157">[ICorDebugChainEnum Interface](icordebugchainenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-158">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugChain`.</span><span class="sxs-lookup"><span data-stu-id="28d73-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 <span data-ttu-id="28d73-159">[ICorDebugClass (interfaz](icordebugclass-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-159">[ICorDebugClass Interface](icordebugclass-interface.md)</span></span>\
 <span data-ttu-id="28d73-160">Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="28d73-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="28d73-161">Si el tipo es genérico, `ICorDebugClass` representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="28d73-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 <span data-ttu-id="28d73-162">\ de la [interfaz ICorDebugClass2](icordebugclass2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-162">[ICorDebugClass2 Interface](icordebugclass2-interface.md)\</span></span>
 <span data-ttu-id="28d73-163">Representa una clase genérica o una clase con un parámetro de método de tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="28d73-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="28d73-164">Esta interfaz extiende `ICorDebugClass`.</span><span class="sxs-lookup"><span data-stu-id="28d73-164">This interface extends `ICorDebugClass`.</span></span>  
  
 <span data-ttu-id="28d73-165">[ICorDebugCode (interfaz](icordebugcode-interface1.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-165">[ICorDebugCode Interface](icordebugcode-interface1.md)</span></span>\
 <span data-ttu-id="28d73-166">Representa un segmento de código de lenguaje intermedio de Microsoft (MSIL) o código nativo.</span><span class="sxs-lookup"><span data-stu-id="28d73-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 <span data-ttu-id="28d73-167">\ de la [interfaz ICorDebugCode2](icordebugcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-167">[ICorDebugCode2 Interface](icordebugcode2-interface.md)\</span></span>
 <span data-ttu-id="28d73-168">Proporciona métodos que amplían las funciones de `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="28d73-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 <span data-ttu-id="28d73-169">\ de la [interfaz ICorDebugCode3](icordebugcode3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-169">[ICorDebugCode3 Interface](icordebugcode3-interface.md)\</span></span>
 <span data-ttu-id="28d73-170">Proporciona un método que extiende [ICorDebugCode](icordebugcode-interface1.md) y [ICorDebugCode2](icordebugcode2-interface.md) para proporcionar información sobre un valor devuelto administrado.</span><span class="sxs-lookup"><span data-stu-id="28d73-170">Provides a method that extends [ICorDebugCode](icordebugcode-interface1.md) and [ICorDebugCode2](icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 <span data-ttu-id="28d73-171">\ de la [interfaz interfaces icordebugcode4](icordebugcode4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-171">[ICorDebugCode4 Interface](icordebugcode4-interface.md)\</span></span>
 <span data-ttu-id="28d73-172">Proporciona un método que permite a un depurador enumerar las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="28d73-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="28d73-173">\ de la [interfaz ICorDebugCodeEnum (](icordebugcodeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-173">[ICorDebugCodeEnum Interface](icordebugcodeenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-174">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="28d73-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 <span data-ttu-id="28d73-175">\ de la [interfaz ICorDebugComObjectValue](icordebugcomobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-175">[ICorDebugComObjectValue Interface](icordebugcomobjectvalue-interface.md)\</span></span>
 <span data-ttu-id="28d73-176">Proporciona métodos para recuperar objetos de la interfaz en caché.</span><span class="sxs-lookup"><span data-stu-id="28d73-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 <span data-ttu-id="28d73-177">\ de la [interfaz icordebugcontext (](icordebugcontext-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-177">[ICorDebugContext Interface](icordebugcontext-interface.md)\</span></span>
 <span data-ttu-id="28d73-178">Representa un objeto de contexto.</span><span class="sxs-lookup"><span data-stu-id="28d73-178">Represents a context object.</span></span> <span data-ttu-id="28d73-179">Esta interfaz no se ha implementado todavía.</span><span class="sxs-lookup"><span data-stu-id="28d73-179">This interface has not been implemented yet.</span></span>  
  
 <span data-ttu-id="28d73-180">[ICorDebugController (interfaz](icordebugcontroller-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-180">[ICorDebugController Interface](icordebugcontroller-interface.md)</span></span>\
 <span data-ttu-id="28d73-181">Representa un ámbito, <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, en el que se puede controlar el contexto de ejecución de código.</span><span class="sxs-lookup"><span data-stu-id="28d73-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 <span data-ttu-id="28d73-182">\ de la [interfaz ICorDebugDataTarget](icordebugdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-182">[ICorDebugDataTarget Interface](icordebugdatatarget-interface.md)\</span></span>
 <span data-ttu-id="28d73-183">Proporciona una interfaz de devolución de llamada que brinda acceso a un proceso de destino determinado.</span><span class="sxs-lookup"><span data-stu-id="28d73-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 <span data-ttu-id="28d73-184">\ de la [interfaz método icordebugdatatarget2](icordebugdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-184">[ICorDebugDataTarget2 Interface](icordebugdatatarget2-interface.md)\</span></span>
 <span data-ttu-id="28d73-185">Extiende lógicamente la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="28d73-185">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="28d73-186">**Solo está disponible en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="28d73-186">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="28d73-187">\ de la [interfaz ICorDebugDataTarget3](icordebugdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-187">[ICorDebugDataTarget3 Interface](icordebugdatatarget3-interface.md)\</span></span>
 <span data-ttu-id="28d73-188">Extiende lógicamente la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md) para proporcionar información sobre los módulos cargados.</span><span class="sxs-lookup"><span data-stu-id="28d73-188">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="28d73-189">**Solo está disponible en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="28d73-189">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="28d73-190">\ de la [interfaz ICorDebugDebugEvent](icordebugdebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-190">[ICorDebugDebugEvent Interface](icordebugdebugevent-interface.md)\</span></span>
 <span data-ttu-id="28d73-191">Define la interfaz base de la que derivan todos los eventos de depuración `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="28d73-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="28d73-192">**Solo está disponible en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="28d73-192">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="28d73-193">\ de la [interfaz ICorDebugEditAndContinueErrorInfo](icordebugeditandcontinueerrorinfo-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-193">[ICorDebugEditAndContinueErrorInfo Interface](icordebugeditandcontinueerrorinfo-interface.md)\</span></span>
 <span data-ttu-id="28d73-194">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="28d73-194">Obsolete.</span></span> <span data-ttu-id="28d73-195">No utilice esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="28d73-195">Do not use this interface.</span></span>  
  
 <span data-ttu-id="28d73-196">\ de la [interfaz ICorDebugEditAndContinueSnapshot](icordebugeditandcontinuesnapshot-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-196">[ICorDebugEditAndContinueSnapshot Interface](icordebugeditandcontinuesnapshot-interface.md)\</span></span>
 <span data-ttu-id="28d73-197">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="28d73-197">Obsolete.</span></span> <span data-ttu-id="28d73-198">No utilice esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="28d73-198">Do not use this interface.</span></span>  
  
 <span data-ttu-id="28d73-199">[ICorDebugEnum (interfaz](icordebugenum-interface1.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-199">[ICorDebugEnum Interface](icordebugenum-interface1.md)</span></span>\
 <span data-ttu-id="28d73-200">Actúa como la interfaz base abstracta para la depuración de enumeradores.</span><span class="sxs-lookup"><span data-stu-id="28d73-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 <span data-ttu-id="28d73-201">\ de la [interfaz icordebugerrorinfoenum (](icordebugerrorinfoenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-201">[ICorDebugErrorInfoEnum Interface](icordebugerrorinfoenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-202">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="28d73-202">Obsolete.</span></span> <span data-ttu-id="28d73-203">No utilice esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="28d73-203">Do not use this interface.</span></span>  
  
 <span data-ttu-id="28d73-204">[ICorDebugEval (interfaz](icordebugeval-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-204">[ICorDebugEval Interface](icordebugeval-interface.md)</span></span>\
 <span data-ttu-id="28d73-205">Proporciona métodos que permiten al depurador ejecutar código en el contexto del código que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="28d73-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 <span data-ttu-id="28d73-206">\ de la [interfaz ICorDebugEval2](icordebugeval2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-206">[ICorDebugEval2 Interface](icordebugeval2-interface.md)\</span></span>
 <span data-ttu-id="28d73-207">Extiende `ICorDebugEval` para proporcionar compatibilidad con los tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="28d73-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 <span data-ttu-id="28d73-208">\ de la [interfaz ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-208">[ICorDebugExceptionDebugEvent Interface](icordebugexceptiondebugevent-interface.md)\</span></span>
 <span data-ttu-id="28d73-209">Extiende la interfaz [ICorDebugDebugEvent](icordebugdebugevent-interface.md) para admitir eventos de excepción.</span><span class="sxs-lookup"><span data-stu-id="28d73-209">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="28d73-210">**Solo está disponible en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="28d73-210">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="28d73-211">\ de la [interfaz icordebugexceptionobjectcallstackenum (](icordebugexceptionobjectcallstackenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-211">[ICorDebugExceptionObjectCallStackEnum Interface](icordebugexceptionobjectcallstackenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-212">Proporciona un enumerador para la información de la pila de llamadas que está incrustada en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="28d73-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 <span data-ttu-id="28d73-213">\ de la [interfaz icordebugexceptionobjectvalue (](icordebugexceptionobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-213">[ICorDebugExceptionObjectValue Interface](icordebugexceptionobjectvalue-interface.md)\</span></span>
 <span data-ttu-id="28d73-214">Extiende la interfaz [ICorDebugObjectValue](icordebugobjectvalue-interface.md) para proporcionar información de seguimiento de la pila de un objeto de excepción administrado.</span><span class="sxs-lookup"><span data-stu-id="28d73-214">Extends the [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 <span data-ttu-id="28d73-215">[ICorDebugFrame (interfaz](icordebugframe-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-215">[ICorDebugFrame Interface](icordebugframe-interface.md)</span></span>\
 <span data-ttu-id="28d73-216">Representa un marco en la pila actual.</span><span class="sxs-lookup"><span data-stu-id="28d73-216">Represents a frame on the current stack.</span></span>  
  
 <span data-ttu-id="28d73-217">\ de la [interfaz ICorDebugFrameEnum (](icordebugframeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-217">[ICorDebugFrameEnum Interface](icordebugframeenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-218">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="28d73-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 <span data-ttu-id="28d73-219">[ICorDebugFunction (interfaz](icordebugfunction-interface1.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-219">[ICorDebugFunction Interface](icordebugfunction-interface1.md)</span></span>\
 <span data-ttu-id="28d73-220">Representa una función o un método administrado.</span><span class="sxs-lookup"><span data-stu-id="28d73-220">Represents a managed function or method.</span></span>  
  
 <span data-ttu-id="28d73-221">[ICorDebugFunction2 (interfaz](icordebugfunction2-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-221">[ICorDebugFunction2 Interface](icordebugfunction2-interface.md)</span></span>\
 <span data-ttu-id="28d73-222">Extiende `ICorDebugFunction` de manera lógica para ofrecer compatibilidad con la depuración paso a paso de "Sólo mi código".</span><span class="sxs-lookup"><span data-stu-id="28d73-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 <span data-ttu-id="28d73-223">\ de la [interfaz icordebugfunction3 (](icordebugfunction3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-223">[ICorDebugFunction3 Interface](icordebugfunction3-interface.md)\</span></span>
 <span data-ttu-id="28d73-224">Extiende lógicamente la interfaz [ICorDebugFunction](icordebugfunction-interface1.md) para proporcionar acceso al código desde una solicitud ReJIT.</span><span class="sxs-lookup"><span data-stu-id="28d73-224">Logically extends the [ICorDebugFunction](icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 <span data-ttu-id="28d73-225">\ de la [interfaz ICorDebugFunctionBreakpoint](icordebugfunctionbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-225">[ICorDebugFunctionBreakpoint Interface](icordebugfunctionbreakpoint-interface.md)\</span></span>
 <span data-ttu-id="28d73-226">Amplía `ICorDebugBreakpoint` para admitir los puntos de interrupción dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="28d73-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 <span data-ttu-id="28d73-227">\ de la [interfaz icordebuggcreferenceenum (](icordebuggcreferenceenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-227">[ICorDebugGCReferenceEnum Interface](icordebuggcreferenceenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-228">Proporciona un enumerador para los objetos que se recolectarán como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="28d73-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 <span data-ttu-id="28d73-229">\ de la [interfaz ICorDebugGenericValue](icordebuggenericvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-229">[ICorDebugGenericValue Interface](icordebuggenericvalue-interface.md)\</span></span>
 <span data-ttu-id="28d73-230">Subclase de `ICorDebugValue` que se aplica a todos los valores.</span><span class="sxs-lookup"><span data-stu-id="28d73-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="28d73-231">Esta interfaz proporciona métodos Get y Set para el valor.</span><span class="sxs-lookup"><span data-stu-id="28d73-231">This interface provides Get and Set methods for the value.</span></span>  
  
 <span data-ttu-id="28d73-232">\ de la [interfaz icordebugguidtotypeenum (](icordebugguidtotypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-232">[ICorDebugGuidToTypeEnum Interface](icordebugguidtotypeenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-233">Proporciona un enumerador para un objeto que asigna GUID y sus objetos `ICorDebugType` correspondientes.</span><span class="sxs-lookup"><span data-stu-id="28d73-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 <span data-ttu-id="28d73-234">[ICorDebugHandleValue (interfaz](icordebughandlevalue-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-234">[ICorDebugHandleValue Interface](icordebughandlevalue-interface.md)</span></span>\
 <span data-ttu-id="28d73-235">Subclase de `ICorDebugReferenceValue` que representa un valor de referencia para el cual el depurador ha creado un identificador para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="28d73-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 <span data-ttu-id="28d73-236">\ de la [interfaz icordebugheapenum (](icordebugheapenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-236">[ICorDebugHeapEnum Interface](icordebugheapenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-237">Proporciona un enumerador para los objetos del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="28d73-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 <span data-ttu-id="28d73-238">\ de la [interfaz icordebugheapsegmentenum (](icordebugheapsegmentenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-238">[ICorDebugHeapSegmentEnum Interface](icordebugheapsegmentenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-239">Proporciona un enumerador para las regiones de memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="28d73-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 <span data-ttu-id="28d73-240">[ICorDebugHeapValue (interfaz](icordebugheapvalue-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-240">[ICorDebugHeapValue Interface](icordebugheapvalue-interface.md)</span></span>\
 <span data-ttu-id="28d73-241">Subclase de `ICorDebugValue` que representa un objeto que ha sido recopilado por el recolector de elementos no utilizados de CLR.</span><span class="sxs-lookup"><span data-stu-id="28d73-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 <span data-ttu-id="28d73-242">\ de la [interfaz icordebugheapvalue2 (](icordebugheapvalue2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-242">[ICorDebugHeapValue2 Interface](icordebugheapvalue2-interface1.md)\</span></span>
 <span data-ttu-id="28d73-243">Extensión de `ICorDebugHeapValue` que proporciona compatibilidad con los identificadores del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="28d73-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 <span data-ttu-id="28d73-244">\ de la [interfaz ICorDebugHeapValue3](icordebugheapvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-244">[ICorDebugHeapValue3 Interface](icordebugheapvalue3-interface.md)\</span></span>
 <span data-ttu-id="28d73-245">Expone las propiedades de bloqueo de monitor de objetos.</span><span class="sxs-lookup"><span data-stu-id="28d73-245">Exposes the monitor lock properties of objects.</span></span>  
  
 <span data-ttu-id="28d73-246">\ de la [interfaz ICorDebugILCode](icordebugilcode-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-246">[ICorDebugILCode Interface](icordebugilcode-interface.md)\</span></span>
 <span data-ttu-id="28d73-247">Representa un segmento de código de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="28d73-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 <span data-ttu-id="28d73-248">\ de la [interfaz ICorDebugILCode2](icordebugilcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-248">[ICorDebugILCode2 Interface](icordebugilcode2-interface.md)\</span></span>
 <span data-ttu-id="28d73-249">Extiende lógicamente la interfaz [ICorDebugILCode](icordebugilcode-interface.md) para proporcionar métodos que devuelven el token de la firma de variable local de una función y que asignan los desplazamientos del lenguaje intermedio INSTRUMENTADO (IL) del generador de perfiles a los desplazamientos de Il del método original.</span><span class="sxs-lookup"><span data-stu-id="28d73-249">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 <span data-ttu-id="28d73-250">[ICorDebugILFrame (interfaz](icordebugilframe-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-250">[ICorDebugILFrame Interface](icordebugilframe-interface.md)</span></span>\
 <span data-ttu-id="28d73-251">Representa un marco de pila de código de MSIL.</span><span class="sxs-lookup"><span data-stu-id="28d73-251">Represents a stack frame of MSIL code.</span></span>  
  
 <span data-ttu-id="28d73-252">\ de la [interfaz ICorDebugILFrame2](icordebugilframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-252">[ICorDebugILFrame2 Interface](icordebugilframe2-interface.md)\</span></span>
 <span data-ttu-id="28d73-253">Extensión lógica de `ICorDebugILFrame`.</span><span class="sxs-lookup"><span data-stu-id="28d73-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 <span data-ttu-id="28d73-254">\ de la [interfaz ICorDebugILFrame3](icordebugilframe3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-254">[ICorDebugILFrame3 Interface](icordebugilframe3-interface.md)\</span></span>
 <span data-ttu-id="28d73-255">Proporciona un método que encapsula el valor devuelto de una función.</span><span class="sxs-lookup"><span data-stu-id="28d73-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 <span data-ttu-id="28d73-256">\ de la [interfaz ICorDebugILFrame4](icordebugilframe4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-256">[ICorDebugILFrame4 Interface](icordebugilframe4-interface.md)\</span></span>
 <span data-ttu-id="28d73-257">Proporciona métodos que permiten acceder a las variables locales y al código en un marco de pila de código de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="28d73-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="28d73-258">Un parámetro especifica si el depurador tiene acceso a las variables y al código agregados en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="28d73-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 <span data-ttu-id="28d73-259">\ de la [interfaz ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-259">[ICorDebugInstanceFieldSymbol Interface](icordebuginstancefieldsymbol-interface.md)\</span></span>
 <span data-ttu-id="28d73-260">Representa la información de símbolos de depuración para un campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="28d73-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="28d73-261">**Solo está disponible en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="28d73-261">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="28d73-262">\ de la [interfaz ICorDebugInternalFrame (](icordebuginternalframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-262">[ICorDebugInternalFrame Interface](icordebuginternalframe-interface.md)\</span></span>
 <span data-ttu-id="28d73-263">Identifica los tipos de marco del depurador.</span><span class="sxs-lookup"><span data-stu-id="28d73-263">Identifies frame types for the debugger.</span></span>  
  
 <span data-ttu-id="28d73-264">\ de la [interfaz ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-264">[ICorDebugInternalFrame2 Interface](icordebuginternalframe2-interface.md)\</span></span>
 <span data-ttu-id="28d73-265">Proporciona información sobre los marcos internos, incluida la dirección de pila y la posición en relación con los objetos [ICorDebugFrame](icordebugframe-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="28d73-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](icordebugframe-interface.md) objects.</span></span>  
  
 <span data-ttu-id="28d73-266">\ de la [interfaz ICorDebugLoadedModule](icordebugloadedmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-266">[ICorDebugLoadedModule Interface](icordebugloadedmodule-interface.md)\</span></span>
 <span data-ttu-id="28d73-267">Proporciona información acerca de un módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="28d73-267">Provides information about a loaded module.</span></span> <span data-ttu-id="28d73-268">**Solo está disponible en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="28d73-268">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="28d73-269">[ICorDebugManagedCallback (interfaz](icordebugmanagedcallback-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-269">[ICorDebugManagedCallback Interface](icordebugmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="28d73-270">Proporciona métodos que permiten procesar las devoluciones de llamada del depurador.</span><span class="sxs-lookup"><span data-stu-id="28d73-270">Provides methods to process debugger callbacks.</span></span>  
  
 <span data-ttu-id="28d73-271">\ de la [interfaz ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-271">[ICorDebugManagedCallback2 Interface](icordebugmanagedcallback2-interface.md)\</span></span>
 <span data-ttu-id="28d73-272">Proporciona métodos para admitir el control de excepciones del depurador y asistentes para depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="28d73-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="28d73-273">`ICorDebugManagedCallback2` es una extensión lógica de `ICorDebugManagedCallback`.</span><span class="sxs-lookup"><span data-stu-id="28d73-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 <span data-ttu-id="28d73-274">\ de la [interfaz ICorDebugManagedCallback3 (](icordebugmanagedcallback3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-274">[ICorDebugManagedCallback3 Interface](icordebugmanagedcallback3-interface.md)\</span></span>
 <span data-ttu-id="28d73-275">Proporciona un método de devolución de llamada que indica que se ha producido una notificación del depurador personalizada habilitada.</span><span class="sxs-lookup"><span data-stu-id="28d73-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 <span data-ttu-id="28d73-276">[ICorDebugMDA (interfaz](icordebugmda-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-276">[ICorDebugMDA Interface](icordebugmda-interface.md)</span></span>\
 <span data-ttu-id="28d73-277">Representa un mensaje del asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="28d73-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 <span data-ttu-id="28d73-278">\ de la [interfaz ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-278">[ICorDebugMemoryBuffer Interface](icordebugmemorybuffer-interface.md)\</span></span>
 <span data-ttu-id="28d73-279">Representa un búfer en memoria.</span><span class="sxs-lookup"><span data-stu-id="28d73-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="28d73-280">**Solo está disponible en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="28d73-280">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="28d73-281">\ de la [interfaz ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-281">[ICorDebugMergedAssemblyRecord Interface](icordebugmergedassemblyrecord-interface.md)\</span></span>
 <span data-ttu-id="28d73-282">Proporciona información acerca de un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="28d73-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="28d73-283">**Solo está disponible en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="28d73-283">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="28d73-284">\ de la [interfaz ICorDebugMetaDataLocator (](icordebugmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-284">[ICorDebugMetaDataLocator Interface](icordebugmetadatalocator-interface.md)\</span></span>
 <span data-ttu-id="28d73-285">Proporciona información de metadatos al depurador.</span><span class="sxs-lookup"><span data-stu-id="28d73-285">Provides metadata information to the debugger.</span></span>  
  
 <span data-ttu-id="28d73-286">[ICorDebugModule (interfaz](icordebugmodule-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-286">[ICorDebugModule Interface](icordebugmodule-interface.md)</span></span>\
 <span data-ttu-id="28d73-287">Representa un módulo de CLR, que es un archivo ejecutable o una biblioteca de vínculos dinámicos (DLL).</span><span class="sxs-lookup"><span data-stu-id="28d73-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 <span data-ttu-id="28d73-288">\ de la [interfaz ICorDebugModule2](icordebugmodule2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-288">[ICorDebugModule2 Interface](icordebugmodule2-interface.md)\</span></span>
 <span data-ttu-id="28d73-289">Actúa como una extensión lógica de `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="28d73-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 <span data-ttu-id="28d73-290">\ de la [interfaz ICorDebugModule3](icordebugmodule3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-290">[ICorDebugModule3 Interface](icordebugmodule3-interface.md)\</span></span>
 <span data-ttu-id="28d73-291">Crea un lector de símbolos para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="28d73-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 <span data-ttu-id="28d73-292">\ de la [interfaz ICorDebugModuleBreakpoint (](icordebugmodulebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-292">[ICorDebugModuleBreakpoint Interface](icordebugmodulebreakpoint-interface.md)\</span></span>
 <span data-ttu-id="28d73-293">Extiende `ICorDebugBreakpoint` para proporcionar acceso a módulos específicos.</span><span class="sxs-lookup"><span data-stu-id="28d73-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 <span data-ttu-id="28d73-294">\ de la [interfaz ICorDebugModuleDebugEvent](icordebugmoduledebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-294">[ICorDebugModuleDebugEvent Interface](icordebugmoduledebugevent-interface.md)\</span></span>
 <span data-ttu-id="28d73-295">Extiende la interfaz [ICorDebugDebugEvent](icordebugdebugevent-interface.md) para admitir eventos de nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="28d73-295">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="28d73-296">**Solo está disponible en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="28d73-296">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="28d73-297">\ de la [interfaz ICorDebugModuleEnum (](icordebugmoduleenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-297">[ICorDebugModuleEnum Interface](icordebugmoduleenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-298">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="28d73-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 <span data-ttu-id="28d73-299">\ de la [interfaz ICorDebugMutableDataTarget](icordebugmutabledatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-299">[ICorDebugMutableDataTarget Interface](icordebugmutabledatatarget-interface.md)\</span></span>
 <span data-ttu-id="28d73-300">Extiende la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md) para admitir destinos de datos mutables.</span><span class="sxs-lookup"><span data-stu-id="28d73-300">Extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 <span data-ttu-id="28d73-301">[ICorDebugNativeFrame (interfaz](icordebugnativeframe-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-301">[ICorDebugNativeFrame Interface](icordebugnativeframe-interface.md)</span></span>\
 <span data-ttu-id="28d73-302">Implementación especializada de `ICorDebugFrame` que se utiliza para los marcos nativos.</span><span class="sxs-lookup"><span data-stu-id="28d73-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 <span data-ttu-id="28d73-303">\ de la [interfaz ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-303">[ICorDebugNativeFrame2 Interface](icordebugnativeframe2-interface.md)\</span></span>
 <span data-ttu-id="28d73-304">Proporciona métodos que comprueban las relaciones entre marcos primarios y secundarios.</span><span class="sxs-lookup"><span data-stu-id="28d73-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 <span data-ttu-id="28d73-305">\ de la [interfaz ICorDebugObjectEnum (](icordebugobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-305">[ICorDebugObjectEnum Interface](icordebugobjectenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-306">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de objetos según sus direcciones virtuales relativas (RVA).</span><span class="sxs-lookup"><span data-stu-id="28d73-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 <span data-ttu-id="28d73-307">[ICorDebugObjectValue (interfaz](icordebugobjectvalue-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-307">[ICorDebugObjectValue Interface](icordebugobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="28d73-308">Subclase de `ICorDebugValue` que representa un valor que contiene un objeto.</span><span class="sxs-lookup"><span data-stu-id="28d73-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 <span data-ttu-id="28d73-309">\ de la [interfaz icordebugobjectvalue2 (](icordebugobjectvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-309">[ICorDebugObjectValue2 Interface](icordebugobjectvalue2-interface.md)\</span></span>
 <span data-ttu-id="28d73-310">Extiende `ICorDebugObjectValue` para ofrecer compatibilidad con la herencia y los reemplazos.</span><span class="sxs-lookup"><span data-stu-id="28d73-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 <span data-ttu-id="28d73-311">[ICorDebugProcess (interfaz](icordebugprocess-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-311">[ICorDebugProcess Interface](icordebugprocess-interface.md)</span></span>\
 <span data-ttu-id="28d73-312">Representa un proceso que ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="28d73-312">Represents a process that is executing managed code.</span></span>  
  
 <span data-ttu-id="28d73-313">\ de la [interfaz ICorDebugProcess2](icordebugprocess2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-313">[ICorDebugProcess2 Interface](icordebugprocess2-interface1.md)\</span></span>
 <span data-ttu-id="28d73-314">Extensión lógica de `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="28d73-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 <span data-ttu-id="28d73-315">\ de la [interfaz ICorDebugProcess3 (](icordebugprocess3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-315">[ICorDebugProcess3 Interface](icordebugprocess3-interface.md)\</span></span>
 <span data-ttu-id="28d73-316">Controla las notificaciones del depurador personalizadas.</span><span class="sxs-lookup"><span data-stu-id="28d73-316">Controls custom debugger notifications.</span></span>

 <span data-ttu-id="28d73-317">\ de la [interfaz ICorDebugProcess4](icordebugprocess4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-317">[ICorDebugProcess4 Interface](icordebugprocess4-interface.md)\</span></span>
 <span data-ttu-id="28d73-318">Proporciona compatibilidad para el control de ejecución fuera de proceso.</span><span class="sxs-lookup"><span data-stu-id="28d73-318">Provides support for out of process execution control.</span></span>
  
 <span data-ttu-id="28d73-319">\ de la [interfaz ICorDebugProcess5](icordebugprocess5-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-319">[ICorDebugProcess5 Interface](icordebugprocess5-interface.md)\</span></span>
 <span data-ttu-id="28d73-320">Extiende la interfaz [ICorDebugProcess](icordebugprocess-interface.md) para admitir el acceso al montón administrado, para proporcionar información sobre la recolección de elementos no utilizados de objetos administrados y para determinar si un depurador carga imágenes desde la memoria caché de imágenes nativas local de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="28d73-320">Extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 <span data-ttu-id="28d73-321">\ de la [interfaz método icordebugprocess6](icordebugprocess6-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-321">[ICorDebugProcess6 Interface](icordebugprocess6-interface.md)\</span></span>
 <span data-ttu-id="28d73-322">Extiende lógicamente la interfaz [ICorDebugProcess](icordebugprocess-interface.md) para habilitar características como la descodificación de eventos de depuración administrados codificados en eventos de depuración de excepción nativa y la división de módulos virtuales.</span><span class="sxs-lookup"><span data-stu-id="28d73-322">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="28d73-323">**Solo está disponible en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="28d73-323">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="28d73-324">\ de la [interfaz icordebugprocess7 (](icordebugprocess7-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-324">[ICorDebugProcess7 Interface](icordebugprocess7-interface.md)\</span></span>
 <span data-ttu-id="28d73-325">Proporciona un método que configura el depurador para controlar las actualizaciones en memoria de los metadatos en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="28d73-325">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 <span data-ttu-id="28d73-326">\ de la [interfaz ICorDebugProcess8](icordebugprocess8-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-326">[ICorDebugProcess8 Interface](icordebugprocess8-interface.md)\</span></span>
 <span data-ttu-id="28d73-327">Extiende lógicamente la interfaz [ICorDebugProcess](icordebugprocess-interface.md) para habilitar o deshabilitar determinados tipos de devoluciones de llamada de excepción [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="28d73-327">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 <span data-ttu-id="28d73-328">\ de la [interfaz icordebugprocessenum (](icordebugprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-328">[ICorDebugProcessEnum Interface](icordebugprocessenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-329">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="28d73-329">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 <span data-ttu-id="28d73-330">[ICorDebugReferenceValue (interfaz](icordebugreferencevalue-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-330">[ICorDebugReferenceValue Interface](icordebugreferencevalue-interface.md)</span></span>\
 <span data-ttu-id="28d73-331">Subclase de `ICorDebugValue` que admite tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="28d73-331">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 <span data-ttu-id="28d73-332">[ICorDebugRegisterSet (interfaz](icordebugregisterset-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-332">[ICorDebugRegisterSet Interface](icordebugregisterset-interface.md)</span></span>\
 <span data-ttu-id="28d73-333">Representa el conjunto de registros disponibles en el equipo que está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="28d73-333">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 <span data-ttu-id="28d73-334">\ de la [interfaz ICorDebugRegisterSet2](icordebugregisterset2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-334">[ICorDebugRegisterSet2 Interface](icordebugregisterset2-interface.md)\</span></span>
 <span data-ttu-id="28d73-335">Extiende la funcionalidad de `ICorDebugRegisterSet` para plataformas hardware que tienen más de 64 registros.</span><span class="sxs-lookup"><span data-stu-id="28d73-335">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 <span data-ttu-id="28d73-336">\ de la [interfaz ICorDebugRemote](icordebugremote-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-336">[ICorDebugRemote Interface](icordebugremote-interface.md)\</span></span>
 <span data-ttu-id="28d73-337">Proporciona la capacidad de iniciar o de adjuntar un depurador administrado a un proceso remoto de destino.</span><span class="sxs-lookup"><span data-stu-id="28d73-337">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 <span data-ttu-id="28d73-338">\ de la [interfaz ICorDebugRemoteTarget](icordebugremotetarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-338">[ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md)\</span></span>
 <span data-ttu-id="28d73-339">Proporciona métodos que permiten depurar aplicaciones basadas en Silverlight en el entorno de CLR.</span><span class="sxs-lookup"><span data-stu-id="28d73-339">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="28d73-340">\ de la [interfaz icordebugruntimeunwindableframe (](icordebugruntimeunwindableframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-340">[ICorDebugRuntimeUnwindableFrame Interface](icordebugruntimeunwindableframe-interface.md)\</span></span>
 <span data-ttu-id="28d73-341">Proporciona compatibilidad para métodos no administrados que necesitan que Common Language Runtime (CLR) desenrede un marco.</span><span class="sxs-lookup"><span data-stu-id="28d73-341">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 <span data-ttu-id="28d73-342">[ICorDebugStackWalk (interfaz](icordebugstackwalk-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-342">[ICorDebugStackWalk Interface](icordebugstackwalk-interface.md)</span></span>\
 <span data-ttu-id="28d73-343">Proporciona métodos para obtener los métodos administrados, o marcos, de la pila de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="28d73-343">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 <span data-ttu-id="28d73-344">\ de la [interfaz ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-344">[ICorDebugStaticFieldSymbol Interface](icordebugstaticfieldsymbol-interface.md)\</span></span>
 <span data-ttu-id="28d73-345">Representa la información de símbolos de depuración para un campo estático.</span><span class="sxs-lookup"><span data-stu-id="28d73-345">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="28d73-346">**Solo está disponible en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="28d73-346">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="28d73-347">[ICorDebugStepper (interfaz](icordebugstepper-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-347">[ICorDebugStepper Interface](icordebugstepper-interface.md)</span></span>\
 <span data-ttu-id="28d73-348">Representa un paso en la ejecución del código realizado por un depurador, actúa como identificador entre la emisión y la finalización de un comando, y proporciona un modo de cancelar un paso.</span><span class="sxs-lookup"><span data-stu-id="28d73-348">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 <span data-ttu-id="28d73-349">\ de la [interfaz icordebugstepper2 (](icordebugstepper2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-349">[ICorDebugStepper2 Interface](icordebugstepper2-interface1.md)\</span></span>
 <span data-ttu-id="28d73-350">Proporciona compatibilidad con la depuración de "Sólo mi código" (JMC).</span><span class="sxs-lookup"><span data-stu-id="28d73-350">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 <span data-ttu-id="28d73-351">\ de la [interfaz ICorDebugStepperEnum (](icordebugstepperenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-351">[ICorDebugStepperEnum Interface](icordebugstepperenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-352">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugStepper`.</span><span class="sxs-lookup"><span data-stu-id="28d73-352">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 <span data-ttu-id="28d73-353">[ICorDebugStringValue (interfaz](icordebugstringvalue-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-353">[ICorDebugStringValue Interface](icordebugstringvalue-interface.md)</span></span>\
 <span data-ttu-id="28d73-354">Subclase de `ICorDebugHeapValue` que se aplica a los valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="28d73-354">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 <span data-ttu-id="28d73-355">\ de la [interfaz ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-355">[ICorDebugSymbolProvider Interface](icordebugsymbolprovider-interface.md)\</span></span>
 <span data-ttu-id="28d73-356">Proporciona métodos que pueden utilizarse para recuperar información de símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="28d73-356">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="28d73-357">**Solo está disponible en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="28d73-357">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="28d73-358">\ de la [interfaz icordebugsymbolprovider2 (](icordebugsymbolprovider2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-358">[ICorDebugSymbolProvider2 Interface](icordebugsymbolprovider2-interface.md)\</span></span>
 <span data-ttu-id="28d73-359">Extiende lógicamente la interfaz [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) para recuperar información de símbolos de depuración adicional.</span><span class="sxs-lookup"><span data-stu-id="28d73-359">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="28d73-360">**Solo está disponible en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="28d73-360">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="28d73-361">[ICorDebugThread (interfaz](icordebugthread-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-361">[ICorDebugThread Interface](icordebugthread-interface.md)</span></span>\
 <span data-ttu-id="28d73-362">Representa un subproceso de un proceso.</span><span class="sxs-lookup"><span data-stu-id="28d73-362">Represents a thread in a process.</span></span> <span data-ttu-id="28d73-363">El período de duración de una instancia de `ICorDebugThread` es el mismo que el del subproceso que representa.</span><span class="sxs-lookup"><span data-stu-id="28d73-363">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 <span data-ttu-id="28d73-364">\ de la [interfaz ICorDebugThread2](icordebugthread2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-364">[ICorDebugThread2 Interface](icordebugthread2-interface.md)\</span></span>
 <span data-ttu-id="28d73-365">Actúa como una extensión lógica de `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="28d73-365">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 <span data-ttu-id="28d73-366">\ de la [interfaz ICorDebugThread3](icordebugthread3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-366">[ICorDebugThread3 Interface](icordebugthread3-interface.md)\</span></span>
 <span data-ttu-id="28d73-367">Proporciona el punto de entrada a [ICorDebugStackWalk](icordebugstackwalk-interface.md) y las interfaces correspondientes.</span><span class="sxs-lookup"><span data-stu-id="28d73-367">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 <span data-ttu-id="28d73-368">\ de la [interfaz ICorDebugThread4](icordebugthread4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-368">[ICorDebugThread4 Interface](icordebugthread4-interface.md)\</span></span>
 <span data-ttu-id="28d73-369">Proporciona información de bloqueo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="28d73-369">Provides thread blocking information.</span></span>  
  
 <span data-ttu-id="28d73-370">\ de la [interfaz ICorDebugThreadEnum (](icordebugthreadenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-370">[ICorDebugThreadEnum Interface](icordebugthreadenum-interface1.md)\</span></span>
 <span data-ttu-id="28d73-371">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="28d73-371">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 <span data-ttu-id="28d73-372">[ICorDebugType (interfaz](icordebugtype-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-372">[ICorDebugType Interface](icordebugtype-interface.md)</span></span>\
 <span data-ttu-id="28d73-373">Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="28d73-373">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="28d73-374">Si el tipo es genérico, `ICorDebugType` representa el tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="28d73-374">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 <span data-ttu-id="28d73-375">\ de la [interfaz ICorDebugType2](icordebugtype2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-375">[ICorDebugType2 Interface](icordebugtype2-interface.md)\</span></span>
 <span data-ttu-id="28d73-376">Extiende la interfaz [ICorDebugType](icordebugtype-interface.md) para recuperar el identificador de tipo de un tipo base o un tipo complejo (definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="28d73-376">Extends the [ICorDebugType](icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 <span data-ttu-id="28d73-377">[ICorDebugTypeEnum (interfaz](icordebugtypeenum-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-377">[ICorDebugTypeEnum Interface](icordebugtypeenum-interface.md)</span></span>\
 <span data-ttu-id="28d73-378">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="28d73-378">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 <span data-ttu-id="28d73-379">\ de la [interfaz ICorDebugUnmanagedCallback (](icordebugunmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-379">[ICorDebugUnmanagedCallback Interface](icordebugunmanagedcallback-interface.md)\</span></span>
 <span data-ttu-id="28d73-380">Proporciona notificación de eventos nativos no relacionados directamente con CLR.</span><span class="sxs-lookup"><span data-stu-id="28d73-380">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="28d73-381">[ICorDebugValue](icordebugvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-381">[ICorDebugValue](icordebugvalue-interface.md)</span></span>\
 <span data-ttu-id="28d73-382">Representa un valor de escritura o lectura en el proceso que se va a depurar.</span><span class="sxs-lookup"><span data-stu-id="28d73-382">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="28d73-383">\ [ICorDebugValue2](icordebugvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-383">[ICorDebugValue2](icordebugvalue2-interface.md)\</span></span>
 <span data-ttu-id="28d73-384">Extiende `ICorDebugValue` para proporcionar compatibilidad con `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="28d73-384">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="28d73-385">\ de la [interfaz icordebugvalue3 (](icordebugvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-385">[ICorDebugValue3 Interface](icordebugvalue3-interface.md)\</span></span>
 <span data-ttu-id="28d73-386">Extiende las interfaces "ICorDebugValue" y "ICorDebugValue2" para proporcionar compatibilidad con matrices mayores de 2 GB.</span><span class="sxs-lookup"><span data-stu-id="28d73-386">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="28d73-387">\ [icordebugvaluebreakpoint (](icordebugvaluebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\</span></span>
 <span data-ttu-id="28d73-388">Extiende `ICorDebugBreakpoint` para proporcionar acceso a valores concretos.</span><span class="sxs-lookup"><span data-stu-id="28d73-388">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="28d73-389">\ [ICorDebugValueEnum](icordebugvalueenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-390">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="28d73-390">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 <span data-ttu-id="28d73-391">\ de la [interfaz ICorDebugVariableHome](icordebugvariablehome-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-391">[ICorDebugVariableHome Interface](icordebugvariablehome-interface.md)\</span></span>
 <span data-ttu-id="28d73-392">Representa una variable local o un argumento de una función.</span><span class="sxs-lookup"><span data-stu-id="28d73-392">Represents a local variable or argument of a function.</span></span>  
  
 <span data-ttu-id="28d73-393">\ de la [interfaz ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-393">[ICorDebugVariableHomeEnum Interface](icordebugvariablehomeenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-394">Proporciona un enumerador para las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="28d73-394">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="28d73-395">\ de la [interfaz ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-395">[ICorDebugVariableSymbol Interface](icordebugvariablesymbol-interface.md)\</span></span>
 <span data-ttu-id="28d73-396">Recupera la información de símbolos de depuración para una variable.</span><span class="sxs-lookup"><span data-stu-id="28d73-396">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="28d73-397">**Solo está disponible en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="28d73-397">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="28d73-398">\ de la [interfaz ICorDebugVirtualUnwinder](icordebugvirtualunwinder-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-398">[ICorDebugVirtualUnwinder Interface](icordebugvirtualunwinder-interface.md)\</span></span>
 <span data-ttu-id="28d73-399">Proporciona métodos que ayudan al desenredo de la pila.</span><span class="sxs-lookup"><span data-stu-id="28d73-399">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="28d73-400">**Solo está disponible en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="28d73-400">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="28d73-401">[ICorPublish (interfaz](icorpublish-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-401">[ICorPublish Interface](icorpublish-interface.md)</span></span>\
 <span data-ttu-id="28d73-402">Actúa como interfaz general para los procesos de publicación.</span><span class="sxs-lookup"><span data-stu-id="28d73-402">Serves as the general interface for the publishing processes.</span></span>  
  
 <span data-ttu-id="28d73-403">[ICorPublishAppDomain (interfaz](icorpublishappdomain-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-403">[ICorPublishAppDomain Interface](icorpublishappdomain-interface.md)</span></span>\
 <span data-ttu-id="28d73-404">Representa y proporciona información sobre un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="28d73-404">Represents and provides information about an application domain.</span></span>  
  
 <span data-ttu-id="28d73-405">\ de la [interfaz ICorPublishAppDomainEnum (](icorpublishappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-405">[ICorPublishAppDomainEnum Interface](icorpublishappdomainenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-406">Proporciona métodos que atraviesan una colección de objetos `ICorPublishAppDomain` que actualmente existen dentro de un proceso.</span><span class="sxs-lookup"><span data-stu-id="28d73-406">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 <span data-ttu-id="28d73-407">[ICorPublishEnum (interfaz](icorpublishenum-interface.md) )</span><span class="sxs-lookup"><span data-stu-id="28d73-407">[ICorPublishEnum Interface](icorpublishenum-interface.md)</span></span>\
 <span data-ttu-id="28d73-408">Actúa como la base abstracta para los enumeradores de publicación.</span><span class="sxs-lookup"><span data-stu-id="28d73-408">Serves as the abstract base for publishing enumerators.</span></span>  
  
 <span data-ttu-id="28d73-409">[Interfaz ICorPublishProcess](icorpublishprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-409">[ICorPublishProcess Interface](icorpublishprocess-interface.md)</span></span>\
 <span data-ttu-id="28d73-410">Proporciona métodos que tienen acceso a información de un proceso.</span><span class="sxs-lookup"><span data-stu-id="28d73-410">Provides methods that access information about a process.</span></span>  
  
 <span data-ttu-id="28d73-411">\ de la [interfaz ICorPublishProcessEnum (](icorpublishprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-411">[ICorPublishProcessEnum Interface](icorpublishprocessenum-interface.md)\</span></span>
 <span data-ttu-id="28d73-412">Proporciona métodos que atraviesan una colección de objetos `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="28d73-412">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  

 <span data-ttu-id="28d73-413">\ de la [interfaz ISOSDacInterface](isosdacinterface-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-413">[ISOSDacInterface Interface](isosdacinterface-interface.md)\</span></span>
 <span data-ttu-id="28d73-414">Proporciona métodos auxiliares para tener acceso a los datos de `SOS`.</span><span class="sxs-lookup"><span data-stu-id="28d73-414">Provides helper methods to access data from `SOS`.</span></span>

 <span data-ttu-id="28d73-415">\ de la [interfaz IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-415">[IXCLRDataMethodDefinition Interface](ixclrdatamethoddefinition-interface.md)\</span></span>
 <span data-ttu-id="28d73-416">Proporciona métodos para consultar información sobre una definición de método.</span><span class="sxs-lookup"><span data-stu-id="28d73-416">Provides methods for querying information about a method definition.</span></span>
 
 <span data-ttu-id="28d73-417">\ de la [interfaz IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-417">[IXCLRDataMethodInstance Interface](ixclrdatamethodinstance-interface.md)\</span></span>
 <span data-ttu-id="28d73-418">Proporciona métodos para consultar información sobre una instancia de método.</span><span class="sxs-lookup"><span data-stu-id="28d73-418">Provides methods for querying information about a method instance.</span></span>
 
 <span data-ttu-id="28d73-419">\ de la [interfaz IXCLRDataModule](ixclrdatamodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-419">[IXCLRDataModule Interface](ixclrdatamodule-interface.md)\</span></span>
 <span data-ttu-id="28d73-420">Proporciona métodos para consultar información sobre un módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="28d73-420">Provides methods for querying information about a loaded module.</span></span>
 
 <span data-ttu-id="28d73-421">\ de la [interfaz IXCLRDataProcess](ixclrdataprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-421">[IXCLRDataProcess Interface](ixclrdataprocess-interface.md)\</span></span>
 <span data-ttu-id="28d73-422">Proporciona métodos para consultar información sobre un proceso.</span><span class="sxs-lookup"><span data-stu-id="28d73-422">Provides methods for querying information about a process.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="28d73-423">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="28d73-423">Related Sections</span></span>  
 <span data-ttu-id="28d73-424">[Coclases de Depuración](debugging-coclasses.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-424">[Debugging Coclasses](debugging-coclasses.md)</span></span>\
 <span data-ttu-id="28d73-425">[Funciones estáticas globales de Depuración](debugging-global-static-functions.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-425">[Debugging Global Static Functions](debugging-global-static-functions.md)</span></span>\
 <span data-ttu-id="28d73-426">[Depuración de enumeraciones](debugging-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-426">[Debugging Enumerations](debugging-enumerations.md)</span></span>\
 <span data-ttu-id="28d73-427">\ de [estructuras de depuración](debugging-structures.md)</span><span class="sxs-lookup"><span data-stu-id="28d73-427">[Debugging Structures](debugging-structures.md)\</span></span>
