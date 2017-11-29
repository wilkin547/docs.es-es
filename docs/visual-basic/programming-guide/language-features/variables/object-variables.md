---
title: Variables de objeto en Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 44689d649a381618e5d6c934deb2b7b9bea463ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="object-variables-in-visual-basic"></a>Variables de objeto en Visual Basic
Además de almacenar valores directamente, una variable puede hacer referencia a un objeto. Asignar un objeto a una variable por las mismas razones que se asigne cualquier valor a una variable:  
  
-   Un nombre de variable suele ser más corto y más fácil de recordar que la ruta de acceso completa de métodos y propiedades necesarios para tener acceso el propio objeto.  
  
-   Uso de una variable que hace referencia a un objeto es más eficaz que acceso repetidamente el propio objeto a través de las propiedades o métodos necesarios.  
  
-   Puede cambiar una variable para hacer referencia a otros objetos mientras se ejecuta el código.  
  
## <a name="making-code-shorter"></a>El código es más corto  
 Puede usar variables de objeto para acortar el código que tiene que escribir. En el ejemplo siguiente se utiliza la ruta de acceso completa de métodos y propiedades para tener acceso a un <xref:System.Windows.Forms.Control> objeto.  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 Puede reducir este código y acelerar la ejecución, si usa una variable de objeto para el control. Debe declarar la variable de objeto con la clase específica que se va a asignar a él (`Control` en este caso). Una vez que se asigna un objeto a la variable, podrá tratarla exactamente el mismo tal y como se trata el objeto al que hace referencia. Puede establecer o recuperar las propiedades del objeto o utilizar cualquiera de sus métodos. En el ejemplo siguiente se utiliza una variable de objeto para simplificar el código en el ejemplo anterior.  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## <a name="see-also"></a>Vea también  
 [Declaración de variables](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Acelerar el acceso a un objeto con una ruta de acceso de calificación larga](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)  
 [Declaración de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [Asignación de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Valores de las variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
