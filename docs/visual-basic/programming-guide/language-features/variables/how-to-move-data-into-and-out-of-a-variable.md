---
title: "C&#243;mo: Introducir y extraer los datos de una variable (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "variables [Visual Basic], recuperar valores"
  - "variables [Visual Basic], almacenar datos"
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Introducir y extraer los datos de una variable (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Almacena un valor en una variable colocando el nombre de variable en el lado izquierdo de una instrucción de asignación.  
  
## Colocar datos en una variable  
  
#### Para almacenar un valor en una variable  
  
-   Utilice el nombre de variable en el lado izquierdo de una instrucción de asignación.  
  
     El ejemplo siguiente establece el valor de la variable `alpha`.  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     El valor generado en el lado derecho de la instrucción de asignación se almacena en la variable.  
  
## Obtener datos de una variable  
 Recupera el valor de una variable incluyendo el nombre de variable en una expresión.  
  
#### Para recuperar un valor de una variable  
  
-   Utilice el nombre de variable en una expresión.  Puede utilizar una variable en cualquier parte donde se puede utilizar una constante o un literal, excepto en una expresión que define el valor de una constante.  
  
     O bien  
  
-   Utilice el nombre de variable que sigue al signo igual \(`=`\) en una instrucción de asignación.  
  
     El ejemplo siguiente lee el valor de la variable `startValue` y, a continuación, utiliza el valor de la variable `counter` en una expresión.  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     El valor de la variable participa en la expresión del mismo modo que una constante y se almacena en la variable o propiedad en el lado izquierdo de la instrucción de asignación.  
  
## Vea también  
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Declaración de variable](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)