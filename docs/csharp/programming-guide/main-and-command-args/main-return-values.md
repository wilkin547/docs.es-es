---
title: 'Valores devueltos de Main(): Guía de programación de C#'
description: Aprenda sobre los valores devueltos de Main(). Vea ejemplos de código y código generado por compiladores, y examine los recursos adicionales disponibles.
ms.date: 03/11/2021
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
ms.openlocfilehash: 6f4001ecd490d5627d3a1ec74ecf7d593451e104
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190364"
---
# <a name="main-return-values-c-programming-guide"></a><span data-ttu-id="55bbe-104">Valores devueltos de Main() (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="55bbe-104">Main() return values (C# Programming Guide)</span></span>

<span data-ttu-id="55bbe-105">Puede devolver un objeto `int` desde el método `Main` si lo define de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="55bbe-105">You can return an `int` from the `Main` method by defining the method in one of the following ways:</span></span>

| <span data-ttu-id="55bbe-106">Código del método `Main`</span><span class="sxs-lookup"><span data-stu-id="55bbe-106">`Main` method code</span></span>             | <span data-ttu-id="55bbe-107">Signatura de `Main`</span><span class="sxs-lookup"><span data-stu-id="55bbe-107">`Main` signature</span></span>                             |
|--------------------------------|----------------------------------------------|
| <span data-ttu-id="55bbe-108">No se usa `args` ni `await`</span><span class="sxs-lookup"><span data-stu-id="55bbe-108">No use of `args` or `await`</span></span>    | `static int Main()`                          |
| <span data-ttu-id="55bbe-109">Se usa `args`, no se usa `await`</span><span class="sxs-lookup"><span data-stu-id="55bbe-109">Uses `args`, no use of `await`</span></span> | `static int Main(string[] args)`             |
| <span data-ttu-id="55bbe-110">No se usa `args`, se usa `await`</span><span class="sxs-lookup"><span data-stu-id="55bbe-110">No use of `args`, uses `await`</span></span> | `static async Task<int> Main()`              |
| <span data-ttu-id="55bbe-111">Se usan `args` y `await`</span><span class="sxs-lookup"><span data-stu-id="55bbe-111">Uses `args` and `await`</span></span>        | `static async Task<int> Main(string[] args)` |

<span data-ttu-id="55bbe-112">Si el valor devuelto de `Main` no se usa, la devolución de `void` o `Task` permite que el código sea ligeramente más sencillo.</span><span class="sxs-lookup"><span data-stu-id="55bbe-112">If the return value from `Main` is not used, returning `void` or `Task` allows for slightly simpler code.</span></span>

| <span data-ttu-id="55bbe-113">Código del método `Main`</span><span class="sxs-lookup"><span data-stu-id="55bbe-113">`Main` method code</span></span>             | <span data-ttu-id="55bbe-114">Signatura de `Main`</span><span class="sxs-lookup"><span data-stu-id="55bbe-114">`Main` signature</span></span>                        |
|--------------------------------|-----------------------------------------|
| <span data-ttu-id="55bbe-115">No se usa `args` ni `await`</span><span class="sxs-lookup"><span data-stu-id="55bbe-115">No use of `args` or `await`</span></span>    | `static void Main()`                    |
| <span data-ttu-id="55bbe-116">Se usa `args`, no se usa `await`</span><span class="sxs-lookup"><span data-stu-id="55bbe-116">Uses `args`, no use of `await`</span></span> | `static void Main(string[] args)`       |
| <span data-ttu-id="55bbe-117">No se usa `args`, se usa `await`</span><span class="sxs-lookup"><span data-stu-id="55bbe-117">No use of `args`, uses `await`</span></span> | `static async Task Main()`              |
| <span data-ttu-id="55bbe-118">Se usan `args` y `await`</span><span class="sxs-lookup"><span data-stu-id="55bbe-118">Uses `args` and `await`</span></span>        | `static async Task Main(string[] args)` |

