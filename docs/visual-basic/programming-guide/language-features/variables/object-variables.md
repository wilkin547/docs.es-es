---
title: Variables de objeto en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: 046119664fc0277a6a5305d0cf086b4438b13f9d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685469"
---
# <a name="object-variables-in-visual-basic"></a>Variables de objeto en Visual Basic
Además de almacenar valores directamente, una variable puede hacer referencia a un objeto. Asignar un objeto a una variable por las mismas razones, que asignar cualquier valor a una variable:  
  
-   Un nombre de variable a menudo es más corto y más fácil de recordar que la ruta de acceso completa de métodos y propiedades necesarias para tener acceso al propio objeto.  
  
-   Uso de una variable que hace referencia a un objeto es más eficaz que repetidamente obtener acceso al propio objeto a través de los métodos o propiedades.  
  
-   Puede cambiar una variable para hacer referencia a otros objetos mientras se ejecuta el código.  
  
## <a name="making-code-shorter"></a>Acortar el código  
 Puede usar variables de objeto para acortar el código que tiene que escribir. En el ejemplo siguiente se usa la ruta de acceso completa de métodos y propiedades para tener acceso a un <xref:System.Windows.Forms.Control> objeto.  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 Puede acortar este código y acelerar la ejecución, si usa una variable de objeto para el control. Debe declarar la variable de objeto con la clase específica que se va a asignar a ella (`Control` en este caso). Una vez que asigne un objeto a la variable, se puede tratar exactamente el mismo como tratar el objeto al que hace referencia. Puede establecer o recuperar las propiedades del objeto o usar cualquiera de sus métodos. El ejemplo siguiente usa una variable de objeto para simplificar el código en el ejemplo anterior.  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## <a name="see-also"></a>Vea también
- [Declaración de variables](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Cómo: Acelerar el acceso a un objeto con una ruta de acceso de calificación larga](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [Declaración de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Asignación de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Valores de las variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
