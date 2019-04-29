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
ms.openlocfilehash: dff1b9bb9e87f827663786cac3f33531db41b2c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757071"
---
# <a name="object-variable-assignment-visual-basic"></a>Asignación de variables de objeto (Visual Basic)
Utilice una instrucción de asignación normal para asignar un objeto a una variable de objeto. Puede asignar una expresión de objeto o la [nada](../../../../visual-basic/language-reference/nothing.md) palabra clave, como en el ejemplo siguiente se muestra.  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 `Nothing` significa que no hay ningún objeto asignado actualmente a la variable.  
  
## <a name="initialization"></a>Inicialización  
 Cuando el código empieza a ejecutarse, el objeto de variables se inicializan con `Nothing`. Aquellos cuyos declaraciones incluyen la inicialización se reinicializan con los valores especificados cuando se ejecutan las instrucciones de declaración.  
  
 Puede incluir en la declaración de inicialización mediante el uso de la [New](../../../../visual-basic/language-reference/operators/new-operator.md) palabra clave. Las siguientes instrucciones de declaración declaran variables de objeto `testUri` y `ver` y se les asignan objetos específicos. Cada uno utiliza uno de los constructores sobrecargados de la clase adecuada para inicializar el objeto.  
  
```  
Dim testUri As New System.Uri("https://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## <a name="disassociation"></a>Desasociación  
 Establecer una variable de objeto en `Nothing` interrumpe la asociación de la variable con cualquier objeto específico. Esto evita que se modifiquen accidentalmente el objeto cambiando la variable. También permite comprobar si la variable de objeto señala a un objeto válido, como se muestra en el ejemplo siguiente.  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 Si el objeto que hace referencia la variable está en otra aplicación, esta prueba no puede determinar si esa aplicación ha finalizado o se ha invalidado el objeto.  
  
 Una variable de objeto con un valor de `Nothing` también se denomina un *referencia nula*.  
  
## <a name="current-instance"></a>Instancia actual  
 El *instancia actual* de un objeto está en el que se está ejecutando actualmente el código. Dado que todo el código se ejecuta dentro de un procedimiento, la instancia actual es el en el que se invocó el procedimiento.  
  
 El `Me` palabra clave actúa como una variable de objeto que hace referencia a la instancia actual. Si un procedimiento no es [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), puede usar el `Me` palabra clave para obtener un puntero a la instancia actual. Los procedimientos compartidos no se puede asociados con una instancia específica de una clase.  
  
 Uso de `Me` es especialmente útil para pasar la instancia actual a un procedimiento en otro módulo. Por ejemplo, suponga que tiene un número de documentos XML y desea agregar algún texto estándar a todos ellos. El ejemplo siguiente define un procedimiento para ello.  
  
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

- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Declaración de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Valores de las variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Cómo: Declarar una Variable de objeto y asignarle un objeto en Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [Cómo: Crea un objeto de Variable no hacen referencia a cualquier instancia](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)
- [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
