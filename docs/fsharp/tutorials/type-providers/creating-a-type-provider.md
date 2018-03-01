---
title: 'Tutorial: Crear un proveedor de tipos (F#)'
description: "Obtenga información acerca de cómo crear sus propios proveedores de tipo de F # en F # 3.0 mediante el examen de varios proveedores de tipo simples para ilustrar los conceptos básicos."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 82bec076-19d4-470c-979f-6c3a14b7c70a
ms.openlocfilehash: c09f8abe4dd46453cb6cc5ed7dbb6f60dbf0ad98
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="tutorial-creating-a-type-provider"></a><span data-ttu-id="11f10-104">Tutorial: Crear un proveedor de tipos</span><span class="sxs-lookup"><span data-stu-id="11f10-104">Tutorial: Creating a Type Provider</span></span>

> [!NOTE]
<span data-ttu-id="11f10-105">Esta guía se escribió para F # 3.0 y se actualizará.</span><span class="sxs-lookup"><span data-stu-id="11f10-105">This guide was written for F# 3.0 and will be updated.</span></span>

<span data-ttu-id="11f10-106">La programación con amplio acceso a diferentes fuentes de información de F# 3.0 tiene uno de sus pilares más importantes en el mecanismo de proveedores de tipos de este.</span><span class="sxs-lookup"><span data-stu-id="11f10-106">The type provider mechanism in F# 3.0 is a significant part of its support for information rich programming.</span></span> <span data-ttu-id="11f10-107">Este tutorial le explica cómo crear proveedores de tipos, a la vez que le guía en el desarrollo de varios proveedores de tipo simples para ilustrar los conceptos básicos.</span><span class="sxs-lookup"><span data-stu-id="11f10-107">This tutorial explains how to create your own type providers by walking you through the development of several simple type providers to illustrate the basic concepts.</span></span> <span data-ttu-id="11f10-108">Para obtener más información sobre el mecanismo de proveedores de tipo de F #, vea [proveedores de tipo](index.md).</span><span class="sxs-lookup"><span data-stu-id="11f10-108">For more information about the type provider mechanism in F#, see [Type Providers](index.md).</span></span>

<span data-ttu-id="11f10-109">F# 3.0 contiene varios proveedores de tipos integrados que se utilizan habitualmente para servicios de datos empresariales y de Internet.</span><span class="sxs-lookup"><span data-stu-id="11f10-109">F# 3.0 contains several built-in type providers for commonly used Internet and enterprise data services.</span></span> <span data-ttu-id="11f10-110">Estos proveedores de tipos proporcionan acceso simple y regular a bases de datos relacionales SQL y servicios OData y WSDL basados en redes.</span><span class="sxs-lookup"><span data-stu-id="11f10-110">These type providers give simple and regular access to SQL relational databases and network-based OData and WSDL services.</span></span> <span data-ttu-id="11f10-111">Estos proveedores también admiten el uso de consultas LINQ de F# con estos orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="11f10-111">These providers also support the use of F# LINQ queries against these data sources.</span></span>

<span data-ttu-id="11f10-112">En caso necesario, se pueden crear proveedores de tipo personalizados o se puede hacer referencia a proveedores de tipo creados por otros.</span><span class="sxs-lookup"><span data-stu-id="11f10-112">Where necessary, you can create custom type providers, or you can reference type providers that others have created.</span></span> <span data-ttu-id="11f10-113">Por ejemplo, una organización podría tener un servicio de datos que proporcionara un número elevado y creciente de conjuntos de datos con nombre, cada uno con su propio esquema de datos estable.</span><span class="sxs-lookup"><span data-stu-id="11f10-113">For example, your organization could have a data service that provides a large and growing number of named data sets, each with its own stable data schema.</span></span> <span data-ttu-id="11f10-114">Se puede crear un proveedor de tipos que lea los esquemas y presente los conjuntos de datos actuales al programador de una manera fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="11f10-114">You can create a type provider that reads the schemas and presents the current data sets to the programmer in a strongly typed way.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="11f10-115">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="11f10-115">Before You Start</span></span>
<span data-ttu-id="11f10-116">El mecanismo de proveedores de tipo está diseñado principalmente para insertar espacios de información de servicios y datos estables en la experiencia de programación de F#.</span><span class="sxs-lookup"><span data-stu-id="11f10-116">The type provider mechanism is primarily designed for injecting stable data and service information spaces into the F# programming experience.</span></span>

<span data-ttu-id="11f10-117">Este mecanismo no está diseñado para insertar espacios de información cuyo esquema cambie durante la ejecución del programa de forma relevante para la lógica del programa.</span><span class="sxs-lookup"><span data-stu-id="11f10-117">This mechanism isn’t designed for injecting information spaces whose schema changes during program execution in ways that are relevant to program logic.</span></span> <span data-ttu-id="11f10-118">El mecanismo tampoco está diseñado para la metaprogramación dentro del lenguaje, aunque ese dominio contenga algunas aplicaciones válidas.</span><span class="sxs-lookup"><span data-stu-id="11f10-118">Also, the mechanism isn't designed for intra-language meta-programming, even though that domain contains some valid uses.</span></span> <span data-ttu-id="11f10-119">Debe utilizar este mecanismo solo en caso necesario y cuando el desarrollo de un proveedor de tipo produzca un valor muy alto.</span><span class="sxs-lookup"><span data-stu-id="11f10-119">You should use this mechanism only where necessary and where the development of a type provider yields very high value.</span></span>

<span data-ttu-id="11f10-120">Debe evitar escribir un proveedor de tipos cuando no hay un esquema disponible.</span><span class="sxs-lookup"><span data-stu-id="11f10-120">You should avoid writing a type provider where a schema isn't available.</span></span> <span data-ttu-id="11f10-121">Igualmente, debe evitar escribir un proveedor de tipo cuando una biblioteca de .NET normal (o incluso una existente) sería suficiente.</span><span class="sxs-lookup"><span data-stu-id="11f10-121">Likewise, you should avoid writing a type provider where an ordinary (or even an existing) .NET library would suffice.</span></span>

<span data-ttu-id="11f10-122">Antes de comenzar, debería hacerse las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="11f10-122">Before you start, you might ask the following questions:</span></span>


- <span data-ttu-id="11f10-123">¿Tiene un esquema para su fuente de información?</span><span class="sxs-lookup"><span data-stu-id="11f10-123">Do you have a schema for your information source?</span></span> <span data-ttu-id="11f10-124">Si lo tiene, ¿cuál es la correspondencia entre los sistemas de tipos de F# y .NET?</span><span class="sxs-lookup"><span data-stu-id="11f10-124">If so, what’s the mapping into the F# and .NET type system?</span></span>

- <span data-ttu-id="11f10-125">¿Puede utilizar una API existente (dinámicamente tipada) como punto de partida para su implementación?</span><span class="sxs-lookup"><span data-stu-id="11f10-125">Can you use an existing (dynamically typed) API as a starting point for your implementation?</span></span>

- <span data-ttu-id="11f10-126">¿Usarán usted y su organización el proveedor de tipo lo suficiente como para hacer que valga la pena escribirlo?</span><span class="sxs-lookup"><span data-stu-id="11f10-126">Will you and your organization have enough uses of the type provider to make writing it worthwhile?</span></span> <span data-ttu-id="11f10-127">¿Cubriría una biblioteca normal de .NET sus necesidades?</span><span class="sxs-lookup"><span data-stu-id="11f10-127">Would a normal .NET library meet your needs?</span></span>

- <span data-ttu-id="11f10-128">¿Cuánto cambiará el esquema?</span><span class="sxs-lookup"><span data-stu-id="11f10-128">How much will your schema change?</span></span>

- <span data-ttu-id="11f10-129">¿Cambiará durante la escritura del código?</span><span class="sxs-lookup"><span data-stu-id="11f10-129">Will it change during coding?</span></span>

- <span data-ttu-id="11f10-130">¿Cambiará entre las sesiones de escritura de código?</span><span class="sxs-lookup"><span data-stu-id="11f10-130">Will it change between coding sessions?</span></span>

- <span data-ttu-id="11f10-131">¿Cambiará durante la ejecución del programa?</span><span class="sxs-lookup"><span data-stu-id="11f10-131">Will it change during program execution?</span></span>

<span data-ttu-id="11f10-132">Los proveedores de tipo son más adecuados en situaciones en las que el esquema es estable en tiempo de ejecución y durante el tiempo de vida del código compilado.</span><span class="sxs-lookup"><span data-stu-id="11f10-132">Type providers are best suited to situations where the schema is stable at runtime and during the lifetime of compiled code.</span></span>


