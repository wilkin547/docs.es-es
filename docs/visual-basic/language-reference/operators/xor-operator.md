---
title: "Xor (Operador, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Xor"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "comparación bit a bit"
  - "operadores bit a bit, XOR (operador)"
  - "operador de exclusión"
  - "OR exclusivo (operador)"
  - "exclusión lógica"
  - "operadores [Visual Basic], bit a bit"
  - "operadores [Visual Basic], or exclusivos"
  - "Xor (palabra clave)"
  - "Xor (operador) [Visual Basic]"
ms.assetid: 036000a9-3934-4e7f-a9d0-a816de3d84a6
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Xor (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Realiza una exclusión lógica entre dos expresiones de tipo `Boolean` o bien una exclusión bit a bit entre dos expresiones numéricas.  
  
## Sintaxis  
  
```  
  
result = expression1 Xor expression2  
```  
  
## Elementos  
 `result`  
 Obligatorio.  Cualquier variable numérica o de tipo `Boolean`.  Para la comparación booleana, `result` es la exclusión lógica \(disyunción lógica exclusiva\) de dos valores `Boolean`.  Para las operaciones bit a bit, `result` es un valor numérico que representa la exclusión bit a bit \(disyunción bit a bit exclusiva\) de dos modelos de bits numéricos.  
  
 `expression1`  
 Obligatorio.  Cualquier expresión numérica o de tipo `Boolean`.  
  
 `expression2`  
 Obligatorio.  Cualquier expresión numérica o de tipo `Boolean`.  
  
## Comentarios  
 En la comparación booleana, `result` es `True` si y sólo si uno de los argumentos `expression1` y `expression2` se evalúa exactamente en `True`.  Es decir, si y sólo si `expression1` y `expression2` se evalúan en valores `Boolean` opuestos.  En la tabla siguiente se ilustra cómo se determina el argumento `result`.  
  
|Si el valor de `expression1` es:|Y `expression2` es|El valor de `result` es:|  
|--------------------------------------|------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  En una comparación booleana, el operador `Xor` evalúa siempre las dos expresiones, lo que podría incluir llamadas a procedimientos.  No hay ningún homólogo de cortocircuito para `Xor`, ya que el resultado depende siempre de ambos operandos.  Para *cortocircuitar* los operadores lógicos, vea [AndAlso \(Operador\)](../../../visual-basic/language-reference/operators/andalso-operator.md) y [OrElse \(Operador\)](../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
 Para operaciones bit a bit, el operador `Xor` realiza una comparación bit a bit de los bits ubicados de manera idéntica en dos expresiones numéricas y establece el bit correspondiente en `result` de acuerdo con la siguiente tabla.  
  
|Si el bit de `expression1` es|Y el bit de `expression2` es...|El bit de `result` es|  
|-----------------------------------|-------------------------------------|---------------------------|  
|1|1|0|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
>  Dado que los operadores lógicos y los operadores bit a bit tienen una prioridad inferior a la de otros operadores aritméticos y relacionales, las operaciones bit a bit deben incluirse entre paréntesis para garantizar una correcta ejecución.  
  
 Por ejemplo, 5 `Xor` 3 es 6.  Para saber por qué, convierta 5 y 3 en sus representaciones binarias, 101 y 011.  A continuación, utilice la tabla anterior para determinar que 101 Xor 011 es 110, que es la representación binaria del número 6 decimal.  
  
## Tipos de datos  
 Si los operandos constan de una expresión `Boolean` y una expresión numérica, Visual Basic convierte la expresión `Boolean` a un valor numérico \(–1 para `True` y 0 para `False`\), y realiza una operación bit a bit.  
  
 Para una comparación `Boolean`, el tipo de datos del resultado es `Boolean`.  Para una comparación bit a bit, el tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`.  Vea la tabla "Comparaciones relacionales y bit a bit" en [Tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## Sobrecarga  
 El operador `Xor` se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  Si el código utiliza este operador en una clase o estructura de este tipo, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el ejemplo siguiente se usa el operador `Xor` para realizar una exclusión lógica \(disyunción lógica exclusiva\) entre dos expresiones.  El resultado será un valor de tipo `Boolean` que indicará exactamente si una de las dos expresiones es `True`.  
  
 [!code-vb[VbVbalrOperators#40](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xor-operator_1.vb)]  
  
 En el ejemplo anterior se generan los resultados de `False`, `True` y `False`, respectivamente.  
  
## Ejemplo  
 En el ejemplo siguiente se usa el operador `Xor` para realizar una exclusión lógica \(disyunción lógica exclusiva\) en los bits individuales de dos expresiones numéricas.  El bit en el modelo resultante se establece si uno de los bits correspondientes de los operandos se ha establecido en 1 exactamente.  
  
 [!code-vb[VbVbalrOperators#41](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xor-operator_2.vb)]  
  
 En el ejemplo anterior se generan los resultados 2, 12 y 14, respectivamente.  
  
## Vea también  
 [Operadores lógicos y operadores bit a bit](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)