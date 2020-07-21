---
title: Información general del modelo de programación con atributos (MEF)
description: Introducción al modelo de programación con atributos, que es el predeterminado para Managed Extensibility Framework (MEF) en .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MEF, attributed programming model
- attributed programming model [MEF]
ms.assetid: 49b787ff-2741-4836-ad51-c3017dc592d4
ms.openlocfilehash: aea3a19ffe6f177901e5c0839b618bb36f573beb
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281373"
---
# <a name="attributed-programming-model-overview-mef"></a><span data-ttu-id="fff45-103">Información general del modelo de programación con atributos (MEF)</span><span class="sxs-lookup"><span data-stu-id="fff45-103">Attributed Programming Model Overview (MEF)</span></span>

<span data-ttu-id="fff45-104">En Managed Extensibility Framework (MEF), un *modelo de programación* es una manera específica de definir el conjunto de objetos conceptuales en los que opera MEF.</span><span class="sxs-lookup"><span data-stu-id="fff45-104">In the Managed Extensibility Framework (MEF), a *programming model* is a particular method of defining the set of conceptual objects on which MEF operates.</span></span> <span data-ttu-id="fff45-105">Estos objetos conceptuales incluyen partes, importaciones y exportaciones.</span><span class="sxs-lookup"><span data-stu-id="fff45-105">These conceptual objects include parts, imports, and exports.</span></span> <span data-ttu-id="fff45-106">MEF utiliza estos objetos, pero no especifica cómo se deben representar.</span><span class="sxs-lookup"><span data-stu-id="fff45-106">MEF uses these objects, but does not specify how they should be represented.</span></span> <span data-ttu-id="fff45-107">Por consiguiente, es posible una gran variedad de modelos de programación, incluidos modelos personalizados.</span><span class="sxs-lookup"><span data-stu-id="fff45-107">Therefore, a wide variety of programming models are possible, including customized programming models.</span></span>

<span data-ttu-id="fff45-108">El modelo de programación predeterminado utilizado en MEF es el *modelo de programación con atributos*.</span><span class="sxs-lookup"><span data-stu-id="fff45-108">The default programming model used in MEF is the *attributed programming model*.</span></span> <span data-ttu-id="fff45-109">En el modelo de programación con atributos se definen las partes, las importaciones, las exportaciones y otros objetos con atributos que decoran las clases de .NET Framework normales.</span><span class="sxs-lookup"><span data-stu-id="fff45-109">In the attributed programming model parts, imports, exports, and other objects are defined with attributes that decorate ordinary .NET Framework classes.</span></span> <span data-ttu-id="fff45-110">En este tema se explica cómo utilizar los atributos que proporciona el modelo de programación con atributos para crear una aplicación MEF.</span><span class="sxs-lookup"><span data-stu-id="fff45-110">This topic explains how to use the attributes provided by the attributed programming model to create a MEF application.</span></span>

<a name="import_and_export_basics"></a>

## <a name="import-and-export-basics"></a><span data-ttu-id="fff45-111">Conceptos básicos sobre importaciones y exportaciones</span><span class="sxs-lookup"><span data-stu-id="fff45-111">Import and Export Basics</span></span>

<span data-ttu-id="fff45-112">Una *exportación* es un valor que una parte proporciona a otras partes del contenedor y una *importación* es un requisito que una parte especifica al contenedor, y que se debe satisfacer con las exportaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="fff45-112">An *export* is a value that a part provides to other parts in the container, and an *import* is a requirement that a part expresses to the container, to be filled from the available exports.</span></span> <span data-ttu-id="fff45-113">En el modelo de programación con atributos, las importaciones y exportaciones se declaran decorando clases o miembros con atributos `Import` e `Export` .</span><span class="sxs-lookup"><span data-stu-id="fff45-113">In the attributed programming model, imports and exports are declared by decorating classes or members with the `Import` and `Export` attributes.</span></span> <span data-ttu-id="fff45-114">El atributo `Export` puede decorar una clase, campo, propiedad o método, mientras que el atributo `Import` puede decorar un campo, propiedad o parámetro de constructor.</span><span class="sxs-lookup"><span data-stu-id="fff45-114">The `Export` attribute can decorate a class, field, property, or method, while the `Import` attribute can decorate a field, property, or constructor parameter.</span></span>

<span data-ttu-id="fff45-115">Para que una importación pueda coincidir con una exportación, ambas deben tener el mismo *contrato*.</span><span class="sxs-lookup"><span data-stu-id="fff45-115">In order for an import to be matched with an export, the import and export must have the same *contract*.</span></span> <span data-ttu-id="fff45-116">El contrato está compuesto de una cadena, llamada *nombre del contrato*, y el tipo del objeto exportado o importado, denominado *tipo del contrato*.</span><span class="sxs-lookup"><span data-stu-id="fff45-116">The contract consists of a string, called the *contract name*, and the type of the exported or imported object, called the *contract type*.</span></span> <span data-ttu-id="fff45-117">Solo si el nombre del contrato y el tipo del contrato coinciden se considera que una exportación satisface una importación determinada.</span><span class="sxs-lookup"><span data-stu-id="fff45-117">Only if both the contract name and contract type match is an export considered to fulfill a particular import.</span></span>

<span data-ttu-id="fff45-118">Cualquiera de los parámetros del contrato (o ambos) puede ser implícito o explícito.</span><span class="sxs-lookup"><span data-stu-id="fff45-118">Either or both of the contract parameters can be implicit or explicit.</span></span> <span data-ttu-id="fff45-119">El siguiente código muestra una clase que declara una importación básica.</span><span class="sxs-lookup"><span data-stu-id="fff45-119">The following code shows a class that declares a basic import.</span></span>

```vb
Public Class MyClass1
    <Import()>
    Public Property MyAddin As IMyAddin
End Class
```

```csharp
public class MyClass
{
    [Import]
    public IMyAddin MyAddin { get; set; }
}
```

<span data-ttu-id="fff45-120">En esta importación, el atributo `Import` no tiene un tipo de contrato ni un parámetro de nombre de contrato adjunto.</span><span class="sxs-lookup"><span data-stu-id="fff45-120">In this import, the `Import` attribute has neither a contract type nor a contract name parameter attached.</span></span> <span data-ttu-id="fff45-121">Por consiguiente, ambos se deducirán de la propiedad decorada.</span><span class="sxs-lookup"><span data-stu-id="fff45-121">Therefore, both will be inferred from the decorated property.</span></span> <span data-ttu-id="fff45-122">En este caso, el tipo de contrato será `IMyAddin`y el nombre del contrato será una cadena única creada a partir del tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="fff45-122">In this case, the contract type will be `IMyAddin`, and the contract name will be a unique string created from the contract type.</span></span> <span data-ttu-id="fff45-123">(Es decir, el nombre del contrato sólo coincidirá con aquellas exportaciones cuyos nombres también se deduzcan del tipo `IMyAddin`.)</span><span class="sxs-lookup"><span data-stu-id="fff45-123">(In other words, the contract name will match only exports whose names are also inferred from the type `IMyAddin`.)</span></span>

<span data-ttu-id="fff45-124">A continuación se muestra una exportación que coincide con la importación anterior.</span><span class="sxs-lookup"><span data-stu-id="fff45-124">The following shows an export that matches the previous import.</span></span>

```vb
<Export(GetType(IMyAddin))>
Public Class MyLogger
    Implements IMyAddin

End Class
```

```csharp
[Export(typeof(IMyAddin))]
public class MyLogger : IMyAddin { }
```

<span data-ttu-id="fff45-125">En esta exportación, el tipo de contrato es `IMyAddin` porque se especifica como un parámetro del atributo `Export` .</span><span class="sxs-lookup"><span data-stu-id="fff45-125">In this export, the contract type is `IMyAddin` because it is specified as a parameter of the `Export` attribute.</span></span> <span data-ttu-id="fff45-126">El tipo exportado debe ser igual que el tipo de contrato, derivar del tipo de contrato o implementar el tipo del contrato si se trata de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="fff45-126">The exported type must be either the same as the contract type, derive from the contract type, or implement the contract type if it is an interface.</span></span> <span data-ttu-id="fff45-127">En este ejemplo, el tipo `MyLogger` implementa la interfaz `IMyAddin`.</span><span class="sxs-lookup"><span data-stu-id="fff45-127">In this export, the actual type `MyLogger` implements the interface `IMyAddin`.</span></span> <span data-ttu-id="fff45-128">El nombre del contrato se deduce del tipo de contrato, lo que significa que esta exportación coincidirá con la importación anterior.</span><span class="sxs-lookup"><span data-stu-id="fff45-128">The contract name is inferred from the contract type, which means that this export will match the previous import.</span></span>

> [!NOTE]
> <span data-ttu-id="fff45-129">Las exportaciones y las importaciones se deben declarar en clases o miembros públicos.</span><span class="sxs-lookup"><span data-stu-id="fff45-129">Exports and imports should usually be declared on public classes or members.</span></span> <span data-ttu-id="fff45-130">Se admiten otras declaraciones, pero exportar o importar un miembro privado, protegido o interno rompe el modelo de aislamiento para la parte y, por lo tanto, no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="fff45-130">Other declarations are supported, but exporting or importing a private, protected, or internal member breaks the isolation model for the part and is therefore not recommended.</span></span>

<span data-ttu-id="fff45-131">El tipo de contrato debe coincidir exactamente para que se considere que hay una coincidencia en la exportación y la importación.</span><span class="sxs-lookup"><span data-stu-id="fff45-131">The contract type must match exactly for the export and import to be considered a match.</span></span> <span data-ttu-id="fff45-132">Observe la exportación siguiente.</span><span class="sxs-lookup"><span data-stu-id="fff45-132">Consider the following export.</span></span>

```vb
<Export()> 'WILL NOT match the previous import!
Public Class MyLogger
    Implements IMyAddin

End Class
```

```csharp
[Export] //WILL NOT match the previous import!
public class MyLogger : IMyAddin { }
```

<span data-ttu-id="fff45-133">En esta exportación, el tipo de contrato es `MyLogger` en lugar de `IMyAddin`.</span><span class="sxs-lookup"><span data-stu-id="fff45-133">In this export, the contract type is `MyLogger` instead of `IMyAddin`.</span></span> <span data-ttu-id="fff45-134">Aunque `MyLogger` implementa `IMyAddin`y, por consiguiente, se pudo convertir en un objeto `IMyAddin` , esta exportación no coincidirá con la importación anterior porque los tipos de contrato no coinciden.</span><span class="sxs-lookup"><span data-stu-id="fff45-134">Even though `MyLogger` implements `IMyAddin`, and therefore could be cast to an `IMyAddin` object, this export will not match the previous import because the contract types are not the same.</span></span>

