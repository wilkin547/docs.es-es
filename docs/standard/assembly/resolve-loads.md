---
title: Resolución de cargas de ensamblado
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], resolving loads
- application domains, loading assemblies
- resolving assembly loads
- assemblies [.NET Framework], loading
- application domains, resolving assembly loads
ms.assetid: 5099e549-f4fd-49fb-a290-549edd456c6a
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: d6314fae266505fbb4410aaaa351973070ab3811
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156444"
---
# <a name="resolve-assembly-loads"></a><span data-ttu-id="3b09e-102">Resolución de cargas de ensamblado</span><span class="sxs-lookup"><span data-stu-id="3b09e-102">Resolve assembly loads</span></span>
<span data-ttu-id="3b09e-103">.NET proporciona el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> para aplicaciones que requieren un mayor control sobre la carga de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3b09e-103">.NET provides the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event for applications that require greater control over assembly loading.</span></span> <span data-ttu-id="3b09e-104">Al controlar este evento, la aplicación puede cargar un ensamblado en el contexto de carga desde fuera de las rutas de acceso de sondeo normales, seleccionar qué versión de ensamblado cargar, emitir un ensamblado dinámico y devolverlo, etc.</span><span class="sxs-lookup"><span data-stu-id="3b09e-104">By handling this event, your application can load an assembly into the load context from outside the normal probing paths, select which of several assembly versions to load, emit a dynamic assembly and return it, and so on.</span></span> <span data-ttu-id="3b09e-105">En este tema se proporcionan instrucciones para controlar el evento <xref:System.AppDomain.AssemblyResolve>.</span><span class="sxs-lookup"><span data-stu-id="3b09e-105">This topic provides guidance for handling the <xref:System.AppDomain.AssemblyResolve> event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3b09e-106">Para resolver cargas de ensamblado en el contexto de solo reflexión, use en su lugar el evento <xref:System.AppDomain.ReflectionOnlyAssemblyResolve?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3b09e-106">For resolving assembly loads in the reflection-only context, use the <xref:System.AppDomain.ReflectionOnlyAssemblyResolve?displayProperty=nameWithType> event instead.</span></span>  
  
## <a name="how-the-assemblyresolve-event-works"></a><span data-ttu-id="3b09e-107">Cómo funciona el evento AssemblyResolve</span><span class="sxs-lookup"><span data-stu-id="3b09e-107">How the AssemblyResolve event works</span></span>  
 <span data-ttu-id="3b09e-108">Al registrar un controlador para el evento <xref:System.AppDomain.AssemblyResolve>, se invoca el controlador si se produce un error cuando el tiempo de ejecución enlaza a un ensamblado por nombre.</span><span class="sxs-lookup"><span data-stu-id="3b09e-108">When you register a handler for the <xref:System.AppDomain.AssemblyResolve> event, the handler is invoked whenever the runtime fails to bind to an assembly by name.</span></span> <span data-ttu-id="3b09e-109">Por ejemplo, si se llama a los métodos siguientes desde el código de usuario, puede producirse el evento <xref:System.AppDomain.AssemblyResolve>:</span><span class="sxs-lookup"><span data-stu-id="3b09e-109">For example, calling the following methods from user code can cause the <xref:System.AppDomain.AssemblyResolve> event to be raised:</span></span>  
  
