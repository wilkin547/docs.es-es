---
title: "Reducción de dependencias de paquete con project.json"
description: Reduzca las dependencias de paquete al crear bibliotecas basadas en project.json.
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 916251e3-87f9-4eee-81ec-94076215e6fa
ms.workload: dotnetcore
ms.openlocfilehash: 858fc77d9652bfa59ed0bb3159260f40c76156a4
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="reducing-package-dependencies-with-projectjson"></a><span data-ttu-id="37231-104">Reducción de dependencias de paquete con project.json</span><span class="sxs-lookup"><span data-stu-id="37231-104">Reducing Package Dependencies with project.json</span></span>

<span data-ttu-id="37231-105">En este artículo se analiza todo lo que necesita saber sobre cómo reducir las dependencias de paquete cuando se crean bibliotecas `project.json`.</span><span class="sxs-lookup"><span data-stu-id="37231-105">This article covers what you need to know about reducing your package dependencies when authoring `project.json` libraries.</span></span> <span data-ttu-id="37231-106">Al final de este artículo, habrá aprendido a redactar la biblioteca de manera tal que solo use las dependencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="37231-106">By the end of this article, you will learn how to compose your library such that it only uses the dependencies it needs.</span></span> 

## <a name="why-its-important"></a><span data-ttu-id="37231-107">Por qué es importante</span><span class="sxs-lookup"><span data-stu-id="37231-107">Why it's Important</span></span>

