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
# <a name="main-return-values-c-programming-guide"></a>Valores devueltos de Main() (Guía de programación de C#)

Puede devolver un objeto `int` desde el método `Main` si lo define de una de las siguientes maneras:

| Código del método `Main`             | Signatura de `Main`                             |
|--------------------------------|----------------------------------------------|
| No se usa `args` ni `await`    | `static int Main()`                          |
| Se usa `args`, no se usa `await` | `static int Main(string[] args)`             |
| No se usa `args`, se usa `await` | `static async Task<int> Main()`              |
| Se usan `args` y `await`        | `static async Task<int> Main(string[] args)` |

Si el valor devuelto de `Main` no se usa, la devolución de `void` o `Task` permite que el código sea ligeramente más sencillo.

| Código del método `Main`             | Signatura de `Main`                        |
|--------------------------------|-----------------------------------------|
| No se usa `args` ni `await`    | `static void Main()`                    |
| Se usa `args`, no se usa `await` | `static void Main(string[] args)`       |
| No se usa `args`, se usa `await` | `static async Task Main()`              |
| Se usan `args` y `await`        | `static async Task Main(string[] args)` |

Pero, si se devuelve `int` o `Task<int>`, el programa puede comunicar información de estado a otros programas o scripts que invocan el archivo ejecutable.

En el ejemplo siguiente se muestra cómo se puede acceder al código de salida para el proceso.

## <a name="example"></a>Ejemplo

En este ejemplo se usan las herramientas de línea de comandos de [.NET Core](../../../core/introduction.md). Si no está familiarizado con las herramientas de línea de comandos de .NET Core, puede obtener información sobre ellas en este [artículo de introducción](../../../core/tutorials/with-visual-studio-code.md).

Modifique el método `Main` en *program.cs* como se indica a continuación:

 [!code-csharp[csProgGuideMain#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#14)]

Cuando un programa se ejecuta en Windows, cualquier valor devuelto por la función `Main` se almacena en una variable de entorno. Esta variable de entorno se puede recuperar mediante `ERRORLEVEL` desde un archivo por lotes, o mediante `$LastExitCode` desde PowerShell.

Puede compilar la aplicación mediante el comando `dotnet build` de la [CLI de dotnet](../../../core/tools/dotnet.md).

Después, cree un script de PowerShell para ejecutar la aplicación y mostrar el resultado. Pegue el código siguiente en un archivo de texto y guárdelo como `test.ps1` en la carpeta que contiene el proyecto. Ejecute el script de PowerShell. Para ello, escriba `test.ps1` en el símbolo del sistema de PowerShell.

Dado que el código devuelve el valor cero, el archivo por lotes comunicará un resultado satisfactorio. En cambio, si cambia MainReturnValTest.cs para que devuelva un valor distinto de cero y luego vuelve a compilar el programa, la ejecución posterior del script de PowerShell informará de que se ha producido un error.

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

## <a name="sample-output"></a>Resultados de ejemplo

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a>Valores devueltos asincrónicos de Main

Los valores devueltos asincrónicos de Main mueven el código reutilizable necesario para llamar a métodos asincrónicos en `Main` al código generado por el compilador. Antes, había que escribir esta construcción para llamar a código asincrónico y asegurarse de que el programa se ejecutase hasta la finalización de la operación asincrónica:

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

Ahora, esto se puede reemplazar por lo siguiente:

[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]

La ventaja de la nueva sintaxis es que el compilador siempre genera el código correcto.

## <a name="compiler-generated-code"></a>Código generado por el compilador

Cuando el punto de entrada de la aplicación devuelve `Task` o `Task<int>`, el compilador genera un nuevo punto de entrada que llama al método de punto de entrada declarado en el código de la aplicación. Suponiendo que este punto de entrada se denomina `$GeneratedMain`, el compilador genera el código siguiente para estos puntos de entrada:

- `static Task Main()` hace que el compilador emita el equivalente de `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`
- `static Task Main(string[])` hace que el compilador emita el equivalente de `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`
- `static Task<int> Main()` hace que el compilador emita el equivalente de `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`
- `static Task<int> Main(string[])` hace que el compilador emita el equivalente de `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`

> [!NOTE]
>Si en los ejemplos se usase el modificador `async` en el método `Main`, el compilador generaría el mismo código.

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Referencia de C#](../../language-reference/index.md)
- [Main() y argumentos de la línea de comandos](index.md)
- [Procedimiento para mostrar argumentos de la línea de comandos](./how-to-display-command-line-arguments.md)
