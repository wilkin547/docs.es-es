---
title: 'Valores devueltos de Main(): Guía de programación de C#'
description: Aprenda sobre los valores devueltos de Main(). Vea ejemplos de código y código generado por compiladores, y examine los recursos adicionales disponibles.
ms.date: 08/02/2017
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
ms.openlocfilehash: 4458f3cd7c8259c5725cfe5e853f826fe2ef61cc
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382066"
---
# <a name="main-return-values-c-programming-guide"></a><span data-ttu-id="c5e07-104">Valores devueltos de Main() (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="c5e07-104">Main() return values (C# Programming Guide)</span></span>

<span data-ttu-id="c5e07-105">El método `Main` puede devolver el valor `void`:</span><span class="sxs-lookup"><span data-stu-id="c5e07-105">The `Main` method can return `void`:</span></span>

 [!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

<span data-ttu-id="c5e07-106">También puede devolver un valor `int`:</span><span class="sxs-lookup"><span data-stu-id="c5e07-106">It can also return an `int`:</span></span>

 [!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

<span data-ttu-id="c5e07-107">Si el valor devuelto de `Main` no se usa, la devolución de `void` permite contar con un código ligeramente más simple.</span><span class="sxs-lookup"><span data-stu-id="c5e07-107">If the return value from `Main` is not used, returning `void` allows for slightly simpler code.</span></span> <span data-ttu-id="c5e07-108">En cambio, devolver un valor entero permite que el programa comunique información de estado a otros programas o scripts que invocan el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="c5e07-108">However, returning an integer enables the program to communicate status information to other programs or scripts that invoke the executable file.</span></span> <span data-ttu-id="c5e07-109">El valor devuelto de `Main` se trata como el código de salida para el proceso.</span><span class="sxs-lookup"><span data-stu-id="c5e07-109">The return value from `Main` is treated as the exit code for the process.</span></span> <span data-ttu-id="c5e07-110">Si se devuelve `void` de `Main`, el código de salida será implícitamente `0`.</span><span class="sxs-lookup"><span data-stu-id="c5e07-110">If `void` is returned from `Main`, the exit code will be implicitly `0`.</span></span> <span data-ttu-id="c5e07-111">En el ejemplo siguiente se muestra cómo se puede acceder al valor devuelto de `Main`.</span><span class="sxs-lookup"><span data-stu-id="c5e07-111">The following example shows how the return value from `Main` can be accessed.</span></span>

## <a name="example"></a><span data-ttu-id="c5e07-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5e07-112">Example</span></span>

<span data-ttu-id="c5e07-113">En este ejemplo se usan las herramientas de línea de comandos de [.NET Core](../../../core/index.yml).</span><span class="sxs-lookup"><span data-stu-id="c5e07-113">This example uses [.NET Core](../../../core/index.yml) command-line tools.</span></span> <span data-ttu-id="c5e07-114">Si no está familiarizado con las herramientas de línea de comandos de .NET Core, puede obtener información sobre ellas en este [artículo de introducción](../../../core/tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="c5e07-114">If you are unfamiliar with .NET Core command-line tools, you can learn about them in this [get-started article](../../../core/tutorials/with-visual-studio-code.md).</span></span>

<span data-ttu-id="c5e07-115">Modifique el método `Main` en *program.cs* como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="c5e07-115">Modify the `Main` method in *program.cs* as follows:</span></span>

 [!code-csharp[csProgGuideMain#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#14)]

<span data-ttu-id="c5e07-116">Cuando un programa se ejecuta en Windows, cualquier valor devuelto por la función `Main` se almacena en una variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="c5e07-116">When a program is executed in Windows, any value returned from the `Main` function is stored in an environment variable.</span></span> <span data-ttu-id="c5e07-117">Esta variable de entorno se puede recuperar mediante `ERRORLEVEL` desde un archivo por lotes, o mediante `$LastExitCode` desde PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5e07-117">This environment variable can be retrieved using `ERRORLEVEL` from a batch file, or `$LastExitCode` from powershell.</span></span>

<span data-ttu-id="c5e07-118">Puede compilar la aplicación mediante el comando `dotnet build` de la [CLI de dotnet](../../../core/tools/dotnet.md).</span><span class="sxs-lookup"><span data-stu-id="c5e07-118">You can build the application using the [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build` command.</span></span>

<span data-ttu-id="c5e07-119">Después, cree un script de PowerShell para ejecutar la aplicación y mostrar el resultado.</span><span class="sxs-lookup"><span data-stu-id="c5e07-119">Next, create a Powershell script to run the application and display the result.</span></span> <span data-ttu-id="c5e07-120">Pegue el código siguiente en un archivo de texto y guárdelo como `test.ps1` en la carpeta que contiene el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c5e07-120">Paste the following code into a text file and save it as `test.ps1` in the folder that contains the project.</span></span> <span data-ttu-id="c5e07-121">Ejecute el script de PowerShell. Para ello, escriba `test.ps1` en el símbolo del sistema de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5e07-121">Run the powershell script by typing `test.ps1` at the powershell prompt.</span></span>

<span data-ttu-id="c5e07-122">Dado que el código devuelve el valor cero, el archivo por lotes comunicará un resultado satisfactorio.</span><span class="sxs-lookup"><span data-stu-id="c5e07-122">Because the code returns zero, the batch file will report success.</span></span> <span data-ttu-id="c5e07-123">En cambio, si cambia MainReturnValTest.cs para que devuelva un valor distinto de cero y luego vuelve a compilar el programa, la ejecución posterior del script de PowerShell informará de que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="c5e07-123">However, if you change MainReturnValTest.cs to return a non-zero value and then recompile the program, subsequent execution of the powershell script will report failure.</span></span>

```dotnetcli
dotnet run
```

```powershell
if ($LastExitCode -eq 0) {
    Write-Host "Execution succeeded"
} else
{
    Write-Host "Execution Failed"
}
Write-Host "Return value = " $LastExitCode
```

## <a name="sample-output"></a><span data-ttu-id="c5e07-124">Resultados de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5e07-124">Sample output</span></span>

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a><span data-ttu-id="c5e07-125">Valores devueltos asincrónicos de Main</span><span class="sxs-lookup"><span data-stu-id="c5e07-125">Async Main return values</span></span>

<span data-ttu-id="c5e07-126">Los valores devueltos asincrónicos de Main mueven el código reutilizable necesario para llamar a métodos asincrónicos en `Main` al código generado por el compilador.</span><span class="sxs-lookup"><span data-stu-id="c5e07-126">Async Main return values move the boilerplate code necessary for calling asynchronous methods in `Main` to code generated by the compiler.</span></span> <span data-ttu-id="c5e07-127">Antes, había que escribir esta construcción para llamar a código asincrónico y asegurarse de que el programa se ejecutase hasta la finalización de la operación asincrónica:</span><span class="sxs-lookup"><span data-stu-id="c5e07-127">Previously, you would need to write this construct to call asynchronous code and ensure your program ran until the asynchronous operation completed:</span></span>

```csharp
public static void Main()
{
    AsyncConsoleWork().GetAwaiter().GetResult();
}

private static async Task<int> AsyncConsoleWork()
{
    // Main body here
    return 0;
}
```

<span data-ttu-id="c5e07-128">Ahora, esto se puede reemplazar por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c5e07-128">Now, this can be replaced by:</span></span>

[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]

<span data-ttu-id="c5e07-129">La ventaja de la nueva sintaxis es que el compilador siempre genera el código correcto.</span><span class="sxs-lookup"><span data-stu-id="c5e07-129">The advantage of the new syntax is that the compiler always generates the correct code.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="c5e07-130">Código generado por el compilador</span><span class="sxs-lookup"><span data-stu-id="c5e07-130">Compiler-generated code</span></span>

<span data-ttu-id="c5e07-131">Cuando el punto de entrada de la aplicación devuelve `Task` o `Task<int>`, el compilador genera un nuevo punto de entrada que llama al método de punto de entrada declarado en el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c5e07-131">When the application entry point returns a `Task` or `Task<int>`, the compiler generates a new entry point that calls the entry point method declared in the application code.</span></span> <span data-ttu-id="c5e07-132">Suponiendo que este punto de entrada se denomina `$GeneratedMain`, el compilador genera el código siguiente para estos puntos de entrada:</span><span class="sxs-lookup"><span data-stu-id="c5e07-132">Assuming that this entry point is called `$GeneratedMain`, the compiler generates the following code for these entry points:</span></span>

- <span data-ttu-id="c5e07-133">`static Task Main()` hace que el compilador emita el equivalente de `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="c5e07-133">`static Task Main()` results in the compiler emitting the equivalent of `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="c5e07-134">`static Task Main(string[])` hace que el compilador emita el equivalente de `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="c5e07-134">`static Task Main(string[])` results in the compiler emitting the equivalent of `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="c5e07-135">`static Task<int> Main()` hace que el compilador emita el equivalente de `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="c5e07-135">`static Task<int> Main()` results in the compiler emitting the equivalent of `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="c5e07-136">`static Task<int> Main(string[])` hace que el compilador emita el equivalente de `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="c5e07-136">`static Task<int> Main(string[])` results in the compiler emitting the equivalent of `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>

> [!NOTE]
><span data-ttu-id="c5e07-137">Si en los ejemplos se usase el modificador `async` en el método `Main`, el compilador generaría el mismo código.</span><span class="sxs-lookup"><span data-stu-id="c5e07-137">If the examples used `async` modifier on the `Main` method, the compiler would generate the same code.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5e07-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5e07-138">See also</span></span>

- [<span data-ttu-id="c5e07-139">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c5e07-139">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c5e07-140">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c5e07-140">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c5e07-141">Main() y argumentos de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="c5e07-141">Main() and Command-Line Arguments</span></span>](index.md)
- [<span data-ttu-id="c5e07-142">Procedimiento para mostrar argumentos de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="c5e07-142">How to display command line arguments</span></span>](./how-to-display-command-line-arguments.md)