## <a name="a-simple-type-provider"></a><span data-ttu-id="11f10-133">Un proveedor de tipos simple</span><span class="sxs-lookup"><span data-stu-id="11f10-133">A Simple Type Provider</span></span>
<span data-ttu-id="11f10-134">Este ejemplo es Samples.HelloWorldTypeProvider en la `SampleProviders\Providers` directorio de la [módulo con el ejemplo de F # 3.0](https://fsharp3sample.codeplex.com) en el sitio Web de Codeplex.</span><span class="sxs-lookup"><span data-stu-id="11f10-134">This sample is Samples.HelloWorldTypeProvider in the `SampleProviders\Providers` directory of the [F# 3.0 Sample Pack](https://fsharp3sample.codeplex.com) on the Codeplex website.</span></span> <span data-ttu-id="11f10-135">El proveedor hace que esté disponible un "espacio de tipos" que contiene 100 tipos borrados, como muestra el código siguiente, en el que se usa la sintaxis de signatura de F# y se omiten los detalles de todos los tipos excepto `Type1`.</span><span class="sxs-lookup"><span data-stu-id="11f10-135">The provider makes available a "type space" that contains 100 erased types, as the following code shows by using F# signature syntax and omitting the details for all except `Type1`.</span></span> <span data-ttu-id="11f10-136">Para obtener más información sobre los tipos borrados, consulte [obtener más información acerca de los tipos borrados proporcionados](#details-about-erased-provided-types) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="11f10-136">For more information about erased types, see [Details About Erased Provided Types](#details-about-erased-provided-types) later in this topic.</span></span>

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

    /// This is an instance property.
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

<span data-ttu-id="11f10-137">Observe que el conjunto de tipos y miembros proporcionados se conoce de forma estática.</span><span class="sxs-lookup"><span data-stu-id="11f10-137">Note that the set of types and members provided is statically known.</span></span> <span data-ttu-id="11f10-138">Este ejemplo no aprovecha la capacidad de los proveedores para proporcionar tipos que dependen de un esquema.</span><span class="sxs-lookup"><span data-stu-id="11f10-138">This example doesn't leverage the ability of providers to provide types that depend on a schema.</span></span> <span data-ttu-id="11f10-139">La implementación del proveedor de tipo se muestra en el código siguiente y sus detalles se tratan en secciones posteriores de este tema.</span><span class="sxs-lookup"><span data-stu-id="11f10-139">The implementation of the type provider is outlined in the following code, and the details are covered in later sections of this topic.</span></span>


>[!WARNING] 
<span data-ttu-id="11f10-140">Puede haber algunas pequeñas diferencias entre los nombres de este código y los de los ejemplos en línea.</span><span class="sxs-lookup"><span data-stu-id="11f10-140">There may be some small naming differences between this code and the online samples.</span></span>

```fsharp
namespace Samples.FSharp.HelloWorldTypeProvider

open System
open System.Reflection
open Samples.FSharp.ProvidedTypes
open Microsoft.FSharp.Core.CompilerServices
open Microsoft.FSharp.Quotations

// This type defines the type provider. When compiled to a DLL, it can be added
// as a reference to an F# command-line compilation, script, or project.
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this = 

  // Inheriting from this type provides implementations of ITypeProvider 
  // in terms of the provided types below.
  inherit TypeProviderForNamespaces()

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

<span data-ttu-id="11f10-141">Para utilizar este proveedor, abra una instancia independiente de Visual Studio 2012, crear un script de F # y, a continuación, agregue una referencia al proveedor desde el script utilizando #r como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="11f10-141">To use this provider, open a separate instance of Visual Studio 2012, create an F# script, and then add a reference to the provider from your script by using #r as the following code shows:</span></span>

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

<span data-ttu-id="11f10-142">A continuación, busque los tipos en el espacio de nombres `Samples.HelloWorldTypeProvider` generado por el proveedor de tipo.</span><span class="sxs-lookup"><span data-stu-id="11f10-142">Then look for the types under the `Samples.HelloWorldTypeProvider` namespace that the type provider generated.</span></span>

<span data-ttu-id="11f10-143">Antes de volver a compilar el proveedor, asegúrese de que se han cerrado todas las instancias de Visual Studio y de F# Interactive que están utilizando la DLL del proveedor.</span><span class="sxs-lookup"><span data-stu-id="11f10-143">Before you recompile the provider, make sure that you have closed all instances of Visual Studio and F# Interactive that are using the provider DLL.</span></span> <span data-ttu-id="11f10-144">De lo contrario, aparecerá un error de compilación porque la DLL de salida estará bloqueada.</span><span class="sxs-lookup"><span data-stu-id="11f10-144">Otherwise, a build error will occur because the output DLL will be locked.</span></span>

<span data-ttu-id="11f10-145">Para depurar este proveedor mediante instrucciones de impresión, cree un script que exponga un problema con el proveedor y, a continuación, utilice el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="11f10-145">To debug this provider by using print statements, make a script that exposes a problem with the provider, and then use the following code:</span></span>

```fsharp
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="11f10-146">Para depurar este proveedor mediante Visual Studio, abra el símbolo del sistema de Visual Studio con credenciales administrativas y ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="11f10-146">To debug this provider by using Visual Studio, open the Visual Studio command prompt with administrative credentials, and run the following command:</span></span>

```fsharp
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="11f10-147">Como alternativa, abra Visual Studio, abra el menú Depurar, elija `Debug/Attach to process…`y asociarlo a otro `devenv` proceso donde puede editar la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="11f10-147">As an alternative, open Visual Studio, open the Debug menu, choose `Debug/Attach to process…`, and attach to another `devenv` process where you’re editing your script.</span></span> <span data-ttu-id="11f10-148">Con este método, le resultará más fácil centrarse en la lógica particular del proveedor de tipos escribiendo interactivamente expresiones en la segunda instancia (con IntelliSense completo y otras características).</span><span class="sxs-lookup"><span data-stu-id="11f10-148">By using this method, you can more easily target particular logic in the type provider by interactively typing expressions into the second instance (with full IntelliSense and other features).</span></span>

<span data-ttu-id="11f10-149">Puede deshabilitar la depuración "Solo mi código" para identificar mejor los errores en el código generado.</span><span class="sxs-lookup"><span data-stu-id="11f10-149">You can disable Just My Code debugging to better identify errors in generated code.</span></span> <span data-ttu-id="11f10-150">Para obtener información acerca de cómo habilitar o deshabilitar esta característica, consulte [desplazarse por el código con el depurador](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span><span class="sxs-lookup"><span data-stu-id="11f10-150">For information about how to enable or disable this feature, see [Navigating through Code with the Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span></span> <span data-ttu-id="11f10-151">Además, también puede establecer excepciones de primera oportunidad detectar abriendo el `Debug` menú y, a continuación, eligiendo `Exceptions` o eligiendo las teclas Ctrl + Alt + E para abrir el `Exceptions` cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="11f10-151">Also, you can also set first-chance exception catching by opening the `Debug` menu and then choosing `Exceptions` or by choosing the Ctrl+Alt+E keys to open the `Exceptions` dialog box.</span></span> <span data-ttu-id="11f10-152">Este cuadro de diálogo, en `Common Language Runtime Exceptions`, seleccione la `Thrown` casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="11f10-152">In that dialog box, under `Common Language Runtime Exceptions`, select the `Thrown` check box.</span></span>


### <a name="implementation-of-the-type-provider"></a><span data-ttu-id="11f10-153">Implementación del proveedor de tipos</span><span class="sxs-lookup"><span data-stu-id="11f10-153">Implementation of the Type Provider</span></span>
<span data-ttu-id="11f10-154">En esta sección se muestran las etapas principales de la implementación del proveedor de tipo.</span><span class="sxs-lookup"><span data-stu-id="11f10-154">This section walks you through the principal sections of the type provider implementation.</span></span> <span data-ttu-id="11f10-155">En primer lugar, defina el tipo del proveedor de tipos personalizado:</span><span class="sxs-lookup"><span data-stu-id="11f10-155">First, you define the type for the custom type provider itself:</span></span>

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

<span data-ttu-id="11f10-156">Este tipo debe ser pública y debe marcarse con el [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) para que el compilador reconozca el proveedor de tipos cuando un proyecto independiente de F # hace referencia al ensamblado que contiene el tipo de atributo.</span><span class="sxs-lookup"><span data-stu-id="11f10-156">This type must be public, and you must mark it with the [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) attribute so that the compiler will recognize the type provider when a separate F# project references the assembly that contains the type.</span></span> <span data-ttu-id="11f10-157">El *config* parámetro es opcional y, si lo hay, contiene información de configuración contextual para la instancia del proveedor de tipo creados por el compilador de F #.</span><span class="sxs-lookup"><span data-stu-id="11f10-157">The *config* parameter is optional, and, if present, contains contextual configuration information for the type provider instance that the F# compiler creates.</span></span>

<span data-ttu-id="11f10-158">A continuación, implementará la [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) interfaz.</span><span class="sxs-lookup"><span data-stu-id="11f10-158">Next, you implement the [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) interface.</span></span> <span data-ttu-id="11f10-159">En este caso, puede utilizar el tipo `TypeProviderForNamespaces` de la API `ProvidedTypes` como tipo base.</span><span class="sxs-lookup"><span data-stu-id="11f10-159">In this case, you use the `TypeProviderForNamespaces` type from the `ProvidedTypes` API as a base type.</span></span> <span data-ttu-id="11f10-160">Este tipo auxiliar puede proporcionar una colección finita de espacios de nombres proporcionados anticipadamente, cada uno de los cuales contiene directamente un número finito de tipos fijos proporcionados anticipadamente.</span><span class="sxs-lookup"><span data-stu-id="11f10-160">This helper type can provide a finite collection of eagerly provided namespaces, each of which directly contains a finite number of fixed, eagerly provided types.</span></span> <span data-ttu-id="11f10-161">En este contexto, el proveedor *anticipadamente* genera tipos aunque no son necesarios ni se utilicen.</span><span class="sxs-lookup"><span data-stu-id="11f10-161">In this context, the provider *eagerly* generates types even if they aren't needed or used.</span></span>

```fsharp
inherit TypeProviderForNamespaces()
```

<span data-ttu-id="11f10-162">A continuación, defina los valores privados locales que especifican el espacio de nombres para los tipos proporcionados y busque el ensamblado propio del proveedor de tipos.</span><span class="sxs-lookup"><span data-stu-id="11f10-162">Next, define local private values that specify the namespace for the provided types, and find the type provider assembly itself.</span></span> <span data-ttu-id="11f10-163">Este ensamblado se utiliza más adelante como tipo primario lógico de los tipos borrados proporcionados.</span><span class="sxs-lookup"><span data-stu-id="11f10-163">This assembly is used later as the logical parent type of the erased types that are provided.</span></span>

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

<span data-ttu-id="11f10-164">A continuación, cree una función para proporcionar cada uno de los tipos Type1… Type100.</span><span class="sxs-lookup"><span data-stu-id="11f10-164">Next, create a function to provide each of the types Type1…Type100.</span></span> <span data-ttu-id="11f10-165">Esta función se explica con más detalle más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="11f10-165">This function is explained in more detail later in this topic.</span></span>

```fsharp
let makeOneProvidedType (n:int) = …
```

<span data-ttu-id="11f10-166">A continuación, genere los 100 tipos proporcionados:</span><span class="sxs-lookup"><span data-stu-id="11f10-166">Next, generate the 100 provided types:</span></span>

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

<span data-ttu-id="11f10-167">Después, agregue los tipos como un espacio de nombres proporcionado:</span><span class="sxs-lookup"><span data-stu-id="11f10-167">Next, add the types as a provided namespace:</span></span>

```fsharp
do this.AddNamespace(namespaceName, types)
```

<span data-ttu-id="11f10-168">Finalmente, agregue un atributo de ensamblado que indique que está creando una DLL de proveedor de tipos:</span><span class="sxs-lookup"><span data-stu-id="11f10-168">Finally, add an assembly attribute that indicates that you are creating a type provider DLL:</span></span>

```fsharp
[<assembly:TypeProviderAssembly>] 
do()
```

### <a name="providing-one-type-and-its-members"></a><span data-ttu-id="11f10-169">Proporcionar un tipo y sus miembros</span><span class="sxs-lookup"><span data-stu-id="11f10-169">Providing One Type And Its Members</span></span>
<span data-ttu-id="11f10-170">La función `makeOneProvidedType` hace el trabajo real de proporcionar uno de los tipos.</span><span class="sxs-lookup"><span data-stu-id="11f10-170">The `makeOneProvidedType` function does the real work of providing one of the types.</span></span>

```fsharp
let makeOneProvidedType (n:int) = 
…
```

<span data-ttu-id="11f10-171">En este paso se explica la implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="11f10-171">This step explains the implementation of this function.</span></span> <span data-ttu-id="11f10-172">En primer lugar, cree el tipo proporcionado (por ejemplo, Type1, cuando n = 1, o Type57, cuando n = 57).</span><span class="sxs-lookup"><span data-stu-id="11f10-172">First, create the provided type (for example, Type1, when n = 1, or Type57, when n = 57).</span></span>

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code, 
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly,namespaceName,
"Type" + string n,
baseType = Some typeof<obj>)
```

<span data-ttu-id="11f10-173">Debe tener en cuenta los puntos siguientes:</span><span class="sxs-lookup"><span data-stu-id="11f10-173">You should note the following points:</span></span>


- <span data-ttu-id="11f10-174">Este tipo proporcionado es un tipo borrado.</span><span class="sxs-lookup"><span data-stu-id="11f10-174">This provided type is erased.</span></span>  <span data-ttu-id="11f10-175">Dado que ha indicado que el tipo base es `obj`, instancias aparecerán como valores de tipo [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) en el código compilado.</span><span class="sxs-lookup"><span data-stu-id="11f10-175">Because you indicate that the base type is `obj`, instances will appear as values of type [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) in compiled code.</span></span>
<br />

- <span data-ttu-id="11f10-176">Cuando especifique un tipo no anidado, deberá especificar también el ensamblado y el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="11f10-176">When you specify a non-nested type, you must specify the assembly and namespace.</span></span> <span data-ttu-id="11f10-177">Para los tipos borrados, el ensamblado deberá ser el propio ensamblado del proveedor de tipo.</span><span class="sxs-lookup"><span data-stu-id="11f10-177">For erased types, the assembly should be the type provider assembly itself.</span></span>
<br />

<span data-ttu-id="11f10-178">A continuación, agregue la documentación XML al tipo.</span><span class="sxs-lookup"><span data-stu-id="11f10-178">Next, add XML documentation to the type.</span></span> <span data-ttu-id="11f10-179">Esta documentación se demora, es decir, se calcula a petición si el compilador host la necesita.</span><span class="sxs-lookup"><span data-stu-id="11f10-179">This documentation is delayed, that is, computed on-demand if the host compiler needs it.</span></span>

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

<span data-ttu-id="11f10-180">A continuación, agregue una propiedad estática proporcionada al tipo:</span><span class="sxs-lookup"><span data-stu-id="11f10-180">Next you add a provided static property to the type:</span></span>

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty", 
propertyType = typeof<string>, 
IsStatic=true,
GetterCode= (fun args -> <@@ "Hello!" @@>))
```

<span data-ttu-id="11f10-181">Al obtener esta propiedad, siempre se evaluará como la cadena "Hello!".</span><span class="sxs-lookup"><span data-stu-id="11f10-181">Getting this property will always evaluate to the string "Hello!".</span></span> <span data-ttu-id="11f10-182">La función `GetterCode` de la propiedad utiliza una expresión de código delimitada de F# que representa el código que genera el compilador host para obtener la propiedad.</span><span class="sxs-lookup"><span data-stu-id="11f10-182">The `GetterCode` for the property uses an F# quotation, which represents the code that the host compiler generates for getting the property.</span></span> <span data-ttu-id="11f10-183">Para obtener más información acerca de expresiones de código delimitadas, consulte [expresiones de código delimitadas (F #)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).</span><span class="sxs-lookup"><span data-stu-id="11f10-183">For more information about quotations, see [Code Quotations (F#)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).</span></span>

<span data-ttu-id="11f10-184">Agregue la documentación XML a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="11f10-184">Add XML documentation to the property.</span></span>

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

<span data-ttu-id="11f10-185">Ahora asocie la propiedad proporcionada al tipo proporcionado.</span><span class="sxs-lookup"><span data-stu-id="11f10-185">Now attach the provided property to the provided type.</span></span> <span data-ttu-id="11f10-186">Debe asociar un miembro proporcionado a un único tipo.</span><span class="sxs-lookup"><span data-stu-id="11f10-186">You must attach a provided member to one and only one type.</span></span> <span data-ttu-id="11f10-187">De lo contrario, el miembro nunca será accesible.</span><span class="sxs-lookup"><span data-stu-id="11f10-187">Otherwise, the member will never be accessible.</span></span>

```fsharp
t.AddMember staticProp
```

<span data-ttu-id="11f10-188">Ahora cree un constructor proporcionado que no reciba ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="11f10-188">Now create a provided constructor that takes no parameters.</span></span>

```fsharp
let ctor = ProvidedConstructor(parameters = [ ], 
InvokeCode= (fun args -> <@@ "The object data" :> obj @@>))
```

<span data-ttu-id="11f10-189">La función `InvokeCode` del constructor devuelve una expresión de código delimitada de F# que representa el código que el compilador host genera cuando se llama al constructor.</span><span class="sxs-lookup"><span data-stu-id="11f10-189">The `InvokeCode` for the constructor returns an F# quotation, which represents the code that the host compiler generates when the constructor is called.</span></span> <span data-ttu-id="11f10-190">Por ejemplo, puede usar el constructor siguiente:</span><span class="sxs-lookup"><span data-stu-id="11f10-190">For example, you can use the following constructor:</span></span>

```fsharp
new Type10()
```

<span data-ttu-id="11f10-191">Se creará una instancia del tipo proporcionado con los datos subyacentes "The object data".</span><span class="sxs-lookup"><span data-stu-id="11f10-191">An instance of the provided type will be created with underlying data "The object data".</span></span> <span data-ttu-id="11f10-192">El código delimitado incluye una conversión a [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) porque ese tipo es el borrado de este tipo proporcionado (tal y como se especificó cuando declaró el tipo proporcionado).</span><span class="sxs-lookup"><span data-stu-id="11f10-192">The quoted code includes a conversion to [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) because that type is the erasure of this provided type (as you specified when you declared the provided type).</span></span>

<span data-ttu-id="11f10-193">Agregue la documentación XML al constructor y agregue el constructor proporcionado al tipo proporcionado:</span><span class="sxs-lookup"><span data-stu-id="11f10-193">Add XML documentation to the constructor, and add the provided constructor to the provided type:</span></span>

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

<span data-ttu-id="11f10-194">Cree un segundo constructor proporcionado que tome un parámetro:</span><span class="sxs-lookup"><span data-stu-id="11f10-194">Create a second provided constructor that takes one parameter:</span></span>

```fsharp
let ctor2 = 
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ], 
InvokeCode= (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

<span data-ttu-id="11f10-195">La función `InvokeCode` del constructor devuelve de nuevo una expresión de código delimitada de F# que representa el código que el compilador host generó para una llamada al método.</span><span class="sxs-lookup"><span data-stu-id="11f10-195">The `InvokeCode` for the constructor again returns an F# quotation, which represents the code that the host compiler generated for a call to the method.</span></span> <span data-ttu-id="11f10-196">Por ejemplo, puede usar el constructor siguiente:</span><span class="sxs-lookup"><span data-stu-id="11f10-196">For example, you can use the following constructor:</span></span>

```fsharp
new Type10("ten")
```

<span data-ttu-id="11f10-197">Se crea una instancia del tipo proporcionado con los datos subyacentes "ten".</span><span class="sxs-lookup"><span data-stu-id="11f10-197">An instance of the provided type is created with underlying data "ten".</span></span> <span data-ttu-id="11f10-198">Es posible que haya notado que la función `InvokeCode` devuelve una expresión de código delimitada.</span><span class="sxs-lookup"><span data-stu-id="11f10-198">You may have already noticed that the `InvokeCode` function returns a quotation.</span></span> <span data-ttu-id="11f10-199">La entrada de esta función es una lista de expresiones, una por cada parámetro del constructor.</span><span class="sxs-lookup"><span data-stu-id="11f10-199">The input to this function is a list of expressions, one per constructor parameter.</span></span> <span data-ttu-id="11f10-200">En este caso, una expresión que representa el valor del único parámetro está disponible en `args.[0]`.</span><span class="sxs-lookup"><span data-stu-id="11f10-200">In this case, an expression that represents the single parameter value is available in `args.[0]`.</span></span> <span data-ttu-id="11f10-201">El código de una llamada al constructor convierte el valor devuelto en el tipo borrado `obj`.</span><span class="sxs-lookup"><span data-stu-id="11f10-201">The code for a call to the constructor coerces the return value to the erased type `obj`.</span></span> <span data-ttu-id="11f10-202">Después de agregar el segundo constructor proporcionado al tipo, cree una propiedad de instancia proporcionada:</span><span class="sxs-lookup"><span data-stu-id="11f10-202">After you add the second provided constructor to the type, you create a provided instance property:</span></span>

```fsharp
let instanceProp = 
ProvidedProperty(propertyName = "InstanceProperty", 
propertyType = typeof<int>, 
GetterCode= (fun args -> 
<@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

<span data-ttu-id="11f10-203">Al obtener esta propiedad, se devuelve la longitud de la cadena, que es el objeto de representación.</span><span class="sxs-lookup"><span data-stu-id="11f10-203">Getting this property will return the length of the string, which is the representation object.</span></span> <span data-ttu-id="11f10-204">La propiedad `GetterCode` devuelve una expresión de código delimitada de F# que especifica el código que genera el compilador host para obtener la propiedad.</span><span class="sxs-lookup"><span data-stu-id="11f10-204">The `GetterCode` property returns an F# quotation that specifies the code that the host compiler generates to get the property.</span></span> <span data-ttu-id="11f10-205">Al igual que la función `InvokeCode`, la función `GetterCode` devuelve una expresión de código delimitada.</span><span class="sxs-lookup"><span data-stu-id="11f10-205">Like `InvokeCode`, the `GetterCode` function returns a quotation.</span></span> <span data-ttu-id="11f10-206">El compilador host llama a esta función con una lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="11f10-206">The host compiler calls this function with a list of arguments.</span></span> <span data-ttu-id="11f10-207">En este caso, los argumentos incluyen únicamente la expresión que representa la instancia sobre la que se llama a la función, a la cual se puede tener acceso mediante `args.[0]`. Seguidamente, la implementación de `GetterCode` se une a la expresión de código delimitada resultante en el tipo borrado `obj` y se utiliza una conversión para satisfacer el mecanismo del compilador que comprueba los tipos así como que el objeto es una cadena.</span><span class="sxs-lookup"><span data-stu-id="11f10-207">In this case, the arguments include just the single expression that represents the instance upon which the getter is being called, which you can access by using `args.[0]`.The implementation of `GetterCode` then splices into the result quotation at the erased type `obj`, and a cast is used to satisfy the compiler's mechanism for checking types that the object is a string.</span></span> <span data-ttu-id="11f10-208">La parte siguiente de `makeOneProvidedType` proporciona un método de instancia con un parámetro.</span><span class="sxs-lookup"><span data-stu-id="11f10-208">The next part of `makeOneProvidedType` provides an instance method with one parameter.</span></span>

```fsharp
let instanceMeth = 
ProvidedMethod(methodName = "InstanceMethod", 
parameters = [ProvidedParameter("x",typeof<int>)], 
returnType = typeof<char>, 
InvokeCode = (fun args -> 
<@@ ((%%(args.[0]) : obj) :?> string).Chars(%%(args.[1]) : int) @@>))

instanceMeth.AddXmlDocDelayed(fun () -> "This is an instance method")
// Add the instance method to the type.
t.AddMember instanceMeth
```

<span data-ttu-id="11f10-209">Finalmente, cree un tipo anidado que contenga 100 propiedades anidadas.</span><span class="sxs-lookup"><span data-stu-id="11f10-209">Finally, create a nested type that contains 100 nested properties.</span></span> <span data-ttu-id="11f10-210">La creación de este tipo anidado y sus propiedades se demora, es decir, se calcula a petición.</span><span class="sxs-lookup"><span data-stu-id="11f10-210">The creation of this nested type and its properties is delayed, that is, computed on-demand.</span></span>

```fsharp
t.AddMembersDelayed(fun () -> 
let nestedType = ProvidedTypeDefinition("NestedType",
Some typeof<obj>

)

nestedType.AddMembersDelayed (fun () -> 
let staticPropsInNestedType = 
[ for i in 1 .. 100 do
let valueOfTheProperty = "I am string "  + string i

let p = ProvidedProperty(propertyName = "StaticProperty" + string i, 
propertyType = typeof<string>, 
IsStatic=true,
GetterCode= (fun args -> <@@ valueOfTheProperty @@>))

p.AddXmlDocDelayed(fun () -> 
sprintf "This is StaticProperty%d on NestedType" i)

yield p ]
staticPropsInNestedType)

[nestedType])

// The result of makeOneProvidedType is the type.
t
```

### <a name="details-about-erased-provided-types"></a><span data-ttu-id="11f10-211">Detalles sobre los tipos proporcionados borrados</span><span class="sxs-lookup"><span data-stu-id="11f10-211">Details about Erased Provided Types</span></span>
<span data-ttu-id="11f10-212">En el ejemplo de esta sección se proporciona solo *tipos proporcionados borrados*, que son especialmente útiles en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="11f10-212">The example in this section provides only *erased provided types*, which are particularly useful in the following situations:</span></span>


- <span data-ttu-id="11f10-213">Cuando se escribe un proveedor para un espacio de información que solo contiene datos y métodos.</span><span class="sxs-lookup"><span data-stu-id="11f10-213">When you are writing a provider for an information space that contains only data and methods.</span></span>
<br />

- <span data-ttu-id="11f10-214">Cuando se escribe un proveedor en el que la semántica precisa de tipos en tiempo de ejecución no es fundamental para el uso práctico del espacio de información.</span><span class="sxs-lookup"><span data-stu-id="11f10-214">When you are writing a provider where accurate runtime-type semantics aren't critical for practical use of the information space.</span></span>
<br />

- <span data-ttu-id="11f10-215">Cuando se escribe un proveedor para un espacio de información que es tan grande y está tan interconectado que no es técnicamente factible generar tipos reales de .NET para el espacio de información.</span><span class="sxs-lookup"><span data-stu-id="11f10-215">When you are writing a provider for an information space that is so large and interconnected that it isn’t technically feasible to generate real .NET types for the information space.</span></span>
<br />

<span data-ttu-id="11f10-216">En este ejemplo, se borra cada tipo proporcionado para el tipo `obj` y todos los usos del tipo aparecen como tipo `obj` en el código compilado.</span><span class="sxs-lookup"><span data-stu-id="11f10-216">In this example, each provided type is erased to type `obj`, and all uses of the type will appear as type `obj` in compiled code.</span></span> <span data-ttu-id="11f10-217">De hecho, los objetos subyacentes de estos ejemplos son cadenas, pero el tipo aparecerá como `System.Object` en el código compilado de .NET.</span><span class="sxs-lookup"><span data-stu-id="11f10-217">In fact, the underlying objects in these examples are strings, but the type will appear as `System.Object` in .NET compiled code.</span></span> <span data-ttu-id="11f10-218">Como con todos los usos del borrado de tipos, se puede utilizar la conversión boxing explícita, la conversión unboxing y la conversión para trastocar los tipos borrados.</span><span class="sxs-lookup"><span data-stu-id="11f10-218">As with all uses of type erasure, you can use explicit boxing, unboxing, and casting to subvert erased types.</span></span> <span data-ttu-id="11f10-219">En este caso, puede producirse una excepción de conversión no válida cuando se utiliza el objeto.</span><span class="sxs-lookup"><span data-stu-id="11f10-219">In this case, a cast exception that isn’t valid may result when the object is used.</span></span> <span data-ttu-id="11f10-220">Un runtime de un proveedor puede definir su propio tipo de representación privado para ayudar a protegerse contra representaciones falsas.</span><span class="sxs-lookup"><span data-stu-id="11f10-220">A provider runtime can define its own private representation type to help protect against false representations.</span></span> <span data-ttu-id="11f10-221">No se pueden definir tipos borrados en F#.</span><span class="sxs-lookup"><span data-stu-id="11f10-221">You can’t define erased types in F# itself.</span></span> <span data-ttu-id="11f10-222">Solo se pueden borrar los tipos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="11f10-222">Only provided types may be erased.</span></span> <span data-ttu-id="11f10-223">Se deben entender las implicaciones, tanto prácticas como semánticas, de utilizar los tipos borrados para el proveedor de tipo o un proveedor que proporcione tipos borrados.</span><span class="sxs-lookup"><span data-stu-id="11f10-223">You must understand the ramifications, both practical and semantic, of using either erased types for your type provider or a provider that provides erased types.</span></span> <span data-ttu-id="11f10-224">Un tipo borrado no tiene un tipo real de .NET.</span><span class="sxs-lookup"><span data-stu-id="11f10-224">An erased type has no real .NET type.</span></span> <span data-ttu-id="11f10-225">Por consiguiente, no se puede hacer una reflexión precisa sobre el tipo y se podrían trastocar los tipos borrados si se utilizan conversiones en tiempo de ejecución y otras técnicas que dependen de semánticas exactas de tipos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="11f10-225">Therefore, you cannot do accurate reflection over the type, and you might subvert erased types if you use runtime casts and other techniques that rely on exact runtime type semantics.</span></span> <span data-ttu-id="11f10-226">El trastocamiento de tipos borrados frecuentemente da lugar a excepciones de conversión de tipos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="11f10-226">Subversion of erased types frequently results in type cast exceptions at runtime.</span></span>


### <a name="choosing-representations-for-erased-provided-types"></a><span data-ttu-id="11f10-227">Elegir representaciones para los tipos proporcionados borrados</span><span class="sxs-lookup"><span data-stu-id="11f10-227">Choosing Representations for Erased Provided Types</span></span>
<span data-ttu-id="11f10-228">Para algunos usos de los tipos proporcionados borrados, no se requiere ninguna representación.</span><span class="sxs-lookup"><span data-stu-id="11f10-228">For some uses of erased provided types, no representation is required.</span></span> <span data-ttu-id="11f10-229">Por ejemplo, el tipo proporcionado borrado podría contener únicamente propiedades y miembros estáticos y ningún constructor, por lo que ningún método ni propiedad devolvería ninguna instancia del tipo.</span><span class="sxs-lookup"><span data-stu-id="11f10-229">For example, the erased provided type might contain only static properties and members and no constructors, and no methods or properties would return an instance of the type.</span></span> <span data-ttu-id="11f10-230">Si puede tener acceso a instancias de un tipo proporcionado borrado, considere las preguntas siguientes:</span><span class="sxs-lookup"><span data-stu-id="11f10-230">If you can reach instances of an erased provided type, you must consider the following questions:</span></span>


- <span data-ttu-id="11f10-231">¿Qué es el borrado de un tipo proporcionado?</span><span class="sxs-lookup"><span data-stu-id="11f10-231">What is the erasure of a provided type?</span></span>
<br />
  - <span data-ttu-id="11f10-232">El borrado de un tipo proporcionado es el modo en que el tipo aparece en el código compilado de .NET.</span><span class="sxs-lookup"><span data-stu-id="11f10-232">The erasure of a provided type is how the type appears in compiled .NET code.</span></span>
<br />

  - <span data-ttu-id="11f10-233">El borrado de una clase de un tipo proporcionado borrado siempre es el primer tipo base no borrado de la cadena de herencia del tipo.</span><span class="sxs-lookup"><span data-stu-id="11f10-233">The erasure of a provided erased class type is always the first non-erased base type in the inheritance chain of the type.</span></span>
<br />

  - <span data-ttu-id="11f10-234">El borrado de una interfaz de un tipo de borrado proporcionado es siempre `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="11f10-234">The erasure of a provided erased interface type is always `System.Object`.</span></span>
<br />

- <span data-ttu-id="11f10-235">¿Qué son las representaciones de un tipo proporcionado?</span><span class="sxs-lookup"><span data-stu-id="11f10-235">What are the representations of a provided type?</span></span>
<br />
  - <span data-ttu-id="11f10-236">Se denomina representaciones al conjunto de objetos posibles para un tipo proporcionado borrado.</span><span class="sxs-lookup"><span data-stu-id="11f10-236">The set of possible objects for an erased provided type are called its representations.</span></span> <span data-ttu-id="11f10-237">En el ejemplo de este documento, las representaciones de todos los tipos proporcionados borrados `Type1..Type100` son siempre objetos de cadena.</span><span class="sxs-lookup"><span data-stu-id="11f10-237">In the example in this document, the representations of all the erased provided types `Type1..Type100` are always string objects.</span></span>
<br />

<span data-ttu-id="11f10-238">Todas las representaciones de un tipo proporcionado deben ser compatibles con el borrado del tipo proporcionado.</span><span class="sxs-lookup"><span data-stu-id="11f10-238">All representations of a provided type must be compatible with the erasure of the provided type.</span></span> <span data-ttu-id="11f10-239">(De lo contrario, el compilador de F# generará un error para un uso del proveedor de tipos o se generará código no comprobable de .NET que no es válido.</span><span class="sxs-lookup"><span data-stu-id="11f10-239">(Otherwise, either the F# compiler will give an error for a use of the type provider, or unverifiable .NET code that isn't valid will be generated.</span></span> <span data-ttu-id="11f10-240">Un proveedor de tipos no es válido si devuelve código que proporciona una representación no válida).</span><span class="sxs-lookup"><span data-stu-id="11f10-240">A type provider isn’t valid if it returns code that gives a  representation that isn't valid.)</span></span>

<span data-ttu-id="11f10-241">Se puede elegir una representación para los objetos proporcionados mediante uno de los dos métodos siguientes, los cuales son muy comunes:</span><span class="sxs-lookup"><span data-stu-id="11f10-241">You can choose a representation for provided objects by using either of the following approaches, both of which are very common:</span></span>


- <span data-ttu-id="11f10-242">Si lo que se hace es simplemente proporcionar un contenedor fuertemente tipado sobre un tipo existente de .NET, tiene sentido que el tipo borre ese tipo, use instancias de ese tipo como representaciones, o ambas cosas.</span><span class="sxs-lookup"><span data-stu-id="11f10-242">If you're simply providing a strongly typed wrapper over an existing .NET type, it often makes sense for your type to erase to that type, use instances of that type as representations, or both.</span></span> <span data-ttu-id="11f10-243">Este enfoque es adecuado cuando la mayoría de los métodos existentes en ese tipo tienen sentido al usar la versión fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="11f10-243">This approach is appropriate when most of the existing methods on that type still make sense when using the strongly typed version.</span></span>
<br />

- <span data-ttu-id="11f10-244">Si lo que se desea es crear una API que difiera significativamente de cualquier API existente de .NET, tiene sentido crear tipos en tiempo de ejecución que constituyan la representación y el borrado de tipos para los tipos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="11f10-244">If you want to create an API that differs significantly from any existing .NET API, it makes sense to create runtime types that will be the type erasure and representations for the provided types.</span></span>
<br />

<span data-ttu-id="11f10-245">El ejemplo de este documento utiliza cadenas como representaciones de los objetos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="11f10-245">The example in this document uses strings as representations of provided objects.</span></span> <span data-ttu-id="11f10-246">Con frecuencia, puede ser adecuado utilizar otros objetos para las representaciones.</span><span class="sxs-lookup"><span data-stu-id="11f10-246">Frequently, it may be appropriate to use other objects for representations.</span></span> <span data-ttu-id="11f10-247">Por ejemplo, se puede utilizar un diccionario como contenedor de propiedades:</span><span class="sxs-lookup"><span data-stu-id="11f10-247">For example, you may use a dictionary as a property bag:</span></span>

```fsharp
ProvidedConstructor(parameters = [], 
InvokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

<span data-ttu-id="11f10-248">También se puede definir un tipo en el proveedor de tipo que se usará en tiempo de ejecución para formar la representación, junto con una o más operaciones en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="11f10-248">As an alternative, you may define a type in your type provider that will be used at runtime to form the representation, along with one or more runtime operations:</span></span>

```fsharp
type DataObject() =
let data = Dictionary<string,obj>()
member x.RuntimeOperation() = data.Count
```

<span data-ttu-id="11f10-249">Entonces los miembros proporcionados podrán construir instancias de este tipo de objeto:</span><span class="sxs-lookup"><span data-stu-id="11f10-249">Provided members can then construct instances of this object type:</span></span>

```fsharp
ProvidedConstructor(parameters = [], 
InvokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

<span data-ttu-id="11f10-250">En este caso, se puede (opcionalmente) utilizar este tipo como borrado de tipos especificando este tipo como `baseType` al construir `ProvidedTypeDefinition`:</span><span class="sxs-lookup"><span data-stu-id="11f10-250">In this case, you may (optionally) use this type as the type erasure by specifying this type as the `baseType` when constructing the `ProvidedTypeDefinition`:</span></span>

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

`Key Lessons`

<span data-ttu-id="11f10-251">En la sección anterior se explicó cómo crear un proveedor de tipos de borrado simple que proporciona una serie de tipos, propiedades y métodos.</span><span class="sxs-lookup"><span data-stu-id="11f10-251">The previous section explained how to create a simple erasing type provider that provides a range of types, properties, and methods.</span></span> <span data-ttu-id="11f10-252">En dicha sección se explicó también el concepto de borrado de tipos, incluidas algunas de las ventajas y desventajas de proporcionar tipos borrados desde un proveedor de tipos, y se explicaron las representaciones de los tipos borrados.</span><span class="sxs-lookup"><span data-stu-id="11f10-252">This section also explained the concept of type erasure, including some of the advantages and disadvantages of providing erased types from a type provider, and discussed representations of erased types.</span></span>


## <a name="a-type-provider-that-uses-static-parameters"></a><span data-ttu-id="11f10-253">Un proveedor de tipos que usa parámetros estáticos</span><span class="sxs-lookup"><span data-stu-id="11f10-253">A Type Provider That Uses Static Parameters</span></span>
<span data-ttu-id="11f10-254">La capacidad de parametrizar los proveedores de tipos mediante datos estáticos permite muchos escenarios interesantes, incluso en los casos en que el proveedor no necesita tener acceso a ningún dato local o remoto.</span><span class="sxs-lookup"><span data-stu-id="11f10-254">The ability to parameterize type providers by static data enables many interesting scenarios, even in cases when the provider doesn't need to access any local or remote data.</span></span> <span data-ttu-id="11f10-255">En esta sección, aprenderá algunas técnicas básicas para construir tales proveedores.</span><span class="sxs-lookup"><span data-stu-id="11f10-255">In this section, you’ll learn some basic techniques for putting together such a provider.</span></span>


### <a name="type-checked-regex-provider"></a><span data-ttu-id="11f10-256">Proveedor de tipo de comprobación de expresiones regulares</span><span class="sxs-lookup"><span data-stu-id="11f10-256">Type Checked Regex Provider</span></span>
<span data-ttu-id="11f10-257">Imagine que desea implementar un proveedor de tipo para expresiones regulares que contenga las bibliotecas `System.Text.RegularExpressions.Regex` de .NET en una interfaz que proporcione las siguientes garantías en tiempo de compilación:</span><span class="sxs-lookup"><span data-stu-id="11f10-257">Imagine that you want to implement a type provider for regular expressions that wraps the .NET `System.Text.RegularExpressions.Regex` libraries in an interface that provides the following compile-time guarantees:</span></span>


- <span data-ttu-id="11f10-258">Comprobar si una expresión regular es válida.</span><span class="sxs-lookup"><span data-stu-id="11f10-258">Verifying whether a regular expression is valid.</span></span>
<br />

- <span data-ttu-id="11f10-259">Proporcionar propiedades con nombre en las coincidencias basadas en cualquier nombre de grupo de la expresión regular.</span><span class="sxs-lookup"><span data-stu-id="11f10-259">Providing named properties on matches that are based on any group names in the regular expression.</span></span>
<br />

<span data-ttu-id="11f10-260">En esta sección se muestra cómo utilizar los proveedores de tipo para crear un tipo `RegExProviderType` parametrizado por el patrón de expresiones regulares para proporcionar estas ventajas.</span><span class="sxs-lookup"><span data-stu-id="11f10-260">This section shows you how to use type providers to create a `RegExProviderType` type that the regular expression pattern parameterizes to provide these benefits.</span></span> <span data-ttu-id="11f10-261">El compilador notificará un error si el patrón proporcionado no es válido y el proveedor de tipos puede extraer los grupos del patrón de modo que se pueda tener acceso a ellos mediante propiedades con nombre en las coincidencias.</span><span class="sxs-lookup"><span data-stu-id="11f10-261">The compiler will report an error if the supplied pattern isn't valid, and the type provider can extract the groups from the pattern so that you can access them by using named properties on matches.</span></span> <span data-ttu-id="11f10-262">Cuando se diseña un proveedor de tipo, se debería considerar el aspecto que debería presentar su API expuesta para los usuarios finales y cómo se traducirá este diseño a código de .NET.</span><span class="sxs-lookup"><span data-stu-id="11f10-262">When you design a type provider, you should consider how its exposed API should look to end users and how this design will translate to .NET code.</span></span> <span data-ttu-id="11f10-263">El ejemplo siguiente muestra cómo usar una API como esta para obtener los componentes del código de área de un número de teléfono:</span><span class="sxs-lookup"><span data-stu-id="11f10-263">The following example shows how to use such an API to get the components of the area code:</span></span>

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

<span data-ttu-id="11f10-264">El ejemplo siguiente muestra cómo convierte el proveedor de tipos estas llamadas:</span><span class="sxs-lookup"><span data-stu-id="11f10-264">The following example shows how the type provider translates these calls:</span></span>

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

<span data-ttu-id="11f10-265">Tenga en cuenta los puntos siguientes:</span><span class="sxs-lookup"><span data-stu-id="11f10-265">Note the following points:</span></span>


- <span data-ttu-id="11f10-266">El tipo estándar Regex representa el tipo parametrizado `RegexTyped`.</span><span class="sxs-lookup"><span data-stu-id="11f10-266">The standard Regex type represents the parameterized `RegexTyped` type.</span></span>
<br />

- <span data-ttu-id="11f10-267">El constructor `RegexTyped` produce una llamada al constructor Regex y le pasa el argumento de tipo estático para el patrón.</span><span class="sxs-lookup"><span data-stu-id="11f10-267">The `RegexTyped` constructor results in a call to the Regex constructor, passing in the static type argument for the pattern.</span></span>
<br />

- <span data-ttu-id="11f10-268">Los resultados del método `Match` se representan mediante el tipo estándar `System.Text.RegularExpressions.Match`.</span><span class="sxs-lookup"><span data-stu-id="11f10-268">The results of the `Match` method are represented by the standard `System.Text.RegularExpressions.Match` type.</span></span>
<br />

- <span data-ttu-id="11f10-269">Cada grupo con nombre produce una propiedad proporcionada, y el acceso a la propiedad produce el uso de un indizador en la colección `Groups` de una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="11f10-269">Each named group results in a provided property, and accessing the property results in a use of an indexer on a match’s `Groups` collection.</span></span>
<br />

<span data-ttu-id="11f10-270">El código siguiente es la base de la lógica para implementar un proveedor como este y este ejemplo omite la adición de todos los miembros al tipo proporcionado.</span><span class="sxs-lookup"><span data-stu-id="11f10-270">The following code is the core of the logic to implement such a provider, and this example omits the addition of all members to the provided type.</span></span> <span data-ttu-id="11f10-271">Para obtener información sobre cada miembro agregado, consulte la sección correspondiente más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="11f10-271">For information about each added member, see the appropriate section later in this topic.</span></span> <span data-ttu-id="11f10-272">Para obtener el código completo, descargue el ejemplo de la [módulo con el ejemplo de F # 3.0](https://fsharp3sample.codeplex.com) en el sitio Web de Codeplex.</span><span class="sxs-lookup"><span data-stu-id="11f10-272">For the full code, download the sample from the [F# 3.0 Sample Pack](https://fsharp3sample.codeplex.com) on the Codeplex website.</span></span>

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
let ty = ProvidedTypeDefinition(
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

<span data-ttu-id="11f10-273">Tenga en cuenta los puntos siguientes:</span><span class="sxs-lookup"><span data-stu-id="11f10-273">Note the following points:</span></span>


- <span data-ttu-id="11f10-274">El proveedor de tipo toma dos parámetros estáticos: `pattern`, el patrón, que es obligatorio, y `options`, las opciones, que son opcionales (porque se proporciona un valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="11f10-274">The type provider takes two static parameters: the `pattern`, which is mandatory, and the `options`, which are optional (because a default value is provided).</span></span>
<br />

- <span data-ttu-id="11f10-275">Después de proporcionar los argumentos estáticos, se crea una instancia de la expresión regular.</span><span class="sxs-lookup"><span data-stu-id="11f10-275">After the static arguments are supplied, you create an instance of the regular expression.</span></span> <span data-ttu-id="11f10-276">Esta instancia inicia una excepción si la Regex no es correcta, y se notifica el error a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="11f10-276">This instance will throw an exception if the Regex is malformed, and this error will be reported to users.</span></span>
<br />

- <span data-ttu-id="11f10-277">El tipo que se devolverá cuando se den los argumentos se define dentro de la devolución de llamada `DefineStaticParameters`.</span><span class="sxs-lookup"><span data-stu-id="11f10-277">Within the `DefineStaticParameters` callback, you define the type that will be returned after the arguments are supplied.</span></span>
<br />

- <span data-ttu-id="11f10-278">Este código establece `HideObjectMethods` en true para que el uso de IntelliSense siga estando optimizado.</span><span class="sxs-lookup"><span data-stu-id="11f10-278">This code sets `HideObjectMethods` to true so that the IntelliSense experience will remain streamlined.</span></span> <span data-ttu-id="11f10-279">Este atributo hace que los miembros `Equals`, `GetHashCode`, `Finalize` y `GetType` se supriman de listas de IntelliSense para un objeto proporcionado.</span><span class="sxs-lookup"><span data-stu-id="11f10-279">This attribute causes the `Equals`, `GetHashCode`, `Finalize`, and `GetType` members to be suppressed from IntelliSense lists for a provided object.</span></span>
<br />

- <span data-ttu-id="11f10-280">Se utiliza `obj` como tipo base del método, pero se utilizará un objeto `Regex` como representación en tiempo de ejecución de este tipo, como muestra el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="11f10-280">You use `obj` as the base type of the method, but you’ll use a `Regex` object as the runtime representation of this type, as the next example shows.</span></span>
<br />

- <span data-ttu-id="11f10-281">La llamada al constructor `Regex` inicia una excepción `System.ArgumentException` cuando una expresión regular no es válida.</span><span class="sxs-lookup"><span data-stu-id="11f10-281">The call to the `Regex` constructor throws a `System.ArgumentException` when a regular expression isn’t valid.</span></span> <span data-ttu-id="11f10-282">El compilador detecta esta excepción y envía un mensaje de error al usuario en tiempo de compilación o en el editor de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="11f10-282">The compiler catches this exception and reports an error message to the user at compile time or in the Visual Studio editor.</span></span> <span data-ttu-id="11f10-283">Esta excepción permite que las expresiones regulares se validen sin ejecutar una aplicación.</span><span class="sxs-lookup"><span data-stu-id="11f10-283">This exception enables regular expressions to be validated without running an application.</span></span>
<br />

<span data-ttu-id="11f10-284">El tipo definido anteriormente todavía no es útil porque no contiene propiedades ni métodos significativos.</span><span class="sxs-lookup"><span data-stu-id="11f10-284">The type defined above isn't useful yet because it doesn’t contain any meaningful methods or properties.</span></span> <span data-ttu-id="11f10-285">En primer lugar, agregue un método `IsMatch` estático:</span><span class="sxs-lookup"><span data-stu-id="11f10-285">First, add a static `IsMatch` method:</span></span>

```fsharp
let isMatch = ProvidedMethod(
methodName = "IsMatch", 
parameters = [ProvidedParameter("input", typeof<string>)], 
returnType = typeof<bool>, 
IsStaticMethod = true,
InvokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>) 

isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string." 
ty.AddMember isMatch
```

<span data-ttu-id="11f10-286">El código anterior define un método `IsMatch`, que toma una cadena como entrada y devuelve un valor `bool`.</span><span class="sxs-lookup"><span data-stu-id="11f10-286">The previous code defines a method `IsMatch`, which takes a string as input and returns a `bool`.</span></span> <span data-ttu-id="11f10-287">La única parte difícil es el uso del argumento `args` dentro de la definición de la función `InvokeCode`.</span><span class="sxs-lookup"><span data-stu-id="11f10-287">The only tricky part is the use of the `args` argument within the `InvokeCode` definition.</span></span> <span data-ttu-id="11f10-288">En este ejemplo, `args` es una lista de expresiones de código delimitadas que representa los argumentos de este método.</span><span class="sxs-lookup"><span data-stu-id="11f10-288">In this example, `args` is a list of quotations that represents the arguments to this method.</span></span> <span data-ttu-id="11f10-289">Si el método es un método de instancia, el primer argumento representa el argumento `this`.</span><span class="sxs-lookup"><span data-stu-id="11f10-289">If the method is an instance method, the first argument represents the `this` argument.</span></span> <span data-ttu-id="11f10-290">Sin embargo, para un método estático, los argumentos son simplemente los argumentos explícitos para el método.</span><span class="sxs-lookup"><span data-stu-id="11f10-290">However, for a static method, the arguments are all just the explicit arguments to the method.</span></span> <span data-ttu-id="11f10-291">Observe que el tipo del valor de la expresión de código delimitada debe coincidir con el tipo del valor devuelto especificado (en este caso, `bool`).</span><span class="sxs-lookup"><span data-stu-id="11f10-291">Note that the type of the quoted value should match the specified return type (in this case, `bool`).</span></span> <span data-ttu-id="11f10-292">Observe también que este código utiliza el método `AddXmlDoc` para asegurarse de que el método proporcionado también tiene documentación útil, que se puede proporcionar con IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="11f10-292">Also note that this code uses the `AddXmlDoc` method to make sure that the provided method also has useful documentation, which you can supply through IntelliSense.</span></span>

<span data-ttu-id="11f10-293">A continuación, agregue un método de instancia Match.</span><span class="sxs-lookup"><span data-stu-id="11f10-293">Next, add an instance Match method.</span></span> <span data-ttu-id="11f10-294">Sin embargo, este método debe devolver un valor de un tipo `Match` proporcionado, de modo que se pueda tener acceso a los grupos de manera fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="11f10-294">However, this method should return a value of a provided `Match` type so that the groups can be accessed in a strongly typed fashion.</span></span> <span data-ttu-id="11f10-295">Por ello, primero se declara el tipo `Match`.</span><span class="sxs-lookup"><span data-stu-id="11f10-295">Thus, you first declare the `Match` type.</span></span> <span data-ttu-id="11f10-296">Como este tipo depende del patrón que se proporcionó como argumento estático, este tipo debe estar anidado dentro de la definición de tipos parametrizados:</span><span class="sxs-lookup"><span data-stu-id="11f10-296">Because this type depends on the pattern that was supplied as a static argument, this type must be nested within the parameterized type definition:</span></span>

```fsharp
let matchTy = ProvidedTypeDefinition(
"MatchType", 
baseType = Some baseTy, 
HideObjectMethods = true)

ty.AddMember matchTy
```

<span data-ttu-id="11f10-297">A continuación, se agrega una propiedad al tipo Match de cada grupo.</span><span class="sxs-lookup"><span data-stu-id="11f10-297">You then add one property to the Match type for each group.</span></span> <span data-ttu-id="11f10-298">En tiempo de ejecución, una coincidencia se representa como un valor `System.Text.RegularExpressions.Match`, por lo que la expresión de código delimitada que define la propiedad debe utilizar la propiedad indizada `System.Text.RegularExpressions.Match.Groups` para obtener el grupo pertinente.</span><span class="sxs-lookup"><span data-stu-id="11f10-298">At runtime, a match is represented as a `System.Text.RegularExpressions.Match` value, so the quotation that defines the property must use the `System.Text.RegularExpressions.Match.Groups` indexed property to get the relevant group.</span></span>

```fsharp
for group in r.GetGroupNames() do
// Ignore the group named 0, which represents all input.
if group <> "0" then
let prop = ProvidedProperty(
propertyName = group, 
propertyType = typeof<Group>, 
GetterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
matchTy.AddMember prop
```

<span data-ttu-id="11f10-299">Una vez más, observe que se está agregando la documentación XML a la propiedad proporcionada.</span><span class="sxs-lookup"><span data-stu-id="11f10-299">Again, note that you’re adding XML documentation to the provided property.</span></span> <span data-ttu-id="11f10-300">También observe que una propiedad puede leerse si se proporciona una función `GetterCode` y puede escribirse si se proporciona una función `SetterCode`, por lo que la propiedad resultante es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="11f10-300">Also note that a property can be read if a `GetterCode` function is provided, and the property can be written if a `SetterCode` function is provided, so the resulting property is read only.</span></span>

<span data-ttu-id="11f10-301">Now you can create an instance method that returns a value of this `Match` type:</span><span class="sxs-lookup"><span data-stu-id="11f10-301">Now you can create an instance method that returns a value of this `Match` type:</span></span>

```fsharp
let matchMethod = 
ProvidedMethod(
methodName = "Match", 
parameters = [ProvidedParameter("input", typeof<string>)], 
returnType = matchTy, 
InvokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)
matchMeth.AddXmlDoc "Searches the specified input string for the first ocurrence of this regular expression" 

ty.AddMember matchMeth
```

<span data-ttu-id="11f10-302">Como está creando un método de instancia, `args.[0]` representa la instancia de `RegexTyped` en la que se está llamando al método y `args.[1]` es el argumento de entrada.</span><span class="sxs-lookup"><span data-stu-id="11f10-302">Because you are creating an instance method, `args.[0]` represents the `RegexTyped` instance on which the method is being called, and `args.[1]` is the input argument.</span></span>

<span data-ttu-id="11f10-303">Finalmente, proporcione un constructor para que se puedan crear instancias del tipo proporcionado.</span><span class="sxs-lookup"><span data-stu-id="11f10-303">Finally, provide a constructor so that instances of the provided type can be created.</span></span>

```fsharp
let ctor = ProvidedConstructor(
parameters = [], 
InvokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)
ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

<span data-ttu-id="11f10-304">El constructor simplemente borra para la creación de una Regex estándar de .NET, a la cual también se le aplica la conversión box en un objeto porque `obj` es el borrado del tipo proporcionado.</span><span class="sxs-lookup"><span data-stu-id="11f10-304">The constructor merely erases to the creation of a standard .NET Regex instance, which is again boxed to an object because `obj` is the erasure of the provided type.</span></span> <span data-ttu-id="11f10-305">Con ese cambio, el uso de la API de ejemplo especificada previamente en el tema funciona como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="11f10-305">With that change, the sample API usage that specified earlier in the topic works as expected.</span></span> <span data-ttu-id="11f10-306">A continuación se muestra la versión final del código completo:</span><span class="sxs-lookup"><span data-stu-id="11f10-306">The following code is complete and final:</span></span>

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



let ty = ProvidedTypeDefinition(
thisAssembly, 
rootNamespace, 
typeName, 
baseType = Some baseTy)

ty.AddXmlDoc "A strongly typed interface to the regular expression '%s'"

// Provide strongly typed version of Regex.IsMatch static method.
let isMatch = ProvidedMethod(
methodName = "IsMatch", 
parameters = [ProvidedParameter("input", typeof<string>)], 
returnType = typeof<bool>, 
IsStaticMethod = true,
InvokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>) 

isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string"

ty.AddMember isMatch

// Provided type for matches
// Again, erase to obj even though the representation will always be a Match
let matchTy = ProvidedTypeDefinition(
"MatchType", 
baseType = Some baseTy, 
HideObjectMethods = true)

// Nest the match type within parameterized Regex type.
ty.AddMember matchTy

// Add group properties to match type
for group in r.GetGroupNames() do
// Ignore the group named 0, which represents all input.
if group <> "0" then
let prop = ProvidedProperty(
propertyName = group, 
propertyType = typeof<Group>, 
GetterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
matchTy.AddMember(prop)

// Provide strongly typed version of Regex.Match instance method.
let matchMeth = ProvidedMethod(
methodName = "Match", 
parameters = [ProvidedParameter("input", typeof<string>)], 
returnType = matchTy, 
InvokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)
matchMeth.AddXmlDoc "Searches the specified input string for the first occurence of this regular expression"

ty.AddMember matchMeth

// Declare a constructor.
let ctor = ProvidedConstructor(
parameters = [], 
InvokeCode = fun args -> <@@ Regex(pattern) :> obj @@>)

// Add documentation to the constructor.
ctor.AddXmlDoc "Initializes a regular expression instance"

ty.AddMember ctor

ty
| _ -> failwith "unexpected parameter values")) 

do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

`Key Lessons`

<span data-ttu-id="11f10-307">En esta sección se ha explicado cómo crear un proveedor de tipos que opera con sus parámetros estáticos.</span><span class="sxs-lookup"><span data-stu-id="11f10-307">This section explained how to create a type provider that operates on its static parameters.</span></span> <span data-ttu-id="11f10-308">El proveedor comprueba el parámetro estático y proporciona operaciones basadas en su valor.</span><span class="sxs-lookup"><span data-stu-id="11f10-308">The provider checks the static parameter and provides operations based on its value.</span></span>


## <a name="a-type-provider-that-is-backed-by-local-data"></a><span data-ttu-id="11f10-309">Un proveedor de tipo que está respaldado por datos locales</span><span class="sxs-lookup"><span data-stu-id="11f10-309">A Type Provider That Is Backed By Local Data</span></span>
<span data-ttu-id="11f10-310">Con frecuencia se requiere que los proveedores de tipos muestren API basadas no solo en parámetros estáticos sino también en información procedente de sistemas locales o remotos.</span><span class="sxs-lookup"><span data-stu-id="11f10-310">Frequently you might want type providers to present APIs based on not only static parameters but also information from local or remote systems.</span></span> <span data-ttu-id="11f10-311">Esta sección trata sobre los proveedores de tipo basados en datos locales, como los archivos de datos locales.</span><span class="sxs-lookup"><span data-stu-id="11f10-311">This section discusses type providers that are based on local data, such as local data files.</span></span>


### <a name="simple-csv-file-provider"></a><span data-ttu-id="11f10-312">Proveedor simple de archivos CSV</span><span class="sxs-lookup"><span data-stu-id="11f10-312">Simple CSV File Provider</span></span>
<span data-ttu-id="11f10-313">Como ejemplo sencillo, considere un proveedor de tipo para tener acceso a datos científicos con el formato de valores separados por comas (CSV).</span><span class="sxs-lookup"><span data-stu-id="11f10-313">As a simple example, consider a type provider for accessing scientific data in Comma Separated Value (CSV) format.</span></span> <span data-ttu-id="11f10-314">En esta sección se supone que los archivos CSV contienen una fila de encabezado seguida de datos en coma flotante, como se muestra en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="11f10-314">This section assumes that the CSV files contain a header row followed by floating point data, as the following table illustrates:</span></span>



|<span data-ttu-id="11f10-315">Distancia (metros)</span><span class="sxs-lookup"><span data-stu-id="11f10-315">Distance (meter)</span></span>|<span data-ttu-id="11f10-316">Tiempo (segundos)</span><span class="sxs-lookup"><span data-stu-id="11f10-316">Time (second)</span></span>|
|----------------|-------------|
|<span data-ttu-id="11f10-317">50.0</span><span class="sxs-lookup"><span data-stu-id="11f10-317">50.0</span></span>|<span data-ttu-id="11f10-318">3.7</span><span class="sxs-lookup"><span data-stu-id="11f10-318">3.7</span></span>|
|<span data-ttu-id="11f10-319">100.0</span><span class="sxs-lookup"><span data-stu-id="11f10-319">100.0</span></span>|<span data-ttu-id="11f10-320">5.2</span><span class="sxs-lookup"><span data-stu-id="11f10-320">5.2</span></span>|
|<span data-ttu-id="11f10-321">150.0</span><span class="sxs-lookup"><span data-stu-id="11f10-321">150.0</span></span>|<span data-ttu-id="11f10-322">6.4</span><span class="sxs-lookup"><span data-stu-id="11f10-322">6.4</span></span>|
<span data-ttu-id="11f10-323">En esta sección se muestra cómo proporcionar un tipo que se puede usar para obtener filas con una propiedad `Distance` de tipo `float<meter>` y una propiedad `Time` de tipo `float<second>`.</span><span class="sxs-lookup"><span data-stu-id="11f10-323">This section shows how to provide a type that you can use to get rows with a `Distance` property of type `float<meter>` and a `Time` property of type `float<second>`.</span></span> <span data-ttu-id="11f10-324">Para simplificar, se realizan las suposiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="11f10-324">For simplicity, the following assumptions are made:</span></span>


- <span data-ttu-id="11f10-325">Los nombres de encabezado son unidades de medida o tener el formato "Nombre (unidad)" y no contienen comas.</span><span class="sxs-lookup"><span data-stu-id="11f10-325">Header names are either unit-less or have the form "Name (unit)" and don't contain commas.</span></span>
<br />

- <span data-ttu-id="11f10-326">Las unidades son todas las unidades al sistema internacional (SI) como el [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames (módulo de F #)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) módulo define.</span><span class="sxs-lookup"><span data-stu-id="11f10-326">Units are all Systeme International (SI) units as the [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames Module (F#)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) module defines.</span></span>
<br />

- <span data-ttu-id="11f10-327">Las unidades son todas simples (por ejemplo, metro) en lugar de compuestas (por ejemplo, metros por segundo).</span><span class="sxs-lookup"><span data-stu-id="11f10-327">Units are all simple (for example, meter) rather than compound (for example, meter/second).</span></span>
<br />

- <span data-ttu-id="11f10-328">Todas las columnas contienen datos en coma flotante.</span><span class="sxs-lookup"><span data-stu-id="11f10-328">All columns contain floating point data.</span></span>
<br />

<span data-ttu-id="11f10-329">Un proveedor más completo relajaría estas restricciones.</span><span class="sxs-lookup"><span data-stu-id="11f10-329">A more complete provider would loosen these restrictions.</span></span>

<span data-ttu-id="11f10-330">De nuevo, el primer paso es considerar qué aspecto debe tener la API.</span><span class="sxs-lookup"><span data-stu-id="11f10-330">Again the first step is to consider how the API should look.</span></span> <span data-ttu-id="11f10-331">Dado un archivo `info.csv` con el contenido de la tabla anterior (en formato separado por comas), los usuarios del proveedor deberían poder escribir un código similar al del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="11f10-331">Given an `info.csv` file with the contents from the previous table (in comma-separated format), users of the provider should be able to write code that resembles the following example:</span></span>

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

<span data-ttu-id="11f10-332">En este caso, el compilador debería convertir estas llamadas en algo similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="11f10-332">In this case, the compiler should convert these calls into something like the following example:</span></span>

```fsharp
let info = new MiniCsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

<span data-ttu-id="11f10-333">La conversión óptima requerirá que el proveedor de tipo defina un tipo `CsvFile` real en el ensamblado del proveedor de tipo.</span><span class="sxs-lookup"><span data-stu-id="11f10-333">The optimal translation will require the type provider to define a real `CsvFile` type in the type provider's assembly.</span></span> <span data-ttu-id="11f10-334">Los proveedores de tipos a veces se basan en algunos tipos y métodos auxiliares para contener la lógica importante.</span><span class="sxs-lookup"><span data-stu-id="11f10-334">Type providers often rely on a few helper types and methods to wrap important logic.</span></span> <span data-ttu-id="11f10-335">Dado que las medidas se borran en tiempo de ejecución, se puede utilizar `float[]` como el tipo borrado para una fila.</span><span class="sxs-lookup"><span data-stu-id="11f10-335">Because measures are erased at runtime, you can use a `float[]` as the erased type for a row.</span></span> <span data-ttu-id="11f10-336">El compilador considerará que las distintas columnas contienen distintos tipos de medidas.</span><span class="sxs-lookup"><span data-stu-id="11f10-336">The compiler will treat different columns as having different measure types.</span></span> <span data-ttu-id="11f10-337">Por ejemplo, la primera columna de nuestro ejemplo contiene el tipo `float<meter>` y la segunda contiene `float<second>`.</span><span class="sxs-lookup"><span data-stu-id="11f10-337">For example, the first column in our example has type `float<meter>`, and the second has `float<second>`.</span></span> <span data-ttu-id="11f10-338">Sin embargo, la representación borrada puede seguir siendo bastante simple.</span><span class="sxs-lookup"><span data-stu-id="11f10-338">However, the erased representation can remain quite simple.</span></span>

<span data-ttu-id="11f10-339">En el ejemplo de código siguiente se muestra el núcleo de la implementación.</span><span class="sxs-lookup"><span data-stu-id="11f10-339">The following code shows the core of the implementation.</span></span>

```fsharp
// Simple type wrapping CSV data
type CsvFile(filename) =
// Cache the sequence of all data lines (all lines but the first)
let data = 
seq { for line in File.ReadAllLines(filename) |> Seq.skip 1 do
yield line.Split(',') |> Array.map float }
|> Seq.cache
member __.Data = data

[<TypeProvider>]
type public MiniCsvProvider(cfg:TypeProviderConfig) as this =
inherit TypeProviderForNamespaces()

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

let prop = ProvidedProperty(fieldName, fieldTy, 
GetterCode = fun [row] -> <@@ (%%row:float[]).[i] @@>)

// Add metadata that defines the property's location in the referenced file.
prop.AddDefinitionLocation(1, headers.[i].Index + 1, filename)
rowTy.AddMember(prop) 

// Define the provided type, erasing to CsvFile.
let ty = ProvidedTypeDefinition(asm, ns, tyName, Some(typeof<CsvFile>))

// Add a parameterless constructor that loads the file that was used to define the schema.
let ctor0 = ProvidedConstructor([], 
InvokeCode = fun [] -> <@@ CsvFile(resolvedFilename) @@>)
ty.AddMember ctor0

// Add a constructor that takes the file name to load.
let ctor1 = ProvidedConstructor([ProvidedParameter("filename", typeof<string>)], 
InvokeCode = fun [filename] -> <@@ CsvFile(%%filename) @@>)
ty.AddMember ctor1

// Add a more strongly typed Data property, which uses the existing property at runtime.
let prop = ProvidedProperty("Data", typedefof<seq<_>>.MakeGenericType(rowTy), 
GetterCode = fun [csvFile] -> <@@ (%%csvFile:CsvFile).Data @@>)
ty.AddMember prop

// Add the row type as a nested type.
ty.AddMember rowTy
ty)

// Add the type to the namespace.
do this.AddNamespace(ns, [csvTy])
```

<span data-ttu-id="11f10-340">Tenga en cuenta las siguientes observaciones sobre la implementación:</span><span class="sxs-lookup"><span data-stu-id="11f10-340">Note the following points about the implementation:</span></span>


- <span data-ttu-id="11f10-341">Los constructores sobrecargados permiten leer el archivo original o uno que tenga un esquema idéntico.</span><span class="sxs-lookup"><span data-stu-id="11f10-341">Overloaded constructors allow either the original file or one that has an identical schema to be read.</span></span> <span data-ttu-id="11f10-342">Este patrón es habitual al escribir un proveedor de tipos para orígenes de datos locales o remotos, y además permite el uso de un archivo local como plantilla para los datos remotos.</span><span class="sxs-lookup"><span data-stu-id="11f10-342">This pattern is common when you write a type provider for local or remote data sources, and this pattern allows a local file to be used as the template for remote data.</span></span>
<br />  <span data-ttu-id="11f10-343">Puede usar el [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) valor que se pasa al constructor del proveedor de tipo para resolver los nombres de archivo relativos.</span><span class="sxs-lookup"><span data-stu-id="11f10-343">You can use the [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) value that’s passed in to the type provider constructor to resolve relative file names.</span></span>
<br />

- <span data-ttu-id="11f10-344">Se puede utilizar el método `AddDefinitionLocation` para definir la ubicación de las propiedades proporcionadas.</span><span class="sxs-lookup"><span data-stu-id="11f10-344">You can use the `AddDefinitionLocation` method to define the location of the provided properties.</span></span> <span data-ttu-id="11f10-345">Por lo tanto, si utiliza `Go To Definition` en una propiedad proporcionada, el archivo CSV se abrirá en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="11f10-345">Therefore, if you use `Go To Definition` on a provided property, the CSV file will open in Visual Studio.</span></span>
<br />

- <span data-ttu-id="11f10-346">Se puede utilizar el tipo `ProvidedMeasureBuilder` para buscar las unidades del SI y generar los tipos `float<_>` pertinentes.</span><span class="sxs-lookup"><span data-stu-id="11f10-346">You can use the `ProvidedMeasureBuilder` type to look up the SI units and to generate the relevant `float<_>` types.</span></span>
<br />

`Key Lessons`

<span data-ttu-id="11f10-347">En esta sección se ha explicado cómo crear un proveedor de tipos para un origen de datos local con un esquema simple que está contenido en el propio origen de datos.</span><span class="sxs-lookup"><span data-stu-id="11f10-347">This section explained how to create a type provider for a local data source with a simple schema that's contained in the data source itself.</span></span>


## <a name="going-further"></a><span data-ttu-id="11f10-348">Ampliar conocimientos</span><span class="sxs-lookup"><span data-stu-id="11f10-348">Going Further</span></span>
<span data-ttu-id="11f10-349">En las secciones siguientes se incluyen sugerencias para ampliar conocimientos sobre el tema.</span><span class="sxs-lookup"><span data-stu-id="11f10-349">The following sections include suggestions for further study.</span></span>


### <a name="a-look-at-the-compiled-code-for-erased-types"></a><span data-ttu-id="11f10-350">Un vistazo al código compilado de los tipos borrados</span><span class="sxs-lookup"><span data-stu-id="11f10-350">A Look at the Compiled Code for Erased Types</span></span>
<span data-ttu-id="11f10-351">Para tener una idea de cómo se corresponde el uso del proveedor de tipo con el código emitido, revise la función siguiente mediante el proveedor `HelloWorldTypeProvider` utilizado anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="11f10-351">To give you some idea of how the use of the type provider corresponds to the code that's emitted, look at the following function by using the `HelloWorldTypeProvider` that's used earlier in this topic.</span></span>

```fsharp
let function1 () = 
let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
obj1.InstanceProperty
```

<span data-ttu-id="11f10-352">A continuación se muestra una imagen del código resultante descompilado mediante ildasm.exe:</span><span class="sxs-lookup"><span data-stu-id="11f10-352">Here’s an image of the resulting code decompiled by using ildasm.exe:</span></span>

```
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

<span data-ttu-id="11f10-353">Como muestra el ejemplo, se han borrado todas las menciones del tipo `Type1` y la propiedad `InstanceProperty`, y quedan solo las operaciones para los tipos de tiempo de ejecución relacionados.</span><span class="sxs-lookup"><span data-stu-id="11f10-353">As the example shows, all mentions of the type `Type1` and the `InstanceProperty` property have been erased, leaving only operations on the runtime types involved.</span></span>


### <a name="design-and-naming-conventions-for-type-providers"></a><span data-ttu-id="11f10-354">Diseño y convenciones de nomenclatura para los proveedores de tipos</span><span class="sxs-lookup"><span data-stu-id="11f10-354">Design and Naming Conventions for Type Providers</span></span>
<span data-ttu-id="11f10-355">Respete las convenciones siguientes al crear proveedores de tipos.</span><span class="sxs-lookup"><span data-stu-id="11f10-355">Observe the following conventions when authoring type providers.</span></span>


- `Providers for Connectivity Protocols`
<br />  <span data-ttu-id="11f10-356">Normalmente, los nombres de la mayoría de los archivos DLL de los proveedores para protocolos de conectividad para datos y servicios, como OData o conexiones SQL, deben terminar por `TypeProvider` o `TypeProviders`.</span><span class="sxs-lookup"><span data-stu-id="11f10-356">In general, names of most provider DLLs for data and service connectivity protocols, such as OData or SQL connections, should end in `TypeProvider` or `TypeProviders`.</span></span> <span data-ttu-id="11f10-357">Por ejemplo, utilice un nombre de DLL similar a la siguiente cadena:</span><span class="sxs-lookup"><span data-stu-id="11f10-357">For example, use a DLL name that resembles the following string:</span></span>
<br />

```
  Fabrikam.Management.BasicTypeProviders.dll
```

  <span data-ttu-id="11f10-358">Asegúrese de que los tipos proporcionados son miembros del espacio de nombres correspondiente e indican el protocolo de conexión que se ha implementado:</span><span class="sxs-lookup"><span data-stu-id="11f10-358">Ensure that your provided types are members of the corresponding namespace, and indicate the connectivity protocol that you implemented:</span></span>
<br />

```
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

- `Utility Providers for General Coding`
<br />  <span data-ttu-id="11f10-359">Para un proveedor de tipos de utilidad, como el de las expresiones regulares, el proveedor de tipos puede ser parte de una biblioteca base, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="11f10-359">For a utility type provider such as that for regular expressions, the type provider may be part of a base library, as the following example shows:</span></span>
<br />

```fsharp
  #r "Fabrikam.Core.Text.Utilities.dll"
```

  <span data-ttu-id="11f10-360">En este caso, el tipo proporcionado aparecería en un punto adecuado según las convenciones normales de diseño de .NET:</span><span class="sxs-lookup"><span data-stu-id="11f10-360">In this case, the provided type would appear at an appropriate point according to normal .NET design conventions:</span></span>
<br />

```fsharp
  open Fabrikam.Core.Text.RegexTyped
  
  let regex = new RegexTyped<"a+b+a+b+">()
```

- `Singleton Data Sources`
<br />  <span data-ttu-id="11f10-361">Algunos proveedores de tipos se conectan a un único origen de datos dedicado y solo proporcionan datos.</span><span class="sxs-lookup"><span data-stu-id="11f10-361">Some type providers connect to a single dedicated data source and provide only data.</span></span> <span data-ttu-id="11f10-362">En este caso, se debería quitar el sufijo `TypeProvider` y utilizar las convenciones normales de nomenclatura de .NET:</span><span class="sxs-lookup"><span data-stu-id="11f10-362">In this case, you should drop the `TypeProvider` suffix and use normal conventions for .NET naming:</span></span>
<br />

```fsharp
  #r "Fabrikam.Data.Freebase.dll"
  
  let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

  <span data-ttu-id="11f10-363">Para obtener más información, vea la convención de diseño `GetConnection` que se describe más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="11f10-363">For more information, see the `GetConnection` design convention that's described later in this topic.</span></span>
<br />


### <a name="design-patterns-for-type-providers"></a><span data-ttu-id="11f10-364">Patrones de diseño para los proveedores de tipos</span><span class="sxs-lookup"><span data-stu-id="11f10-364">Design Patterns for Type Providers</span></span>
<span data-ttu-id="11f10-365">En las secciones siguientes se describen los patrones de diseño que se pueden usar cuando se crean los proveedores de tipo.</span><span class="sxs-lookup"><span data-stu-id="11f10-365">The following sections describe design patterns you can use when authoring type providers.</span></span>


#### <a name="the-getconnection-design-pattern"></a><span data-ttu-id="11f10-366">El patrón de diseño GetConnection</span><span class="sxs-lookup"><span data-stu-id="11f10-366">The GetConnection Design Pattern</span></span>
<span data-ttu-id="11f10-367">La mayoría de los proveedores de tipo se deben escribir para que usen el patrón `GetConnection` utilizado por los proveedores de tipo en FSharp.Data.TypeProviders.dll, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="11f10-367">Most type providers should be written to use the `GetConnection` pattern that's used by the type providers in FSharp.Data.TypeProviders.dll, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a><span data-ttu-id="11f10-368">Proveedores de tipos respaldados por datos y servicios remotos</span><span class="sxs-lookup"><span data-stu-id="11f10-368">Type Providers Backed By Remote Data and Services</span></span>
<span data-ttu-id="11f10-369">Antes de crear un proveedor de tipos respaldado por datos y servicios remotos, se deben tener en cuenta varios problemas que son inherentes a la programación conectada.</span><span class="sxs-lookup"><span data-stu-id="11f10-369">Before you create a type provider that's backed by remote data and services, you must consider a range of issues that are inherent in connected programming.</span></span> <span data-ttu-id="11f10-370">Estos problemas incluyen los siguientes aspectos:</span><span class="sxs-lookup"><span data-stu-id="11f10-370">These issues include the following considerations:</span></span>


- <span data-ttu-id="11f10-371">Asignación de esquemas</span><span class="sxs-lookup"><span data-stu-id="11f10-371">schema mapping</span></span>
<br />

- <span data-ttu-id="11f10-372">Vida e invalidación en presencia de un cambio de esquema</span><span class="sxs-lookup"><span data-stu-id="11f10-372">liveness and invalidation in the presence of schema change</span></span>
<br />

- <span data-ttu-id="11f10-373">Almacenamiento en caché de esquemas</span><span class="sxs-lookup"><span data-stu-id="11f10-373">schema caching</span></span>
<br />

- <span data-ttu-id="11f10-374">Implementaciones asíncronas de operaciones de acceso a datos</span><span class="sxs-lookup"><span data-stu-id="11f10-374">asynchronous implementations of data access operations</span></span>
<br />

- <span data-ttu-id="11f10-375">Consultas admitidas, incluidas las consultas LINQ</span><span class="sxs-lookup"><span data-stu-id="11f10-375">supporting queries, including LINQ queries</span></span>
<br />

- <span data-ttu-id="11f10-376">Credenciales y autenticación</span><span class="sxs-lookup"><span data-stu-id="11f10-376">credentials and authentication</span></span>
<br />

<span data-ttu-id="11f10-377">Este tema no profundiza en estos problemas.</span><span class="sxs-lookup"><span data-stu-id="11f10-377">This topic doesn't explore these issues further.</span></span>


### <a name="additional-authoring-techniques"></a><span data-ttu-id="11f10-378">Técnicas adicionales de creación</span><span class="sxs-lookup"><span data-stu-id="11f10-378">Additional Authoring Techniques</span></span>
<span data-ttu-id="11f10-379">Al escribir sus propios proveedores de tipos, quizá quiera utilizar las siguientes técnicas adicionales.</span><span class="sxs-lookup"><span data-stu-id="11f10-379">When you write your own type providers, you might want to use the following additional techniques.</span></span>


- `Creating Types and Members On-Demand`
<br />  <span data-ttu-id="11f10-380">La API de ProvidedType tiene versiones demoradas de AddMember.</span><span class="sxs-lookup"><span data-stu-id="11f10-380">The ProvidedType API has delayed versions of AddMember.</span></span>
<br />

```fsharp
  type ProvidedType =
  member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
  member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

  <span data-ttu-id="11f10-381">Estas versiones se utilizan para crear espacios de tipos a petición.</span><span class="sxs-lookup"><span data-stu-id="11f10-381">These versions are used to create on-demand spaces of types.</span></span>
<br />

- `Providing Array, ByRef, and Pointer types`
<br />  <span data-ttu-id="11f10-382">Los miembros proporcionados (cuyas signaturas incluyen tipos de matriz, tipos byref y creaciones de instancias de tipos genéricos) se crean mediante el uso de los métodos `MakeArrayType`, `MakePointerType` y `MakeGenericType` normales en cualquier instancia de System.Type, incluyendo `ProvidedTypeDefinitions`.</span><span class="sxs-lookup"><span data-stu-id="11f10-382">You make provided members (whose signatures include array types, byref types, and instantiations of generic types) by using the normal `MakeArrayType`, `MakePointerType`, and `MakeGenericType` on any instance of System.Type, including `ProvidedTypeDefinitions`.</span></span>
<br />

- `Providing Unit of Measure Annotations`
<br />  <span data-ttu-id="11f10-383">La API ProvidedTypes proporciona aplicaciones auxiliares para proporcionar anotaciones de medidas.</span><span class="sxs-lookup"><span data-stu-id="11f10-383">The ProvidedTypes API provides helpers for providing measure annotations.</span></span> <span data-ttu-id="11f10-384">Por ejemplo, para proporcionar el tipo `float<kg>`, utilice el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="11f10-384">For example, to provide the type `float<kg>`, use the following code:</span></span>
<br />

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  <span data-ttu-id="11f10-385">Para proporcionar el tipo `Nullable<decimal<kg/m^2>>`, utilice el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="11f10-385">To provide the type `Nullable<decimal<kg/m^2>>`, use the following code:</span></span>
<br />

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

- `Accessing Project-Local or Script-Local Resources`
<br />  <span data-ttu-id="11f10-386">A cada instancia de un proveedor de tipo se le puede asignar un valor `TypeProviderConfig` durante la construcción.</span><span class="sxs-lookup"><span data-stu-id="11f10-386">Each instance of a type provider can be given a `TypeProviderConfig` value during construction.</span></span> <span data-ttu-id="11f10-387">Este valor contiene la "carpeta de resolución" para el proveedor (es decir, la carpeta del proyecto para la compilación o el directorio que contiene un script), la lista de ensamblados a los que se hace referencia y otra información.</span><span class="sxs-lookup"><span data-stu-id="11f10-387">This value contains the "resolution folder" for the provider (that is, the project folder for the compilation or the directory that contains a script), the list of referenced assemblies, and other information.</span></span>
<br />

- `Invalidation`
<br />  <span data-ttu-id="11f10-388">Los proveedores pueden generar señales de invalidación para notificar al servicio del lenguaje F# que las suposiciones acerca del esquema pueden haber cambiado.</span><span class="sxs-lookup"><span data-stu-id="11f10-388">Providers can raise invalidation signals to notify the F# language service that the schema assumptions may have changed.</span></span> <span data-ttu-id="11f10-389">Cuando se produce la invalidación, se repite una comprobación de tipos si el proveedor se hospeda en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="11f10-389">When invalidation occurs, a typecheck is redone if the provider is being hosted in Visual Studio.</span></span> <span data-ttu-id="11f10-390">Esta señal se omite cuando el proveedor se hospeda en F# Interactive o por el compilador de F# (fsc.exe).</span><span class="sxs-lookup"><span data-stu-id="11f10-390">This signal will be ignored when the provider is hosted in F# Interactive or by the F# Compiler (fsc.exe).</span></span>
<br />

- `Caching Schema Information`
<br />  <span data-ttu-id="11f10-391">A menudo los proveedores deben almacenar en memoria caché el acceso a la información del esquema.</span><span class="sxs-lookup"><span data-stu-id="11f10-391">Providers must often cache access to schema information.</span></span> <span data-ttu-id="11f10-392">Los datos almacenados en caché deben almacenarse utilizando un nombre de archivo que se da como parámetro estático o como datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="11f10-392">The cached data should be stored by using a file name that's given as a static parameter or as user data.</span></span> <span data-ttu-id="11f10-393">Un ejemplo de almacenamiento en caché de esquema es el parámetro `LocalSchemaFile` en los proveedores de tipos del ensamblado `FSharp.Data.TypeProviders`.</span><span class="sxs-lookup"><span data-stu-id="11f10-393">An example of schema caching is the `LocalSchemaFile` parameter in the type providers in the `FSharp.Data.TypeProviders` assembly.</span></span> <span data-ttu-id="11f10-394">En la implementación de estos proveedores, este parámetro estático ordena al proveedor de tipo que use la información del esquema del archivo local especificado en lugar de acceder al origen de datos en la red.</span><span class="sxs-lookup"><span data-stu-id="11f10-394">In the implementation of these providers, this static parameter directs the type provider to use the schema information in the specified local file instead of accessing the data source over the network.</span></span> <span data-ttu-id="11f10-395">Para utilizar la información del esquema almacenada en caché, también se debe establecer el parámetro estático `ForceUpdate` en `false`.</span><span class="sxs-lookup"><span data-stu-id="11f10-395">To use cached schema information, you must also set the static parameter `ForceUpdate` to `false`.</span></span> <span data-ttu-id="11f10-396">Se puede usar una técnica similar para permitir el acceso a datos en línea y sin conexión.</span><span class="sxs-lookup"><span data-stu-id="11f10-396">You could use a similar technique to enable online and offline data access.</span></span>
<br />

- `Backing Assembly`
<br />  <span data-ttu-id="11f10-397">Cuando se compila un archivo .dll o .exe, el archivo .dll de respaldo para los tipos generados se vincula estáticamente al ensamblado resultante.</span><span class="sxs-lookup"><span data-stu-id="11f10-397">When you compile a .dll or .exe file, the backing .dll file for generated types is statically linked into the resulting assembly.</span></span> <span data-ttu-id="11f10-398">Este vínculo se crea copiando las definiciones de tipos del lenguaje intermedio (IL) y cualquier recurso administrado del ensamblado de respaldo al ensamblado final.</span><span class="sxs-lookup"><span data-stu-id="11f10-398">This link is created by copying the Intermediate Language (IL) type definitions and any managed resources from the backing assembly into the final assembly.</span></span> <span data-ttu-id="11f10-399">Cuando se usa F# Interactive, el archivo .dll de respaldo no se copia, sino que se carga directamente en el proceso de F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="11f10-399">When you use F# Interactive, the backing .dll file isn't copied and is instead loaded directly into the F# Interactive process.</span></span>
<br />

- `Exceptions and Diagnostics from Type Providers`
<br />  <span data-ttu-id="11f10-400">Todos los usos de todos los miembros de los tipos proporcionados pueden producir excepciones.</span><span class="sxs-lookup"><span data-stu-id="11f10-400">All uses of all members from provided types may throw exceptions.</span></span> <span data-ttu-id="11f10-401">En todos los casos, si un proveedor de tipo genera una excepción, el compilador host atribuye el error a un proveedor de tipo específico.</span><span class="sxs-lookup"><span data-stu-id="11f10-401">In all cases, if a type provider throws an exception, the host compiler attributes the error to a specific type provider.</span></span>
<br />
  - <span data-ttu-id="11f10-402">Las excepciones de proveedores de tipos nunca deben producir errores internos del compilador.</span><span class="sxs-lookup"><span data-stu-id="11f10-402">Type provider exceptions should never result in internal compiler errors.</span></span>
<br />

  - <span data-ttu-id="11f10-403">Los proveedores de tipos no pueden notificar advertencias.</span><span class="sxs-lookup"><span data-stu-id="11f10-403">Type providers can't report warnings.</span></span>
<br />

  - <span data-ttu-id="11f10-404">Cuando un proveedor de tipos se hospeda en el compilador de F#, un entorno de desarrollo de F# o F# Interactive, se detectan todas las excepciones de ese proveedor.</span><span class="sxs-lookup"><span data-stu-id="11f10-404">When a type provider is hosted in the F# compiler, an F# development environment, or F# Interactive, all exceptions from that provider are caught.</span></span> <span data-ttu-id="11f10-405">La propiedad Message es siempre el texto del error y no aparece ningún seguimiento de pila.</span><span class="sxs-lookup"><span data-stu-id="11f10-405">The Message property is always the error text, and no stack trace appears.</span></span> <span data-ttu-id="11f10-406">Si se va a producir una excepción, se pueden producir los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="11f10-406">If you’re going to throw an exception, you can throw the following examples:</span></span>
<br />
    - `System.NotSupportedException`
<br />

    - `System.IO.IOException`
<br />

    - `System.Exception`
<br />


#### <a name="providing-generated-types"></a><span data-ttu-id="11f10-407">Proporcionar tipos generados</span><span class="sxs-lookup"><span data-stu-id="11f10-407">Providing Generated Types</span></span>
<span data-ttu-id="11f10-408">Hasta ahora, en este documento se ha explicado cómo proporcionar tipos borrados.</span><span class="sxs-lookup"><span data-stu-id="11f10-408">So far, this document has explained how provide erased types.</span></span> <span data-ttu-id="11f10-409">También se puede usar el mecanismo de proveedores de tipos de F# para proporcionar tipos generados, que se agregan como definiciones de tipo reales de .NET en el programa del usuario.</span><span class="sxs-lookup"><span data-stu-id="11f10-409">You can also use the type provider mechanism in F# to provide generated types, which are added as real .NET type definitions into the users' program.</span></span> <span data-ttu-id="11f10-410">Se debe hacer referencia a los tipos proporcionados generados mediante una definición de tipo.</span><span class="sxs-lookup"><span data-stu-id="11f10-410">You must refer to generated provided types by using a type definition.</span></span>

```fsharp
open Microsoft.FSharp.TypeProviders 

type Service = ODataService<" https://services.odata.org/Northwind/Northwind.svc/">
```

<span data-ttu-id="11f10-411">El código auxiliar ProvidedTypes-0.2 que forma parte de la versión 3.0 de F# solo tiene compatibilidad limitada para proporcionar tipos generados.</span><span class="sxs-lookup"><span data-stu-id="11f10-411">The ProvidedTypes-0.2 helper code that is part of the F# 3.0 release has only limited support for providing generated types.</span></span> <span data-ttu-id="11f10-412">Los enunciados siguientes deben ser verdaderos para una definición de un tipo generado:</span><span class="sxs-lookup"><span data-stu-id="11f10-412">The following statements must be true for a generated type definition:</span></span>


- <span data-ttu-id="11f10-413">IsErased debe estar establecido en `false`.</span><span class="sxs-lookup"><span data-stu-id="11f10-413">IsErased must be set to `false`.</span></span>
<br />

- <span data-ttu-id="11f10-414">El proveedor debe tener un ensamblado que tenga un archivo .dll de respaldo real de .NET con un archivo .dll coincidente en el disco.</span><span class="sxs-lookup"><span data-stu-id="11f10-414">The provider must have an assembly that has an actual backing .NET .dll file with a matching .dll file on disk.</span></span>
<br />

<span data-ttu-id="11f10-415">También se debe llamar a `ConvertToGenerated` en un tipo proporcionado raíz cuyos tipos anidados forman un conjunto cerrado de tipos generados.</span><span class="sxs-lookup"><span data-stu-id="11f10-415">You must also call `ConvertToGenerated` on a root provided type whose nested types form a closed set of generated types.</span></span> <span data-ttu-id="11f10-416">Esta llamada emite la definición de tipo proporcionado especificada y sus definiciones de tipo anidadas en un ensamblado y ajusta la propiedad `Assembly` de todas las definiciones de tipo proporcionado para que devuelva ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="11f10-416">This call emits the given provided type definition and its nested type definitions into an assembly and adjusts the `Assembly` property of all provided type definitions to return that assembly.</span></span> <span data-ttu-id="11f10-417">El ensamblado se emite solo cuando se tiene acceso a la propiedad Assembly en el tipo raíz por primera vez.</span><span class="sxs-lookup"><span data-stu-id="11f10-417">The assembly is emitted only when the Assembly property on the root type is accessed for the first time.</span></span> <span data-ttu-id="11f10-418">El compilador de F# del host tiene acceso a esta propiedad cuando procesa una declaración de tipos generativa para el tipo.</span><span class="sxs-lookup"><span data-stu-id="11f10-418">The host F# compiler does access this property when it processes a generative type declaration for the type.</span></span>


## <a name="rules-and-limitations"></a><span data-ttu-id="11f10-419">Reglas y limitaciones</span><span class="sxs-lookup"><span data-stu-id="11f10-419">Rules and Limitations</span></span>
<span data-ttu-id="11f10-420">Al escribir proveedores de tipos, tenga en cuenta las siguientes reglas y limitaciones.</span><span class="sxs-lookup"><span data-stu-id="11f10-420">When you write type providers, keep the following rules and limitations in mind.</span></span>


- `Provided types must be reachable.`
<br />  <span data-ttu-id="11f10-421">Debe tenerse acceso a todos los tipos proporcionados desde los tipos no anidados.</span><span class="sxs-lookup"><span data-stu-id="11f10-421">All provided types should be reachable from the non-nested types.</span></span> <span data-ttu-id="11f10-422">Los tipos no anidados se proporcionan en la llamada al constructor `TypeProviderForNamespaces` o en una llamada a `AddNamespace`.</span><span class="sxs-lookup"><span data-stu-id="11f10-422">The non-nested types are given in the call to the `TypeProviderForNamespaces` constructor or a call to `AddNamespace`.</span></span> <span data-ttu-id="11f10-423">Por ejemplo, si el proveedor proporciona un tipo `StaticClass.P : T`, debe asegurarse de que T es un tipo no anidado o está anidado debajo de uno.</span><span class="sxs-lookup"><span data-stu-id="11f10-423">For example, if the provider provides a type `StaticClass.P : T`, you must ensure that T is either a non-nested type or nested under one.</span></span>
<br />  <span data-ttu-id="11f10-424">Por ejemplo, algunos proveedores tienen una clase estática como `DataTypes` que contiene estos tipos `T1, T2, T3, ...`.</span><span class="sxs-lookup"><span data-stu-id="11f10-424">For example, some providers have a static class such as `DataTypes` that contain these `T1, T2, T3, ...` types.</span></span> <span data-ttu-id="11f10-425">De lo contrario, el error indica que se ha encontrado una referencia al tipo T en el ensamblado A, pero el tipo no se encuentra en ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="11f10-425">Otherwise, the error says that a reference to type T in assembly A was found, but the type couldn't be found in that assembly.</span></span> <span data-ttu-id="11f10-426">Si aparece este error, compruebe que se puede obtener acceso a todos los subtipos desde los tipos del proveedor.</span><span class="sxs-lookup"><span data-stu-id="11f10-426">If this error appears, verify that all your subtypes can be reached from the provider types.</span></span> <span data-ttu-id="11f10-427">Nota: Estos `T1, T2, T3...` tipos se conocen como el *sobre la marcha* tipos.</span><span class="sxs-lookup"><span data-stu-id="11f10-427">Note: These `T1, T2, T3...` types are referred to as the *on-the-fly* types.</span></span> <span data-ttu-id="11f10-428">Recuerde colocarlos en un espacio de nombres accesible o en un tipo primario.</span><span class="sxs-lookup"><span data-stu-id="11f10-428">Remember to put them in an accessible namespace or a parent type.</span></span>
<br />

- `Limitations of the Type Provider Mechanism`
<br />  <span data-ttu-id="11f10-429">El mecanismo de proveedores de tipos de F# tiene las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="11f10-429">The type provider mechanism in F# has the following limitations:</span></span>
<br />
  - <span data-ttu-id="11f10-430">La infraestructura subyacente para los proveedores de tipos de F# no admite tipos genéricos proporcionados ni métodos genéricos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="11f10-430">The underlying infrastructure for type providers in F# doesn't support provided generic types or provided generic methods.</span></span>
<br />

  - <span data-ttu-id="11f10-431">El mecanismo no admite tipos anidados con parámetros estáticos.</span><span class="sxs-lookup"><span data-stu-id="11f10-431">The mechanism doesn't support nested types with static parameters.</span></span>
<br />

- `Limitations of the ProvidedTypes Support Code`
<br />  <span data-ttu-id="11f10-432">El código de soporte de `ProvidedTypes` tiene las siguientes reglas y limitaciones:</span><span class="sxs-lookup"><span data-stu-id="11f10-432">The `ProvidedTypes` support code has the following rules and limitations:</span></span>
<br />
  1. <span data-ttu-id="11f10-433">Las propiedades proporcionadas con captadores y establecedores indizados no están implementadas.</span><span class="sxs-lookup"><span data-stu-id="11f10-433">Provided properties with indexed getters and setters aren't implemented.</span></span>
<br />

  2. <span data-ttu-id="11f10-434">Los eventos proporcionados no están implementados.</span><span class="sxs-lookup"><span data-stu-id="11f10-434">Provided events aren't implemented.</span></span>
<br />

  3. <span data-ttu-id="11f10-435">Los tipos proporcionados y los objetos de información únicamente deben utilizarse para el mecanismo de proveedores de tipos de F#.</span><span class="sxs-lookup"><span data-stu-id="11f10-435">The provided types and information objects should be used only for the type provider mechanism in F#.</span></span> <span data-ttu-id="11f10-436">No son utilizables de forma más general como objetos System.Type.</span><span class="sxs-lookup"><span data-stu-id="11f10-436">They aren't more generally usable as System.Type objects.</span></span>
<br />

  4. <span data-ttu-id="11f10-437">Las construcciones que se pueden usar en las expresiones de código delimitadas que definen las implementaciones de los métodos tienen varias limitaciones.</span><span class="sxs-lookup"><span data-stu-id="11f10-437">The constructs that you can use in quotations that define method implementations have several limitations.</span></span> <span data-ttu-id="11f10-438">Puede hacer referencia al código fuente para ProvidedTypes -*versión* para ver qué construcciones son compatibles en expresiones de código delimitadas.</span><span class="sxs-lookup"><span data-stu-id="11f10-438">You can refer to the source code for ProvidedTypes-*Version* to see which constructs are supported in quotations.</span></span>
<br />

- `Type providers must generate output assemblies that are .dll files, not .exe files.`
<br />


## <a name="development-tips"></a><span data-ttu-id="11f10-439">Sugerencias de desarrollo</span><span class="sxs-lookup"><span data-stu-id="11f10-439">Development Tips</span></span>
<span data-ttu-id="11f10-440">Puede que le resulten útiles las sugerencias siguientes durante el proceso de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="11f10-440">You might find the following tips helpful during the development process.</span></span>


- <span data-ttu-id="11f10-441">`Run Two Instances of Visual Studio.` Puede desarrollar el proveedor de tipo en una instancia y probarlo en la otra porque el IDE de prueba tomará un bloqueo en el archivo .dll que evita que el proveedor de tipo que se va a volver a generar.</span><span class="sxs-lookup"><span data-stu-id="11f10-441">`Run Two Instances of Visual Studio.` You can develop the type provider in one instance and test the provider in the other because the test IDE will take a lock on the .dll file that prevents the type provider from being rebuilt.</span></span> <span data-ttu-id="11f10-442">Por lo tanto, debe cerrar la segunda instancia de Visual Studio mientras se compila el proveedor en la primera y, a continuación, debe volver a abrir la segunda instancia después de compilar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="11f10-442">Thus, you must close the second instance of Visual Studio while the provider is built in the first instance, and then you must reopen the second instance after the provider is built.</span></span>
<br />

- <span data-ttu-id="11f10-443">`Debug type providers by using invocations of fsc.exe.` Puede invocar proveedores de tipos mediante el uso de las siguientes herramientas:</span><span class="sxs-lookup"><span data-stu-id="11f10-443">`Debug type providers by using invocations of fsc.exe.` You can invoke type providers by using the following tools:</span></span>
<br />
  - <span data-ttu-id="11f10-444">fsc.exe (el compilador de línea de comandos de F#)</span><span class="sxs-lookup"><span data-stu-id="11f10-444">fsc.exe (The F# command line compiler)</span></span>
<br />

  - <span data-ttu-id="11f10-445">fsi.exe (el compilador interactivo de F#)</span><span class="sxs-lookup"><span data-stu-id="11f10-445">fsi.exe (The F# Interactive compiler)</span></span>
<br />

  - <span data-ttu-id="11f10-446">devenv.exe (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="11f10-446">devenv.exe (Visual Studio)</span></span>
<br />

  <span data-ttu-id="11f10-447">A menudo, lo más fácil es depurar los proveedores de tipo mediante fsc.exe en un archivo de script de prueba (por ejemplo, script.fsx).</span><span class="sxs-lookup"><span data-stu-id="11f10-447">You can often debug type providers most easily by using fsc.exe on a test script file (for example, script.fsx).</span></span> <span data-ttu-id="11f10-448">Puede iniciar un depurador desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="11f10-448">You can launch a debugger from a command prompt.</span></span>
<br />

```
  devenv /debugexe fsc.exe script.fsx
```

  <span data-ttu-id="11f10-449">Puede usar print-to-stdout como registro.</span><span class="sxs-lookup"><span data-stu-id="11f10-449">You can use print-to-stdout logging.</span></span>
<br />


## <a name="see-also"></a><span data-ttu-id="11f10-450">Vea también</span><span class="sxs-lookup"><span data-stu-id="11f10-450">See Also</span></span>
[<span data-ttu-id="11f10-451">Proveedores de tipos</span><span class="sxs-lookup"><span data-stu-id="11f10-451">Type Providers</span></span>](index.md)
