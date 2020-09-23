---
title: Declaración de variables de objeto
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
ms.openlocfilehash: 74b1401df3dbb2d744de74734d10cbcd92e9689e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077051"
---
# <a name="object-variable-declaration-visual-basic"></a>Declaración de variables de objeto (Visual Basic)

Use una instrucción de declaración normal para declarar una variable de objeto. Para el tipo de datos, se especifica `Object` (es decir, el [tipo de datos Object](../../../language-reference/data-types/object-data-type.md)) o una clase más específica de la que se va a crear el objeto.  
  
 Declarar una variable como `Object` es igual que la declaración como <xref:System.Object?displayProperty=nameWithType> .  
  
 Cuando se declara una variable con una clase de objeto específica, puede tener acceso a todos los métodos y propiedades expuestos por esa clase y las clases de las que hereda. Si declara la variable con <xref:System.Object> , solo podrá tener acceso a los miembros de la <xref:System.Object> clase, a menos que Active `Option Strict Off` permitir el enlace en tiempo de ejecución.  
  
## <a name="declaration-syntax"></a>Sintaxis de la declaración  

 Use la siguiente sintaxis para declarar una variable de objeto:  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 También puede especificar [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md), `Protected Friend` , [Private](../../../language-reference/modifiers/private.md), [Shared](../../../language-reference/modifiers/shared.md)o [static](../../../language-reference/modifiers/static.md) en la declaración. Las siguientes declaraciones de ejemplo son válidas:  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a>Enlace en tiempo de ejecución y enlace temprano  

 A veces, se desconoce la clase específica hasta que se ejecuta el código. En este caso, debe declarar la variable de objeto con el `Object` tipo de datos. Esto crea una referencia general a cualquier tipo de objeto y la clase específica se asigna en tiempo de ejecución. Esto se denomina *enlace en tiempo de ejecución*. El enlace en tiempo de ejecución requiere tiempo de ejecución adicional. También limita el código a los métodos y propiedades de la clase que se le ha asignado más recientemente. Esto puede producir errores en tiempo de ejecución si el código intenta obtener acceso a miembros de una clase diferente.  
  
 Cuando conozca la clase específica en tiempo de compilación, debe declarar la variable de objeto para que sea de esa clase. Esto se denomina *enlace anticipado*. El enlace temprano mejora el rendimiento y garantiza el acceso del código a todos los métodos y propiedades de la clase específica. En las declaraciones de ejemplo anteriores, si variable `objA` solo usa objetos de clase <xref:System.Windows.Forms.Label?displayProperty=nameWithType> , debe especificar `As System.Windows.Forms.Label` en su declaración.  
  
### <a name="advantages-of-early-binding"></a>Ventajas del enlace anticipado  

 Declarar una variable de objeto como una clase específica proporciona varias ventajas:  
  
- Comprobación automática de tipos  
  
- Acceso garantizado a todos los miembros de la clase específica  
  
- Compatibilidad de Microsoft IntelliSense en el editor de código  
  
- Mejora de la legibilidad del código  
  
- Menos errores en el código  
  
- Errores detectados en tiempo de compilación en lugar de en tiempo de ejecución  
  
- Ejecución de código más rápida  
  
## <a name="access-to-object-variable-members"></a>Acceso a los miembros de variables de objeto  

 Cuando `Option Strict` se activa `On` , una variable de objeto solo puede tener acceso a los métodos y propiedades de la clase con la que se declara. Esto se ilustra en el siguiente ejemplo:  
  
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
  
## <a name="flexibility-of-object-variables"></a>Flexibilidad de las variables de objeto  

 Cuando se trabaja con objetos en una jerarquía de herencia, se puede elegir qué clase se debe usar para declarar las variables de objeto. Al elegir esta opción, debe equilibrar la flexibilidad de la asignación de objetos con respecto al acceso a los miembros de una clase. Por ejemplo, considere la jerarquía de herencia que conduce a la <xref:System.Windows.Forms.Form?displayProperty=nameWithType> clase:  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 Supongamos que la aplicación define una clase de formulario denominada `specialForm` , que hereda de la clase <xref:System.Windows.Forms.Form> . Puede declarar una variable de objeto que haga referencia específicamente a `specialForm` , como se muestra en el ejemplo siguiente.  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 La declaración en el ejemplo anterior limita la variable `nextForm` a objetos de clase `specialForm` , pero también hace que todos los métodos y propiedades de `specialForm` estén disponibles para `nextForm` , así como todos los miembros de todas las clases de las que `specialForm` hereda.  
  
 Para hacer que una variable de objeto sea más general, puede declararla como de tipo <xref:System.Windows.Forms.Form> , como se muestra en el ejemplo siguiente.  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 La declaración en el ejemplo anterior le permite asignar cualquier formulario de la aplicación a `anyForm` . Sin embargo, aunque `anyForm` puede tener acceso a todos los miembros de la clase <xref:System.Windows.Forms.Form> , no puede usar ninguno de los métodos o propiedades adicionales definidos para formularios específicos como `specialForm` .  
  
 Todos los miembros de una clase base están disponibles para las clases derivadas, pero los miembros adicionales de una clase derivada no están disponibles para la clase base.  
  
## <a name="see-also"></a>Vea también

- [Variables de objeto](object-variables.md)
- [Asignación de variables de objeto](object-variable-assignment.md)
- [Valores de las variables de objeto](object-variable-values.md)
- [Cómo: Declarar una variable de objeto y asignarle un objeto en Visual Basic](how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [Procedimiento para obtener acceso a los miembros de un objeto](how-to-access-members-of-an-object.md)
- [New (operador)](../../../language-reference/operators/new-operator.md)
- [Option Strict (instrucción)](../../../language-reference/statements/option-strict-statement.md)
- [Inferencia de tipo de variable local](local-type-inference.md)
