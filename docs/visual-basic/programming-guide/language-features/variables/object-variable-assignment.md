---
title: "Asignaci&#243;n de variables de objeto (Visual Basic) | Microsoft Docs"
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
  - "instrucciones de asignación, asignación de variables de objeto"
  - "instancia actual, definición"
  - "Me (palabra clave), como variable de objeto"
  - "Nothing (palabra clave), asignación de variables de objeto"
  - "variables de objeto, asignar"
  - "variables de objeto, inicializar"
  - "objetos [Visual Basic], instancia actual"
  - "variables [Visual Basic], asignar"
  - "variables [Visual Basic], inicializar"
  - "variables [Visual Basic], variables de objeto"
ms.assetid: 3706811d-fd40-44fe-8727-d692e8e55d6d
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Asignaci&#243;n de variables de objeto (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Utilice una instrucción de asignación normal para asignar un objeto a una variable de objeto.  Puede asignar una expresión de objeto o la palabra clave [Nothing](../../../../visual-basic/language-reference/nothing.md), tal como se muestra en el ejemplo siguiente.  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 `Nothing` significa que no hay ningún objeto asignado actualmente a la variable.  
  
## Inicialización  
 Cuando el código empieza a ejecutarse, las variables de objeto se inicializan con `Nothing`.  Aquéllos cuyas declaraciones incluyen la inicialización se reinicializan con los valores que especifica cuando se ejecutan las instrucciones de declaración.  
  
 Puede incluir la inicialización en su declaración utilizando la palabra clave [New](../../../../visual-basic/language-reference/operators/new-operator.md).  En las siguientes instrucciones de declaración se declaran variables de objeto `testUri` y `ver`, y se les asignan objetos específicos.  Cada una utiliza uno de los constructores sobrecargados de la clase adecuada para inicializar el objeto.  
  
```  
Dim testUri As New System.Uri("http://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## Desasociación  
 Si se establece una variable de objeto en `Nothing` se interrumpe la asociación de la variable con cualquier objeto específico,  lo que impide que el objeto se modifique de forma accidental al cambiar la variable.  También permite comprobar si la variable de objeto señala a un objeto válido, tal como se muestra en el ejemplo siguiente:  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 Si el objeto al que hace referencia la variable está en otra aplicación, esta comprobación no permite averiguar si la aplicación se ha terminado o ha invalidado el objeto.  
  
 Una variable de objeto con un valor de `Nothing` también se llama *referencia nula*.  
  
## Instancia actual  
 La *instancia actual* de un objeto es aquella en la que se está ejecutando el código.  Dado que todo el código se ejecuta siempre dentro de un procedimiento, la instancia actual es aquella en la cual se invocó al procedimiento.  
  
 La palabra clave `Me` cumple la función de una variable de objeto que hace referencia a la instancia actual.  Si un procedimiento no es [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), puede utilizar la palabra clave `Me` para obtener un puntero a la instancia actual.  Los procedimientos compartidos no pueden asociarse a una instancia específica de una clase.  
  
 El uso de la palabra clave `Me` es especialmente útil para pasar la instancia actual a un procedimiento de otro módulo.  Por ejemplo, suponga que tiene varios documentos XML y desea agregar un texto estándar a todos ellos.  El ejemplo siguiente define un procedimiento para ello.  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 Después, todos los objetos de documento XML pueden llamar al procedimiento y pasar como argumento su instancia actual.  En el siguiente ejemplo se muestra cómo.  
  
```  
addStandardText(Me)  
```  
  
## Vea también  
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Declaración de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Valores de las variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [Cómo: Declarar una variable de objeto y asignarle un objeto en Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)   
 [Cómo: Crear una variable de objeto que no haga referencia a ninguna instancia](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)   
 [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)