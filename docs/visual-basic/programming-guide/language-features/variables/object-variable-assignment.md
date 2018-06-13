---
title: Asignación de variables de objeto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], object variable assignment
- object variables [Visual Basic], initializing
- variables [Visual Basic], initializing
- objects [Visual Basic], current instance
- object variables [Visual Basic], assigning
- variables [Visual Basic], object variables
- current instance [Visual Basic], defined
- variables [Visual Basic], assigning
- assignment statements [Visual Basic], object variable assignment
- Me keyword [Visual Basic], as object variable
ms.assetid: 3706811d-fd40-44fe-8727-d692e8e55d6d
ms.openlocfilehash: f20a03c4d9a0e33203629ae066686f4c9f25c105
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656063"
---
# <a name="object-variable-assignment-visual-basic"></a>Asignación de variables de objeto (Visual Basic)
Usar una instrucción de asignación normal para asignar un objeto a una variable de objeto. Puede asignar una expresión de objeto o la [nada](../../../../visual-basic/language-reference/nothing.md) palabra clave, como en el ejemplo siguiente se muestra.  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 `Nothing` significa que no hay ningún objeto asignado actualmente a la variable.  
  
## <a name="initialization"></a>Inicialización  
 Cuando el código inicia la ejecución, el objeto se inicializan las variables a `Nothing`. Aquéllos cuyas declaraciones incluyen la inicialización se reinicializan con los valores especificados cuando se ejecutan las instrucciones de declaración.  
  
 Puede incluir la inicialización en su declaración utilizando el [New](../../../../visual-basic/language-reference/operators/new-operator.md) (palabra clave). Las siguientes instrucciones de declaración declaran variables de objeto `testUri` y `ver` y asignan objetos específicos. Cada uno utiliza uno de los constructores sobrecargados de la clase adecuada para inicializar el objeto.  
  
```  
Dim testUri As New System.Uri("http://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## <a name="disassociation"></a>Desasociación  
 Si se establece una variable de objeto en `Nothing` se interrumpe la asociación de la variable con cualquier objeto concreto. Esto impide que se modifique accidentalmente el objeto cambiando la variable. También permite comprobar si la variable de objeto hace referencia a un objeto válido, como se muestra en el ejemplo siguiente.  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 Si el objeto al que hace referencia la variable está en otra aplicación, esta prueba no puede determinar si esa aplicación ha terminado o ha invalidado el objeto.  
  
 Una variable de objeto con un valor de `Nothing` también se denomina un *referencia nula*.  
  
## <a name="current-instance"></a>Instancia actual  
 El *instancia actual* de un objeto es el que se está ejecutando el código actualmente. Puesto que todo el código se ejecuta dentro de un procedimiento, la instancia actual es uno en el que se invocó el procedimiento.  
  
 El `Me` palabra clave actúa como una variable de objeto que hace referencia a la instancia actual. Si un procedimiento no es [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), puede usar el `Me` palabra clave que se va a obtener un puntero a la instancia actual. Los procedimientos compartidos no se pueden asociados a una instancia específica de una clase.  
  
 Usar `Me` es especialmente útil para pasar la instancia actual a un procedimiento en otro módulo. Por ejemplo, suponga que tiene un número de documentos XML y desea agregar algún texto estándar a todos ellos. En el ejemplo siguiente se define un procedimiento para hacer esto.  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 Cada objeto de documento XML, a continuación, podría llamar al procedimiento y pasar la instancia actual como un argumento. En el siguiente ejemplo se muestra cómo hacerlo.  
  
```  
addStandardText(Me)  
```  
  
## <a name="see-also"></a>Vea también  
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Declaración de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [Valores de las variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [Cómo: declarar una Variable de objeto y asignarle un objeto en Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)  
 [Crear una variable de objeto que no haga referencia a ninguna instancia](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)  
 [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
