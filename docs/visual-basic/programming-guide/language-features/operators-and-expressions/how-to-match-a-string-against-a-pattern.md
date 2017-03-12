---
title: "C&#243;mo: Comprobar si una cadena coincide con un modelo (Visual Basic) | Microsoft Docs"
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
  - "operadores de comparación, comparar cadenas"
  - "Like (operador) [Visual Basic], coincidencia de patrones"
  - "operadores [Visual Basic], comparación"
  - "coincidencia de patrones"
  - "coincidencia de patrones, cadenas vacías"
  - "coincidencia de patrones, comparación de cadenas"
  - "comparación de cadenas [Visual Basic]"
  - "comparación de cadenas [Visual Basic], operadores"
  - "cadenas [Visual Basic], comparar"
  - "código de Visual Basic, operadores"
ms.assetid: 19a83804-b5af-4739-928b-ac93e64e457f
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# C&#243;mo: Comprobar si una cadena coincide con un modelo (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Si desea averiguar si una expresión de [String \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisface un modelo, puede utilizar el [Like \(Operador\)](../../../../visual-basic/language-reference/operators/like-operator.md).  
  
 `Like` toma dos operandos.  El operando izquierdo es una expresión de cadena y el operando derecho es una cadena que contiene el modelo que se debe utilizar para la equivalencia.  `Like` devuelve un valor `Boolean`, lo que indica si la expresión de cadena satisface el modelo.  
  
 Puede hacer coincidir cada carácter de la expresión de cadena con un carácter concreto, un carácter comodín, una lista de caracteres o un intervalo de caracteres.  Las posiciones de las especificaciones de la cadena modelo corresponden con las posiciones de los caracteres que se deben hacer coincidir en la expresión de cadena.  
  
### Para hacer coincidir un carácter de la expresión de cadena con respecto a un carácter concreto  
  
-   Coloque directamente el carácter concreto en la cadena del modelo.  Ciertos caracteres especiales se deben incluir entre corchetes \(`[ ]`\).  Para obtener más información, vea [Like \(Operador\)](../../../../visual-basic/language-reference/operators/like-operator.md).  
  
     El ejemplo siguiente prueba si `myString` consta exactamente del carácter individual `H`.  
  
     [!code-vb[VbVbalrOperators#70](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-match-a-string-ag_1.vb)]  
  
### Para hacer coincidir un carácter de la expresión de cadena con respecto a un carácter comodín  
  
-   Coloque un signo de interrogación \(`?`\) en la cadena del modelo.  Cualquier carácter válido para esta posición obtiene una coincidencia correcta.  
  
     El ejemplo siguiente prueba si `myString` está compuesto del carácter individual `W` seguido de exactamente dos caracteres de cualquier valor.  
  
     [!code-vb[VbVbalrOperators#71](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-match-a-string-ag_2.vb)]  
  
### Para hacer coincidir un carácter de la expresión de cadena con respecto a una lista de caracteres  
  
-   Coloque corchetes \(`[ ]`\) en la cadena del modelo y, dentro de los corchetes, coloque la lista de caracteres.  No separe los caracteres con comas ni con cualquier otro separador.  Cualquier carácter individual en la lista consigue una coincidencia correcta.  
  
     El ejemplo siguiente prueba si `myString` está compuesto de cualquier carácter válido seguido por exactamente uno de los caracteres `A`, `C` o `E`.  
  
     [!code-vb[VbVbalrOperators#72](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-match-a-string-ag_3.vb)]  
  
     Tenga en cuenta que esta coincidencia distingue entre mayúsculas y minúsculas.  
  
### Para hacer coincidir un carácter de la expresión de cadena con respecto a un intervalo de caracteres  
  
-   Coloque corchetes \(`[ ]`\) en la cadena del modelo y, dentro de los corchetes, coloque el primer y el último caracteres del intervalo, separados por un guión \(`–`\).  Cualquier carácter individual contenido en del intervalo obtiene una coincidencia correcta.  
  
     El ejemplo siguiente prueba si `myString` incluye los caracteres `num` seguidos por exactamente uno de los caracteres `i`, `j`, `k`, `l`, `m` o `n`.  
  
     [!code-vb[VbVbalrOperators#73](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-match-a-string-ag_4.vb)]  
  
     Tenga en cuenta que esta coincidencia distingue entre mayúsculas y minúsculas.  
  
## Coincidencia de cadenas vacías  
 `Like` trata la secuencia `[]` como una cadena de longitud cero \(`""`\).  Puede utilizar `[]` para probar si toda la expresión de cadena está vacía, pero no para probar si una posición concreta de la expresión de cadena está vacía.  Si una posición vacía es una de las opciones que necesita comprobar, puede utilizar `Like` más de una vez.  
  
#### Para hacer coincidir un carácter de la expresión de cadena con respecto a una lista de caracteres o con ningún carácter  
  
1.  Llame dos veces al operador `Like` en la misma expresión de cadena y conecte las dos llamadas con [Or \(Operador\)](../../../../visual-basic/language-reference/operators/or-operator.md) u [OrElse \(Operador\)](../../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
2.  En la cadena del modelo para la primera cláusula `Like`, incluya la lista de caracteres, encerrándola entre corchetes \(`[ ]`\).  
  
3.  En la cadena del modelo para la segunda cláusula `Like`, no coloque ningún carácter en la posición en cuestión.  
  
     El ejemplo siguiente prueba el número de teléfono de siete dígitos `phoneNum` para ver si está formado exactamente por tres números seguidos por un espacio, un guión \(`–`\), un punto \(`.`\) o ningún carácter, seguidos exactamente por cuatro números.  
  
     [!code-vb[VbVbalrOperators#74](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-match-a-string-ag_5.vb)]  
  
## Vea también  
 [Operadores de comparación](../../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Operadores y expresiones](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Like \(Operador\)](../../../../visual-basic/language-reference/operators/like-operator.md)   
 [String \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/string-data-type.md)