<span data-ttu-id="fff45-135">En general, no es necesario especificar el nombre del contrato, y la mayoría de los contratos se deberían definir según el tipo de contrato y los metadatos.</span><span class="sxs-lookup"><span data-stu-id="fff45-135">In general, it is not necessary to specify the contract name, and most contracts should be defined in terms of the contract type and metadata.</span></span> <span data-ttu-id="fff45-136">Sin embargo, en algunas circunstancias, es importante especificar el nombre del contrato directamente.</span><span class="sxs-lookup"><span data-stu-id="fff45-136">However, under certain circumstances, it is important to specify the contract name directly.</span></span> <span data-ttu-id="fff45-137">El caso más habitual es cuando una clase exporta varios valores que comparten un tipo común, como los primitivos.</span><span class="sxs-lookup"><span data-stu-id="fff45-137">The most common case is when a class exports several values that share a common type, such as primitives.</span></span> <span data-ttu-id="fff45-138">El nombre del contrato se puede especificar como el primer parámetro del atributo `Import` o `Export` .</span><span class="sxs-lookup"><span data-stu-id="fff45-138">The contract name can be specified as the first parameter of the `Import` or `Export` attribute.</span></span> <span data-ttu-id="fff45-139">El siguiente código muestra una importación y una exportación con un nombre de contrato especificado de `MajorRevision`.</span><span class="sxs-lookup"><span data-stu-id="fff45-139">The following code shows an import and an export with a specified contract name of `MajorRevision`.</span></span>

```vb
Public Class MyExportClass

    'This one will match
    <Export("MajorRevision")>
    Public ReadOnly Property MajorRevision As Integer
        Get
            Return 4
        End Get
    End Property

    <Export("MinorRevision")>
    Public ReadOnly Property MinorRevision As Integer
        Get
            Return 16
        End Get
    End Property
End Class
```

```csharp
public class MyClass
{
    [Import("MajorRevision")]
    public int MajorRevision { get; set; }
}

public class MyExportClass
{
    [Export("MajorRevision")] //This one will match.
    public int MajorRevision = 4;

    [Export("MinorRevision")]
    public int MinorRevision = 16;
}
```

<span data-ttu-id="fff45-140">Si no se especifica el tipo de contrato, se deducirá del tipo de la importación o exportación.</span><span class="sxs-lookup"><span data-stu-id="fff45-140">If the contract type is not specified, it will still be inferred from the type of the import or export.</span></span> <span data-ttu-id="fff45-141">Sin embargo, aun cuando explícitamente se especifica el nombre del contrato, el tipo de contrato debe coincidir también exactamente para que se considere que la importación y la exportación coinciden.</span><span class="sxs-lookup"><span data-stu-id="fff45-141">However, even if the contract name is specified explicitly, the contract type must also match exactly for the import and export to be considered a match.</span></span> <span data-ttu-id="fff45-142">Por ejemplo, si el campo `MajorRevision` fuera una cadena, los tipos de contrato deducidos no coincidirían y la exportación no coincidiría con la importación, a pesar de tener el mismo nombre de contrato.</span><span class="sxs-lookup"><span data-stu-id="fff45-142">For example, if the `MajorRevision` field was a string, the inferred contract types would not match and the export would not match the import, despite having the same contract name.</span></span>

### <a name="importing-and-exporting-a-method"></a><span data-ttu-id="fff45-143">Importar y exportar métodos</span><span class="sxs-lookup"><span data-stu-id="fff45-143">Importing and Exporting a Method</span></span>

<span data-ttu-id="fff45-144">El atributo `Export` también puede decorar un método, de la misma manera que una clase, propiedad o función.</span><span class="sxs-lookup"><span data-stu-id="fff45-144">The `Export` attribute can also decorate a method, in the same way as a class, property, or function.</span></span> <span data-ttu-id="fff45-145">Las exportaciones de métodos deben especificar un tipo o un nombre de contrato, porque el tipo no se puede deducir.</span><span class="sxs-lookup"><span data-stu-id="fff45-145">Method exports must specify a contract type or contract name, as the type cannot be inferred.</span></span> <span data-ttu-id="fff45-146">El tipo especificado puede ser un delegado personalizado o un tipo genérico, como `Func`.</span><span class="sxs-lookup"><span data-stu-id="fff45-146">The specified type can be either a custom delegate or a generic type, such as `Func`.</span></span> <span data-ttu-id="fff45-147">La siguiente clase exporta un método denominado `DoSomething`.</span><span class="sxs-lookup"><span data-stu-id="fff45-147">The following class exports a method named `DoSomething`.</span></span>

```vb
Public Class MyAddin

    'Explicitly specifying a generic type
    <Export(GetType(Func(Of Integer, String)))>
    Public Function DoSomething(ByVal TheParam As Integer) As String
        Return Nothing 'Function body goes here
    End Function

End Class
```

```csharp
public class MyAddin
{
    //Explicitly specifying a generic type.
    [Export(typeof(Func<int, string>))]
    public string DoSomething(int TheParam);
}
```

<span data-ttu-id="fff45-148">En esta clase, el método `DoSomething` toma un parámetro `int` único y devuelve `string`.</span><span class="sxs-lookup"><span data-stu-id="fff45-148">In this class, the `DoSomething` method takes a single `int` parameter and returns a `string`.</span></span> <span data-ttu-id="fff45-149">Para coincidir con esta exportación, la parte de la importación debe declarar un miembro adecuado.</span><span class="sxs-lookup"><span data-stu-id="fff45-149">To match this export, the importing part must declare an appropriate member.</span></span> <span data-ttu-id="fff45-150">La clase siguiente importa el método `DoSomething` .</span><span class="sxs-lookup"><span data-stu-id="fff45-150">The following class imports the `DoSomething` method.</span></span>

```vb
Public Class MyClass1

    'Contract name must match!
    <Import()>
    Public Property MajorRevision As Func(Of Integer, String)
End Class
```

```csharp
public class MyClass
{
    [Import] //Contract name must match!
    public Func<int, string> DoSomething { get; set; }
}
```

<span data-ttu-id="fff45-151">Para obtener más información sobre cómo utilizar el objeto `Func<T, T>` , vea <xref:System.Func%602>.</span><span class="sxs-lookup"><span data-stu-id="fff45-151">For more information about how to use of the `Func<T, T>` object, see <xref:System.Func%602>.</span></span>

<a name="types_of_imports"></a>

## <a name="types-of-imports"></a><span data-ttu-id="fff45-152">Tipos de importaciones</span><span class="sxs-lookup"><span data-stu-id="fff45-152">Types of Imports</span></span>

<span data-ttu-id="fff45-153">MEF admite varios tipos de importación: dinámica, diferida, de requisito previo y opcional.</span><span class="sxs-lookup"><span data-stu-id="fff45-153">MEF support several import types, including dynamic, lazy, prerequisite, and optional.</span></span>

### <a name="dynamic-imports"></a><span data-ttu-id="fff45-154">Importaciones dinámicas</span><span class="sxs-lookup"><span data-stu-id="fff45-154">Dynamic Imports</span></span>

<span data-ttu-id="fff45-155">En algunos casos, la clase que importa puede querer coincidir con exportaciones de cualquier tipo que tengan un nombre de contrato determinado.</span><span class="sxs-lookup"><span data-stu-id="fff45-155">In some cases, the importing class may want to match exports of any type that have a particular contract name.</span></span> <span data-ttu-id="fff45-156">En este escenario, la clase puede declarar una *importación dinámica*.</span><span class="sxs-lookup"><span data-stu-id="fff45-156">In this scenario, the class can declare a *dynamic import*.</span></span> <span data-ttu-id="fff45-157">La siguiente importación coincide con cualquier exportación que tenga el nombre de contrato "TheString".</span><span class="sxs-lookup"><span data-stu-id="fff45-157">The following import matches any export with contract name "TheString".</span></span>

```vb
Public Class MyClass1

    <Import("TheString")>
    Public Property MyAddin

End Class
```

```csharp
public class MyClass
{
    [Import("TheString")]
    public dynamic MyAddin { get; set; }
}
```

<span data-ttu-id="fff45-158">Cuando el tipo de contrato se deduce de la palabra clave `dynamic` , coincidirá con cualquier tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="fff45-158">When the contract type is inferred from the `dynamic` keyword, it will match any contract type.</span></span> <span data-ttu-id="fff45-159">En este caso, una importación debería especificar **siempre** un nombre de contrato con el que coincidir.</span><span class="sxs-lookup"><span data-stu-id="fff45-159">In this case, an import should **always** specify a contract name to match on.</span></span> <span data-ttu-id="fff45-160">(Si no se especifica ningún nombre de contrato, se considerará que la importación no coincide con ninguna exportación). Estas dos exportaciones coincidirían con la importación anterior.</span><span class="sxs-lookup"><span data-stu-id="fff45-160">(If no contract name is specified, the import will be considered to match no exports.) Both of the following exports would match the previous import.</span></span>

```vb
<Export("TheString", GetType(IMyAddin))>
Public Class MyLogger
    Implements IMyAddin

End Class

<Export("TheString")>
Public Class MyToolbar

End Class
```

```csharp
[Export("TheString", typeof(IMyAddin))]
public class MyLogger : IMyAddin { }

[Export("TheString")]
public class MyToolbar { }
```

<span data-ttu-id="fff45-161">Obviamente, la clase de importación se debe preparar para tratar con un objeto de tipo arbitrario.</span><span class="sxs-lookup"><span data-stu-id="fff45-161">Obviously, the importing class must be prepared to deal with an object of arbitrary type.</span></span>

### <a name="lazy-imports"></a><span data-ttu-id="fff45-162">Importaciones diferidas</span><span class="sxs-lookup"><span data-stu-id="fff45-162">Lazy Imports</span></span>

<span data-ttu-id="fff45-163">En algunos casos, la clase de importación puede requerir una referencia indirecta al objeto importado, para que no se creen instancias del objeto inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="fff45-163">In some cases, the importing class may require an indirect reference to the imported object, so that the object is not instantiated immediately.</span></span> <span data-ttu-id="fff45-164">En este escenario, la clase puede declarar una *importación diferida* utilizando un tipo de contrato `Lazy<T>`.</span><span class="sxs-lookup"><span data-stu-id="fff45-164">In this scenario, the class can declare a *lazy import* by using a contract type of `Lazy<T>`.</span></span> <span data-ttu-id="fff45-165">La siguiente propiedad de importación declara una importación diferida.</span><span class="sxs-lookup"><span data-stu-id="fff45-165">The following importing property declares a lazy import.</span></span>

```vb
Public Class MyClass1

    <Import()>
    Public Property MyAddin As Lazy(Of IMyAddin)

End Class
```

