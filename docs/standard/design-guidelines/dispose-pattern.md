---
title: Patrón de Dispose
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Dispose method
- class library design guidelines [.NET Framework], Dispose method
- class library design guidelines [.NET Framework], Finalize method
- customizing Dispose method name
- Finalize method
ms.assetid: 31a6c13b-d6a2-492b-9a9f-e5238c983bcb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7bb9420d6439cff36c5cfa997152773503fbd9a
ms.sourcegitcommit: ed7b4b9b77d35e94a35a2634e8c874f46603fb2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2018
ms.locfileid: "36948555"
---
# <a name="dispose-pattern"></a><span data-ttu-id="e41f9-102">Patrón de Dispose</span><span class="sxs-lookup"><span data-stu-id="e41f9-102">Dispose Pattern</span></span>
<span data-ttu-id="e41f9-103">Todos los programas adquieren uno o más recursos del sistema, como la memoria, los identificadores del sistema o las conexiones de base de datos, en el transcurso de su ejecución.</span><span class="sxs-lookup"><span data-stu-id="e41f9-103">All programs acquire one or more system resources, such as memory, system handles, or database connections, during the course of their execution.</span></span> <span data-ttu-id="e41f9-104">Los desarrolladores tienen que tenga cuidado al usar estos recursos del sistema, porque debe liberarse después de adquirir y usar.</span><span class="sxs-lookup"><span data-stu-id="e41f9-104">Developers have to be careful when using such system resources, because they must be released after they have been acquired and used.</span></span>  
  
 <span data-ttu-id="e41f9-105">CLR proporciona compatibilidad para la administración automática de la memoria.</span><span class="sxs-lookup"><span data-stu-id="e41f9-105">The CLR provides support for automatic memory management.</span></span> <span data-ttu-id="e41f9-106">La memoria administrada (memoria asignada mediante el operador de C# `new`) no es necesario liberar de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="e41f9-106">Managed memory (memory allocated using the C# operator `new`) does not need to be explicitly released.</span></span> <span data-ttu-id="e41f9-107">Se liberan automáticamente por el recolector de elementos no utilizados (GC).</span><span class="sxs-lookup"><span data-stu-id="e41f9-107">It is released automatically by the garbage collector (GC).</span></span> <span data-ttu-id="e41f9-108">Esto evita que los desarrolladores la tarea tediosa y difícil de liberación de memoria y ha sido una de las razones principales para la productividad sin precedentes ofrecida por .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e41f9-108">This frees developers from the tedious and difficult task of releasing memory and has been one of the main reasons for the unprecedented productivity afforded by the .NET Framework.</span></span>  
  
 <span data-ttu-id="e41f9-109">Desafortunadamente, la memoria administrada es solo uno de muchos tipos de recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="e41f9-109">Unfortunately, managed memory is just one of many types of system resources.</span></span> <span data-ttu-id="e41f9-110">Aún así, los recursos distintos de la memoria administrada deben liberar explícitamente y se conocen como recursos no administrados.</span><span class="sxs-lookup"><span data-stu-id="e41f9-110">Resources other than managed memory still need to be released explicitly and are referred to as unmanaged resources.</span></span> <span data-ttu-id="e41f9-111">El catálogo global concreto no se diseñó para administrar estos recursos no administrados, lo que significa que la responsabilidad de administrar los recursos no administrados que se encuentra en manos de los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="e41f9-111">The GC was specifically not designed to manage such unmanaged resources, which means that the responsibility for managing unmanaged resources lies in the hands of the developers.</span></span>  
  
 <span data-ttu-id="e41f9-112">El CLR proporciona ayuda en liberar recursos no administrados.</span><span class="sxs-lookup"><span data-stu-id="e41f9-112">The CLR provides some help in releasing unmanaged resources.</span></span> <span data-ttu-id="e41f9-113"><xref:System.Object?displayProperty=nameWithType> declara un método virtual <xref:System.Object.Finalize%2A> (también denominado el finalizador) que es llamado por el catálogo global antes de la memoria del objeto sea reclamada por el catálogo global y se puede invalidar para liberar recursos no administrados.</span><span class="sxs-lookup"><span data-stu-id="e41f9-113"><xref:System.Object?displayProperty=nameWithType> declares a virtual method <xref:System.Object.Finalize%2A> (also called the finalizer) that is called by the GC before the object’s memory is reclaimed by the GC and can be overridden to release unmanaged resources.</span></span> <span data-ttu-id="e41f9-114">Los tipos que invalidan el finalizador se conocen como tipos susceptibles de finalización.</span><span class="sxs-lookup"><span data-stu-id="e41f9-114">Types that override the finalizer are referred to as finalizable types.</span></span>  
  
 <span data-ttu-id="e41f9-115">Aunque los finalizadores son eficaces en algunos escenarios de limpieza, tienen dos desventajas importantes:</span><span class="sxs-lookup"><span data-stu-id="e41f9-115">Although finalizers are effective in some cleanup scenarios, they have two significant drawbacks:</span></span>  
  
-   <span data-ttu-id="e41f9-116">El finalizador se llama cuando el GC detecta que un objeto es apto para la recolección.</span><span class="sxs-lookup"><span data-stu-id="e41f9-116">The finalizer is called when the GC detects that an object is eligible for collection.</span></span> <span data-ttu-id="e41f9-117">Esto sucede durante un período indeterminado de tiempo después de que el recurso no es necesaria ya.</span><span class="sxs-lookup"><span data-stu-id="e41f9-117">This happens at some undetermined period of time after the resource is not needed anymore.</span></span> <span data-ttu-id="e41f9-118">El retraso entre cuando el desarrollador puede o desea liberar el recurso y la hora cuando el recurso se libera realmente por el finalizador podría ser aceptable en programas que adquieren muchos recursos insuficientes (recursos que se pueden agotar fácilmente) o en casos en que los recursos son costosos mantener en uso (p. ej., los búferes de gran cantidad de memoria no administrada).</span><span class="sxs-lookup"><span data-stu-id="e41f9-118">The delay between when the developer could or would like to release the resource and the time when the resource is actually released by the finalizer might be unacceptable in programs that acquire many scarce resources (resources that can be easily exhausted) or in cases in which resources are costly to keep in use (e.g., large unmanaged memory buffers).</span></span>  
  
-   <span data-ttu-id="e41f9-119">Cuando el CLR necesita llamar a un finalizador, debe posponer esta acción de la memoria del objeto hasta que la siguiente de ida y vuelta de recolección de elementos (los finalizadores ejecutar entre colecciones).</span><span class="sxs-lookup"><span data-stu-id="e41f9-119">When the CLR needs to call a finalizer, it must postpone collection of the object’s memory until the next round of garbage collection (the finalizers run between collections).</span></span> <span data-ttu-id="e41f9-120">Esto significa que la memoria del objeto (y todos los objetos que se hace referencia a) no se disocie durante un período más largo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="e41f9-120">This means that the object’s memory (and all objects it refers to) will not be released for a longer period of time.</span></span>  
  
 <span data-ttu-id="e41f9-121">Por lo tanto, basarse exclusivamente en los finalizadores podría no ser apropiado en muchos escenarios cuando es importante reclamar los recursos no administrados lo más rápido posible, cuando se trabaja con recursos insuficientes, o en escenarios de alta un rendimiento superior en el que la sobrecarga adicional de GC de finalización no es aceptable.</span><span class="sxs-lookup"><span data-stu-id="e41f9-121">Therefore, relying exclusively on finalizers might not be appropriate in many scenarios when it is important to reclaim unmanaged resources as quickly as possible, when dealing with scarce resources, or in highly performant scenarios in which the added GC overhead of finalization is unacceptable.</span></span>  
  
 <span data-ttu-id="e41f9-122">El marco de trabajo proporciona el <xref:System.IDisposable?displayProperty=nameWithType> interfaz que debe implementarse para proporcionar a los programadores un método manual para liberar recursos no administrados como no son necesarios.</span><span class="sxs-lookup"><span data-stu-id="e41f9-122">The Framework provides the <xref:System.IDisposable?displayProperty=nameWithType> interface that should be implemented to provide the developer a manual way to release unmanaged resources as soon as they are not needed.</span></span> <span data-ttu-id="e41f9-123">También proporciona la <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> método que puede indicar el catálogo global que un objeto se ha eliminado manualmente y no necesita ser finalizados ya, en cuyo caso se puede reclamar la memoria del objeto anterior.</span><span class="sxs-lookup"><span data-stu-id="e41f9-123">It also provides the <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> method that can tell the GC that an object was manually disposed of and does not need to be finalized anymore, in which case the object’s memory can be reclaimed earlier.</span></span> <span data-ttu-id="e41f9-124">Los tipos que implementan la `IDisposable` interfaz se conocen como tipos descartables.</span><span class="sxs-lookup"><span data-stu-id="e41f9-124">Types that implement the `IDisposable` interface are referred to as disposable types.</span></span>  
  
 <span data-ttu-id="e41f9-125">El patrón Dispose está diseñado para estandarizar el uso y la implementación de los finalizadores y el `IDisposable` interfaz.</span><span class="sxs-lookup"><span data-stu-id="e41f9-125">The Dispose Pattern is intended to standardize the usage and implementation of finalizers and the `IDisposable` interface.</span></span>  
  
 <span data-ttu-id="e41f9-126">La motivación principal para el patrón es reducir la complejidad de la implementación de la <xref:System.Object.Finalize%2A> y <xref:System.IDisposable.Dispose%2A> métodos.</span><span class="sxs-lookup"><span data-stu-id="e41f9-126">The main motivation for the pattern is to reduce the complexity of the implementation of the <xref:System.Object.Finalize%2A> and the <xref:System.IDisposable.Dispose%2A> methods.</span></span> <span data-ttu-id="e41f9-127">La complejidad proviene del hecho de que los métodos comparten algunos, pero no todas las rutas de acceso de código (las diferencias se describen más adelante en el capítulo).</span><span class="sxs-lookup"><span data-stu-id="e41f9-127">The complexity stems from the fact that the methods share some but not all code paths (the differences are described later in the chapter).</span></span> <span data-ttu-id="e41f9-128">Además, existen motivos históricos para algunos de los elementos del modelo relacionados con la evolución de la compatibilidad de idioma para la administración de recursos determinista.</span><span class="sxs-lookup"><span data-stu-id="e41f9-128">In addition, there are historical reasons for some elements of the pattern related to the evolution of language support for deterministic resource management.</span></span>  
  
 <span data-ttu-id="e41f9-129">**✓ DO** implementar el patrón de Dispose básico en tipos que contiene instancias de los tipos descartables.</span><span class="sxs-lookup"><span data-stu-id="e41f9-129">**✓ DO** implement the Basic Dispose Pattern on types containing instances of disposable types.</span></span> <span data-ttu-id="e41f9-130">Consulte la [patrón de Dispose básico](#basic_pattern) sección para obtener más información sobre el patrón básico.</span><span class="sxs-lookup"><span data-stu-id="e41f9-130">See the [Basic Dispose Pattern](#basic_pattern) section for details on the basic pattern.</span></span>  
  
 <span data-ttu-id="e41f9-131">Si un tipo es responsable de la duración de otros objetos descartables, los desarrolladores necesitan una manera para deshacerse de ellos, demasiado.</span><span class="sxs-lookup"><span data-stu-id="e41f9-131">If a type is responsible for the lifetime of other disposable objects, developers need a way to dispose of them, too.</span></span> <span data-ttu-id="e41f9-132">Uso del contenedor `Dispose` método es una manera cómoda para que esto sea posible.</span><span class="sxs-lookup"><span data-stu-id="e41f9-132">Using the container’s `Dispose` method is a convenient way to make this possible.</span></span>  
  
 <span data-ttu-id="e41f9-133">**✓ DO** implementar el patrón Dispose básico y se proporciona un finalizador en tipos que contiene recursos que deben ser liberados explícitamente y que no tienen los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="e41f9-133">**✓ DO** implement the Basic Dispose Pattern and provide a finalizer on types holding resources that need to be freed explicitly and that do not have finalizers.</span></span>  
  
 <span data-ttu-id="e41f9-134">Por ejemplo, el modelo debe implementarse en tipos de almacenamiento de los búferes de memoria no administrada.</span><span class="sxs-lookup"><span data-stu-id="e41f9-134">For example, the pattern should be implemented on types storing unmanaged memory buffers.</span></span> <span data-ttu-id="e41f9-135">El [tipos susceptibles de finalización](#finalizable_types) sección describe directrices relacionadas con la implementación de los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="e41f9-135">The [Finalizable Types](#finalizable_types) section discusses guidelines related to implementing finalizers.</span></span>  
  
 <span data-ttu-id="e41f9-136">**✓ CONSIDER** implementar el patrón de Dispose básicas en las clases que ellos mismos no mantenga los recursos no administrados o los objetos descartables pero están probables que tienen subtipos que realizar.</span><span class="sxs-lookup"><span data-stu-id="e41f9-136">**✓ CONSIDER** implementing the Basic Dispose Pattern on classes that themselves don’t hold unmanaged resources or disposable objects but are likely to have subtypes that do.</span></span>  
  
 <span data-ttu-id="e41f9-137">Un buen ejemplo de esto es la <xref:System.IO.Stream?displayProperty=nameWithType> clase.</span><span class="sxs-lookup"><span data-stu-id="e41f9-137">A great example of this is the <xref:System.IO.Stream?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="e41f9-138">Aunque es una clase base abstracta que no contiene todos los recursos, no de la mayoría de sus subclases y por este motivo, implementa este patrón.</span><span class="sxs-lookup"><span data-stu-id="e41f9-138">Although it is an abstract base class that doesn’t hold any resources, most of its subclasses do and because of this, it implements this pattern.</span></span>  
  
<a name="basic_pattern"></a>   
## <a name="basic-dispose-pattern"></a><span data-ttu-id="e41f9-139">Patrón de Dispose básica</span><span class="sxs-lookup"><span data-stu-id="e41f9-139">Basic Dispose Pattern</span></span>  
 <span data-ttu-id="e41f9-140">La implementación básica del patrón, es preciso implementar la `System.IDisposable` interfaz y declarar la `Dispose(bool)` método que implementa la lógica de limpieza de todos los recursos que deban compartirse entre el `Dispose` método y el finalizador opcional.</span><span class="sxs-lookup"><span data-stu-id="e41f9-140">The basic implementation of the pattern involves implementing the `System.IDisposable` interface and declaring the `Dispose(bool)` method that implements all resource cleanup logic to be shared between the `Dispose` method and the optional finalizer.</span></span>  
  
 <span data-ttu-id="e41f9-141">En el ejemplo siguiente se muestra una implementación simple del patrón básico:</span><span class="sxs-lookup"><span data-stu-id="e41f9-141">The following example shows a simple implementation of the basic pattern:</span></span>  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
  
    private SafeHandle resource; // handle to a resource  
  
    public DisposableResourceHolder() {  
        this.resource = ... // allocates the resource  
    }  
  
    public void Dispose() {  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
  
    protected virtual void Dispose(bool disposing) {  
        if (disposing) {  
            if (resource!= null) resource.Dispose();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="e41f9-142">El parámetro booleano `disposing` indica si el método se invoca desde la `IDisposable.Dispose` implementación o desde el finalizador.</span><span class="sxs-lookup"><span data-stu-id="e41f9-142">The Boolean parameter `disposing` indicates whether the method was invoked from the `IDisposable.Dispose` implementation or from the finalizer.</span></span> <span data-ttu-id="e41f9-143">El `Dispose(bool)` implementación debe comprobar el parámetro antes de obtener acceso a otros objetos de referencia (por ejemplo, el campo de recursos en el ejemplo anterior).</span><span class="sxs-lookup"><span data-stu-id="e41f9-143">The `Dispose(bool)` implementation should check the parameter before accessing other reference objects (e.g., the resource field in the preceding sample).</span></span> <span data-ttu-id="e41f9-144">Solo se deben acceder a estos objetos cuando se llama al método desde el `IDisposable.Dispose` implementación (cuando el `disposing` parámetro es igual a true).</span><span class="sxs-lookup"><span data-stu-id="e41f9-144">Such objects should only be accessed when the method is called from the `IDisposable.Dispose` implementation (when the `disposing` parameter is equal to true).</span></span> <span data-ttu-id="e41f9-145">Si el método se invoca desde el finalizador (`disposing` es false), no se deben tener acceso a otros objetos.</span><span class="sxs-lookup"><span data-stu-id="e41f9-145">If the method is invoked from the finalizer (`disposing` is false), other objects should not be accessed.</span></span> <span data-ttu-id="e41f9-146">La razón es que los objetos se finalizan en un orden impredecible y por lo tanto, o cualquiera de sus dependencias, podría haber finalizado.</span><span class="sxs-lookup"><span data-stu-id="e41f9-146">The reason is that objects are finalized in an unpredictable order and so they, or any of their dependencies, might already have been finalized.</span></span>  
  
 <span data-ttu-id="e41f9-147">Además, esta sección se aplica a las clases con una base de que ya no implementan el patrón Dispose.</span><span class="sxs-lookup"><span data-stu-id="e41f9-147">Also, this section applies to classes with a base that does not already implement the Dispose Pattern.</span></span> <span data-ttu-id="e41f9-148">Si se hereda de una clase que ya implementa el patrón, invalide el `Dispose(bool)` método para proporcionar lógica de limpieza de recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="e41f9-148">If you are inheriting from a class that already implements the pattern, simply override the `Dispose(bool)` method to provide additional resource cleanup logic.</span></span>  
  
 <span data-ttu-id="e41f9-149">**✓ DO** declarar un `protected virtual void Dispose(bool disposing)` relacionado de método para centralizar toda la lógica para liberar recursos no administrados.</span><span class="sxs-lookup"><span data-stu-id="e41f9-149">**✓ DO** declare a `protected virtual void Dispose(bool disposing)` method to centralize all logic related to releasing unmanaged resources.</span></span>  
  
 <span data-ttu-id="e41f9-150">Todos los recursos deben limpiarse en este método.</span><span class="sxs-lookup"><span data-stu-id="e41f9-150">All resource cleanup should occur in this method.</span></span> <span data-ttu-id="e41f9-151">Se llama al método desde el finalizador de ambos y `IDisposable.Dispose` método.</span><span class="sxs-lookup"><span data-stu-id="e41f9-151">The method is called from both the finalizer and the `IDisposable.Dispose` method.</span></span> <span data-ttu-id="e41f9-152">El parámetro será false si se va a invocar desde dentro de un finalizador.</span><span class="sxs-lookup"><span data-stu-id="e41f9-152">The parameter will be false if being invoked from inside a finalizer.</span></span> <span data-ttu-id="e41f9-153">Se debe usar para asegurarse de que cualquier código que se ejecuta durante la finalización no se tiene acceso a otros objetos susceptibles de finalización.</span><span class="sxs-lookup"><span data-stu-id="e41f9-153">It should be used to ensure any code running during finalization is not accessing other finalizable objects.</span></span> <span data-ttu-id="e41f9-154">Detalles de la implementación de los finalizadores se describen en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="e41f9-154">Details of implementing finalizers are described in the next section.</span></span>  
  
```csharp
protected virtual void Dispose(bool disposing) {  
    if (disposing) {  
        if (resource!= null) resource.Dispose();  
    }  
}  
```  
  
 <span data-ttu-id="e41f9-155">**✓ DO** implementar la `IDisposable` interfaz llamando simplemente `Dispose(true)` seguido de `GC.SuppressFinalize(this)`.</span><span class="sxs-lookup"><span data-stu-id="e41f9-155">**✓ DO** implement the `IDisposable` interface by simply calling `Dispose(true)` followed by `GC.SuppressFinalize(this)`.</span></span>  
  
 <span data-ttu-id="e41f9-156">La llamada a `SuppressFinalize` solo deberían producirse si `Dispose(true)` se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="e41f9-156">The call to `SuppressFinalize` should only occur if `Dispose(true)` executes successfully.</span></span>  
  
```csharp
public void Dispose(){  
    Dispose(true);  
    GC.SuppressFinalize(this);  
}  
```  
  
 <span data-ttu-id="e41f9-157">**X DO NOT** realizar sin parámetros `Dispose` método virtual.</span><span class="sxs-lookup"><span data-stu-id="e41f9-157">**X DO NOT** make the parameterless `Dispose` method virtual.</span></span>  
  
 <span data-ttu-id="e41f9-158">El `Dispose(bool)` método es el que debe reemplazarse por las subclases.</span><span class="sxs-lookup"><span data-stu-id="e41f9-158">The `Dispose(bool)` method is the one that should be overridden by subclasses.</span></span>  
  
```csharp
// bad design  
public class DisposableResourceHolder : IDisposable {  
    public virtual void Dispose() { ... }  
    protected virtual void Dispose(bool disposing) { ... }  
}  
  
// good design  
public class DisposableResourceHolder : IDisposable {  
    public void Dispose() { ... }  
    protected virtual void Dispose(bool disposing) { ... }  
}  
```  
  
 <span data-ttu-id="e41f9-159">**X DO NOT** declarar las sobrecargas de la `Dispose` otro método que `Dispose()` y `Dispose(bool)`.</span><span class="sxs-lookup"><span data-stu-id="e41f9-159">**X DO NOT** declare any overloads of the `Dispose` method other than `Dispose()` and `Dispose(bool)`.</span></span>  
  
 <span data-ttu-id="e41f9-160">`Dispose` debe considerarse una palabra reservada para ayudar a codificar este patrón y evitar la confusión entre los implementadores y los usuarios, los compiladores.</span><span class="sxs-lookup"><span data-stu-id="e41f9-160">`Dispose` should be considered a reserved word to help codify this pattern and prevent confusion among implementers, users, and compilers.</span></span> <span data-ttu-id="e41f9-161">Algunos lenguajes pueden optar por implementar automáticamente este patrón de determinados tipos.</span><span class="sxs-lookup"><span data-stu-id="e41f9-161">Some languages might choose to automatically implement this pattern on certain types.</span></span>  
  
 <span data-ttu-id="e41f9-162">**✓ DO** permitir la `Dispose(bool)` método al que llamar más de una vez.</span><span class="sxs-lookup"><span data-stu-id="e41f9-162">**✓ DO** allow the `Dispose(bool)` method to be called more than once.</span></span> <span data-ttu-id="e41f9-163">El método puede optar por no hacer nada después de la primera llamada.</span><span class="sxs-lookup"><span data-stu-id="e41f9-163">The method might choose to do nothing after the first call.</span></span>  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
  
    bool disposed = false;  
  
    protected virtual void Dispose(bool disposing) {  
        if (disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 <span data-ttu-id="e41f9-164">**X AVOID** producir una excepción desde `Dispose(bool)` excepto en situaciones críticas que se ha dañado el proceso que lo contiene (pérdidas, un estado compartido incoherente, etcetera).</span><span class="sxs-lookup"><span data-stu-id="e41f9-164">**X AVOID** throwing an exception from within `Dispose(bool)` except under critical situations where the containing process has been corrupted (leaks, inconsistent shared state, etc.).</span></span>  
  
 <span data-ttu-id="e41f9-165">Los usuarios esperan que una llamada a `Dispose` no generará una excepción.</span><span class="sxs-lookup"><span data-stu-id="e41f9-165">Users expect that a call to `Dispose` will not raise an exception.</span></span>  
  
 <span data-ttu-id="e41f9-166">Si `Dispose` podría producir una excepción, no se ejecutará más lógica de limpieza del bloque finally.</span><span class="sxs-lookup"><span data-stu-id="e41f9-166">If `Dispose` could raise an exception, further finally-block cleanup logic will not execute.</span></span> <span data-ttu-id="e41f9-167">Para resolver este problema, el usuario necesitaría ajustar todas las llamadas a `Dispose` (en el bloque finally!) en un bloque try, lo que conduce a controladores de limpieza muy complejos.</span><span class="sxs-lookup"><span data-stu-id="e41f9-167">To work around this, the user would need to wrap every call to `Dispose` (within the finally block!) in a try block, which leads to very complex cleanup handlers.</span></span> <span data-ttu-id="e41f9-168">Si ejecuta un `Dispose(bool disposing)` método, nunca inician una excepción si la eliminación es false.</span><span class="sxs-lookup"><span data-stu-id="e41f9-168">If executing a `Dispose(bool disposing)` method, never throw an exception if disposing is false.</span></span> <span data-ttu-id="e41f9-169">Si lo hace, se terminará el proceso si la ejecución dentro de un contexto de finalizador.</span><span class="sxs-lookup"><span data-stu-id="e41f9-169">Doing so will terminate the process if executing inside a finalizer context.</span></span>  
  
 <span data-ttu-id="e41f9-170">**✓ DO** producir una <xref:System.ObjectDisposedException> de cualquier miembro que no se puede utilizar una vez que se ha eliminado el objeto.</span><span class="sxs-lookup"><span data-stu-id="e41f9-170">**✓ DO** throw an <xref:System.ObjectDisposedException> from any member that cannot be used after the object has been disposed of.</span></span>  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
    bool disposed = false;  
    SafeHandle resource; // handle to a resource  
  
    public void DoSomething() {  
        if (disposed) throw new ObjectDisposedException(...);  
        // now call some native methods using the resource   
        ...  
    }  
    protected virtual void Dispose(bool disposing) {  
        if (disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 <span data-ttu-id="e41f9-171">**✓ CONSIDER** proporciona el método `Close()`, además el `Dispose()`, si es cerrar terminología estándar en el área.</span><span class="sxs-lookup"><span data-stu-id="e41f9-171">**✓ CONSIDER** providing method `Close()`, in addition to the `Dispose()`, if close is standard terminology in the area.</span></span>  
  
 <span data-ttu-id="e41f9-172">Al hacerlo, es importante que realice la `Close` idéntico de la implementación `Dispose` y considere implementar la `IDisposable.Dispose` método explícitamente.</span><span class="sxs-lookup"><span data-stu-id="e41f9-172">When doing so, it is important that you make the `Close` implementation identical to `Dispose` and consider implementing the `IDisposable.Dispose` method explicitly.</span></span>  
  
```csharp
public class Stream : IDisposable {  
    IDisposable.Dispose() {  
        Close();  
    }  
    public void Close() {  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
<a name="finalizable_types"></a>   
## <a name="finalizable-types"></a><span data-ttu-id="e41f9-173">Tipos susceptibles de finalización</span><span class="sxs-lookup"><span data-stu-id="e41f9-173">Finalizable Types</span></span>  
 <span data-ttu-id="e41f9-174">Los tipos susceptibles de finalización son tipos que extienden el patrón Dispose básico reemplazando el finalizador y proporcionar la ruta de acceso de código de finalización en la `Dispose(bool)` método.</span><span class="sxs-lookup"><span data-stu-id="e41f9-174">Finalizable types are types that extend the Basic Dispose Pattern by overriding the finalizer and providing finalization code path in the `Dispose(bool)` method.</span></span>  
  
 <span data-ttu-id="e41f9-175">Los finalizadores son considerablemente difíciles de implementar correctamente, principalmente porque no se realizan determinadas suposiciones (suele ser válidos) sobre el estado del sistema durante su ejecución.</span><span class="sxs-lookup"><span data-stu-id="e41f9-175">Finalizers are notoriously difficult to implement correctly, primarily because you cannot make certain (normally valid) assumptions about the state of the system during their execution.</span></span> <span data-ttu-id="e41f9-176">Las instrucciones siguientes deben tenerse en consideración cuidadosa.</span><span class="sxs-lookup"><span data-stu-id="e41f9-176">The following guidelines should be taken into careful consideration.</span></span>  
  
 <span data-ttu-id="e41f9-177">Tenga en cuenta que algunas de las instrucciones se aplican no solo a los `Finalize` (método), pero en cualquier código llamar desde un finalizador.</span><span class="sxs-lookup"><span data-stu-id="e41f9-177">Note that some of the guidelines apply not just to the `Finalize` method, but to any code called from a finalizer.</span></span> <span data-ttu-id="e41f9-178">En el caso del Dispose patrón básico definido anteriormente, esto significa lógica que se ejecute dentro de `Dispose(bool disposing)` cuando el `disposing` del parámetro es false.</span><span class="sxs-lookup"><span data-stu-id="e41f9-178">In the case of the Basic Dispose Pattern previously defined, this means logic that executes inside `Dispose(bool disposing)` when the `disposing` parameter is false.</span></span>  
  
 <span data-ttu-id="e41f9-179">Si la clase base ya está susceptibles de finalización e implementa el patrón Dispose básico, no debe invalidar `Finalize` nuevo.</span><span class="sxs-lookup"><span data-stu-id="e41f9-179">If the base class already is finalizable and implements the Basic Dispose Pattern, you should not override `Finalize` again.</span></span> <span data-ttu-id="e41f9-180">En su lugar, debería invalidar simplemente la `Dispose(bool)` método para proporcionar lógica de limpieza de recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="e41f9-180">You should instead just override the `Dispose(bool)` method to provide additional resource cleanup logic.</span></span>  
  
 <span data-ttu-id="e41f9-181">El código siguiente muestra un ejemplo de un tipo susceptibles de finalización:</span><span class="sxs-lookup"><span data-stu-id="e41f9-181">The following code shows an example of a finalizable type:</span></span>  
  
```csharp
public class ComplexResourceHolder : IDisposable {  
  
    private IntPtr buffer; // unmanaged memory buffer  
    private SafeHandle resource; // disposable handle to a resource  
  
    public ComplexResourceHolder() {  
        this.buffer = ... // allocates memory  
        this.resource = ... // allocates the resource  
    }  
  
    protected virtual void Dispose(bool disposing) {  
            ReleaseBuffer(buffer); // release unmanaged memory  
        if (disposing) { // release other disposable objects  
            if (resource!= null) resource.Dispose();  
        }  
    }  
  
    ~ComplexResourceHolder() {
        Dispose(false);  
    }  
  
    public void Dispose() {
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
 <span data-ttu-id="e41f9-182">**X AVOID** realicen tipos susceptibles de finalización.</span><span class="sxs-lookup"><span data-stu-id="e41f9-182">**X AVOID** making types finalizable.</span></span>  
  
 <span data-ttu-id="e41f9-183">Tenga en cuenta todos los casos en que cree que es necesario un finalizador.</span><span class="sxs-lookup"><span data-stu-id="e41f9-183">Carefully consider any case in which you think a finalizer is needed.</span></span> <span data-ttu-id="e41f9-184">Hay un número real los costos asociados con instancias con los finalizadores, desde la perspectiva de complejidad de un código y el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="e41f9-184">There is a real cost associated with instances with finalizers, from both a performance and code complexity standpoint.</span></span> <span data-ttu-id="e41f9-185">Prefiere con contenedores de recursos como <xref:System.Runtime.InteropServices.SafeHandle> para encapsular los recursos no administrados que siempre que sea posible, en cuyo caso un finalizador se convierte en innecesario porque el contenedor es responsable de su propia limpieza de recursos.</span><span class="sxs-lookup"><span data-stu-id="e41f9-185">Prefer using resource wrappers such as <xref:System.Runtime.InteropServices.SafeHandle> to encapsulate unmanaged resources where possible, in which case a finalizer becomes unnecessary because the wrapper is responsible for its own resource cleanup.</span></span>  
  
 <span data-ttu-id="e41f9-186">**X DO NOT** que los tipos de valor susceptibles de finalización.</span><span class="sxs-lookup"><span data-stu-id="e41f9-186">**X DO NOT** make value types finalizable.</span></span>  
  
 <span data-ttu-id="e41f9-187">Solo los tipos de referencia realmente obtengan finalizados CLR y, por tanto, se pasará por alto cualquier intento para colocar un finalizador en un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="e41f9-187">Only reference types actually get finalized by the CLR, and thus any attempt to place a finalizer on a value type will be ignored.</span></span> <span data-ttu-id="e41f9-188">Los compiladores de C++ y C# aplican esta regla.</span><span class="sxs-lookup"><span data-stu-id="e41f9-188">The C# and C++ compilers enforce this rule.</span></span>  
  
 <span data-ttu-id="e41f9-189">**✓ DO** que un tipo susceptibles de finalización si el tipo es responsable de liberar un recurso no administrado que no tiene su propio finalizador.</span><span class="sxs-lookup"><span data-stu-id="e41f9-189">**✓ DO** make a type finalizable if the type is responsible for releasing an unmanaged resource that does not have its own finalizer.</span></span>  
  
 <span data-ttu-id="e41f9-190">Al implementar el finalizador, basta con llamar a `Dispose(false)` y coloque toda la lógica de limpieza de recursos dentro de la `Dispose(bool disposing)` método.</span><span class="sxs-lookup"><span data-stu-id="e41f9-190">When implementing the finalizer, simply call `Dispose(false)` and place all resource cleanup logic inside the `Dispose(bool disposing)` method.</span></span>  
  
```csharp
public class ComplexResourceHolder : IDisposable {  
  
    ~ComplexResourceHolder() {
        Dispose(false);  
    }  
  
    protected virtual void Dispose(bool disposing) {
        ...  
    }  
}  
```  
  
 <span data-ttu-id="e41f9-191">**✓ DO** implementar el patrón de Dispose básico en todos los tipos susceptibles de finalización.</span><span class="sxs-lookup"><span data-stu-id="e41f9-191">**✓ DO** implement the Basic Dispose Pattern on every finalizable type.</span></span>  
  
 <span data-ttu-id="e41f9-192">Esto proporciona a los usuarios del tipo de medio para realizar explícitamente una limpieza determinista de los mismos recursos que es responsable el finalizador.</span><span class="sxs-lookup"><span data-stu-id="e41f9-192">This gives users of the type a means to explicitly perform deterministic cleanup of those same resources for which the finalizer is responsible.</span></span>  
  
 <span data-ttu-id="e41f9-193">**X DO NOT** tener acceso a los objetos susceptibles de finalización en la ruta de acceso del código de finalizador, porque no hay riesgo significativo que ya habrá finalizados.</span><span class="sxs-lookup"><span data-stu-id="e41f9-193">**X DO NOT** access any finalizable objects in the finalizer code path, because there is significant risk that they will have already been finalized.</span></span>  
  
 <span data-ttu-id="e41f9-194">Por ejemplo, un objeto susceptible de finalización A que tiene una referencia a otro objeto susceptibles de finalización B confiable no puede usar B en del finalizador, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="e41f9-194">For example, a finalizable object A that has a reference to another finalizable object B cannot reliably use B in A’s finalizer, or vice versa.</span></span> <span data-ttu-id="e41f9-195">Los finalizadores se llaman en orden aleatorio (aparte de una garantía de ordenación débil de finalización crítica).</span><span class="sxs-lookup"><span data-stu-id="e41f9-195">Finalizers are called in a random order (short of a weak ordering guarantee for critical finalization).</span></span>  
  
 <span data-ttu-id="e41f9-196">Además, tenga en cuenta que estos objetos almacenados en variables estáticas se se recopilan en ciertos puntos durante una descarga del dominio de aplicación o al salir del proceso.</span><span class="sxs-lookup"><span data-stu-id="e41f9-196">Also, be aware that objects stored in static variables will get collected at certain points during an application domain unload or while exiting the process.</span></span> <span data-ttu-id="e41f9-197">Obtener acceso a una variable estática que hace referencia a un objeto susceptible de finalización (o llamar a un método estático que puedan usar los valores almacenados en variables estáticas) podría no ser seguro if <xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType> devuelve true.</span><span class="sxs-lookup"><span data-stu-id="e41f9-197">Accessing a static variable that refers to a finalizable object (or calling a static method that might use values stored in static variables) might not be safe if <xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType> returns true.</span></span>  
  
 <span data-ttu-id="e41f9-198">**✓ DO** realizar su `Finalize` método protegido.</span><span class="sxs-lookup"><span data-stu-id="e41f9-198">**✓ DO** make your `Finalize` method protected.</span></span>  
  
 <span data-ttu-id="e41f9-199">Los desarrolladores de C#, C++ y VB.NET no tiene que preocuparse sobre esto, porque los compiladores de ayudan a aplicar esta directriz.</span><span class="sxs-lookup"><span data-stu-id="e41f9-199">C#, C++, and VB.NET developers do not need to worry about this, because the compilers help to enforce this guideline.</span></span>  
  
 <span data-ttu-id="e41f9-200">**X DO NOT** escape permiten excepciones de la lógica de finalizador, excepto los errores críticos del sistema.</span><span class="sxs-lookup"><span data-stu-id="e41f9-200">**X DO NOT** let exceptions escape from the finalizer logic, except for system-critical failures.</span></span>  
  
 <span data-ttu-id="e41f9-201">Si se produce una excepción de un finalizador, el CLR se apagará de todo el proceso (a partir de .NET Framework versión 2.0), impide que otros finalizadores ejecutar y recursos de que se liberan de una manera controlada.</span><span class="sxs-lookup"><span data-stu-id="e41f9-201">If an exception is thrown from a finalizer, the CLR will shut down the entire process (as of .NET Framework version 2.0), preventing other finalizers from executing and resources from being released in a controlled manner.</span></span>  
  
 <span data-ttu-id="e41f9-202">**✓ CONSIDER** crear y usar un objeto susceptibles de finalización crítico (un tipo con una jerarquía de tipos que contiene <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) para situaciones en que un finalizador absolutamente debe ejecutar incluso frente a la fuerza del dominio de aplicación forzada y subprocesos se anula.</span><span class="sxs-lookup"><span data-stu-id="e41f9-202">**✓ CONSIDER** creating and using a critical finalizable object (a type with a type hierarchy that contains <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) for situations in which a finalizer absolutely must execute even in the face of forced application domain unloads and thread aborts.</span></span>  
  
 <span data-ttu-id="e41f9-203">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="e41f9-203">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e41f9-204">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="e41f9-204">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e41f9-205">Vea también</span><span class="sxs-lookup"><span data-stu-id="e41f9-205">See Also</span></span>  
 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="e41f9-206">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e41f9-206">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="e41f9-207">Patrones de diseño comunes</span><span class="sxs-lookup"><span data-stu-id="e41f9-207">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 [<span data-ttu-id="e41f9-208">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="e41f9-208">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
