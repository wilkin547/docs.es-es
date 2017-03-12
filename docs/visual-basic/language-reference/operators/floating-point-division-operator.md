---
title: "/ (Operador, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb./"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/ (operador) [Visual Basic]"
  - "operadores aritméticos, división"
  - "operador de división, punto flotante"
  - "operador de división, sintaxis"
  - "división, entre cero"
  - "números de punto flotante, operador de división"
  - "operadores matemáticos"
  - "operadores [Visual Basic], aritméticos"
  - "operadores [Visual Basic], división"
  - "barra diagonal (/): operador"
  - "cero, división por cero"
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# / (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Divide dos números y devuelve un resultado de punto flotante.  
  
## Sintaxis  
  
```  
  
expression1 / expression2  
```  
  
## Elementos  
 `expression1`  
 Obligatorio.  Cualquier expresión numérica.  
  
 `expression2`  
 Obligatorio.  Cualquier expresión numérica.  
  
## Tipos admitidos  
 Todos los tipos numéricos, incluidos los tipos de punto flotante, sin signo y `Decimal`.  
  
## Resultado  
 El resultado es el cociente completo de `expression1` dividido por `expression2`, incluido cualquier resto.  
  
 [\\ \(Operador\)](../../../visual-basic/language-reference/operators/integer-division-operator.md) devuelve el cociente entero, que omite el resto.  
  
## Comentarios  
 El tipo de datos del resultado depende de los tipos de los operandos.  En la tabla siguiente se muestra cómo se determina el tipo de datos del resultado.  
  
|Tipos de datos de operando|Tipo de datos de resultado|  
|--------------------------------|--------------------------------|  
|Ambas expresiones son tipos de datos integrales \([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)\)|`Double`|  
|Una expresión es un tipo de datos [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) numérico y la otra no es [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Single`|  
|Una expresión es un tipo de datos [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) y la otra no es [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) ni [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Decimal`|  
|Cualquier expresión es un tipo de datos [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
  
 Antes de que se realice la división, cualquier expresión numérica entera se amplía a `Double`.  Si asigna el resultado a un tipo de datos entero, Visual Basic intenta convertir el resultado de `Double` a ese tipo.  Esto puede producir una excepción si el resultado no se ajusta a ese tipo.  Vea en particular "División por cero intentada" en esta página de Ayuda.  
  
 Si se evalúa `expression1` o `expression2` como [Nothing](../../../visual-basic/language-reference/nothing.md), se trata como si fuese cero.  
  
## Intento de dividir por cero  
 Si se evalúa `expression2` como cero, el operador `/` se comporta de manera diferente para los distintos tipos de datos de operando.  En la siguiente tabla se muestran los posibles comportamientos.  
  
|Tipos de datos de operando|Comportamiento si `expression2` es cero|  
|--------------------------------|---------------------------------------------|  
|Punto flotante \(`Single` o `Double`\)|Devuelve infinito \(<xref:System.Double.PositiveInfinity> o <xref:System.Double.NegativeInfinity>\) o <xref:System.Double.NaN> \(no es un número\) si `expression1` también es cero|  
|`Decimal`|Produce <xref:System.DivideByZeroException>|  
|Entero \(con signo o sin signo\)|La conversión intentada recuperando el tipo entero produce una <xref:System.OverflowException> porque los tipos enteros no pueden aceptar <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity> ni <xref:System.Double.NaN>|  
  
> [!NOTE]
>  El operador `/` se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  Si el código utiliza este operador en una clase o estructura de este tipo, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En este ejemplo se usa el operador `/` para realizar una división de punto flotante.  El resultado será el cociente de ambos operandos.  
  
 [!code-vb[VbVbalrOperators#16](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/floating-point-division-_1_1.vb)]  
  
 Las expresiones en el ejemplo anterior devuelven valores de 2,5 y 3,333333.  Observe que el resultado es siempre de punto flotante \(`Double`\), aunque ambos operandos sean constantes enteras.  
  
## Vea también  
 [\/\= \(Operador\)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)   
 [\\ \(Operador\)](../../../visual-basic/language-reference/operators/integer-division-operator.md)   
 [Tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)   
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)