```csharp
public class MyClass
{
    [Import]
    public Lazy<IMyAddin> MyAddin { get; set; }
}
```

<span data-ttu-id="fff45-166">Desde el punto de vista del motor de composición, un tipo de contrato `Lazy<T>` se considera idéntico al tipo de contrato `T`.</span><span class="sxs-lookup"><span data-stu-id="fff45-166">From the point of view of the composition engine, a contract type of `Lazy<T>` is considered identical to contract type of `T`.</span></span> <span data-ttu-id="fff45-167">Por consiguiente, la importación anterior coincidiría con la siguiente exportación.</span><span class="sxs-lookup"><span data-stu-id="fff45-167">Therefore, the previous import would match the following export.</span></span>

```vb
<Export(GetType(IMyAddin))>
Public Class MyLogger
    Implements IMyAddin

End Class
```

```csharp
[Export(typeof(IMyAddin))]
public class MyLogger : IMyAddin { }
```

<span data-ttu-id="fff45-168">El nombre de contrato y el tipo de contrato se pueden especificar en el atributo `Import` para una importación diferida, tal y como se describe anteriormente en la sección "Conceptos básicos sobre importaciones y exportaciones".</span><span class="sxs-lookup"><span data-stu-id="fff45-168">The contract name and contract type can be specified in the `Import` attribute for a lazy import, as described earlier in the "Basic Imports and Exports" section.</span></span>

### <a name="prerequisite-imports"></a><span data-ttu-id="fff45-169">Importaciones de requisito previo</span><span class="sxs-lookup"><span data-stu-id="fff45-169">Prerequisite Imports</span></span>

<span data-ttu-id="fff45-170">El motor de composición, en respuesta a una solicitud directa o a la necesidad de completar una importación coincidente, crea normalmente las partes de MEF exportadas.</span><span class="sxs-lookup"><span data-stu-id="fff45-170">Exported MEF parts are typically created by the composition engine, in response to a direct request or the need to fill a matched import.</span></span> <span data-ttu-id="fff45-171">De forma predeterminada, al crear una parte, el motor de composición utiliza el constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="fff45-171">By default, when creating a part, the composition engine uses the parameter-less constructor.</span></span> <span data-ttu-id="fff45-172">Para que el motor use un constructor diferente, márquelo con el atributo `ImportingConstructor` .</span><span class="sxs-lookup"><span data-stu-id="fff45-172">To make the engine use a different constructor, you can mark it with the `ImportingConstructor` attribute.</span></span>

<span data-ttu-id="fff45-173">Cada parte solo puede tener un constructor para uso por parte del motor de composición.</span><span class="sxs-lookup"><span data-stu-id="fff45-173">Each part may have only one constructor for use by the composition engine.</span></span> <span data-ttu-id="fff45-174">No proporcionar ningún constructor sin parámetros y ningún atributo `ImportingConstructor`, o proporcionar más de un atributo `ImportingConstructor`, generará un error.</span><span class="sxs-lookup"><span data-stu-id="fff45-174">Providing no parameterless constructor and no `ImportingConstructor` attribute, or providing more than one `ImportingConstructor` attribute, will produce an error.</span></span>

<span data-ttu-id="fff45-175">Para completar los parámetros de un constructor marcados con el atributo `ImportingConstructor` , todos esos parámetros se declaran automáticamente como importaciones.</span><span class="sxs-lookup"><span data-stu-id="fff45-175">To fill the parameters of a constructor marked with the `ImportingConstructor` attribute, all of those parameters are automatically declared as imports.</span></span> <span data-ttu-id="fff45-176">Ésta es una manera conveniente de declarar importaciones que se utilizan durante la inicialización de las partes.</span><span class="sxs-lookup"><span data-stu-id="fff45-176">This is a convenient way to declare imports that are used during part initialization.</span></span> <span data-ttu-id="fff45-177">La siguiente clase utiliza `ImportingConstructor` para declarar una importación.</span><span class="sxs-lookup"><span data-stu-id="fff45-177">The following class uses `ImportingConstructor` to declare an import.</span></span>

```vb
Public Class MyClass1

    Private _theAddin As IMyAddin

    'Parameterless constructor will NOT be used
    'because the ImportingConstructor
    'attribute is present.
    Public Sub New()

    End Sub

    'This constructor will be used.
    'An import with contract type IMyAddin
    'is declared automatically.
    <ImportingConstructor()>
    Public Sub New(ByVal MyAddin As IMyAddin)
        _theAddin = MyAddin
    End Sub

End Class
```

```csharp
public class MyClass
{
    private IMyAddin _theAddin;

    //Parameterless constructor will NOT be
    //used because the ImportingConstructor
    //attribute is present.
    public MyClass() { }

    //This constructor will be used.
    //An import with contract type IMyAddin is
    //declared automatically.
    [ImportingConstructor]
    public MyClass(IMyAddin MyAddin)
    {
        _theAddin = MyAddin;
    }
}
```

<span data-ttu-id="fff45-178">De forma predeterminada, el atributo `ImportingConstructor` usa tipos de contrato y nombres de contrato deducidos para todas las importaciones de parámetros.</span><span class="sxs-lookup"><span data-stu-id="fff45-178">By default, the `ImportingConstructor` attribute uses inferred contract types and contract names for all of the parameter imports.</span></span> <span data-ttu-id="fff45-179">Es posible reemplazar esto decorando los parámetros con atributos `Import` , que pueden definir después explícitamente el tipo y el nombre del contrato.</span><span class="sxs-lookup"><span data-stu-id="fff45-179">It is possible to override this by decorating the parameters with `Import` attributes, which can then define the contract type and contract name explicitly.</span></span> <span data-ttu-id="fff45-180">El siguiente código muestra un constructor que utiliza esta sintaxis para importar una clase derivada en lugar de una clase principal.</span><span class="sxs-lookup"><span data-stu-id="fff45-180">The following code demonstrates a constructor that uses this syntax to import a derived class instead of a parent class.</span></span>

```vb
<ImportingConstructor()>
Public Sub New(<Import(GetType(IMySubAddin))> ByVal MyAddin As IMyAddin)

End Sub
```

```csharp
[ImportingConstructor]
public MyClass([Import(typeof(IMySubAddin))]IMyAddin MyAddin)
{
    _theAddin = MyAddin;
}
```

<span data-ttu-id="fff45-181">En concreto, debería tener precaución con los parámetros de colección.</span><span class="sxs-lookup"><span data-stu-id="fff45-181">In particular, you should be careful with collection parameters.</span></span> <span data-ttu-id="fff45-182">Por ejemplo, si especifica `ImportingConstructor` en un constructor con un parámetro de tipo `IEnumerable<int>`, la importación coincidirá con una exportación única de tipo `IEnumerable<int>`, en lugar de con un conjunto de exportaciones de tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="fff45-182">For example, if you specify `ImportingConstructor` on a constructor with a parameter of type `IEnumerable<int>`, the import will match a single export of type `IEnumerable<int>`, instead of a set of exports of type `int`.</span></span> <span data-ttu-id="fff45-183">Para coincidir con un conjunto de exportaciones de tipo `int`, tiene que decorar el parámetro con el atributo `ImportMany` .</span><span class="sxs-lookup"><span data-stu-id="fff45-183">To match a set of exports of type `int`, you have to decorate the parameter with the `ImportMany` attribute.</span></span>

<span data-ttu-id="fff45-184">Los parámetros declarados como importaciones por el atributo `ImportingConstructor` también se marcan como *importaciones de requisito previo*.</span><span class="sxs-lookup"><span data-stu-id="fff45-184">Parameters declared as imports by the `ImportingConstructor` attribute are also marked as *prerequisite imports*.</span></span> <span data-ttu-id="fff45-185">Normalmente MEF permite que las exportaciones e importaciones formen un *ciclo*.</span><span class="sxs-lookup"><span data-stu-id="fff45-185">MEF normally allows exports and imports to form a *cycle*.</span></span> <span data-ttu-id="fff45-186">Por ejemplo, un ciclo es donde el objeto A importa un objeto B, que a su vez importa el objeto A. En circunstancias normales, un ciclo no es un problema y el contenedor de composición construye ambos objetos normalmente.</span><span class="sxs-lookup"><span data-stu-id="fff45-186">For example, a cycle is where object A imports object B, which in turn imports object A. Under ordinary circumstances, a cycle is not a problem, and the composition container constructs both objects normally.</span></span>

<span data-ttu-id="fff45-187">Cuando el constructor de una parte requiere un valor importado, ese objeto no puede participar en un ciclo.</span><span class="sxs-lookup"><span data-stu-id="fff45-187">When an imported value is required by the constructor of a part, that object cannot participate in a cycle.</span></span> <span data-ttu-id="fff45-188">Si el objeto A requiere para poder construirse que antes se construya ese objeto B, y el objeto B importa el objeto A, el ciclo no se podrá resolver y se producirá un error de composición.</span><span class="sxs-lookup"><span data-stu-id="fff45-188">If object A requires that object B be constructed before it can be constructed itself, and object B imports object A, then the cycle will be unable to resolve and a composition error will occur.</span></span> <span data-ttu-id="fff45-189">Las importaciones declaradas en parámetros de constructor son, por consiguiente, importaciones de requisito previo, las cuales deben completarse para que las exportaciones del objeto que las requiere se puedan utilizar.</span><span class="sxs-lookup"><span data-stu-id="fff45-189">Imports declared on constructor parameters are therefore prerequisite imports, which must all be filled before any of the exports from the object that requires them can be used.</span></span>

### <a name="optional-imports"></a><span data-ttu-id="fff45-190">Importaciones opcionales</span><span class="sxs-lookup"><span data-stu-id="fff45-190">Optional Imports</span></span>

<span data-ttu-id="fff45-191">El atributo `Import` especifica un requisito para que la parte funcione.</span><span class="sxs-lookup"><span data-stu-id="fff45-191">The `Import` attribute specifies a requirement for the part to function.</span></span> <span data-ttu-id="fff45-192">Si no se puede satisfacer una importación, se producirá un error en la composición de esa parte, que no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="fff45-192">If an import cannot be fulfilled, the composition of that part will fail and the part will not be available.</span></span>

<span data-ttu-id="fff45-193">Puede especificar que una importación sea *opcional* utilizando la propiedad `AllowDefault` .</span><span class="sxs-lookup"><span data-stu-id="fff45-193">You can specify that an import is *optional* by using the `AllowDefault` property.</span></span> <span data-ttu-id="fff45-194">En este caso, la composición tendrá éxito aun cuando la importación no coincida con las exportaciones disponibles, y la propiedad de importación estará establecida en el valor predeterminado para su tipo de propiedad (`null` para las propiedades de objeto, `false` para valores booleanos o cero para las propiedades numéricas). La siguiente clase utiliza una importación opcional.</span><span class="sxs-lookup"><span data-stu-id="fff45-194">In this case, the composition will succeed even if the import does not match any available exports, and the importing property will be set to the default for its property type (`null` for object properties, `false` for Booleans, or zero for numeric properties.) The following class uses an optional import.</span></span>

