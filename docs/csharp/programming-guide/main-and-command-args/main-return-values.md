---
title: "Valores devueltos de Main() (Guía de programación de C#)"
ms.date: 2017-08-02
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: d019d1c5757a961c03439d756e808ae13fd8a67b
ms.openlocfilehash: 50943bdd0b7726145797faf82719537a388dad89
ms.contentlocale: es-es
ms.lasthandoff: 08/03/2017

---

# <a name="main-return-values-c-programming-guide"></a><span data-ttu-id="88875-102">Valores devueltos de Main() (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="88875-102">Main() return values (C# Programming Guide)</span></span>

<span data-ttu-id="88875-103">El método `Main` puede devolver el valor `void`:</span><span class="sxs-lookup"><span data-stu-id="88875-103">The `Main` method can return `void`:</span></span>

<span data-ttu-id="88875-104">[!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="88875-104">[!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_1.cs)]</span></span>

<span data-ttu-id="88875-105">También puede devolver un valor `int`:</span><span class="sxs-lookup"><span data-stu-id="88875-105">It can also return an `int`:</span></span>

<span data-ttu-id="88875-106">[!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="88875-106">[!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_2.cs)]</span></span>

<span data-ttu-id="88875-107">Si el valor devuelto de `Main` no se usa, la devolución de `void` permite contar con un código ligeramente más simple.</span><span class="sxs-lookup"><span data-stu-id="88875-107">If the return value from `Main` is not used, returning `void` allows for slightly simpler code.</span></span> <span data-ttu-id="88875-108">En cambio, devolver un valor entero permite que el programa comunique información de estado a otros programas o scripts que invocan el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="88875-108">However, returning an integer enables the program to communicate status information to other programs or scripts that invoke the executable file.</span></span> <span data-ttu-id="88875-109">El valor devuelto de `Main` se trata como el código de salida para el proceso.</span><span class="sxs-lookup"><span data-stu-id="88875-109">The return value from `Main` is treated as the exit code for the process.</span></span> <span data-ttu-id="88875-110">En el ejemplo siguiente se muestra cómo se puede acceder al valor devuelto de `Main`.</span><span class="sxs-lookup"><span data-stu-id="88875-110">The following example shows how the return value from `Main` can be accessed.</span></span>

## <a name="example"></a><span data-ttu-id="88875-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="88875-111">Example</span></span>

<span data-ttu-id="88875-112">En este ejemplo se usan las herramientas de línea de comandos de [.NET Core](../../../core/index.md).</span><span class="sxs-lookup"><span data-stu-id="88875-112">This example uses [.NET Core](../../../core/index.md) command line tools.</span></span> <span data-ttu-id="88875-113">Si no está familiarizado con las herramientas de línea de comandos de .NET Core, puede obtener información sobre ellas en este [tema de introducción](../../../core/tutorials/using-with-xplat-cli.md).</span><span class="sxs-lookup"><span data-stu-id="88875-113">If you are unfamilar with .NET Core command line tools, you can learn about them in this [Get started topic](../../../core/tutorials/using-with-xplat-cli.md).</span></span>

<span data-ttu-id="88875-114">Modifique el método `Main` en *program.cs* como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="88875-114">Modify the `Main` method in *program.cs* as follows:</span></span>

