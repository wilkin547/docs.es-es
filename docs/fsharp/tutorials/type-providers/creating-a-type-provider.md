---
title: 'Tutorial: Creación de un proveedor de tipos'
description: 'Obtenga información sobre cómo crear sus propios proveedores de tipos de F # en F # 3,0 examinando varios proveedores de tipos simples para ilustrar los conceptos básicos.'
ms.date: 11/04/2019
ms.openlocfilehash: 71225614ed983a76d35c214faa87bbad0fbb7d24
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88810877"
---
# <a name="tutorial-create-a-type-provider"></a><span data-ttu-id="b3d47-103">Tutorial: Creación de un proveedor de tipos</span><span class="sxs-lookup"><span data-stu-id="b3d47-103">Tutorial: Create a Type Provider</span></span>

<span data-ttu-id="b3d47-104">El mecanismo de proveedores de tipos de F # es una parte importante de su compatibilidad con la programación enriquecida de información.</span><span class="sxs-lookup"><span data-stu-id="b3d47-104">The type provider mechanism in F# is a significant part of its support for information rich programming.</span></span> <span data-ttu-id="b3d47-105">Este tutorial le explica cómo crear proveedores de tipos, a la vez que le guía en el desarrollo de varios proveedores de tipo simples para ilustrar los conceptos básicos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-105">This tutorial explains how to create your own type providers by walking you through the development of several simple type providers to illustrate the basic concepts.</span></span> <span data-ttu-id="b3d47-106">Para obtener más información sobre el mecanismo de proveedores de tipos en F #, vea [proveedores de tipos](index.md).</span><span class="sxs-lookup"><span data-stu-id="b3d47-106">For more information about the type provider mechanism in F#, see [Type Providers](index.md).</span></span>

<span data-ttu-id="b3d47-107">El ecosistema de F # contiene una variedad de proveedores de tipo para los servicios de datos empresariales y de Internet que se usan habitualmente.</span><span class="sxs-lookup"><span data-stu-id="b3d47-107">The F# ecosystem contains a range of type providers for commonly used Internet and enterprise data services.</span></span> <span data-ttu-id="b3d47-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b3d47-108">For example:</span></span>

