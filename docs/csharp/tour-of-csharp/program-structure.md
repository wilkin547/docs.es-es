---
title: 'Estructura del programa de C#: un paseo por el lenguaje C#'
description: Conozca más acerca de los bloques de compilación básicos de un programa de C#.
ms.date: 08/10/2016
ms.assetid: 984f0314-507f-47a0-af56-9011243f5e65
ms.openlocfilehash: 5e095e71549ed3eec6c73e6a134fdb5a64fb63c0
ms.sourcegitcommit: 68a4b28242da50e1d25aab597c632767713a6f81
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2019
ms.locfileid: "74884389"
---
# <a name="program-structure"></a><span data-ttu-id="ed55b-103">Estructura del programa</span><span class="sxs-lookup"><span data-stu-id="ed55b-103">Program Structure</span></span>

<span data-ttu-id="ed55b-104">Los principales conceptos organizativos en C# son ***programas***, ***espacios de nombres***, ***tipos***, ***miembros*** y ***ensamblados***.</span><span class="sxs-lookup"><span data-stu-id="ed55b-104">The key organizational concepts in C# are ***programs***, ***namespaces***, ***types***, ***members***, and ***assemblies***.</span></span> <span data-ttu-id="ed55b-105">Los programas de C# constan de uno o más archivos de origen.</span><span class="sxs-lookup"><span data-stu-id="ed55b-105">C# programs consist of one or more source files.</span></span> <span data-ttu-id="ed55b-106">Los programas declaran tipos, que contienen miembros y pueden organizarse en espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="ed55b-106">Programs declare types, which contain members and can be organized into namespaces.</span></span> <span data-ttu-id="ed55b-107">Las clases e interfaces son ejemplos de tipos.</span><span class="sxs-lookup"><span data-stu-id="ed55b-107">Classes and interfaces are examples of types.</span></span> <span data-ttu-id="ed55b-108">Los campos, los métodos, las propiedades y los eventos son ejemplos de miembros.</span><span class="sxs-lookup"><span data-stu-id="ed55b-108">Fields, methods, properties, and events are examples of members.</span></span> <span data-ttu-id="ed55b-109">Cuando se compilan programas de C#, se empaquetan físicamente en ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ed55b-109">When C# programs are compiled, they are physically packaged into assemblies.</span></span> <span data-ttu-id="ed55b-110">Normalmente, los ensamblados tienen la extensión de archivo `.exe` o `.dll`, dependiendo de si implementan ***aplicaciones*** o ***bibliotecas***, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="ed55b-110">Assemblies typically have the file extension `.exe` or `.dll`, depending on whether they implement ***applications*** or ***libraries***, respectively.</span></span>

<span data-ttu-id="ed55b-111">En el ejemplo se declara una clase denominada `Stack` en un espacio de nombres llamado `Acme.Collections`:</span><span class="sxs-lookup"><span data-stu-id="ed55b-111">The example declares a class named `Stack` in a namespace called `Acme.Collections`:</span></span>

