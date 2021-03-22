---
title: 'Instrucciones de nivel superior: Guía de programación de C#'
description: Obtenga información sobre las instrucciones de nivel superior en C# 9 y versiones posteriores.
ms.date: 03/08/2021
helpviewer_keywords:
- C# language, top-level statements
- C# language, Main method
ms.openlocfilehash: 69ff5fd606f5e12f55bd3e6dfc15fc7e64d8352b
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190450"
---
# <a name="top-level-statements-c-programming-guide"></a>Instrucciones de nivel superior (Guía de programación de C#)

A partir de C# 9, no es necesario incluir explícitamente un método `Main` en un proyecto de aplicación de consola. En su lugar, puede usar la característica de *instrucciones de nivel superior* para minimizar el código que tiene que escribir. En este caso, el compilador genera una clase y un punto de entrada de método `Main` para la aplicación.

A continuación se muestra un archivo *Program.cs* que es un programa de C# completo en C# 9:

:::code language="csharp" source="snippets/top-level-statements-1/Program.cs":::

Las instrucciones de nivel superior permiten escribir programas sencillos para utilidades pequeñas, como Azure Functions y Acciones de GitHub. También facilitan a los nuevos programadores de C# empezar a aprender y escribir código.

En las secciones siguientes se explican las reglas de lo que puede y no puede hacer con las instrucciones de nivel superior.

## <a name="only-one-top-level-file"></a>Solo un archivo de nivel superior

Una aplicación debe tener solo un punto de entrada, por lo que un proyecto solo puede tener un archivo con instrucciones de nivel superior. Al colocar instrucciones de nivel superior en más de un archivo de un proyecto, se produce el error del compilador siguiente:

> CS8802 Solo una unidad de compilación puede tener instrucciones de nivel superior.

Un proyecto puede tener cualquier número de archivos de código fuente adicionales que no tengan instrucciones de nivel superior.

## <a name="no-other-entry-points"></a>Ningún otro punto de entrada

Puede escribir un método `Main` de forma explícita, pero no puede funcionar como punto de entrada. El compilador emite la advertencia siguiente:

> CS7022 El punto de entrada del programa es código global: se ignora el punto de entrada "Main()".

En un proyecto con instrucciones de nivel superior, no se puede usar la opción del compilador [-main](../../language-reference/compiler-options/main-compiler-option.md) para seleccionar el punto de entrada, incluso si el proyecto tiene uno o varios métodos `Main`.

## <a name="using-directives"></a>Directivas `using`

Si incluye directivas using, deben aparecer en primer lugar en el archivo, como en este ejemplo:

:::code language="csharp" source="snippets/top-level-statements-1/Program.cs":::

## <a name="global-namespace"></a>Espacio de nombres global

Las instrucciones de nivel superior están implícitamente en el espacio de nombres global.

## <a name="namespaces-and-type-definitions"></a>Espacios de nombres y definiciones de tipos

Un archivo con instrucciones de nivel superior también puede contener espacios de nombres y definiciones de tipos, pero deben aparecer después de las instrucciones de nivel superior. Por ejemplo:

:::code language="csharp" source="snippets/top-level-statements-2/Program.cs":::

## `args`

Las instrucciones de nivel superior pueden hacer referencia a la variable `args` para acceder a los argumentos de línea de comandos que se hayan escrito. La variable `args` nunca es NULL, pero su valor `Length` es cero si no se han proporcionado argumentos de línea de comandos. Por ejemplo:

:::code language="csharp" source="snippets/top-level-statements-3/Program.cs":::

## `await`

Puede llamar a un método asincrónico mediante el uso `await`. Por ejemplo:

:::code language="csharp" source="snippets/top-level-statements-4/Program.cs":::

## <a name="exit-code-for-the-process"></a>Código de salida para el proceso

Para devolver un valor `int` cuando finaliza la aplicación, use la instrucción `return` como lo haría en un método `Main` que devuelva una instancia de `int`. Por ejemplo:

:::code language="csharp" source="snippets/top-level-statements-5/Program.cs":::

## <a name="implicit-entry-point-method"></a>Método de punto de entrada implícito

El compilador genera un método que actúa como el punto de entrada del programa para un proyecto con instrucciones de nivel superior. El nombre de este método no es en realidad `Main`, es un detalle de implementación al que el código no puede hacer referencia directamente. La signatura del método depende de si las instrucciones de nivel superior contienen la palabra clave `await` o la instrucción `return`. En la tabla siguiente se muestra el aspecto que tendría la signatura del método, utilizando el nombre del método `Main` en la tabla para mayor comodidad.

| El código de nivel superior contiene| Signatura de `Main` implícita                    |
|------------------------|----------------------------------------------|
| `await` y `return`   | `static async Task<int> Main(string[] args)` |
| `await`                | `static async Task Main(string[] args)`      |
| `return`               | `static int Main(string[] args)`             |
| No `await` ni `return` | `static void Main(string[] args)`            |

## <a name="c-language-specification"></a>especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]
[Instrucciones de nivel superior](~/_csharplang/proposals/csharp-9.0/top-level-statements.md)

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Métodos](../classes-and-structs/methods.md)
- [Dentro de un programa de C#](../inside-a-program/index.md)
