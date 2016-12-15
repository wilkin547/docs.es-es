---
title: "Estructuras de decisi&#243;n (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "instrucciones condicionales, estructuras de decisión"
  - "flujo de control, estructuras de decisión"
  - "estructuras de decisión"
  - "If (instrucción), estructuras de decisión"
  - "If (instrucción), If...Then...Else"
  - "instrucciones [Visual Basic], flujo de control"
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
caps.latest.revision: 29
caps.handback.revision: 29
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Estructuras de decisi&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] permite probar condiciones y realizar diferentes operaciones en función de los resultados de la prueba.  Puede comprobar si una condición es verdadera o falsa, los distintos valores de una expresión o las diferentes excepciones que se generan al ejecutar una serie de instrucciones.  
  
 En el siguiente ejemplo se muestra una estructura de decisión que prueba si el valor de una condición es true y emprende distintas acciones en función del resultado.  
  
 ![Gráfico de flujo de una construcción If...Then...Else](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")  
Emprender acciones diferentes cuando el valor de una condición es true y cuando es false  
  
## Construcción If...Then...Else  
 Las construcciones `If...Then...Else` permiten probar una o más condiciones y ejecutar una o más instrucciones en función de cada condición.  Puede probar las condiciones y tomar medidas de las maneras siguientes:  
  
-   Ejecutar una o más instrucciones si una condición es `True`.  
  
-   Ejecutar una o más instrucciones si una condición es `False`.  
  
-   Ejecutar algunas instrucciones si una condición es `True` y otras si es `False`.  
  
-   Probar una condición adicional si una condición anterior es `False`.  
  
 La estructura de control que proporciona todas estas posibilidades es [If...Then...Else \(Instrucción\)](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).  Puede utilizar una versión de una línea si tiene simplemente una comprobación y una instrucción para ejecutar.  Si tiene un conjunto más complejo de condiciones y acciones, puede utilizar la versión de varias líneas.  
  
## Construcción Select...Case  
 La construcción `Select...Case` permite evaluar una expresión una vez y ejecutar distintos conjuntos de instrucciones basados en diferentes valores posibles.  Para obtener más información, vea [Select...Case \(Instrucción\)](../../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## Construcción Try...Catch...Finally  
 Las construcciones `Try...Catch...Finally` permiten ejecutar un conjunto de instrucciones en un entorno que conserva el control si una de las instrucciones provoca una excepción.  Puede tomar distintas medidas para excepciones diferentes.  Opcionalmente, puede especificar un bloque de código que se ejecuta antes de salir de la construcción `Try...Catch...Finally` completa, sin tener en cuenta el resultado.  Para obtener más información, vea [Try...Catch...Finally \(Instrucción\)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
>  En muchas estructuras de control, al hacer clic en una palabra clave, se resaltan todas las palabras clave en la estructura.  Por ejemplo, al hacer clic en `If` en una construcción `If...Then...Else`, se resaltan todas las instancias de `If`, `Then`, `ElseIf`, `Else` y `End If` de la construcción.  Para desplazarse a la palabra clave resaltada siguiente o anterior, presione CTRL\+MAYÚS\+FLECHA ABAJO o CTRL\+MAYÚS\+FLECHA ARRIBA.  
  
## Vea también  
 [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Estructuras de bucles](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Estructuras de control adicionales](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)   
 [Estructuras de control anidadas](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [If \(operador\)](../../../../visual-basic/language-reference/operators/if-operator.md)