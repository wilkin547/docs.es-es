---
title: "\ (Operador, Visual Basic) | Microsoft Docs"
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
  - "vb.\"
  - "\"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "\ (operador) [Visual Basic]"
  - "operadores aritméticos, división"
  - "barra diagonal inversa (\) [Visual Basic]"
  - "operador de división, enteros"
  - "división, entre cero"
  - "operador de división de número entero"
  - "cociente entero"
  - "operadores matemáticos"
  - "cocientes, enteros"
  - "truncamiento, división de enteros"
  - "cero, división por cero"
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# \ (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Divide dos números y devuelve un resultado de número entero.  
  
## Sintaxis  
  
```  
  
expression1 \ expression2  
```  
  
## Elementos  
 `expression1`  
 Obligatorio.  Cualquier expresión numérica.  
  
 `expression2`  
 Obligatorio.  Cualquier expresión numérica.  
  
## Tipos admitidos  
 Todos los tipos numéricos, incluidos los tipos de punto flotante, sin signo y `Decimal`.  
  
## Resultado  
 El resultado es el cociente entero de `expression1` dividido por `expression2` que descarta cualquier resto y conserva sólo la parte entera.  Esto se conoce como *truncado*.  
  
 El tipo de datos resultante es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`.  Vea las tablas "Aritmética de enteros" en [Tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
 [\/ \(Operador\)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) devuelve el cociente completo que conserva el resto en la parte decimal.  
  
## Comentarios  
 Antes de realizar la división, Visual Basic intenta convertir cualquier expresión numérica de punto flotante en `Long`.  Si `Option Strict` es `On`, se produce un error del compilador.  Si `Option Strict` es `Off`, es posible que se produzca <xref:System.OverflowException> si el valor está fuera del intervalo de [Long \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/long-data-type.md).  La conversión a `Long` también está sujeta al *redondeo bancario*.  Para obtener más información, vea "Partes decimales" en [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Si se evalúa `expression1` o `expression2` como [Nothing](../../../visual-basic/language-reference/nothing.md), se trata como si fuese cero.  
  
## Intento de dividir por cero  
 Si se evalúa `expression2` a cero, el operador `\` produce una excepción <xref:System.DivideByZeroException>.  Esto es verdad para todos los tipos de datos numéricos de los operandos.  
  
> [!NOTE]
>  El operador `\` se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  Si el código utiliza este operador en una clase o estructura de este tipo, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el siguiente ejemplo se usa el operador `\` para realizar una división de entero.  El resultado será un número entero que representa el cociente entero de ambos operandos, con el resto descartado.  
  
 [!code-vb[VbVbalrOperators#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/integer-division-operator_1.vb)]  
  
 Las expresiones en el ejemplo anterior devuelven valores de 2, 3, 33 y \-22 respectivamente.  
  
## Vea también  
 [\\\= \(Operador\)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)   
 [\/ \(Operador\)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)   
 [Option Strict \(Instrucción\)](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)