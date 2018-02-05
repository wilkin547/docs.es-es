---
title: "Operadores sobrecargables (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, operator overloading
- operator overloading [C#]
ms.assetid: 390d9d01-79fc-40ab-9ed3-0bf448da1b6a
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7487f398ec412c4a302054ade20800f431e2c793
ms.sourcegitcommit: 22a48b64a0150a60b00b4fc4d8c62cde7f1670c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2018
---
# <a name="overloadable-operators-c-programming-guide"></a>Operadores sobrecargables (Guía de programación de C#)

C# permite que los tipos definidos por el usuario sobrecarguen operadores al definir funciones miembro estáticas mediante la palabra clave [operator](../../../csharp/language-reference/keywords/operator.md). Sin embargo, no todos los operadores se pueden sobrecargar y algunos presentan restricciones, como se muestra en esta tabla:

| Operadores | Posibilidad de sobrecarga |
| --------- | --------------- |
|[+](../../../csharp/language-reference/operators/addition-operator.md), [-](../../../csharp/language-reference/operators/subtraction-operator.md), [!](../../../csharp/language-reference/operators/logical-negation-operator.md), [~](../../../csharp/language-reference/operators/bitwise-complement-operator.md), [++](../../../csharp/language-reference/operators/increment-operator.md), [--](../../../csharp/language-reference/operators/decrement-operator.md), [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md)|Estos operadores unarios se pueden sobrecargar.|
|[+](../../../csharp/language-reference/operators/addition-operator.md), [-](../../../csharp/language-reference/operators/subtraction-operator.md), [\*](../../../csharp/language-reference/operators/multiplication-operator.md), [/](../../../csharp/language-reference/operators/division-operator.md), [%](../../../csharp/language-reference/operators/modulus-operator.md), [&](../../../csharp/language-reference/operators/and-operator.md), [&#124;](../../../csharp/language-reference/operators/or-operator.md), [^](../../../csharp/language-reference/operators/xor-operator.md), [\<\<](../../../csharp/language-reference/operators/left-shift-operator.md), [>>](../../../csharp/language-reference/operators/right-shift-operator.md)|Estos operadores binarios se pueden sobrecargar.|
|[==](../../../csharp/language-reference/operators/equality-comparison-operator.md), [!=](../../../csharp/language-reference/operators/not-equal-operator.md), [\<](../../../csharp/language-reference/operators/less-than-operator.md), [>](../../../csharp/language-reference/operators/greater-than-operator.md), [\<=](../../../csharp/language-reference/operators/less-than-equal-operator.md), [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md)|Los operadores de comparación se pueden sobrecargar (pero consulte la nota que aparece a continuación de la tabla).|
|[&&](../../../csharp/language-reference/operators/conditional-and-operator.md), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)|Los operadores lógicos condicionales no se pueden sobrecargar, pero se evalúan mediante `&` y <code>&#124;</code>, que se pueden sobrecargar.|
|[&#91;&#93;](../../../csharp/language-reference/operators/index-operator.md)|El operador de indización de matriz no se puede sobrecargar, pero es posible definir indizadores.|
|[(T)x](../../../csharp/language-reference/operators/invocation-operator.md)|El operador de conversión no se puede sobrecargar, pero es posible definir operadores de conversión nuevos (vea [explicit](../../../csharp/language-reference/keywords/explicit.md) e [implicit](../../../csharp/language-reference/keywords/implicit.md)).|
|[+=](../../../csharp/language-reference/operators/addition-assignment-operator.md), [-=](../../../csharp/language-reference/operators/subtraction-assignment-operator.md), [\*=](../../../csharp/language-reference/operators/multiplication-assignment-operator.md), [/=](../../../csharp/language-reference/operators/division-assignment-operator.md), [%=](../../../csharp/language-reference/operators/modulus-assignment-operator.md), [&=](../../../csharp/language-reference/operators/and-assignment-operator.md), [&#124;=](../../../csharp/language-reference/operators/or-assignment-operator.md), [^=](../../../csharp/language-reference/operators/xor-assignment-operator.md), [\<\<=](../../../csharp/language-reference/operators/left-shift-assignment-operator.md), [>>=](../../../csharp/language-reference/operators/right-shift-assignment-operator.md)|Los operadores de asignación no se pueden sobrecargar, pero `+=`, por ejemplo, se evalúa con `+`, que se puede sobrecargar.|
|[=](../../../csharp/language-reference/operators/assignment-operator.md), [.](../../../csharp/language-reference/operators/member-access-operator.md), [?:](../../../csharp/language-reference/operators/conditional-operator.md), [??](../../../csharp/language-reference/operators/null-conditional-operator.md), [->](../../../csharp/language-reference/operators/dereference-operator.md), [=>](../../../csharp/language-reference/operators/lambda-operator.md), [f(x)](../../../csharp/language-reference/operators/invocation-operator.md), [as](../../../csharp/language-reference/keywords/as.md), [checked](../../../csharp/language-reference/keywords/checked.md), [unchecked](../../../csharp/language-reference/keywords/unchecked.md), [default](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md), [delegate](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), [is](../../../csharp/language-reference/keywords/is.md), [new](../../../csharp/language-reference/keywords/new.md), [sizeof](../../../csharp/language-reference/keywords/sizeof.md), [typeof](../../../csharp/language-reference/keywords/typeof.md)|Estos operadores no se pueden sobrecargar.|

> [!NOTE]
> Los operadores de comparación, si se sobrecargan, deben sobrecargarse en pares; es decir, si `==` está sobrecargado, también debe estarlo `!=`. Esto también ocurre a la inversa, donde la sobrecarga de `!=` requiere una sobrecarga de `==`. Lo mismo puede ocurrir para los operadores de comparación `<` y `>` y para `<=` y `>=`.

Para sobrecargar un operador en una clase personalizada es necesario crear un método en la clase con la firma correcta. El método se debe denominar "operator X", donde X es el nombre o símbolo del operador que se sobrecarga. Los operadores unarios tienen un parámetro y los operadores binarios tienen dos parámetros. En cada caso, un parámetro debe ser del mismo tipo que la clase o estructura que declara el operador.

```csharp
public static Complex operator +(Complex c1, Complex c2)
{
    return new Complex(c1.real + c2.real, c1.imaginary + c2.imaginary);
}
```

Es habitual tener definiciones que simplemente devuelven de inmediato el resultado de una expresión.  Hay un acceso directo de sintaxis que usa `=>` para estas situaciones.

```csharp
public static Complex operator +(Complex c1, Complex c2) =>
        new Complex(c1.real + c2.real, c1.imaginary + c2.imaginary);
  
// Override ToString() to display a complex number in the traditional format:
public override string ToString() => $"{this.real} + {this.imaginary}";
```

Para obtener más información, vea [Cómo: Usar la sobrecarga de operadores para crear una clase de números complejos](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-operator-overloading-to-create-a-complex-number-class.md).

## <a name="see-also"></a>Vea también

[Guía de programación de C#](../../../csharp/programming-guide/index.md)  
[Instrucciones, expresiones y operadores](../../../csharp/programming-guide/statements-expressions-operators/index.md)  
[Operadores](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
[Operadores de C#](../../../csharp/language-reference/operators/index.md)  
[Why are overloaded operators always static in C#?](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/) (¿Por qué los operadores sobrecargados son siempre estáticos en C#?)
