---
title: 'Estructura del programa de C#: un paseo por el lenguaje C#'
description: Conozca más acerca de los bloques de compilación básicos de un programa de C#.
ms.date: 02/25/2020
ms.assetid: 984f0314-507f-47a0-af56-9011243f5e65
ms.openlocfilehash: c0a4dcaed7b53a7da7008d6000b3bec2ffe3ee7b
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141015"
---
# <a name="program-structure"></a><span data-ttu-id="5377d-103">Estructura del programa</span><span class="sxs-lookup"><span data-stu-id="5377d-103">Program Structure</span></span>

<span data-ttu-id="5377d-104">Los principales conceptos organizativos en C# son ***programas***, ***espacios de nombres***, ***tipos***, ***miembros*** y ***ensamblados***.</span><span class="sxs-lookup"><span data-stu-id="5377d-104">The key organizational concepts in C# are ***programs***, ***namespaces***, ***types***, ***members***, and ***assemblies***.</span></span> <span data-ttu-id="5377d-105">Los programas de C# constan de uno o más archivos de origen.</span><span class="sxs-lookup"><span data-stu-id="5377d-105">C# programs consist of one or more source files.</span></span> <span data-ttu-id="5377d-106">Los programas declaran tipos, que contienen miembros y pueden organizarse en espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="5377d-106">Programs declare types, which contain members and can be organized into namespaces.</span></span> <span data-ttu-id="5377d-107">Las clases e interfaces son ejemplos de tipos.</span><span class="sxs-lookup"><span data-stu-id="5377d-107">Classes and interfaces are examples of types.</span></span> <span data-ttu-id="5377d-108">Los campos, los métodos, las propiedades y los eventos son ejemplos de miembros.</span><span class="sxs-lookup"><span data-stu-id="5377d-108">Fields, methods, properties, and events are examples of members.</span></span> <span data-ttu-id="5377d-109">Cuando se compilan programas de C#, se empaquetan físicamente en ensamblados.</span><span class="sxs-lookup"><span data-stu-id="5377d-109">When C# programs are compiled, they're physically packaged into assemblies.</span></span> <span data-ttu-id="5377d-110">Normalmente, los ensamblados tienen la extensión de archivo `.exe` o `.dll`, dependiendo de si implementan ***aplicaciones*** o ***bibliotecas***, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="5377d-110">Assemblies typically have the file extension `.exe` or `.dll`, depending on whether they implement ***applications*** or ***libraries***, respectively.</span></span>

<span data-ttu-id="5377d-111">Puede crear un proyecto de biblioteca denominado *acme* mediante el comando `dotnet new`:</span><span class="sxs-lookup"><span data-stu-id="5377d-111">You can create a library project named *acme* using the `dotnet new` command:</span></span>

```dotnetcli
dotnet new classlib -o acme
```

<span data-ttu-id="5377d-112">En ese proyecto, declare una clase denominada `Stack` en un espacio de nombres llamado `Acme.Collections`:</span><span class="sxs-lookup"><span data-stu-id="5377d-112">In that project, declare a class named `Stack` in a namespace called `Acme.Collections`:</span></span>