```vb
Public Class MyClass1

    <Import(AllowDefault:=True)>
    Public Property thePlugin As Plugin

    'If no matching export is available,
    'thePlugin will be set to null.
End Class
```

```csharp
public class MyClass
{
    [Import(AllowDefault = true)]
    public Plugin thePlugin { get; set; }

    //If no matching export is available,
    //thePlugin will be set to null.
}
```

### <a name="importing-multiple-objects"></a><span data-ttu-id="fff45-195">Importar varios objetos</span><span class="sxs-lookup"><span data-stu-id="fff45-195">Importing Multiple Objects</span></span>

<span data-ttu-id="fff45-196">Se creará el atributo `Import` correctamente solo cuando coincida con una y solo una exportación.</span><span class="sxs-lookup"><span data-stu-id="fff45-196">The `Import` attribute will only be successfully composed when it matches one and only one export.</span></span> <span data-ttu-id="fff45-197">En otros casos se generará un error de composición.</span><span class="sxs-lookup"><span data-stu-id="fff45-197">Other cases will produce a composition error.</span></span> <span data-ttu-id="fff45-198">Para importar más de una exportación que coincida con el mismo contrato, utilice el atributo `ImportMany` .</span><span class="sxs-lookup"><span data-stu-id="fff45-198">To import more than one export that matches the same contract, use the `ImportMany` attribute.</span></span> <span data-ttu-id="fff45-199">Las importaciones marcadas con este atributo son siempre opcionales.</span><span class="sxs-lookup"><span data-stu-id="fff45-199">Imports marked with this attribute are always optional.</span></span> <span data-ttu-id="fff45-200">Por ejemplo, no se producirá un error en la composición si no hay ninguna exportación coincidente presente.</span><span class="sxs-lookup"><span data-stu-id="fff45-200">For example, composition will not fail if no matching exports are present.</span></span> <span data-ttu-id="fff45-201">La siguiente clase importa cualquier número de exportaciones de tipo `IMyAddin`.</span><span class="sxs-lookup"><span data-stu-id="fff45-201">The following class imports any number of exports of type `IMyAddin`.</span></span>

```vb
Public Class MyClass1

    <ImportMany()>
    Public Property MyAddin As IEnumerable(Of IMyAddin)

End Class
```

```csharp
public class MyClass
{
    [ImportMany]
    public IEnumerable<IMyAddin> MyAddin { get; set; }
}
```

<span data-ttu-id="fff45-202">Se puede tener acceso a la matriz importada con métodos y sintaxis `IEnumerable<T>` normales.</span><span class="sxs-lookup"><span data-stu-id="fff45-202">The imported array can be accessed by using ordinary `IEnumerable<T>` syntax and methods.</span></span> <span data-ttu-id="fff45-203">También es posible utilizar una matriz normal (`IMyAddin[]`) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="fff45-203">It is also possible to use an ordinary array (`IMyAddin[]`) instead.</span></span>

<span data-ttu-id="fff45-204">Este modelo puede ser muy importante si se usa en combinación con la sintaxis `Lazy<T>` .</span><span class="sxs-lookup"><span data-stu-id="fff45-204">This pattern can be very important when you use it in combination with the `Lazy<T>` syntax.</span></span> <span data-ttu-id="fff45-205">Por ejemplo, utilizando `ImportMany`, `IEnumerable<T>`y `Lazy<T>`, puede importar las referencias indirectas a cualquier número de objetos y crear instancias de los que resultan necesarios únicamente.</span><span class="sxs-lookup"><span data-stu-id="fff45-205">For example, by using `ImportMany`, `IEnumerable<T>`, and `Lazy<T>`, you can import indirect references to any number of objects and only instantiate the ones that become necessary.</span></span> <span data-ttu-id="fff45-206">La siguiente clase muestra este modelo.</span><span class="sxs-lookup"><span data-stu-id="fff45-206">The following class shows this pattern.</span></span>

```vb
Public Class MyClass1

    <ImportMany()>
    Public Property MyAddin As IEnumerable(Of Lazy(Of IMyAddin))

End Class
```

```csharp
public class MyClass
{
    [ImportMany]
    public IEnumerable<Lazy<IMyAddin>> MyAddin { get; set; }
}
```

<a name="avoiding_discovery"></a>

## <a name="avoiding-discovery"></a><span data-ttu-id="fff45-207">Evitar la detección</span><span class="sxs-lookup"><span data-stu-id="fff45-207">Avoiding Discovery</span></span>

<span data-ttu-id="fff45-208">En algunos casos, puede desear evitar que una parte sea detectada como parte de un catálogo.</span><span class="sxs-lookup"><span data-stu-id="fff45-208">In some cases, you may want to prevent a part from being discovered as part of a catalog.</span></span> <span data-ttu-id="fff45-209">Por ejemplo, la parte puede ser una clase base pensada para que se herede de ella, pero no para usarla.</span><span class="sxs-lookup"><span data-stu-id="fff45-209">For example, the part may be a base class intended to be inherited from, but not used.</span></span> <span data-ttu-id="fff45-210">Hay dos maneras de lograrlo.</span><span class="sxs-lookup"><span data-stu-id="fff45-210">There are two ways to accomplish this.</span></span> <span data-ttu-id="fff45-211">Primero, puede utilizar la palabra clave `abstract` en la clase de la parte.</span><span class="sxs-lookup"><span data-stu-id="fff45-211">First, you can use the `abstract` keyword on the part class.</span></span> <span data-ttu-id="fff45-212">Las clases abstractas nunca proporcionan exportaciones, aunque pueden proporcionar exportaciones heredadas a las clases que derivan de ellas.</span><span class="sxs-lookup"><span data-stu-id="fff45-212">Abstract classes never provide exports, although they can provide inherited exports to classes that derive from them.</span></span>

<span data-ttu-id="fff45-213">Si la clase no se puede hacer abstracta, puede decorarla con el atributo `PartNotDiscoverable` .</span><span class="sxs-lookup"><span data-stu-id="fff45-213">If the class cannot be made abstract, you can decorate it with the `PartNotDiscoverable` attribute.</span></span> <span data-ttu-id="fff45-214">Una parte decorada con este atributo no estará incluida en ningún catálogo.</span><span class="sxs-lookup"><span data-stu-id="fff45-214">A part decorated with this attribute will not be included in any catalogs.</span></span> <span data-ttu-id="fff45-215">En el siguiente ejemplo se muestran estos modelos.</span><span class="sxs-lookup"><span data-stu-id="fff45-215">The following example demonstrates these patterns.</span></span> <span data-ttu-id="fff45-216">El catálogo detectará`DataOne` .</span><span class="sxs-lookup"><span data-stu-id="fff45-216">`DataOne` will be discovered by the catalog.</span></span> <span data-ttu-id="fff45-217">Puesto que `DataTwo` es abstracta, no se detectará.</span><span class="sxs-lookup"><span data-stu-id="fff45-217">Since `DataTwo` is abstract, it will not be discovered.</span></span> <span data-ttu-id="fff45-218">Puesto que `DataThree` utilizó el atributo `PartNotDiscoverable` , no se detectará.</span><span class="sxs-lookup"><span data-stu-id="fff45-218">Since `DataThree` used the `PartNotDiscoverable` attribute, it will not be discovered.</span></span>

```vb
<Export()>
Public Class DataOne
    'This part will be discovered
    'as normal by the catalog.
End Class

<Export()>
Public MustInherit Class DataTwo
    'This part will not be discovered
    'by the catalog.
End Class

<PartNotDiscoverable()>
<Export()>
Public Class DataThree
    'This part will also not be discovered
    'by the catalog.
End Class
```

```csharp
[Export]
public class DataOne
{
    //This part will be discovered
    //as normal by the catalog.
}

[Export]
public abstract class DataTwo
{
    //This part will not be discovered
    //by the catalog.
}

[PartNotDiscoverable]
[Export]
public class DataThree
{
    //This part will also not be discovered
    //by the catalog.
}
```

<a name="metadata_and_metadata_views"></a>

## <a name="metadata-and-metadata-views"></a><span data-ttu-id="fff45-219">Metadatos y vistas de metadatos</span><span class="sxs-lookup"><span data-stu-id="fff45-219">Metadata and Metadata Views</span></span>

<span data-ttu-id="fff45-220">Las exportaciones pueden proporcionar información adicional sobre ellas, lo que se conoce como *metadatos*.</span><span class="sxs-lookup"><span data-stu-id="fff45-220">Exports can provide additional information about themselves known as *metadata*.</span></span> <span data-ttu-id="fff45-221">Los metadatos se pueden utilizar para llevar propiedades del objeto exportado a la parte de importación.</span><span class="sxs-lookup"><span data-stu-id="fff45-221">Metadata can be used to convey properties of the exported object to the importing part.</span></span> <span data-ttu-id="fff45-222">La parte de importación puede utilizar estos datos para decidir qué exportaciones usar o recopilar información sobre una exportación sin tener que construirla.</span><span class="sxs-lookup"><span data-stu-id="fff45-222">The importing part can use this data to decide which exports to use, or to gather information about an export without having to construct it.</span></span> <span data-ttu-id="fff45-223">Por esta razón, una importación debe ser diferida para utilizar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="fff45-223">For this reason, an import must be lazy to use metadata.</span></span>

<span data-ttu-id="fff45-224">Para utilizar los metadatos, se declara normalmente una interfaz conocida como *vista de metadatos*, que declara qué metadatos estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="fff45-224">To use metadata, you typically declare an interface known as a *metadata view*, which declares what metadata will be available.</span></span> <span data-ttu-id="fff45-225">La interfaz de vista de los metadatos solo debe tener propiedades y esas propiedades deben tener descriptores de acceso `get` .</span><span class="sxs-lookup"><span data-stu-id="fff45-225">The metadata view interface must have only properties, and those properties must have `get` accessors.</span></span> <span data-ttu-id="fff45-226">La siguiente interfaz es ejemplo de una vista de metadatos.</span><span class="sxs-lookup"><span data-stu-id="fff45-226">The following interface is an example metadata view.</span></span>

```vb
Public Interface IPluginMetadata

    ReadOnly Property Name As String

    <DefaultValue(1)>
    ReadOnly Property Version As Integer

End Interface
```

