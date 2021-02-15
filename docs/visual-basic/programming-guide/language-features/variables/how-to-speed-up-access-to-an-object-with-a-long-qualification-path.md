---
description: 'Más información acerca de cómo: acelerar el acceso a un objeto con una ruta de acceso de calificación larga (Visual Basic)'
title: Procedimiento para acelerar el acceso a un objeto con una ruta de acceso de calificación larga
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: 8e0b5dc2ab6c23d57a4e9d905cfd711a79843185
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100467048"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a>Cómo: Acelerar el acceso a un objeto con una ruta de acceso de calificación larga (Visual Basic)

Si tiene acceso a menudo a un objeto que requiere una ruta de acceso de calificación de varios métodos y propiedades, puede acelerar el código sin repetir la ruta de acceso de la calificación.

Hay dos maneras de evitar repetir la ruta de acceso de la calificación. Puede asignar el objeto a una variable o puede usarlo en un `With` bloque... `End With` .

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

1. Coloque la ruta de acceso de la calificación en una `With` instrucción.

    ```vb
    With someForm.ActiveForm.ActiveControl
    ```

2. Obtenga acceso a los miembros del objeto dentro del `With` bloque, antes de la `End With` instrucción.

    ```vb
        .Text = "Test"
        .Location = New Point(100, 100)
        .Show()
    End With
    ```

## <a name="see-also"></a>Consulte también

- [Variables de objeto](object-variables.md)
- [Instrucción With...End With](../../../language-reference/statements/with-end-with-statement.md)
