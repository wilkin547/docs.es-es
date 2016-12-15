---
title: "&lt;&lt; (Operador, Visual Basic) | Microsoft Docs"
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
  - "vb.<<"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "<< (operador) [Visual Basic]"
  - "operadores de desplazamiento de bits"
  - "operador <<, operador de desplazamiento a la izquierda en Visual Basic"
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;&lt; (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Realiza un desplazamiento aritmético a la izquierda en un modelo de bits.  
  
## Sintaxis  
  
```  
  
result = pattern << amount  
```  
  
## Elementos  
 `result`  
 Obligatorio.  Valor numérico integral.  Resultado de desplazar el modelo de bits.  El tipo de datos es el mismo que el de `pattern`.  
  
 `pattern`  
 Obligatorio.  Expresión numérica integral.  Modelo de bits que se va a desplazar.  El tipo de datos debe ser un tipo entero \(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` o `ULong`\).  
  
 `amount`  
 Obligatorio.  Expresión numérica.  Número de bits que se va a desplazar el modelo de bits.  El tipo de datos debe ser `Integer` o ampliarse a `Integer`.  
  
## Comentarios  
 Los desplazamientos aritméticos no son circulares, lo que significa que los bits desplazados a un extremo del resultado no se vuelven a introducir en el otro extremo.  En un desplazamiento aritmético a la izquierda, los bits desplazados más allá del intervalo del tipo de datos del resultado se descartan y las posiciones vacías de los bits de la derecha se establecen en cero.  
  
 Para no desplazar más bits que los que pueda contener el resultado, Visual Basic enmascara el valor de `amount` con una máscara de tamaño correspondiente al tipo de datos de `pattern`.  El operador AND binario de estos valores se utiliza para la cantidad de desplazamiento.  La máscaras de tamaño son las siguientes:  
  
|Tipo de datos de `pattern`|Máscara de tamaño \(decimal\)|Máscara de tamaño \(hexadecimal\)|  
|--------------------------------|-----------------------------------|---------------------------------------|  
|`SByte`, `Byte`|7|&H00000007|  
|`Short`, `UShort`|15|&H0000000F|  
|`Integer`, `UInteger`|31|&H0000001F|  
|`Long`, `ULong`|63|&H0000003F|  
  
 Si `amount` es cero, el valor de `result` es idéntico al valor de `pattern`.  Si `amount` es negativo, se toma como un valor sin signo y se enmascara con la máscara de tamaño adecuada.  
  
 Los desplazamientos aritméticos nunca generan excepciones de desbordamiento.  
  
> [!NOTE]
>  El operador `<<` se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  Si el código usa este operador en una clase o estructura de este tipo, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza el operador `<<` para realizar un desplazamiento aritmético a la izquierda en valores integrales.  El resultado tiene siempre el mismo tipo de datos que la expresión que se está desplazando.  
  
 [!code-vb[VbVbalrOperators#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-operator_1.vb)]  
  
 Los resultados del ejemplo anterior son los siguientes:  
  
-   `result1` es 192 \(0000 0000 1100 0000\).  
  
-   `result2` es 3072 \(0000 1100 0000 0000\).  
  
-   `result3` es \-32768 \(1000 0000 0000 0000\).  
  
-   `result4` es 384 \(0000 0001 1000 0000\).  
  
-   `result5` es 0 \(se desplaza 15 posiciones a la izquierda\).  
  
 La cantidad de desplazamiento de `result4` se calcula como 17 AND 15, lo que equivale a 1.  
  
## Vea también  
 [Operadores de desplazamiento](../../../visual-basic/language-reference/operators/bit-shift-operators.md)   
 [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [\<\<\= \(Operador\)](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)