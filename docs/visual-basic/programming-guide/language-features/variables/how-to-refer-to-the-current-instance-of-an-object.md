---
title: "C&#243;mo: Hacer referencia a la instancia actual de un objeto (Visual Basic) | Microsoft Docs"
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
  - "instancia actual"
  - "instancias, hacer referencia al actual"
  - "variables de objeto"
  - "objetos [Visual Basic], hacer referencia a la instancia actual"
  - "variables [Visual Basic], objeto"
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Hacer referencia a la instancia actual de un objeto (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

La *instancia actual* de un objeto es la instancia en la que se está ejecutando el código.  
  
 Utiliza la palabra clave `Me`  para hacer referencia a la instancia actual.  
  
### Para hacer referencia a la instancia actual  
  
-   Utilice la palabra clave `Me` donde utilizaría normalmente el nombre de una variable de objeto.  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     Aunque la palabra clave `Me` se comporta como una variable de objeto, no puede declararla ni asignarle nada.  `Me` siempre hace referencia a la instancia actual.  
  
## Vea también  
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Asignación de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)