---
title: "Copiar el valor de &#39; ByRef &#39; parámetro &#39; &lt;parametername&gt;&#39; nuevo en el argumento correspondiente se restringe de tipo &#39;&lt; NombreTipo1&gt;&#39; escriba &#39;&lt; nombredetipo2&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4bf993639007162e2e17d4b8cb9dfe8d5316acaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument-narrows-from-type-39lttypename1gt39-to-type-39lttypename2gt39"></a>Copiar el valor de &#39; ByRef &#39; parámetro &#39; &lt;parametername&gt;&#39; nuevo en el argumento correspondiente se restringe de tipo &#39;&lt; NombreTipo1&gt;&#39; escriba &#39;&lt; nombredetipo2&gt;&#39;
Se llama a un procedimiento con un argumento que se amplía al tipo de parámetro correspondiente, y la conversión del parámetro al argumento es de restricción.  
  
 Al definir una clase o estructura, puede definir uno o varios operadores de conversión para convertir ese tipo de clase o estructura a otros tipos. También puede definir operadores de conversión inversos para convertir esos otros tipos de nuevo a su clase o tipo de estructura. Cuando use su tipo de clase o estructura en una llamada de procedimiento, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] puede usar estos operadores de conversión para convertir el tipo de un argumento al tipo del parámetro correspondiente.  
  
 Si se pasa el argumento [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] a veces copia el valor del argumento en una variable local en el procedimiento en lugar de pasar una referencia. En tal caso, cuando el procedimiento vuelve, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] debe copiar el valor de la variable local de nuevo en el argumento en el código de llamada.  
  
 Si un valor de argumento `ByRef` se copia en el procedimiento y el argumento y el parámetro son del mismo tipo, no es necesario realizar ninguna conversión. Pero si los tipos son diferentes, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] se debe convertir en ambas direcciones. Si uno de los tipos es su tipo de clase o estructura, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] lo debe convertir a y desde el otro tipo. Si es una de estas conversiones de ampliación, la conversión inversa podría ser de restricción.  
  
 **Id. de error:** BC32053  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si es posible, use un argumento de llamada del mismo tipo, como el parámetro de procedimiento, por lo que [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] no necesita hacer ninguna conversión.  
  
-   Si necesita llamar al procedimiento con un argumento de tipo diferente del tipo de parámetro pero no es necesario devolver un valor al argumento de llamada, defina el parámetro para que sea [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) en lugar de `ByRef`.  
  
-   Si necesita devolver un valor al argumento de llamada, defina el operador de conversión inversa como [Widening](../../../visual-basic/language-reference/modifiers/widening.md), si es posible.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Argumentos y parámetros de procedimiento](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [Paso de argumentos por valor y por referencia](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [Procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [Conversiones de tipos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
