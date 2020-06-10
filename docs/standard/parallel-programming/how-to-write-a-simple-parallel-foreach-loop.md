---
title: Escribir un programa en paralelo sencillo con Parallel.ForEach
description: En este artículo, aprenderá a habilitar el paralelismo de datos en .NET. Escriba un bucle Parallel.ForEach para cualquier origen de datos IEnumerable o IEnumerable<T>.
ms.date: 02/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
ms.openlocfilehash: 59c8710a8e3fc878b2ceded8595f7f3319d4c953
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2020
ms.locfileid: "84447204"
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a><span data-ttu-id="f40aa-104">Procedimiento Escribir un bucle Parallel.ForEach sencillo</span><span class="sxs-lookup"><span data-stu-id="f40aa-104">How to: Write a simple Parallel.ForEach loop</span></span>

<span data-ttu-id="f40aa-105">Este ejemplo muestra cómo utilizar un bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> para habilitar el paralelismo de datos sobre cualquier origen de datos <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f40aa-105">This example shows how to use a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop to enable data parallelism over any <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> data source.</span></span>

> [!NOTE]
> <span data-ttu-id="f40aa-106">En esta documentación, se utilizan expresiones lambda para definir delegados en PLINQ.</span><span class="sxs-lookup"><span data-stu-id="f40aa-106">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="f40aa-107">Si no está familiarizado con las expresiones lambda de C# o Visual Basic, vea [Expresiones lambda en PLINQ y TPL](lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="f40aa-107">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda expressions in PLINQ and TPL](lambda-expressions-in-plinq-and-tpl.md).</span></span>

## <a name="example"></a><span data-ttu-id="f40aa-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f40aa-108">Example</span></span>

<span data-ttu-id="f40aa-109">En este ejemplo se supone que tiene varios archivos .jpg en la carpeta *C:\Usuarios\Público\Imágenes\Imágenes de muestra* y crea una subcarpeta con el nombre *Modificadas*.</span><span class="sxs-lookup"><span data-stu-id="f40aa-109">This example assumes you have several .jpg files in a *C:\Users\Public\Pictures\Sample Pictures* folder and creates a new sub-folder named *Modified*.</span></span> <span data-ttu-id="f40aa-110">Al ejecutar el ejemplo, gira cada imagen .jpg de *Imágenes de muestra* y la guarda en *Modificadas*.</span><span class="sxs-lookup"><span data-stu-id="f40aa-110">When you run the example, it rotates each .jpg image in *Sample Pictures* and saves it to *Modified*.</span></span> <span data-ttu-id="f40aa-111">Puede modificar las dos rutas de acceso según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f40aa-111">You can modify the two paths as necessary.</span></span>

