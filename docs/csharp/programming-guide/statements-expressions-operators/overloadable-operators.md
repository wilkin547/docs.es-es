---
title: "Operadores sobrecargables (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, sobrecarga de operadores"
  - "sobrecarga de operadores [C#]"
ms.assetid: 390d9d01-79fc-40ab-9ed3-0bf448da1b6a
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operadores sobrecargables (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

C\# permite que los tipos definidos por el usuario sobrecarguen operadores al definir funciones miembro estáticas mediante la palabra clave [operator](../../../csharp/language-reference/keywords/operator.md).  Sin embargo, no todos los operadores se pueden sobrecargar y algunos presentan restricciones, como se muestra en esta tabla:  
  
|Operadores|Posibilidad de sobrecarga|  
|----------------|-------------------------------|  
|[\+](../../../csharp/language-reference/operators/addition-operator.md), [\-](../../../csharp/language-reference/operators/subtraction-operator.md), [\!](../../../csharp/language-reference/operators/logical-negation-operator.md), [~](../../../csharp/language-reference/operators/bitwise-complement-operator.md), [\+\+](../../../csharp/language-reference/operators/increment-operator.md), [\-\-](../../../csharp/language-reference/operators/decrement-operator.md), [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md)|Estos operadores unarios se pueden sobrecargar.|  
|[\+](../../../csharp/language-reference/operators/addition-operator.md), [\-](../../../csharp/language-reference/operators/subtraction-operator.md), [\*](../../../csharp/language-reference/operators/multiplication-operator.md), [\/](../../../csharp/language-reference/operators/division-operator.md), [%](../../../csharp/language-reference/operators/modulus-operator.md), [&](../../../csharp/language-reference/operators/and-operator.md),                               [&#124;](../../../csharp/language-reference/operators/or-operator.md) , [^](../../../csharp/language-reference/operators/xor-operator.md), [\<\<](../../../csharp/language-reference/operators/left-shift-operator.md), [\>\>](../../../csharp/language-reference/operators/right-shift-operator.md)|Estos operadores binarios se pueden sobrecargar.|  
|[\=\=](../../../csharp/language-reference/operators/equality-comparison-operator.md), [\!\=](../../../csharp/language-reference/operators/not-equal-operator.md), [\<](../../../csharp/language-reference/operators/less-than-operator.md), [\>](../../../csharp/language-reference/operators/greater-than-operator.md), [\<\=](../../../csharp/language-reference/operators/less-than-equal-operator.md), [\>\=](../../../csharp/language-reference/operators/greater-than-equal-operator.md)|Los operadores de comparación se pueden sobrecargar \(pero consulte la nota que aparece a continuación de la tabla\).|  
|[&&](../../../csharp/language-reference/operators/conditional-and-operator.md), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)|Los operadores lógicos condicionales no se pueden sobrecargar, pero se evalúan mediante `&` y                               `&#124;` , que se pueden sobrecargar.|  
|[&#91;&#93;](../../../csharp/language-reference/operators/index-operator.md)|El operador de indización de matriz no se puede sobrecargar, pero es posible definir indizadores.|  
|[\(T\)x](../../../csharp/language-reference/operators/invocation-operator.md)|El operador de conversión no se puede sobrecargar, pero es posible definir operadores de conversión nuevos \(vea [explicit](../../../csharp/language-reference/keywords/explicit.md) e [implicit](../../../csharp/language-reference/keywords/implicit.md)\).|  
|[\+\=](../../../csharp/language-reference/operators/addition-assignment-operator.md), [\-\=](../../../csharp/language-reference/operators/subtraction-assignment-operator-1.md), [\*\=](../../../csharp/language-reference/operators/multiplication-assignment-operator.md), [\/\=](../../../csharp/language-reference/operators/subtraction-assignment-operator.md), [%\=](../../../csharp/language-reference/operators/modulus-assignment-operator.md), [&\=](../../../csharp/language-reference/operators/and-assignment-operator.md), [&#124;\=](../../../csharp/language-reference/operators/or-assignment-operator.md), [^\=](../../../csharp/language-reference/operators/xor-assignment-operator.md), [\<\<\=](../../../csharp/language-reference/operators/left-shift-assignment-operator.md), [\>\>\=](../../../csharp/language-reference/operators/right-shift-assignment-operator.md)|Los operadores de asignación no se pueden sobrecargar, pero `+=`, por ejemplo, se evalúa con `+`, que se puede sobrecargar.|  
|[\=](../../../csharp/language-reference/operators/assignment-operator.md), [.](../../../csharp/language-reference/operators/member-access-operator.md), [?:](../../../csharp/language-reference/operators/conditional-operator.md), [??](../../../csharp/language-reference/operators/null-conditional-operator.md), [\-\>](../../../csharp/language-reference/operators/dereference-operator.md), [\=\>](../../../csharp/language-reference/operators/lambda-operator.md), [f\(x\)](../../../csharp/language-reference/operators/invocation-operator.md), [as](../../../csharp/language-reference/keywords/as.md), [checked](../../../csharp/language-reference/keywords/checked.md), [unchecked](../../../csharp/language-reference/keywords/unchecked.md), [default](../../../csharp/programming-guide/generics/default-keyword-in-generic-code.md), [delegate](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), [is](../../../csharp/language-reference/keywords/is.md), [new](../../../csharp/language-reference/keywords/new.md), [sizeof](../../../csharp/language-reference/keywords/sizeof.md), [typeof](../../../csharp/language-reference/keywords/typeof.md)|Estos operadores no se pueden sobrecargar.|  
  
> [!NOTE]
>  Los operadores de comparación, si se sobrecargan, deben sobrecargarse en pares; es decir, si `==` está sobrecargado, también debe estarlo `!=`.  Esto también ocurre a la inversa, y es similar para `<` y `>`, y para `<=` y `>=`.  
  
 Para sobrecargar un operador en una clase personalizada es necesario crear un método en la clase con la firma correcta.  El método se debe denominar "operator X", donde X es el nombre o símbolo del operador que se sobrecarga.  Los operadores unarios tienen un parámetro y los operadores binarios tienen dos parámetros.  En cada caso, un parámetro debe ser del mismo tipo que la clase o estructura que declara el operador.  
  
```c#  
public static Complex operator +(Complex c1, Complex c2)  
    {  
        Return new Complex(c1.real + c2.real, c1.imaginary + c2.imaginary);  
    }  
  
```  
  
 Es habitual tener definiciones que simplemente devuelven de inmediato el resultado de una expresión.  Hay un acceso directo de sintaxis que usa `=>` para estas situaciones.  
  
```c#  
public static Complex operator +(Complex c1, Complex c2) =>  
        new Complex(c1.real + c2.real, c1.imaginary + c2.imaginary);  
  
    // Override ToString() to display a complex number   
    // in the traditional format:  
    public override string ToString() => $"{this.real} + {this.imaginary}";  
  
```  
  
 Para obtener más información, consulte [Cómo: Utilizar la sobrecarga de operadores para crear una clase de números complejos](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-operator-overloading-to-create-a-complex-number-class.md).  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Instrucciones, expresiones y operadores](../../../csharp/programming-guide/statements-expressions-operators/index.md)   
 [Operadores](../../../csharp/programming-guide/statements-expressions-operators/operators.md)   
 [operadores de C\#](../../../csharp/language-reference/operators/index.md)   
 [¿Por qué los operadores sobrecargados son siempre estáticos en C\#?](http://go.microsoft.com/fwlink/?LinkId=112383)