[!code-csharp[Stack](../../../samples/snippets/csharp/tour/program-structure/program.cs#L1-L34)]

<span data-ttu-id="5377d-113">El nombre completo de esta clase es `Acme.Collections.Stack`.</span><span class="sxs-lookup"><span data-stu-id="5377d-113">The fully qualified name of this class is `Acme.Collections.Stack`.</span></span> <span data-ttu-id="5377d-114">La clase contiene varios miembros: un campo denominado `top`, dos métodos denominados `Push` y `Pop`, y una clase anidada denominada `Entry`.</span><span class="sxs-lookup"><span data-stu-id="5377d-114">The class contains several members: a field named `top`, two methods named `Push` and `Pop`, and a nested class named `Entry`.</span></span> <span data-ttu-id="5377d-115">La clase `Entry` contiene además tres miembros: un campo denominado `next`, un campo denominado `data` y un constructor.</span><span class="sxs-lookup"><span data-stu-id="5377d-115">The `Entry` class further contains three members: a field named `next`, a field named `data`, and a constructor.</span></span> <span data-ttu-id="5377d-116">El comando:</span><span class="sxs-lookup"><span data-stu-id="5377d-116">The command:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="5377d-117">compila el ejemplo como una biblioteca (código sin un punto de entrada `Main` y genera un ensamblado denominado `acme.dll`.</span><span class="sxs-lookup"><span data-stu-id="5377d-117">compiles the example as a library (code without a `Main` entry point) and produces an assembly named `acme.dll`.</span></span>

<span data-ttu-id="5377d-118">Los ensamblados contienen código ejecutable en forma de instrucciones de lenguaje intermedio (IL) e información simbólica en forma de metadatos.</span><span class="sxs-lookup"><span data-stu-id="5377d-118">Assemblies contain executable code in the form of Intermediate Language (IL) instructions, and symbolic information in the form of metadata.</span></span> <span data-ttu-id="5377d-119">Antes de ejecutarlo, el compilador Just-In-Time (JIT) del entorno de ejecución de .NET convierte el código de IL de un ensamblado en código específico del procesador.</span><span class="sxs-lookup"><span data-stu-id="5377d-119">Before it's executed, the Just-In-Time (JIT) compiler of .NET Common Language Runtime converts the IL code in an assembly to processor-specific code.</span></span>

<span data-ttu-id="5377d-120">Como un ensamblado es una unidad autodescriptiva de funcionalidad que contiene código y metadatos, no hay necesidad de directivas `#include` ni archivos de encabezado de C#.</span><span class="sxs-lookup"><span data-stu-id="5377d-120">Because an assembly is a self-describing unit of functionality containing both code and metadata, there's no need for `#include` directives and header files in C#.</span></span> <span data-ttu-id="5377d-121">Los tipos y miembros públicos contenidos en un ensamblado determinado estarán disponibles en un programa de C# simplemente haciendo referencia a dicho ensamblado al compilar el programa.</span><span class="sxs-lookup"><span data-stu-id="5377d-121">The public types and members contained in a particular assembly are made available in a C# program simply by referencing that assembly when compiling the program.</span></span> <span data-ttu-id="5377d-122">Por ejemplo, este programa usa la clase `Acme.Collections.Stack` desde el ensamblado `acme.dll`:</span><span class="sxs-lookup"><span data-stu-id="5377d-122">For example, this program uses the `Acme.Collections.Stack` class from the `acme.dll` assembly:</span></span>

[!code-csharp[UsingStack](../../../samples/snippets/csharp/tour/program-structure/Program.cs#L38-L52)]

<span data-ttu-id="5377d-123">El archivo *csproj* del proyecto del programa anterior debe incluir un nodo de referencia para que el compilador de C# resuelva las referencias a las clases del ensamblado `acme.dll`:</span><span class="sxs-lookup"><span data-stu-id="5377d-123">The *csproj* file for the preceding program's project must include a reference node for the C# compiler to resolve references to the classes in the `acme.dll` assembly:</span></span>

```xml
  <ItemGroup>
    <ProjectReference Include="..\acme\acme.csproj" />
  </ItemGroup>
```

<span data-ttu-id="5377d-124">Después de agregarlo, `dotnet build` crea un ensamblado ejecutable denominado `example.exe` que, cuando se ejecuta, produce esta salida:</span><span class="sxs-lookup"><span data-stu-id="5377d-124">After that addition, `dotnet build` creates an executable assembly named `example.exe`, which, when run, produces the output:</span></span>

```dotnetcli
100
10
1
```

<span data-ttu-id="5377d-125">C# permite que el texto de origen de un programa se almacene en varios archivos de origen.</span><span class="sxs-lookup"><span data-stu-id="5377d-125">C# permits the source text of a program to be stored in several source files.</span></span> <span data-ttu-id="5377d-126">Cuando se compila un programa de C# de varios archivos, todos los archivos de origen se procesan juntos y los archivos de origen pueden hacerse referencia mutuamente de forma libre; desde un punto de vista conceptual, es como si todos los archivos de origen estuvieran concatenados en un archivo de gran tamaño antes de ser procesados.</span><span class="sxs-lookup"><span data-stu-id="5377d-126">When a multi-file C# program is compiled, all of the source files are processed together, and the source files can freely reference each other—conceptually, it is as if all the source files were concatenated into one large file before being processed.</span></span> <span data-ttu-id="5377d-127">En C# nunca se necesitan declaraciones adelantadas porque, excepto en contadas ocasiones, el orden de declaración es insignificante.</span><span class="sxs-lookup"><span data-stu-id="5377d-127">Forward declarations are never needed in C# because, with few exceptions, declaration order is insignificant.</span></span> <span data-ttu-id="5377d-128">C# no limita un archivo de origen a declarar solamente un tipo público ni precisa que el nombre del archivo de origen coincida con un tipo declarado en el archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="5377d-128">C# does not limit a source file to declaring only one public type nor does it require the name of the source file to match a type declared in the source file.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5377d-129">[Anterior](index.md)
>[Siguiente](types-and-variables.md)</span><span class="sxs-lookup"><span data-stu-id="5377d-129">[Previous](index.md)
[Next](types-and-variables.md)</span></span>
