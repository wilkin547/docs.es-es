---
title: "Cómo: Acelerar el acceso a un objeto con una ruta de acceso de calificación larga (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5d91eeaeb034a4c8b4fefcffdf2fdebe72127d66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a>Cómo: Acelerar el acceso a un objeto con una ruta de acceso de calificación larga (Visual Basic)
Si frecuentemente tiene acceso a un objeto que se requiere una ruta de acceso de calificación de varios métodos y propiedades, puede acelerar el código no repite la ruta de acceso de calificación.  
  
 Hay dos maneras de evitar la repetición de la ruta de acceso de calificación. El objeto se puede asignar a una variable, o puede usar en un `With`... `End With` bloque.  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a>Para agilizar el acceso a un objeto muy calificado asignándolo a una variable  
  
1.  Declare una variable del tipo del objeto que tiene acceso con frecuencia. Especifique la ruta de acceso de calificación en la parte de la inicialización de la declaración.  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  Utilice la variable para tener acceso a los miembros del objeto.  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a>Para agilizar el acceso a un objeto muy calificado mediante un With... Bloque End With  
  
1.  Coloque la ruta de acceso de calificación en una `With` instrucción.  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  Obtener acceso a los miembros del objeto dentro de la `With` bloquear, antes del `End With` instrucción.  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [With...End With (instrucción)](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
