---
title: Sombreado
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], shadowing
- overriding, and shadowing
- shadowing
- duplicate names [Visual Basic]
- shadowing, by inheritance
- declared elements [Visual Basic], referencing
- shadowing, by scope
- declared elements [Visual Basic], hiding
- naming conflicts, shadowing
- declared elements [Visual Basic], shadowing
- shadowing, and overriding
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic], about
- objects [Visual Basic], names
- names [Visual Basic], shadowing
ms.assetid: 54bb4c25-12c4-4181-b4a0-93546053964e
ms.openlocfilehash: 20a33478f622fca6d3183772f53dcb3e72f79409
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266890"
---
# <a name="shadowing-in-visual-basic"></a>Sombrear en Visual Basic
Cuando dos elementos de programación comparten el mismo nombre, uno de ellos puede ocultar, o *sombra,* el otro. En tal situación, el elemento sombreado no está disponible como referencia; en su lugar, cuando el código usa el nombre del elemento, el compilador de Visual Basic lo resuelve en el elemento de sombreado.  
  
## <a name="purpose"></a>Propósito  
 El propósito principal del sombreado es proteger la definición de los miembros de la clase. La clase base puede sufrir un cambio que crea un elemento con el mismo nombre que ya ha definido. Si esto sucede, el `Shadows` modificador fuerza las referencias a través de la clase para que se resuelvan en el miembro que definió, en lugar del nuevo elemento de clase base.  
  
## <a name="types-of-shadowing"></a>Tipos de Sombras  
 Un elemento puede sombrear otro elemento de dos maneras diferentes. El elemento de sombreado se puede declarar dentro de una subregión de la región que contiene el elemento sombreado, en cuyo caso el sombreado se realiza *a través*del ámbito . O una clase derivada puede redefinir un miembro de una clase base, en cuyo caso el sombreado se realiza *a través*de la herencia.  
  
### <a name="shadowing-through-scope"></a>Sombreado a través del alcance  
 Es posible que los elementos de programación del mismo módulo, clase o estructura tengan el mismo nombre pero un ámbito diferente. Cuando se declaran dos elementos de esta manera y el código hace referencia al nombre que comparten, el elemento con el ámbito más estrecho sombrea el otro elemento (el ámbito de bloque es el más estrecho).  
  
 Por ejemplo, un módulo `Public` puede `temp`definir una variable denominada , y un `temp`procedimiento dentro del módulo puede declarar una variable local también denominada . Las `temp` referencias desde dentro del procedimiento tienen `temp` acceso a la `Public` variable local, mientras que las referencias desde fuera del procedimiento tienen acceso a la variable. En este caso, `temp` la variable `temp`de procedimiento sombrea la variable de módulo .  
  
 En la ilustración siguiente se `temp`muestran dos variables, ambas denominadas . La variable `temp` local sombrea la variable `temp` `p`miembro cuando se accede desde su propio procedimiento. Sin `MyClass` embargo, la palabra clave omite el sombreado y tiene acceso a la variable miembro.  
  
 ![Gráfico que muestra sombras a través del ámbito.](./media/shadowing/shadow-scope-diagram.gif)
  
 Para obtener un ejemplo de sombreado a través del ámbito, vea [Cómo: Ocultar una variable con el mismo nombre que](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)la variable .  
  
