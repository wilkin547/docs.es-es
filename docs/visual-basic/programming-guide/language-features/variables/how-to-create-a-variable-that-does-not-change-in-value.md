---
title: "C&#243;mo: Crear una variable que no cambia de valor (Visual Basic) | Microsoft Docs"
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
  - "variables [Visual Basic], valor constante"
  - "variables [Visual Basic], solo lectura"
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Crear una variable que no cambia de valor (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

La noción de una variable que no cambia de valor podría parecer contradictoria.  Pero hay situaciones en las que una constante no es factible y es útil tener una variable con un valor fijo.  En tal caso puede definir una variable miembro con la palabra clave [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 No puede utilizar [Const \(Instrucción\)](../../../../visual-basic/language-reference/statements/const-statement.md) para declarar y asignar un valor constante en las circunstancias siguientes:  
  
-   La instrucción `Const` no acepta el tipo de datos que desea utilizar.  
  
-   No conoce el valor en tiempo de compilación.  
  
-   No puede calcular el valor constante en tiempo de compilación.  
  
### Para crear una variable que no cambia de valor  
  
1.  En el nivel de módulo, declare una variable miembro con [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md) e incluya la palabra clave [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md)  
  
    ```  
  
    Dim ReadOnly timeStarted  
    ```  
  
     Sólo puede especificar `ReadOnly` en una variable miembro.  Esto significa que debe definir la variable en el nivel de módulo, fuera de cualquier procedimiento.  
  
2.  Si puede calcular el valor en una instrucción única en el momento de la compilación, utilice una cláusula de inicialización en la instrucción `Dim`.  Agregue detrás de la cláusula [As](../../../../visual-basic/language-reference/statements/as-clause.md) un signo igual \(`=`\), seguido de una expresión.  Asegúrese de que el compilador puede evaluar esta expresión en un valor constante.  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     Sólo puede asignar una vez un valor a una variable `ReadOnly`.  Una vez hecho esto, ningún código podrá cambiar nunca su valor.  
  
     Si no conoce el valor o no puede calcularlo en una instrucción única en tiempo de compilación, puede asignarlo durante el tiempo de ejecución en un constructor.  Para ello, debe declarar la variable `ReadOnly` en la clase o nivel de estructura.  En el constructor para esa clase o estructura, calcule el valor fijo de la variable y asígnelo a la variable antes de que vuelva del constructor.  
  
## Vea también  
 [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)   
 [Const \(Instrucción\)](../../../../visual-basic/language-reference/statements/const-statement.md)