```csharp
public interface IPluginMetadata
{
    string Name { get; }

    [DefaultValue(1)]
    int Version { get; }
}
```

<span data-ttu-id="fff45-227">También es posible utilizar una colección genérica, `IDictionary<string, object>`, como vista de metadatos, pero esto anula las ventajas de la comprobación de tipos y se debe evitar.</span><span class="sxs-lookup"><span data-stu-id="fff45-227">It is also possible to use a generic collection, `IDictionary<string, object>`, as a metadata view, but this forfeits the benefits of type checking and should be avoided.</span></span>

<span data-ttu-id="fff45-228">Normalmente, todas las propiedades nombradas en la vista de metadatos son obligatorias y las exportaciones que no las proporcionen no se considerarán una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="fff45-228">Ordinarily, all of the properties named in the metadata view are required, and any exports that do not provide them will not be considered a match.</span></span> <span data-ttu-id="fff45-229">El atributo `DefaultValue` especifica que una propiedad es opcional.</span><span class="sxs-lookup"><span data-stu-id="fff45-229">The `DefaultValue` attribute specifies that a property is optional.</span></span> <span data-ttu-id="fff45-230">Si la propiedad no está incluida, se le asignará el valor predeterminado especificado como un parámetro de `DefaultValue`.</span><span class="sxs-lookup"><span data-stu-id="fff45-230">If the property is not included, it will be assigned the default value specified as a parameter of `DefaultValue`.</span></span> <span data-ttu-id="fff45-231">A continuación se incluyen dos clases diferentes decoradas con metadatos.</span><span class="sxs-lookup"><span data-stu-id="fff45-231">The following are two different classes decorated with metadata.</span></span> <span data-ttu-id="fff45-232">Ambas clases coincidirían con la vista de metadatos anterior.</span><span class="sxs-lookup"><span data-stu-id="fff45-232">Both of these classes would match the previous metadata view.</span></span>

```vb
<Export(GetType(IPlugin))>
<ExportMetadata("Name", "Logger")>
<ExportMetadata("Version", 4)>
Public Class MyLogger
    Implements IPlugin

End Class

'Version is not required because of the DefaultValue
<Export(GetType(IPlugin))>
<ExportMetadata("Name", "Disk Writer")>
Public Class DWriter
    Implements IPlugin

End Class
```

```csharp
[Export(typeof(IPlugin)),
    ExportMetadata("Name", "Logger"),
    ExportMetadata("Version", 4)]
public class Logger : IPlugin
{
}

[Export(typeof(IPlugin)),
    ExportMetadata("Name", "Disk Writer")]
    //Version is not required because of the DefaultValue
public class DWriter : IPlugin
{
}
```

<span data-ttu-id="fff45-233">Los metadatos se expresan detrás del atributo `Export` mediante el atributo `ExportMetadata` .</span><span class="sxs-lookup"><span data-stu-id="fff45-233">Metadata is expressed after the `Export` attribute by using the `ExportMetadata` attribute.</span></span> <span data-ttu-id="fff45-234">Cada componente de los metadatos consta de un par de nombre/valor.</span><span class="sxs-lookup"><span data-stu-id="fff45-234">Each piece of metadata is composed of a name/value pair.</span></span> <span data-ttu-id="fff45-235">La parte del nombre de los metadatos debe coincidir con el nombre de la propiedad adecuada en la vista de metadatos y el valor se asignará a esa propiedad.</span><span class="sxs-lookup"><span data-stu-id="fff45-235">The name portion of the metadata must match the name of the appropriate property in the metadata view, and the value will be assigned to that property.</span></span>

<span data-ttu-id="fff45-236">Es el importador el que especifica qué vista de metadatos se usará, en caso de que se use alguna.</span><span class="sxs-lookup"><span data-stu-id="fff45-236">It is the importer that specifies what metadata view, if any, will be in use.</span></span> <span data-ttu-id="fff45-237">Una importación con metadatos se declara como una importación diferida, con la interfaz de metadatos como el segundo parámetro de tipo para `Lazy<T,T>`.</span><span class="sxs-lookup"><span data-stu-id="fff45-237">An import with metadata is declared as a lazy import, with the metadata interface as the second type parameter to `Lazy<T,T>`.</span></span> <span data-ttu-id="fff45-238">La siguiente clase importa la parte anterior con metadatos.</span><span class="sxs-lookup"><span data-stu-id="fff45-238">The following class imports the previous part with metadata.</span></span>

```vb
Public Class Addin

    <Import()>
    Public Property plugin As Lazy(Of IPlugin, IPluginMetadata)
End Class
```

```csharp
public class Addin
{
    [Import]
    public Lazy<IPlugin, IPluginMetadata> plugin;
}
```

<span data-ttu-id="fff45-239">En muchos casos, deseará combinar los metadatos con el atributo `ImportMany` , con el fin de analizar las importaciones disponibles y elegir y crear instancias de una sola, o filtrará una colección para que coincida con determinada condición.</span><span class="sxs-lookup"><span data-stu-id="fff45-239">In many cases, you will want to combine metadata with the `ImportMany` attribute, in order to parse through the available imports and choose and instantiate only one, or filter a collection to match a certain condition.</span></span> <span data-ttu-id="fff45-240">La siguiente clase únicamente crea instancias de los objetos `IPlugin` que tienen el valor `Name` "Logger".</span><span class="sxs-lookup"><span data-stu-id="fff45-240">The following class instantiates only `IPlugin` objects that have the `Name` value "Logger".</span></span>

```vb
Public Class User

    <ImportMany()>
    Public Property plugins As IEnumerable(Of Lazy(Of IPlugin, IPluginMetadata))

    Public Function InstantiateLogger() As IPlugin

        Dim logger As IPlugin
        logger = Nothing

        For Each Plugin As Lazy(Of IPlugin, IPluginMetadata) In plugins
            If Plugin.Metadata.Name = "Logger" Then
                logger = Plugin.Value
            End If
        Next
        Return logger
    End Function

End Class
```

```csharp
public class User
{
    [ImportMany]
    public IEnumerable<Lazy<IPlugin, IPluginMetadata>> plugins;

    public IPlugin InstantiateLogger()
    {
        IPlugin logger = null;

        foreach (Lazy<IPlugin, IPluginMetadata> plugin in plugins)
        {
            if (plugin.Metadata.Name == "Logger")
                logger = plugin.Value;
        }
        return logger;
    }
}
```

<a name="import_and_export_inheritance"></a>

## <a name="import-and-export-inheritance"></a><span data-ttu-id="fff45-241">Herencia de las importaciones y exportaciones</span><span class="sxs-lookup"><span data-stu-id="fff45-241">Import and Export Inheritance</span></span>

<span data-ttu-id="fff45-242">Si una clase hereda de una parte, esa clase también se puede convertir en una parte.</span><span class="sxs-lookup"><span data-stu-id="fff45-242">If a class inherits from a part, that class may also become a part.</span></span> <span data-ttu-id="fff45-243">Las importaciones siempre son heredadas por las subclases.</span><span class="sxs-lookup"><span data-stu-id="fff45-243">Imports are always inherited by subclasses.</span></span> <span data-ttu-id="fff45-244">Por consiguiente, una subclase de una parte siempre será una parte, con las mismas importaciones que su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="fff45-244">Therefore, a subclass of a part will always be a part, with the same imports as its parent class.</span></span>

<span data-ttu-id="fff45-245">Las exportaciones declaradas con el atributo `Export` no son heredadas por las subclases.</span><span class="sxs-lookup"><span data-stu-id="fff45-245">Exports declared by using the `Export` attribute are not inherited by subclasses.</span></span> <span data-ttu-id="fff45-246">Sin embargo, una parte se puede exportar utilizando el atributo `InheritedExport` .</span><span class="sxs-lookup"><span data-stu-id="fff45-246">However, a part can export itself by using the `InheritedExport` attribute.</span></span> <span data-ttu-id="fff45-247">Las subclases de la parte heredarán y proporcionarán la misma exportación, incluido el nombre y el tipo del contrato.</span><span class="sxs-lookup"><span data-stu-id="fff45-247">Subclasses of the part will inherit and provide the same export, including contract name and contract type.</span></span> <span data-ttu-id="fff45-248">A diferencia de un atributo `Export` , `InheritedExport` solo se puede aplicar en el nivel de clase, no en el nivel de miembro.</span><span class="sxs-lookup"><span data-stu-id="fff45-248">Unlike an `Export` attribute, `InheritedExport` can be applied only at the class level, and not at the member level.</span></span> <span data-ttu-id="fff45-249">Por consiguiente, las exportaciones de nivel de miembro nunca pueden heredarse.</span><span class="sxs-lookup"><span data-stu-id="fff45-249">Therefore, member-level exports can never be inherited.</span></span>

<span data-ttu-id="fff45-250">Las siguientes cuatro clases muestran los principios de la herencia de la importación y la exportación.</span><span class="sxs-lookup"><span data-stu-id="fff45-250">The following four classes demonstrate the principles of import and export inheritance.</span></span> <span data-ttu-id="fff45-251">`NumTwo` hereda de `NumOne`, de modo que `NumTwo` importará `IMyData`.</span><span class="sxs-lookup"><span data-stu-id="fff45-251">`NumTwo` inherits from `NumOne`, so `NumTwo` will import `IMyData`.</span></span> <span data-ttu-id="fff45-252">Las exportaciones normales no se heredan, de modo que `NumTwo` no exportará nada.</span><span class="sxs-lookup"><span data-stu-id="fff45-252">Ordinary exports are not inherited, so `NumTwo` will not export anything.</span></span> <span data-ttu-id="fff45-253">`NumFour` hereda de `NumThree`.</span><span class="sxs-lookup"><span data-stu-id="fff45-253">`NumFour` inherits from `NumThree`.</span></span> <span data-ttu-id="fff45-254">Dado que `NumThree` utilizó `InheritedExport`, `NumFour` tiene una exportación con tipo de contrato `NumThree`.</span><span class="sxs-lookup"><span data-stu-id="fff45-254">Because `NumThree` used `InheritedExport`, `NumFour` has one export with contract type `NumThree`.</span></span> <span data-ttu-id="fff45-255">Las exportaciones de nivel de miembro nunca se heredan, de modo que `IMyData` no se exporta.</span><span class="sxs-lookup"><span data-stu-id="fff45-255">Member-level exports are never inherited, so `IMyData` is not exported.</span></span>