- <span data-ttu-id="3b09e-110">Una sobrecarga del método <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> o una sobrecarga del método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> cuyo primer argumento es una cadena que representa el nombre para mostrar del ensamblado que se va a cargar (es decir, la cadena devuelta por la propiedad <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="3b09e-110">An <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> method overload or <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method overload whose first argument is a string that represents the display name of the assembly to load (that is, the string returned by the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property).</span></span>  
  
- <span data-ttu-id="3b09e-111">Una sobrecarga del método <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> o una sobrecarga del método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> cuyo primer argumento es un objeto <xref:System.Reflection.AssemblyName> que identifica el ensamblado que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="3b09e-111">An <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> method overload or <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method overload whose first argument is an <xref:System.Reflection.AssemblyName> object that identifies the assembly to load.</span></span>  
  
- <span data-ttu-id="3b09e-112">Una sobrecarga del método <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3b09e-112">An <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType> method overload.</span></span>  
  
- <span data-ttu-id="3b09e-113">Una sobrecarga del método <xref:System.AppDomain.CreateInstance%2A?displayProperty=nameWithType> o <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType> que crea instancias de un objeto en otro dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3b09e-113">An <xref:System.AppDomain.CreateInstance%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType> method overload that instantiates an object in another application domain.</span></span>  
  
### <a name="what-the-event-handler-does"></a><span data-ttu-id="3b09e-114">Qué hace el controlador de eventos</span><span class="sxs-lookup"><span data-stu-id="3b09e-114">What the event handler does</span></span>  
 <span data-ttu-id="3b09e-115">El controlador del evento <xref:System.AppDomain.AssemblyResolve> recibe el nombre para mostrar del ensamblado que se va a cargar, en la propiedad <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3b09e-115">The handler for the <xref:System.AppDomain.AssemblyResolve> event receives the display name of the assembly to be loaded, in the <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="3b09e-116">Si el controlador no reconoce el nombre del ensamblado, devuelve `null` (C#), `Nothing` (Visual Basic) o `nullptr` (Visual C++).</span><span class="sxs-lookup"><span data-stu-id="3b09e-116">If the handler does not recognize the assembly name, it returns `null` (C#), `Nothing` (Visual Basic), or `nullptr` (Visual C++).</span></span>  
  
 <span data-ttu-id="3b09e-117">Si el controlador reconoce el nombre del ensamblado, puede cargar y devolver un ensamblado que cumpla la solicitud.</span><span class="sxs-lookup"><span data-stu-id="3b09e-117">If the handler recognizes the assembly name, it can load and return an assembly that satisfies the request.</span></span> <span data-ttu-id="3b09e-118">En la lista siguiente se describen algunos escenarios de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3b09e-118">The following list describes some sample scenarios.</span></span>  
  
- <span data-ttu-id="3b09e-119">Si el controlador conoce la ubicación de una versión del ensamblado, puede cargar el ensamblado mediante el método <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType> y devolver el ensamblado cargado si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="3b09e-119">If the handler knows the location of a version of the assembly, it can load the assembly by using the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType> method, and can return the loaded assembly if successful.</span></span>  
  
- <span data-ttu-id="3b09e-120">Si el controlador tiene acceso a una base de datos de los ensamblados almacenados como matrices de bytes, puede cargar una matriz de bytes mediante una de las sobrecargas del método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> que toman una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="3b09e-120">If the handler has access to a database of assemblies stored as byte arrays, it can load a byte array by using one of the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method overloads that take a byte array.</span></span>  
  
- <span data-ttu-id="3b09e-121">El controlador puede generar un ensamblado dinámico y devolverlo.</span><span class="sxs-lookup"><span data-stu-id="3b09e-121">The handler can generate a dynamic assembly and return it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3b09e-122">El controlador debe cargar el ensamblado en el contexto de origen de carga, en el contexto de carga o sin contexto. Si el controlador carga el ensamblado en el contexto de solo reflexión mediante el método <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType>, se produce un error en el intento de carga que ha provocado el evento <xref:System.AppDomain.AssemblyResolve>.</span><span class="sxs-lookup"><span data-stu-id="3b09e-122">The handler must load the assembly into the load-from context, into the load context, or without context.If the handler loads the assembly into the reflection-only context by using the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> or the <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType> method, the load attempt that raised the <xref:System.AppDomain.AssemblyResolve> event fails.</span></span>  
  
 <span data-ttu-id="3b09e-123">El controlador de eventos se encarga de devolver un ensamblado adecuado.</span><span class="sxs-lookup"><span data-stu-id="3b09e-123">It is the responsibility of the event handler to return a suitable assembly.</span></span> <span data-ttu-id="3b09e-124">El controlador puede analizar el nombre para mostrar del ensamblado solicitado. Para ello, pasa el valor de propiedad <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType> al constructor <xref:System.Reflection.AssemblyName.%23ctor%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="3b09e-124">The handler can parse the display name of the requested assembly by passing the <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType> property value to the <xref:System.Reflection.AssemblyName.%23ctor%28System.String%29> constructor.</span></span> <span data-ttu-id="3b09e-125">A partir de .NET Framework 4, el controlador puede usar la propiedad <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> para determinar si la solicitud actual es una dependencia de otro ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3b09e-125">Beginning with the .NET Framework 4, the handler can use the <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> property to determine whether the current request is a dependency of another assembly.</span></span> <span data-ttu-id="3b09e-126">Esta información puede ayudar a identificar un ensamblado que cumplirá la dependencia.</span><span class="sxs-lookup"><span data-stu-id="3b09e-126">This information can help identify an assembly that will satisfy the dependency.</span></span>  
  
 <span data-ttu-id="3b09e-127">El controlador de eventos puede devolver una versión del ensamblado diferente de la versión solicitada.</span><span class="sxs-lookup"><span data-stu-id="3b09e-127">The event handler can return a different version of the assembly than the version that was requested.</span></span>  
  
 <span data-ttu-id="3b09e-128">En la mayoría de los casos, el ensamblado que el controlador devuelve aparece en el contexto de carga, independientemente del contexto en el que lo carga el controlador.</span><span class="sxs-lookup"><span data-stu-id="3b09e-128">In most cases, the assembly that is returned by the handler appears in the load context, regardless of the context the handler loads it into.</span></span> <span data-ttu-id="3b09e-129">Por ejemplo, si el controlador usa el método <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> para cargar un ensamblado en el contexto de origen de carga, el ensamblado aparece en el contexto de carga cuando el controlador lo devuelve.</span><span class="sxs-lookup"><span data-stu-id="3b09e-129">For example, if the handler uses the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method to load an assembly into the load-from context, the assembly appears in the load context when the handler returns it.</span></span> <span data-ttu-id="3b09e-130">Pero en el caso siguiente, el ensamblado aparece sin contexto cuando el controlador lo devuelve:</span><span class="sxs-lookup"><span data-stu-id="3b09e-130">However, in the following case the assembly appears without context when the handler returns it:</span></span>  
  
- <span data-ttu-id="3b09e-131">El controlador carga un ensamblado sin contexto.</span><span class="sxs-lookup"><span data-stu-id="3b09e-131">The handler loads an assembly without context.</span></span>  
  
- <span data-ttu-id="3b09e-132">La propiedad <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> no es NULL.</span><span class="sxs-lookup"><span data-stu-id="3b09e-132">The <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> property is not null.</span></span>  
  
- <span data-ttu-id="3b09e-133">El ensamblado solicitante (es decir, el ensamblado devuelto por la propiedad <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType>) se ha cargado sin contexto.</span><span class="sxs-lookup"><span data-stu-id="3b09e-133">The requesting assembly (that is, the assembly that is returned by the <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> property) was loaded without context.</span></span>  
  
 <span data-ttu-id="3b09e-134">Para obtener información sobre los contextos, vea la sobrecarga del método <xref:System.Reflection.Assembly.LoadFrom%28System.String%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3b09e-134">For information about contexts, see the <xref:System.Reflection.Assembly.LoadFrom%28System.String%29?displayProperty=nameWithType> method overload.</span></span>  
  
 <span data-ttu-id="3b09e-135">Es posible cargar varias versiones del mismo ensamblado en el mismo dominio de aplicación,</span><span class="sxs-lookup"><span data-stu-id="3b09e-135">Multiple versions of the same assembly can be loaded into the same application domain.</span></span> <span data-ttu-id="3b09e-136">pero esta práctica no se recomienda porque puede provocar problemas de asignación de tipos.</span><span class="sxs-lookup"><span data-stu-id="3b09e-136">This practice is not recommended, because it can lead to type assignment problems.</span></span> <span data-ttu-id="3b09e-137">Vea [Procedimientos recomendados para cargar ensamblados](../../framework/deployment/best-practices-for-assembly-loading.md).</span><span class="sxs-lookup"><span data-stu-id="3b09e-137">See [Best practices for assembly loading](../../framework/deployment/best-practices-for-assembly-loading.md).</span></span>  
  
### <a name="what-the-event-handler-should-not-do"></a><span data-ttu-id="3b09e-138">Qué no debe hacer el controlador de eventos</span><span class="sxs-lookup"><span data-stu-id="3b09e-138">What the event handler should not do</span></span>  
<span data-ttu-id="3b09e-139">La regla principal que debe observar para controlar el evento <xref:System.AppDomain.AssemblyResolve> es que no debe intentar devolver un ensamblado que no reconozca.</span><span class="sxs-lookup"><span data-stu-id="3b09e-139">The primary rule for handling the <xref:System.AppDomain.AssemblyResolve> event is that you should not try to return an assembly you do not recognize.</span></span> <span data-ttu-id="3b09e-140">Cuando se escribe el controlador, debe saber qué ensamblados pueden hacer que se produzca el evento.</span><span class="sxs-lookup"><span data-stu-id="3b09e-140">When you write the handler, you should know which assemblies might cause the event to be raised.</span></span> <span data-ttu-id="3b09e-141">El controlador debe devolver NULL para otros ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3b09e-141">Your handler should return null for other assemblies.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="3b09e-142">A partir de .NET Framework 4, se genera el evento <xref:System.AppDomain.AssemblyResolve> para los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="3b09e-142">Beginning with the .NET Framework 4, the <xref:System.AppDomain.AssemblyResolve> event is raised for satellite assemblies.</span></span> <span data-ttu-id="3b09e-143">Este cambio afecta a los controladores de eventos escritos para versiones anteriores de .NET Framework si intentan resolver todas las solicitudes de carga del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3b09e-143">This change affects an event handler that was written for an earlier version of the .NET Framework, if the handler tries to resolve all assembly load requests.</span></span> <span data-ttu-id="3b09e-144">Los controladores de eventos que omiten los ensamblados que no reconocen no se ven afectados por este cambio: devuelven NULL y se siguen los mecanismos normales de reserva.</span><span class="sxs-lookup"><span data-stu-id="3b09e-144">Event handlers that ignore assemblies they do not recognize are not affected by this change: They return null, and normal fallback mechanisms are followed.</span></span>  

<span data-ttu-id="3b09e-145">Al cargar un ensamblado, el controlador de eventos no debe usar las sobrecargas del método <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> que pueden hacer que se produzca el evento <xref:System.AppDomain.AssemblyResolve> de forma recursiva, ya que esto puede provocar un desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="3b09e-145">When loading an assembly, the event handler must not use any of the <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method overloads that can cause the <xref:System.AppDomain.AssemblyResolve> event to be raised recursively, because this can lead to a stack overflow.</span></span> <span data-ttu-id="3b09e-146">(Vea la lista proporcionada anteriormente en este tema). Esto ocurre incluso si proporciona el control de excepciones para la solicitud de carga, porque no se produce ninguna excepción hasta que se hayan devuelto todos los controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="3b09e-146">(See the list provided earlier in this topic.) This happens even if you provide exception handling for the load request, because no exception is thrown until all event handlers have returned.</span></span> <span data-ttu-id="3b09e-147">Así pues, el código siguiente produce un desbordamiento de pila si no se encuentra `MyAssembly`:</span><span class="sxs-lookup"><span data-stu-id="3b09e-147">Thus, the following code results in a stack overflow if `MyAssembly` is not found:</span></span>  

```cpp
using namespace System;
using namespace System::Reflection;

ref class Example
{
internal:
    static Assembly^ MyHandler(Object^ source, ResolveEventArgs^ e)
    {
        Console::WriteLine("Resolving {0}", e->Name);
        return Assembly::Load(e->Name);
    }
};

void main()
{
    AppDomain^ ad = AppDomain::CreateDomain("Test");
    ad->AssemblyResolve += gcnew ResolveEventHandler(&Example::MyHandler);

    try
    {
        Object^ obj = ad->CreateInstanceAndUnwrap(
            "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
            "MyType");
    }
    catch (Exception^ ex)
    {
        Console::WriteLine(ex->Message);
    }
}

/* This example produces output similar to the following:

Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
...
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null

Process is terminated due to StackOverflowException.
 */
```

```csharp
using System;
using System.Reflection;

class BadExample
{
    static void Main()
    {
        AppDomain ad = AppDomain.CreateDomain("Test");
        ad.AssemblyResolve += MyHandler;

        try
        {
            object obj = ad.CreateInstanceAndUnwrap(
                "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
                "MyType");
        }
        catch (Exception ex)
        {
            Console.WriteLine(ex.Message);
        }
    }

    static Assembly MyHandler(object source, ResolveEventArgs e)
    {
        Console.WriteLine("Resolving {0}", e.Name);
        return Assembly.Load(e.Name);
    }
}

/* This example produces output similar to the following:

Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
...
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null

Process is terminated due to StackOverflowException.
 */
```

```vb
Imports System.Reflection

Class BadExample

    Shared Sub Main()

        Dim ad As AppDomain = AppDomain.CreateDomain("Test")
        AddHandler ad.AssemblyResolve, AddressOf MyHandler

        Try
            Dim obj As object = ad.CreateInstanceAndUnwrap(
                "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
                "MyType")
        Catch ex As Exception
            Console.WriteLine(ex.Message)
        End Try
    End Sub

    Shared Function MyHandler(ByVal source As Object, _
                              ByVal e As ResolveEventArgs) As Assembly
        Console.WriteLine("Resolving {0}", e.Name)
        Return Assembly.Load(e.Name)
    End Function
End Class

' This example produces output similar to the following:
'
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'...
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'
'Process is terminated due to StackOverflowException.
```

## <a name="see-also"></a><span data-ttu-id="3b09e-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b09e-148">See also</span></span>

- [<span data-ttu-id="3b09e-149">Procedimientos recomendados para cargar ensamblados</span><span class="sxs-lookup"><span data-stu-id="3b09e-149">Best practices for assembly loading</span></span>](../../framework/deployment/best-practices-for-assembly-loading.md)
- [<span data-ttu-id="3b09e-150">Utilizar dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="3b09e-150">Use application domains</span></span>](../../framework/app-domains/use.md)
