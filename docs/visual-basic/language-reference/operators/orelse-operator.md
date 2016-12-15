---
title: "OrElse (Operador) (Visual Basic) | Microsoft Docs"
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
  - "OrElse"
  - "vb.OrElse"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "operadores [Visual Basic], disyunción"
  - "operadores [Visual Basic], cortocircuitar"
  - "OrElse (operador) [Visual Basic]"
  - "evaluación cortocircuitada"
  - "cortocircuitar"
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# OrElse (Operador) (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Realiza una disyunción lógica inclusiva "cortocircuitada" en dos expresiones.  
  
## Sintaxis  
  
```  
  
result = expression1 OrElse expression2  
```  
  
## Elementos  
 `result`  
 Obligatorio.  Cualquier expresión de tipo `Boolean`.  
  
 `expression1`  
 Obligatorio.  Cualquier expresión de tipo `Boolean`.  
  
 `expression2`  
 Obligatorio.  Cualquier expresión de tipo `Boolean`.  
  
## Comentarios  
 Se dice que una operación lógica se encuentra *cortocircuitada* si el código compilado puede omitir la evaluación de una expresión en función del resultado de otra.  Si el resultado de la primera expresión evaluada determina el resultado final de la operación, no es necesario evaluar la segunda expresión, ya que no cambiará el resultado final.  La evaluación cortocircuitada puede mejorar el rendimiento si la expresión omitida es compleja o si implica llamadas de procedimiento.  
  
 Si una o ambas expresiones se evalúan como `True`, `result` es `True`.  En la tabla siguiente se ilustra cómo se determina el argumento `result`.  
  
|Si el valor de `expression1` es:|Y `expression2` es|El valor de `result` es:|  
|--------------------------------------|------------------------|------------------------------|  
|`True`|\(no se evalúa\)|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## Tipos de datos  
 El operador `OrElse` solo se define para [Boolean \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/boolean-data-type.md).  Visual Basic convierte cada operando según sea necesario a `Boolean` y lleva a cabo toda la operación en `Boolean`.  Si asigna el resultado a un tipo numérico, Visual Basic lo convierte de `Boolean` a ese tipo.  Esto podría generar un comportamiento inesperado.  Por ejemplo, `5 OrElse 12` tiene como resultado `–1` cuando se convierte en `Integer`.  
  
## Sobrecarga  
 [Or \(Operador\)](../../../visual-basic/language-reference/operators/or-operator.md) e [IsTrue \(Operador\)](../../../visual-basic/language-reference/operators/istrue-operator.md) se pueden *sobrecargar*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  La sobrecarga de los operadores `Or` e `IsTrue` afecta al comportamiento del operador `OrElse`.  Si el código utiliza `OrElse` en una clase o estructura que sobrecarga `Or` e `IsTrue`, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el ejemplo siguiente se usa el operador `OrElse` para realizar una disyunción lógica entre dos expresiones.  El resultado será un valor de tipo `Boolean` que indicará si alguna de las dos expresiones es verdadera \(True\).  Si la primera expresión es `True`, la segunda no será evaluada.  
  
 [!code-vb[VbVbalrOperators#37](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_1.vb)]  
  
 El ejemplo anterior genera unos resultados de `True`, `True` y `False`, respectivamente.  En el cálculo de `firstCheck`, no se evalúa la segunda expresión porque la primera ya es `True`.  Sin embargo, la segunda expresión se evalúa en el cálculo de `secondCheck`.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra la instrucción `If`...`Then` que contiene dos llamadas a procedimientos.  Si la primera llamada devuelve `True`, no se llama al segundo procedimiento.  Esto puede generar resultados inesperados si el segundo procedimiento realiza tareas importantes que se deben realizar siempre que se ejecute esta sección del código.  
  
 [!code-vb[VbVbalrOperators#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_2.vb)]  
  
## Vea también  
 [Operadores lógicos y operadores bit a bit](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Or \(Operador\)](../../../visual-basic/language-reference/operators/or-operator.md)   
 [IsTrue \(Operador\)](../../../visual-basic/language-reference/operators/istrue-operator.md)   
 [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)