```vb
<Export()>
Public Class NumOne
    <Import()>
    Public Property MyData As IMyData
End Class

Public Class NumTwo
    Inherits NumOne

    'Imports are always inherited, so NumTwo will
    'Import IMyData

    'Ordinary exports are not inherited, so
    'NumTwo will NOT export anything.  As a result it
    'will not be discovered by the catalog!

End Class

<InheritedExport()>
Public Class NumThree

    <Export()>
    Public Property MyData As IMyData

    'This part provides two exports, one of
    'contract type NumThree, and one of
    'contract type IMyData.

End Class

Public Class NumFour
    Inherits NumThree

    'Because NumThree used InheritedExport,
    'this part has one export with contract
    'type NumThree.

    'Member-level exports are never inherited,
    'so IMyData is not exported.

End Class
```

```csharp
[Export]
public class NumOne
{
    [Import]
    public IMyData MyData { get; set; }
}

public class NumTwo : NumOne
{
    //Imports are always inherited, so NumTwo will
    //import IMyData.

    //Ordinary exports are not inherited, so
    //NumTwo will NOT export anything. As a result it
    //will not be discovered by the catalog!
}

[InheritedExport]
public class NumThree
{
    [Export]
    Public IMyData MyData { get; set; }

    //This part provides two exports, one of
    //contract type NumThree, and one of
    //contract type IMyData.
}

public class NumFour : NumThree
{
    //Because NumThree used InheritedExport,
    //this part has one export with contract
    //type NumThree.

    //Member-level exports are never inherited,
    //so IMyData is not exported.
}
```

<span data-ttu-id="fff45-256">Si hay metadatos asociados al atributo `InheritedExport` , también se heredarán.</span><span class="sxs-lookup"><span data-stu-id="fff45-256">If there is metadata associated with an `InheritedExport` attribute, that metadata will also be inherited.</span></span> <span data-ttu-id="fff45-257">(Para obtener más información, vea la sección anterior "Metadatos y vistas de metadatos"). La subclase no puede modificar los metadatos heredados.</span><span class="sxs-lookup"><span data-stu-id="fff45-257">(For more information, see the earlier "Metadata and Metadata Views" section.) Inherited metadata cannot be modified by the subclass.</span></span> <span data-ttu-id="fff45-258">Sin embargo, si se vuelve a declarar el atributo `InheritedExport` con el mismo nombre y tipo de contrato, pero con nuevos metadatos, la subclase puede reemplazar los metadatos heredados por los nuevos metadatos.</span><span class="sxs-lookup"><span data-stu-id="fff45-258">However, by re-declaring the `InheritedExport` attribute with the same contract name and contract type, but with new metadata, the subclass can replace the inherited metadata with new metadata.</span></span> <span data-ttu-id="fff45-259">La clase siguiente muestra este principio.</span><span class="sxs-lookup"><span data-stu-id="fff45-259">The following class demonstrates this principle.</span></span> <span data-ttu-id="fff45-260">La parte `MegaLogger` hereda de `Logger` e incluye el atributo `InheritedExport` .</span><span class="sxs-lookup"><span data-stu-id="fff45-260">The `MegaLogger` part inherits from `Logger` and includes the `InheritedExport` attribute.</span></span> <span data-ttu-id="fff45-261">Puesto que `MegaLogger` vuelve a declarar nuevos metadatos denominados Status, no hereda los metadatos Name y Version de `Logger`.</span><span class="sxs-lookup"><span data-stu-id="fff45-261">Since `MegaLogger` re-declares new metadata named Status, it does not inherit the Name and Version metadata from `Logger`.</span></span>

```vb
<InheritedExport(GetType(IPlugin))>
<ExportMetadata("Name", "Logger")>
<ExportMetadata("Version", 4)>
Public Class Logger
    Implements IPlugin

    'Exports with contract type IPlugin
    'and metadata "Name" and "Version".
End Class

Public Class SuperLogger
    Inherits Logger

    'Exports with contract type IPlugin and
    'metadata "Name" and "Version", exactly the same
    'as the Logger class.

End Class

<InheritedExport(GetType(IPlugin))>
<ExportMetadata("Status", "Green")>
Public Class MegaLogger
    Inherits Logger

    'Exports with contract type IPlugin and
    'metadata "Status" only. Re-declaring
    'the attribute replaces all metadata.

End Class
```

```csharp
[InheritedExport(typeof(IPlugin)),
    ExportMetadata("Name", "Logger"),
    ExportMetadata("Version", 4)]
public class Logger : IPlugin
{
    //Exports with contract type IPlugin and
    //metadata "Name" and "Version".
}

public class SuperLogger : Logger
{
    //Exports with contract type IPlugin and
    //metadata "Name" and "Version", exactly the same
    //as the Logger class.
}

[InheritedExport(typeof(IPlugin)),
    ExportMetadata("Status", "Green")]
public class MegaLogger : Logger        {
    //Exports with contract type IPlugin and
    //metadata "Status" only. Re-declaring
    //the attribute replaces all metadata.
}
```

<span data-ttu-id="fff45-262">Al volver a declarar el atributo `InheritedExport` para reemplazar los metadatos, asegúrese de que los tipos de contrato son los mismos.</span><span class="sxs-lookup"><span data-stu-id="fff45-262">When re-declaring the `InheritedExport` attribute to override metadata, make sure that the contract types are the same.</span></span> <span data-ttu-id="fff45-263">(En el ejemplo anterior, `IPlugin` es el tipo del contrato). Si difieren, el segundo atributo creará, en lugar de reemplazar, una segunda exportación independiente de la parte.</span><span class="sxs-lookup"><span data-stu-id="fff45-263">(In the previous example, `IPlugin` is the contract type.) If they differ, instead of overriding, the second attribute will create a second, independent export from the part.</span></span> <span data-ttu-id="fff45-264">Generalmente, esto significa que tendrá que especificar el tipo de contrato explícitamente al reemplazar un atributo `InheritedExport` , como se muestra en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="fff45-264">Generally, this means that you will have to explicitly specify the contract type when you override an `InheritedExport` attribute, as shown in the previous example.</span></span>

<span data-ttu-id="fff45-265">Puesto que no se pueden crear instancias de interfaces directamente, por lo general no se pueden decorar con atributos `Export` o `Import` .</span><span class="sxs-lookup"><span data-stu-id="fff45-265">Since interfaces cannot be instantiated directly, they generally cannot be decorated with `Export` or `Import` attributes.</span></span> <span data-ttu-id="fff45-266">Sin embargo, una interfaz se puede decorar con un atributo `InheritedExport` en el nivel de interfaz y esa exportación junto con los metadatos asociados las heredarán las clases implementadoras.</span><span class="sxs-lookup"><span data-stu-id="fff45-266">However, an interface can be decorated with an `InheritedExport` attribute at the interface level, and that export along with any associated metadata will be inherited by any implementing classes.</span></span> <span data-ttu-id="fff45-267">Sin embargo, la propia interfaz no estará disponible como una parte.</span><span class="sxs-lookup"><span data-stu-id="fff45-267">The interface itself will not be available as a part, however.</span></span>

<a name="custom_export_attributes"></a>

## <a name="custom-export-attributes"></a><span data-ttu-id="fff45-268">Atributos de exportación personalizados</span><span class="sxs-lookup"><span data-stu-id="fff45-268">Custom Export Attributes</span></span>

<span data-ttu-id="fff45-269">Los atributos de exportación básicos, `Export` e `InheritedExport`, se pueden extender para incluir los metadatos como propiedades de atributo.</span><span class="sxs-lookup"><span data-stu-id="fff45-269">The basic export attributes, `Export` and `InheritedExport`, can be extended to include metadata as attribute properties.</span></span> <span data-ttu-id="fff45-270">Esta técnica es útil para aplicar metadatos similares a muchas partes o para crear un árbol de herencia de atributos de metadatos.</span><span class="sxs-lookup"><span data-stu-id="fff45-270">This technique is useful for applying similar metadata to many parts, or creating an inheritance tree of metadata attributes.</span></span>

<span data-ttu-id="fff45-271">Un atributo personalizado puede especificar el tipo de contrato, el nombre del contrato o cualquier otro tipo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="fff45-271">A custom attribute can specify the contract type, the contract name, or any other metadata.</span></span> <span data-ttu-id="fff45-272">Para definir un atributo personalizado, una clase que hereda de `ExportAttribute` (o `InheritedExportAttribute`) se debe decorar con el atributo `MetadataAttribute` .</span><span class="sxs-lookup"><span data-stu-id="fff45-272">In order to define a custom attribute, a class inheriting from `ExportAttribute` (or `InheritedExportAttribute`) must be decorated with the `MetadataAttribute` attribute.</span></span> <span data-ttu-id="fff45-273">La siguiente clase define un atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="fff45-273">The following class defines a custom attribute.</span></span>

```vb
<MetadataAttribute()>
<AttributeUsage(AttributeTargets.Class, AllowMultiple:=false)>
Public Class MyAttribute
    Inherits ExportAttribute

    Public Property MyMetadata As String

    Public Sub New(ByVal myMetadata As String)
        MyBase.New(GetType(IMyAddin))

        myMetadata = myMetadata
    End Sub

End Class
```

```csharp
[MetadataAttribute]
[AttributeUsage(AttributeTargets.Class, AllowMultiple=false)]
public class MyAttribute : ExportAttribute
{
    public MyAttribute(string myMetadata)
        : base(typeof(IMyAddin))
    {
        MyMetadata = myMetadata;
    }

    public string MyMetadata { get; private set; }
}
```

<span data-ttu-id="fff45-274">Esta clase define un atributo personalizado denominado `MyAttribute` con tipo de contrato `IMyAddin` y algunos metadatos denominados `MyMetadata`.</span><span class="sxs-lookup"><span data-stu-id="fff45-274">This class defines a custom attribute named `MyAttribute` with contract type `IMyAddin` and some metadata named `MyMetadata`.</span></span> <span data-ttu-id="fff45-275">Se considera que todas las propiedades de una clase marcadas con el atributo `MetadataAttribute` son metadatos definidos en el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="fff45-275">All properties in a class marked with the `MetadataAttribute` attribute are considered to be metadata defined in the custom attribute.</span></span> <span data-ttu-id="fff45-276">Las dos declaraciones siguientes son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="fff45-276">The following two declarations are equivalent.</span></span>

```vb
<Export(GetType(IMyAddin))>
<ExportMetadata("MyMetadata", "theData")>
Public Property myAddin As MyAddin
```

```vb
<MyAttribute("theData")>
Public Property myAddin As MyAddin
```

```csharp
[Export(typeof(IMyAddin)),
    ExportMetadata("MyMetadata", "theData")]
public MyAddin myAddin { get; set; }
```

```csharp
[MyAttribute("theData")]
public MyAddin myAddin { get; set; }
```

