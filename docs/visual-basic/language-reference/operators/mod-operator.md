---
title: "Mod (Operador, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Mod"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "resto (operador Mod)"
  - "operador de división, operador Mod"
  - "operador modulus, Visual Basic"
  - "Mod (operador) [Visual Basic]"
  - "operadores [Visual Basic], división"
  - "operadores aritméticos, Mod"
  - "operadores matemáticos"
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Mod (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Divide dos números y sólo devuelve el resto.  
  
## Sintaxis  
  
```  
  
number1 Mod number2  
```  
  
## Elementos  
 `number1`  
 Requerido.  Cualquier expresión numérica.  
  
 `number2`  
 Requerido.  Cualquier expresión numérica.  
  
## Tipos admitidos  
 Todos los tipos numéricos.  Esto incluye los tipos sin signo, los tipos de punto flotante y los tipos `Decimal`.  
  
## Resultado  
 El resultado es el resto que queda después de dividir `number1` entre `number2`.  Por ejemplo, la expresión `14 Mod 4` se evalúa como 2.  
  
## Comentarios  
 Si `number1` o `number2` es un valor de coma flotante, se devuelve el resto en punto flotante de la división.  El tipo de datos del resultado es el tipo de datos más pequeño que puede contener todos los valores posibles que resultan de la división con los tipos de datos de `number1` y `number2`.  
  
 Si se evalúa `number1` o `number2` como [Nothing](../../../visual-basic/language-reference/nothing.md), se trata como si fuese cero.  
  
 Los operadores relacionados son los siguientes:  
  
-   [\\ \(Operador\)](../../../visual-basic/language-reference/operators/integer-division-operator.md) devuelve el cociente entero de una división.  Por ejemplo, la expresión `14 \ 4` se evalúa como 3.  
  
-   El [\/ \(Operador\)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) devuelve el cociente completo, incluso el resto, como un número en punto flotante.  Por ejemplo, la expresión `14 / 4` se evalúa como 3,5.  
  
## Intento de dividir por cero  
 Si `number2` se evalúa como cero, el comportamiento del operador `Mod` depende del tipo de datos de los operandos.  Una división de enteros produce una excepción <xref:System.DivideByZeroException>.  Una división de punto flotante devuelve <xref:System.Double.NaN>.  
  
## Fórmula equivalente  
 La expresión `a Mod b` es equivalente a cualquiera de las fórmulas siguientes:  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## Imprecisión de punto flotante  
 Cuando trabaje con números de punto flotante, tenga presente que no siempre tienen una representación precisa en memoria.  Esto podría conducir a resultados inesperados en ciertas operaciones, como la comparación de valores y el operador `Mod`.  Para obtener más información, vea [Solucionar problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## Sobrecarga  
 El operador `Mod` se puede *sobrecargar*, lo que significa que una clase o estructura pueden volver a definir su comportamiento.  Si su código aplica `Mod` a una instancia de una clase o estructura que incluye este tipo de sobrecarga, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el ejemplo siguiente se usa el operador `Mod` para dividir dos números y devolver únicamente el resto.  Si uno de ellos es un número de punto flotante, el resto resultante también será un número punto flotante.  
  
 [!code-vb[VbVbalrOperators#31](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/mod-operator_1.vb)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra la imprecisión potencial de los operandos de punto flotante.  En la primera instrucción, los operandos son `Double`, y 0.2 es una fracción binaria de recursividad infinita cuyo valor almacenado es 0.20000000000000001.  En la segunda instrucción, el carácter de tipo literal `D` obliga a que los dos operandos sean `Decimal`, y 0.2 tiene una representación precisa.  
  
 [!code-vb[VbVbalrOperators#32](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/mod-operator_2.vb)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>   
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>   
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Solucionar problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [\\ \(Operador\)](../../../visual-basic/language-reference/operators/integer-division-operator.md)