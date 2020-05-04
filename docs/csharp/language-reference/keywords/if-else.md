---
title: if-else - Referencia de C#
ms.date: 07/20/2015
f1_keywords:
- if_CSharpKeyword
- else
- else_CSharpKeyword
- if
helpviewer_keywords:
- else keyword [C#]
- if keyword [C#]
ms.assetid: d9a1d562-8cf5-4bd4-9ba7-8ad970cd25b2
ms.openlocfilehash: 61b60674d3b5de4649a52d2a165265ae0a27e0be
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738851"
---
# <a name="if-else-c-reference"></a>if-else (Referencia de C#)

Una instrucción `if` identifica qué instrucción se debe ejecutar dependiendo del valor de una expresión booleana. En el ejemplo siguiente, la variable `bool``condition` se establece en `true` y, a continuación, se comprueba en la instrucción `if` . El resultado es `The variable is set to true.`

[!code-csharp[csrefKeywordsSelection#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#1)]

Puede ejecutar los ejemplos de este tema situándolos en el método `Main` de una aplicación de consola.

Una instrucción `if` en C# puede tener dos formas, tal como se muestra en el ejemplo siguiente.

```csharp
// if-else statement
if (condition)
{
    then-statement;
}
else
{
    else-statement;
}
// Next statement in the program.

// if statement without an else
if (condition)
{
    then-statement;
}
// Next statement in the program.
```

En una instrucción `if-else` , si `condition` se evalúa como true, se ejecuta `then-statement` . Si `condition` es false, se ejecuta `else-statement` . Puesto que `condition` no puede ser simultáneamente true y false, la `then-statement` y la `else-statement` de una instrucción `if-else` nunca se podrán ejecutar a la vez. Después de ejecutar la `then-statement` o la `else-statement` , el control se transfiere a la siguiente instrucción situada después de la instrucción `if` .

En una instrucción `if` que no incluya una instrucción `else` , si `condition` es true, se ejecutará la `then-statement` . Si `condition` es false, el control se transfiere a la siguiente instrucción situada después de la instrucción `if` .

Tanto la `then-statement` como la `else-statement` pueden constar de una única instrucción o de varias instrucciones entre llaves (`{}`). Para una única instrucción, las llaves son opcionales pero se recomiendan.

La instrucción o las instrucciones en la `then-statement` y la `else-statement` pueden ser de cualquier tipo, incluida otra instrucción `if` anidada dentro de la instrucción `if` . En instrucciones `if` anidadas, cada cláusula `else` pertenece a la última `if` que no tiene su `else`correspondiente. En el ejemplo siguiente, `Result1` aparece si `m > 10` y `n > 20` se evalúan como true. Si `m > 10` es true, pero `n > 20` es false, aparece `Result2` .

[!code-csharp[csrefKeywordsSelection#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#2)]

En su lugar, si desea que `Result2` aparezca cuando `(m > 10)` es false, puede especificar dicha asociación mediante llaves para establecer el inicio y el fin de la instrucción `if` anidada, como se muestra en el ejemplo siguiente.

[!code-csharp[csrefKeywordsSelection#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#3)]

`Result2` aparece si la condición `(m > 10)` se evalúa como false.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, se escribe un carácter desde el teclado y el programa usa una instrucción `if` anidada para determinar si el carácter de entrada es un carácter alfabético. Si el carácter de entrada es un carácter alfabético, el programa comprueba si el carácter de entrada está en mayúsculas o minúsculas. Aparece un mensaje para cada caso.

[!code-csharp[csrefKeywordsSelection#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#4)]

## <a name="example"></a>Ejemplo

También puede anidar una instrucción `if` dentro de un bloque else, tal como se muestra en el siguiente código parcial. El ejemplo anida instrucciones `if` dentro de dos bloques más y, a continuación, un bloque. Los comentarios de especifican qué condiciones son true o false en cada bloque.

[!code-csharp[csrefKeywordsSelection#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#5)]

## <a name="example"></a>Ejemplo

El ejemplo siguiente determina si un carácter de entrada es una letra minúscula, una letra mayúscula o un número. Si estas tres condiciones son false, el carácter no es un carácter alfanumérico. En el ejemplo se muestra un mensaje para cada caso.

[!code-csharp[csrefKeywordsSelection#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#6)]

Puesto que puede ser válida tanto una instrucción del bloque else como del bloque then, puede usar cualquier expresión booleana válida para la condición. Puede usar [operadores lógicos](../operators/boolean-logical-operators.md) como `!`, `&&`, `||`, `&`, `|` y `^` para hacer condiciones compuestas. En el código siguiente, se muestran algunos ejemplos:

```csharp
// NOT
bool result = true;
if (!result)
{
    Console.WriteLine("The condition is true (result is false).");
}
else
{
    Console.WriteLine("The condition is false (result is true).");
}

// Short-circuit AND
int m = 9;
int n = 7;
int p = 5;
if (m >= n && m >= p)
{
    Console.WriteLine("Nothing is larger than m.");
}

// AND and NOT
if (m >= n && !(p > m))
{
    Console.WriteLine("Nothing is larger than m.");
}

// Short-circuit OR
if (m > n || m > p)
{
    Console.WriteLine("m isn't the smallest.");
}

// NOT and OR
m = 4;
if (!(m >= n || m >= p))
{
    Console.WriteLine("Now m is the smallest.");
}
// Output:
// The condition is false (result is true).
// Nothing is larger than m.
// Nothing is larger than m.
// m isn't the smallest.
// Now m is the smallest.
```

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [?: !](../operators/conditional-operator.md)
- [if-else (Instrucción) (C++)](/cpp/cpp/if-else-statement-cpp)
- [switch](switch.md)