<span data-ttu-id="fff45-277">En la primera declaración, el tipo de contrato y los metadatos se definen explícitamente.</span><span class="sxs-lookup"><span data-stu-id="fff45-277">In the first declaration, the contract type and metadata are explicitly defined.</span></span> <span data-ttu-id="fff45-278">En la segunda declaración, el tipo de contrato y los metadatos están implícitos en el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="fff45-278">In the second declaration, the contract type and metadata are implicit in the customized attribute.</span></span> <span data-ttu-id="fff45-279">Concretamente, en los casos en los que se debe aplicar una cantidad grande de metadatos idénticos a muchas partes (por ejemplo, información sobre el autor y el copyright), utilizar un atributo personalizado ahorra tiempo y duplicados.</span><span class="sxs-lookup"><span data-stu-id="fff45-279">Particularly in cases where a large amount of identical metadata must be applied to many parts (for example, author or copyright information), using a custom attribute can save a lot of time and duplication.</span></span> <span data-ttu-id="fff45-280">Además, se pueden crear árboles de herencia de atributos personalizados para permitir variantes.</span><span class="sxs-lookup"><span data-stu-id="fff45-280">Further, inheritance trees of custom attributes can be created to allow for variations.</span></span>

<span data-ttu-id="fff45-281">Para crear los metadatos opcionales en un atributo personalizado, puede utilizar el atributo `DefaultValue` .</span><span class="sxs-lookup"><span data-stu-id="fff45-281">To create optional metadata in a custom attribute, you can use the `DefaultValue` attribute.</span></span> <span data-ttu-id="fff45-282">Cuando este atributo se aplica a una propiedad de una clase de atributos personalizada, especifica que la propiedad representativa es opcional y no tiene que ser proporcionada por un exportador.</span><span class="sxs-lookup"><span data-stu-id="fff45-282">When this attribute is applied to a property in a custom attribute class, it specifies that the decorated property is optional and does not have to be supplied by an exporter.</span></span> <span data-ttu-id="fff45-283">Si no se proporciona el valor de la propiedad, se le asignará el valor predeterminado de su tipo de propiedad (normalmente `null`, `false`o 0).</span><span class="sxs-lookup"><span data-stu-id="fff45-283">If a value for the property is not supplied, it will be assigned the default value for its property type (usually `null`, `false`, or 0.)</span></span>

<a name="creation_policies"></a>

## <a name="creation-policies"></a><span data-ttu-id="fff45-284">Directivas de creación</span><span class="sxs-lookup"><span data-stu-id="fff45-284">Creation Policies</span></span>

<span data-ttu-id="fff45-285">Cuando una parte especifica una importación y se realiza la composición, el contenedor de composición intenta encontrar una exportación coincidente.</span><span class="sxs-lookup"><span data-stu-id="fff45-285">When a part specifies an import and composition is performed, the composition container attempts to find a matching export.</span></span> <span data-ttu-id="fff45-286">Si la importación coincide correctamente con una exportación, el miembro de importación se establece en una instancia del objeto exportado.</span><span class="sxs-lookup"><span data-stu-id="fff45-286">If it matches the import with an export successfully, the importing member is set to an instance of the exported object.</span></span> <span data-ttu-id="fff45-287">La *directiva de creación*de la parte que exporta controla la procedencia de esta instancia.</span><span class="sxs-lookup"><span data-stu-id="fff45-287">Where this instance comes from is controlled by the exporting part's *creation policy*.</span></span>

<span data-ttu-id="fff45-288">Las dos posibles directivas de creación son *compartida* y *no compartida*.</span><span class="sxs-lookup"><span data-stu-id="fff45-288">The two possible creation policies are *shared* and *non-shared*.</span></span> <span data-ttu-id="fff45-289">Una parte con una directiva de creación compartida se compartirá entre todas las importaciones del contenedor de una parte con ese contrato.</span><span class="sxs-lookup"><span data-stu-id="fff45-289">A part with a creation policy of shared will be shared between every import in the container for a part with that contract.</span></span> <span data-ttu-id="fff45-290">Cuando el motor de composición encuentra una coincidencia y tiene que establecer una propiedad de importación, solo creará una instancia de una nueva copia de la parte si aún no existe; si no, proporcionará la copia existente.</span><span class="sxs-lookup"><span data-stu-id="fff45-290">When the composition engine finds a match and has to set an importing property, it will instantiate a new copy of the part only if one does not already exist; otherwise, it will supply the existing copy.</span></span> <span data-ttu-id="fff45-291">Esto significa que muchos objetos pueden tener referencias a la misma parte.</span><span class="sxs-lookup"><span data-stu-id="fff45-291">This means that many objects may have references to the same part.</span></span> <span data-ttu-id="fff45-292">Estas partes no deberían confiar en un estado interno que se puede cambiar desde muchos lugares.</span><span class="sxs-lookup"><span data-stu-id="fff45-292">Such parts should not rely on internal state that might be changed from many places.</span></span> <span data-ttu-id="fff45-293">Esta directiva es adecuada para las partes estáticas, las que proporcionan servicios y las que utilizan mucha memoria u otros recursos.</span><span class="sxs-lookup"><span data-stu-id="fff45-293">This policy is appropriate for static parts, parts that provide services, and parts that consume a lot of memory or other resources.</span></span>

<span data-ttu-id="fff45-294">Se creará una parte con una directiva de creación de parte no compartida cada vez que se encuentre una importación correspondiente para una de sus exportaciones.</span><span class="sxs-lookup"><span data-stu-id="fff45-294">A part with the creation policy of non-shared will be created every time a matching import for one of its exports is found.</span></span> <span data-ttu-id="fff45-295">Se crearán instancias de una nueva copia para cada importación del contenedor que coincida con uno de los contratos exportados de la parte.</span><span class="sxs-lookup"><span data-stu-id="fff45-295">A new copy will therefore be instantiated for every import in the container that matches one of the part's exported contracts.</span></span> <span data-ttu-id="fff45-296">No se compartirá el estado interno de estas copias.</span><span class="sxs-lookup"><span data-stu-id="fff45-296">The internal state of these copies will not be shared.</span></span> <span data-ttu-id="fff45-297">Esta directiva es adecuada para las partes en las que cada importación requiere su propio estado interno.</span><span class="sxs-lookup"><span data-stu-id="fff45-297">This policy is appropriate for parts where each import requires its own internal state.</span></span>

<span data-ttu-id="fff45-298">La importación y la exportación pueden especificar la directiva de creación de una parte, entre los valores `Shared`, `NonShared`o `Any`.</span><span class="sxs-lookup"><span data-stu-id="fff45-298">Both the import and the export can specify the creation policy of a part, from among the values `Shared`, `NonShared`, or `Any`.</span></span> <span data-ttu-id="fff45-299">El valor predeterminado es `Any` para las importaciones y las exportaciones.</span><span class="sxs-lookup"><span data-stu-id="fff45-299">The default is `Any` for both imports and exports.</span></span> <span data-ttu-id="fff45-300">Una exportación que especifica `Shared` o `NonShared` solo coincidirá con una importación que especifique lo mismo o que especifique `Any`.</span><span class="sxs-lookup"><span data-stu-id="fff45-300">An export that specifies `Shared` or `NonShared` will only match an import that specifies the same, or that specifies `Any`.</span></span> <span data-ttu-id="fff45-301">De igual forma, una exportación que especifica `Shared` o `NonShared` solo coincidirá con una exportación que especifique lo mismo o que especifique `Any`.</span><span class="sxs-lookup"><span data-stu-id="fff45-301">Similarly, an import that specifies `Shared` or `NonShared` will only match an export that specifies the same, or that specifies `Any`.</span></span> <span data-ttu-id="fff45-302">Las importaciones y exportaciones con directivas de creación incompatibles no se consideran una coincidencia, de la misma manera que una importación y exportación cuyo nombre de contrato o tipo de contrato no coinciden.</span><span class="sxs-lookup"><span data-stu-id="fff45-302">Imports and exports with incompatible creation policies are not considered a match, in the same way as an import and export whose contract name or contract type are not a match.</span></span> <span data-ttu-id="fff45-303">Si la importación y la exportación especifican `Any`o no especifican una directiva de creación y tienen como valor predeterminado `Any`, la directiva de creación se establecerá de manera predeterminado en compartida.</span><span class="sxs-lookup"><span data-stu-id="fff45-303">If both import and export specify `Any`, or do not specify a creation policy and default to `Any`, the creation policy will default to shared.</span></span>

<span data-ttu-id="fff45-304">En el siguiente ejemplo se muestran importaciones y exportaciones que especifican directivas de creación.</span><span class="sxs-lookup"><span data-stu-id="fff45-304">The following example shows both imports and exports specifying creation policies.</span></span> <span data-ttu-id="fff45-305">`PartOne` no especifica una directiva de creación, de modo que el valor predeterminado es `Any`.</span><span class="sxs-lookup"><span data-stu-id="fff45-305">`PartOne` does not specify a creation policy, so the default is `Any`.</span></span> <span data-ttu-id="fff45-306">`PartTwo` no especifica una directiva de creación, de modo que el valor predeterminado es `Any`.</span><span class="sxs-lookup"><span data-stu-id="fff45-306">`PartTwo` does not specify a creation policy, so the default is `Any`.</span></span> <span data-ttu-id="fff45-307">Dado que la importación y la exportación tienen como valor predeterminado `Any`, se compartirá `PartOne` .</span><span class="sxs-lookup"><span data-stu-id="fff45-307">Since both import and export default to `Any`, `PartOne` will be shared.</span></span> <span data-ttu-id="fff45-308">`PartThree` especifica una directiva de creación `Shared` , de modo que `PartTwo` y `PartThree` compartirán la misma copia de `PartOne`.</span><span class="sxs-lookup"><span data-stu-id="fff45-308">`PartThree` specifies a `Shared` creation policy, so `PartTwo` and `PartThree` will share the same copy of `PartOne`.</span></span> <span data-ttu-id="fff45-309">`PartFour` especifica una directiva de creación `NonShared` , de modo que `PartFour` será no compartida en `PartFive`.</span><span class="sxs-lookup"><span data-stu-id="fff45-309">`PartFour` specifies a `NonShared` creation policy, so `PartFour` will be non-shared in `PartFive`.</span></span> <span data-ttu-id="fff45-310">`PartSix` especifica una directiva de creación `NonShared` .</span><span class="sxs-lookup"><span data-stu-id="fff45-310">`PartSix` specifies a `NonShared` creation policy.</span></span> <span data-ttu-id="fff45-311">`PartFive` y `PartSix` recibirán copias independientes de `PartFour`.</span><span class="sxs-lookup"><span data-stu-id="fff45-311">`PartFive` and `PartSix` will each receive separate copies of `PartFour`.</span></span> <span data-ttu-id="fff45-312">`PartSeven` especifica una directiva de creación `Shared` .</span><span class="sxs-lookup"><span data-stu-id="fff45-312">`PartSeven` specifies a `Shared` creation policy.</span></span> <span data-ttu-id="fff45-313">Dado que no hay ningún `PartFour` exportado con una directiva de creación de `Shared`, la importación `PartSeven` no coincide con nada y no se completará.</span><span class="sxs-lookup"><span data-stu-id="fff45-313">Because there is no exported `PartFour` with a creation policy of `Shared`, the `PartSeven` import does not match anything and will not be filled.</span></span>

