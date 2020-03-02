---
title: Escribir un programa en paralelo sencillo con Parallel.ForEach
ms.date: 02/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
ms.openlocfilehash: 02b94b673dc4468e68a1dadd83aab0e3bfcfaa16
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160305"
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a><span data-ttu-id="aaa8a-102">Procedimiento Escribir un bucle Parallel.ForEach sencillo</span><span class="sxs-lookup"><span data-stu-id="aaa8a-102">How to: Write a simple Parallel.ForEach loop</span></span>

<span data-ttu-id="aaa8a-103">Este ejemplo muestra cómo utilizar un bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> para habilitar el paralelismo de datos sobre cualquier origen de datos <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-103">This example shows how to use a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop to enable data parallelism over any <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> data source.</span></span>

> [!NOTE]
> <span data-ttu-id="aaa8a-104">En esta documentación, se utilizan expresiones lambda para definir delegados en PLINQ.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="aaa8a-105">Si no está familiarizado con las expresiones lambda de C# o Visual Basic, vea [Expresiones lambda en PLINQ y TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="aaa8a-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>

## <a name="example"></a><span data-ttu-id="aaa8a-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aaa8a-106">Example</span></span>

<span data-ttu-id="aaa8a-107">En este ejemplo se supone que tiene varios archivos .jpg en la carpeta *C:\Usuarios\Público\Imágenes\Imágenes de muestra* y crea una subcarpeta con el nombre *Modificadas*.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-107">This example assumes you have several .jpg files in a *C:\Users\Public\Pictures\Sample Pictures* folder and creates a new sub-folder named *Modified*.</span></span> <span data-ttu-id="aaa8a-108">Al ejecutar el ejemplo, gira cada imagen .jpg de *Imágenes de muestra* y la guarda en *Modificadas*.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-108">When you run the example, it rotates each .jpg image in *Sample Pictures* and saves it to *Modified*.</span></span> <span data-ttu-id="aaa8a-109">Puede modificar las dos rutas de acceso según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-109">You can modify the two paths as necessary.</span></span>

