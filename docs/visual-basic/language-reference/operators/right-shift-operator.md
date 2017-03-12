---
title: "&gt;&gt; (Operador, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.>>"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - ">> (operador) [Visual Basic]"
  - "operadores de desplazamiento de bits"
  - "operador >>"
  - "operador >>"
  - "operadores de desplazamiento a la derecha"
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# &gt;&gt; (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Realiza un desplazamiento aritmético a la derecha en un modelo de bits.  
  
## Sintaxis  
  
```  
  
result = pattern >> amount  
```  
  
## Elementos  
 `result`  
 Obligatorio.  Valor numérico integral.  Resultado de desplazar el modelo de bits.  El tipo de datos es el mismo que el de `pattern`.  
  
 `pattern`  
 Obligatorio.  Expresión numérica integral.  Modelo de bits que se va a desplazar.  El tipo de datos debe ser un tipo entero \(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` o `ULong`\).  
  
 `amount`  
 Obligatorio.  Expresión numérica.  Número de bits que se va a desplazar el modelo de bits.  El tipo de datos debe ser `Integer` o ampliarse a `Integer`.  
  
## Comentarios  
 Los desplazamientos aritméticos no son circulares, lo que significa que los bits desplazados a un extremo del resultado no se vuelven a introducir en el otro extremo.  En un desplazamiento aritmético a la derecha, los bits desplazados más allá de la posición del bit situado más a la derecha se descartan y el bit \(con signo\) situado más a la izquierda se propaga a las posiciones vacías de los bits de la izquierda.  Esto significa que si `pattern` tiene un valor negativo, las posiciones vacías se establecen en uno y, en caso contrario, se establecen en cero.  
  
 Tenga en cuenta que los tipos de datos `Byte`, `UShort`, `UInteger` y `ULong` son sin signo, así que no hay ningún bit de signo para propagar.  Si `pattern` es de tipo sin signo, las posiciones vacías siempre se establecen en cero.  
  
 Para no desplazar más bits que los que pueda contener el resultado, Visual Basic enmascara el valor de `amount` con una máscara de tamaño correspondiente al tipo de datos de `pattern`.  El operador AND binario de estos valores se utiliza para la cantidad de desplazamiento.  La máscaras de tamaño son las siguientes:  
  
|Tipo de datos de `pattern`|Máscara de tamaño \(decimal\)|Máscara de tamaño \(hexadecimal\)|  
|--------------------------------|-----------------------------------|---------------------------------------|  
|`SByte`, `Byte`|7|&H00000007|  
|`Short`, `UShort`|15|&H0000000F|  
|`Integer`, `UInteger`|31|&H0000001F|  
|`Long`, `ULong`|63|&H0000003F|  
  
 Si `amount` es cero, el valor de `result` es idéntico al valor de `pattern`.  Si `amount` es negativo, se toma como un valor sin signo y se enmascara con la máscara de tamaño adecuada.  
  
 Los desplazamientos aritméticos nunca generan excepciones de desbordamiento.  
  
## Sobrecarga  
 El operador `>>` se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  Si el código utiliza este operador en una clase o estructura de este tipo, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el ejemplo siguiente se usa el operador `>>` para realizar desplazamientos aritméticos a la derecha en valores integrales.  El resultado tiene siempre el mismo tipo de datos que la expresión que se está desplazando.  
  
 [!code-vb[VbVbalrOperators#14](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/right-shift-operator_1.vb)]  
  
 Los resultados del ejemplo anterior son los siguientes:  
  
-   `result1` es 2560 \(0000 1010 0000 0000\).  
  
-   `result2` es 160 \(0000 0000 1010 0000\).  
  
-   `result3` es 2 \(0000 0000 0000 0010\).  
  
-   `result4` es 640 \(0000 0010 1000 0000\).  
  
-   `result5` es 0 \(se desplaza 15 posiciones a la derecha\).  
  
 La cantidad de desplazamiento de `result4` se calcula como 18 AND 15, lo que equivale a 2.  
  
 El ejemplo siguiente muestra los cambios aritméticos en un valor negativo.  
  
 [!code-vb[VbVbalrOperators#55](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/right-shift-operator_2.vb)]  
  
 Los resultados del ejemplo anterior son los siguientes:  
  
-   `negresult1` es \-512 \(1111 1110 0000 0000\).  
  
-   `negresult2` es \-1 \(se propaga el bit de signo\).  
  
## Vea también  
 [Operadores de desplazamiento](../../../visual-basic/language-reference/operators/bit-shift-operators.md)   
 [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [\>\>\= \(Operador\)](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)