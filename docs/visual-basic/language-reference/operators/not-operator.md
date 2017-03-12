---
title: "Not (Operador, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Not"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "comparación bit a bit"
  - "operadores bit a bit, NOT (operador)"
  - "expresiones booleanas, negar"
  - "inversión de valores de bits en variables"
  - "negación lógica"
  - "operador de negación"
  - "Not (operador) [Visual Basic]"
  - "operadores [Visual Basic], bit a bit"
  - "operadores [Visual Basic], negación"
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Not (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Lleva a cabo o la negación lógica de una expresión de tipo `Boolean` o la negación bit a bit de una numérica.  
  
## Sintaxis  
  
```  
  
result = Not expression  
```  
  
## Elementos  
 `result`  
 Obligatorio.  Cualquier expresión numérica o de tipo `Boolean`.  
  
 `expression`  
 Obligatorio.  Cualquier expresión numérica o de tipo `Boolean`.  
  
## Comentarios  
 En la siguiente tabla se muestra cómo se determina `result` cuando las expresiones son de tipo `Boolean`:  
  
|Si el valor de `expression` es:|El valor de `result` es:|  
|-------------------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 En las expresiones numéricas, el operador `Not` invierte los valores de bits de las expresiones numéricas y establece el bit correspondiente en `result` de acuerdo con la siguiente tabla:  
  
|Si el bit de `expression` es|El bit de `result` es|  
|----------------------------------|---------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
>  Dado que los operadores lógicos y los operadores bit a bit tienen una prioridad inferior a la de otros operadores aritméticos y relacionales, las operaciones bit a bit deben incluirse entre paréntesis para garantizar una correcta ejecución.  
  
## Tipos de datos  
 En una negación booleana, el tipo de datos del resultado es `Boolean`.  En una negación bit a bit, el tipo de datos del resultado es el mismo que el de `expression`.  Sin embargo, si la expresión es `Decimal`, el resultado es `Long`.  
  
## Sobrecarga  
 El operador `Not` se puede *sobrecargar*, lo que significa que una clase o una estructura puede definir de nuevo su comportamiento cuando su operando tiene el tipo de dicha clase o estructura.  Si el código utiliza este operador en una clase o estructura de este tipo, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza el operador `Not` para llevar a cabo la negación lógica de una expresión de tipo `Boolean`.  El resultado es un valor `Boolean` que representa el inverso del valor de la expresión.  
  
 [!code-vb[VbVbalrOperators#33](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/not-operator_1.vb)]  
  
 En el ejemplo anterior se generan los resultados `False` y `True`, respectivamente.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza el operador `Not` para llevar a cabo la negación lógica de los bits individuales de una expresión numérica.  El bit en el modelo resultante se establecerá en el valor inverso del bit correspondiente en el modelo del operando, incluido el bit correspondiente al signo.  
  
 [!code-vb[VbVbalrOperators#34](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/not-operator_2.vb)]  
  
 En el ejemplo anterior se generan los resultados –11, –9 y –7, respectivamente.  
  
## Vea también  
 [Operadores lógicos y operadores bit a bit](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)