---
title: "And (Operador, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.And"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "And (operador) [Visual Basic]"
  - "AND bit a bit (operador) [Visual Basic]"
  - "comparación bit a bit"
  - "operadores bit a bit, AND (operador)"
  - "operador de conjunción"
  - "conjunción lógica"
  - "operadores [Visual Basic], bit a bit"
  - "operadores [Visual Basic], conjunción"
ms.assetid: 2ea711f3-439a-4c7c-9e3a-1ffe3b0d6046
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# And (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Realiza una conjunción lógica entre dos expresiones `Boolean` o una conjunción bit a bit entre dos expresiones numéricas.  
  
## Sintaxis  
  
```  
  
result = expression1 And expression2  
```  
  
## Elementos  
 `result`  
 Obligatorio.  Cualquier expresión numérica o de tipo `Boolean`.  Para la comparación booleana, `result` es la conjunción lógica de dos valores `Boolean`.  Para las operaciones bit a bit, `result` es un valor numérico que representa la conjunción bit a bit de dos modelos de bits numéricos.  
  
 `expression1`  
 Obligatorio.  Cualquier expresión numérica o de tipo `Boolean`.  
  
 `expression2`  
 Obligatorio.  Cualquier expresión numérica o de tipo `Boolean`.  
  
## Comentarios  
 Para la comparación booleana, `result` es `True` si y sólo si `expression1` y `expression2` se evalúan como `True`.  En la tabla siguiente se ilustra cómo se determina el argumento `result`.  
  
|Si el valor de `expression1` es:|Y `expression2` es|El valor de `result` es:|  
|--------------------------------------|------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  En una comparación booleana, el operador `And` evalúa siempre las dos expresiones, lo que podría incluir llamadas a procedimientos.  [AndAlso \(Operador\)](../../../visual-basic/language-reference/operators/andalso-operator.md) realiza un *cortocircuito*, lo que significa que si `expression1` es `False`, no se evalúa `expression2`.  
  
 Aplicado a valores numéricos, el operador `And` realiza una comparación bit a bit de los bits ubicados de manera idéntica en dos expresiones numéricas y establece el bit correspondiente en `result` de acuerdo con la siguiente tabla:  
  
|Si el bit de `expression1` es|Y el bit de `expression2` es...|El bit de `result` es|  
|-----------------------------------|-------------------------------------|---------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
>  Al tener los operadores lógicos y bit a bit una prioridad inferior a la de otros operadores aritméticos y relacionales, las operaciones bit a bit deben efectuarse entre paréntesis para garantizar unos resultados correctos.  
  
## Tipos de datos  
 Si los operandos constan de una expresión `Boolean` y una expresión numérica, Visual Basic convierte la expresión `Boolean` a un valor numérico \(–1 para `True` y 0 para `False`\), y realiza una operación bit a bit.  
  
 Para una comparación booleana, el tipo de datos del resultado es `Boolean`.  Para una comparación bit a bit, el tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`.  Vea la tabla "Comparaciones relacionales y bit a bit" en [Tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
> [!NOTE]
>  El operador `And` se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  Si el código utiliza este operador en una clase o estructura de este tipo, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el ejemplo siguiente se usa el operador `And` para realizar una conjunción lógica de dos expresiones.  El resultado será un valor de tipo `Boolean` que indicará si las dos expresiones son `True`.  
  
 [!code-vb[VbVbalrOperators#22](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/and-operator_1.vb)]  
  
 El ejemplo anterior genera unos resultados de `True` y `False`, respectivamente.  
  
## Ejemplo  
 En el ejemplo siguiente se usa el operador `And` para realizar una conjunción lógica entre cada uno de los bits de dos expresiones numéricas.  El bit en el modelo resultante se establece si están establecidos en 1 los bits correspondientes de los operandos.  
  
 [!code-vb[VbVbalrOperators#23](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/and-operator_2.vb)]  
  
 El ejemplo anterior genera unos resultados de 8, 2 y 0, respectivamente.  
  
## Vea también  
 [Operadores lógicos y operadores bit a bit](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [AndAlso \(Operador\)](../../../visual-basic/language-reference/operators/andalso-operator.md)   
 [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)