---
title: "Variables de objeto en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "variables de objeto"
  - "variables de objeto, acerca de las variables de objeto"
  - "objetos [Visual Basic], obtener acceso"
  - "variables [Visual Basic], objeto"
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Variables de objeto en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una variable, además de almacenar valores directamente, puede hacer referencia a un objeto.  Puede asignar un objeto a una variable por los mismos motivos que asigna un valor a una variable:  
  
-   Un nombre de variable suele ser más corto y más fácil de recordar que la ruta de acceso completa a los métodos y propiedades necesarios para obtener acceso al propio objeto.  
  
-   El uso de una variable que hace referencia a un objeto es más eficiente que el acceso reiterado al propio objeto mediante los métodos o propiedades adecuados.  
  
-   Es posible cambiar una variable para que haga referencia a otros objetos durante la ejecución del código.  
  
## Acortar el código  
 Las variables de objeto permiten reducir la cantidad de código que hay que escribir.  El ejemplo siguiente utiliza la ruta de acceso completa de métodos y propiedades para tener acceso a un objeto <xref:System.Windows.Forms.Control>.  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 Podría abreviar este segmento de código utilizando una variable de objeto para el control, con lo que aumentaría la rapidez de su ejecución.  Es conveniente que declare la variable de objeto con la clase específica que desee asignarle \(`Control` en este caso\).  Una vez que haya asignado un objeto a la variable, podrá tratarla exactamente igual que el objeto al que hace referencia.  Puede establecer o recuperar las propiedades del objeto o utilizar cualquiera de sus métodos.  El ejemplo siguiente utiliza una variable de objeto para simplificar el código del ejemplo anterior.  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## Vea también  
 [Declaración de variable](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Cómo: Acelerar el acceso a un objeto con una ruta de acceso de calificación larga](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)   
 [Declaración de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Asignación de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Valores de las variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)