[!code-csharp[Stack](../../../samples/snippets/csharp/tour/program-structure/program.cs#L1-L34)]

<span data-ttu-id="ed55b-112">El nombre completo de esta clase es `Acme.Collections.Stack`.</span><span class="sxs-lookup"><span data-stu-id="ed55b-112">The fully qualified name of this class is `Acme.Collections.Stack`.</span></span> <span data-ttu-id="ed55b-113">La clase contiene varios miembros: un campo denominado `top`, dos métodos denominados `Push` y `Pop`, y una clase anidada denominada `Entry`.</span><span class="sxs-lookup"><span data-stu-id="ed55b-113">The class contains several members: a field named `top`, two methods named `Push` and `Pop`, and a nested class named `Entry`.</span></span> <span data-ttu-id="ed55b-114">La clase `Entry` contiene además tres miembros: un campo denominado `next`, un campo denominado `data` y un constructor.</span><span class="sxs-lookup"><span data-stu-id="ed55b-114">The `Entry` class further contains three members: a field named `next`, a field named `data`, and a constructor.</span></span> <span data-ttu-id="ed55b-115">Suponiendo que el código fuente del ejemplo se almacene en el archivo `acme.cs`, la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="ed55b-115">Assuming that the source code of the example is stored in the file `acme.cs`, the command line</span></span>

```console
csc /t:library acme.cs
```

<span data-ttu-id="ed55b-116">compila el ejemplo como una biblioteca (código sin un punto de entrada `Main` y genera un ensamblado denominado `acme.dll`.</span><span class="sxs-lookup"><span data-stu-id="ed55b-116">compiles the example as a library (code without a `Main` entry point) and produces an assembly named `acme.dll`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ed55b-117">Los ejemplos anteriores usan `csc` como el compilador C# de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="ed55b-117">The examples above use `csc` as the command line C# compiler.</span></span> <span data-ttu-id="ed55b-118">Este compilador es un ejecutable de Windows.</span><span class="sxs-lookup"><span data-stu-id="ed55b-118">This compiler is a Windows executable.</span></span> <span data-ttu-id="ed55b-119">Para usar C# en otras plataformas, debe emplear las herramientas de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ed55b-119">To use C# across other platforms, you should use the tools for .NET Core.</span></span> <span data-ttu-id="ed55b-120">El ecosistema .NET Core usa la CLI de `dotnet` para administrar las compilaciones de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="ed55b-120">The .NET Core ecosystem uses the `dotnet` CLI to manage command line builds.</span></span> <span data-ttu-id="ed55b-121">Esto incluye la administración de dependencias y la llamada al compilador de C#.</span><span class="sxs-lookup"><span data-stu-id="ed55b-121">This includes managing dependencies, and invoking the C# compiler.</span></span> <span data-ttu-id="ed55b-122">Consulte [este tutorial](../../core/tutorials/cli-create-console-app.md) para obtener una descripción completa de estas herramientas en las plataformas compatibles con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ed55b-122">See [this tutorial](../../core/tutorials/cli-create-console-app.md) for a full description of those tools on the platforms supported by .NET Core.</span></span>

<span data-ttu-id="ed55b-123">Los ensamblados contienen código ejecutable en forma de instrucciones de lenguaje intermedio (IL) e información simbólica en forma de metadatos.</span><span class="sxs-lookup"><span data-stu-id="ed55b-123">Assemblies contain executable code in the form of Intermediate Language (IL) instructions, and symbolic information in the form of metadata.</span></span> <span data-ttu-id="ed55b-124">Antes de ejecutarlo, el código de IL de un ensamblado se convierte automáticamente en código específico del procesador mediante el compilador de Just in Time (JIT) de .NET Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="ed55b-124">Before it is executed, the IL code in an assembly is automatically converted to processor-specific code by the Just-In-Time (JIT) compiler of .NET Common Language Runtime.</span></span>

<span data-ttu-id="ed55b-125">Dado que un ensamblado es una unidad autodescriptiva de funcionalidad que contiene código y metadatos, no hay necesidad de directivas `#include` ni archivos de encabezado de C#.</span><span class="sxs-lookup"><span data-stu-id="ed55b-125">Because an assembly is a self-describing unit of functionality containing both code and metadata, there is no need for `#include` directives and header files in C#.</span></span> <span data-ttu-id="ed55b-126">Los tipos y miembros públicos contenidos en un ensamblado determinado estarán disponibles en un programa de C# simplemente haciendo referencia a dicho ensamblado al compilar el programa.</span><span class="sxs-lookup"><span data-stu-id="ed55b-126">The public types and members contained in a particular assembly are made available in a C# program simply by referencing that assembly when compiling the program.</span></span> <span data-ttu-id="ed55b-127">Por ejemplo, este programa usa la clase `Acme.Collections.Stack` desde el ensamblado `acme.dll`:</span><span class="sxs-lookup"><span data-stu-id="ed55b-127">For example, this program uses the `Acme.Collections.Stack` class from the `acme.dll` assembly:</span></span>

[!code-csharp[UsingStack](../../../samples/snippets/csharp/tour/program-structure/Program.cs#L38-L52)]

<span data-ttu-id="ed55b-128">Si el programa está almacenado en el archivo `example.cs`, cuando se compila `example.cs`, se puede hacer referencia al ensamblado acme.dl mediante la opción /r del compilador:</span><span class="sxs-lookup"><span data-stu-id="ed55b-128">If the program is stored in the file `example.cs`, when `example.cs` is compiled, the acme.dll assembly can be referenced using the compiler’s /r option:</span></span>

```console
csc /r:acme.dll example.cs
```

<span data-ttu-id="ed55b-129">Esto crea un ensamblado ejecutable denominado `example.exe`, que, cuando se ejecuta, produce el resultado:</span><span class="sxs-lookup"><span data-stu-id="ed55b-129">This creates an executable assembly named `example.exe`, which, when run, produces the output:</span></span>

```console
100
10
1
```

<span data-ttu-id="ed55b-130">C# permite que el texto de origen de un programa se almacene en varios archivos de origen.</span><span class="sxs-lookup"><span data-stu-id="ed55b-130">C# permits the source text of a program to be stored in several source files.</span></span> <span data-ttu-id="ed55b-131">Cuando se compila un programa de C# de varios archivos, todos los archivos de origen se procesan juntos y los archivos de origen pueden hacerse referencia mutuamente de forma libre; desde un punto de vista conceptual, es como si todos los archivos de origen estuvieran concatenados en un archivo de gran tamaño antes de ser procesados.</span><span class="sxs-lookup"><span data-stu-id="ed55b-131">When a multi-file C# program is compiled, all of the source files are processed together, and the source files can freely reference each other—conceptually, it is as if all the source files were concatenated into one large file before being processed.</span></span> <span data-ttu-id="ed55b-132">En C# nunca se necesitan declaraciones adelantadas porque, excepto en contadas ocasiones, el orden de declaración es insignificante.</span><span class="sxs-lookup"><span data-stu-id="ed55b-132">Forward declarations are never needed in C# because, with very few exceptions, declaration order is insignificant.</span></span> <span data-ttu-id="ed55b-133">C# no limita un archivo de origen a declarar solamente un tipo público ni precisa que el nombre del archivo de origen coincida con un tipo declarado en el archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="ed55b-133">C# does not limit a source file to declaring only one public type nor does it require the name of the source file to match a type declared in the source file.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ed55b-134">[Anterior](index.md)
>[Siguiente](types-and-variables.md)</span><span class="sxs-lookup"><span data-stu-id="ed55b-134">[Previous](index.md)
[Next](types-and-variables.md)</span></span>
