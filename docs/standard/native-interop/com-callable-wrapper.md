---
title: Contenedor CCW
description: Cuando un cliente COM llama a un objeto .NET, CLR crea el objeto administrado y un contenedor CCW para él. Los clientes COM llaman al contenedor del objeto.
ms.date: 10/23/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CCW
- COM interop, COM wrappers
- COM wrappers
- callable wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: d04be3b5-27b9-4f5b-8469-a44149fabf78
ms.openlocfilehash: cc27ba47c88d424a80eb47aaa310bdfd6d18433a
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2020
ms.locfileid: "93187923"
---
# <a name="com-callable-wrapper"></a><span data-ttu-id="be85b-104">Contenedor CCW</span><span class="sxs-lookup"><span data-stu-id="be85b-104">COM Callable Wrapper</span></span>

<span data-ttu-id="be85b-105">Cuando un cliente COM llama a un objeto .NET, Common Language Runtime crea el objeto administrado y un contenedor CCW (COM callable wrapper) para el objeto.</span><span class="sxs-lookup"><span data-stu-id="be85b-105">When a COM client calls a .NET object, the common language runtime creates the managed object and a COM callable wrapper (CCW) for the object.</span></span> <span data-ttu-id="be85b-106">Como no pueden hacer referencia a los objetos .NET directamente, los clientes COM usan el CCW como un proxy del objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="be85b-106">Unable to reference a .NET object directly, COM clients use the CCW as a proxy for the managed object.</span></span>

<span data-ttu-id="be85b-107">El motor en tiempo de ejecución crea exactamente un CCW para un objeto administrado, independientemente del número de clientes COM que soliciten sus servicios.</span><span class="sxs-lookup"><span data-stu-id="be85b-107">The runtime creates exactly one CCW for a managed object, regardless of the number of COM clients requesting its services.</span></span> <span data-ttu-id="be85b-108">Como se muestra en la siguiente ilustración, varios clientes COM pueden guardar una referencia al CCW que expone la interfaz INew.</span><span class="sxs-lookup"><span data-stu-id="be85b-108">As the following illustration shows, multiple COM clients can hold a reference to the CCW that exposes the INew interface.</span></span> <span data-ttu-id="be85b-109">A su vez, el CCW contiene una única referencia al objeto administrado que implementa la interfaz y se recolectan los elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="be85b-109">The CCW, in turn, holds a single reference to the managed object that implements the interface and is garbage collected.</span></span> <span data-ttu-id="be85b-110">Los clientes COM y .NET pueden hacer solicitudes en un objeto administrado simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="be85b-110">Both COM and .NET clients can make requests on the same managed object simultaneously.</span></span>

![Varios clientes COM que guardan una referencia al CCW que expone la interfaz INew.](./media/com-callable-wrapper/com-callable-wrapper-clients.gif)

<span data-ttu-id="be85b-112">Los contenedores CCW no están visibles para otras clases en ejecución en el runtime de .NET.</span><span class="sxs-lookup"><span data-stu-id="be85b-112">COM callable wrappers are invisible to other classes running within the .NET runtime.</span></span> <span data-ttu-id="be85b-113">Su objetivo principal es serializar llamadas entre código administrado y no administrado; sin embargo, los CCW también pueden administrar la identidad y la duración de los objetos administrados que contienen.</span><span class="sxs-lookup"><span data-stu-id="be85b-113">Their primary purpose is to marshal calls between managed and unmanaged code; however, CCWs also manage the object identity and object lifetime of the managed objects they wrap.</span></span>

## <a name="object-identity"></a><span data-ttu-id="be85b-114">Identidad de objetos</span><span class="sxs-lookup"><span data-stu-id="be85b-114">Object Identity</span></span>

<span data-ttu-id="be85b-115">El motor en tiempo de ejecución asigna memoria para el objeto .NET desde su montón tras haber eliminado la memoria no utilizada, lo que permite que el motor en tiempo de ejecución mueva el objeto en la memoria como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="be85b-115">The runtime allocates memory for the .NET object from its garbage-collected heap, which enables the runtime to move the object around in memory as necessary.</span></span> <span data-ttu-id="be85b-116">En contraposición, el motor en tiempo de ejecución asigna al CCW memoria de un montón en el que no se ha eliminado la memoria no utilizada, con lo que los clientes COM pueden hacer referencia al contenedor directamente.</span><span class="sxs-lookup"><span data-stu-id="be85b-116">In contrast, the runtime allocates memory for the CCW from a noncollected heap, making it possible for COM clients to reference the wrapper directly.</span></span>

