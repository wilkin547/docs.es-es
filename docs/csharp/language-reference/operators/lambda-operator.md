---
title: Operador =&gt; - Referencia de C#
ms.custom: seodec18
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: fa2e149f5b19e80e3171d08519be3ae249d2a112
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540811"
---
# <a name="gt-operator-c-reference"></a>Operador =&gt; (Referencia de C#)

El token `=>` se admite de dos formas: como el operador lambda y como un separador de un nombre de miembro y la implementación del miembro en una definición de cuerpo de expresión.

## <a name="lambda-operator"></a>Operador lambda

En las [expresiones lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md), el operador lambda `=>` se usa para separar las variables de entrada del lado izquierdo y el cuerpo lambda del lado derecho.

En el ejemplo siguiente se usa la característica [LINQ](../../programming-guide/concepts/linq/index.md) con sintaxis de método para demostrar el uso de las expresiones lambda:

[!code-csharp-interactive[infer types of input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#InferredTypes)]

Las variables de entrada de las expresiones lambda están fuertemente tipadas en tiempo de compilación. Cuando el compilador puede deducir los tipos de las variables de entrada, como en el ejemplo anterior, las declaraciones de tipos se pueden omitir. Si tiene que especificar el tipo de las variables de entrada, debe hacerlo para cada variable, como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[specify types of input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#ExplicitTypes)]

En el ejemplo siguiente se muestra cómo definir una expresión lambda sin variables de entrada:

[!code-csharp-interactive[without input variables](~/samples/snippets/csharp/language-reference/operators/LambdaOperatorExamples.cs#WithoutInput)]

Para obtener más información, vea [Expresiones lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md).

## <a name="expression-body-definition"></a>Definición de cuerpo de expresiones

Una definición de cuerpo de expresión tiene la siguiente sintaxis general:

```csharp
member => expression;
```

donde *expresión* es una expresión válida. Tenga en cuenta que *expresión* puede ser una *expresión de instrucción* solo si el tipo de valor devuelto del miembro es `void`, o bien si el miembro es un constructor, un finalizador o un descriptor de acceso `set` de propiedad.

En el ejemplo siguiente se muestra una definición de cuerpo de expresión para un método `Person.ToString`:

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

Es una versión abreviada de la definición de método siguiente:

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

A partir de C# 6, se admiten definiciones de cuerpos de expresión para métodos y propiedades de solo lectura. A partir de C# 7.0, se admiten definiciones de cuerpos de expresión para constructores, finalizadores, descriptores de acceso de propiedad e indizadores.

Para obtener más información, vea [Miembros con forma de expresión](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

El operador `=>` no se puede sobrecargar.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Expresiones de función anónima](~/_csharplang/spec/expressions.md#anonymous-function-expressions) de la [Especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Expresiones lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md)
- [Miembros con forma de expresión](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)