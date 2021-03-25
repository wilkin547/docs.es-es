---
title: 'Argumento de la línea de comandos: Guía de programación de C#'
description: Aprenda sobre los argumentos de la línea de comandos. Vea un ejemplo en el que se usan argumentos de la línea de comandos en una aplicación de consola.
ms.date: 03/11/2021
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 0e597e0d-ea7a-41ba-a38a-0198122f3c26
ms.openlocfilehash: f495efb3bc2c76a98f74c173d5b777ebe383edcb
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190416"
---
# <a name="command-line-arguments-c-programming-guide"></a>Argumentos de la línea de comandos (Guía de programación de C#)

Puede enviar argumentos al método `Main` definiéndolo de una de las siguientes maneras:

| Código del método `Main`                 | Signatura de `Main`                             |
|------------------------------------|----------------------------------------------|
| No hay valores devueltos, no se usa `await` | `static void Main(string[] args)`            |
| Valor devuelto, no se usa `await`    | `static int Main(string[] args)`             |
| No hay valores devueltos, se usa `await`      | `static async Task Main(string[] args)`      |
| Valor devuelto, se usa `await`         | `static async Task<int> Main(string[] args)` |

Si no se usan los argumentos, puede omitir `args` de la signatura del método para simplificar ligeramente el código:

| Código del método `Main`                 | Signatura de `Main`                |
|------------------------------------|---------------------------------|
| No hay valores devueltos, no se usa `await` | `static void Main()`            |
| Valor devuelto, no se usa `await`    | `static int Main()`             |
| No hay valores devueltos, se usa `await`      | `static async Task Main()`      |
| Valor devuelto, se usa `await`         | `static async Task<int> Main()` |

> [!NOTE]
> Para habilitar los argumentos de la línea de comandos en el método `Main` de una aplicación Windows Forms, tendrá que modificar manualmente la firma de `Main` en *program.cs*. El código generado por el Diseñador de Windows Forms crea un `Main` sin ningún parámetro de entrada. También puede usar <xref:System.Environment.CommandLine%2A?displayProperty=nameWithType> o <xref:System.Environment.GetCommandLineArgs%2A?displayProperty=nameWithType> para tener acceso a los argumentos de la línea de comandos desde cualquier punto en una consola o aplicación Windows.

El parámetro del método `Main` es una matriz <xref:System.String> que representa los argumentos de la línea de comandos. Normalmente, para determinar si hay argumentos, se prueba la propiedad `Length`; por ejemplo:

[!code-csharp[csProgGuideMain#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#4)]

> [!TIP]
> La matriz `args` no puede ser NULL, así que es seguro acceder a la propiedad `Length` sin comprobar los valores NULL.

También puede convertir los argumentos de cadena en tipos numéricos mediante la clase <xref:System.Convert> o el método `Parse`. Por ejemplo, la siguiente instrucción convierte la `string` en un número `long` mediante el método <xref:System.Int64.Parse%2A>:

```csharp
long num = Int64.Parse(args[0]);
```

También se puede usar el tipo de C# `long`, que tiene como alias `Int64`:

```csharp
long num = long.Parse(args[0]);
```

También puede usar el método `ToInt64` de la clase `Convert` para hacer lo mismo:

```csharp
long num = Convert.ToInt64(s);
```

Para obtener más información, vea <xref:System.Int64.Parse%2A> y <xref:System.Convert>.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo usar argumentos de la línea de comandos en una aplicación de consola. La aplicación toma un argumento en tiempo de ejecución, lo convierte en un entero y calcula el factorial del número. Si no se proporciona ningún argumento, la aplicación emite un mensaje en el que se explica el uso correcto del programa.

Para compilar y ejecutar la aplicación desde un símbolo del sistema, siga estos pasos:

1. Pegue el código siguiente en cualquier editor de texto y, después, guarde el archivo como archivo de texto con el nombre *Factorial.cs*.

     [!code-csharp[csProgGuideMain#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#16)]

2. En la pantalla **Inicio** o en el menú **Inicio**, abra una ventana del **símbolo del sistema para desarrolladores** de Visual Studio y navegue hasta la carpeta que contiene el archivo que acaba de crear.

3. Escriba el siguiente comando para compilar la aplicación.
  
     `csc Factorial.cs`  
  
     Si la aplicación no tiene ningún error de compilación, se creará un archivo ejecutable con el nombre *Factorial.exe*.
  
4. Escriba el siguiente comando para calcular el factorial de 3:
  
     `Factorial 3`  
  
5. El comando genera este resultado: `The factorial of 3 is 6.`

> [!NOTE]
> Al ejecutar una aplicación en Visual Studio, puede especificar argumentos de la línea de comandos en la [Página Depuración, Diseñador de proyectos](/visualstudio/ide/reference/debug-page-project-designer).

## <a name="see-also"></a>Vea también

- <xref:System.Environment?displayProperty=nameWithType>
- [Guía de programación de C#](../index.md)
- [Main() y argumentos de la línea de comandos](index.md)
- [Procedimiento para mostrar argumentos de la línea de comandos](how-to-display-command-line-arguments.md)
- [Valores devueltos de Main()](main-return-values.md)
- [Clases](../classes-and-structs/classes.md)
