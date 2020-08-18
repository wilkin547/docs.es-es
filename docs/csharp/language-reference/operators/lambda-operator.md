---
title: Operador => (referencia de C#)
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 30e1a3546f83a0a1ba5b1363238878868e94ab93
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063138"
---
# <a name="-operator-c-reference"></a>Operador => (referencia de C#)

El token `=>` se admite de dos formas: como el [operador lambda](#lambda-operator) y como un separador de un nombre de miembro y la implementación del miembro en una [definición de cuerpo de expresión](#expression-body-definition).

## <a name="lambda-operator"></a>Operador{1}{2}lambda

En las [expresiones lambda](lambda-expressions.md), el operador`=>`{4}lambda {5} separa los parámetros de entrada del lado izquierdo y el cuerpo lambda del lado derecho.

En el ejemplo siguiente se usa la característica [LINQ](../../programming-guide/concepts/linq/index.md) con sintaxis de método para demostrar el uso de las expresiones lambda:

[!code-csharp-interactive[infer types of input variables](snippets/shared/LambdaOperator.cs#InferredTypes)]

Los parámetros de entrada de una expresión lambda están fuertemente tipados en tiempo de compilación. Cuando el compilador puede deducir los tipos de los parámetros de entrada, como en el ejemplo anterior, se pueden omitir las declaraciones de tipos. Si tiene que especificar el tipo de los parámetros de entrada, debe hacerlo para cada uno de ellos, como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[specify types of input variables](snippets/shared/LambdaOperator.cs#ExplicitTypes)]

En el ejemplo siguiente se muestra cómo definir una expresión lambda sin parámetros de entrada:

[!code-csharp-interactive[without input variables](snippets/shared/LambdaOperator.cs#WithoutInput)]

Para obtener más información, vea [Expresiones lambda](lambda-expressions.md).

## <a name="expression-body-definition"></a>Definición de cuerpo de expresiones

Una definición de cuerpo de expresión tiene la siguiente sintaxis general:

```csharp
member => expression;
```

donde `expression` es una expresión válida. El tipo de valor devuelto de `expression` se debe poder convertir implícitamente al tipo de valor devuelto del miembro. Si el tipo de valor devuelto del miembro es `void`, o si el miembro es un constructor, un finalizador o un descriptor de acceso `set` de propiedad o indizador, `expression` debe ser una [*expresión de instrucción*](~/_csharplang/spec/statements.md#expression-statements). Dado que el resultado de la expresión se descarta, el tipo de valor devuelto de esa expresión puede ser cualquiera.

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

A partir de C# 6, se admiten definiciones de cuerpos de expresión para métodos, operadores y propiedades de solo lectura. A partir de C# 7.0, se admiten definiciones de cuerpos de expresión para constructores, finalizadores y descriptores de acceso de propiedad e indizador.

Para obtener más información, vea [Miembros con forma de expresión](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

El operador `=>` no se puede sobrecargar.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información sobre el operador lambda, vea la sección [Expresiones de función anónima](~/_csharplang/spec/expressions.md#anonymous-function-expressions) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores y expresiones de C#](index.md)
