---
title: 'Cómo: Acelerar el acceso a un objeto con una ruta de acceso de calificación larga'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: 83670ae6af0904156b08398024658cf504b7663f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346819"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a>Cómo: Acelerar el acceso a un objeto con una ruta de acceso de calificación larga (Visual Basic)

Si tiene acceso a menudo a un objeto que requiere una ruta de acceso de calificación de varios métodos y propiedades, puede acelerar el código sin repetir la ruta de acceso de la calificación.

Hay dos maneras de evitar repetir la ruta de acceso de la calificación. Puede asignar el objeto a una variable o puede usarlo en un bloque `With`...`End With`.

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a>Para acelerar el acceso a un objeto muy calificado mediante su asignación a una variable

1. Declare una variable del tipo del objeto al que tiene acceso con frecuencia. Especifique la ruta de acceso de calificación en la parte de inicialización de la declaración.

    ```vb
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl
    ```

2. Use la variable para obtener acceso a los miembros del objeto.

    ```vb
    ctrlActv.Text = "Test"
    ctrlActv.Location = New Point(100, 100)
    ctrlActv.Show()
    ```

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a>Para acelerar el acceso a un objeto muy calificado mediante un con... Terminar con bloque

1. Coloque la ruta de acceso de calificación en una instrucción `With`.

    ```vb
    With someForm.ActiveForm.ActiveControl
    ```

2. Obtenga acceso a los miembros del objeto dentro del bloque `With`, antes de la instrucción `End With`.

    ```vb
        .Text = "Test"
        .Location = New Point(100, 100)
        .Show()
    End With
    ```

## <a name="see-also"></a>Vea también

- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [With...End With (instrucción)](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
