---
description: 'Más información acerca de: depurar interfaces'
title: Interfaces para depuración
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
ms.openlocfilehash: 6e6cc07e200b9ecf6bf4039f4fd5fd69e27b6fda
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717971"
---
# <a name="debugging-interfaces"></a><span data-ttu-id="652c1-103">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="652c1-103">Debugging Interfaces</span></span>

<span data-ttu-id="652c1-104">En esta sección se describen las interfaces no administradas que controlan la depuración de un programa que se ejecuta en Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="652c1-104">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="652c1-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="652c1-105">In This Section</span></span>  

 <span data-ttu-id="652c1-106">[ICLRDataEnumMemoryRegions (interfaz)](iclrdataenummemoryregions-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-106">[ICLRDataEnumMemoryRegions Interface](iclrdataenummemoryregions-interface.md)</span></span>\
 <span data-ttu-id="652c1-107">Proporciona un método para enumerar las regiones de memoria especificadas por los llamadores.</span><span class="sxs-lookup"><span data-stu-id="652c1-107">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 <span data-ttu-id="652c1-108">[Interfaz ICLRDataEnumMemoryRegionsCallback (](iclrdataenummemoryregionscallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-108">[ICLRDataEnumMemoryRegionsCallback Interface](iclrdataenummemoryregionscallback-interface.md)</span></span>\
 <span data-ttu-id="652c1-109">Proporciona un método de devolución de llamada para que `EnumMemoryRegions` notifique al depurador el resultado de un intento de enumerar un área de memoria concreta.</span><span class="sxs-lookup"><span data-stu-id="652c1-109">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 <span data-ttu-id="652c1-110">[ICLRDataTarget (interfaz)](iclrdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-110">[ICLRDataTarget Interface](iclrdatatarget-interface.md)</span></span>\
 <span data-ttu-id="652c1-111">Proporciona métodos para la interacción con un proceso de CLR de destino.</span><span class="sxs-lookup"><span data-stu-id="652c1-111">Provides methods for interaction with a target CLR process.</span></span>  
  
 <span data-ttu-id="652c1-112">[Interfaz ICLRDataTarget2](iclrdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-112">[ICLRDataTarget2 Interface](iclrdatatarget2-interface.md)</span></span>\
 <span data-ttu-id="652c1-113">Subclase de `ICLRDataTarget` que se utiliza la capa de servicios de acceso a datos para manipular las áreas de la memoria virtual en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="652c1-113">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 <span data-ttu-id="652c1-114">[Interfaz ICLRDataTarget3](iclrdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-114">[ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)</span></span>\
 <span data-ttu-id="652c1-115">Subclase de [ICLRDataTarget2](iclrdatatarget2-interface.md) que proporciona acceso a la información de la excepción.</span><span class="sxs-lookup"><span data-stu-id="652c1-115">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 <span data-ttu-id="652c1-116">[Interfaz ICLRDebugging](iclrdebugging-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-116">[ICLRDebugging Interface](iclrdebugging-interface.md)</span></span>\
 <span data-ttu-id="652c1-117">Proporciona métodos que controlan la carga y descarga de módulos para depuración.</span><span class="sxs-lookup"><span data-stu-id="652c1-117">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 <span data-ttu-id="652c1-118">[Interfaz ICLRDebuggingLibraryProvider (](iclrdebugginglibraryprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-118">[ICLRDebuggingLibraryProvider Interface](iclrdebugginglibraryprovider-interface.md)</span></span>\
 <span data-ttu-id="652c1-119">Incluye el método del [método ProvideLibrary (](iclrdebugginglibraryprovider-providelibrary-method.md) , que obtiene una interfaz de devolución de llamada del proveedor de bibliotecas que permite buscar y cargar a petición bibliotecas de depuración específicas de la versión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="652c1-119">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 <span data-ttu-id="652c1-120">[Interfaz Iclrmetadatalocator (](iclrmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-120">[ICLRMetadataLocator Interface](iclrmetadatalocator-interface.md)</span></span>\
 <span data-ttu-id="652c1-121">Interfaz utilizada por la capa de servicios de acceso a datos para buscar los metadatos de los ensamblados en un proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="652c1-121">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 <span data-ttu-id="652c1-122">[ICorDebug (interfaz)](icordebug-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-122">[ICorDebug Interface](icordebug-interface.md)</span></span>\
 <span data-ttu-id="652c1-123">Proporciona métodos que permiten a los desarrolladores depurar las aplicaciones en el entorno de CLR.</span><span class="sxs-lookup"><span data-stu-id="652c1-123">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="652c1-124">[ICorDebugAppDomain (interfaz)](icordebugappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-124">[ICorDebugAppDomain Interface](icordebugappdomain-interface.md)</span></span>\
 <span data-ttu-id="652c1-125">Proporciona métodos para depurar dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="652c1-125">Provides methods for debugging application domains.</span></span>  
  
 <span data-ttu-id="652c1-126">[Interfaz ICorDebugAppDomain2](icordebugappdomain2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-126">[ICorDebugAppDomain2 Interface](icordebugappdomain2-interface.md)</span></span>\
 <span data-ttu-id="652c1-127">Proporciona métodos para trabajar con matrices, punteros, punteros a función y tipos ByRef.</span><span class="sxs-lookup"><span data-stu-id="652c1-127">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="652c1-128">Esta interfaz es una extensión de la interfaz `ICorDebugAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="652c1-128">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 <span data-ttu-id="652c1-129">[Interfaz ICorDebugAppDomain3](icordebugappdomain3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-129">[ICorDebugAppDomain3 Interface](icordebugappdomain3-interface.md)</span></span>\
 <span data-ttu-id="652c1-130">Proporciona métodos para trabajar con los tipos de Windows Runtime en un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="652c1-130">Provides methods to work with the Windows Runtime types in an application domain.</span></span> <span data-ttu-id="652c1-131">Esta interfaz es una extensión de las interfaces `ICorDebugAppDomain` e `ICorDebugAppDomain2`.</span><span class="sxs-lookup"><span data-stu-id="652c1-131">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 <span data-ttu-id="652c1-132">[Interfaz ICorDebugAppDomain4](icordebugappdomain4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-132">[ICorDebugAppDomain4 Interface](icordebugappdomain4-interface.md)</span></span>\
 <span data-ttu-id="652c1-133">Extiende lógicamente la interfaz [ICorDebugAppDomain](icordebugappdomain-interface.md) para obtener un objeto administrado desde un contenedor com invocable.</span><span class="sxs-lookup"><span data-stu-id="652c1-133">Logically extends the [ICorDebugAppDomain](icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 <span data-ttu-id="652c1-134">[Interfaz ICorDebugAppDomainEnum (](icordebugappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-134">[ICorDebugAppDomainEnum Interface](icordebugappdomainenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-135">Proporciona un método que devuelve un número especificado de valores de `ICorDebugAppDomain` que comienzan en la siguiente posición de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="652c1-135">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 <span data-ttu-id="652c1-136">[ICorDebugArrayValue (interfaz)](icordebugarrayvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-136">[ICorDebugArrayValue Interface](icordebugarrayvalue-interface.md)</span></span>\
 <span data-ttu-id="652c1-137">Subclase de `ICorDebugHeapValue` que representa una matriz unidimensional o multidimensional.</span><span class="sxs-lookup"><span data-stu-id="652c1-137">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 <span data-ttu-id="652c1-138">[ICorDebugAssembly (interfaz)](icordebugassembly-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-138">[ICorDebugAssembly Interface](icordebugassembly-interface.md)</span></span>\
 <span data-ttu-id="652c1-139">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="652c1-139">Represents an assembly.</span></span>  
  
 <span data-ttu-id="652c1-140">[Interfaz Icordebugassembly2 (](icordebugassembly2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-140">[ICorDebugAssembly2 Interface](icordebugassembly2-interface.md)</span></span>\
 <span data-ttu-id="652c1-141">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="652c1-141">Represents an assembly.</span></span> <span data-ttu-id="652c1-142">Esta interfaz es una extensión de la interfaz `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="652c1-142">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 <span data-ttu-id="652c1-143">[Interfaz método icordebugassembly3](icordebugassembly3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-143">[ICorDebugAssembly3 Interface](icordebugassembly3-interface.md)</span></span>\
 <span data-ttu-id="652c1-144">Extiende lógicamente la interfaz [ICorDebugAssembly](icordebugassembly-interface.md) para proporcionar compatibilidad con los ensamblados de contenedor y sus ensamblados incluidos.</span><span class="sxs-lookup"><span data-stu-id="652c1-144">Logically extends the [ICorDebugAssembly](icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="652c1-145">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="652c1-145">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="652c1-146">[Interfaz ICorDebugAssemblyEnum](icordebugassemblyenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-146">[ICorDebugAssemblyEnum Interface](icordebugassemblyenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-147">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="652c1-147">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 <span data-ttu-id="652c1-148">[Interfaz ICorDebugBlockingObjectEnum](icordebugblockingobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-148">[ICorDebugBlockingObjectEnum Interface](icordebugblockingobjectenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-149">Proporciona un enumerador para una lista de estructuras [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="652c1-149">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
 <span data-ttu-id="652c1-150">[Interfaz ICorDebugBoxValue (](icordebugboxvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-150">[ICorDebugBoxValue Interface](icordebugboxvalue-interface.md)</span></span>\
 <span data-ttu-id="652c1-151">Subclase de `ICorDebugHeapValue` que representa un objeto de clase de valor al que se ha aplicado la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="652c1-151">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 <span data-ttu-id="652c1-152">[ICorDebugBreakpoint (interfaz)](icordebugbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-152">[ICorDebugBreakpoint Interface](icordebugbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="652c1-153">Representa un punto de interrupción en una función o un punto de inspección en un valor.</span><span class="sxs-lookup"><span data-stu-id="652c1-153">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 <span data-ttu-id="652c1-154">[Interfaz ICorDebugBreakpointEnum (](icordebugbreakpointenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-154">[ICorDebugBreakpointEnum Interface](icordebugbreakpointenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-155">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="652c1-155">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 <span data-ttu-id="652c1-156">[ICorDebugChain (interfaz)](icordebugchain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-156">[ICorDebugChain Interface](icordebugchain-interface.md)</span></span>\
 <span data-ttu-id="652c1-157">Representa un segmento de una pila de llamadas física o lógica.</span><span class="sxs-lookup"><span data-stu-id="652c1-157">Represents a segment of a physical or logical call stack.</span></span>  
  
 <span data-ttu-id="652c1-158">[Interfaz ICorDebugChainEnum (](icordebugchainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-158">[ICorDebugChainEnum Interface](icordebugchainenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-159">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugChain`.</span><span class="sxs-lookup"><span data-stu-id="652c1-159">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 <span data-ttu-id="652c1-160">[ICorDebugClass (interfaz)](icordebugclass-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-160">[ICorDebugClass Interface](icordebugclass-interface.md)</span></span>\
 <span data-ttu-id="652c1-161">Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="652c1-161">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="652c1-162">Si el tipo es genérico, `ICorDebugClass` representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="652c1-162">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 <span data-ttu-id="652c1-163">[Interfaz ICorDebugClass2](icordebugclass2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-163">[ICorDebugClass2 Interface](icordebugclass2-interface.md)</span></span>\
 <span data-ttu-id="652c1-164">Representa una clase genérica o una clase con un parámetro de método de tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="652c1-164">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="652c1-165">Esta interfaz extiende `ICorDebugClass`.</span><span class="sxs-lookup"><span data-stu-id="652c1-165">This interface extends `ICorDebugClass`.</span></span>  
  
 <span data-ttu-id="652c1-166">[ICorDebugCode (interfaz)](icordebugcode-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-166">[ICorDebugCode Interface](icordebugcode-interface1.md)</span></span>\
 <span data-ttu-id="652c1-167">Representa un segmento de código de lenguaje intermedio de Microsoft (MSIL) o código nativo.</span><span class="sxs-lookup"><span data-stu-id="652c1-167">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 <span data-ttu-id="652c1-168">[Interfaz ICorDebugCode2](icordebugcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-168">[ICorDebugCode2 Interface](icordebugcode2-interface.md)</span></span>\
 <span data-ttu-id="652c1-169">Proporciona métodos que amplían las funciones de `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="652c1-169">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 <span data-ttu-id="652c1-170">[Interfaz ICorDebugCode3](icordebugcode3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-170">[ICorDebugCode3 Interface](icordebugcode3-interface.md)</span></span>\
 <span data-ttu-id="652c1-171">Proporciona un método que extiende [ICorDebugCode](icordebugcode-interface1.md) y [ICorDebugCode2](icordebugcode2-interface.md) para proporcionar información sobre un valor devuelto administrado.</span><span class="sxs-lookup"><span data-stu-id="652c1-171">Provides a method that extends [ICorDebugCode](icordebugcode-interface1.md) and [ICorDebugCode2](icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 <span data-ttu-id="652c1-172">[Interfaz interfaces icordebugcode4](icordebugcode4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-172">[ICorDebugCode4 Interface](icordebugcode4-interface.md)</span></span>\
 <span data-ttu-id="652c1-173">Proporciona un método que permite a un depurador enumerar las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="652c1-173">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="652c1-174">[Interfaz ICorDebugCodeEnum (](icordebugcodeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-174">[ICorDebugCodeEnum Interface](icordebugcodeenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-175">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="652c1-175">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 <span data-ttu-id="652c1-176">[Interfaz ICorDebugComObjectValue](icordebugcomobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-176">[ICorDebugComObjectValue Interface](icordebugcomobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="652c1-177">Proporciona métodos para recuperar objetos de la interfaz en caché.</span><span class="sxs-lookup"><span data-stu-id="652c1-177">Provides methods to retrieve cached interface objects.</span></span>  
  
 <span data-ttu-id="652c1-178">[Interfaz Icordebugcontext (](icordebugcontext-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-178">[ICorDebugContext Interface](icordebugcontext-interface.md)</span></span>\
 <span data-ttu-id="652c1-179">Representa un objeto de contexto.</span><span class="sxs-lookup"><span data-stu-id="652c1-179">Represents a context object.</span></span> <span data-ttu-id="652c1-180">Esta interfaz no se ha implementado todavía.</span><span class="sxs-lookup"><span data-stu-id="652c1-180">This interface has not been implemented yet.</span></span>  
  
 <span data-ttu-id="652c1-181">[ICorDebugController (interfaz)](icordebugcontroller-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-181">[ICorDebugController Interface](icordebugcontroller-interface.md)</span></span>\
 <span data-ttu-id="652c1-182">Representa un ámbito, <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, en el que se puede controlar el contexto de ejecución de código.</span><span class="sxs-lookup"><span data-stu-id="652c1-182">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 <span data-ttu-id="652c1-183">[Interfaz ICorDebugDataTarget](icordebugdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-183">[ICorDebugDataTarget Interface](icordebugdatatarget-interface.md)</span></span>\
 <span data-ttu-id="652c1-184">Proporciona una interfaz de devolución de llamada que brinda acceso a un proceso de destino determinado.</span><span class="sxs-lookup"><span data-stu-id="652c1-184">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 <span data-ttu-id="652c1-185">[Interfaz método icordebugdatatarget2](icordebugdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-185">[ICorDebugDataTarget2 Interface](icordebugdatatarget2-interface.md)</span></span>\
 <span data-ttu-id="652c1-186">Extiende lógicamente la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="652c1-186">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="652c1-187">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="652c1-187">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="652c1-188">[Interfaz ICorDebugDataTarget3](icordebugdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-188">[ICorDebugDataTarget3 Interface](icordebugdatatarget3-interface.md)</span></span>\
 <span data-ttu-id="652c1-189">Extiende lógicamente la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md) para proporcionar información sobre los módulos cargados.</span><span class="sxs-lookup"><span data-stu-id="652c1-189">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="652c1-190">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="652c1-190">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="652c1-191">[Interfaz ICorDebugDebugEvent](icordebugdebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-191">[ICorDebugDebugEvent Interface](icordebugdebugevent-interface.md)</span></span>\
 <span data-ttu-id="652c1-192">Define la interfaz base de la que derivan todos los eventos de depuración `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="652c1-192">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="652c1-193">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="652c1-193">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="652c1-194">[Interfaz ICorDebugEditAndContinueErrorInfo](icordebugeditandcontinueerrorinfo-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-194">[ICorDebugEditAndContinueErrorInfo Interface](icordebugeditandcontinueerrorinfo-interface.md)</span></span>\
 <span data-ttu-id="652c1-195">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="652c1-195">Obsolete.</span></span> <span data-ttu-id="652c1-196">No utilice esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="652c1-196">Do not use this interface.</span></span>  
  
 <span data-ttu-id="652c1-197">[Interfaz ICorDebugEditAndContinueSnapshot](icordebugeditandcontinuesnapshot-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-197">[ICorDebugEditAndContinueSnapshot Interface](icordebugeditandcontinuesnapshot-interface.md)</span></span>\
 <span data-ttu-id="652c1-198">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="652c1-198">Obsolete.</span></span> <span data-ttu-id="652c1-199">No utilice esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="652c1-199">Do not use this interface.</span></span>  
  
 <span data-ttu-id="652c1-200">[ICorDebugEnum (interfaz)](icordebugenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-200">[ICorDebugEnum Interface](icordebugenum-interface1.md)</span></span>\
 <span data-ttu-id="652c1-201">Actúa como la interfaz base abstracta para la depuración de enumeradores.</span><span class="sxs-lookup"><span data-stu-id="652c1-201">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 <span data-ttu-id="652c1-202">[Interfaz Icordebugerrorinfoenum (](icordebugerrorinfoenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-202">[ICorDebugErrorInfoEnum Interface](icordebugerrorinfoenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-203">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="652c1-203">Obsolete.</span></span> <span data-ttu-id="652c1-204">No utilice esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="652c1-204">Do not use this interface.</span></span>  
  
 <span data-ttu-id="652c1-205">[ICorDebugEval (interfaz)](icordebugeval-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-205">[ICorDebugEval Interface](icordebugeval-interface.md)</span></span>\
 <span data-ttu-id="652c1-206">Proporciona métodos que permiten al depurador ejecutar código en el contexto del código que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="652c1-206">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 <span data-ttu-id="652c1-207">[Interfaz ICorDebugEval2](icordebugeval2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-207">[ICorDebugEval2 Interface](icordebugeval2-interface.md)</span></span>\
 <span data-ttu-id="652c1-208">Extiende `ICorDebugEval` para proporcionar compatibilidad con los tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="652c1-208">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 <span data-ttu-id="652c1-209">[Interfaz ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-209">[ICorDebugExceptionDebugEvent Interface](icordebugexceptiondebugevent-interface.md)</span></span>\
 <span data-ttu-id="652c1-210">Extiende la interfaz [ICorDebugDebugEvent](icordebugdebugevent-interface.md) para admitir eventos de excepción.</span><span class="sxs-lookup"><span data-stu-id="652c1-210">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="652c1-211">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="652c1-211">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="652c1-212">[Interfaz Icordebugexceptionobjectcallstackenum (](icordebugexceptionobjectcallstackenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-212">[ICorDebugExceptionObjectCallStackEnum Interface](icordebugexceptionobjectcallstackenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-213">Proporciona un enumerador para la información de la pila de llamadas que está incrustada en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="652c1-213">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 <span data-ttu-id="652c1-214">[Interfaz Icordebugexceptionobjectvalue (](icordebugexceptionobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-214">[ICorDebugExceptionObjectValue Interface](icordebugexceptionobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="652c1-215">Extiende la interfaz [ICorDebugObjectValue](icordebugobjectvalue-interface.md) para proporcionar información de seguimiento de la pila de un objeto de excepción administrado.</span><span class="sxs-lookup"><span data-stu-id="652c1-215">Extends the [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 <span data-ttu-id="652c1-216">[ICorDebugFrame (interfaz)](icordebugframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-216">[ICorDebugFrame Interface](icordebugframe-interface.md)</span></span>\
 <span data-ttu-id="652c1-217">Representa un marco en la pila actual.</span><span class="sxs-lookup"><span data-stu-id="652c1-217">Represents a frame on the current stack.</span></span>  
  
 <span data-ttu-id="652c1-218">[Interfaz ICorDebugFrameEnum (](icordebugframeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-218">[ICorDebugFrameEnum Interface](icordebugframeenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-219">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="652c1-219">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 <span data-ttu-id="652c1-220">[ICorDebugFunction (interfaz)](icordebugfunction-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-220">[ICorDebugFunction Interface](icordebugfunction-interface1.md)</span></span>\
 <span data-ttu-id="652c1-221">Representa una función o un método administrado.</span><span class="sxs-lookup"><span data-stu-id="652c1-221">Represents a managed function or method.</span></span>  
  
 <span data-ttu-id="652c1-222">[ICorDebugFunction2 (interfaz)](icordebugfunction2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-222">[ICorDebugFunction2 Interface](icordebugfunction2-interface.md)</span></span>\
 <span data-ttu-id="652c1-223">Extiende `ICorDebugFunction` de manera lógica para ofrecer compatibilidad con la depuración paso a paso de "Sólo mi código".</span><span class="sxs-lookup"><span data-stu-id="652c1-223">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 <span data-ttu-id="652c1-224">[Interfaz Icordebugfunction3 (](icordebugfunction3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-224">[ICorDebugFunction3 Interface](icordebugfunction3-interface.md)</span></span>\
 <span data-ttu-id="652c1-225">Extiende lógicamente la interfaz [ICorDebugFunction](icordebugfunction-interface1.md) para proporcionar acceso al código desde una solicitud ReJIT.</span><span class="sxs-lookup"><span data-stu-id="652c1-225">Logically extends the [ICorDebugFunction](icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 <span data-ttu-id="652c1-226">[Interfaz ICorDebugFunctionBreakpoint](icordebugfunctionbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-226">[ICorDebugFunctionBreakpoint Interface](icordebugfunctionbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="652c1-227">Amplía `ICorDebugBreakpoint` para admitir los puntos de interrupción dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="652c1-227">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 <span data-ttu-id="652c1-228">[Interfaz Icordebuggcreferenceenum (](icordebuggcreferenceenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-228">[ICorDebugGCReferenceEnum Interface](icordebuggcreferenceenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-229">Proporciona un enumerador para los objetos que se recolectarán como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="652c1-229">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 <span data-ttu-id="652c1-230">[Interfaz ICorDebugGenericValue](icordebuggenericvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-230">[ICorDebugGenericValue Interface](icordebuggenericvalue-interface.md)</span></span>\
 <span data-ttu-id="652c1-231">Subclase de `ICorDebugValue` que se aplica a todos los valores.</span><span class="sxs-lookup"><span data-stu-id="652c1-231">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="652c1-232">Esta interfaz proporciona métodos Get y Set para el valor.</span><span class="sxs-lookup"><span data-stu-id="652c1-232">This interface provides Get and Set methods for the value.</span></span>  
  
 <span data-ttu-id="652c1-233">[Interfaz Icordebugguidtotypeenum (](icordebugguidtotypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-233">[ICorDebugGuidToTypeEnum Interface](icordebugguidtotypeenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-234">Proporciona un enumerador para un objeto que asigna GUID y sus objetos `ICorDebugType` correspondientes.</span><span class="sxs-lookup"><span data-stu-id="652c1-234">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 <span data-ttu-id="652c1-235">[ICorDebugHandleValue (interfaz)](icordebughandlevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-235">[ICorDebugHandleValue Interface](icordebughandlevalue-interface.md)</span></span>\
 <span data-ttu-id="652c1-236">Subclase de `ICorDebugReferenceValue` que representa un valor de referencia para el cual el depurador ha creado un identificador para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="652c1-236">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 <span data-ttu-id="652c1-237">[Interfaz Icordebugheapenum (](icordebugheapenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-237">[ICorDebugHeapEnum Interface](icordebugheapenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-238">Proporciona un enumerador para los objetos del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="652c1-238">Provides an enumerator for objects on the managed heap.</span></span>  
  
 <span data-ttu-id="652c1-239">[Interfaz Icordebugheapsegmentenum (](icordebugheapsegmentenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-239">[ICorDebugHeapSegmentEnum Interface](icordebugheapsegmentenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-240">Proporciona un enumerador para las regiones de memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="652c1-240">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 <span data-ttu-id="652c1-241">[ICorDebugHeapValue (interfaz)](icordebugheapvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-241">[ICorDebugHeapValue Interface](icordebugheapvalue-interface.md)</span></span>\
 <span data-ttu-id="652c1-242">Subclase de `ICorDebugValue` que representa un objeto que ha sido recopilado por el recolector de elementos no utilizados de CLR.</span><span class="sxs-lookup"><span data-stu-id="652c1-242">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 <span data-ttu-id="652c1-243">[Interfaz Icordebugheapvalue2 (](icordebugheapvalue2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-243">[ICorDebugHeapValue2 Interface](icordebugheapvalue2-interface1.md)</span></span>\
 <span data-ttu-id="652c1-244">Extensión de `ICorDebugHeapValue` que proporciona compatibilidad con los identificadores del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="652c1-244">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 <span data-ttu-id="652c1-245">[Interfaz ICorDebugHeapValue3](icordebugheapvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-245">[ICorDebugHeapValue3 Interface](icordebugheapvalue3-interface.md)</span></span>\
 <span data-ttu-id="652c1-246">Expone las propiedades de bloqueo de monitor de objetos.</span><span class="sxs-lookup"><span data-stu-id="652c1-246">Exposes the monitor lock properties of objects.</span></span>  
  
 <span data-ttu-id="652c1-247">[Interfaz ICorDebugILCode](icordebugilcode-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-247">[ICorDebugILCode Interface](icordebugilcode-interface.md)</span></span>\
 <span data-ttu-id="652c1-248">Representa un segmento de código de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="652c1-248">Represents a segment of intermediate language (IL) code.</span></span>  
  
 <span data-ttu-id="652c1-249">[Interfaz ICorDebugILCode2](icordebugilcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-249">[ICorDebugILCode2 Interface](icordebugilcode2-interface.md)</span></span>\
 <span data-ttu-id="652c1-250">Extiende lógicamente la interfaz [ICorDebugILCode](icordebugilcode-interface.md) para proporcionar métodos que devuelven el token de la firma de variable local de una función y que asignan los desplazamientos del lenguaje intermedio INSTRUMENTADO (IL) del generador de perfiles a los desplazamientos de Il del método original.</span><span class="sxs-lookup"><span data-stu-id="652c1-250">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 <span data-ttu-id="652c1-251">[ICorDebugILFrame (interfaz)](icordebugilframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-251">[ICorDebugILFrame Interface](icordebugilframe-interface.md)</span></span>\
 <span data-ttu-id="652c1-252">Representa un marco de pila de código de MSIL.</span><span class="sxs-lookup"><span data-stu-id="652c1-252">Represents a stack frame of MSIL code.</span></span>  
  
 <span data-ttu-id="652c1-253">[Interfaz ICorDebugILFrame2](icordebugilframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-253">[ICorDebugILFrame2 Interface](icordebugilframe2-interface.md)</span></span>\
 <span data-ttu-id="652c1-254">Extensión lógica de `ICorDebugILFrame`.</span><span class="sxs-lookup"><span data-stu-id="652c1-254">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 <span data-ttu-id="652c1-255">[Interfaz ICorDebugILFrame3](icordebugilframe3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-255">[ICorDebugILFrame3 Interface](icordebugilframe3-interface.md)</span></span>\
 <span data-ttu-id="652c1-256">Proporciona un método que encapsula el valor devuelto de una función.</span><span class="sxs-lookup"><span data-stu-id="652c1-256">Provides a method that encapsulates the return value of a function.</span></span>  
  
 <span data-ttu-id="652c1-257">[Interfaz ICorDebugILFrame4](icordebugilframe4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-257">[ICorDebugILFrame4 Interface](icordebugilframe4-interface.md)</span></span>\
 <span data-ttu-id="652c1-258">Proporciona métodos que permiten acceder a las variables locales y al código en un marco de pila de código de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="652c1-258">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="652c1-259">Un parámetro especifica si el depurador tiene acceso a las variables y al código agregados en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="652c1-259">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 <span data-ttu-id="652c1-260">[Interfaz ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-260">[ICorDebugInstanceFieldSymbol Interface](icordebuginstancefieldsymbol-interface.md)</span></span>\
 <span data-ttu-id="652c1-261">Representa la información de símbolos de depuración para un campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="652c1-261">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="652c1-262">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="652c1-262">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="652c1-263">[Interfaz ICorDebugInternalFrame (](icordebuginternalframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-263">[ICorDebugInternalFrame Interface](icordebuginternalframe-interface.md)</span></span>\
 <span data-ttu-id="652c1-264">Identifica los tipos de marco del depurador.</span><span class="sxs-lookup"><span data-stu-id="652c1-264">Identifies frame types for the debugger.</span></span>  
  
 <span data-ttu-id="652c1-265">[Interfaz ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-265">[ICorDebugInternalFrame2 Interface](icordebuginternalframe2-interface.md)</span></span>\
 <span data-ttu-id="652c1-266">Proporciona información sobre los marcos internos, incluida la dirección de pila y la posición en relación con los objetos [ICorDebugFrame](icordebugframe-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="652c1-266">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](icordebugframe-interface.md) objects.</span></span>  
  
 <span data-ttu-id="652c1-267">[Interfaz ICorDebugLoadedModule](icordebugloadedmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-267">[ICorDebugLoadedModule Interface](icordebugloadedmodule-interface.md)</span></span>\
 <span data-ttu-id="652c1-268">Proporciona información acerca de un módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="652c1-268">Provides information about a loaded module.</span></span> <span data-ttu-id="652c1-269">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="652c1-269">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="652c1-270">[ICorDebugManagedCallback (interfaz)](icordebugmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-270">[ICorDebugManagedCallback Interface](icordebugmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="652c1-271">Proporciona métodos que permiten procesar las devoluciones de llamada del depurador.</span><span class="sxs-lookup"><span data-stu-id="652c1-271">Provides methods to process debugger callbacks.</span></span>  
  
 <span data-ttu-id="652c1-272">[Interfaz ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-272">[ICorDebugManagedCallback2 Interface](icordebugmanagedcallback2-interface.md)</span></span>\
 <span data-ttu-id="652c1-273">Proporciona métodos para admitir el control de excepciones del depurador y asistentes para depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="652c1-273">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="652c1-274">`ICorDebugManagedCallback2` es una extensión lógica de `ICorDebugManagedCallback`.</span><span class="sxs-lookup"><span data-stu-id="652c1-274">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 <span data-ttu-id="652c1-275">[Interfaz Icordebugmanagedcallback3 (](icordebugmanagedcallback3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-275">[ICorDebugManagedCallback3 Interface](icordebugmanagedcallback3-interface.md)</span></span>\
 <span data-ttu-id="652c1-276">Proporciona un método de devolución de llamada que indica que se ha producido una notificación del depurador personalizada habilitada.</span><span class="sxs-lookup"><span data-stu-id="652c1-276">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 <span data-ttu-id="652c1-277">[ICorDebugMDA (interfaz)](icordebugmda-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-277">[ICorDebugMDA Interface](icordebugmda-interface.md)</span></span>\
 <span data-ttu-id="652c1-278">Representa un mensaje del asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="652c1-278">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 <span data-ttu-id="652c1-279">[Interfaz ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-279">[ICorDebugMemoryBuffer Interface](icordebugmemorybuffer-interface.md)</span></span>\
 <span data-ttu-id="652c1-280">Representa un búfer en memoria.</span><span class="sxs-lookup"><span data-stu-id="652c1-280">Represents an in-memory buffer.</span></span> <span data-ttu-id="652c1-281">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="652c1-281">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="652c1-282">[Interfaz ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-282">[ICorDebugMergedAssemblyRecord Interface](icordebugmergedassemblyrecord-interface.md)</span></span>\
 <span data-ttu-id="652c1-283">Proporciona información acerca de un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="652c1-283">Provides information about a merged assembly.</span></span> <span data-ttu-id="652c1-284">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="652c1-284">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="652c1-285">[Interfaz ICorDebugMetaDataLocator (](icordebugmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-285">[ICorDebugMetaDataLocator Interface](icordebugmetadatalocator-interface.md)</span></span>\
 <span data-ttu-id="652c1-286">Proporciona información de metadatos al depurador.</span><span class="sxs-lookup"><span data-stu-id="652c1-286">Provides metadata information to the debugger.</span></span>  
  
 <span data-ttu-id="652c1-287">[ICorDebugModule (interfaz)](icordebugmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-287">[ICorDebugModule Interface](icordebugmodule-interface.md)</span></span>\
 <span data-ttu-id="652c1-288">Representa un módulo de CLR, que es un archivo ejecutable o una biblioteca de vínculos dinámicos (DLL).</span><span class="sxs-lookup"><span data-stu-id="652c1-288">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 <span data-ttu-id="652c1-289">[Interfaz ICorDebugModule2](icordebugmodule2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-289">[ICorDebugModule2 Interface](icordebugmodule2-interface.md)</span></span>\
 <span data-ttu-id="652c1-290">Actúa como una extensión lógica de `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="652c1-290">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 <span data-ttu-id="652c1-291">[Interfaz ICorDebugModule3](icordebugmodule3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-291">[ICorDebugModule3 Interface](icordebugmodule3-interface.md)</span></span>\
 <span data-ttu-id="652c1-292">Crea un lector de símbolos para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="652c1-292">Creates a symbol reader for a dynamic module.</span></span>  
  
 <span data-ttu-id="652c1-293">[Interfaz ICorDebugModuleBreakpoint (](icordebugmodulebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-293">[ICorDebugModuleBreakpoint Interface](icordebugmodulebreakpoint-interface.md)</span></span>\
 <span data-ttu-id="652c1-294">Extiende `ICorDebugBreakpoint` para proporcionar acceso a módulos específicos.</span><span class="sxs-lookup"><span data-stu-id="652c1-294">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 <span data-ttu-id="652c1-295">[Interfaz ICorDebugModuleDebugEvent](icordebugmoduledebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-295">[ICorDebugModuleDebugEvent Interface](icordebugmoduledebugevent-interface.md)</span></span>\
 <span data-ttu-id="652c1-296">Extiende la interfaz [ICorDebugDebugEvent](icordebugdebugevent-interface.md) para admitir eventos de nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="652c1-296">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="652c1-297">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="652c1-297">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="652c1-298">[Interfaz ICorDebugModuleEnum (](icordebugmoduleenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-298">[ICorDebugModuleEnum Interface](icordebugmoduleenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-299">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="652c1-299">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 <span data-ttu-id="652c1-300">[Interfaz ICorDebugMutableDataTarget](icordebugmutabledatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-300">[ICorDebugMutableDataTarget Interface](icordebugmutabledatatarget-interface.md)</span></span>\
 <span data-ttu-id="652c1-301">Extiende la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md) para admitir destinos de datos mutables.</span><span class="sxs-lookup"><span data-stu-id="652c1-301">Extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 <span data-ttu-id="652c1-302">[ICorDebugNativeFrame (interfaz)](icordebugnativeframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-302">[ICorDebugNativeFrame Interface](icordebugnativeframe-interface.md)</span></span>\
 <span data-ttu-id="652c1-303">Implementación especializada de `ICorDebugFrame` que se utiliza para los marcos nativos.</span><span class="sxs-lookup"><span data-stu-id="652c1-303">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 <span data-ttu-id="652c1-304">[Interfaz ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-304">[ICorDebugNativeFrame2 Interface](icordebugnativeframe2-interface.md)</span></span>\
 <span data-ttu-id="652c1-305">Proporciona métodos que comprueban las relaciones entre marcos primarios y secundarios.</span><span class="sxs-lookup"><span data-stu-id="652c1-305">Provides methods that test for child and parent frame relationships.</span></span>  
  
 <span data-ttu-id="652c1-306">[Interfaz ICorDebugObjectEnum (](icordebugobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-306">[ICorDebugObjectEnum Interface](icordebugobjectenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-307">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de objetos según sus direcciones virtuales relativas (RVA).</span><span class="sxs-lookup"><span data-stu-id="652c1-307">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 <span data-ttu-id="652c1-308">[ICorDebugObjectValue (interfaz)](icordebugobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-308">[ICorDebugObjectValue Interface](icordebugobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="652c1-309">Subclase de `ICorDebugValue` que representa un valor que contiene un objeto.</span><span class="sxs-lookup"><span data-stu-id="652c1-309">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 <span data-ttu-id="652c1-310">[Interfaz Icordebugobjectvalue2 (](icordebugobjectvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-310">[ICorDebugObjectValue2 Interface](icordebugobjectvalue2-interface.md)</span></span>\
 <span data-ttu-id="652c1-311">Extiende `ICorDebugObjectValue` para ofrecer compatibilidad con la herencia y los reemplazos.</span><span class="sxs-lookup"><span data-stu-id="652c1-311">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 <span data-ttu-id="652c1-312">[ICorDebugProcess (interfaz)](icordebugprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-312">[ICorDebugProcess Interface](icordebugprocess-interface.md)</span></span>\
 <span data-ttu-id="652c1-313">Representa un proceso que ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="652c1-313">Represents a process that is executing managed code.</span></span>  
  
 <span data-ttu-id="652c1-314">[Interfaz ICorDebugProcess2](icordebugprocess2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-314">[ICorDebugProcess2 Interface](icordebugprocess2-interface1.md)</span></span>\
 <span data-ttu-id="652c1-315">Extensión lógica de `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="652c1-315">A logical extension of `ICorDebugProcess`.</span></span>  
  
 <span data-ttu-id="652c1-316">[Interfaz Icordebugprocess3 (](icordebugprocess3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-316">[ICorDebugProcess3 Interface](icordebugprocess3-interface.md)</span></span>\
 <span data-ttu-id="652c1-317">Controla las notificaciones del depurador personalizadas.</span><span class="sxs-lookup"><span data-stu-id="652c1-317">Controls custom debugger notifications.</span></span>

 <span data-ttu-id="652c1-318">[Interfaz ICorDebugProcess4](icordebugprocess4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-318">[ICorDebugProcess4 Interface](icordebugprocess4-interface.md)</span></span>\
 <span data-ttu-id="652c1-319">Proporciona compatibilidad para el control de ejecución fuera de proceso.</span><span class="sxs-lookup"><span data-stu-id="652c1-319">Provides support for out of process execution control.</span></span>
  
 <span data-ttu-id="652c1-320">[Interfaz ICorDebugProcess5](icordebugprocess5-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-320">[ICorDebugProcess5 Interface](icordebugprocess5-interface.md)</span></span>\
 <span data-ttu-id="652c1-321">Extiende la interfaz [ICorDebugProcess](icordebugprocess-interface.md) para admitir el acceso al montón administrado, para proporcionar información sobre la recolección de elementos no utilizados de objetos administrados y para determinar si un depurador carga imágenes desde la memoria caché de imágenes nativas local de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="652c1-321">Extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 <span data-ttu-id="652c1-322">[Interfaz método icordebugprocess6](icordebugprocess6-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-322">[ICorDebugProcess6 Interface](icordebugprocess6-interface.md)</span></span>\
 <span data-ttu-id="652c1-323">Extiende lógicamente la interfaz [ICorDebugProcess](icordebugprocess-interface.md) para habilitar características como la descodificación de eventos de depuración administrados codificados en eventos de depuración de excepción nativa y la división de módulos virtuales.</span><span class="sxs-lookup"><span data-stu-id="652c1-323">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="652c1-324">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="652c1-324">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="652c1-325">[Interfaz Icordebugprocess7 (](icordebugprocess7-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-325">[ICorDebugProcess7 Interface](icordebugprocess7-interface.md)</span></span>\
 <span data-ttu-id="652c1-326">Proporciona un método que configura el depurador para controlar las actualizaciones en memoria de los metadatos en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="652c1-326">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 <span data-ttu-id="652c1-327">[Interfaz ICorDebugProcess8](icordebugprocess8-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-327">[ICorDebugProcess8 Interface](icordebugprocess8-interface.md)</span></span>\
 <span data-ttu-id="652c1-328">Extiende lógicamente la interfaz [ICorDebugProcess](icordebugprocess-interface.md) para habilitar o deshabilitar determinados tipos de devoluciones de llamada de excepción [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="652c1-328">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 <span data-ttu-id="652c1-329">[Interfaz Icordebugprocessenum (](icordebugprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-329">[ICorDebugProcessEnum Interface](icordebugprocessenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-330">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="652c1-330">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 <span data-ttu-id="652c1-331">[ICorDebugReferenceValue (interfaz)](icordebugreferencevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-331">[ICorDebugReferenceValue Interface](icordebugreferencevalue-interface.md)</span></span>\
 <span data-ttu-id="652c1-332">Subclase de `ICorDebugValue` que admite tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="652c1-332">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 <span data-ttu-id="652c1-333">[ICorDebugRegisterSet (interfaz)](icordebugregisterset-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-333">[ICorDebugRegisterSet Interface](icordebugregisterset-interface.md)</span></span>\
 <span data-ttu-id="652c1-334">Representa el conjunto de registros disponibles en el equipo que está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="652c1-334">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 <span data-ttu-id="652c1-335">[Interfaz ICorDebugRegisterSet2](icordebugregisterset2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-335">[ICorDebugRegisterSet2 Interface](icordebugregisterset2-interface.md)</span></span>\
 <span data-ttu-id="652c1-336">Extiende la funcionalidad de `ICorDebugRegisterSet` para plataformas hardware que tienen más de 64 registros.</span><span class="sxs-lookup"><span data-stu-id="652c1-336">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 <span data-ttu-id="652c1-337">[Interfaz ICorDebugRemote](icordebugremote-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-337">[ICorDebugRemote Interface](icordebugremote-interface.md)</span></span>\
 <span data-ttu-id="652c1-338">Proporciona la capacidad de iniciar o de adjuntar un depurador administrado a un proceso remoto de destino.</span><span class="sxs-lookup"><span data-stu-id="652c1-338">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 <span data-ttu-id="652c1-339">[Interfaz ICorDebugRemoteTarget](icordebugremotetarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-339">[ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md)</span></span>\
 <span data-ttu-id="652c1-340">Proporciona métodos que permiten depurar aplicaciones basadas en Silverlight en el entorno de CLR.</span><span class="sxs-lookup"><span data-stu-id="652c1-340">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="652c1-341">[Interfaz Icordebugruntimeunwindableframe (](icordebugruntimeunwindableframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-341">[ICorDebugRuntimeUnwindableFrame Interface](icordebugruntimeunwindableframe-interface.md)</span></span>\
 <span data-ttu-id="652c1-342">Proporciona compatibilidad para métodos no administrados que necesitan que Common Language Runtime (CLR) desenrede un marco.</span><span class="sxs-lookup"><span data-stu-id="652c1-342">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 <span data-ttu-id="652c1-343">[ICorDebugStackWalk (interfaz)](icordebugstackwalk-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-343">[ICorDebugStackWalk Interface](icordebugstackwalk-interface.md)</span></span>\
 <span data-ttu-id="652c1-344">Proporciona métodos para obtener los métodos administrados, o marcos, de la pila de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="652c1-344">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 <span data-ttu-id="652c1-345">[Interfaz ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-345">[ICorDebugStaticFieldSymbol Interface](icordebugstaticfieldsymbol-interface.md)</span></span>\
 <span data-ttu-id="652c1-346">Representa la información de símbolos de depuración para un campo estático.</span><span class="sxs-lookup"><span data-stu-id="652c1-346">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="652c1-347">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="652c1-347">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="652c1-348">[ICorDebugStepper (interfaz)](icordebugstepper-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-348">[ICorDebugStepper Interface](icordebugstepper-interface.md)</span></span>\
 <span data-ttu-id="652c1-349">Representa un paso en la ejecución del código realizado por un depurador, actúa como identificador entre la emisión y la finalización de un comando, y proporciona un modo de cancelar un paso.</span><span class="sxs-lookup"><span data-stu-id="652c1-349">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 <span data-ttu-id="652c1-350">[Interfaz Icordebugstepper2 (](icordebugstepper2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-350">[ICorDebugStepper2 Interface](icordebugstepper2-interface1.md)</span></span>\
 <span data-ttu-id="652c1-351">Proporciona compatibilidad con la depuración de "Sólo mi código" (JMC).</span><span class="sxs-lookup"><span data-stu-id="652c1-351">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 <span data-ttu-id="652c1-352">[Interfaz ICorDebugStepperEnum (](icordebugstepperenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-352">[ICorDebugStepperEnum Interface](icordebugstepperenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-353">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugStepper`.</span><span class="sxs-lookup"><span data-stu-id="652c1-353">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 <span data-ttu-id="652c1-354">[ICorDebugStringValue (interfaz)](icordebugstringvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-354">[ICorDebugStringValue Interface](icordebugstringvalue-interface.md)</span></span>\
 <span data-ttu-id="652c1-355">Subclase de `ICorDebugHeapValue` que se aplica a los valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="652c1-355">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 <span data-ttu-id="652c1-356">[Interfaz ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-356">[ICorDebugSymbolProvider Interface](icordebugsymbolprovider-interface.md)</span></span>\
 <span data-ttu-id="652c1-357">Proporciona métodos que pueden utilizarse para recuperar información de símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="652c1-357">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="652c1-358">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="652c1-358">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="652c1-359">[Interfaz Icordebugsymbolprovider2 (](icordebugsymbolprovider2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-359">[ICorDebugSymbolProvider2 Interface](icordebugsymbolprovider2-interface.md)</span></span>\
 <span data-ttu-id="652c1-360">Extiende lógicamente la interfaz [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) para recuperar información de símbolos de depuración adicional.</span><span class="sxs-lookup"><span data-stu-id="652c1-360">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="652c1-361">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="652c1-361">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="652c1-362">[ICorDebugThread (interfaz)](icordebugthread-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-362">[ICorDebugThread Interface](icordebugthread-interface.md)</span></span>\
 <span data-ttu-id="652c1-363">Representa un subproceso de un proceso.</span><span class="sxs-lookup"><span data-stu-id="652c1-363">Represents a thread in a process.</span></span> <span data-ttu-id="652c1-364">El período de duración de una instancia de `ICorDebugThread` es el mismo que el del subproceso que representa.</span><span class="sxs-lookup"><span data-stu-id="652c1-364">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 <span data-ttu-id="652c1-365">[Interfaz ICorDebugThread2](icordebugthread2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-365">[ICorDebugThread2 Interface](icordebugthread2-interface.md)</span></span>\
 <span data-ttu-id="652c1-366">Actúa como una extensión lógica de `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="652c1-366">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 <span data-ttu-id="652c1-367">[Interfaz ICorDebugThread3](icordebugthread3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-367">[ICorDebugThread3 Interface](icordebugthread3-interface.md)</span></span>\
 <span data-ttu-id="652c1-368">Proporciona el punto de entrada a [ICorDebugStackWalk](icordebugstackwalk-interface.md) y las interfaces correspondientes.</span><span class="sxs-lookup"><span data-stu-id="652c1-368">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 <span data-ttu-id="652c1-369">[Interfaz ICorDebugThread4](icordebugthread4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-369">[ICorDebugThread4 Interface](icordebugthread4-interface.md)</span></span>\
 <span data-ttu-id="652c1-370">Proporciona información de bloqueo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="652c1-370">Provides thread blocking information.</span></span>  
  
 <span data-ttu-id="652c1-371">[Interfaz ICorDebugThreadEnum (](icordebugthreadenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-371">[ICorDebugThreadEnum Interface](icordebugthreadenum-interface1.md)</span></span>\
 <span data-ttu-id="652c1-372">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="652c1-372">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 <span data-ttu-id="652c1-373">[ICorDebugType (interfaz)](icordebugtype-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-373">[ICorDebugType Interface](icordebugtype-interface.md)</span></span>\
 <span data-ttu-id="652c1-374">Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="652c1-374">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="652c1-375">Si el tipo es genérico, `ICorDebugType` representa el tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="652c1-375">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 <span data-ttu-id="652c1-376">[Interfaz ICorDebugType2](icordebugtype2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-376">[ICorDebugType2 Interface](icordebugtype2-interface.md)</span></span>\
 <span data-ttu-id="652c1-377">Extiende la interfaz [ICorDebugType](icordebugtype-interface.md) para recuperar el identificador de tipo de un tipo base o un tipo complejo (definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="652c1-377">Extends the [ICorDebugType](icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 <span data-ttu-id="652c1-378">[ICorDebugTypeEnum (interfaz)](icordebugtypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-378">[ICorDebugTypeEnum Interface](icordebugtypeenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-379">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="652c1-379">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 <span data-ttu-id="652c1-380">[Interfaz ICorDebugUnmanagedCallback (](icordebugunmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-380">[ICorDebugUnmanagedCallback Interface](icordebugunmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="652c1-381">Proporciona notificación de eventos nativos no relacionados directamente con CLR.</span><span class="sxs-lookup"><span data-stu-id="652c1-381">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="652c1-382">[ICorDebugValue](icordebugvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-382">[ICorDebugValue](icordebugvalue-interface.md)</span></span>\
 <span data-ttu-id="652c1-383">Representa un valor de escritura o lectura en el proceso que se va a depurar.</span><span class="sxs-lookup"><span data-stu-id="652c1-383">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="652c1-384">[ICorDebugValue2](icordebugvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-384">[ICorDebugValue2](icordebugvalue2-interface.md)</span></span>\
 <span data-ttu-id="652c1-385">Extiende `ICorDebugValue` para proporcionar compatibilidad con `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="652c1-385">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="652c1-386">[Interfaz Icordebugvalue3 (](icordebugvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-386">[ICorDebugValue3 Interface](icordebugvalue3-interface.md)</span></span>\
 <span data-ttu-id="652c1-387">Extiende las interfaces "ICorDebugValue" y "ICorDebugValue2" para proporcionar compatibilidad con matrices mayores de 2 GB.</span><span class="sxs-lookup"><span data-stu-id="652c1-387">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="652c1-388">[Icordebugvaluebreakpoint (](icordebugvaluebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-388">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)</span></span>\
 <span data-ttu-id="652c1-389">Extiende `ICorDebugBreakpoint` para proporcionar acceso a valores concretos.</span><span class="sxs-lookup"><span data-stu-id="652c1-389">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="652c1-390">[ICorDebugValueEnum](icordebugvalueenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-390">[ICorDebugValueEnum](icordebugvalueenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-391">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="652c1-391">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 <span data-ttu-id="652c1-392">[Interfaz ICorDebugVariableHome](icordebugvariablehome-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-392">[ICorDebugVariableHome Interface](icordebugvariablehome-interface.md)</span></span>\
 <span data-ttu-id="652c1-393">Representa una variable local o un argumento de una función.</span><span class="sxs-lookup"><span data-stu-id="652c1-393">Represents a local variable or argument of a function.</span></span>  
  
 <span data-ttu-id="652c1-394">[Interfaz ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-394">[ICorDebugVariableHomeEnum Interface](icordebugvariablehomeenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-395">Proporciona un enumerador para las variables locales y los argumentos de una función.</span><span class="sxs-lookup"><span data-stu-id="652c1-395">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="652c1-396">[Interfaz ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-396">[ICorDebugVariableSymbol Interface](icordebugvariablesymbol-interface.md)</span></span>\
 <span data-ttu-id="652c1-397">Recupera la información de símbolos de depuración para una variable.</span><span class="sxs-lookup"><span data-stu-id="652c1-397">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="652c1-398">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="652c1-398">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="652c1-399">[Interfaz ICorDebugVirtualUnwinder](icordebugvirtualunwinder-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-399">[ICorDebugVirtualUnwinder Interface](icordebugvirtualunwinder-interface.md)</span></span>\
 <span data-ttu-id="652c1-400">Proporciona métodos que ayudan al desenredo de la pila.</span><span class="sxs-lookup"><span data-stu-id="652c1-400">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="652c1-401">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="652c1-401">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="652c1-402">[ICorPublish (interfaz)](icorpublish-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-402">[ICorPublish Interface](icorpublish-interface.md)</span></span>\
 <span data-ttu-id="652c1-403">Actúa como interfaz general para los procesos de publicación.</span><span class="sxs-lookup"><span data-stu-id="652c1-403">Serves as the general interface for the publishing processes.</span></span>  
  
 <span data-ttu-id="652c1-404">[ICorPublishAppDomain (interfaz)](icorpublishappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-404">[ICorPublishAppDomain Interface](icorpublishappdomain-interface.md)</span></span>\
 <span data-ttu-id="652c1-405">Representa y proporciona información sobre un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="652c1-405">Represents and provides information about an application domain.</span></span>  
  
 <span data-ttu-id="652c1-406">[Interfaz ICorPublishAppDomainEnum (](icorpublishappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-406">[ICorPublishAppDomainEnum Interface](icorpublishappdomainenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-407">Proporciona métodos que atraviesan una colección de objetos `ICorPublishAppDomain` que actualmente existen dentro de un proceso.</span><span class="sxs-lookup"><span data-stu-id="652c1-407">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 <span data-ttu-id="652c1-408">[ICorPublishEnum (interfaz)](icorpublishenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-408">[ICorPublishEnum Interface](icorpublishenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-409">Actúa como la base abstracta para los enumeradores de publicación.</span><span class="sxs-lookup"><span data-stu-id="652c1-409">Serves as the abstract base for publishing enumerators.</span></span>  
  
 <span data-ttu-id="652c1-410">[ICorPublishProcess (interfaz)](icorpublishprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-410">[ICorPublishProcess Interface](icorpublishprocess-interface.md)</span></span>\
 <span data-ttu-id="652c1-411">Proporciona métodos que tienen acceso a información de un proceso.</span><span class="sxs-lookup"><span data-stu-id="652c1-411">Provides methods that access information about a process.</span></span>  
  
 <span data-ttu-id="652c1-412">[Interfaz ICorPublishProcessEnum (](icorpublishprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-412">[ICorPublishProcessEnum Interface](icorpublishprocessenum-interface.md)</span></span>\
 <span data-ttu-id="652c1-413">Proporciona métodos que atraviesan una colección de objetos `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="652c1-413">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  

 <span data-ttu-id="652c1-414">[Interfaz ISOSDacInterface](isosdacinterface-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-414">[ISOSDacInterface Interface](isosdacinterface-interface.md)</span></span>\
 <span data-ttu-id="652c1-415">Proporciona métodos auxiliares para tener acceso a los datos de `SOS` .</span><span class="sxs-lookup"><span data-stu-id="652c1-415">Provides helper methods to access data from `SOS`.</span></span>

 <span data-ttu-id="652c1-416">[Interfaz IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-416">[IXCLRDataMethodDefinition Interface](ixclrdatamethoddefinition-interface.md)</span></span>\
 <span data-ttu-id="652c1-417">Proporciona métodos para consultar información sobre una definición de método.</span><span class="sxs-lookup"><span data-stu-id="652c1-417">Provides methods for querying information about a method definition.</span></span>

 <span data-ttu-id="652c1-418">[Interfaz IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-418">[IXCLRDataMethodInstance Interface](ixclrdatamethodinstance-interface.md)</span></span>\
 <span data-ttu-id="652c1-419">Proporciona métodos para consultar información sobre una instancia de método.</span><span class="sxs-lookup"><span data-stu-id="652c1-419">Provides methods for querying information about a method instance.</span></span>

 <span data-ttu-id="652c1-420">[Interfaz IXCLRDataModule](ixclrdatamodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-420">[IXCLRDataModule Interface](ixclrdatamodule-interface.md)</span></span>\
 <span data-ttu-id="652c1-421">Proporciona métodos para consultar información sobre un módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="652c1-421">Provides methods for querying information about a loaded module.</span></span>

 <span data-ttu-id="652c1-422">[Interfaz IXCLRDataProcess](ixclrdataprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-422">[IXCLRDataProcess Interface](ixclrdataprocess-interface.md)</span></span>\
 <span data-ttu-id="652c1-423">Proporciona métodos para consultar información sobre un proceso.</span><span class="sxs-lookup"><span data-stu-id="652c1-423">Provides methods for querying information about a process.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="652c1-424">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="652c1-424">Related Sections</span></span>  

 <span data-ttu-id="652c1-425">[Coclases de depuración](debugging-coclasses.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-425">[Debugging Coclasses](debugging-coclasses.md)</span></span>\
 <span data-ttu-id="652c1-426">[Funciones estáticas globales de depuración](debugging-global-static-functions.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-426">[Debugging Global Static Functions](debugging-global-static-functions.md)</span></span>\
 <span data-ttu-id="652c1-427">[Enumeraciones de depuración](debugging-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-427">[Debugging Enumerations](debugging-enumerations.md)</span></span>\
 <span data-ttu-id="652c1-428">[Estructuras de depuración](debugging-structures.md)</span><span class="sxs-lookup"><span data-stu-id="652c1-428">[Debugging Structures](debugging-structures.md)</span></span>\
