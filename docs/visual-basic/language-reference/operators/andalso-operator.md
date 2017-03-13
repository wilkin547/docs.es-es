---
title: "AndAlso (Operador, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.AndAlso"
  - "AndAlso"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "AndAlso (operador)"
  - "operadores [Visual Basic], conjunción"
  - "operadores [Visual Basic], cortocircuitar"
  - "evaluación cortocircuitada"
  - "cortocircuitar"
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# AndAlso (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Realiza una conjunción lógica "cortocircuitada" en dos expresiones.  
  
## Sintaxis  
  
```  
  
result = expression1 AndAlso expression2  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`result`|Obligatorio.  Cualquier expresión de tipo `Boolean`.  El resultado será el resultado `Boolean` de comparar ambas expresiones.|  
|`expression1`|Obligatorio.  Cualquier expresión de tipo `Boolean`.|  
|`expression2`|Obligatorio.  Cualquier expresión de tipo `Boolean`.|  
  
## Comentarios  
 Se dice que una operación lógica se encuentra *cortocircuitada* si el código compilado puede omitir la evaluación de una expresión en función del resultado de otra.  Si el resultado de la primera expresión evaluada determina el resultado final de la operación, no es necesario evaluar la segunda expresión, ya que no cambiará el resultado final.  La evaluación cortocircuitada puede mejorar el rendimiento si la expresión omitida es compleja o si implica llamadas de procedimiento.  
  
 Si ambas expresiones se evalúan como `True`, `result` es `True`.  En la tabla siguiente se ilustra cómo se determina el argumento `result`.  
  
||||  
|-|-|-|  
|Si el valor de `expression1` es:|Y `expression2` es|El valor de `result` es:|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|\(no se evalúa\)|`False`|  
  
## Tipos de datos  
 El operador `AndAlso` sólo se define para [Boolean \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/boolean-data-type.md).  Visual Basic convierte cada operando según sea necesario a `Boolean` y lleva a cabo toda la operación en `Boolean`.  Si asigna el resultado a un tipo numérico, Visual Basic lo convierte de `Boolean` a ese tipo.  Esto podría generar un comportamiento inesperado.  Por ejemplo, `5 AndAlso 12` da como resultado `–1` cuando se convierte a `Integer`.  
  
## Sobrecarga  
 Los operadores [And \(Operador\)](../../../visual-basic/language-reference/operators/and-operator.md) e [IsFalse \(Operador\)](../../../visual-basic/language-reference/operators/isfalse-operator.md) se pueden *sobrecargar*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando pertenece al tipo de dicha clase o estructura.  La sobrecarga de los operadores `And` y `IsFalse` afecta el comportamiento del operador `AndAlso`.  Si el código utiliza `AndAlso` en una clase o estructura que sobrecarga `And` y `IsFalse`, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza el operador `AndAlso` para realizar la conjunción lógica de dos expresiones.  El resultado será un valor de tipo `Boolean` que indicará si la expresión conjunta es en su totalidad verdadera \(True\).  Si la primera expresión es `False`, no se evaluará la segunda.  
  
 [!code-vb[VbVbalrOperators#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_1.vb)]  
  
 En el ejemplo anterior se generan los resultados de `True`, `False` y `False`, respectivamente.  En el cálculo de `secondCheck`, no se evalúa la segunda expresión porque la primera ya es `False`.  Sin embargo, la segunda expresión se evalúa en el cálculo de `thirdCheck`.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra un procedimiento `Function` que busca un valor determinado entre los elementos de una matriz.  Si la matriz está vacía o si se supera su longitud, la instrucción `While` no comprueba el elemento de la matriz con el valor de búsqueda.  
  
 [!code-vb[VbVbalrOperators#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_2.vb)]  
  
## Vea también  
 [Operadores lógicos y operadores bit a bit](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [And \(Operador\)](../../../visual-basic/language-reference/operators/and-operator.md)   
 [IsFalse \(Operador\)](../../../visual-basic/language-reference/operators/isfalse-operator.md)   
 [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)