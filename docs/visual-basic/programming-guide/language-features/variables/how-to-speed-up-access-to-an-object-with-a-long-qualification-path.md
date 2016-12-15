---
title: "C&#243;mo: Acelerar el acceso a un objeto con una ruta de acceso de calificaci&#243;n larga (Visual Basic) | Microsoft Docs"
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
  - "variables de objeto, obtener acceso"
  - "variables [Visual Basic], obtener acceso"
  - "variables [Visual Basic], objeto"
  - "With (bloque)"
  - "With (instrucción)"
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Acelerar el acceso a un objeto con una ruta de acceso de calificaci&#243;n larga (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Si frecuentemente tiene acceso a un objeto que requiere una ruta de acceso de calificación de varios métodos y propiedades, puede acelerar su código sin tener que repetir la ruta de acceso de calificación.  
  
 Hay dos maneras de evitar la repetición de la ruta de acceso de calificación.  Puede asignar el objeto a una variable o puede utilizarlo en un bloque `With`...`End With`.  
  
### Para acelerar el acceso a un objeto muy calificado asignándolo a una variable  
  
1.  Declare una variable del tipo del objeto al que está teniendo acceso con frecuencia.  Especifique la ruta de acceso de calificación en la parte de inicialización de la declaración.  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  Utilice la variable para tener acceso a los miembros del objeto.  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### Para acelerar el acceso a un objeto muy calificado mediante un bloque With...End  
  
1.  Coloque la ruta de acceso de calificación en una instrucción `With`.  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  Tenga acceso a los miembros del objeto dentro del bloque `With`, antes de la instrucción `End With`.  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## Vea también  
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [With...End With \(Instrucción\)](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)