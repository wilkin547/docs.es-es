---
title: Operadores - Guía de programación de C#
ms.custom: seodec18
ms.date: 04/30/2019
helpviewer_keywords:
- operators [C#]
- C# language, operators
- operators [C#], about operators
ms.assetid: 214e7b83-1a41-4f7c-9867-64e9c0bab39f
ms.openlocfilehash: 60e7f7c25b525c6db856731bd16c1c0e60efe6d6
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422927"
---
# <a name="operators-c-programming-guide"></a>Operadores (Guía de programación de C#)

En C#, un *operador* es un elemento de programa que se aplica a uno o varios *operandos* en una expresión o instrucción. Los operadores que toman un operando, como el operador de incremento (`++`) o `new`, se conocen como operadores *unarios* . Los operadores que toman dos operandos, como los operadores aritméticos (`+`,`-`,`*`,`/`) se conocen como operadores *binarios* . Un operador, el operador condicional (`?:`), toma tres operandos y es el único operador ternario de C#.  
  
 La instrucción de C# siguiente contiene un solo operador unario y un único operando. El operador de incremento, `++`, modifica el valor del operando `y`.  
  
 [!code-csharp[csProgGuideStatements#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#5)]  
  
 La instrucción de C# siguiente contiene dos operadores binarios, cada uno con dos operandos. El operador de asignaciones, `=`, tiene la variable de entero `y` y la expresión `2 + 3` como operandos. La propia expresión `2 + 3` está compuesta del operador de suma y dos operandos, `2` y `3`.  
  
 [!code-csharp[csProgGuideStatements#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#6)]  
  
Un operando puede ser una expresión válida que se compone de código de una longitud indeterminada y puede incluir un número cualquiera de subexpresiones. En una expresión que contiene varios operadores, el orden de aplicación de estos viene determinado por la *prioridad de operador*, la *asociatividad*y los paréntesis.  

## <a name="operator-precedence"></a>Prioridad de operadores
  
Cada operador tiene una prioridad definida. En una expresión que contiene varios operadores con distintos niveles de prioridad, la prioridad de los operadores determina el orden en que estos se evalúan. Por ejemplo, la instrucción siguiente asigna 3 a `n1`:

```csharp
n1 = 11 - 2 * 4;
```

La multiplicación se ejecuta en primer lugar porque tiene prioridad sobre la resta.

Para obtener la lista completa de los operadores de C# ordenados por nivel de prioridad, vea [Operadores de C#](../../language-reference/operators/index.md).
  
## <a name="associativity"></a>asociatividad

 Cuando dos o más operadores con la misma prioridad están presentes en una expresión, se evalúan según su asociatividad. Los operadores asociativos a la izquierda se evalúan, por orden, de izquierda a derecha. Por ejemplo, `x * y / z` se evalúa como `(x * y) / z`. Los operadores asociativos a la derecha se evalúan, por orden, de derecha a izquierda. Por ejemplo, el operador de asignación es asociativo a la derecha. De lo contrario, el código siguiente produciría un error.  
  
```csharp  
int a, b, c;  
c = 1;  
// The following two lines are equivalent.  
a = b = c;  
a = (b = c);  
  
// The following line, which forces left associativity, causes an error.  
//(a = b) = c;  
```  
  
 Otro ejemplo sería el operador ternario ([?:](../../../csharp/language-reference/operators/conditional-operator.md)), que es asociativo a la derecha. La mayoría de los operadores binarios son asociativos a la izquierda.  
  
 Independientemente de que los operadores de una expresión sean asociativos a la izquierda o a la derecha, los operandos de cada expresión se evalúan primero, de izquierda a derecha. En los siguientes ejemplos se muestra el orden de evaluación de los operadores y los operandos.  
  
|Instrucción|Orden de evaluación|  
|---------------|-------------------------|  
|`a = b`|a, b, =|  
|`a = b + c`|a, b, c, +, =|  
|`a = b + c * d`|a, b, c, d, *, +, =|  
|`a = b * c + d`|a, b, c, *, d, +, =|  
|`a = b - c + d`|a, b, c, -, d, +, =|  
|`a += b -= c`|a, b, c, -=, +=|  
  
## <a name="adding-parentheses"></a>Agregar paréntesis

 Se puede cambiar el orden impuesto por la prioridad de operador y la asociatividad mediante el uso de paréntesis. Por ejemplo, `2 + 3 * 2` suele evaluarse como 8, porque los operadores de multiplicación tienen prioridad sobre los operadores de suma. Sin embargo, si se escribe la expresión como `(2 + 3) * 2`, la suma se evalúa antes que la multiplicación y el resultado es 10. En los siguientes ejemplos se muestra el orden de evaluación en las expresiones entre paréntesis. Como en ejemplos anteriores, los operandos se evalúan antes de aplicarse el operador.  
  
|Instrucción|Orden de evaluación|  
|---------------|-------------------------|  
|`a = (b + c) * d`|a, b, c, +, d, *, =|  
|`a = b - (c + d)`|a, b, c, d, +, -, =|  
|`a = (b + c) * (d - e)`|a, b, c, +, d, e, -, *, =|  
  
## <a name="operator-overloading"></a>Sobrecarga de operadores

Puede definir el comportamiento de algunos operadores para clases y estructuras personalizadas. Este proceso se conoce como *sobrecarga de operadores*. Para obtener más información, vea [Overloadable operators](overloadable-operators.md) (Operadores recargables) y el artículo sobre palabras clave [operator](../../language-reference/keywords/operator.md).
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Instrucciones, expresiones y operadores](index.md)
- [Operadores de C#](../../language-reference/operators/index.md)