- <span data-ttu-id="b3d47-109">[FSharp. Data](https://fsharp.github.io/FSharp.Data/) incluye proveedores de tipos para los formatos de documento JSON, XML, csv y HTML.</span><span class="sxs-lookup"><span data-stu-id="b3d47-109">[FSharp.Data](https://fsharp.github.io/FSharp.Data/) includes type providers for JSON, XML, CSV and HTML document formats.</span></span>

- <span data-ttu-id="b3d47-110">[SQLProvider](https://fsprojects.github.io/SQLProvider/) proporciona acceso fuertemente tipado a las bases de datos SQL a través de una asignación de objetos y consultas LINQ de F # en estos orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-110">[SQLProvider](https://fsprojects.github.io/SQLProvider/) provides strongly typed access to SQL databases through a object mapping and F# LINQ queries against these data sources.</span></span>

- <span data-ttu-id="b3d47-111">[FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) tiene un conjunto de proveedores de tipos para la inserción comprobada en tiempo de compilación de T-SQL en F#.</span><span class="sxs-lookup"><span data-stu-id="b3d47-111">[FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) has a set of type providers for compile-time checked embedding of T-SQL in F#.</span></span>

- <span data-ttu-id="b3d47-112">[FSharp. Data. TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) es un conjunto anterior de proveedores de tipo para su uso solo con .NET Framework programación para tener acceso a los servicios de datos SQL, Entity Framework, ODATA y WSDL.</span><span class="sxs-lookup"><span data-stu-id="b3d47-112">[FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) is an older set of type providers for use only with .NET Framework programming for accessing SQL, Entity Framework, OData and WSDL data services.</span></span>

<span data-ttu-id="b3d47-113">En caso necesario, se pueden crear proveedores de tipos personalizados o se puede hacer referencia a proveedores de tipos creados por otros.</span><span class="sxs-lookup"><span data-stu-id="b3d47-113">Where necessary, you can create custom type providers, or you can reference type providers that others have created.</span></span> <span data-ttu-id="b3d47-114">Por ejemplo, una organización podría tener un servicio de datos que proporcionara un número elevado y creciente de conjuntos de datos con nombre, cada uno con su propio esquema de datos estable.</span><span class="sxs-lookup"><span data-stu-id="b3d47-114">For example, your organization could have a data service that provides a large and growing number of named data sets, each with its own stable data schema.</span></span> <span data-ttu-id="b3d47-115">Se puede crear un proveedor de tipos que lea los esquemas y presente los conjuntos de datos actuales al programador de una manera fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="b3d47-115">You can create a type provider that reads the schemas and presents the current data sets to the programmer in a strongly typed way.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="b3d47-116">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="b3d47-116">Before You Start</span></span>

<span data-ttu-id="b3d47-117">El mecanismo de proveedores de tipo está diseñado principalmente para insertar espacios de información de servicios y datos estables en la experiencia de programación de F#.</span><span class="sxs-lookup"><span data-stu-id="b3d47-117">The type provider mechanism is primarily designed for injecting stable data and service information spaces into the F# programming experience.</span></span>

<span data-ttu-id="b3d47-118">Este mecanismo no está diseñado para insertar espacios de información cuyo esquema cambie durante la ejecución del programa de forma relevante para la lógica del programa.</span><span class="sxs-lookup"><span data-stu-id="b3d47-118">This mechanism isn’t designed for injecting information spaces whose schema changes during program execution in ways that are relevant to program logic.</span></span> <span data-ttu-id="b3d47-119">El mecanismo tampoco está diseñado para la metaprogramación dentro del lenguaje, aunque ese dominio contenga algunas aplicaciones válidas.</span><span class="sxs-lookup"><span data-stu-id="b3d47-119">Also, the mechanism isn't designed for intra-language meta-programming, even though that domain contains some valid uses.</span></span> <span data-ttu-id="b3d47-120">Debe utilizar este mecanismo solo en caso necesario y cuando el desarrollo de un proveedor de tipos produzca un valor muy alto.</span><span class="sxs-lookup"><span data-stu-id="b3d47-120">You should use this mechanism only where necessary and where the development of a type provider yields very high value.</span></span>

<span data-ttu-id="b3d47-121">Debe evitar escribir un proveedor de tipos cuando no hay un esquema disponible.</span><span class="sxs-lookup"><span data-stu-id="b3d47-121">You should avoid writing a type provider where a schema isn't available.</span></span> <span data-ttu-id="b3d47-122">Igualmente, debe evitar escribir un proveedor de tipo cuando una biblioteca de .NET normal (o incluso una existente) sería suficiente.</span><span class="sxs-lookup"><span data-stu-id="b3d47-122">Likewise, you should avoid writing a type provider where an ordinary (or even an existing) .NET library would suffice.</span></span>

<span data-ttu-id="b3d47-123">Antes de comenzar, debería hacerse las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="b3d47-123">Before you start, you might ask the following questions:</span></span>

- <span data-ttu-id="b3d47-124">¿Tiene un esquema para su fuente de información?</span><span class="sxs-lookup"><span data-stu-id="b3d47-124">Do you have a schema for your information source?</span></span> <span data-ttu-id="b3d47-125">Si lo tiene, ¿cuál es la correspondencia entre los sistemas de tipos de F# y .NET?</span><span class="sxs-lookup"><span data-stu-id="b3d47-125">If so, what’s the mapping into the F# and .NET type system?</span></span>

- <span data-ttu-id="b3d47-126">¿Puede utilizar una API existente (dinámicamente tipada) como punto de partida para su implementación?</span><span class="sxs-lookup"><span data-stu-id="b3d47-126">Can you use an existing (dynamically typed) API as a starting point for your implementation?</span></span>

- <span data-ttu-id="b3d47-127">¿Usarán usted y su organización el proveedor de tipos lo suficiente como para hacer que valga la pena escribirlo?</span><span class="sxs-lookup"><span data-stu-id="b3d47-127">Will you and your organization have enough uses of the type provider to make writing it worthwhile?</span></span> <span data-ttu-id="b3d47-128">¿Cubriría una biblioteca normal de .NET sus necesidades?</span><span class="sxs-lookup"><span data-stu-id="b3d47-128">Would a normal .NET library meet your needs?</span></span>

- <span data-ttu-id="b3d47-129">¿Cuánto cambiará el esquema?</span><span class="sxs-lookup"><span data-stu-id="b3d47-129">How much will your schema change?</span></span>

- <span data-ttu-id="b3d47-130">¿Cambiará durante la escritura del código?</span><span class="sxs-lookup"><span data-stu-id="b3d47-130">Will it change during coding?</span></span>

- <span data-ttu-id="b3d47-131">¿Cambiará entre las sesiones de escritura de código?</span><span class="sxs-lookup"><span data-stu-id="b3d47-131">Will it change between coding sessions?</span></span>

- <span data-ttu-id="b3d47-132">¿Cambiará durante la ejecución del programa?</span><span class="sxs-lookup"><span data-stu-id="b3d47-132">Will it change during program execution?</span></span>

<span data-ttu-id="b3d47-133">Los proveedores de tipos son más adecuados en situaciones en las que el esquema es estable en runtime y durante el tiempo de vida del código compilado.</span><span class="sxs-lookup"><span data-stu-id="b3d47-133">Type providers are best suited to situations where the schema is stable at runtime and during the lifetime of compiled code.</span></span>

## <a name="a-simple-type-provider"></a><span data-ttu-id="b3d47-134">Un proveedor de tipos simple</span><span class="sxs-lookup"><span data-stu-id="b3d47-134">A Simple Type Provider</span></span>

<span data-ttu-id="b3d47-135">Este ejemplo es samples. HelloWorldTypeProvider, similar a los ejemplos del `examples` directorio del [SDK del proveedor de tipos de F #](https://github.com/fsprojects/FSharp.TypeProviders.SDK/).</span><span class="sxs-lookup"><span data-stu-id="b3d47-135">This sample is Samples.HelloWorldTypeProvider, similar to the samples in the `examples` directory of the [F# Type Provider SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/).</span></span> <span data-ttu-id="b3d47-136">El proveedor hace que esté disponible un "espacio de tipos" que contiene 100 tipos borrados, como muestra el código siguiente, en el que se usa la sintaxis de signatura de F# y se omiten los detalles de todos los tipos excepto `Type1`.</span><span class="sxs-lookup"><span data-stu-id="b3d47-136">The provider makes available a "type space" that contains 100 erased types, as the following code shows by using F# signature syntax and omitting the details for all except `Type1`.</span></span> <span data-ttu-id="b3d47-137">Para obtener más información sobre los tipos borrados, consulte [detalles sobre los tipos de borrados proporcionados](#details-about-erased-provided-types) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="b3d47-137">For more information about erased types, see [Details About Erased Provided Types](#details-about-erased-provided-types) later in this topic.</span></span>

```fsharp
namespace Samples.HelloWorldTypeProvider

type Type1 =
    /// This is a static property.
    static member StaticProperty : string

    /// This constructor takes no arguments.
    new : unit -> Type1

    /// This constructor takes one argument.
    new : data:string -> Type1

    /// This is an instance property.
    member InstanceProperty : int

    /// This is an instance method.
    member InstanceMethod : x:int -> char

    nested type NestedType =
        /// This is StaticProperty1 on NestedType.
        static member StaticProperty1 : string
        …
        /// This is StaticProperty100 on NestedType.
        static member StaticProperty100 : string

type Type2 =
…
…

type Type100 =
…
```

<span data-ttu-id="b3d47-138">Observe que el conjunto de tipos y miembros proporcionados se conoce de forma estática.</span><span class="sxs-lookup"><span data-stu-id="b3d47-138">Note that the set of types and members provided is statically known.</span></span> <span data-ttu-id="b3d47-139">Este ejemplo no aprovecha la capacidad de los proveedores para proporcionar tipos que dependen de un esquema.</span><span class="sxs-lookup"><span data-stu-id="b3d47-139">This example doesn't leverage the ability of providers to provide types that depend on a schema.</span></span> <span data-ttu-id="b3d47-140">La implementación del proveedor de tipo se muestra en el código siguiente y sus detalles se tratan en secciones posteriores de este tema.</span><span class="sxs-lookup"><span data-stu-id="b3d47-140">The implementation of the type provider is outlined in the following code, and the details are covered in later sections of this topic.</span></span>

> [!WARNING]
> <span data-ttu-id="b3d47-141">Puede haber diferencias entre este código y los ejemplos en línea.</span><span class="sxs-lookup"><span data-stu-id="b3d47-141">There may be differences between this code and the online samples.</span></span>

```fsharp
namespace Samples.FSharp.HelloWorldTypeProvider

open System
open System.Reflection
open ProviderImplementation.ProvidedTypes
open FSharp.Core.CompilerServices
open FSharp.Quotations

// This type defines the type provider. When compiled to a DLL, it can be added
// as a reference to an F# command-line compilation, script, or project.
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =

  // Inheriting from this type provides implementations of ITypeProvider
  // in terms of the provided types below.
  inherit TypeProviderForNamespaces(config)

  let namespaceName = "Samples.HelloWorldTypeProvider"
  let thisAssembly = Assembly.GetExecutingAssembly()

  // Make one provided type, called TypeN.
  let makeOneProvidedType (n:int) =
  …
  // Now generate 100 types
  let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]

  // And add them to the namespace
  do this.AddNamespace(namespaceName, types)

[<assembly:TypeProviderAssembly>]
do()
```

<span data-ttu-id="b3d47-142">Para usar este proveedor, abra una instancia independiente de Visual Studio, cree un script de F # y, a continuación, agregue una referencia al proveedor desde el script mediante #r como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3d47-142">To use this provider, open a separate instance of Visual Studio, create an F# script, and then add a reference to the provider from your script by using #r as the following code shows:</span></span>

```fsharp
#r @".\bin\Debug\Samples.HelloWorldTypeProvider.dll"

let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")

let obj2 = Samples.HelloWorldTypeProvider.Type1("some other data")

obj1.InstanceProperty
obj2.InstanceProperty

[ for index in 0 .. obj1.InstanceProperty-1 -> obj1.InstanceMethod(index) ]
[ for index in 0 .. obj2.InstanceProperty-1 -> obj2.InstanceMethod(index) ]

let data1 = Samples.HelloWorldTypeProvider.Type1.NestedType.StaticProperty35
```

<span data-ttu-id="b3d47-143">A continuación, busque los tipos en el espacio de nombres `Samples.HelloWorldTypeProvider` generado por el proveedor de tipos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-143">Then look for the types under the `Samples.HelloWorldTypeProvider` namespace that the type provider generated.</span></span>

<span data-ttu-id="b3d47-144">Antes de volver a compilar el proveedor, asegúrese de que se han cerrado todas las instancias de Visual Studio y de F# Interactive que están utilizando la DLL del proveedor.</span><span class="sxs-lookup"><span data-stu-id="b3d47-144">Before you recompile the provider, make sure that you have closed all instances of Visual Studio and F# Interactive that are using the provider DLL.</span></span> <span data-ttu-id="b3d47-145">De lo contrario, aparecerá un error de compilación porque la DLL de salida estará bloqueada.</span><span class="sxs-lookup"><span data-stu-id="b3d47-145">Otherwise, a build error will occur because the output DLL will be locked.</span></span>

<span data-ttu-id="b3d47-146">Para depurar este proveedor mediante instrucciones de impresión, cree un script que exponga un problema con el proveedor y, a continuación, utilice el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3d47-146">To debug this provider by using print statements, make a script that exposes a problem with the provider, and then use the following code:</span></span>

```console
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="b3d47-147">Para depurar este proveedor mediante Visual Studio, abra el Símbolo del sistema para desarrolladores de Visual Studio con credenciales administrativas y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b3d47-147">To debug this provider by using Visual Studio, open the Developer Command Prompt for Visual Studio with administrative credentials, and run the following command:</span></span>

```console
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="b3d47-148">Como alternativa, abra Visual Studio, abra el menú Depurar, elija `Debug/Attach to process…` y asocie a otro `devenv` proceso en el que esté editando el script.</span><span class="sxs-lookup"><span data-stu-id="b3d47-148">As an alternative, open Visual Studio, open the Debug menu, choose `Debug/Attach to process…`, and attach to another `devenv` process where you’re editing your script.</span></span> <span data-ttu-id="b3d47-149">Con este método, le resultará más fácil centrarse en la lógica particular del proveedor de tipo escribiendo interactivamente expresiones en la segunda instancia (con IntelliSense completo y otras características).</span><span class="sxs-lookup"><span data-stu-id="b3d47-149">By using this method, you can more easily target particular logic in the type provider by interactively typing expressions into the second instance (with full IntelliSense and other features).</span></span>

<span data-ttu-id="b3d47-150">Puede deshabilitar la depuración "Solo mi código" para identificar mejor los errores en el código generado.</span><span class="sxs-lookup"><span data-stu-id="b3d47-150">You can disable Just My Code debugging to better identify errors in generated code.</span></span> <span data-ttu-id="b3d47-151">Para obtener información sobre cómo habilitar o deshabilitar esta característica, vea [navegar por el código con el depurador](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span><span class="sxs-lookup"><span data-stu-id="b3d47-151">For information about how to enable or disable this feature, see [Navigating through Code with the Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span></span> <span data-ttu-id="b3d47-152">Además, también puede establecer la detección de excepciones de primera oportunidad abriendo el `Debug` menú y, a continuación, eligiendo `Exceptions` las teclas Ctrl + Alt + E para abrir el `Exceptions` cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b3d47-152">Also, you can also set first-chance exception catching by opening the `Debug` menu and then choosing `Exceptions` or by choosing the Ctrl+Alt+E keys to open the `Exceptions` dialog box.</span></span> <span data-ttu-id="b3d47-153">En ese cuadro de diálogo, en `Common Language Runtime Exceptions` , active la `Thrown` casilla.</span><span class="sxs-lookup"><span data-stu-id="b3d47-153">In that dialog box, under `Common Language Runtime Exceptions`, select the `Thrown` check box.</span></span>

### <a name="implementation-of-the-type-provider"></a><span data-ttu-id="b3d47-154">Implementación del proveedor de tipos</span><span class="sxs-lookup"><span data-stu-id="b3d47-154">Implementation of the Type Provider</span></span>

<span data-ttu-id="b3d47-155">En esta sección se muestran las etapas principales de la implementación del proveedor de tipos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-155">This section walks you through the principal sections of the type provider implementation.</span></span> <span data-ttu-id="b3d47-156">En primer lugar, defina el tipo del proveedor de tipos personalizado:</span><span class="sxs-lookup"><span data-stu-id="b3d47-156">First, you define the type for the custom type provider itself:</span></span>

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

<span data-ttu-id="b3d47-157">Este tipo debe ser público y debe marcarse con el atributo [TypeProvider](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-compilerservices-typeproviderattribute.html) para que el compilador reconozca el proveedor de tipos cuando un proyecto independiente de F # haga referencia al ensamblado que contiene el tipo.</span><span class="sxs-lookup"><span data-stu-id="b3d47-157">This type must be public, and you must mark it with the [TypeProvider](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-compilerservices-typeproviderattribute.html) attribute so that the compiler will recognize the type provider when a separate F# project references the assembly that contains the type.</span></span> <span data-ttu-id="b3d47-158">El parámetro de *configuración* es opcional y, si está presente, contiene información de configuración contextual para la instancia del proveedor de tipo que crea el compilador de F #.</span><span class="sxs-lookup"><span data-stu-id="b3d47-158">The *config* parameter is optional, and, if present, contains contextual configuration information for the type provider instance that the F# compiler creates.</span></span>

<span data-ttu-id="b3d47-159">A continuación, implemente la interfaz [ITypeProvider](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-compilerservices-itypeprovider.html) .</span><span class="sxs-lookup"><span data-stu-id="b3d47-159">Next, you implement the [ITypeProvider](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-compilerservices-itypeprovider.html) interface.</span></span> <span data-ttu-id="b3d47-160">En este caso, puede utilizar el tipo `TypeProviderForNamespaces` de la API `ProvidedTypes` como tipo base.</span><span class="sxs-lookup"><span data-stu-id="b3d47-160">In this case, you use the `TypeProviderForNamespaces` type from the `ProvidedTypes` API as a base type.</span></span> <span data-ttu-id="b3d47-161">Este tipo del asistente puede proporcionar una colección finita de espacios de nombres proporcionados anticipadamente, cada uno de los cuales contiene directamente un número finito de tipos fijos proporcionados anticipadamente.</span><span class="sxs-lookup"><span data-stu-id="b3d47-161">This helper type can provide a finite collection of eagerly provided namespaces, each of which directly contains a finite number of fixed, eagerly provided types.</span></span> <span data-ttu-id="b3d47-162">En este contexto, el proveedor genera *diligentemente* tipos incluso si no son necesarios o se usan.</span><span class="sxs-lookup"><span data-stu-id="b3d47-162">In this context, the provider *eagerly* generates types even if they aren't needed or used.</span></span>

```fsharp
inherit TypeProviderForNamespaces(config)
```

<span data-ttu-id="b3d47-163">A continuación, defina los valores privados locales que especifican el espacio de nombres para los tipos proporcionados y busque el ensamblado propio del proveedor de tipos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-163">Next, define local private values that specify the namespace for the provided types, and find the type provider assembly itself.</span></span> <span data-ttu-id="b3d47-164">Este ensamblado se utiliza más adelante como tipo primario lógico de los tipos borrados proporcionados.</span><span class="sxs-lookup"><span data-stu-id="b3d47-164">This assembly is used later as the logical parent type of the erased types that are provided.</span></span>

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

<span data-ttu-id="b3d47-165">A continuación, cree una función para proporcionar cada uno de los tipos Type1… Type100.</span><span class="sxs-lookup"><span data-stu-id="b3d47-165">Next, create a function to provide each of the types Type1…Type100.</span></span> <span data-ttu-id="b3d47-166">Esta función se explica con más detalle más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="b3d47-166">This function is explained in more detail later in this topic.</span></span>

```fsharp
let makeOneProvidedType (n:int) = …
```

<span data-ttu-id="b3d47-167">A continuación, genere los 100 tipos proporcionados:</span><span class="sxs-lookup"><span data-stu-id="b3d47-167">Next, generate the 100 provided types:</span></span>

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

<span data-ttu-id="b3d47-168">Después, agregue los tipos como un espacio de nombres proporcionado:</span><span class="sxs-lookup"><span data-stu-id="b3d47-168">Next, add the types as a provided namespace:</span></span>

```fsharp
do this.AddNamespace(namespaceName, types)
```

<span data-ttu-id="b3d47-169">Finalmente, agregue un atributo de ensamblado que indique que está creando una DLL de proveedor de tipos:</span><span class="sxs-lookup"><span data-stu-id="b3d47-169">Finally, add an assembly attribute that indicates that you are creating a type provider DLL:</span></span>

```fsharp
[<assembly:TypeProviderAssembly>]
do()
```

### <a name="providing-one-type-and-its-members"></a><span data-ttu-id="b3d47-170">Proporcionar un tipo y sus miembros</span><span class="sxs-lookup"><span data-stu-id="b3d47-170">Providing One Type And Its Members</span></span>

<span data-ttu-id="b3d47-171">La función `makeOneProvidedType` hace el trabajo real de proporcionar uno de los tipos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-171">The `makeOneProvidedType` function does the real work of providing one of the types.</span></span>

```fsharp
let makeOneProvidedType (n:int) =
…
```

<span data-ttu-id="b3d47-172">En este paso se explica la implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="b3d47-172">This step explains the implementation of this function.</span></span> <span data-ttu-id="b3d47-173">En primer lugar, cree el tipo proporcionado (por ejemplo, Type1, cuando n = 1, o Type57, cuando n = 57).</span><span class="sxs-lookup"><span data-stu-id="b3d47-173">First, create the provided type (for example, Type1, when n = 1, or Type57, when n = 57).</span></span>

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code,
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

<span data-ttu-id="b3d47-174">Debe tener en cuenta los puntos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b3d47-174">You should note the following points:</span></span>

- <span data-ttu-id="b3d47-175">Este tipo proporcionado es un tipo borrado.</span><span class="sxs-lookup"><span data-stu-id="b3d47-175">This provided type is erased.</span></span>  <span data-ttu-id="b3d47-176">Dado que indica que el tipo base es `obj` , las instancias aparecerán como valores de tipo [obj](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-obj.html) en código compilado.</span><span class="sxs-lookup"><span data-stu-id="b3d47-176">Because you indicate that the base type is `obj`, instances will appear as values of type [obj](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-obj.html) in compiled code.</span></span>

- <span data-ttu-id="b3d47-177">Cuando especifique un tipo no anidado, deberá especificar también el ensamblado y el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b3d47-177">When you specify a non-nested type, you must specify the assembly and namespace.</span></span> <span data-ttu-id="b3d47-178">Para los tipos borrados, el ensamblado deberá ser el propio ensamblado del proveedor de tipos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-178">For erased types, the assembly should be the type provider assembly itself.</span></span>

<span data-ttu-id="b3d47-179">A continuación, agregue la documentación XML al tipo.</span><span class="sxs-lookup"><span data-stu-id="b3d47-179">Next, add XML documentation to the type.</span></span> <span data-ttu-id="b3d47-180">Esta documentación se demora, es decir, se calcula a petición si el compilador host la necesita.</span><span class="sxs-lookup"><span data-stu-id="b3d47-180">This documentation is delayed, that is, computed on-demand if the host compiler needs it.</span></span>

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

<span data-ttu-id="b3d47-181">A continuación, agregue una propiedad estática proporcionada al tipo:</span><span class="sxs-lookup"><span data-stu-id="b3d47-181">Next you add a provided static property to the type:</span></span>

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty",
                                  propertyType = typeof<string>,
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

<span data-ttu-id="b3d47-182">Al obtener esta propiedad, siempre se evaluará como la cadena "Hello!".</span><span class="sxs-lookup"><span data-stu-id="b3d47-182">Getting this property will always evaluate to the string "Hello!".</span></span> <span data-ttu-id="b3d47-183">La función `GetterCode` de la propiedad utiliza una expresión de código delimitada de F# que representa el código que genera el compilador host para obtener la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b3d47-183">The `GetterCode` for the property uses an F# quotation, which represents the code that the host compiler generates for getting the property.</span></span> <span data-ttu-id="b3d47-184">Para obtener más información sobre las comillas, vea [expresiones de código delimitadas (F #)](../../language-reference/code-quotations.md).</span><span class="sxs-lookup"><span data-stu-id="b3d47-184">For more information about quotations, see [Code Quotations (F#)](../../language-reference/code-quotations.md).</span></span>

<span data-ttu-id="b3d47-185">Agregue la documentación XML a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b3d47-185">Add XML documentation to the property.</span></span>

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

<span data-ttu-id="b3d47-186">Ahora asocie la propiedad proporcionada al tipo proporcionado.</span><span class="sxs-lookup"><span data-stu-id="b3d47-186">Now attach the provided property to the provided type.</span></span> <span data-ttu-id="b3d47-187">Debe asociar un miembro proporcionado a un único tipo.</span><span class="sxs-lookup"><span data-stu-id="b3d47-187">You must attach a provided member to one and only one type.</span></span> <span data-ttu-id="b3d47-188">De lo contrario, el miembro nunca será accesible.</span><span class="sxs-lookup"><span data-stu-id="b3d47-188">Otherwise, the member will never be accessible.</span></span>

```fsharp
t.AddMember staticProp
```

<span data-ttu-id="b3d47-189">Ahora cree un constructor proporcionado que no reciba ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="b3d47-189">Now create a provided constructor that takes no parameters.</span></span>

```fsharp
let ctor = ProvidedConstructor(parameters = [ ],
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

<span data-ttu-id="b3d47-190">La función `InvokeCode` del constructor devuelve una expresión de código delimitada de F# que representa el código que el compilador host genera cuando se llama al constructor.</span><span class="sxs-lookup"><span data-stu-id="b3d47-190">The `InvokeCode` for the constructor returns an F# quotation, which represents the code that the host compiler generates when the constructor is called.</span></span> <span data-ttu-id="b3d47-191">Por ejemplo, puede usar el constructor siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3d47-191">For example, you can use the following constructor:</span></span>

```fsharp
new Type10()
```

<span data-ttu-id="b3d47-192">Se creará una instancia del tipo proporcionado con los datos subyacentes "The object data".</span><span class="sxs-lookup"><span data-stu-id="b3d47-192">An instance of the provided type will be created with underlying data "The object data".</span></span> <span data-ttu-id="b3d47-193">El código entre comillas incluye una conversión a [obj](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-obj.html) porque ese tipo es el borrado de este tipo proporcionado (como se especificó al declarar el tipo proporcionado).</span><span class="sxs-lookup"><span data-stu-id="b3d47-193">The quoted code includes a conversion to [obj](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-obj.html) because that type is the erasure of this provided type (as you specified when you declared the provided type).</span></span>

<span data-ttu-id="b3d47-194">Agregue la documentación XML al constructor y agregue el constructor proporcionado al tipo proporcionado:</span><span class="sxs-lookup"><span data-stu-id="b3d47-194">Add XML documentation to the constructor, and add the provided constructor to the provided type:</span></span>

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

<span data-ttu-id="b3d47-195">Cree un segundo constructor proporcionado que tome un parámetro:</span><span class="sxs-lookup"><span data-stu-id="b3d47-195">Create a second provided constructor that takes one parameter:</span></span>

```fsharp
let ctor2 =
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ],
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

<span data-ttu-id="b3d47-196">La función `InvokeCode` del constructor devuelve de nuevo una expresión de código delimitada de F# que representa el código que el compilador host generó para una llamada al método.</span><span class="sxs-lookup"><span data-stu-id="b3d47-196">The `InvokeCode` for the constructor again returns an F# quotation, which represents the code that the host compiler generated for a call to the method.</span></span> <span data-ttu-id="b3d47-197">Por ejemplo, puede usar el constructor siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3d47-197">For example, you can use the following constructor:</span></span>

```fsharp
new Type10("ten")
```

<span data-ttu-id="b3d47-198">Se crea una instancia del tipo proporcionado con los datos subyacentes "ten".</span><span class="sxs-lookup"><span data-stu-id="b3d47-198">An instance of the provided type is created with underlying data "ten".</span></span> <span data-ttu-id="b3d47-199">Es posible que haya notado que la función `InvokeCode` devuelve una expresión de código delimitada.</span><span class="sxs-lookup"><span data-stu-id="b3d47-199">You may have already noticed that the `InvokeCode` function returns a quotation.</span></span> <span data-ttu-id="b3d47-200">La entrada de esta función es una lista de expresiones, una por cada parámetro del constructor.</span><span class="sxs-lookup"><span data-stu-id="b3d47-200">The input to this function is a list of expressions, one per constructor parameter.</span></span> <span data-ttu-id="b3d47-201">En este caso, una expresión que representa el valor del único parámetro está disponible en `args.[0]`.</span><span class="sxs-lookup"><span data-stu-id="b3d47-201">In this case, an expression that represents the single parameter value is available in `args.[0]`.</span></span> <span data-ttu-id="b3d47-202">El código de una llamada al constructor convierte el valor devuelto en el tipo borrado `obj`.</span><span class="sxs-lookup"><span data-stu-id="b3d47-202">The code for a call to the constructor coerces the return value to the erased type `obj`.</span></span> <span data-ttu-id="b3d47-203">Después de agregar el segundo constructor proporcionado al tipo, cree una propiedad de instancia proporcionada:</span><span class="sxs-lookup"><span data-stu-id="b3d47-203">After you add the second provided constructor to the type, you create a provided instance property:</span></span>

```fsharp
let instanceProp =
    ProvidedProperty(propertyName = "InstanceProperty",
                     propertyType = typeof<int>,
                     getterCode= (fun args ->
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

<span data-ttu-id="b3d47-204">Al obtener esta propiedad, se devuelve la longitud de la cadena, que es el objeto de representación.</span><span class="sxs-lookup"><span data-stu-id="b3d47-204">Getting this property will return the length of the string, which is the representation object.</span></span> <span data-ttu-id="b3d47-205">La propiedad `GetterCode` devuelve una expresión de código delimitada de F# que especifica el código que genera el compilador host para obtener la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b3d47-205">The `GetterCode` property returns an F# quotation that specifies the code that the host compiler generates to get the property.</span></span> <span data-ttu-id="b3d47-206">Al igual que la función `InvokeCode`, la función `GetterCode` devuelve una expresión de código delimitada.</span><span class="sxs-lookup"><span data-stu-id="b3d47-206">Like `InvokeCode`, the `GetterCode` function returns a quotation.</span></span> <span data-ttu-id="b3d47-207">El compilador host llama a esta función con una lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-207">The host compiler calls this function with a list of arguments.</span></span> <span data-ttu-id="b3d47-208">En este caso, los argumentos incluyen solo la expresión única que representa la instancia en la que se llama al captador, a la que se puede tener acceso mediante `args.[0]` .</span><span class="sxs-lookup"><span data-stu-id="b3d47-208">In this case, the arguments include just the single expression that represents the instance upon which the getter is being called, which you can access by using `args.[0]`.</span></span> <span data-ttu-id="b3d47-209">La implementación de `GetterCode` después se inserta en el presupuesto de resultados en el tipo borrado `obj` y se usa una conversión para satisfacer el mecanismo del compilador para comprobar los tipos que el objeto es una cadena.</span><span class="sxs-lookup"><span data-stu-id="b3d47-209">The implementation of `GetterCode` then splices into the result quotation at the erased type `obj`, and a cast is used to satisfy the compiler's mechanism for checking types that the object is a string.</span></span> <span data-ttu-id="b3d47-210">La parte siguiente de `makeOneProvidedType` proporciona un método de instancia con un parámetro.</span><span class="sxs-lookup"><span data-stu-id="b3d47-210">The next part of `makeOneProvidedType` provides an instance method with one parameter.</span></span>

```fsharp
let instanceMeth =
    ProvidedMethod(methodName = "InstanceMethod",
                   parameters = [ProvidedParameter("x",typeof<int>)],
                   returnType = typeof<char>,
                   invokeCode = (fun args ->
                       <@@ ((%%(args.[0]) : obj) :?> string).Chars(%%(args.[1]) : int) @@>))

instanceMeth.AddXmlDocDelayed(fun () -> "This is an instance method")
// Add the instance method to the type.
t.AddMember instanceMeth
```

<span data-ttu-id="b3d47-211">Finalmente, cree un tipo anidado que contenga 100 propiedades anidadas.</span><span class="sxs-lookup"><span data-stu-id="b3d47-211">Finally, create a nested type that contains 100 nested properties.</span></span> <span data-ttu-id="b3d47-212">La creación de este tipo anidado y sus propiedades se demora, es decir, se calcula a petición.</span><span class="sxs-lookup"><span data-stu-id="b3d47-212">The creation of this nested type and its properties is delayed, that is, computed on-demand.</span></span>

```fsharp
t.AddMembersDelayed(fun () ->
  let nestedType = ProvidedTypeDefinition("NestedType", Some typeof<obj>)

  nestedType.AddMembersDelayed (fun () ->
    let staticPropsInNestedType =
      [
          for i in 1 .. 100 ->
              let valueOfTheProperty = "I am string "  + string i

              let p =
                ProvidedProperty(propertyName = "StaticProperty" + string i,
                  propertyType = typeof<string>,
                  isStatic = true,
                  getterCode= (fun args -> <@@ valueOfTheProperty @@>))

              p.AddXmlDocDelayed(fun () ->
                  sprintf "This is StaticProperty%d on NestedType" i)

              p
      ]

    staticPropsInNestedType)

  [nestedType])
```

### <a name="details-about-erased-provided-types"></a><span data-ttu-id="b3d47-213">Detalles sobre los tipos proporcionados borrados</span><span class="sxs-lookup"><span data-stu-id="b3d47-213">Details about Erased Provided Types</span></span>

<span data-ttu-id="b3d47-214">En el ejemplo de esta sección se proporcionan solo *tipos proporcionados borrados*, que son especialmente útiles en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b3d47-214">The example in this section provides only *erased provided types*, which are particularly useful in the following situations:</span></span>

- <span data-ttu-id="b3d47-215">Cuando se escribe un proveedor para un espacio de información que solo contiene datos y métodos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-215">When you are writing a provider for an information space that contains only data and methods.</span></span>

- <span data-ttu-id="b3d47-216">Cuando se escribe un proveedor en el que la semántica precisa de tipos en tiempo de ejecución no es fundamental para el uso práctico del espacio de información.</span><span class="sxs-lookup"><span data-stu-id="b3d47-216">When you are writing a provider where accurate runtime-type semantics aren't critical for practical use of the information space.</span></span>

- <span data-ttu-id="b3d47-217">Cuando se escribe un proveedor para un espacio de información que es tan grande y está tan interconectado que no es técnicamente factible generar tipos reales de .NET para el espacio de información.</span><span class="sxs-lookup"><span data-stu-id="b3d47-217">When you are writing a provider for an information space that is so large and interconnected that it isn’t technically feasible to generate real .NET types for the information space.</span></span>

<span data-ttu-id="b3d47-218">En este ejemplo, se borra cada tipo proporcionado para el tipo `obj` y todos los usos del tipo aparecen como tipo `obj` en el código compilado.</span><span class="sxs-lookup"><span data-stu-id="b3d47-218">In this example, each provided type is erased to type `obj`, and all uses of the type will appear as type `obj` in compiled code.</span></span> <span data-ttu-id="b3d47-219">De hecho, los objetos subyacentes de estos ejemplos son cadenas, pero el tipo aparecerá como `System.Object` en el código compilado de .NET.</span><span class="sxs-lookup"><span data-stu-id="b3d47-219">In fact, the underlying objects in these examples are strings, but the type will appear as `System.Object` in .NET compiled code.</span></span> <span data-ttu-id="b3d47-220">Como con todos los usos del borrado de tipos, se puede utilizar la conversión boxing explícita, la conversión unboxing y la conversión para trastocar los tipos borrados.</span><span class="sxs-lookup"><span data-stu-id="b3d47-220">As with all uses of type erasure, you can use explicit boxing, unboxing, and casting to subvert erased types.</span></span> <span data-ttu-id="b3d47-221">En este caso, puede producirse una excepción de conversión no válida cuando se utiliza el objeto.</span><span class="sxs-lookup"><span data-stu-id="b3d47-221">In this case, a cast exception that isn’t valid may result when the object is used.</span></span> <span data-ttu-id="b3d47-222">Un runtime de un proveedor puede definir su propio tipo de representación privado para ayudar a protegerse contra representaciones falsas.</span><span class="sxs-lookup"><span data-stu-id="b3d47-222">A provider runtime can define its own private representation type to help protect against false representations.</span></span> <span data-ttu-id="b3d47-223">No se pueden definir tipos borrados en F#.</span><span class="sxs-lookup"><span data-stu-id="b3d47-223">You can’t define erased types in F# itself.</span></span> <span data-ttu-id="b3d47-224">Solo se pueden borrar los tipos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="b3d47-224">Only provided types may be erased.</span></span> <span data-ttu-id="b3d47-225">Se deben entender las implicaciones, tanto prácticas como semánticas, de utilizar los tipos borrados para el proveedor de tipo o un proveedor que proporcione tipos borrados.</span><span class="sxs-lookup"><span data-stu-id="b3d47-225">You must understand the ramifications, both practical and semantic, of using either erased types for your type provider or a provider that provides erased types.</span></span> <span data-ttu-id="b3d47-226">Un tipo borrado no tiene un tipo real de .NET.</span><span class="sxs-lookup"><span data-stu-id="b3d47-226">An erased type has no real .NET type.</span></span> <span data-ttu-id="b3d47-227">Por consiguiente, no se puede hacer una reflexión precisa sobre el tipo y se podrían trastocar los tipos borrados si se utilizan conversiones en tiempo de ejecución y otras técnicas que dependen de semánticas exactas de tipos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b3d47-227">Therefore, you cannot do accurate reflection over the type, and you might subvert erased types if you use runtime casts and other techniques that rely on exact runtime type semantics.</span></span> <span data-ttu-id="b3d47-228">El trastocamiento de tipos borrados frecuentemente da lugar a excepciones de conversión de tipos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b3d47-228">Subversion of erased types frequently results in type cast exceptions at runtime.</span></span>

### <a name="choosing-representations-for-erased-provided-types"></a><span data-ttu-id="b3d47-229">Elegir representaciones para los tipos proporcionados borrados</span><span class="sxs-lookup"><span data-stu-id="b3d47-229">Choosing Representations for Erased Provided Types</span></span>

<span data-ttu-id="b3d47-230">Para algunos usos de los tipos proporcionados borrados, no se requiere ninguna representación.</span><span class="sxs-lookup"><span data-stu-id="b3d47-230">For some uses of erased provided types, no representation is required.</span></span> <span data-ttu-id="b3d47-231">Por ejemplo, el tipo proporcionado borrado podría contener únicamente propiedades y miembros estáticos y ningún constructor, por lo que ningún método ni propiedad devolvería ninguna instancia del tipo.</span><span class="sxs-lookup"><span data-stu-id="b3d47-231">For example, the erased provided type might contain only static properties and members and no constructors, and no methods or properties would return an instance of the type.</span></span> <span data-ttu-id="b3d47-232">Si puede tener acceso a instancias de un tipo proporcionado borrado, considere las preguntas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b3d47-232">If you can reach instances of an erased provided type, you must consider the following questions:</span></span>

<span data-ttu-id="b3d47-233">**¿Qué es el borrado de un tipo proporcionado?**</span><span class="sxs-lookup"><span data-stu-id="b3d47-233">**What is the erasure of a provided type?**</span></span>

- <span data-ttu-id="b3d47-234">El borrado de un tipo proporcionado es el modo en que el tipo aparece en el código compilado de .NET.</span><span class="sxs-lookup"><span data-stu-id="b3d47-234">The erasure of a provided type is how the type appears in compiled .NET code.</span></span>

- <span data-ttu-id="b3d47-235">El borrado de una clase de un tipo proporcionado borrado siempre es el primer tipo base no borrado de la cadena de herencia del tipo.</span><span class="sxs-lookup"><span data-stu-id="b3d47-235">The erasure of a provided erased class type is always the first non-erased base type in the inheritance chain of the type.</span></span>

- <span data-ttu-id="b3d47-236">El borrado de una interfaz de un tipo de borrado proporcionado es siempre `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="b3d47-236">The erasure of a provided erased interface type is always `System.Object`.</span></span>

<span data-ttu-id="b3d47-237">**¿Qué son las representaciones de un tipo proporcionado?**</span><span class="sxs-lookup"><span data-stu-id="b3d47-237">**What are the representations of a provided type?**</span></span>

- <span data-ttu-id="b3d47-238">Se denomina representaciones al conjunto de objetos posibles para un tipo proporcionado borrado.</span><span class="sxs-lookup"><span data-stu-id="b3d47-238">The set of possible objects for an erased provided type are called its representations.</span></span> <span data-ttu-id="b3d47-239">En el ejemplo de este documento, las representaciones de todos los tipos proporcionados borrados `Type1..Type100` son siempre objetos de cadena.</span><span class="sxs-lookup"><span data-stu-id="b3d47-239">In the example in this document, the representations of all the erased provided types `Type1..Type100` are always string objects.</span></span>

<span data-ttu-id="b3d47-240">Todas las representaciones de un tipo proporcionado deben ser compatibles con el borrado del tipo proporcionado.</span><span class="sxs-lookup"><span data-stu-id="b3d47-240">All representations of a provided type must be compatible with the erasure of the provided type.</span></span> <span data-ttu-id="b3d47-241">(De lo contrario, el compilador de F# generará un error para un uso del proveedor de tipos o se generará código no comprobable de .NET que no es válido.</span><span class="sxs-lookup"><span data-stu-id="b3d47-241">(Otherwise, either the F# compiler will give an error for a use of the type provider, or unverifiable .NET code that isn't valid will be generated.</span></span> <span data-ttu-id="b3d47-242">Un proveedor de tipos no es válido si devuelve código que proporciona una representación no válida).</span><span class="sxs-lookup"><span data-stu-id="b3d47-242">A type provider isn’t valid if it returns code that gives a  representation that isn't valid.)</span></span>

<span data-ttu-id="b3d47-243">Se puede elegir una representación para los objetos proporcionados mediante uno de los dos métodos siguientes, los cuales son muy comunes:</span><span class="sxs-lookup"><span data-stu-id="b3d47-243">You can choose a representation for provided objects by using either of the following approaches, both of which are very common:</span></span>

- <span data-ttu-id="b3d47-244">Si lo que se hace es simplemente proporcionar un contenedor fuertemente tipado sobre un tipo existente de .NET, tiene sentido que el tipo borre ese tipo, use instancias de ese tipo como representaciones, o ambas cosas.</span><span class="sxs-lookup"><span data-stu-id="b3d47-244">If you're simply providing a strongly typed wrapper over an existing .NET type, it often makes sense for your type to erase to that type, use instances of that type as representations, or both.</span></span> <span data-ttu-id="b3d47-245">Este enfoque es adecuado cuando la mayoría de los métodos existentes en ese tipo tienen sentido al usar la versión fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="b3d47-245">This approach is appropriate when most of the existing methods on that type still make sense when using the strongly typed version.</span></span>

- <span data-ttu-id="b3d47-246">Si lo que se desea es crear una API que difiera significativamente de cualquier API existente de .NET, tiene sentido crear tipos en tiempo de ejecución que constituyan la representación y el borrado de tipos para los tipos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="b3d47-246">If you want to create an API that differs significantly from any existing .NET API, it makes sense to create runtime types that will be the type erasure and representations for the provided types.</span></span>

<span data-ttu-id="b3d47-247">El ejemplo de este documento utiliza cadenas como representaciones de los objetos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="b3d47-247">The example in this document uses strings as representations of provided objects.</span></span> <span data-ttu-id="b3d47-248">Con frecuencia, puede ser adecuado utilizar otros objetos para las representaciones.</span><span class="sxs-lookup"><span data-stu-id="b3d47-248">Frequently, it may be appropriate to use other objects for representations.</span></span> <span data-ttu-id="b3d47-249">Por ejemplo, se puede utilizar un diccionario como contenedor de propiedades:</span><span class="sxs-lookup"><span data-stu-id="b3d47-249">For example, you may use a dictionary as a property bag:</span></span>

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

<span data-ttu-id="b3d47-250">También se puede definir un tipo en el proveedor de tipos que se usará en runtime para formar la representación, junto con una o más operaciones en runtime:</span><span class="sxs-lookup"><span data-stu-id="b3d47-250">As an alternative, you may define a type in your type provider that will be used at runtime to form the representation, along with one or more runtime operations:</span></span>

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

<span data-ttu-id="b3d47-251">Entonces los miembros proporcionados podrán construir instancias de este tipo de objeto:</span><span class="sxs-lookup"><span data-stu-id="b3d47-251">Provided members can then construct instances of this object type:</span></span>

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

<span data-ttu-id="b3d47-252">En este caso, se puede (opcionalmente) utilizar este tipo como borrado de tipos especificando este tipo como `baseType` al construir `ProvidedTypeDefinition`:</span><span class="sxs-lookup"><span data-stu-id="b3d47-252">In this case, you may (optionally) use this type as the type erasure by specifying this type as the `baseType` when constructing the `ProvidedTypeDefinition`:</span></span>

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a><span data-ttu-id="b3d47-253">Lecciones principales</span><span class="sxs-lookup"><span data-stu-id="b3d47-253">Key Lessons</span></span>

<span data-ttu-id="b3d47-254">En la sección anterior se explicó cómo crear un proveedor de tipos de borrado simple que proporciona una serie de tipos, propiedades y métodos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-254">The previous section explained how to create a simple erasing type provider that provides a range of types, properties, and methods.</span></span> <span data-ttu-id="b3d47-255">En dicha sección se explicó también el concepto de borrado de tipos, incluidas algunas de las ventajas y desventajas de proporcionar tipos borrados desde un proveedor de tipos, y se explicaron las representaciones de los tipos borrados.</span><span class="sxs-lookup"><span data-stu-id="b3d47-255">This section also explained the concept of type erasure, including some of the advantages and disadvantages of providing erased types from a type provider, and discussed representations of erased types.</span></span>

## <a name="a-type-provider-that-uses-static-parameters"></a><span data-ttu-id="b3d47-256">Un proveedor de tipos que usa parámetros estáticos</span><span class="sxs-lookup"><span data-stu-id="b3d47-256">A Type Provider That Uses Static Parameters</span></span>

<span data-ttu-id="b3d47-257">La capacidad de parametrizar los proveedores de tipo mediante datos estáticos permite muchos escenarios interesantes, incluso en los casos en que el proveedor no necesita tener acceso a ningún dato local o remoto.</span><span class="sxs-lookup"><span data-stu-id="b3d47-257">The ability to parameterize type providers by static data enables many interesting scenarios, even in cases when the provider doesn't need to access any local or remote data.</span></span> <span data-ttu-id="b3d47-258">En esta sección, aprenderá algunas técnicas básicas para construir tales proveedores.</span><span class="sxs-lookup"><span data-stu-id="b3d47-258">In this section, you’ll learn some basic techniques for putting together such a provider.</span></span>

### <a name="type-checked-regex-provider"></a><span data-ttu-id="b3d47-259">Proveedor de tipo de comprobación de expresiones regulares</span><span class="sxs-lookup"><span data-stu-id="b3d47-259">Type Checked Regex Provider</span></span>

<span data-ttu-id="b3d47-260">Imagine que desea implementar un proveedor de tipos para expresiones regulares que contenga las bibliotecas <xref:System.Text.RegularExpressions.Regex> de .NET en una interfaz que proporcione las siguientes garantías en tiempo de compilación:</span><span class="sxs-lookup"><span data-stu-id="b3d47-260">Imagine that you want to implement a type provider for regular expressions that wraps the .NET <xref:System.Text.RegularExpressions.Regex> libraries in an interface that provides the following compile-time guarantees:</span></span>

- <span data-ttu-id="b3d47-261">Comprobar si una expresión regular es válida.</span><span class="sxs-lookup"><span data-stu-id="b3d47-261">Verifying whether a regular expression is valid.</span></span>

- <span data-ttu-id="b3d47-262">Proporcionar propiedades con nombre en las coincidencias basadas en cualquier nombre de grupo de la expresión regular.</span><span class="sxs-lookup"><span data-stu-id="b3d47-262">Providing named properties on matches that are based on any group names in the regular expression.</span></span>

<span data-ttu-id="b3d47-263">En esta sección se muestra cómo utilizar los proveedores de tipo para crear un tipo `RegexTyped` parametrizado por el patrón de expresiones regulares para proporcionar estas ventajas.</span><span class="sxs-lookup"><span data-stu-id="b3d47-263">This section shows you how to use type providers to create a `RegexTyped` type that the regular expression pattern parameterizes to provide these benefits.</span></span> <span data-ttu-id="b3d47-264">El compilador notificará un error si el patrón proporcionado no es válido y el proveedor de tipos puede extraer los grupos del patrón de modo que se pueda tener acceso a ellos mediante propiedades con nombre en las coincidencias.</span><span class="sxs-lookup"><span data-stu-id="b3d47-264">The compiler will report an error if the supplied pattern isn't valid, and the type provider can extract the groups from the pattern so that you can access them by using named properties on matches.</span></span> <span data-ttu-id="b3d47-265">Cuando se diseña un proveedor de tipo, se debería considerar el aspecto que debería presentar su API expuesta para los usuarios finales y cómo se traducirá este diseño a código de .NET.</span><span class="sxs-lookup"><span data-stu-id="b3d47-265">When you design a type provider, you should consider how its exposed API should look to end users and how this design will translate to .NET code.</span></span> <span data-ttu-id="b3d47-266">El ejemplo siguiente muestra cómo usar una API como esta para obtener los componentes del código de área de un número de teléfono:</span><span class="sxs-lookup"><span data-stu-id="b3d47-266">The following example shows how to use such an API to get the components of the area code:</span></span>

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

<span data-ttu-id="b3d47-267">El ejemplo siguiente muestra cómo convierte el proveedor de tipos estas llamadas:</span><span class="sxs-lookup"><span data-stu-id="b3d47-267">The following example shows how the type provider translates these calls:</span></span>

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

<span data-ttu-id="b3d47-268">Tenga en cuenta los puntos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b3d47-268">Note the following points:</span></span>

- <span data-ttu-id="b3d47-269">El tipo estándar Regex representa el tipo parametrizado `RegexTyped`.</span><span class="sxs-lookup"><span data-stu-id="b3d47-269">The standard Regex type represents the parameterized `RegexTyped` type.</span></span>

- <span data-ttu-id="b3d47-270">El constructor `RegexTyped` produce una llamada al constructor Regex y le pasa el argumento de tipo estático para el patrón.</span><span class="sxs-lookup"><span data-stu-id="b3d47-270">The `RegexTyped` constructor results in a call to the Regex constructor, passing in the static type argument for the pattern.</span></span>

- <span data-ttu-id="b3d47-271">Los resultados del método `Match` se representan mediante el tipo estándar <xref:System.Text.RegularExpressions.Match>.</span><span class="sxs-lookup"><span data-stu-id="b3d47-271">The results of the `Match` method are represented by the standard <xref:System.Text.RegularExpressions.Match> type.</span></span>

- <span data-ttu-id="b3d47-272">Cada grupo con nombre produce una propiedad proporcionada, y el acceso a la propiedad produce el uso de un indizador en la colección `Groups` de una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="b3d47-272">Each named group results in a provided property, and accessing the property results in a use of an indexer on a match’s `Groups` collection.</span></span>

<span data-ttu-id="b3d47-273">El código siguiente es la base de la lógica para implementar un proveedor como este y este ejemplo omite la adición de todos los miembros al tipo proporcionado.</span><span class="sxs-lookup"><span data-stu-id="b3d47-273">The following code is the core of the logic to implement such a provider, and this example omits the addition of all members to the provided type.</span></span> <span data-ttu-id="b3d47-274">Para obtener información sobre cada miembro agregado, consulte la sección correspondiente más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="b3d47-274">For information about each added member, see the appropriate section later in this topic.</span></span> <span data-ttu-id="b3d47-275">Para obtener el código completo, descargue el ejemplo del [paquete de ejemplo de F # 3,0](https://archive.codeplex.com/?p=fsharp3sample) en el sitio web de codeplex.</span><span class="sxs-lookup"><span data-stu-id="b3d47-275">For the full code, download the sample from the [F# 3.0 Sample Pack](https://archive.codeplex.com/?p=fsharp3sample) on the CodePlex website.</span></span>

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams,
        instantiationFunction=(fun typeName parameterValues ->

          match parameterValues with
          | [| :? string as pattern|] ->

            // Create an instance of the regular expression.
            //
            // This will fail with System.ArgumentException if the regular expression is not valid.
            // The exception will escape the type provider and be reported in client code.
            let r = System.Text.RegularExpressions.Regex(pattern)

            // Declare the typed regex provided type.
            // The type erasure of this type is 'obj', even though the representation will always be a Regex
            // This, combined with hiding the object methods, makes the IntelliSense experience simpler.
            let ty =
              ProvidedTypeDefinition(
                thisAssembly,
                rootNamespace,
                typeName,
                baseType = Some baseTy)

            ...

            ty
          | _ -> failwith "unexpected parameter values"))

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

<span data-ttu-id="b3d47-276">Tenga en cuenta los puntos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b3d47-276">Note the following points:</span></span>

- <span data-ttu-id="b3d47-277">El proveedor de tipos toma dos parámetros estáticos: `pattern`, el patrón, que es obligatorio, y `options`, las opciones, que son opcionales (porque se proporciona un valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="b3d47-277">The type provider takes two static parameters: the `pattern`, which is mandatory, and the `options`, which are optional (because a default value is provided).</span></span>

- <span data-ttu-id="b3d47-278">Después de proporcionar los argumentos estáticos, se crea una instancia de la expresión regular.</span><span class="sxs-lookup"><span data-stu-id="b3d47-278">After the static arguments are supplied, you create an instance of the regular expression.</span></span> <span data-ttu-id="b3d47-279">Esta instancia inicia una excepción si la Regex no es correcta, y se notifica el error a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b3d47-279">This instance will throw an exception if the Regex is malformed, and this error will be reported to users.</span></span>

- <span data-ttu-id="b3d47-280">El tipo que se devolverá cuando se den los argumentos se define dentro de la devolución de llamada `DefineStaticParameters`.</span><span class="sxs-lookup"><span data-stu-id="b3d47-280">Within the `DefineStaticParameters` callback, you define the type that will be returned after the arguments are supplied.</span></span>

- <span data-ttu-id="b3d47-281">Este código establece `HideObjectMethods` en true para que el uso de IntelliSense siga estando optimizado.</span><span class="sxs-lookup"><span data-stu-id="b3d47-281">This code sets `HideObjectMethods` to true so that the IntelliSense experience will remain streamlined.</span></span> <span data-ttu-id="b3d47-282">Este atributo hace que los miembros `Equals`, `GetHashCode`, `Finalize` y `GetType` se supriman de listas de IntelliSense para un objeto proporcionado.</span><span class="sxs-lookup"><span data-stu-id="b3d47-282">This attribute causes the `Equals`, `GetHashCode`, `Finalize`, and `GetType` members to be suppressed from IntelliSense lists for a provided object.</span></span>

- <span data-ttu-id="b3d47-283">Se utiliza `obj` como tipo base del método, pero se utilizará un objeto `Regex` como representación en tiempo de ejecución de este tipo, como muestra el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b3d47-283">You use `obj` as the base type of the method, but you’ll use a `Regex` object as the runtime representation of this type, as the next example shows.</span></span>

- <span data-ttu-id="b3d47-284">La llamada al constructor `Regex` inicia una excepción <xref:System.ArgumentException> cuando una expresión regular no es válida.</span><span class="sxs-lookup"><span data-stu-id="b3d47-284">The call to the `Regex` constructor throws a <xref:System.ArgumentException> when a regular expression isn’t valid.</span></span> <span data-ttu-id="b3d47-285">El compilador detecta esta excepción y envía un mensaje de error al usuario en tiempo de compilación o en el editor de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b3d47-285">The compiler catches this exception and reports an error message to the user at compile time or in the Visual Studio editor.</span></span> <span data-ttu-id="b3d47-286">Esta excepción permite que las expresiones regulares se validen sin ejecutar una aplicación.</span><span class="sxs-lookup"><span data-stu-id="b3d47-286">This exception enables regular expressions to be validated without running an application.</span></span>

<span data-ttu-id="b3d47-287">El tipo definido anteriormente todavía no es útil porque no contiene propiedades ni métodos significativos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-287">The type defined above isn't useful yet because it doesn’t contain any meaningful methods or properties.</span></span> <span data-ttu-id="b3d47-288">En primer lugar, agregue un método `IsMatch` estático:</span><span class="sxs-lookup"><span data-stu-id="b3d47-288">First, add a static `IsMatch` method:</span></span>

```fsharp
let isMatch =
    ProvidedMethod(
        methodName = "IsMatch",
        parameters = [ProvidedParameter("input", typeof<string>)],
        returnType = typeof<bool>,
        isStatic = true,
        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>)

isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string."
ty.AddMember isMatch
```

<span data-ttu-id="b3d47-289">El código anterior define un método `IsMatch`, que toma una cadena como entrada y devuelve un valor `bool`.</span><span class="sxs-lookup"><span data-stu-id="b3d47-289">The previous code defines a method `IsMatch`, which takes a string as input and returns a `bool`.</span></span> <span data-ttu-id="b3d47-290">La única parte difícil es el uso del argumento `args` dentro de la definición de la función `InvokeCode`.</span><span class="sxs-lookup"><span data-stu-id="b3d47-290">The only tricky part is the use of the `args` argument within the `InvokeCode` definition.</span></span> <span data-ttu-id="b3d47-291">En este ejemplo, `args` es una lista de expresiones de código delimitadas que representa los argumentos de este método.</span><span class="sxs-lookup"><span data-stu-id="b3d47-291">In this example, `args` is a list of quotations that represents the arguments to this method.</span></span> <span data-ttu-id="b3d47-292">Si el método es un método de instancia, el primer argumento representa el argumento `this`.</span><span class="sxs-lookup"><span data-stu-id="b3d47-292">If the method is an instance method, the first argument represents the `this` argument.</span></span> <span data-ttu-id="b3d47-293">Sin embargo, para un método estático, los argumentos son simplemente los argumentos explícitos para el método.</span><span class="sxs-lookup"><span data-stu-id="b3d47-293">However, for a static method, the arguments are all just the explicit arguments to the method.</span></span> <span data-ttu-id="b3d47-294">Observe que el tipo del valor de la expresión de código delimitada debe coincidir con el tipo del valor devuelto especificado (en este caso, `bool`).</span><span class="sxs-lookup"><span data-stu-id="b3d47-294">Note that the type of the quoted value should match the specified return type (in this case, `bool`).</span></span> <span data-ttu-id="b3d47-295">Observe también que este código utiliza el método `AddXmlDoc` para asegurarse de que el método proporcionado también tiene documentación útil, que se puede proporcionar con IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="b3d47-295">Also note that this code uses the `AddXmlDoc` method to make sure that the provided method also has useful documentation, which you can supply through IntelliSense.</span></span>

<span data-ttu-id="b3d47-296">A continuación, agregue un método de instancia Match.</span><span class="sxs-lookup"><span data-stu-id="b3d47-296">Next, add an instance Match method.</span></span> <span data-ttu-id="b3d47-297">Sin embargo, este método debe devolver un valor de un tipo `Match` proporcionado, de modo que se pueda tener acceso a los grupos de manera fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="b3d47-297">However, this method should return a value of a provided `Match` type so that the groups can be accessed in a strongly typed fashion.</span></span> <span data-ttu-id="b3d47-298">Por ello, primero se declara el tipo `Match`.</span><span class="sxs-lookup"><span data-stu-id="b3d47-298">Thus, you first declare the `Match` type.</span></span> <span data-ttu-id="b3d47-299">Como este tipo depende del patrón que se proporcionó como argumento estático, este tipo debe estar anidado dentro de la definición de tipos parametrizados:</span><span class="sxs-lookup"><span data-stu-id="b3d47-299">Because this type depends on the pattern that was supplied as a static argument, this type must be nested within the parameterized type definition:</span></span>

```fsharp
let matchTy =
    ProvidedTypeDefinition(
        "MatchType",
        baseType = Some baseTy,
        hideObjectMethods = true)

ty.AddMember matchTy
```

<span data-ttu-id="b3d47-300">A continuación, se agrega una propiedad al tipo Match de cada grupo.</span><span class="sxs-lookup"><span data-stu-id="b3d47-300">You then add one property to the Match type for each group.</span></span> <span data-ttu-id="b3d47-301">En tiempo de ejecución, una coincidencia se representa como un valor <xref:System.Text.RegularExpressions.Match>, por lo que la expresión de código delimitada que define la propiedad debe utilizar la propiedad indizada <xref:System.Text.RegularExpressions.Match.Groups> para obtener el grupo pertinente.</span><span class="sxs-lookup"><span data-stu-id="b3d47-301">At runtime, a match is represented as a <xref:System.Text.RegularExpressions.Match> value, so the quotation that defines the property must use the <xref:System.Text.RegularExpressions.Match.Groups> indexed property to get the relevant group.</span></span>

```fsharp
for group in r.GetGroupNames() do
    // Ignore the group named 0, which represents all input.
    if group <> "0" then
    let prop =
      ProvidedProperty(
        propertyName = group,
        propertyType = typeof<Group>,
        getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
    matchTy.AddMember prop
```

<span data-ttu-id="b3d47-302">Una vez más, observe que se está agregando la documentación XML a la propiedad proporcionada.</span><span class="sxs-lookup"><span data-stu-id="b3d47-302">Again, note that you’re adding XML documentation to the provided property.</span></span> <span data-ttu-id="b3d47-303">También observe que una propiedad puede leerse si se proporciona una función `GetterCode` y puede escribirse si se proporciona una función `SetterCode`, por lo que la propiedad resultante es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="b3d47-303">Also note that a property can be read if a `GetterCode` function is provided, and the property can be written if a `SetterCode` function is provided, so the resulting property is read only.</span></span>

<span data-ttu-id="b3d47-304">Now you can create an instance method that returns a value of this `Match` type:</span><span class="sxs-lookup"><span data-stu-id="b3d47-304">Now you can create an instance method that returns a value of this `Match` type:</span></span>

```fsharp
let matchMethod =
    ProvidedMethod(
        methodName = "Match",
        parameters = [ProvidedParameter("input", typeof<string>)],
        returnType = matchTy,
        invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)

matchMeth.AddXmlDoc "Searches the specified input string for the first occurrence of this regular expression"

ty.AddMember matchMeth
```

<span data-ttu-id="b3d47-305">Como está creando un método de instancia, `args.[0]` representa la instancia de `RegexTyped` en la que se está llamando al método y `args.[1]` es el argumento de entrada.</span><span class="sxs-lookup"><span data-stu-id="b3d47-305">Because you are creating an instance method, `args.[0]` represents the `RegexTyped` instance on which the method is being called, and `args.[1]` is the input argument.</span></span>

<span data-ttu-id="b3d47-306">Finalmente, proporcione un constructor para que se puedan crear instancias del tipo proporcionado.</span><span class="sxs-lookup"><span data-stu-id="b3d47-306">Finally, provide a constructor so that instances of the provided type can be created.</span></span>

```fsharp
let ctor =
    ProvidedConstructor(
        parameters = [],
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

<span data-ttu-id="b3d47-307">El constructor simplemente borra para la creación de una Regex estándar de .NET, a la cual también se le aplica la conversión box en un objeto porque `obj` es el borrado del tipo proporcionado.</span><span class="sxs-lookup"><span data-stu-id="b3d47-307">The constructor merely erases to the creation of a standard .NET Regex instance, which is again boxed to an object because `obj` is the erasure of the provided type.</span></span> <span data-ttu-id="b3d47-308">Con ese cambio, el uso de la API de ejemplo especificada previamente en el tema funciona como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="b3d47-308">With that change, the sample API usage that specified earlier in the topic works as expected.</span></span> <span data-ttu-id="b3d47-309">A continuación se muestra la versión final del código completo:</span><span class="sxs-lookup"><span data-stu-id="b3d47-309">The following code is complete and final:</span></span>

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types.
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams,
        instantiationFunction=(fun typeName parameterValues ->

            match parameterValues with
            | [| :? string as pattern|] ->

                // Create an instance of the regular expression.

                let r = System.Text.RegularExpressions.Regex(pattern)

                // Declare the typed regex provided type.

                let ty =
                    ProvidedTypeDefinition(
                        thisAssembly,
                        rootNamespace,
                        typeName,
                        baseType = Some baseTy)

                ty.AddXmlDoc "A strongly typed interface to the regular expression '%s'"

                // Provide strongly typed version of Regex.IsMatch static method.
                let isMatch =
                    ProvidedMethod(
                        methodName = "IsMatch",
                        parameters = [ProvidedParameter("input", typeof<string>)],
                        returnType = typeof<bool>,
                        isStatic = true,
                        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>)

                isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string"

                ty.AddMember isMatch

                // Provided type for matches
                // Again, erase to obj even though the representation will always be a Match
                let matchTy =
                    ProvidedTypeDefinition(
                        "MatchType",
                        baseType = Some baseTy,
                        hideObjectMethods = true)

                // Nest the match type within parameterized Regex type.
                ty.AddMember matchTy

                // Add group properties to match type
                for group in r.GetGroupNames() do
                    // Ignore the group named 0, which represents all input.
                    if group <> "0" then
                        let prop =
                          ProvidedProperty(
                            propertyName = group,
                            propertyType = typeof<Group>,
                            getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
                        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
                        matchTy.AddMember(prop)

                // Provide strongly typed version of Regex.Match instance method.
                let matchMeth =
                  ProvidedMethod(
                    methodName = "Match",
                    parameters = [ProvidedParameter("input", typeof<string>)],
                    returnType = matchTy,
                    invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)
                matchMeth.AddXmlDoc "Searches the specified input string for the first occurrence of this regular expression"

                ty.AddMember matchMeth

                // Declare a constructor.
                let ctor =
                  ProvidedConstructor(
                    parameters = [],
                    invokeCode = fun args -> <@@ Regex(pattern) :> obj @@>)

                // Add documentation to the constructor.
                ctor.AddXmlDoc "Initializes a regular expression instance"

                ty.AddMember ctor

                ty
            | _ -> failwith "unexpected parameter values"))

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

### <a name="key-lessons"></a><span data-ttu-id="b3d47-310">Lecciones principales</span><span class="sxs-lookup"><span data-stu-id="b3d47-310">Key Lessons</span></span>

<span data-ttu-id="b3d47-311">En esta sección se ha explicado cómo crear un proveedor de tipos que opera con sus parámetros estáticos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-311">This section explained how to create a type provider that operates on its static parameters.</span></span> <span data-ttu-id="b3d47-312">El proveedor comprueba el parámetro estático y proporciona operaciones basadas en su valor.</span><span class="sxs-lookup"><span data-stu-id="b3d47-312">The provider checks the static parameter and provides operations based on its value.</span></span>

## <a name="a-type-provider-that-is-backed-by-local-data"></a><span data-ttu-id="b3d47-313">Un proveedor de tipos que está respaldado por datos locales</span><span class="sxs-lookup"><span data-stu-id="b3d47-313">A Type Provider That Is Backed By Local Data</span></span>

<span data-ttu-id="b3d47-314">Con frecuencia se requiere que los proveedores de tipos muestren API basadas no solo en parámetros estáticos sino también en información procedente de sistemas locales o remotos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-314">Frequently you might want type providers to present APIs based on not only static parameters but also information from local or remote systems.</span></span> <span data-ttu-id="b3d47-315">Esta sección trata sobre los proveedores de tipos basados en datos locales, como los archivos de datos locales.</span><span class="sxs-lookup"><span data-stu-id="b3d47-315">This section discusses type providers that are based on local data, such as local data files.</span></span>

### <a name="simple-csv-file-provider"></a><span data-ttu-id="b3d47-316">Proveedor simple de archivos CSV</span><span class="sxs-lookup"><span data-stu-id="b3d47-316">Simple CSV File Provider</span></span>

<span data-ttu-id="b3d47-317">Como ejemplo sencillo, considere un proveedor de tipo para tener acceso a datos científicos con el formato de valores separados por comas (CSV).</span><span class="sxs-lookup"><span data-stu-id="b3d47-317">As a simple example, consider a type provider for accessing scientific data in Comma Separated Value (CSV) format.</span></span> <span data-ttu-id="b3d47-318">En esta sección se supone que los archivos CSV contienen una fila de encabezado seguida de datos en coma flotante, como se muestra en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3d47-318">This section assumes that the CSV files contain a header row followed by floating point data, as the following table illustrates:</span></span>

|<span data-ttu-id="b3d47-319">Distancia (metros)</span><span class="sxs-lookup"><span data-stu-id="b3d47-319">Distance (meter)</span></span>|<span data-ttu-id="b3d47-320">Tiempo (segundos)</span><span class="sxs-lookup"><span data-stu-id="b3d47-320">Time (second)</span></span>|
|----------------|-------------|
|<span data-ttu-id="b3d47-321">50,0</span><span class="sxs-lookup"><span data-stu-id="b3d47-321">50.0</span></span>|<span data-ttu-id="b3d47-322">3.7</span><span class="sxs-lookup"><span data-stu-id="b3d47-322">3.7</span></span>|
|<span data-ttu-id="b3d47-323">100.0</span><span class="sxs-lookup"><span data-stu-id="b3d47-323">100.0</span></span>|<span data-ttu-id="b3d47-324">5.2</span><span class="sxs-lookup"><span data-stu-id="b3d47-324">5.2</span></span>|
|<span data-ttu-id="b3d47-325">150.0</span><span class="sxs-lookup"><span data-stu-id="b3d47-325">150.0</span></span>|<span data-ttu-id="b3d47-326">6.4</span><span class="sxs-lookup"><span data-stu-id="b3d47-326">6.4</span></span>|

<span data-ttu-id="b3d47-327">En esta sección se muestra cómo proporcionar un tipo que se puede usar para obtener filas con una propiedad `Distance` de tipo `float<meter>` y una propiedad `Time` de tipo `float<second>`.</span><span class="sxs-lookup"><span data-stu-id="b3d47-327">This section shows how to provide a type that you can use to get rows with a `Distance` property of type `float<meter>` and a `Time` property of type `float<second>`.</span></span> <span data-ttu-id="b3d47-328">Para simplificar, se realizan las suposiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b3d47-328">For simplicity, the following assumptions are made:</span></span>

- <span data-ttu-id="b3d47-329">Los nombres de encabezado son de unidad menos o tienen el formato "nombre (unidad)" y no contienen comas.</span><span class="sxs-lookup"><span data-stu-id="b3d47-329">Header names are either unit-less or have the form "Name (unit)" and don't contain commas.</span></span>

- <span data-ttu-id="b3d47-330">Las unidades son unidades internacionales (SI) del sistema, ya que el módulo [FSharp. Data. UnitSystems. Si. UnitNames (F #)](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-data-unitsystems-si-unitnames.html) define.</span><span class="sxs-lookup"><span data-stu-id="b3d47-330">Units are all System International (SI) units as the [FSharp.Data.UnitSystems.SI.UnitNames Module (F#)](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-data-unitsystems-si-unitnames.html) module defines.</span></span>

- <span data-ttu-id="b3d47-331">Las unidades son todas simples (por ejemplo, metro) en lugar de compuestas (por ejemplo, metros por segundo).</span><span class="sxs-lookup"><span data-stu-id="b3d47-331">Units are all simple (for example, meter) rather than compound (for example, meter/second).</span></span>

- <span data-ttu-id="b3d47-332">Todas las columnas contienen datos en coma flotante.</span><span class="sxs-lookup"><span data-stu-id="b3d47-332">All columns contain floating point data.</span></span>

<span data-ttu-id="b3d47-333">Un proveedor más completo relajaría estas restricciones.</span><span class="sxs-lookup"><span data-stu-id="b3d47-333">A more complete provider would loosen these restrictions.</span></span>

<span data-ttu-id="b3d47-334">De nuevo, el primer paso es considerar qué aspecto debe tener la API.</span><span class="sxs-lookup"><span data-stu-id="b3d47-334">Again the first step is to consider how the API should look.</span></span> <span data-ttu-id="b3d47-335">Dado un archivo `info.csv` con el contenido de la tabla anterior (en formato separado por comas), los usuarios del proveedor deberían poder escribir un código similar al del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3d47-335">Given an `info.csv` file with the contents from the previous table (in comma-separated format), users of the provider should be able to write code that resembles the following example:</span></span>

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

<span data-ttu-id="b3d47-336">En este caso, el compilador debería convertir estas llamadas en algo similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3d47-336">In this case, the compiler should convert these calls into something like the following example:</span></span>

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

<span data-ttu-id="b3d47-337">La conversión óptima requerirá que el proveedor de tipos defina un tipo `CsvFile` real en el ensamblado del proveedor de tipos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-337">The optimal translation will require the type provider to define a real `CsvFile` type in the type provider's assembly.</span></span> <span data-ttu-id="b3d47-338">Los proveedores de tipos a veces se basan en algunos tipos y métodos del asistente para contener la lógica importante.</span><span class="sxs-lookup"><span data-stu-id="b3d47-338">Type providers often rely on a few helper types and methods to wrap important logic.</span></span> <span data-ttu-id="b3d47-339">Dado que las medidas se borran en tiempo de ejecución, se puede utilizar `float[]` como el tipo borrado para una fila.</span><span class="sxs-lookup"><span data-stu-id="b3d47-339">Because measures are erased at runtime, you can use a `float[]` as the erased type for a row.</span></span> <span data-ttu-id="b3d47-340">El compilador considerará que las distintas columnas contienen distintos tipos de medidas.</span><span class="sxs-lookup"><span data-stu-id="b3d47-340">The compiler will treat different columns as having different measure types.</span></span> <span data-ttu-id="b3d47-341">Por ejemplo, la primera columna de nuestro ejemplo contiene el tipo `float<meter>` y la segunda contiene `float<second>`.</span><span class="sxs-lookup"><span data-stu-id="b3d47-341">For example, the first column in our example has type `float<meter>`, and the second has `float<second>`.</span></span> <span data-ttu-id="b3d47-342">Sin embargo, la representación borrada puede seguir siendo bastante simple.</span><span class="sxs-lookup"><span data-stu-id="b3d47-342">However, the erased representation can remain quite simple.</span></span>

<span data-ttu-id="b3d47-343">En el ejemplo de código siguiente se muestra el núcleo de la implementación.</span><span class="sxs-lookup"><span data-stu-id="b3d47-343">The following code shows the core of the implementation.</span></span>

```fsharp
// Simple type wrapping CSV data
type CsvFile(filename) =
    // Cache the sequence of all data lines (all lines but the first)
    let data =
        seq {
            for line in File.ReadAllLines(filename) |> Seq.skip 1 ->
                line.Split(',') |> Array.map float
        }
        |> Seq.cache
    member _.Data = data

[<TypeProvider>]
type public MiniCsvProvider(cfg:TypeProviderConfig) as this =
    inherit TypeProviderForNamespaces(cfg)

    // Get the assembly and namespace used to house the provided types.
    let asm = System.Reflection.Assembly.GetExecutingAssembly()
    let ns = "Samples.FSharp.MiniCsvProvider"

    // Create the main provided type.
    let csvTy = ProvidedTypeDefinition(asm, ns, "MiniCsv", Some(typeof<obj>))

    // Parameterize the type by the file to use as a template.
    let filename = ProvidedStaticParameter("filename", typeof<string>)
    do csvTy.DefineStaticParameters([filename], fun tyName [| :? string as filename |] ->

        // Resolve the filename relative to the resolution folder.
        let resolvedFilename = Path.Combine(cfg.ResolutionFolder, filename)

        // Get the first line from the file.
        let headerLine = File.ReadLines(resolvedFilename) |> Seq.head

        // Define a provided type for each row, erasing to a float[].
        let rowTy = ProvidedTypeDefinition("Row", Some(typeof<float[]>))

        // Extract header names from the file, splitting on commas.
        // use Regex matching to get the position in the row at which the field occurs
        let headers = Regex.Matches(headerLine, "[^,]+")

        // Add one property per CSV field.
        for i in 0 .. headers.Count - 1 do
            let headerText = headers.[i].Value

            // Try to decompose this header into a name and unit.
            let fieldName, fieldTy =
                let m = Regex.Match(headerText, @"(?<field>.+) \((?<unit>.+)\)")
                if m.Success then

                    let unitName = m.Groups.["unit"].Value
                    let units = ProvidedMeasureBuilder.Default.SI unitName
                    m.Groups.["field"].Value, ProvidedMeasureBuilder.Default.AnnotateType(typeof<float>,[units])

                else
                    // no units, just treat it as a normal float
                    headerText, typeof<float>

            let prop =
                ProvidedProperty(fieldName, fieldTy,
                    getterCode = fun [row] -> <@@ (%%row:float[]).[i] @@>)

            // Add metadata that defines the property's location in the referenced file.
            prop.AddDefinitionLocation(1, headers.[i].Index + 1, filename)
            rowTy.AddMember(prop)

        // Define the provided type, erasing to CsvFile.
        let ty = ProvidedTypeDefinition(asm, ns, tyName, Some(typeof<CsvFile>))

        // Add a parameterless constructor that loads the file that was used to define the schema.
        let ctor0 =
            ProvidedConstructor([],
                invokeCode = fun [] -> <@@ CsvFile(resolvedFilename) @@>)
        ty.AddMember ctor0

        // Add a constructor that takes the file name to load.
        let ctor1 = ProvidedConstructor([ProvidedParameter("filename", typeof<string>)],
            invokeCode = fun [filename] -> <@@ CsvFile(%%filename) @@>)
        ty.AddMember ctor1

        // Add a more strongly typed Data property, which uses the existing property at runtime.
        let prop =
            ProvidedProperty("Data", typedefof<seq<_>>.MakeGenericType(rowTy),
                getterCode = fun [csvFile] -> <@@ (%%csvFile:CsvFile).Data @@>)
        ty.AddMember prop

        // Add the row type as a nested type.
        ty.AddMember rowTy
        ty)

    // Add the type to the namespace.
    do this.AddNamespace(ns, [csvTy])
```

<span data-ttu-id="b3d47-344">Tenga en cuenta las siguientes observaciones sobre la implementación:</span><span class="sxs-lookup"><span data-stu-id="b3d47-344">Note the following points about the implementation:</span></span>

- <span data-ttu-id="b3d47-345">Los constructores sobrecargados permiten leer el archivo original o uno que tenga un esquema idéntico.</span><span class="sxs-lookup"><span data-stu-id="b3d47-345">Overloaded constructors allow either the original file or one that has an identical schema to be read.</span></span> <span data-ttu-id="b3d47-346">Este patrón es habitual al escribir un proveedor de tipo para orígenes de datos locales o remotos, y además permite el uso de un archivo local como plantilla para los datos remotos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-346">This pattern is common when you write a type provider for local or remote data sources, and this pattern allows a local file to be used as the template for remote data.</span></span>

- <span data-ttu-id="b3d47-347">Puede utilizar el valor [TypeProviderConfig](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-compilerservices-typeproviderconfig.html) que se pasa al constructor del proveedor de tipos para resolver nombres de archivo relativos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-347">You can use the [TypeProviderConfig](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-compilerservices-typeproviderconfig.html) value that’s passed in to the type provider constructor to resolve relative file names.</span></span>

- <span data-ttu-id="b3d47-348">Se puede utilizar el método `AddDefinitionLocation` para definir la ubicación de las propiedades proporcionadas.</span><span class="sxs-lookup"><span data-stu-id="b3d47-348">You can use the `AddDefinitionLocation` method to define the location of the provided properties.</span></span> <span data-ttu-id="b3d47-349">Por lo tanto, si usa `Go To Definition` en una propiedad proporcionada, el archivo CSV se abrirá en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b3d47-349">Therefore, if you use `Go To Definition` on a provided property, the CSV file will open in Visual Studio.</span></span>

- <span data-ttu-id="b3d47-350">Se puede utilizar el tipo `ProvidedMeasureBuilder` para buscar las unidades del SI y generar los tipos `float<_>` pertinentes.</span><span class="sxs-lookup"><span data-stu-id="b3d47-350">You can use the `ProvidedMeasureBuilder` type to look up the SI units and to generate the relevant `float<_>` types.</span></span>

### <a name="key-lessons"></a><span data-ttu-id="b3d47-351">Lecciones principales</span><span class="sxs-lookup"><span data-stu-id="b3d47-351">Key Lessons</span></span>

<span data-ttu-id="b3d47-352">En esta sección se ha explicado cómo crear un proveedor de tipo para un origen de datos local con un esquema simple que está contenido en el propio origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-352">This section explained how to create a type provider for a local data source with a simple schema that's contained in the data source itself.</span></span>

## <a name="going-further"></a><span data-ttu-id="b3d47-353">Ampliar conocimientos</span><span class="sxs-lookup"><span data-stu-id="b3d47-353">Going Further</span></span>

<span data-ttu-id="b3d47-354">En las secciones siguientes se incluyen sugerencias para ampliar conocimientos sobre el tema.</span><span class="sxs-lookup"><span data-stu-id="b3d47-354">The following sections include suggestions for further study.</span></span>

### <a name="a-look-at-the-compiled-code-for-erased-types"></a><span data-ttu-id="b3d47-355">Un vistazo al código compilado de los tipos borrados</span><span class="sxs-lookup"><span data-stu-id="b3d47-355">A Look at the Compiled Code for Erased Types</span></span>

<span data-ttu-id="b3d47-356">Para tener una idea de cómo se corresponde el uso del proveedor de tipos con el código emitido, revise la función siguiente mediante el proveedor `HelloWorldTypeProvider` utilizado anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="b3d47-356">To give you some idea of how the use of the type provider corresponds to the code that's emitted, look at the following function by using the `HelloWorldTypeProvider` that's used earlier in this topic.</span></span>

```fsharp
let function1 () =
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

<span data-ttu-id="b3d47-357">A continuación se muestra una imagen del código resultante descompilado mediante ildasm.exe:</span><span class="sxs-lookup"><span data-stu-id="b3d47-357">Here’s an image of the resulting code decompiled by using ildasm.exe:</span></span>

```il
.class public abstract auto ansi sealed Module1
extends [mscorlib]System.Object
{
.custom instance void [FSharp.Core]Microsoft.FSharp.Core.CompilationMappingAtt
ribute::.ctor(valuetype [FSharp.Core]Microsoft.FSharp.Core.SourceConstructFlags)
= ( 01 00 07 00 00 00 00 00 )
.method public static int32  function1() cil managed
{
// Code size       24 (0x18)
.maxstack  3
.locals init ([0] object obj1)
IL_0000:  nop
IL_0001:  ldstr      "some data"
IL_0006:  unbox.any  [mscorlib]System.Object
IL_000b:  stloc.0
IL_000c:  ldloc.0
IL_000d:  call       !!0 [FSharp.Core_2]Microsoft.FSharp.Core.LanguagePrimit
ives/IntrinsicFunctions::UnboxGeneric<string>(object)
IL_0012:  callvirt   instance int32 [mscorlib_3]System.String::get_Length()
IL_0017:  ret
} // end of method Module1::function1

} // end of class Module1
```

<span data-ttu-id="b3d47-358">Como muestra el ejemplo, se han borrado todas las menciones del tipo `Type1` y la propiedad `InstanceProperty`, y quedan solo las operaciones para los tipos de tiempo de ejecución relacionados.</span><span class="sxs-lookup"><span data-stu-id="b3d47-358">As the example shows, all mentions of the type `Type1` and the `InstanceProperty` property have been erased, leaving only operations on the runtime types involved.</span></span>

### <a name="design-and-naming-conventions-for-type-providers"></a><span data-ttu-id="b3d47-359">Diseño y convenciones de nomenclatura para los proveedores de tipos</span><span class="sxs-lookup"><span data-stu-id="b3d47-359">Design and Naming Conventions for Type Providers</span></span>

<span data-ttu-id="b3d47-360">Respete las convenciones siguientes al crear proveedores de tipos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-360">Observe the following conventions when authoring type providers.</span></span>

<span data-ttu-id="b3d47-361">**Proveedores de protocolos de conectividad** En general, los nombres de la mayoría de los archivos dll de proveedor para los protocolos de datos y conectividad de servicio, como las conexiones de OData o SQL, deben acabar en `TypeProvider` o `TypeProviders` .</span><span class="sxs-lookup"><span data-stu-id="b3d47-361">**Providers for Connectivity Protocols** In general, names of most provider DLLs for data and service connectivity protocols, such as OData or SQL connections, should end in `TypeProvider` or `TypeProviders`.</span></span> <span data-ttu-id="b3d47-362">Por ejemplo, utilice un nombre de DLL similar a la siguiente cadena:</span><span class="sxs-lookup"><span data-stu-id="b3d47-362">For example, use a DLL name that resembles the following string:</span></span>

`Fabrikam.Management.BasicTypeProviders.dll`

<span data-ttu-id="b3d47-363">Asegúrese de que los tipos proporcionados son miembros del espacio de nombres correspondiente e indican el protocolo de conexión que se ha implementado:</span><span class="sxs-lookup"><span data-stu-id="b3d47-363">Ensure that your provided types are members of the corresponding namespace, and indicate the connectivity protocol that you implemented:</span></span>

```fsharp
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

<span data-ttu-id="b3d47-364">**Proveedores de utilidades para la codificación general**.</span><span class="sxs-lookup"><span data-stu-id="b3d47-364">**Utility Providers for General Coding**.</span></span>  <span data-ttu-id="b3d47-365">Para un proveedor de tipos de utilidad, como el de las expresiones regulares, el proveedor de tipos puede ser parte de una biblioteca base, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3d47-365">For a utility type provider such as that for regular expressions, the type provider may be part of a base library, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Core.Text.Utilities.dll"
```

<span data-ttu-id="b3d47-366">En este caso, el tipo proporcionado aparecería en un punto adecuado según las convenciones normales de diseño de .NET:</span><span class="sxs-lookup"><span data-stu-id="b3d47-366">In this case, the provided type would appear at an appropriate point according to normal .NET design conventions:</span></span>

```fsharp
  open Fabrikam.Core.Text.RegexTyped

  let regex = new RegexTyped<"a+b+a+b+">()
```

<span data-ttu-id="b3d47-367">**Orígenes de datos singleton**.</span><span class="sxs-lookup"><span data-stu-id="b3d47-367">**Singleton Data Sources**.</span></span> <span data-ttu-id="b3d47-368">Algunos proveedores de tipos se conectan a un único origen de datos dedicado y solo proporcionan datos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-368">Some type providers connect to a single dedicated data source and provide only data.</span></span> <span data-ttu-id="b3d47-369">En este caso, se debería colocar el sufijo `TypeProvider` y utilizar las convenciones normales de nomenclatura de .NET:</span><span class="sxs-lookup"><span data-stu-id="b3d47-369">In this case, you should drop the `TypeProvider` suffix and use normal conventions for .NET naming:</span></span>

```fsharp
#r "Fabrikam.Data.Freebase.dll"

let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

<span data-ttu-id="b3d47-370">Para obtener más información, vea la convención de diseño `GetConnection` que se describe más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="b3d47-370">For more information, see the `GetConnection` design convention that's described later in this topic.</span></span>

### <a name="design-patterns-for-type-providers"></a><span data-ttu-id="b3d47-371">Patrones de diseño para los proveedores de tipos</span><span class="sxs-lookup"><span data-stu-id="b3d47-371">Design Patterns for Type Providers</span></span>

<span data-ttu-id="b3d47-372">En las secciones siguientes se describen los patrones de diseño que se pueden usar cuando se crean los proveedores de tipos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-372">The following sections describe design patterns you can use when authoring type providers.</span></span>

#### <a name="the-getconnection-design-pattern"></a><span data-ttu-id="b3d47-373">El patrón de diseño GetConnection</span><span class="sxs-lookup"><span data-stu-id="b3d47-373">The GetConnection Design Pattern</span></span>

<span data-ttu-id="b3d47-374">La mayoría de los proveedores de tipos se deben escribir para que usen el patrón `GetConnection` utilizado por los proveedores de tipo en FSharp.Data.TypeProviders.dll, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3d47-374">Most type providers should be written to use the `GetConnection` pattern that's used by the type providers in FSharp.Data.TypeProviders.dll, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a><span data-ttu-id="b3d47-375">Proveedores de tipos respaldados por datos y servicios remotos</span><span class="sxs-lookup"><span data-stu-id="b3d47-375">Type Providers Backed By Remote Data and Services</span></span>

<span data-ttu-id="b3d47-376">Antes de crear un proveedor de tipos respaldado por datos y servicios remotos, se deben tener en cuenta varios problemas que son inherentes a la programación conectada.</span><span class="sxs-lookup"><span data-stu-id="b3d47-376">Before you create a type provider that's backed by remote data and services, you must consider a range of issues that are inherent in connected programming.</span></span> <span data-ttu-id="b3d47-377">Estos problemas incluyen los siguientes aspectos:</span><span class="sxs-lookup"><span data-stu-id="b3d47-377">These issues include the following considerations:</span></span>

- <span data-ttu-id="b3d47-378">Asignación de esquemas</span><span class="sxs-lookup"><span data-stu-id="b3d47-378">schema mapping</span></span>

- <span data-ttu-id="b3d47-379">Vida e invalidación en presencia de un cambio de esquema</span><span class="sxs-lookup"><span data-stu-id="b3d47-379">liveness and invalidation in the presence of schema change</span></span>

- <span data-ttu-id="b3d47-380">Almacenamiento en caché de esquemas</span><span class="sxs-lookup"><span data-stu-id="b3d47-380">schema caching</span></span>

- <span data-ttu-id="b3d47-381">Implementaciones asíncronas de operaciones de acceso a datos</span><span class="sxs-lookup"><span data-stu-id="b3d47-381">asynchronous implementations of data access operations</span></span>

- <span data-ttu-id="b3d47-382">Consultas admitidas, incluidas las consultas LINQ</span><span class="sxs-lookup"><span data-stu-id="b3d47-382">supporting queries, including LINQ queries</span></span>

- <span data-ttu-id="b3d47-383">Credenciales y autenticación</span><span class="sxs-lookup"><span data-stu-id="b3d47-383">credentials and authentication</span></span>

<span data-ttu-id="b3d47-384">Este tema no profundiza en estos problemas.</span><span class="sxs-lookup"><span data-stu-id="b3d47-384">This topic doesn't explore these issues further.</span></span>

### <a name="additional-authoring-techniques"></a><span data-ttu-id="b3d47-385">Técnicas adicionales de creación</span><span class="sxs-lookup"><span data-stu-id="b3d47-385">Additional Authoring Techniques</span></span>

<span data-ttu-id="b3d47-386">Al escribir sus propios proveedores de tipos, quizá quiera utilizar las siguientes técnicas adicionales.</span><span class="sxs-lookup"><span data-stu-id="b3d47-386">When you write your own type providers, you might want to use the following additional techniques.</span></span>

### <a name="creating-types-and-members-on-demand"></a><span data-ttu-id="b3d47-387">Crear tipos y miembros bajo demanda</span><span class="sxs-lookup"><span data-stu-id="b3d47-387">Creating Types and Members On-Demand</span></span>

<span data-ttu-id="b3d47-388">La API de ProvidedType tiene versiones demoradas de AddMember.</span><span class="sxs-lookup"><span data-stu-id="b3d47-388">The ProvidedType API has delayed versions of AddMember.</span></span>

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

<span data-ttu-id="b3d47-389">Estas versiones se utilizan para crear espacios de tipos a petición.</span><span class="sxs-lookup"><span data-stu-id="b3d47-389">These versions are used to create on-demand spaces of types.</span></span>

### <a name="providing-array-types-and-generic-type-instantiations"></a><span data-ttu-id="b3d47-390">Proporcionar tipos de matriz y crear instancias de tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="b3d47-390">Providing Array types and Generic Type Instantiations</span></span>

<span data-ttu-id="b3d47-391">Los miembros proporcionados (cuyas firmas incluyen tipos de matriz, tipos de ByRef y creaciones de instancias de tipos genéricos) usan el normal `MakeArrayType` , `MakePointerType` y `MakeGenericType` en cualquier instancia de <xref:System.Type> , incluido `ProvidedTypeDefinitions` .</span><span class="sxs-lookup"><span data-stu-id="b3d47-391">You make provided members (whose signatures include array types, byref types, and instantiations of generic types) by using the normal `MakeArrayType`, `MakePointerType`, and `MakeGenericType` on any instance of <xref:System.Type>, including `ProvidedTypeDefinitions`.</span></span>

> [!NOTE]
> <span data-ttu-id="b3d47-392">En algunos casos, es posible que tenga que usar el ayudante en `ProvidedTypeBuilder.MakeGenericType` .</span><span class="sxs-lookup"><span data-stu-id="b3d47-392">In some cases you may have to use the helper in `ProvidedTypeBuilder.MakeGenericType`.</span></span>  <span data-ttu-id="b3d47-393">Consulte la [documentación del SDK del proveedor de tipos](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="b3d47-393">See the [Type Provider SDK documentation](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) for more details.</span></span>

### <a name="providing-unit-of-measure-annotations"></a><span data-ttu-id="b3d47-394">Proporcionar anotaciones de unidades de medida</span><span class="sxs-lookup"><span data-stu-id="b3d47-394">Providing Unit of Measure Annotations</span></span>

<span data-ttu-id="b3d47-395">La API ProvidedTypes proporciona asistentes para proporcionar anotaciones de medidas.</span><span class="sxs-lookup"><span data-stu-id="b3d47-395">The ProvidedTypes API provides helpers for providing measure annotations.</span></span> <span data-ttu-id="b3d47-396">Por ejemplo, para proporcionar el tipo `float<kg>`, utilice el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3d47-396">For example, to provide the type `float<kg>`, use the following code:</span></span>

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  <span data-ttu-id="b3d47-397">Para proporcionar el tipo `Nullable<decimal<kg/m^2>>`, utilice el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3d47-397">To provide the type `Nullable<decimal<kg/m^2>>`, use the following code:</span></span>

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a><span data-ttu-id="b3d47-398">Acceder a recursos locales del proyecto o del script</span><span class="sxs-lookup"><span data-stu-id="b3d47-398">Accessing Project-Local or Script-Local Resources</span></span>

<span data-ttu-id="b3d47-399">A cada instancia de un proveedor de tipo se le puede asignar un valor `TypeProviderConfig` durante la construcción.</span><span class="sxs-lookup"><span data-stu-id="b3d47-399">Each instance of a type provider can be given a `TypeProviderConfig` value during construction.</span></span> <span data-ttu-id="b3d47-400">Este valor contiene la "carpeta de resolución" para el proveedor (es decir, la carpeta del proyecto para la compilación o el directorio que contiene un script), la lista de ensamblados a los que se hace referencia y otra información.</span><span class="sxs-lookup"><span data-stu-id="b3d47-400">This value contains the "resolution folder" for the provider (that is, the project folder for the compilation or the directory that contains a script), the list of referenced assemblies, and other information.</span></span>

### <a name="invalidation"></a><span data-ttu-id="b3d47-401">Invalidación</span><span class="sxs-lookup"><span data-stu-id="b3d47-401">Invalidation</span></span>

<span data-ttu-id="b3d47-402">Los proveedores pueden generar señales de invalidación para notificar al servicio del lenguaje F# que las suposiciones acerca del esquema pueden haber cambiado.</span><span class="sxs-lookup"><span data-stu-id="b3d47-402">Providers can raise invalidation signals to notify the F# language service that the schema assumptions may have changed.</span></span> <span data-ttu-id="b3d47-403">Cuando se produce la invalidación, se repite una comprobación de tipos si el proveedor se hospeda en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b3d47-403">When invalidation occurs, a typecheck is redone if the provider is being hosted in Visual Studio.</span></span> <span data-ttu-id="b3d47-404">Esta señal se omite cuando el proveedor se hospeda en F# Interactive o por el compilador de F# (fsc.exe).</span><span class="sxs-lookup"><span data-stu-id="b3d47-404">This signal will be ignored when the provider is hosted in F# Interactive or by the F# Compiler (fsc.exe).</span></span>

### <a name="caching-schema-information"></a><span data-ttu-id="b3d47-405">Almacenar en caché la información del esquema</span><span class="sxs-lookup"><span data-stu-id="b3d47-405">Caching Schema Information</span></span>

<span data-ttu-id="b3d47-406">A menudo los proveedores deben almacenar en memoria caché el acceso a la información del esquema.</span><span class="sxs-lookup"><span data-stu-id="b3d47-406">Providers must often cache access to schema information.</span></span> <span data-ttu-id="b3d47-407">Los datos almacenados en caché deben almacenarse utilizando un nombre de archivo que se da como parámetro estático o como datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="b3d47-407">The cached data should be stored by using a file name that's given as a static parameter or as user data.</span></span> <span data-ttu-id="b3d47-408">Un ejemplo de almacenamiento en caché de esquema es el parámetro `LocalSchemaFile` en los proveedores de tipos del ensamblado `FSharp.Data.TypeProviders`.</span><span class="sxs-lookup"><span data-stu-id="b3d47-408">An example of schema caching is the `LocalSchemaFile` parameter in the type providers in the `FSharp.Data.TypeProviders` assembly.</span></span> <span data-ttu-id="b3d47-409">En la implementación de estos proveedores, este parámetro estático ordena al proveedor de tipos que use la información del esquema del archivo local especificado en lugar de acceder al origen de datos en la red.</span><span class="sxs-lookup"><span data-stu-id="b3d47-409">In the implementation of these providers, this static parameter directs the type provider to use the schema information in the specified local file instead of accessing the data source over the network.</span></span> <span data-ttu-id="b3d47-410">Para utilizar la información del esquema almacenada en caché, también se debe establecer el parámetro estático `ForceUpdate` en `false`.</span><span class="sxs-lookup"><span data-stu-id="b3d47-410">To use cached schema information, you must also set the static parameter `ForceUpdate` to `false`.</span></span> <span data-ttu-id="b3d47-411">Se puede usar una técnica similar para permitir el acceso a datos en línea y sin conexión.</span><span class="sxs-lookup"><span data-stu-id="b3d47-411">You could use a similar technique to enable online and offline data access.</span></span>

### <a name="backing-assembly"></a><span data-ttu-id="b3d47-412">Ensamblado de respaldo</span><span class="sxs-lookup"><span data-stu-id="b3d47-412">Backing Assembly</span></span>

<span data-ttu-id="b3d47-413">Al compilar `.dll` un `.exe` archivo o, el archivo. dll de respaldo para los tipos generados se vincula estáticamente en el ensamblado resultante.</span><span class="sxs-lookup"><span data-stu-id="b3d47-413">When you compile a `.dll` or `.exe` file, the backing .dll file for generated types is statically linked into the resulting assembly.</span></span> <span data-ttu-id="b3d47-414">Este vínculo se crea copiando las definiciones de tipos del lenguaje intermedio (IL) y cualquier recurso administrado del ensamblado de respaldo al ensamblado final.</span><span class="sxs-lookup"><span data-stu-id="b3d47-414">This link is created by copying the Intermediate Language (IL) type definitions and any managed resources from the backing assembly into the final assembly.</span></span> <span data-ttu-id="b3d47-415">Cuando se usa F# Interactive, el archivo .dll de respaldo no se copia, sino que se carga directamente en el proceso de F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="b3d47-415">When you use F# Interactive, the backing .dll file isn't copied and is instead loaded directly into the F# Interactive process.</span></span>

### <a name="exceptions-and-diagnostics-from-type-providers"></a><span data-ttu-id="b3d47-416">Excepciones y diagnósticos de proveedores de tipo</span><span class="sxs-lookup"><span data-stu-id="b3d47-416">Exceptions and Diagnostics from Type Providers</span></span>

<span data-ttu-id="b3d47-417">Todos los usos de todos los miembros de los tipos proporcionados pueden producir excepciones.</span><span class="sxs-lookup"><span data-stu-id="b3d47-417">All uses of all members from provided types may throw exceptions.</span></span> <span data-ttu-id="b3d47-418">En todos los casos, si un proveedor de tipos genera una excepción, el compilador host atribuye el error a un proveedor de tipos específico.</span><span class="sxs-lookup"><span data-stu-id="b3d47-418">In all cases, if a type provider throws an exception, the host compiler attributes the error to a specific type provider.</span></span>

- <span data-ttu-id="b3d47-419">Las excepciones de proveedores de tipos nunca deben producir errores internos del compilador.</span><span class="sxs-lookup"><span data-stu-id="b3d47-419">Type provider exceptions should never result in internal compiler errors.</span></span>

- <span data-ttu-id="b3d47-420">Los proveedores de tipo no pueden notificar advertencias.</span><span class="sxs-lookup"><span data-stu-id="b3d47-420">Type providers can't report warnings.</span></span>

- <span data-ttu-id="b3d47-421">Cuando un proveedor de tipo se hospeda en el compilador de F#, un entorno de desarrollo de F# o F# Interactive, se detectan todas las excepciones de ese proveedor.</span><span class="sxs-lookup"><span data-stu-id="b3d47-421">When a type provider is hosted in the F# compiler, an F# development environment, or F# Interactive, all exceptions from that provider are caught.</span></span> <span data-ttu-id="b3d47-422">La propiedad Message es siempre el texto del error y no aparece ningún seguimiento de pila.</span><span class="sxs-lookup"><span data-stu-id="b3d47-422">The Message property is always the error text, and no stack trace appears.</span></span> <span data-ttu-id="b3d47-423">Si va a iniciar una excepción, puede iniciar los ejemplos siguientes: `System.NotSupportedException` , `System.IO.IOException` , `System.Exception` .</span><span class="sxs-lookup"><span data-stu-id="b3d47-423">If you’re going to throw an exception, you can throw the following examples: `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`.</span></span>

#### <a name="providing-generated-types"></a><span data-ttu-id="b3d47-424">Proporcionar tipos generados</span><span class="sxs-lookup"><span data-stu-id="b3d47-424">Providing Generated Types</span></span>

<span data-ttu-id="b3d47-425">Hasta ahora, en este documento se ha explicado cómo proporcionar tipos borrados.</span><span class="sxs-lookup"><span data-stu-id="b3d47-425">So far, this document has explained how to provide erased types.</span></span> <span data-ttu-id="b3d47-426">También se puede usar el mecanismo de proveedores de tipo de F# para proporcionar tipos generados, que se agregan como definiciones de tipo reales de .NET en el programa del usuario.</span><span class="sxs-lookup"><span data-stu-id="b3d47-426">You can also use the type provider mechanism in F# to provide generated types, which are added as real .NET type definitions into the users' program.</span></span> <span data-ttu-id="b3d47-427">Se debe hacer referencia a los tipos proporcionados generados mediante una definición de tipo.</span><span class="sxs-lookup"><span data-stu-id="b3d47-427">You must refer to generated provided types by using a type definition.</span></span>

```fsharp
open Microsoft.FSharp.TypeProviders

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

<span data-ttu-id="b3d47-428">El código del asistente ProvidedTypes-0.2 que forma parte de la versión 3.0 de F# solo tiene compatibilidad limitada para proporcionar tipos generados.</span><span class="sxs-lookup"><span data-stu-id="b3d47-428">The ProvidedTypes-0.2 helper code that is part of the F# 3.0 release has only limited support for providing generated types.</span></span> <span data-ttu-id="b3d47-429">Los enunciados siguientes deben ser verdaderos para una definición de un tipo generado:</span><span class="sxs-lookup"><span data-stu-id="b3d47-429">The following statements must be true for a generated type definition:</span></span>

- <span data-ttu-id="b3d47-430">`isErased` se debe establecer en `false`.</span><span class="sxs-lookup"><span data-stu-id="b3d47-430">`isErased` must be set to `false`.</span></span>

- <span data-ttu-id="b3d47-431">El tipo generado se debe agregar a un recién construido `ProvidedAssembly()` , que representa un contenedor para fragmentos de código generados.</span><span class="sxs-lookup"><span data-stu-id="b3d47-431">The generated type must be added to a newly constructed `ProvidedAssembly()`, which represents a container for generated code fragments.</span></span>

- <span data-ttu-id="b3d47-432">El proveedor debe tener un ensamblado que tenga un archivo .dll de respaldo real de .NET con un archivo .dll coincidente en el disco.</span><span class="sxs-lookup"><span data-stu-id="b3d47-432">The provider must have an assembly that has an actual backing .NET .dll file with a matching .dll file on disk.</span></span>

## <a name="rules-and-limitations"></a><span data-ttu-id="b3d47-433">Reglas y limitaciones</span><span class="sxs-lookup"><span data-stu-id="b3d47-433">Rules and Limitations</span></span>

<span data-ttu-id="b3d47-434">Al escribir proveedores de tipos, tenga en cuenta las siguientes reglas y limitaciones.</span><span class="sxs-lookup"><span data-stu-id="b3d47-434">When you write type providers, keep the following rules and limitations in mind.</span></span>

### <a name="provided-types-must-be-reachable"></a><span data-ttu-id="b3d47-435">Los tipos proporcionados deben ser accesibles</span><span class="sxs-lookup"><span data-stu-id="b3d47-435">Provided types must be reachable</span></span>

<span data-ttu-id="b3d47-436">Debe tenerse acceso a todos los tipos proporcionados desde los tipos no anidados.</span><span class="sxs-lookup"><span data-stu-id="b3d47-436">All provided types should be reachable from the non-nested types.</span></span> <span data-ttu-id="b3d47-437">Los tipos no anidados se proporcionan en la llamada al constructor `TypeProviderForNamespaces` o en una llamada a `AddNamespace`.</span><span class="sxs-lookup"><span data-stu-id="b3d47-437">The non-nested types are given in the call to the `TypeProviderForNamespaces` constructor or a call to `AddNamespace`.</span></span> <span data-ttu-id="b3d47-438">Por ejemplo, si el proveedor proporciona un tipo `StaticClass.P : T`, debe asegurarse de que T es un tipo no anidado o está anidado debajo de uno.</span><span class="sxs-lookup"><span data-stu-id="b3d47-438">For example, if the provider provides a type `StaticClass.P : T`, you must ensure that T is either a non-nested type or nested under one.</span></span>

<span data-ttu-id="b3d47-439">Por ejemplo, algunos proveedores tienen una clase estática como `DataTypes` que contiene estos tipos `T1, T2, T3, ...`.</span><span class="sxs-lookup"><span data-stu-id="b3d47-439">For example, some providers have a static class such as `DataTypes` that contain these `T1, T2, T3, ...` types.</span></span> <span data-ttu-id="b3d47-440">De lo contrario, el error indica que se ha encontrado una referencia al tipo T en el ensamblado A, pero el tipo no se encuentra en ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b3d47-440">Otherwise, the error says that a reference to type T in assembly A was found, but the type couldn't be found in that assembly.</span></span> <span data-ttu-id="b3d47-441">Si aparece este error, compruebe que se puede obtener acceso a todos los subtipos desde los tipos del proveedor.</span><span class="sxs-lookup"><span data-stu-id="b3d47-441">If this error appears, verify that all your subtypes can be reached from the provider types.</span></span> <span data-ttu-id="b3d47-442">Nota: estos `T1, T2, T3...` tipos se conocen como tipos *sobre la marcha* .</span><span class="sxs-lookup"><span data-stu-id="b3d47-442">Note: These `T1, T2, T3...` types are referred to as the *on-the-fly* types.</span></span> <span data-ttu-id="b3d47-443">Recuerde colocarlos en un espacio de nombres accesible o en un tipo primario.</span><span class="sxs-lookup"><span data-stu-id="b3d47-443">Remember to put them in an accessible namespace or a parent type.</span></span>

### <a name="limitations-of-the-type-provider-mechanism"></a><span data-ttu-id="b3d47-444">Limitaciones del mecanismo de proveedores de tipos</span><span class="sxs-lookup"><span data-stu-id="b3d47-444">Limitations of the Type Provider Mechanism</span></span>

<span data-ttu-id="b3d47-445">El mecanismo de proveedores de tipos de F# tiene las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="b3d47-445">The type provider mechanism in F# has the following limitations:</span></span>

- <span data-ttu-id="b3d47-446">La infraestructura subyacente para los proveedores de tipos de F# no admite tipos genéricos proporcionados ni métodos genéricos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="b3d47-446">The underlying infrastructure for type providers in F# doesn't support provided generic types or provided generic methods.</span></span>

- <span data-ttu-id="b3d47-447">El mecanismo no admite tipos anidados con parámetros estáticos.</span><span class="sxs-lookup"><span data-stu-id="b3d47-447">The mechanism doesn't support nested types with static parameters.</span></span>

## <a name="development-tips"></a><span data-ttu-id="b3d47-448">Sugerencias de desarrollo</span><span class="sxs-lookup"><span data-stu-id="b3d47-448">Development Tips</span></span>

<span data-ttu-id="b3d47-449">Puede que le resulten útiles las siguientes sugerencias durante el proceso de desarrollo:</span><span class="sxs-lookup"><span data-stu-id="b3d47-449">You might find the following tips helpful during the development process:</span></span>

### <a name="run-two-instances-of-visual-studio"></a><span data-ttu-id="b3d47-450">Ejecutar dos instancias de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b3d47-450">Run two instances of Visual Studio</span></span>

<span data-ttu-id="b3d47-451">Puede desarrollar el proveedor de tipo en una instancia y probarlo en la otra porque el IDE de prueba tomará un bloqueo en el archivo .dll que evita que se recompile el proveedor de tipo.</span><span class="sxs-lookup"><span data-stu-id="b3d47-451">You can develop the type provider in one instance and test the provider in the other because the test IDE will take a lock on the .dll file that prevents the type provider from being rebuilt.</span></span> <span data-ttu-id="b3d47-452">Por lo tanto, debe cerrar la segunda instancia de Visual Studio mientras se compila el proveedor en la primera y, a continuación, debe volver a abrir la segunda instancia después de compilar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="b3d47-452">Thus, you must close the second instance of Visual Studio while the provider is built in the first instance, and then you must reopen the second instance after the provider is built.</span></span>

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a><span data-ttu-id="b3d47-453">Depurar proveedores de tipos mediante invocaciones de fsc.exe</span><span class="sxs-lookup"><span data-stu-id="b3d47-453">Debug type providers by using invocations of fsc.exe</span></span>

<span data-ttu-id="b3d47-454">Puede invocar proveedores de tipo mediante las herramientas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b3d47-454">You can invoke type providers by using the following tools:</span></span>

- <span data-ttu-id="b3d47-455">fsc.exe (el compilador de línea de comandos de F#)</span><span class="sxs-lookup"><span data-stu-id="b3d47-455">fsc.exe (The F# command line compiler)</span></span>

- <span data-ttu-id="b3d47-456">fsi.exe (el compilador interactivo de F#)</span><span class="sxs-lookup"><span data-stu-id="b3d47-456">fsi.exe (The F# Interactive compiler)</span></span>

- <span data-ttu-id="b3d47-457">devenv.exe (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="b3d47-457">devenv.exe (Visual Studio)</span></span>

<span data-ttu-id="b3d47-458">A menudo, lo más fácil es depurar los proveedores de tipo mediante fsc.exe en un archivo de script de prueba (por ejemplo, script.fsx).</span><span class="sxs-lookup"><span data-stu-id="b3d47-458">You can often debug type providers most easily by using fsc.exe on a test script file (for example, script.fsx).</span></span> <span data-ttu-id="b3d47-459">Puede iniciar un depurador desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="b3d47-459">You can launch a debugger from a command prompt.</span></span>

```console
devenv /debugexe fsc.exe script.fsx
```

  <span data-ttu-id="b3d47-460">Puede usar print-to-stdout como registro.</span><span class="sxs-lookup"><span data-stu-id="b3d47-460">You can use print-to-stdout logging.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3d47-461">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b3d47-461">See also</span></span>

- [<span data-ttu-id="b3d47-462">Proveedores de tipos</span><span class="sxs-lookup"><span data-stu-id="b3d47-462">Type Providers</span></span>](index.md)
- [<span data-ttu-id="b3d47-463">SDK del proveedor de tipos</span><span class="sxs-lookup"><span data-stu-id="b3d47-463">The Type Provider SDK</span></span>](https://github.com/fsprojects/FSharp.TypeProviders.SDK)