[!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
[!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]

<span data-ttu-id="f40aa-112">Un bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> funciona como un bucle <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f40aa-112">A <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop works like a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop.</span></span> <span data-ttu-id="f40aa-113">El bucle divide la colección de origen y programa el trabajo en varios subprocesos en función del entorno del sistema.</span><span class="sxs-lookup"><span data-stu-id="f40aa-113">The loop partitions the source collection and schedules the work on multiple threads based on the system environment.</span></span> <span data-ttu-id="f40aa-114">Mientras más procesadores haya en el sistema, más rápido se ejecutará el método paralelo.</span><span class="sxs-lookup"><span data-stu-id="f40aa-114">The more processors on the system, the faster the parallel method runs.</span></span> <span data-ttu-id="f40aa-115">Para algunas colecciones de origen, un bucle secuencial puede ser más rápido, dependiendo del tamaño del origen y del tipo de trabajo que realiza el bucle.</span><span class="sxs-lookup"><span data-stu-id="f40aa-115">For some source collections, a sequential loop may be faster, depending on the size of the source and the kind of work the loop performs.</span></span> <span data-ttu-id="f40aa-116">Para más información sobre el rendimiento, vea [Problemas potenciales en el paralelismo de datos y tareas](potential-pitfalls-in-data-and-task-parallelism.md).</span><span class="sxs-lookup"><span data-stu-id="f40aa-116">For more information about performance, see [Potential pitfalls in data and task parallelism](potential-pitfalls-in-data-and-task-parallelism.md).</span></span>

<span data-ttu-id="f40aa-117">Para obtener más información sobre los bucles paralelos, vea [Procedimiento para escribir un bucle Parallel.For sencillo](how-to-write-a-simple-parallel-for-loop.md).</span><span class="sxs-lookup"><span data-stu-id="f40aa-117">For more information about parallel loops, see [How to: Write a simple Parallel.For loop](how-to-write-a-simple-parallel-for-loop.md).</span></span>

<span data-ttu-id="f40aa-118">Para usar <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> con una colección no genérica, puede usar el método de extensión <xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType> para convertir la colección en una colección genérica, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f40aa-118">To use <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> with a non-generic collection, you can use the <xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType> extension method to convert the collection to a generic collection, as shown in the following example:</span></span>

[!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
[!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]

<span data-ttu-id="f40aa-119">También puede utilizar Parallel LINQ (PLINQ) para paralelizar el procesamiento de orígenes de datos <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="f40aa-119">You can also use Parallel LINQ (PLINQ) to parallelize processing of <xref:System.Collections.Generic.IEnumerable%601> data sources.</span></span> <span data-ttu-id="f40aa-120">PLINQ permite usar la sintaxis de consulta declarativa para expresar el comportamiento del bucle.</span><span class="sxs-lookup"><span data-stu-id="f40aa-120">PLINQ enables you to use declarative query syntax to express the loop behavior.</span></span> <span data-ttu-id="f40aa-121">Para más información, consulte [Parallel LINQ (PLINQ)](introduction-to-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="f40aa-121">For more information, see [Parallel LINQ (PLINQ)](introduction-to-plinq.md).</span></span>

## <a name="compile-and-run-the-code"></a><span data-ttu-id="f40aa-122">Compilación y ejecución del código</span><span class="sxs-lookup"><span data-stu-id="f40aa-122">Compile and run the code</span></span>

<span data-ttu-id="f40aa-123">Puede compilar el código como una aplicación de consola de .NET Framework o como una aplicación de consola de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f40aa-123">You can compile the code as a console application for .NET Framework or as a console application for .NET Core.</span></span>

<span data-ttu-id="f40aa-124">En Visual Studio, hay plantillas de aplicación de consola de Visual Basic y C# para Windows Desktop y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f40aa-124">In Visual Studio, there are Visual Basic and C# console application templates for Windows Desktop and .NET Core.</span></span>

<span data-ttu-id="f40aa-125">Desde la línea de comandos, puede usar la CLI de .NET Core y sus comandos (por ejemplo, `dotnet new console` o `dotnet new console -lang vb`). También puede crear el archivo y usar el compilador de línea de comandos para una aplicación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f40aa-125">From the command line, you can use either the .NET Core CLI commands (for example, `dotnet new console` or `dotnet new console -lang vb`), or you can create the file and use the command-line compiler for a .NET Framework application.</span></span>

<span data-ttu-id="f40aa-126">Para un proyecto de .NET Core, debe hacer referencia al paquete NuGet **System.Drawing.Common**.</span><span class="sxs-lookup"><span data-stu-id="f40aa-126">For a .NET Core project, you must reference the **System.Drawing.Common** NuGet package.</span></span> <span data-ttu-id="f40aa-127">En Visual Studio, use el Administrador de paquetes de NuGet para instalar el paquete.</span><span class="sxs-lookup"><span data-stu-id="f40aa-127">In Visual Studio, use the NuGet Package Manager to install the package.</span></span> <span data-ttu-id="f40aa-128">Si lo prefiere, puede agregar una referencia al paquete en su archivo \*.csproj o \*.vbproj:</span><span class="sxs-lookup"><span data-stu-id="f40aa-128">Alternatively, you can add a reference to the package in your \*.csproj or \*.vbproj file:</span></span>

```xml
<ItemGroup>
     <PackageReference Include="System.Drawing.Common" Version="4.5.1" />
</ItemGroup>
```

<span data-ttu-id="f40aa-129">Para ejecutar una aplicación de consola .NET Core desde la línea de comandos, use `dotnet run` desde la carpeta que contenga la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f40aa-129">To run a .NET Core console application from the command line, use `dotnet run` from the folder that contains your application.</span></span>

<span data-ttu-id="f40aa-130">Para ejecutar la aplicación de consola desde Visual Studio, presione **F5**.</span><span class="sxs-lookup"><span data-stu-id="f40aa-130">To run your console application from Visual Studio, press **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f40aa-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="f40aa-131">See also</span></span>

- [<span data-ttu-id="f40aa-132">Paralelismo de datos (biblioteca TPL)</span><span class="sxs-lookup"><span data-stu-id="f40aa-132">Data parallelism</span></span>](data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="f40aa-133">Programación en paralelo en .NET</span><span class="sxs-lookup"><span data-stu-id="f40aa-133">Parallel programming</span></span>](index.md)
- [<span data-ttu-id="f40aa-134">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="f40aa-134">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