<span data-ttu-id="37231-108">.NET Core es un producto que consta de paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="37231-108">.NET Core is a product made up of NuGet packages.</span></span>  <span data-ttu-id="37231-109">Un paquete esencial es el [metapaquete .NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library), que es un paquete NuGet que consta de otros paquetes.</span><span class="sxs-lookup"><span data-stu-id="37231-109">An essential package is the [.NETStandard.Library metapackage](https://www.nuget.org/packages/NETStandard.Library), which is a NuGet package composed of other packages.</span></span>  <span data-ttu-id="37231-110">Proporciona el conjunto de paquetes que se garantiza que funcionan con varias implementaciones de .NET, como .NET Framework, .NET Core y Xamarin/Mono.</span><span class="sxs-lookup"><span data-stu-id="37231-110">It provides you with the set of packages that are guaranteed to work on multiple .NET implementations, such as .NET Framework, .NET Core and Xamarin/Mono.</span></span>

<span data-ttu-id="37231-111">Sin embargo, hay muchas posibilidades de que la biblioteca no use cada uno de los paquetes que contiene.</span><span class="sxs-lookup"><span data-stu-id="37231-111">However, there's a good chance that your library won't use every single package it contains.</span></span>  <span data-ttu-id="37231-112">Cuando se crea una biblioteca y se la distribuye en NuGet, un procedimiento recomendado es "recortar" las dependencias para que solo queden los paquetes que realmente usa.</span><span class="sxs-lookup"><span data-stu-id="37231-112">When authoring a library and distributing it over NuGet, it's a best practice to "trim" your dependencies down to only the packages you actually use.</span></span>  <span data-ttu-id="37231-113">Esto da como resultado una superficie total menor de los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="37231-113">This results in a smaller overall footprint for NuGet packages.</span></span>

## <a name="how-to-do-it"></a><span data-ttu-id="37231-114">Cómo hacerlo</span><span class="sxs-lookup"><span data-stu-id="37231-114">How to do it</span></span>

<span data-ttu-id="37231-115">Actualmente, no hay ningún comando de `dotnet` oficial que recorte las referencias de paquete.</span><span class="sxs-lookup"><span data-stu-id="37231-115">Currently, there is no official `dotnet` command which trims package references.</span></span>  <span data-ttu-id="37231-116">En lugar de eso, deberá hacerlo de manera manual.</span><span class="sxs-lookup"><span data-stu-id="37231-116">Instead, you'll have to do it manually.</span></span>  <span data-ttu-id="37231-117">El proceso general tiene el aspecto siguiente:</span><span class="sxs-lookup"><span data-stu-id="37231-117">The general process looks like the following:</span></span>

1. <span data-ttu-id="37231-118">Haga referencia a `NETStandard.Library` versión `1.6.0` en una sección `dependencies` del `project.json`.</span><span class="sxs-lookup"><span data-stu-id="37231-118">Reference `NETStandard.Library` version `1.6.0` in a `dependencies` section of your `project.json`.</span></span>
2. <span data-ttu-id="37231-119">Restaure paquetes con `dotnet restore` ([vea la nota](#dotnet-restore-note)) desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="37231-119">Restore packages with `dotnet restore` ([see note](#dotnet-restore-note)) from the command line.</span></span>
3. <span data-ttu-id="37231-120">Revise el archivo `project.lock.json` y encuentre la sección `NETSTandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="37231-120">Inspect the `project.lock.json` file and find the `NETSTandard.Library` section.</span></span>  <span data-ttu-id="37231-121">Se encuentra cerca del comienzo del archivo.</span><span class="sxs-lookup"><span data-stu-id="37231-121">It's near the beginning of the file.</span></span>
4. <span data-ttu-id="37231-122">Copie todos los paquetes que aparecen en `dependencies`.</span><span class="sxs-lookup"><span data-stu-id="37231-122">Copy all of the listed packages under `dependencies`.</span></span>
5. <span data-ttu-id="37231-123">Quite la referencia a `.NETStandard.Library` y reemplácela por los paquetes copiados.</span><span class="sxs-lookup"><span data-stu-id="37231-123">Remove the `.NETStandard.Library` reference and replace it with the copied packages.</span></span>
6. <span data-ttu-id="37231-124">Quite las referencias a paquetes que no necesita.</span><span class="sxs-lookup"><span data-stu-id="37231-124">Remove references to packages you don't need.</span></span>


<span data-ttu-id="37231-125">Una de las siguientes formas le permite saber cuáles son los paquetes que no necesita:</span><span class="sxs-lookup"><span data-stu-id="37231-125">You can find out which packages you don't need by one of the following ways:</span></span>

1. <span data-ttu-id="37231-126">Prueba y error.</span><span class="sxs-lookup"><span data-stu-id="37231-126">Trial and error.</span></span>  <span data-ttu-id="37231-127">Esto implica quitar un paquete, realizar la restauración, ver si la biblioteca se compila y repetir este proceso.</span><span class="sxs-lookup"><span data-stu-id="37231-127">This involves removing a package, restoring, seeing if your library still compiles, and repeating this process.</span></span>
2. <span data-ttu-id="37231-128">Mediante el uso de una herramienta como [ILSpy](http://ilspy.net) o [.NET Reflector](http://www.red-gate.com/products/dotnet-development/reflector) para echar un vistazo a las referencias y ver las que realmente usa el código.</span><span class="sxs-lookup"><span data-stu-id="37231-128">Using a tool such as [ILSpy](http://ilspy.net) or [.NET Reflector](http://www.red-gate.com/products/dotnet-development/reflector) to peek at references to see what your code is actually using.</span></span>  <span data-ttu-id="37231-129">De ese modo, puede quitar los paquetes que no corresponden a los tipos que usa.</span><span class="sxs-lookup"><span data-stu-id="37231-129">You can then remove packages which don't correspond to types you're using.</span></span>

## <a name="example"></a><span data-ttu-id="37231-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37231-130">Example</span></span> 

<span data-ttu-id="37231-131">Imagine que escribió una biblioteca que brindó una funcionalidad adicional a los tipos de colección genéricos.</span><span class="sxs-lookup"><span data-stu-id="37231-131">Imagine that you wrote a library which provided additional functionality to generic collection types.</span></span>  <span data-ttu-id="37231-132">Dicha biblioteca debería depender de paquetes como `System.Collections`, pero probablemente no dependería para nada de paquetes tales como `System.Net.Http`.</span><span class="sxs-lookup"><span data-stu-id="37231-132">Such a library would need to depend on packages such as `System.Collections`, but may not at all depend on packages such as `System.Net.Http`.</span></span>  <span data-ttu-id="37231-133">Por lo tanto, sería bueno recortar las dependencias de paquete para que solo queden las que necesita esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="37231-133">As such, it would be good to trim package dependencies down to only what this library required!</span></span>

<span data-ttu-id="37231-134">Para recortar esta biblioteca, comience con el archivo `project.json` y agregue una referencia a `NETStandard.Library` versión `1.6.0`.</span><span class="sxs-lookup"><span data-stu-id="37231-134">To trim this library, you start with the `project.json` file and add a reference to `NETStandard.Library` version `1.6.0`.</span></span>

```json
{
    "version":"1.0.0",
    "dependencies":{
        "NETStandard.Library":"1.6.0"
    },
    "frameworks": {
        "netstandard1.0": {}
     }
}
```

<span data-ttu-id="37231-135">Luego, restaure los paquetes con `dotnet restore` ([vea la nota](#dotnet-restore-note)), revise el archivo `project.lock.json` y encuentre todos los paquetes restaurados para `NETSTandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="37231-135">Next, you restore packages with `dotnet restore` ([see note](#dotnet-restore-note)), inspect the `project.lock.json` file, and find all the packages restored for `NETSTandard.Library`.</span></span>

<span data-ttu-id="37231-136">Aquí puede ver el aspecto que tiene la sección correspondiente del archivo `project.lock.json` cuando se tiene como destino `netstandard1.0`:</span><span class="sxs-lookup"><span data-stu-id="37231-136">Here's what the relevant section in the `project.lock.json` file looks like when targeting `netstandard1.0`:</span></span>

```json
"NETStandard.Library/1.6.0":{
    "type": "package",
    "dependencies": {
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Diagnostics.Debug": "4.0.11",
        "System.Diagnostics.Tools": "4.0.1",
        "System.Globalization": "4.0.11",
        "System.IO": "4.1.0",
        "System.Linq": "4.1.0",
        "System.Net.Primitives": "4.0.11",
        "System.ObjectModel": "4.0.12",
        "System.Reflection": "4.1.0",
        "System.Reflection.Extensions": "4.0.1",
        "System.Reflection.Primitives": "4.0.1",
        "System.Resources.ResourceManager": "4.0.1",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Text.Encoding": "4.0.11",
        "System.Text.Encoding.Extensions": "4.0.11",
        "System.Text.RegularExpressions": "4.1.0",
        "System.Threading": "4.0.11",
        "System.Threading.Tasks": "4.0.11",
        "System.Xml.ReaderWriter": "4.0.11",
        "System.Xml.XDocument": "4.0.11"
    }
}
```

<span data-ttu-id="37231-137">A continuación, copie las referencias de paquete a la sección `dependencies` del archivo `project.json` de la biblioteca, reemplazando la referencia de `NETStandard.Library`:</span><span class="sxs-lookup"><span data-stu-id="37231-137">Next, copy over the package references into the `dependencies` section of the library's `project.json` file, replacing the `NETStandard.Library` reference:</span></span>

```json
{
    "version":"1.0.0",
    "dependencies":{
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Diagnostics.Debug": "4.0.11",
        "System.Diagnostics.Tools": "4.0.1",
        "System.Globalization": "4.0.11",
        "System.IO": "4.1.0",
        "System.Linq": "4.1.0",
        "System.Net.Primitives": "4.0.11",
        "System.ObjectModel": "4.0.12",
        "System.Reflection": "4.1.0",
        "System.Reflection.Extensions": "4.0.1",
        "System.Reflection.Primitives": "4.0.1",
        "System.Resources.ResourceManager": "4.0.1",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Text.Encoding": "4.0.11",
        "System.Text.Encoding.Extensions": "4.0.11",
        "System.Text.RegularExpressions": "4.1.0",
        "System.Threading": "4.0.11",
        "System.Threading.Tasks": "4.0.11",
        "System.Xml.ReaderWriter": "4.0.11",
        "System.Xml.XDocument": "4.0.11"
    },
    "frameworks":{
        "netstandard1.0": {}
    }
}
```

<span data-ttu-id="37231-138">Es una enorme cantidad de paquetes, muchos de los cuales en realidad no son necesarios para extender los tipos de colección.</span><span class="sxs-lookup"><span data-stu-id="37231-138">That's quite a lot of packages, many of which which certainly aren't necessary for extending collection types.</span></span>  <span data-ttu-id="37231-139">Puede quitar manualmente los paquetes o usar una herramienta como [ILSpy](http://ilspy.net) o [.NET Reflector](http://www.red-gate.com/products/dotnet-development/reflector) para identificar los paquetes que el código realmente usa.</span><span class="sxs-lookup"><span data-stu-id="37231-139">You can either remove packages manually or use a tool such as [ILSpy](http://ilspy.net) or [.NET Reflector](http://www.red-gate.com/products/dotnet-development/reflector) to identify which packages your code actually uses.</span></span>

<span data-ttu-id="37231-140">Aquí puede ver el aspecto que tendría un paquete recortado:</span><span class="sxs-lookup"><span data-stu-id="37231-140">Here's what a trimmed package could look like:</span></span>

```json
{
    "dependencies":{
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Linq": "4.1.0",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Runtime.Handles": "4.0.1",
        "System.Runtime.InteropServices": "4.1.0",
        "System.Runtime.InteropServices.RuntimeInformation": "4.0.0",
        "System.Threading.Tasks": "4.0.11"
    },
    "frameworks":{
        "netstandard1.0": {}
     }
}
```

<span data-ttu-id="37231-141">Ahora tiene una menor superficie que si hubiese dependido del metapaquete `NETStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="37231-141">Now, it has a smaller footprint than if it had depended on the `NETStandard.Library` metapackage.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]