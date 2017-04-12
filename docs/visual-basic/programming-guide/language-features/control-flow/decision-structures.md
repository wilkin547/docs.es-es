---
title: "La decisión de estructuras (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement, decision structures
- If statement, If...Then...Else
- control flow, decision structures
- decision structures
- conditional statements, decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c69b487322dc75ae8d54f42c1c62f8f5cc35757d
ms.lasthandoff: 03/13/2017

---
# <a name="decision-structures-visual-basic"></a>Estructuras de decisión (Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]le permite probar condiciones y realizar diferentes operaciones en función de los resultados de la prueba. Puede probar si una condición es true o false para distintos valores de una expresión o varias excepciones que se genera cuando se ejecuta una serie de instrucciones.  
  
 La ilustración siguiente muestra una estructura de decisión que prueba si una condición es true y lleva a cabo diferentes acciones dependiendo de si es true o false.  
  
 ![Diagrama de flujo de If... Entonces... Construcción else](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")  
Emprender acciones diferentes cuando una condición es true y cuando es false  
  
## <a name="ifthenelse-construction"></a>If... Entonces... Construcción else  
 `If...Then...Else`construcciones le permiten probar una o más condiciones y ejecutar instrucciones de uno o más dependiendo de cada condición. Puede probar condiciones y realizar acciones de las maneras siguientes:  
  
-   Ejecutar una o más instrucciones si una condición es`True`  
  
-   Ejecutar una o más instrucciones si una condición es`False`  
  
-   Ejecutar algunas instrucciones si una condición es `True` y otras si es`False`  
  
-   Probar una condición adicional si es un requisito previo`False`  
  
 La estructura de control que proporciona todas estas posibilidades es la [si... Entonces... Else (instrucción)](../../../../visual-basic/language-reference/statements/if-then-else-statement.md). Puede utilizar una versión de línea si tiene simplemente una comprobación y una instrucción para ejecutar. Si tiene un conjunto más complejo de condiciones y acciones, puede utilizar la versión de varias líneas.  
  
## <a name="selectcase-construction"></a>Seleccione... Construcción de mayúsculas  
 El `Select...Case` construcción permite evaluar una expresión una vez y ejecutar distintos conjuntos de instrucciones basados en diferentes valores posibles. Para obtener más información, consulte [seleccione... Case (instrucción)](../../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="trycatchfinally-construction"></a>Try... Catch... Por último, construcción  
 `Try...Catch...Finally`permiten ejecutar un conjunto de instrucciones en un entorno que conserva el control si cualquiera de las instrucciones provoca una excepción. Puede realizar diferentes acciones para excepciones diferentes. También puede especificar un bloque de código que se ejecuta antes de salir de todo el `Try...Catch...Finally` construcción, independientemente de lo que ocurre. Para obtener más información, consulte [intente... Catch... Finally (instrucción)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
>  En muchas estructuras de control, al hacer clic en una palabra clave, se resaltan todas las palabras clave de la estructura. Por ejemplo, al hacer clic en `If` en una `If...Then...Else` construcción, todas las instancias de `If`, `Then`, `ElseIf`, `Else`, y `End If` se resaltan en la construcción. Para desplazarse a la palabra clave resaltada siguiente o anterior, presione CTRL + MAYÚS + flecha abajo o CTRL + MAYÚS + flecha arriba.  
  
## <a name="see-also"></a>Vea también  
 [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Estructuras de bucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Otras estructuras de Control](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)   
 [Estructuras de Control anidadas](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [If (operador)](../../../../visual-basic/language-reference/operators/if-operator.md)