## <a name="object-lifetime"></a><span data-ttu-id="be85b-117">Duración de objetos</span><span class="sxs-lookup"><span data-stu-id="be85b-117">Object Lifetime</span></span>

<span data-ttu-id="be85b-118">A diferencia del cliente .NET que contiene, las referencias del CCW se cuentan siguiendo la manera habitual de COM.</span><span class="sxs-lookup"><span data-stu-id="be85b-118">Unlike the .NET client it wraps, the CCW is reference-counted in traditional COM fashion.</span></span> <span data-ttu-id="be85b-119">Cuando el número de referencias del CCW llega a cero, el contenedor libera su referencia en el objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="be85b-119">When the reference count on the CCW reaches zero, the wrapper releases its reference on the managed object.</span></span> <span data-ttu-id="be85b-120">Los objetos administrados a los que ya no quedan referencias se recogen en el siguiente ciclo de recolección de memoria no utilizada.</span><span class="sxs-lookup"><span data-stu-id="be85b-120">A managed object with no remaining references is collected during the next garbage-collection cycle.</span></span>

## <a name="simulating-com-interfaces"></a><span data-ttu-id="be85b-121">Simulación de interfaces COM</span><span class="sxs-lookup"><span data-stu-id="be85b-121">Simulating COM interfaces</span></span>

<span data-ttu-id="be85b-122">CCW expone todos los tipos de datos, interfaces visibles para COM públicas y valores devueltos a los clientes COM de manera coherente con los requisitos de COM de interacción basada en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="be85b-122">CCW exposes all public, COM-visible interfaces, data types, and return values to COM clients in a manner that is consistent with COM's enforcement of interface-based interaction.</span></span> <span data-ttu-id="be85b-123">Para un cliente COM, la invocación de métodos en un objeto .NET es idéntica a la invocación de métodos en un objeto COM.</span><span class="sxs-lookup"><span data-stu-id="be85b-123">For a COM client, invoking methods on a .NET object is identical to invoking methods on a COM object.</span></span>

<span data-ttu-id="be85b-124">Para crear este enfoque uniforme, el CCW genera interfaces COM tradicionales como **IUnknown** e **IDispatch**.</span><span class="sxs-lookup"><span data-stu-id="be85b-124">To create this seamless approach, the CCW manufactures traditional COM interfaces, such as **IUnknown** and **IDispatch**.</span></span> <span data-ttu-id="be85b-125">Como se muestra en la siguiente ilustración, el CCW mantiene una sola referencia en el objeto .NET que encapsula.</span><span class="sxs-lookup"><span data-stu-id="be85b-125">As the following illustration shows, the CCW maintains a single reference on the .NET object that it wraps.</span></span> <span data-ttu-id="be85b-126">El cliente COM y el objeto .NET interactúan entre sí a través de la construcción de proxy y código auxiliar del CCW.</span><span class="sxs-lookup"><span data-stu-id="be85b-126">Both the COM client and the .NET object interact with each other through the proxy and stub construction of the CCW.</span></span>

![Diagrama que muestra cómo CCW crea interfaces de COM.](./media/com-callable-wrapper/com-callable-wrapper-interfaces.gif)

<span data-ttu-id="be85b-128">Además de exponer las interfaces implementadas explícitamente por una clase en el entorno administrado, el runtime de .NET proporciona implementaciones de las interfaces COM enumeradas en la tabla siguiente en nombre del objeto.</span><span class="sxs-lookup"><span data-stu-id="be85b-128">In addition to exposing the interfaces that are explicitly implemented by a class in the managed environment, the .NET runtime supplies implementations of the COM interfaces listed in the following table on behalf of the object.</span></span> <span data-ttu-id="be85b-129">Una clase .NET puede proporcionar su propia implementación de estas interfaces para invalidar el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="be85b-129">A .NET class can override the default behavior by providing its own implementation of these interfaces.</span></span> <span data-ttu-id="be85b-130">El tiempo de ejecución proporciona siempre la implementación de las interfaces **IUnknown** e **IDispatch**.</span><span class="sxs-lookup"><span data-stu-id="be85b-130">However, the runtime always provides the implementation for the **IUnknown** and **IDispatch** interfaces.</span></span>