### <a name="shadowing-through-inheritance"></a>Sombreado a través de la herencia  
 Si una clase derivada redefine un elemento de programación heredado de una clase base, el elemento de redefinición sombrea el elemento original. Puede sombrear cualquier tipo de elemento declarado, o conjunto de elementos sobrecargados, con cualquier otro tipo. Por ejemplo, `Integer` una variable `Function` puede sombrear un procedimiento. Si sombrea un procedimiento con otro procedimiento, puede utilizar una lista de parámetros diferente y un tipo de valor devuelto diferente.  
  
 En la ilustración `b` siguiente se muestra `d` una clase `b`base y una clase derivada que hereda de . La clase base define `proc`un procedimiento denominado y la clase derivada lo sombrea con otro procedimiento del mismo nombre. La `Call` primera instrucción tiene `proc` acceso al sombreado de la clase derivada. Sin `MyBase` embargo, la palabra clave omite el sombreado y tiene acceso al procedimiento sombreado en la clase base.  
  
 ![Diagrama gráfico de sombreado por herencia](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 Para obtener un ejemplo de sombreado a través de la herencia, vea [Cómo: Ocultar una variable con el mismo nombre que](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) la variable y [Cómo: Ocultar una variable heredada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).  
  
#### <a name="shadowing-and-access-level"></a>Sombreado y nivel de acceso  
 El elemento de sombreado no siempre es accesible desde el código mediante la clase derivada. Por ejemplo, podría `Private`declararse . En tal caso, se derrota el sombreado y el compilador resuelve cualquier referencia al mismo elemento que tendría si no hubiera habido ninguna sombra. Este elemento es el elemento accesible el menor número de pasos derivacionales hacia atrás desde la clase de sombreado. Si el elemento sombreado es un procedimiento, la resolución es a la versión accesible más cercana con el mismo nombre, lista de parámetros y tipo de valor devuelto.  
  
 En el ejemplo siguiente se muestra una jerarquía de herencia de tres clases. Cada clase `Sub` define `display`un procedimiento y cada `display` clase derivada sombrea el procedimiento en su clase base.  
  
```vb  
Public Class firstClass  
    Public Sub display()  
        MsgBox("This is firstClass")  
    End Sub  
End Class  
Public Class secondClass  
    Inherits firstClass  
    Private Shadows Sub display()  
        MsgBox("This is secondClass")  
    End Sub  
End Class  
Public Class thirdClass  
    Inherits secondClass  
    Public Shadows Sub display()  
        MsgBox("This is thirdClass")  
    End Sub  
End Class  
Module callDisplay  
    Dim first As New firstClass  
    Dim second As New secondClass  
    Dim third As New thirdClass  
    Public Sub callDisplayProcedures()  
        ' The following statement displays "This is firstClass".  
        first.display()  
        ' The following statement displays "This is firstClass".  
        second.display()  
        ' The following statement displays "This is thirdClass".  
        third.display()  
    End Sub  
End Module  
```  
  
 En el ejemplo anterior, la `secondClass` `display` clase `Private` derivada se sombrea con un procedimiento. Cuando `callDisplay` el `display` `secondClass`módulo llama adentro, el código de llamada está fuera `secondClass` y, por lo tanto, no puede tener acceso al procedimiento privado. `display` Se derrota el sombreado y el compilador resuelve la `display` referencia al procedimiento de clase base.  
  
 Sin embargo, la `thirdClass` clase `display` `Public`derivada adicional declara `callDisplay` como , por lo que el código en puede tener acceso a ella.  
  
## <a name="shadowing-and-overriding"></a>Sombra y anulación  
 No confunda las sombras con la invalidación. Ambos se utilizan cuando una clase derivada hereda de una clase base y ambos redefinen un elemento declarado con otro. Pero hay diferencias significativas entre los dos. Para obtener una comparación, consulte [Diferencias entre sombreado y anulación](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).  
  
## <a name="shadowing-and-overloading"></a>Sombreado y sobrecarga  
 Si sombrea el mismo elemento de clase base con más de un elemento en la clase derivada, los elementos de sombreado se convierten en versiones sobrecargadas de ese elemento. Para obtener más información, consulta [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## <a name="accessing-a-shadowed-element"></a>Acceso a un elemento sombreado  
 Cuando se tiene acceso a un elemento desde una clase derivada, normalmente se hace a través de la instancia actual de esa clase derivada, calificando el nombre del elemento con la `Me` palabra clave. Si la clase derivada sombrea el elemento de la clase base, puede `MyBase` tener acceso al elemento de clase base calificándolo con la palabra clave.  
  
 Para obtener un ejemplo de acceso a un elemento sombreado, vea [Cómo: obtener acceso a una variable oculta por una clase derivada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
### <a name="declaration-of-the-object-variable"></a>Declaración de la variable de objeto  
 La forma de crear la variable de objeto también puede afectar a si la clase derivada tiene acceso a un elemento de sombreado o al elemento sombreado. En el ejemplo siguiente se crean dos objetos a partir de una clase derivada, pero un objeto se declara como la clase base y el otro como la clase derivada.  
  
```vb  
Public Class baseCls  
    ' The following statement declares the element that is to be shadowed.  
    Public z As Integer = 100  
End Class  
Public Class dervCls  
    Inherits baseCls  
    ' The following statement declares the shadowing element.  
    Public Shadows z As String = "*"  
End Class  
Public Class useClasses  
    ' The following statement creates the object declared as the base class.  
    Dim basObj As baseCls = New dervCls()  
    ' Note that dervCls widens to its base class baseCls.  
    ' The following statement creates the object declared as the derived class.  
    Dim derObj As dervCls = New dervCls()  
    Public Sub showZ()
    ' The following statement outputs 100 (the shadowed element).  
        MsgBox("Accessed through base class: " & basObj.z)  
    ' The following statement outputs "*" (the shadowing element).  
        MsgBox("Accessed through derived class: " & derObj.z)  
    End Sub  
End Class  
```  
  
 En el ejemplo anterior, `basObj` la variable se declara como la clase base. Asignarle `dervCls` un objeto constituye una conversión cada vez mayor y, por lo tanto, es válida. Sin embargo, la clase base no `z` puede tener acceso a la versión de sombreado de la variable en la clase derivada, por lo que el compilador se resuelve `basObj.z` en el valor de clase base original.  
  
## <a name="see-also"></a>Consulte también

- [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [Invalidaciones](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Fundamentos de la herencia](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
