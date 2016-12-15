---
title: "* (Operador, Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.*"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "* (operador) [Visual Basic]"
  - "operadores aritméticos, multiplicación"
  - "operadores matemáticos"
  - "operador de multiplicación, sintaxis"
  - "operadores [Visual Basic], multiplicación"
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# * (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Multiplica dos números.  
  
## Sintaxis  
  
```  
  
number1 * number2  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`number1`|Obligatorio.  Cualquier expresión numérica.|  
|`number2`|Obligatorio.  Cualquier expresión numérica.|  
  
## Resultado  
 El resultado es el producto de `number1` y `number2`.  
  
## Tipos admitidos  
 Todos los tipos numéricos, incluidos los tipos de punto flotante, sin signo y `Decimal`.  
  
## Comentarios  
 El tipo de datos del resultado depende de los tipos de los operandos.  En la tabla siguiente se muestra cómo se determina el tipo de datos del resultado.  
  
|||  
|-|-|  
|Tipos de datos de operando|Tipo de datos de resultado|  
|Ambas expresiones son tipos de datos integrales \([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)\)|Un tipo de dato numérico adecuado para los tipos de datos de `number1` y `number2`.  Vea las tablas "Aritmética de enteros" en [Tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Ambas expresiones son [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`|  
|Ambas expresiones son [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`|  
|Una expresión es un tipo de datos de punto flotante \(`Single` o [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)\) pero no ambas `Single` \(observe que `Decimal` no es un tipo de datos de punto flotante\)|`Double`|  
  
 Si una expresión da como resultado [Nothing](../../../visual-basic/language-reference/nothing.md), se tratará como si fuera cero.  
  
## Sobrecarga  
 El operador `*` se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  Si el código utiliza este operador en una clase o estructura de este tipo, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En este ejemplo se usa el operador `*` para multiplicar dos números.  El resultado será el producto de dos operandos.  
  
 [!code-vb[VbVbalrOperators#4](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-operator_1.vb)]  
  
## Vea también  
 [\*\= \(Operador\)](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)   
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)