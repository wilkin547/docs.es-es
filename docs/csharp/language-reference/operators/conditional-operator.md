---
title: 'Operador ?: (Referencia de C#)'
ms.date: 07/20/2015
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 3e45ff6eaaefa5829c3ed9415abe1a12b7a1d069
ms.sourcegitcommit: 4bca8f7e172fd019ef437a4803bf5895c6bc4781
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2018
ms.locfileid: "50980627"
---
# <a name="-operator-c-reference"></a>Operador ?: (Referencia de C#)

El operador condicional (`?:`), normalmente conocido como un operador condicional ternario, devuelve uno de dos valores según el valor de una expresión booleana. A continuación se muestra la sintaxis del operador condicional.  

```csharp
condition ? first_expression : second_expression;  
```

A partir C# 7.2, `first_expression` y `second_expression` pueden ser [ expresiones `ref`](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md):

```csharp
ref condition ? ref first_expression : ref second_expression;  
```

El resultado se puede asignar a una variable `ref` o `ref readonly`, o bien a una variable sin ninguno de los modificadores.

## <a name="remarks"></a>Comentarios

`condition` debe evaluarse como `true` o `false`. Si `condition` es `true`, `first_expression` se evalúa y se convierte en el resultado. Si `condition` es `false`, `second_expression` se evalúa y se convierte en el resultado. Solo se evalúa una de las dos expresiones. Esto es especialmente importante para las expresiones donde el resultado es `ref`, como en el ejemplo siguiente válido:

```csharp
ref (storage != null) ? ref storage[3] : ref defaultValue;
```

La referencia a `storage` no se evalúa cuando `storage` es NULL.

Cuando el resultado es un valor, el tipo de `first_expression` y `second_expression` debe coincidir, o bien debe existir una conversión implícita de un tipo al otro. Cuando el resultado es `ref`, el tipo de `first_expression` y `second_expression` debe ser el mismo.

Puede expresar cálculos que, de lo contrario, podrían requerir una construcción `if-else` más concisa mediante el operador condicional. Por ejemplo, el código siguiente usa primero una instrucción `if` y después un operador condicional para clasificar un entero como positivo o negativo.

```csharp
int input = Convert.ToInt32(Console.ReadLine());  
string classify;  
  
// if-else construction.  
if (input > 0)  
    classify = "positive";  
else  
    classify = "negative";  
  
// ?: conditional operator.  
classify = (input > 0) ? "positive" : "negative";  
```

El operador condicional es asociativo a la derecha. La expresión `a ? b : c ? d : e` se evalúa como `a ? b : (c ? d : e)`, no como `(a ? b : c) ? d : e`.  
  
El operador condicional no se puede sobrecargar.
  
## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra el operador condicional cuyo resultado es un valor:

[!code-csharp[csRefOperators?:](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

En el ejemplo siguiente alternativo se muestra el operador condicional cuando el resultado es una referencia:

[!code-csharp[csRefOperatorsRef?:](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Operadores de C#](../../../csharp/language-reference/operators/index.md)  
- [if-else](../../../csharp/language-reference/keywords/if-else.md)  
- [Operadores ?. y ?[]](../../../csharp/language-reference/operators/null-conditional-operators.md)  
- [Operador !](../../../csharp/language-reference/operators/null-coalescing-operator.md)
