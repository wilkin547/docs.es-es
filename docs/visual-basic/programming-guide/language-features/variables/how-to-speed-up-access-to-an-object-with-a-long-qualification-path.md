---
title: Filtrar Acelerar el acceso a un objeto con una ruta de acceso de calificación larga (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: b10876c22d2f6dd5832baa0d498db7c4205a3fcb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816297"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a>Filtrar Acelerar el acceso a un objeto con una ruta de acceso de calificación larga (Visual Basic)
Si frecuentemente tiene acceso a un objeto que requiere una ruta de acceso de calificación de varios métodos y propiedades, puede acelerar su código no repite la ruta de acceso de calificación.  
  
 Hay dos maneras de evitar la repetición de la ruta de acceso de calificación. El objeto se puede asignar a una variable, o puede usarla en un `With`... `End With` bloque.  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a>Para acelerar el acceso a un objeto muy calificado asignándolo a una variable  
  
1.  Declare una variable del tipo del objeto que tiene acceso con frecuencia. Especifique la ruta de acceso de calificación en la parte de la inicialización de la declaración.  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  Use la variable para tener acceso a los miembros del objeto.  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a>Para acelerar el acceso a un objeto muy calificado mediante el uso de r con... Bloque End With  
  
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

- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [With...End With (instrucción)](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