[!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
[!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]

<span data-ttu-id="aaa8a-110">Un bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> funciona como un bucle <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-110">A <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop works like a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop.</span></span> <span data-ttu-id="aaa8a-111">El bucle divide la colección de origen y programa el trabajo en varios subprocesos en función del entorno del sistema.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-111">The loop partitions the source collection and schedules the work on multiple threads based on the system environment.</span></span> <span data-ttu-id="aaa8a-112">Mientras más procesadores haya en el sistema, más rápido se ejecutará el método paralelo.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-112">The more processors on the system, the faster the parallel method runs.</span></span> <span data-ttu-id="aaa8a-113">Para algunas colecciones de origen, un bucle secuencial puede ser más rápido, dependiendo del tamaño del origen y del tipo de trabajo que realiza el bucle.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-113">For some source collections, a sequential loop may be faster, depending on the size of the source and the kind of work the loop performs.</span></span> <span data-ttu-id="aaa8a-114">Para más información sobre el rendimiento, vea [Problemas potenciales en el paralelismo de datos y tareas](potential-pitfalls-in-data-and-task-parallelism.md).</span><span class="sxs-lookup"><span data-stu-id="aaa8a-114">For more information about performance, see [Potential pitfalls in data and task parallelism](potential-pitfalls-in-data-and-task-parallelism.md).</span></span>

<span data-ttu-id="aaa8a-115">Para obtener más información sobre los bucles paralelos, vea [Procedimiento para escribir un bucle Parallel.For sencillo](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).</span><span class="sxs-lookup"><span data-stu-id="aaa8a-115">For more information about parallel loops, see [How to: Write a simple Parallel.For loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).</span></span>

<span data-ttu-id="aaa8a-116">Para usar <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> con una colección no genérica, puede usar el método de extensión <xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType> para convertir la colección en una colección genérica, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aaa8a-116">To use <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> with a non-generic collection, you can use the <xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType> extension method to convert the collection to a generic collection, as shown in the following example:</span></span>

[!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
[!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]

<span data-ttu-id="aaa8a-117">También puede utilizar Parallel LINQ (PLINQ) para paralelizar el procesamiento de orígenes de datos <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-117">You can also use Parallel LINQ (PLINQ) to parallelize processing of <xref:System.Collections.Generic.IEnumerable%601> data sources.</span></span> <span data-ttu-id="aaa8a-118">PLINQ permite usar la sintaxis de consulta declarativa para expresar el comportamiento del bucle.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-118">PLINQ enables you to use declarative query syntax to express the loop behavior.</span></span> <span data-ttu-id="aaa8a-119">Para más información, consulte [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="aaa8a-119">For more information, see [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span></span>

## <a name="compile-and-run-the-code"></a><span data-ttu-id="aaa8a-120">Compilación y ejecución del código</span><span class="sxs-lookup"><span data-stu-id="aaa8a-120">Compile and run the code</span></span>

<span data-ttu-id="aaa8a-121">Puede compilar el código como una aplicación de consola de .NET Framework o como una aplicación de consola de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-121">You can compile the code as a console application for .NET Framework or as a console application for .NET Core.</span></span>

<span data-ttu-id="aaa8a-122">En Visual Studio, hay plantillas de aplicación de consola de Visual Basic y C# para Windows Desktop y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-122">In Visual Studio, there are Visual Basic and C# console application templates for Windows Desktop and .NET Core.</span></span>

<span data-ttu-id="aaa8a-123">Desde la línea de comandos, puede usar la CLI de .NET Core y sus comandos (por ejemplo, `dotnet new console` o `dotnet new console -lang vb`). También puede crear el archivo y usar el compilador de línea de comandos para una aplicación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-123">From the command line, you can use either the .NET Core CLI commands (for example, `dotnet new console` or `dotnet new console -lang vb`), or you can create the file and use the command-line compiler for a .NET Framework application.</span></span>

<span data-ttu-id="aaa8a-124">Para un proyecto de .NET Core, debe hacer referencia al paquete NuGet **System.Drawing.Common**.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-124">For a .NET Core project, you must reference the **System.Drawing.Common** NuGet package.</span></span> <span data-ttu-id="aaa8a-125">En Visual Studio, use el Administrador de paquetes de NuGet para instalar el paquete.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-125">In Visual Studio, use the NuGet Package Manager to install the package.</span></span> <span data-ttu-id="aaa8a-126">Si lo prefiere, puede agregar una referencia al paquete en su archivo \*.csproj o \*.vbproj:</span><span class="sxs-lookup"><span data-stu-id="aaa8a-126">Alternatively, you can add a reference to the package in your \*.csproj or \*.vbproj file:</span></span>

```xml
<ItemGroup>
     <PackageReference Include="System.Drawing.Common" Version="4.5.1" />
</ItemGroup>
```

<span data-ttu-id="aaa8a-127">Para ejecutar una aplicación de consola .NET Core desde la línea de comandos, use `dotnet run` desde la carpeta que contenga la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-127">To run a .NET Core console application from the command line, use `dotnet run` from the folder that contains your application.</span></span>

<span data-ttu-id="aaa8a-128">Para ejecutar la aplicación de consola desde Visual Studio, presione **F5**.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-128">To run your console application from Visual Studio, press **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="aaa8a-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="aaa8a-129">See also</span></span>

- [<span data-ttu-id="aaa8a-130">Paralelismo de datos (biblioteca TPL)</span><span class="sxs-lookup"><span data-stu-id="aaa8a-130">Data parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="aaa8a-131">Programación en paralelo en .NET</span><span class="sxs-lookup"><span data-stu-id="aaa8a-131">Parallel programming</span></span>](../../../docs/standard/parallel-programming/index.md)
- [<span data-ttu-id="aaa8a-132">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="aaa8a-132">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