<span data-ttu-id="55bbe-119">Pero, si se devuelve `int` o `Task<int>`, el programa puede comunicar información de estado a otros programas o scripts que invocan el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="55bbe-119">However, returning `int` or `Task<int>` enables the program to communicate status information to other programs or scripts that invoke the executable file.</span></span>

<span data-ttu-id="55bbe-120">En el ejemplo siguiente se muestra cómo se puede acceder al código de salida para el proceso.</span><span class="sxs-lookup"><span data-stu-id="55bbe-120">The following example shows how the exit code for the process can be accessed.</span></span>

## <a name="example"></a><span data-ttu-id="55bbe-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="55bbe-121">Example</span></span>

<span data-ttu-id="55bbe-122">En este ejemplo se usan las herramientas de línea de comandos de [.NET Core](../../../core/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="55bbe-122">This example uses [.NET Core](../../../core/introduction.md) command-line tools.</span></span> <span data-ttu-id="55bbe-123">Si no está familiarizado con las herramientas de línea de comandos de .NET Core, puede obtener información sobre ellas en este [artículo de introducción](../../../core/tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="55bbe-123">If you are unfamiliar with .NET Core command-line tools, you can learn about them in this [get-started article](../../../core/tutorials/with-visual-studio-code.md).</span></span>

<span data-ttu-id="55bbe-124">Modifique el método `Main` en *program.cs* como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="55bbe-124">Modify the `Main` method in *program.cs* as follows:</span></span>

 [!code-csharp[csProgGuideMain#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#14)]

<span data-ttu-id="55bbe-125">Cuando un programa se ejecuta en Windows, cualquier valor devuelto por la función `Main` se almacena en una variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="55bbe-125">When a program is executed in Windows, any value returned from the `Main` function is stored in an environment variable.</span></span> <span data-ttu-id="55bbe-126">Esta variable de entorno se puede recuperar mediante `ERRORLEVEL` desde un archivo por lotes, o mediante `$LastExitCode` desde PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55bbe-126">This environment variable can be retrieved using `ERRORLEVEL` from a batch file, or `$LastExitCode` from PowerShell.</span></span>

<span data-ttu-id="55bbe-127">Puede compilar la aplicación mediante el comando `dotnet build` de la [CLI de dotnet](../../../core/tools/dotnet.md).</span><span class="sxs-lookup"><span data-stu-id="55bbe-127">You can build the application using the [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build` command.</span></span>

<span data-ttu-id="55bbe-128">Después, cree un script de PowerShell para ejecutar la aplicación y mostrar el resultado.</span><span class="sxs-lookup"><span data-stu-id="55bbe-128">Next, create a PowerShell script to run the application and display the result.</span></span> <span data-ttu-id="55bbe-129">Pegue el código siguiente en un archivo de texto y guárdelo como `test.ps1` en la carpeta que contiene el proyecto.</span><span class="sxs-lookup"><span data-stu-id="55bbe-129">Paste the following code into a text file and save it as `test.ps1` in the folder that contains the project.</span></span> <span data-ttu-id="55bbe-130">Ejecute el script de PowerShell. Para ello, escriba `test.ps1` en el símbolo del sistema de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55bbe-130">Run the PowerShell script by typing `test.ps1` at the PowerShell prompt.</span></span>

<span data-ttu-id="55bbe-131">Dado que el código devuelve el valor cero, el archivo por lotes comunicará un resultado satisfactorio.</span><span class="sxs-lookup"><span data-stu-id="55bbe-131">Because the code returns zero, the batch file will report success.</span></span> <span data-ttu-id="55bbe-132">En cambio, si cambia MainReturnValTest.cs para que devuelva un valor distinto de cero y luego vuelve a compilar el programa, la ejecución posterior del script de PowerShell informará de que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="55bbe-132">However, if you change MainReturnValTest.cs to return a non-zero value and then recompile the program, subsequent execution of the PowerShell script will report failure.</span></span>

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

## <a name="sample-output"></a><span data-ttu-id="55bbe-133">Resultados de ejemplo</span><span class="sxs-lookup"><span data-stu-id="55bbe-133">Sample output</span></span>

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a><span data-ttu-id="55bbe-134">Valores devueltos asincrónicos de Main</span><span class="sxs-lookup"><span data-stu-id="55bbe-134">Async Main return values</span></span>

<span data-ttu-id="55bbe-135">Los valores devueltos asincrónicos de Main mueven el código reutilizable necesario para llamar a métodos asincrónicos en `Main` al código generado por el compilador.</span><span class="sxs-lookup"><span data-stu-id="55bbe-135">Async Main return values move the boilerplate code necessary for calling asynchronous methods in `Main` to code generated by the compiler.</span></span> <span data-ttu-id="55bbe-136">Antes, había que escribir esta construcción para llamar a código asincrónico y asegurarse de que el programa se ejecutase hasta la finalización de la operación asincrónica:</span><span class="sxs-lookup"><span data-stu-id="55bbe-136">Previously, you would need to write this construct to call asynchronous code and ensure your program ran until the asynchronous operation completed:</span></span>

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

<span data-ttu-id="55bbe-137">Ahora, esto se puede reemplazar por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="55bbe-137">Now, this can be replaced by:</span></span>

[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]

<span data-ttu-id="55bbe-138">La ventaja de la nueva sintaxis es que el compilador siempre genera el código correcto.</span><span class="sxs-lookup"><span data-stu-id="55bbe-138">The advantage of the new syntax is that the compiler always generates the correct code.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="55bbe-139">Código generado por el compilador</span><span class="sxs-lookup"><span data-stu-id="55bbe-139">Compiler-generated code</span></span>

<span data-ttu-id="55bbe-140">Cuando el punto de entrada de la aplicación devuelve `Task` o `Task<int>`, el compilador genera un nuevo punto de entrada que llama al método de punto de entrada declarado en el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="55bbe-140">When the application entry point returns a `Task` or `Task<int>`, the compiler generates a new entry point that calls the entry point method declared in the application code.</span></span> <span data-ttu-id="55bbe-141">Suponiendo que este punto de entrada se denomina `$GeneratedMain`, el compilador genera el código siguiente para estos puntos de entrada:</span><span class="sxs-lookup"><span data-stu-id="55bbe-141">Assuming that this entry point is called `$GeneratedMain`, the compiler generates the following code for these entry points:</span></span>

- <span data-ttu-id="55bbe-142">`static Task Main()` hace que el compilador emita el equivalente de `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="55bbe-142">`static Task Main()` results in the compiler emitting the equivalent of `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="55bbe-143">`static Task Main(string[])` hace que el compilador emita el equivalente de `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="55bbe-143">`static Task Main(string[])` results in the compiler emitting the equivalent of `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="55bbe-144">`static Task<int> Main()` hace que el compilador emita el equivalente de `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="55bbe-144">`static Task<int> Main()` results in the compiler emitting the equivalent of `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="55bbe-145">`static Task<int> Main(string[])` hace que el compilador emita el equivalente de `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="55bbe-145">`static Task<int> Main(string[])` results in the compiler emitting the equivalent of `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>

> [!NOTE]
><span data-ttu-id="55bbe-146">Si en los ejemplos se usase el modificador `async` en el método `Main`, el compilador generaría el mismo código.</span><span class="sxs-lookup"><span data-stu-id="55bbe-146">If the examples used `async` modifier on the `Main` method, the compiler would generate the same code.</span></span>

## <a name="see-also"></a><span data-ttu-id="55bbe-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="55bbe-147">See also</span></span>

- [<span data-ttu-id="55bbe-148">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="55bbe-148">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="55bbe-149">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="55bbe-149">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="55bbe-150">Main() y argumentos de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="55bbe-150">Main() and Command-Line Arguments</span></span>](index.md)
- [<span data-ttu-id="55bbe-151">Procedimiento para mostrar argumentos de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="55bbe-151">How to display command line arguments</span></span>](./how-to-display-command-line-arguments.md)