<span data-ttu-id="88875-115">[!code-cs[csProgGuideMain#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="88875-115">[!code-cs[csProgGuideMain#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_3.cs)]</span></span>

<span data-ttu-id="88875-116">Cuando un programa se ejecuta en Windows, cualquier valor devuelto por la función `Main` se almacena en una variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="88875-116">When a program is executed in Windows, any value returned from the `Main` function is stored in an environment variable.</span></span> <span data-ttu-id="88875-117">Esta variable de entorno se puede recuperar mediante `ERRORLEVEL` desde un archivo por lotes, o mediante `$LastExitCode` desde PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88875-117">This environment variable can be retrieved using `ERRORLEVEL` from a batch file, or `$LastExitCode` from powershell.</span></span>

<span data-ttu-id="88875-118">Puede compilar la aplicación mediante el comando `dotnet build` de la [CLI de dotnet](../../../core/tools/dotnet.md).</span><span class="sxs-lookup"><span data-stu-id="88875-118">You can build the application using the [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build` command.</span></span>

<span data-ttu-id="88875-119">Después, cree un script de PowerShell para ejecutar la aplicación y mostrar el resultado.</span><span class="sxs-lookup"><span data-stu-id="88875-119">Next, create a Powershell script to run the application and display the result.</span></span> <span data-ttu-id="88875-120">Pegue el código siguiente en un archivo de texto y guárdelo como `test.ps1` en la carpeta que contiene el proyecto.</span><span class="sxs-lookup"><span data-stu-id="88875-120">Paste the following code into a text file and save it as `test.ps1` in the folder that contains the project.</span></span> <span data-ttu-id="88875-121">Ejecute el script de PowerShell. Para ello, escriba `test.ps1` en el símbolo del sistema de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88875-121">Run the powershell script by typing `test.ps1` at the powershell prompt.</span></span>

<span data-ttu-id="88875-122">Dado que el código devuelve el valor cero, el archivo por lotes comunicará un resultado satisfactorio.</span><span class="sxs-lookup"><span data-stu-id="88875-122">Because the code returns zero, the batch file will report success.</span></span> <span data-ttu-id="88875-123">En cambio, si cambia MainReturnValTest.cs para que devuelva un valor distinto de cero y luego vuelve a compilar el programa, la ejecución posterior del script de PowerShell informará de que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="88875-123">However, if you change MainReturnValTest.cs to return a non-zero value and then re-compile the program, subsequent execution of the powershell script will report failure.</span></span>

```powershell
dotnet run
if ($LastExitCode -eq 0) {
    Write-Host "Execution succeeded"
} else
{
    Write-Host "Execution Failed"
}
Write-Host "Return value = " $LastExitCode
```

## <a name="sample-output"></a><span data-ttu-id="88875-124">Resultados de ejemplo</span><span class="sxs-lookup"><span data-stu-id="88875-124">Sample output</span></span>

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a><span data-ttu-id="88875-125">Valores devueltos asincrónicos de Main</span><span class="sxs-lookup"><span data-stu-id="88875-125">Async Main return values</span></span>

<span data-ttu-id="88875-126">Los valores devueltos asincrónicos de Main mueven el código reutilizable necesario para llamar a métodos asincrónicos en `Main` al código generado por el compilador.</span><span class="sxs-lookup"><span data-stu-id="88875-126">Async Main return values move the boilerplate code necessary for calling asynchronous methods in `Main` to code generated by the compiler.</span></span> <span data-ttu-id="88875-127">Antes, había que escribir esta construcción para llamar a código asincrónico y asegurarse de que el programa se ejecutase hasta la finalización de la operación asincrónica:</span><span class="sxs-lookup"><span data-stu-id="88875-127">Previously, you would need to write this construct to call asynchronous code and ensure your program ran until the asynchronous operation completed:</span></span>

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

<span data-ttu-id="88875-128">Ahora, esto se puede reemplazar por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="88875-128">Now, this can be replaced by:</span></span>

<span data-ttu-id="88875-129">[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]</span><span class="sxs-lookup"><span data-stu-id="88875-129">[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]</span></span>

<span data-ttu-id="88875-130">La ventaja de la nueva sintaxis es que el compilador siempre genera el código correcto.</span><span class="sxs-lookup"><span data-stu-id="88875-130">The advantage of the new syntax is that the compiler always generates the correct code.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="88875-131">Código generado por el compilador</span><span class="sxs-lookup"><span data-stu-id="88875-131">Compiler generated code</span></span>

<span data-ttu-id="88875-132">Cuando el punto de entrada de la aplicación devuelve `Task` o `Task<int>`, el compilador genera un nuevo punto de entrada que llama al método de punto de entrada declarado en el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="88875-132">When the application entry point returns a `Task` or `Task<int>`, the compiler generates a new entry point that calls the entry point method declared in the application code.</span></span> <span data-ttu-id="88875-133">Suponiendo que este punto de entrada se denomina `$GeneratedMain`, el compilador genera el código siguiente para estos puntos de entrada:</span><span class="sxs-lookup"><span data-stu-id="88875-133">Assuming that this entry point is called `$GeneratedMain`, the compiler generates the following code for these entry points:</span></span>

- <span data-ttu-id="88875-134">`static Task Main()` hace que el compilador emita el equivalente de `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="88875-134">`static Task Main()` results in the compiler emitting the equivalent of `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="88875-135">`static Task Main(string[])` hace que el compilador emita el equivalente de `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="88875-135">`static Task Main(string[])` results in the compiler emitting the equivalent of `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="88875-136">`static Task<int> Main()` hace que el compilador emita el equivalente de `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="88875-136">`static Task<int> Main()` results in the compiler emitting the equivalent of `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="88875-137">`static Task<int> Main(string[])` hace que el compilador emita el equivalente de `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="88875-137">`static Task<int> Main(string[])` results in the compiler emitting the equivalent of `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>

> [!NOTE]
><span data-ttu-id="88875-138">Si en los ejemplos se usase el modificador `async` en el método `Main`, el compilador generaría el mismo código.</span><span class="sxs-lookup"><span data-stu-id="88875-138">If the examples used `async` modifier on the `Main` method, the compiler would generate the same code.</span></span>

## <a name="see-also"></a><span data-ttu-id="88875-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="88875-139">See also</span></span>
<span data-ttu-id="88875-140">[Guía de programación de C#](../../programming-guide/index.md)
[Referencia de C#](../index.md)
[Main() y argumentos de la línea de comandos](index.md)
[Cómo: Mostrar argumentos de la línea de comandos](../../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
[Cómo: Obtener acceso a argumentos de la línea de comandos utilizando Foreach](../../programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)</span><span class="sxs-lookup"><span data-stu-id="88875-140">[C# Programming Guide](../../programming-guide/index.md)
[C# Reference](../index.md)
[Main() and Command-Line Arguments](index.md)
[How to: Display Command Line Arguments](../../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
[How to: Access Command-Line Arguments Using foreach](../../programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)</span></span>