```vb
<Export()>
Public Class PartOne
    'The default creation policy for an export is Any.
End Class

Public Class PartTwo

    <Import()>
    Public Property partOne As PartOne

    'The default creation policy for an import is Any.
    'If both policies are Any, the part will be shared.

End Class

Public Class PartThree

    <Import(RequiredCreationPolicy:=CreationPolicy.Shared)>
    Public Property partOne As PartOne

    'The Shared creation policy is explicitly specified.
    'PartTwo and PartThree will receive references to the
    'SAME copy of PartOne.

End Class

<Export()>
<PartCreationPolicy(CreationPolicy.NonShared)>
Public Class PartFour
    'The NonShared creation policy is explicitly specified.
End Class

Public Class PartFive

    <Import()>
    Public Property partFour As PartFour

    'The default creation policy for an import is Any.
    'Since the export's creation policy was explicitly
    'defined, the creation policy for this property will
    'be non-shared.

End Class

Public Class PartSix

    <Import(RequiredCreationPolicy:=CreationPolicy.NonShared)>
    Public Property partFour As PartFour

    'Both import and export specify matching creation
    'policies.  PartFive and PartSix will each receive
    'SEPARATE copies of PartFour, each with its own
    'internal state.

End Class

Public Class PartSeven

    <Import(RequiredCreationPolicy:=CreationPolicy.Shared)>
    Public Property partFour As PartFour

    'A creation policy mismatch.  Because there is no
    'exported PartFour with a creation policy of Shared,
    'this import does not match anything and will not be
    'filled.

End Class
```

```csharp
[Export]
public class PartOne
{
    //The default creation policy for an export is Any.
}

public class PartTwo
{
    [Import]
    public PartOne partOne { get; set; }

    //The default creation policy for an import is Any.
    //If both policies are Any, the part will be shared.
}

public class PartThree
{
    [Import(RequiredCreationPolicy = CreationPolicy.Shared)]
    public PartOne partOne { get; set; }

    //The Shared creation policy is explicitly specified.
    //PartTwo and PartThree will receive references to the
    //SAME copy of PartOne.
}

[Export]
[PartCreationPolicy(CreationPolicy.NonShared)]
public class PartFour
{
    //The NonShared creation policy is explicitly specified.
}

public class PartFive
{
    [Import]
    public PartFour partFour { get; set; }

    //The default creation policy for an import is Any.
    //Since the export's creation policy was explicitly
    //defined, the creation policy for this property will
    //be non-shared.
}

public class PartSix
{
    [Import(RequiredCreationPolicy = CreationPolicy.NonShared)]
    public PartFour partFour { get; set; }

    //Both import and export specify matching creation
    //policies.  PartFive and PartSix will each receive
    //SEPARATE copies of PartFour, each with its own
    //internal state.
}

public class PartSeven
{
    [Import(RequiredCreationPolicy = CreationPolicy.Shared)]
    public PartFour partFour { get; set; }

    //A creation policy mismatch.  Because there is no
    //exported PartFour with a creation policy of Shared,
    //this import does not match anything and will not be
    //filled.
}
```

<a name="life_cycle_and_disposing"></a>

## <a name="life-cycle-and-disposing"></a><span data-ttu-id="fff45-314">Ciclo de vida y eliminación</span><span class="sxs-lookup"><span data-stu-id="fff45-314">Life Cycle and Disposing</span></span>

<span data-ttu-id="fff45-315">Dado que las partes se hospedan en el contenedor de composición, su ciclo de vida puede ser más complejo que el de los objetos ordinarios.</span><span class="sxs-lookup"><span data-stu-id="fff45-315">Because parts are hosted in the composition container, their life cycle can be more complex than ordinary objects.</span></span> <span data-ttu-id="fff45-316">Las partes pueden implementar dos importantes interfaces relacionadas con el ciclo de vida: `IDisposable` e `IPartImportsSatisfiedNotification`.</span><span class="sxs-lookup"><span data-stu-id="fff45-316">Parts can implement two important life cycle-related interfaces: `IDisposable` and `IPartImportsSatisfiedNotification`.</span></span>

<span data-ttu-id="fff45-317">Las partes que exigen realizar trabajo al cerrar o que necesitan liberar recursos deberían implementar `IDisposable`como de costumbre para los objetos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fff45-317">Parts that require work to be performed at shut down or that need to release resources should implement `IDisposable`, as usual for .NET Framework objects.</span></span> <span data-ttu-id="fff45-318">Sin embargo, ya que el contenedor crea y mantiene las referencias a las partes, solo el contenedor que posee una parte debería llamar al método `Dispose` en él.</span><span class="sxs-lookup"><span data-stu-id="fff45-318">However, since the container creates and maintains references to parts, only the container that owns a part should call the `Dispose` method on it.</span></span> <span data-ttu-id="fff45-319">El contenedor implementa `IDisposable`, y como parte de la limpieza en `Dispose` llamará a `Dispose` en todas las partes que posee.</span><span class="sxs-lookup"><span data-stu-id="fff45-319">The container itself implements `IDisposable`, and as portion of its cleanup in `Dispose` it will call `Dispose` on all the parts that it owns.</span></span> <span data-ttu-id="fff45-320">Por esta razón, debería eliminar, cuando ya no se necesite, el contenedor de composición y sus partes.</span><span class="sxs-lookup"><span data-stu-id="fff45-320">For this reason, you should always dispose the composition container when it and any parts it owns are no longer needed.</span></span>

<span data-ttu-id="fff45-321">Para los contenedores de composición duraderos, el consumo de memoria de las partes con una directiva de creación de parte no compartida puede convertirse en un problema.</span><span class="sxs-lookup"><span data-stu-id="fff45-321">For long-lived composition containers, memory consumption by parts with a creation policy of non-shared can become a problem.</span></span> <span data-ttu-id="fff45-322">Estas partes no compartidas se pueden crear varias veces y no se eliminarán hasta que se elimine el contenedor.</span><span class="sxs-lookup"><span data-stu-id="fff45-322">These non-shared parts can be created multiple times and will not be disposed until the container itself is disposed.</span></span> <span data-ttu-id="fff45-323">Para solucionar esto, el contenedor proporciona el método `ReleaseExport` .</span><span class="sxs-lookup"><span data-stu-id="fff45-323">To deal with this, the container provides the `ReleaseExport` method.</span></span> <span data-ttu-id="fff45-324">Llamando a este método en una exportación no compartida, se quita esa exportación del contenedor de composición y se elimina.</span><span class="sxs-lookup"><span data-stu-id="fff45-324">Calling this method on a non-shared export removes that export from the composition container and disposes it.</span></span> <span data-ttu-id="fff45-325">Las partes que solo utilizaba la exportación eliminada y demás hacia abajo en el árbol, también se quitan y se eliminan.</span><span class="sxs-lookup"><span data-stu-id="fff45-325">Parts that are used only by the removed export, and so on down the tree, are also removed and disposed.</span></span> <span data-ttu-id="fff45-326">De esta manera, los recursos se pueden reclamar sin eliminar el contenedor de composición.</span><span class="sxs-lookup"><span data-stu-id="fff45-326">In this way, resources can be reclaimed without disposing the composition container itself.</span></span>

<span data-ttu-id="fff45-327">`IPartImportsSatisfiedNotification` contiene un método denominado `OnImportsSatisfied`.</span><span class="sxs-lookup"><span data-stu-id="fff45-327">`IPartImportsSatisfiedNotification` contains one method named `OnImportsSatisfied`.</span></span> <span data-ttu-id="fff45-328">El contenedor de composición llama a este método en cualquier parte que implemente la interfaz cuando se ha completado la composición y las importaciones de la parte están listas para el uso.</span><span class="sxs-lookup"><span data-stu-id="fff45-328">This method is called by the composition container on any parts that implement the interface when composition has been completed and the part's imports are ready for use.</span></span> <span data-ttu-id="fff45-329">El motor de la composición crea las partes para completar las importaciones de otras partes.</span><span class="sxs-lookup"><span data-stu-id="fff45-329">Parts are created by the composition engine to fill the imports of other parts.</span></span> <span data-ttu-id="fff45-330">Antes de que las importaciones de una parte se hayan establecido, no puede realizar ninguna inicialización que confíe o manipule los valores importados en el constructor de la parte, a menos que esos valores se hayan especificado como requisitos previos mediante el atributo `ImportingConstructor` .</span><span class="sxs-lookup"><span data-stu-id="fff45-330">Before the imports of a part have been set, you cannot perform any initialization that relies on or manipulates imported values in the part constructor unless those values have been specified as prerequisites by using the `ImportingConstructor` attribute.</span></span> <span data-ttu-id="fff45-331">Éste es normalmente el método preferido, pero en algunos casos, la inyección de constructor tal vez no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="fff45-331">This is normally the preferred method, but in some cases, constructor injection may not be available.</span></span> <span data-ttu-id="fff45-332">En esos casos, la inicialización se puede realizar en `OnImportsSatisfied`y la parte debería implementar `IPartImportsSatisfiedNotification`.</span><span class="sxs-lookup"><span data-stu-id="fff45-332">In those cases, initialization can be performed in `OnImportsSatisfied`, and the part should implement `IPartImportsSatisfiedNotification`.</span></span>

## <a name="see-also"></a><span data-ttu-id="fff45-333">Vea también</span><span class="sxs-lookup"><span data-stu-id="fff45-333">See also</span></span>

- [<span data-ttu-id="fff45-334">Vídeo de Channel 9: Abrir las aplicaciones con Managed Extensibility Framework</span><span class="sxs-lookup"><span data-stu-id="fff45-334">Channel 9 Video: Open Up Your Applications with the Managed Extensibility Framework</span></span>](https://channel9.msdn.com/events/TechEd/NorthAmerica/2009/DTL328)
- [<span data-ttu-id="fff45-335">Vídeo de Channel 9: Managed Extensibility Framework (MEF) 2.0</span><span class="sxs-lookup"><span data-stu-id="fff45-335">Channel 9 Video: Managed Extensibility Framework (MEF) 2.0</span></span>](https://channel9.msdn.com/posts/NET-45-Oleg-Lvovitch-and-Kevin-Ransom-Managed-Extensibility-Framework-MEF-20)
