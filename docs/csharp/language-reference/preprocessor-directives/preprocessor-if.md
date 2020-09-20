---
description: '#Directiva de preprocesador if: Referencia de C#'
title: '#Directiva de preprocesador if: Referencia de C#'
ms.date: 10/27/2019
f1_keywords:
- '#if'
helpviewer_keywords:
- '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
ms.openlocfilehash: dc3e235db49279691203a0db4d124239fb972c69
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065244"
---
# <a name="if-c-reference"></a>#if (referencia de C#)

Cuando el compilador de C# encuentra una directiva `#if`, seguida finalmente por una directiva [#endif](preprocessor-endif.md), compila el código entre las directivas solo si se ha definido el símbolo especificado. A diferencia de C y C++, no se puede asignar un valor numérico a un símbolo. La instrucción `#if` en C# es booleana y solo comprueba si el símbolo se ha definido o no. Por ejemplo:

```csharp
#if DEBUG
    Console.WriteLine("Debug version");
#endif
```

Puede usar los operadores [==](../operators/equality-operators.md#equality-operator-) (igualdad) y [!=](../operators/equality-operators.md#inequality-operator-) (desigualdad) solo para comprobar los valores [booleanos](../builtin-types/bool.md)`true` o `false`. `true` significa que el símbolo está definido. La instrucción `#if DEBUG` tiene el mismo significado que `#if (DEBUG == true)`. Puede usar los operadores [&& (AND)](../operators/boolean-logical-operators.md#conditional-logical-and-operator-), [&#124;&#124; (OR)](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) y [! (NOT)](../operators/boolean-logical-operators.md#logical-negation-operator-) para evaluar si se han definido varios símbolos. Es posible agrupar símbolos y operadores mediante paréntesis.

## <a name="remarks"></a>Observaciones

`#if`, junto con las directivas [#else](preprocessor-else.md), [#elif](preprocessor-elif.md), [#endif](preprocessor-endif.md), [#define](preprocessor-define.md) y [#undef](preprocessor-undef.md), permite incluir o excluir código basado en la existencia de uno o varios símbolos. Esto puede resultar útil al compilar código para una compilación de depuración o al compilar para una configuración específica.

Una directiva condicional que empieza con una directiva `#if` debe terminar de forma explícita con una directiva `#endif`.

`#define` permite definir un símbolo. Si luego se usa el símbolo como la expresión pasada a la directiva `#if`, la expresión se evalúa como `true`.

También se puede definir un símbolo con la opción del compilador [-define](../compiler-options/define-compiler-option.md). La definición de un símbolo se puede anular mediante [#undef](preprocessor-undef.md).

Un símbolo definido con `-define` o `#define` no debe entrar en conflicto con una variable del mismo nombre. Es decir, un nombre de variable no debe pasarse a una directiva de preprocesador y un símbolo solo puede ser evaluado por una directiva de preprocesador.

El ámbito de un símbolo creado con `#define` es el archivo en que se ha definido.

El sistema de compilación también tiene en cuenta los símbolos de preprocesador predefinidos que representan distintos [marcos de destino](../../../standard/frameworks.md) en proyectos de estilo SDK. Resultan útiles al crear aplicaciones que pueden tener como destino más de una versión de .NET.

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

> [!NOTE]
> En el caso de los proyectos que no son de estilo SDK, tendrá que configurar manualmente los símbolos de compilación condicional para las diferentes plataformas de destino en Visual Studio a través de las páginas de propiedades del proyecto.

Otros símbolos predefinidos incluyen las constantes DEBUG y TRACE. Puede invalidar los valores establecidos para el proyecto con `#define`. Por ejemplo, el símbolo DEBUG se establece automáticamente según las propiedades de configuración de compilación (modo de "depuración" o de "versión").

## <a name="examples"></a>Ejemplos

En el ejemplo siguiente se muestra cómo definir un símbolo MYTEST en un archivo y luego probar los valores de los símbolos MYTEST y DEBUG. El resultado de este ejemplo depende de si ha compilado el proyecto en modo de configuración de depuración o de versión.

```csharp
#define MYTEST
using System;
public class MyClass
{
    static void Main()
    {
#if (DEBUG && !MYTEST)
        Console.WriteLine("DEBUG is defined");
#elif (!DEBUG && MYTEST)
        Console.WriteLine("MYTEST is defined");
#elif (DEBUG && MYTEST)
        Console.WriteLine("DEBUG and MYTEST are defined");  
#else
        Console.WriteLine("DEBUG and MYTEST are not defined");
#endif
    }
}
```

En el ejemplo siguiente se muestra cómo probar distintos marcos de destino para que se puedan usar las API más recientes cuando sea posible:

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        WebClient _client = new WebClient();
#else
        HttpClient _client = new HttpClient();
#endif
    }
    //...
}
```

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Directivas de preprocesador de C#](index.md)
- [Cómo: Compilación condicional con Trace y Debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
