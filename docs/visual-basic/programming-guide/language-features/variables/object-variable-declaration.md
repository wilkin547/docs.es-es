---
title: Declaración de variables de objeto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- early binding [Visual Basic]
- declarations [Visual Basic], class
- classes [Visual Basic], declaring
- binding [Visual Basic], late and early
- object variables [Visual Basic], declaring
- variables [Visual Basic], object
- declaring variables [Visual Basic], object variables
- declaring classes [Visual Basic]
- late binding [Visual Basic]
ms.assetid: 2a5a41a3-1aa8-4236-b1f0-2382af7bf715
ms.openlocfilehash: f5f77b81380d997e078a9f52ac4aae6f6e975575
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="object-variable-declaration-visual-basic"></a>Declaración de variables de objeto (Visual Basic)
Utilice una instrucción de declaración normal para declarar una variable de objeto. Para el tipo de datos especifique `Object` (es decir, el [tipo de datos de objeto](../../../../visual-basic/language-reference/data-types/object-data-type.md)) o una clase más específica desde la que es necesario crear el objeto.  
  
 Declarar una variable como `Object` es el mismo que declararla como como <xref:System.Object?displayProperty=nameWithType>.  
  
 Cuando se declara una variable con una clase de objeto específico, puede tener acceso a todos los métodos y propiedades expuestas por esa clase y las clases de la que hereda. Si se declara la variable con <xref:System.Object>, pueden tener acceso a solo los miembros de la <xref:System.Object> de la clase, a menos que Active `Option Strict Off` para permitir el enlace.  
  
## <a name="declaration-syntax"></a>Sintaxis de la declaración  
 Utilice la siguiente sintaxis para declarar una variable de objeto:  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 También puede especificar [público](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [privada](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), o [estático](../../../../visual-basic/language-reference/modifiers/static.md) en la declaración. Las siguientes declaraciones de ejemplo son válidas:  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a>Enlace de tiempo de ejecución y el enlace anticipado  
 A veces la clase específica es desconocida hasta que se ejecuta el código. En este caso, debe declarar la variable de objeto con el `Object` tipo de datos. Esto crea una referencia general a cualquier tipo de objeto y se asigna la clase específica en tiempo de ejecución. Esto se denomina *enlace más tarde*. Enlace más tarde, requiere más tiempo de ejecución. También limita su código a los métodos y propiedades de la clase más recientemente que haya asignado a él. Esto puede causar errores en tiempo de ejecución si el código intenta obtener acceso a los miembros de una clase diferente.  
  
 Si conoce la clase específica en tiempo de compilación, se debe declarar la variable de objeto de esa clase. Esto se denomina *enlace anticipado*. Enlace temprano mejora el rendimiento y garantiza su código tenga acceso a todos los métodos y propiedades de la clase específica. En las declaraciones del ejemplo anterior, si la variable `objA` utiliza sólo los objetos de clase <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, debe especificar `As System.Windows.Forms.Label` en su declaración.  
  
### <a name="advantages-of-early-binding"></a>Ventajas del enlace anticipado  
 Declarar una variable de objeto como una clase específica ofrece varias ventajas:  
  
-   Comprobación automática de tipos  
  
-   Garantiza el acceso a todos los miembros de la clase específica  
  
-   Compatibilidad con Microsoft IntelliSense en el Editor de código  
  
-   Mejorar la legibilidad del código  
  
-   Menos errores en el código  
  
-   Errores detectados en tiempo de compilación en lugar de tiempo de ejecución  
  
-   La ejecución de código con mayor rapidez  
  
## <a name="access-to-object-variable-members"></a>Acceso a miembros de Variable de objeto  
 Cuando `Option Strict` está activado `On`, puede tener acceso a una variable de objeto sólo los métodos y propiedades de la clase con la que se declara. Esto se ilustra en el siguiente ejemplo:  
  
```vb  
' Option statements must precede all other source file lines.  
Option Strict On  
' Imports statement must precede all declarations in the source file.  
Imports System.Windows.Forms  
Public Sub accessMembers()  
    Dim p As Object  
    Dim q As System.Windows.Forms.Label  
    p = New System.Windows.Forms.Label  
    q = New System.Windows.Forms.Label  
    Dim j, k As Integer  
    ' The following statement generates a compiler ERROR.  
    j = p.Left  
    ' The following statement retrieves the left edge of the label in pixels.  
    k = q.Left  
End Sub  
```  
  
 En este ejemplo, `p` puede usar solo los miembros de la propia clase <xref:System.Object> , que no incluyen la propiedad `Left` . Por otro lado, `q` se ha declarado con el tipo <xref:System.Windows.Forms.Label>, así que puede usar todos los métodos y propiedades de la clase <xref:System.Windows.Forms.Label> en el espacio de nombres <xref:System.Windows.Forms> .  
  
## <a name="flexibility-of-object-variables"></a>Flexibilidad de las Variables de objeto  
 Cuando se trabaja con objetos en una jerarquía de herencia, tendrá la opción de clase que se debe usar para declarar las variables de objeto. Hora de tomar esta decisión, debe equilibrar la flexibilidad de asignación de objeto contra el acceso a los miembros de una clase. Por ejemplo, considere la jerarquía de herencia que conduce a la <xref:System.Windows.Forms.Form?displayProperty=nameWithType> clase:  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 Supongamos que la aplicación define una clase de formulario llamada `specialForm`, que hereda de la clase <xref:System.Windows.Forms.Form>. Puede declarar una variable de objeto que hace referencia específicamente a `specialForm`, como se muestra en el ejemplo siguiente.  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 La declaración en el ejemplo anterior limita la variable `nextForm` a objetos de clase `specialForm`, pero también pone todos los métodos y propiedades de `specialForm` disponibles para `nextForm`, así como todos los miembros de todas las clases desde el que `specialForm` hereda.  
  
 Hacer que una variable de objeto más general declarando que sea de tipo <xref:System.Windows.Forms.Form>, como se muestra en el ejemplo siguiente.  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 La declaración en el ejemplo anterior le permite asignar cualquier formulario de la aplicación para `anyForm`. Sin embargo, aunque `anyForm` puede tener acceso a todos los miembros de clase <xref:System.Windows.Forms.Form>, no puede usar cualquiera de los métodos o propiedades adicionales definidos para formularios específicos como `specialForm`.  
  
 Todos los miembros de una clase base están disponibles para las clases derivadas, pero los miembros adicionales de una clase derivada no están disponibles para la clase base.  
  
## <a name="see-also"></a>Vea también  
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Asignación de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Valores de las variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [Cómo: declarar una Variable de objeto y asignarle un objeto en Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)  
 [Obtener acceso a los miembros de un objeto](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)  
 [New (operador)](../../../../visual-basic/language-reference/operators/new-operator.md)  
 [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
