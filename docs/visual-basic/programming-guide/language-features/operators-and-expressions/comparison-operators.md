---
title: "Operadores de comparaci&#243;n en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "operadores de comparación"
  - "operadores de comparación, comparar valores numéricos"
  - "operadores de comparación, comparar objetos"
  - "operadores de comparación, comparar cadenas"
  - "números, comparar"
  - "valores numéricos, comparar"
  - "objetos [Visual Basic], comparar"
  - "operadores [Visual Basic], comparación"
  - "comparación de cadenas [Visual Basic]"
  - "comparación de cadenas [Visual Basic], operadores"
  - "cadenas [Visual Basic], comparar"
  - "código de Visual Basic, operadores"
ms.assetid: 0b570339-5407-474f-8421-e183a8b303ee
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Operadores de comparaci&#243;n en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Los operadores de comparación comparan dos expresiones y devuelven un valor `Boolean` que representa la relación entre sus valores.  Existen operadores para comparar valores numéricos, operadores para comparar cadenas y operadores para comparar objetos.  Los tres tipos de operadores se describen a continuación.  
  
## Comparar valores numéricos  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] compara valores numéricos mediante seis operadores de comparación numéricos.  Cada operador toma como operandos dos expresiones que se evalúan como valores numéricos.  La tabla siguiente enumera los operadores y muestra ejemplos de cada uno.  
  
|Operador|Condición que prueba|Ejemplos|  
|--------------|--------------------------|--------------|  
|`=` \(Igualdad\)|¿Es igual el valor de la primera expresión que el de la segunda?|`23`   `=`   `33    ' False`<br /><br /> `23`   `=`   `23    ' True`<br /><br /> `23`   `=`   `12    ' False`|  
|`<>` \(Desigualdad\)|¿Es distinto el valor de la primera expresión del valor de la segunda?|`23`   `<>`   `33    ' True`<br /><br /> `23`   `<>`   `23    ' False`<br /><br /> `23`   `<>`   `12    ' True`|  
|`<` \(Menor que\)|¿Es el valor de la primera expresión menor que el valor de la segunda?|`23`   `<`   `33    ' True`<br /><br /> `23`   `<`   `23    ' False`<br /><br /> `23`   `<`   `12    ' False`|  
|`>` \(Mayor que\)|¿Es el valor de la primera expresión mayor que el valor de la segunda?|`23`   `>`   `33    ' False`<br /><br /> `23`   `>`   `23    ' False`<br /><br /> `23`   `>`   `12    ' True`|  
|`<=` \(Menor o igual que\)|¿Es el valor de la primera expresión menor o igual que el valor de la segunda?|`23`   `<=`   `33    ' True`<br /><br /> `23`   `<=`   `23    ' True`<br /><br /> `23`   `<=`   `12    ' False`|  
|`>=` \(Mayor o igual que\)|¿Es el valor de la primera expresión mayor o igual que el valor de la segunda?|`23`   `>=`   `33    ' False`<br /><br /> `23`   `>=`   `23    ' True`<br /><br /> `23`   `>=`   `12    ' True`|  
  
## Comparar cadenas  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] compara cadenas mediante [Like \(Operador\)](../../../../visual-basic/language-reference/operators/like-operator.md) así como los operadores de comparación numéricos.  El operador `Like` le permite especificar un modelo.  La cadena se compara a continuación contra el modelo y si coincide, el resultado es `True`.  De lo contrario, el resultado es `False`.  Los operadores numéricos permiten comparar valores `String` basándose en su criterio de ordenación, como se indica en el ejemplo siguiente:  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 El resultado del ejemplo anterior es `True` porque el primer carácter de la primera cadena se ordena antes que el primer carácter de la segunda cadena.  Si los primeros caracteres fueran iguales, la comparación continuaría con el siguiente carácter de las dos cadenas, y así sucesivamente.  También puede probar la igualdad de cadenas utilizando al operador de igualdad, como se puede ver en el ejemplo siguiente.  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 Si una cadena es un prefijo de otra, como "aa" y "aaa", la cadena más larga se considera mayor que la más corta.  Esto se ilustra en el siguiente ejemplo:  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 El criterio de ordenación se basará en una comparación binaria o una comparación textual, en función del valor de `Option Compare`.  Para obtener más información, vea [Option Compare \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## Comparar objetos  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] compara dos variables de referencia a objetos con [Is \(Operador\)](../../../../visual-basic/language-reference/operators/is-operator.md) e [IsNot \(Operador\)](../../../../visual-basic/language-reference/operators/isnot-operator.md).  Puede utilizar cualquiera de estos operadores para determinar si las dos variables de referencia se refieren a la misma instancia de objeto.  Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrOperators#65](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/comparison-operators_1.vb)]  
  
 En el ejemplo anterior, `x Is y` se evalúa como `True`, porque ambas variables se refieren a la misma instancia.  Compare este resultado con el del ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#66](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/comparison-operators_2.vb)]  
  
 En el ejemplo anterior, `x Is y` se evalúa como `False`, porque aunque las variables hacen referencia a objetos del mismo tipo, se refieren a distintas instancias de ese tipo.  
  
 Cuando desee probar dos objetos que no señalan a la misma instancia, el operador `IsNot` permite evitar una combinación gramaticalmente torpe de `Not` e `Is`.  Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrOperators#67](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/comparison-operators_3.vb)]  
  
 En el ejemplo anterior, `If a IsNot b` es equivalente a `If Not a Is b`.  
  
### Comparar tipos de objetos  
 Para probar si un objeto es de un tipo concreto se puede utilizar la expresión `TypeOf`...`Is`.  La sintaxis es la siguiente:  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 Cuando `typename` especifica un tipo de interfaz, la expresión `TypeOf`...`Is` devuelve `True` si el objeto implementa el tipo de interfaz.  Cuando `typename` es un tipo de clase, la expresión devuelve `True` si el objeto es una instancia de la clase especificada o de una clase que se deriva de la clase especificada.  Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrOperators#68](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/comparison-operators_4.vb)]  
  
 En el ejemplo anterior, la expresión `TypeOf x Is Control` se evalúa como `True` porque el tipo de `x` es `Button`, que hereda de `Control`.  
  
 Para obtener más información, vea [TypeOf \(Operador\)](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## Vea también  
 [Comparaciones de valores](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Operadores de comparación](../../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Operadores](../../../../visual-basic/language-reference/operators/index.md)   
 [Operadores aritméticos en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Operadores de concatenación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)   
 [Operadores lógicos y bit a bit en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)