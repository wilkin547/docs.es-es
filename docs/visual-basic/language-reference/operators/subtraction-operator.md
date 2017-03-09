---
title: "- (Operador, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Negate"
  - "vb.-"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "- (operador) [Visual Basic]"
  - "operadores aritméticos, resta"
  - "operador de diferencia"
  - "operadores matemáticos"
  - "minus (operador) [Visual Basic]"
  - "operador de negación"
  - "operadores [Visual Basic], aritméticos"
  - "operadores [Visual Basic], diferencia"
  - "operadores [Visual Basic], negación"
  - "operadores [Visual Basic], resta"
  - "operador de resta, sintaxis"
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# - (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Devuelve la diferencia entre dos expresiones numéricas o el valor negativo de una expresión numérica.  
  
## Sintaxis  
  
```  
  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## Elementos  
 `expression1`  
 Obligatorio.  Cualquier expresión numérica.  
  
 `expression2`  
 Se requiere al menos que el operador `–` esté calculando un valor negativo.  Cualquier expresión numérica.  
  
## Resultado  
 El resultado es la diferencia entre `expression1` y `expression2` o el valor con signo negativo de `expression1`.  
  
 El tipo de datos resultante es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`.  Vea las tablas "Aritmética de enteros" en [Tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## Tipos admitidos  
 Todos los tipos numéricos.  Esto incluye los tipos sin signo, los tipos de punto flotante y los tipos `Decimal`.  
  
## Comentarios  
 En la sintaxis mostrada con anterioridad, la primera vez que se usa, el operador `–` es el operador de resta aritmética *binario* que halla la diferencia entre dos expresiones numéricas.  
  
 La segunda vez que se usa, el operador `–` es el operador de negación *unario* que halla el valor negativo de una expresión.  En este sentido, la negación invierte el signo de `expression1`, por lo que el resultado es positivo si `expression1` es negativo.  
  
 Si alguna expresión se evalúa como [Nothing](../../../visual-basic/language-reference/nothing.md), el operador `–` la trata como si fuera cero.  
  
> [!NOTE]
>  El operador `–` se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  Si el código usa este operador en una clase o estructura de este tipo, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza el operador `–` para calcular y devolver la diferencia entre dos números; y, a continuación, para negar un número.  
  
 [!code-vb[VbVbalrOperators#10](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/subtraction-operator_1.vb)]  
  
 Tras la ejecución de estas instrucciones, `binaryResult` contiene 124.45 y `unaryResult` contiene \-334.90.  
  
## Vea también  
 [\-\= \(Operador\)](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)   
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)