|<span data-ttu-id="be85b-131">Interfaz</span><span class="sxs-lookup"><span data-stu-id="be85b-131">Interface</span></span>|<span data-ttu-id="be85b-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="be85b-132">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="be85b-133">**IDispatch**</span><span class="sxs-lookup"><span data-stu-id="be85b-133">**IDispatch**</span></span>|<span data-ttu-id="be85b-134">Proporciona un mecanismo para el enlace en tiempo de ejecución al tipo.</span><span class="sxs-lookup"><span data-stu-id="be85b-134">Provides a mechanism for late binding to type.</span></span>|
|<span data-ttu-id="be85b-135">**IErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="be85b-135">**IErrorInfo**</span></span>|<span data-ttu-id="be85b-136">Proporciona una descripción textual del error, su origen, un archivo de ayuda, contexto de ayuda y el GUID de la interfaz que definió el error (siempre **GUID_NULL** para las clases. NET).</span><span class="sxs-lookup"><span data-stu-id="be85b-136">Provides a textual description of the error, its source, a Help file, Help context, and the GUID of the interface that defined the error (always **GUID_NULL** for .NET classes).</span></span>|
|<span data-ttu-id="be85b-137">**IProvideClassInfo**</span><span class="sxs-lookup"><span data-stu-id="be85b-137">**IProvideClassInfo**</span></span>|<span data-ttu-id="be85b-138">Permite que los clientes COM tengan acceso a la interfaz **ITypeInfo** implementada por una clase administrada.</span><span class="sxs-lookup"><span data-stu-id="be85b-138">Enables COM clients to gain access to the **ITypeInfo** interface implemented by a managed class.</span></span> <span data-ttu-id="be85b-139">Devuelve `COR_E_NOTSUPPORTED` en .NET Core para los tipos no importados desde COM.</span><span class="sxs-lookup"><span data-stu-id="be85b-139">Returns `COR_E_NOTSUPPORTED` on .NET Core for types not imported from COM.</span></span> |
|<span data-ttu-id="be85b-140">**ISupportErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="be85b-140">**ISupportErrorInfo**</span></span>|<span data-ttu-id="be85b-141">Permite a un cliente COM determinar si el objeto administrado es compatible con la interfaz **IErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="be85b-141">Enables a COM client to determine whether the managed object supports the **IErrorInfo** interface.</span></span> <span data-ttu-id="be85b-142">Si es así, permite al cliente obtener un puntero al objeto de excepción más reciente.</span><span class="sxs-lookup"><span data-stu-id="be85b-142">If so, enables the client to obtain a pointer to the latest exception object.</span></span> <span data-ttu-id="be85b-143">Todos los tipos administrados son compatibles con la interfaz **IErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="be85b-143">All managed types support the **IErrorInfo** interface.</span></span>|
|<span data-ttu-id="be85b-144">**ITypeInfo** (solo .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="be85b-144">**ITypeInfo** (.NET Framework only)</span></span>|<span data-ttu-id="be85b-145">Proporciona información de tipos para una clase que es exactamente igual que la información de tipos producida Tlbexp.exe.</span><span class="sxs-lookup"><span data-stu-id="be85b-145">Provides type information for a class that is exactly the same as the type information produced by Tlbexp.exe.</span></span>|
|<span data-ttu-id="be85b-146">**IUnknown**</span><span class="sxs-lookup"><span data-stu-id="be85b-146">**IUnknown**</span></span>|<span data-ttu-id="be85b-147">Proporciona la implementación estándar de la interfaz **IUnknown** con la que el cliente COM administra la duración del CCW y proporciona coerción de tipos.</span><span class="sxs-lookup"><span data-stu-id="be85b-147">Provides the standard implementation of the **IUnknown** interface with which the COM client manages the lifetime of the CCW and provides type coercion.</span></span>|

 <span data-ttu-id="be85b-148">Una clase administrada también puede proporcionar las interfaces COM que se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="be85b-148">A managed class can also provide the COM interfaces described in the following table.</span></span>

|<span data-ttu-id="be85b-149">Interfaz</span><span class="sxs-lookup"><span data-stu-id="be85b-149">Interface</span></span>|<span data-ttu-id="be85b-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="be85b-150">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="be85b-151">Interfaz de clase (\_*nombreDeClase* )</span><span class="sxs-lookup"><span data-stu-id="be85b-151">The (\_*classname* ) class interface</span></span>|<span data-ttu-id="be85b-152">Interfaz, expuesta por el runtime y no definida explícitamente, que expone todas las interfaces públicas, métodos, propiedades y campos que se exponen explícitamente en un objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="be85b-152">Interface, exposed by the runtime and not explicitly defined, that exposes all public interfaces, methods, properties, and fields that are explicitly exposed on a managed object.</span></span>|
|<span data-ttu-id="be85b-153">**IConnectionPoint** e **IConnectionPointContainer**</span><span class="sxs-lookup"><span data-stu-id="be85b-153">**IConnectionPoint** and **IConnectionPointContainer**</span></span>|<span data-ttu-id="be85b-154">Interfaz para objetos que son origen de eventos basados en delegados (interfaz para registrar suscriptores de eventos).</span><span class="sxs-lookup"><span data-stu-id="be85b-154">Interface for objects that source delegate-based events (an interface for registering event subscribers).</span></span>|
|<span data-ttu-id="be85b-155">**IDispatchEx** (solo .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="be85b-155">**IDispatchEx** (.NET Framework only)</span></span>|<span data-ttu-id="be85b-156">Interfaz proporcionada por el tiempo de ejecución si la clase implementa **IExpando**.</span><span class="sxs-lookup"><span data-stu-id="be85b-156">Interface supplied by the runtime if the class implements **IExpando**.</span></span> <span data-ttu-id="be85b-157">La interfaz **IDispatchEx** es una extensión de la interfaz **IDispatch** que, a diferencia de **IDispatch** , permite enumerar, agregar, eliminar y llamar a miembros con distinción de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="be85b-157">The **IDispatchEx** interface is an extension of the **IDispatch** interface that, unlike **IDispatch** , enables enumeration, addition, deletion, and case-sensitive calling of members.</span></span>|
|<span data-ttu-id="be85b-158">**IEnumVARIANT**</span><span class="sxs-lookup"><span data-stu-id="be85b-158">**IEnumVARIANT**</span></span>|<span data-ttu-id="be85b-159">Interfaz para clases de tipo de colección que enumera los objetos de la colección si la clase implementa **IEnumerable**.</span><span class="sxs-lookup"><span data-stu-id="be85b-159">Interface for collection-type classes, which enumerates the objects in the collection if the class implements **IEnumerable**.</span></span>|

## <a name="introducing-the-class-interface"></a><span data-ttu-id="be85b-160">Presentar la interfaz de clase</span><span class="sxs-lookup"><span data-stu-id="be85b-160">Introducing the class interface</span></span>

<span data-ttu-id="be85b-161">La interfaz de clase, que no se define explícitamente en el código administrado, es una interfaz que expone todos los métodos, propiedades, campos y eventos públicos que se exponen explícitamente en el objeto .NET.</span><span class="sxs-lookup"><span data-stu-id="be85b-161">The class interface, which is not explicitly defined in managed code, is an interface that exposes all public methods, properties, fields, and events that are explicitly exposed on the .NET object.</span></span> <span data-ttu-id="be85b-162">Puede ser una interfaz dual o sólo de envío.</span><span class="sxs-lookup"><span data-stu-id="be85b-162">This interface can be a dual or dispatch-only interface.</span></span> <span data-ttu-id="be85b-163">La interfaz de clase recibe el nombre de la propia clase .NET, precedida por un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="be85b-163">The class interface receives the name of the .NET class itself, preceded by an underscore.</span></span> <span data-ttu-id="be85b-164">Por ejemplo, para la clase Mammal, la interfaz de clase es \_Mammal.</span><span class="sxs-lookup"><span data-stu-id="be85b-164">For example, for class Mammal, the class interface is \_Mammal.</span></span>

<span data-ttu-id="be85b-165">Para las clases derivadas, la interfaz de clase también expone todos los métodos, propiedades y campos públicos de la clase base.</span><span class="sxs-lookup"><span data-stu-id="be85b-165">For derived classes, the class interface also exposes all public methods, properties, and fields of the base class.</span></span> <span data-ttu-id="be85b-166">La clase derivada también expone una interfaz de clase para cada clase base.</span><span class="sxs-lookup"><span data-stu-id="be85b-166">The derived class also exposes a class interface for each base class.</span></span> <span data-ttu-id="be85b-167">Por ejemplo, si la clase Mammal extiende la clase MammalSuperclass, que a su vez extiende System.Object, el objeto .NET expone a los clientes COM tres interfaces de clase llamadas \_Mammal, \_MammalSuperclass y \_Object.</span><span class="sxs-lookup"><span data-stu-id="be85b-167">For example, if class Mammal extends class MammalSuperclass, which itself extends System.Object, the .NET object exposes to COM clients three class interfaces named \_Mammal, \_MammalSuperclass, and \_Object.</span></span>

<span data-ttu-id="be85b-168">Por ejemplo, observe la siguiente clase .NET:</span><span class="sxs-lookup"><span data-stu-id="be85b-168">For example, consider the following .NET class:</span></span>

```vb
' Applies the ClassInterfaceAttribute to set the interface to dual.
<ClassInterface(ClassInterfaceType.AutoDual)> _
' Implicitly extends System.Object.
Public Class Mammal
    Sub Eat()
    Sub Breathe()
    Sub Sleep()
End Class
```

```csharp
// Applies the ClassInterfaceAttribute to set the interface to dual.
[ClassInterface(ClassInterfaceType.AutoDual)]
// Implicitly extends System.Object.
public class Mammal
{
    public void Eat() {}
    public void Breathe() {}
    public void Sleep() {}
}
```

<span data-ttu-id="be85b-169">El cliente COM puede obtener un puntero a una interfaz de clase denominada `_Mammal`.</span><span class="sxs-lookup"><span data-stu-id="be85b-169">The COM client can obtain a pointer to a class interface named `_Mammal`.</span></span> <span data-ttu-id="be85b-170">En .NET Framework, se puede usar la herramienta [Exportador de la biblioteca de tipos (Tlbexp.exe)](../../framework/tools/tlbexp-exe-type-library-exporter.md) para generar una biblioteca de tipos que contiene la definición de la interfaz `_Mammal`.</span><span class="sxs-lookup"><span data-stu-id="be85b-170">On .NET Framework, you can use the [Type Library Exporter (Tlbexp.exe)](../../framework/tools/tlbexp-exe-type-library-exporter.md) tool to generate a type library containing the `_Mammal` interface definition.</span></span> <span data-ttu-id="be85b-171">La herramienta Exportador de la biblioteca de tipos no es compatible con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="be85b-171">The Type Library Exporter is not supported on .NET Core.</span></span> <span data-ttu-id="be85b-172">Si la clase `Mammal` implementó una o más interfaces, estas aparecerán bajo la coclase.</span><span class="sxs-lookup"><span data-stu-id="be85b-172">If the `Mammal` class implemented one or more interfaces, the interfaces would appear under the coclass.</span></span>

```console
[odl, uuid(…), hidden, dual, nonextensible, oleautomation]
interface _Mammal : IDispatch
{
    [id(0x00000000), propget] HRESULT ToString([out, retval] BSTR*
        pRetVal);
    [id(0x60020001)] HRESULT Equals([in] VARIANT obj, [out, retval]
        VARIANT_BOOL* pRetVal);
    [id(0x60020002)] HRESULT GetHashCode([out, retval] short* pRetVal);
    [id(0x60020003)] HRESULT GetType([out, retval] _Type** pRetVal);
    [id(0x6002000d)] HRESULT Eat();
    [id(0x6002000e)] HRESULT Breathe();
    [id(0x6002000f)] HRESULT Sleep();
}
[uuid(…)]
coclass Mammal
{
    [default] interface _Mammal;
}
```

<span data-ttu-id="be85b-173">Generar la interfaz de clase es una acción opcional.</span><span class="sxs-lookup"><span data-stu-id="be85b-173">Generating the class interface is optional.</span></span> <span data-ttu-id="be85b-174">De manera predeterminada, la interoperabilidad COM genera una interfaz solo de envío para cada clase que se exporta a una biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="be85b-174">By default, COM interop generates a dispatch-only interface for each class you export to a type library.</span></span> <span data-ttu-id="be85b-175">La creación automática de esta interfaz se puede impedir o modificar aplicando <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> a la clase.</span><span class="sxs-lookup"><span data-stu-id="be85b-175">You can prevent or modify the automatic creation of this interface by applying the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> to your class.</span></span> <span data-ttu-id="be85b-176">Si bien la interfaz de clase puede facilitar la tarea de exponer clases administradas a COM, sus usos son limitados.</span><span class="sxs-lookup"><span data-stu-id="be85b-176">Although the class interface can ease the task of exposing managed classes to COM, its uses are limited.</span></span>

> [!CAUTION]
> <span data-ttu-id="be85b-177">Si se usa la interfaz de clase en lugar de definir una interfaz propia de manera explícita, el control de las futuras versiones de la clase administrada puede ser más complicado.</span><span class="sxs-lookup"><span data-stu-id="be85b-177">Using the class interface, instead of explicitly defining your own, can complicate the future versioning of your managed class.</span></span> <span data-ttu-id="be85b-178">Antes de usar la interfaz de clase lea las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="be85b-178">Please read the following guidelines before using the class interface.</span></span>

### <a name="define-an-explicit-interface-for-com-clients-to-use-rather-than-generating-the-class-interface"></a><span data-ttu-id="be85b-179">Defina una interfaz explícita para que la usen los clientes COM en lugar de generar la interfaz de clase.</span><span class="sxs-lookup"><span data-stu-id="be85b-179">Define an explicit interface for COM clients to use rather than generating the class interface.</span></span>

<span data-ttu-id="be85b-180">Dado que la interoperabilidad COM genera automáticamente una interfaz de clase, los cambios en versiones posteriores de la clase pueden modificar el diseño de la interfaz de clase expuesta por Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="be85b-180">Because COM interop generates a class interface automatically, post-version changes to your class can alter the layout of the class interface exposed by the common language runtime.</span></span> <span data-ttu-id="be85b-181">Puesto que los clientes COM no están preparados normalmente para controlar cambios en el diseño de una interfaz, se interrumpen si se cambia el diseño de miembro de la clase.</span><span class="sxs-lookup"><span data-stu-id="be85b-181">Since COM clients are typically unprepared to handle changes in the layout of an interface, they break if you change the member layout of the class.</span></span>

<span data-ttu-id="be85b-182">Esta instrucción enfatiza la idea de que las interfaces expuestas a los clientes COM no se deben modificar.</span><span class="sxs-lookup"><span data-stu-id="be85b-182">This guideline reinforces the notion that interfaces exposed to COM clients must remain unchangeable.</span></span> <span data-ttu-id="be85b-183">Para reducir el riesgo de que los clientes COM se interrumpan por volver a ordenar involuntariamente el diseño de interfaz, aísle del diseño de interfaz todos los cambios que se hagan en la clase definiendo las interfaces de manera explícita.</span><span class="sxs-lookup"><span data-stu-id="be85b-183">To reduce the risk of breaking COM clients by inadvertently reordering the interface layout, isolate all changes to the class from the interface layout by explicitly defining interfaces.</span></span>

<span data-ttu-id="be85b-184">Use **ClassInterfaceAttribute** para desactivar la generación automática de la interfaz de clase e implemente una interfaz explícita para la clase, como se muestra en el fragmento de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="be85b-184">Use the **ClassInterfaceAttribute** to disengage the automatic generation of the class interface and implement an explicit interface for the class, as the following code fragment shows:</span></span>

```vb
<ClassInterface(ClassInterfaceType.None)>Public Class LoanApp
    Implements IExplicit
    Sub M() Implements IExplicit.M
…
End Class
```

```csharp
[ClassInterface(ClassInterfaceType.None)]
public class LoanApp : IExplicit
{
    int IExplicit.M() { return 0; }
}
```

<span data-ttu-id="be85b-185">El valor **ClassInterfaceType.None** impide que la interfaz de clase se genere cuando los metadatos de la clase se exportan a una biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="be85b-185">The **ClassInterfaceType.None** value prevents the class interface from being generated when the class metadata is exported to a type library.</span></span> <span data-ttu-id="be85b-186">En el ejemplo anterior, los clientes COM tan solo pueden tener acceso a la clase `LoanApp` a través de la interfaz `IExplicit`.</span><span class="sxs-lookup"><span data-stu-id="be85b-186">In the preceding example, COM clients can access the `LoanApp` class only through the `IExplicit` interface.</span></span>

### <a name="avoid-caching-dispatch-identifiers-dispids"></a><span data-ttu-id="be85b-187">Evitar almacenamiento en caché de identificadores de envío (DISPID)</span><span class="sxs-lookup"><span data-stu-id="be85b-187">Avoid caching dispatch identifiers (DispIds)</span></span>

<span data-ttu-id="be85b-188">El uso de la interfaz de clase es una opción aceptable para los clientes con scripts, los clientes de Microsoft Visual Basic 6.0 o cualquier cliente enlazado en tiempo de ejecución que no almacene en caché los identificadores DispId de los miembros de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="be85b-188">Using the class interface is an acceptable option for scripted clients, Microsoft Visual Basic 6.0 clients, or any late-bound client that does not cache the DispIds of interface members.</span></span> <span data-ttu-id="be85b-189">Los identificadores DispId identifican los miembros de la interfaz para admitir enlaces en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="be85b-189">DispIds identify interface members to enable late binding.</span></span>

<span data-ttu-id="be85b-190">Para la interfaz de clase, la generación de identificadores DispId se basa en la posición del miembro en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="be85b-190">For the class interface, generation of DispIds is based on the position of the member in the interface.</span></span> <span data-ttu-id="be85b-191">Si cambia el orden del miembro y exporta la clase a una biblioteca de tipos, modificará los identificadores DispId generados en la interfaz de clase.</span><span class="sxs-lookup"><span data-stu-id="be85b-191">If you change the order of the member and export the class to a type library, you will alter the DispIds generated in the class interface.</span></span>

<span data-ttu-id="be85b-192">Para evitar que los clientes COM enlazados en tiempo de ejecución se interrumpan al usar la interfaz de clase, aplique **ClassInterfaceAttribute** con el valor **ClassInterfaceType.AutoDispatch**.</span><span class="sxs-lookup"><span data-stu-id="be85b-192">To avoid breaking late-bound COM clients when using the class interface, apply the **ClassInterfaceAttribute** with the **ClassInterfaceType.AutoDispatch** value.</span></span> <span data-ttu-id="be85b-193">Este valor implementa una interfaz de clase de solo envío, pero omite la descripción de la interfaz de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="be85b-193">This value implements a dispatch-only class interface, but omits the interface description from the type library.</span></span> <span data-ttu-id="be85b-194">Sin una descripción de la interfaz, los clientes no pueden almacenar en caché los identificadores DispId en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="be85b-194">Without an interface description, clients are unable to cache DispIds at compile time.</span></span> <span data-ttu-id="be85b-195">Aunque este es el tipo predeterminado de la interfaz de clase, se puede aplicar el valor del atributo de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="be85b-195">Although this is the default interface type for the class interface, you can apply the attribute value explicitly.</span></span>

```vb
<ClassInterface(ClassInterfaceType.AutoDispatch)> Public Class LoanApp
    Implements IAnother
    Sub M() Implements IAnother.M
…
End Class
```

```csharp
[ClassInterface(ClassInterfaceType.AutoDispatch)]
public class LoanApp
{
    public int M() { return 0; }
}
```

<span data-ttu-id="be85b-196">Para obtener el DispId de un miembro de interfaz en tiempo de ejecución, los clientes COM pueden llamar a **IDispatch.GetIdsOfNames**.</span><span class="sxs-lookup"><span data-stu-id="be85b-196">To get the DispId of an interface member at run time, COM clients can call **IDispatch.GetIdsOfNames**.</span></span> <span data-ttu-id="be85b-197">Para invocar un método en la interfaz, pase el DispId devuelto como argumento a **IDispatch.Invoke**.</span><span class="sxs-lookup"><span data-stu-id="be85b-197">To invoke a method on the interface, pass the returned DispId as an argument to **IDispatch.Invoke**.</span></span>

### <a name="restrict-using-the-dual-interface-option-for-the-class-interface"></a><span data-ttu-id="be85b-198">Restrinja el uso de la opción de interfaz dual en la interfaz de clase.</span><span class="sxs-lookup"><span data-stu-id="be85b-198">Restrict using the dual interface option for the class interface.</span></span>

<span data-ttu-id="be85b-199">Las interfaces duales permiten el enlace en tiempo de diseño y en tiempo de ejecución de los clientes COM con los miembros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="be85b-199">Dual interfaces enable early and late binding to interface members by COM clients.</span></span> <span data-ttu-id="be85b-200">El establecimiento de la interfaz de clase en dual puede ser útil en tiempo de diseño y durante las pruebas.</span><span class="sxs-lookup"><span data-stu-id="be85b-200">At design time and during testing, you might find it useful to set the class interface to dual.</span></span> <span data-ttu-id="be85b-201">Esta opción también es aceptable para una clase administrada (y sus clases base) que no se va a modificar nunca.</span><span class="sxs-lookup"><span data-stu-id="be85b-201">For a managed class (and its base classes) that will never be modified, this option is also acceptable.</span></span> <span data-ttu-id="be85b-202">En todos los demás casos, no es necesario establecer la interfaz de clase en dual.</span><span class="sxs-lookup"><span data-stu-id="be85b-202">In all other cases, avoid setting the class interface to dual.</span></span>

<span data-ttu-id="be85b-203">Una interfaz dual generada automáticamente puede ser apropiada en algunos casos, pero a menudo genera complicaciones de control de versiones.</span><span class="sxs-lookup"><span data-stu-id="be85b-203">An automatically generated dual interface might be appropriate in rare cases; however, more often it creates version-related complexity.</span></span> <span data-ttu-id="be85b-204">Por ejemplo, los clientes COM que usen la interfaz de clase de una clase derivada se pueden interrumpir con facilidad si se hacen cambios en la clase base.</span><span class="sxs-lookup"><span data-stu-id="be85b-204">For example, COM clients using the class interface of a derived class can easily break with changes to the base class.</span></span> <span data-ttu-id="be85b-205">Si la clase base es de terceros, el usuario no tiene control sobre el diseño de la interfaz de clase.</span><span class="sxs-lookup"><span data-stu-id="be85b-205">When a third party provides the base class, the layout of the class interface is out of your control.</span></span> <span data-ttu-id="be85b-206">Además, a diferencia de una interfaz de solo envío, una interfaz dual ( **ClassInterfaceType.AutoDual** ) proporciona una descripción de la interfaz de clase en la biblioteca de tipos exportada.</span><span class="sxs-lookup"><span data-stu-id="be85b-206">Further, unlike a dispatch-only interface, a dual interface ( **ClassInterfaceType.AutoDual** ) provides a description of the class interface in the exported type library.</span></span> <span data-ttu-id="be85b-207">Dicha descripción hace que los clientes enlazados en tiempo de ejecución almacenen en caché los identificadores DispId en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="be85b-207">Such a description encourages late-bound clients to cache DispIds at compile time.</span></span>

### <a name="ensure-that-all-com-event-notifications-are-late-bound"></a><span data-ttu-id="be85b-208">Asegúrese de que todas las notificaciones de eventos COM están enlazadas tardíamente.</span><span class="sxs-lookup"><span data-stu-id="be85b-208">Ensure that all COM event notifications are late-bound.</span></span>

<span data-ttu-id="be85b-209">De forma predeterminada, la información de tipos COM se inserta directamente en los ensamblados administrados, lo que elimina la necesidad de ensamblados de interoperabilidad primarios (PIA).</span><span class="sxs-lookup"><span data-stu-id="be85b-209">By default, COM type information is embedded directly into managed assemblies, which eliminates the need for primary interop assemblies (PIAs).</span></span> <span data-ttu-id="be85b-210">Sin embargo, una de las limitaciones de la información de tipo insertada es que no admite la entrega de notificaciones de eventos COM mediante llamadas enlazadas tempranamente vtable, sino que solo admite llamadas `IDispatch::Invoke` enlazadas tardíamente.</span><span class="sxs-lookup"><span data-stu-id="be85b-210">However, one of the limitations of embedded type information is that it does not support delivery of COM event notifications by early-bound vtable calls, but only supports late-bound `IDispatch::Invoke` calls.</span></span>

<span data-ttu-id="be85b-211">Si la aplicación requiere las llamadas enlazadas tempranamente a los métodos de interfaz de eventos COM, puede establecer la propiedad **Incrustar tipos de interoperabilidad** en Visual Studio en `true` o incluir el siguiente elemento en el archivo de proyecto:</span><span class="sxs-lookup"><span data-stu-id="be85b-211">If your application requires early-bound calls to COM event interface methods, you can set the **Embed Interop Types** property in Visual Studio to `true`, or include the following element in your project file:</span></span>

```xml
<EmbedInteropTypes>True</EmbedInteropTypes>
```

## <a name="see-also"></a><span data-ttu-id="be85b-212">Vea también</span><span class="sxs-lookup"><span data-stu-id="be85b-212">See also</span></span>

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>
- [<span data-ttu-id="be85b-213">Contenedores COM</span><span class="sxs-lookup"><span data-stu-id="be85b-213">COM Wrappers</span></span>](com-wrappers.md)
- [<span data-ttu-id="be85b-214">Exponer componentes de .NET Framework en COM</span><span class="sxs-lookup"><span data-stu-id="be85b-214">Exposing .NET Framework Components to COM</span></span>](../../framework/interop/exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="be85b-215">Exposición de los componentes de .NET Core a COM</span><span class="sxs-lookup"><span data-stu-id="be85b-215">Exposing .NET Core Components to COM</span></span>](../../core/native-interop/expose-components-to-com.md)
- [<span data-ttu-id="be85b-216">Habilitar tipos de .NET para la interoperación</span><span class="sxs-lookup"><span data-stu-id="be85b-216">Qualifying .NET Types for Interoperation</span></span>](qualify-net-types-for-interoperation.md)
- [<span data-ttu-id="be85b-217">Contenedor al que se puede llamar en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="be85b-217">Runtime Callable Wrapper</span></span>](runtime-callable-wrapper.md)
