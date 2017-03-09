---
title: "La acci&#243;n de volver a copiar el valor del par&#225;metro &#39;ByRef&#39; &#39;&lt;nombre de par&#225;metro&gt;&#39; en el argumento coincidente restringe del tipo &#39;&lt;nombre de tipo 1&gt;&#39; al tipo &#39;&lt;nombre de tipo 2&gt;&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc32053"
  - "vbc32053"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32053"
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# La acci&#243;n de volver a copiar el valor del par&#225;metro &#39;ByRef&#39; &#39;&lt;nombre de par&#225;metro&gt;&#39; en el argumento coincidente restringe del tipo &#39;&lt;nombre de tipo 1&gt;&#39; al tipo &#39;&lt;nombre de tipo 2&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Se llama a un procedimiento con un argumento que se amplía al tipo de parámetro correspondiente, y la conversión del parámetro al argumento es de restricción.  
  
 Al definir una clase o una estructura, puede definir uno o varios operadores de conversión para convertir ese tipo de clase o estructura a otros tipos.  También puede definir a los operadores de conversión inversos para convertir esos otros tipos de vuelta a su clase o tipo de estructura.  Cuando utilice su tipo de clase o estructura en una llamada a procedimiento, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] puede usar esos operadores de conversión para convertir el tipo de un argumento al tipo de su parámetro correspondiente.  
  
 Si pasa el argumento [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] a veces copia el valor del argumento en una variable local del procedimiento en lugar de pasar una referencia.  En este caso, cuando el procedimiento vuelve, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] debe copiar de nuevo el valor de la variable local en el argumento del código de llamada.  
  
 Si un valor de argumento `ByRef` se copia en el procedimiento y el argumento y el parámetro son del mismo tipo, no es necesaria ninguna conversión.  Si los tipos son diferentes, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] debe convertir en ambas direcciones.  Si uno de los tipos es su clase o tipo de estructura, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] debe convertirlo tanto al otro tipo como desde el mismo.  Si una de estas conversiones es de ampliación, la conversión inversa podría ser de restricción.  
  
 **Identificador de error:** BC32053  
  
### Para corregir este error  
  
-   Si es posible, utilice un argumento de llamada del mismo tipo que el parámetro de procedimiento, de forma que [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] no necesite realizar ninguna conversión.  
  
-   Si necesita llamar al procedimiento con un tipo de argumento diferente del tipo de parámetro pero no necesita devolver un valor al argumento que realiza la llamada, defina el parámetro como [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) en lugar de definirlo como `ByRef`.  
  
-   Si necesita devolver un valor al argumento de llamada, defina el operador de conversión inversa como [Widening](../../../visual-basic/language-reference/modifiers/widening.md), si es posible.  
  
## Vea también  
 [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Argumentos y parámetros de procedimiento](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Pasar argumentos por valor y por referencia](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Operator \(Instrucción\)](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Cómo: Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [Cómo: Definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Conversiones de tipos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)