---
title: Sombrear en Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 489e1786b08085f229f66b2dbc434b96b06d86df
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="shadowing-in-visual-basic"></a>Sombrear en Visual Basic
Si dos elementos de programación comparten el mismo nombre, uno de ellos puede ocultar, o *instantáneas*, el otro se. En esta situación, el elemento sombreado no está disponible como referencia; en su lugar, cuando el código usa el nombre del elemento, el compilador de Visual Basic resuelve en el elemento reemplazado.  
  
## <a name="purpose"></a>Propósito  
 El propósito principal de sombrear es proteger la definición de los miembros de clase. La clase base puede sufrir un cambio que se crea un elemento con el mismo nombre que ya se ha definido. Si esto ocurre, el `Shadows` modificador fuerza referencias a través de la clase para que se resuelvan en el miembro definido, en lugar de en el nuevo elemento de clase base.  
  
## <a name="types-of-shadowing"></a>Tipos de sombreado  
 Un elemento puede prevalecer sobre otro elemento de dos maneras diferentes. El elemento que sombrea puede declararse dentro de una subregión de la región que contiene el elemento sombreado, en el que se consigue caso el sombreado *a través de ámbito*. O una clase derivada puede volver a definir un miembro de una clase base, en cuyo caso el sombreado se consigue *a través de la herencia*.  
  
### <a name="shadowing-through-scope"></a>Sombreado por ámbito  
 Es posible para la programación de elementos en el mismo módulo, clase o estructura tengan el mismo nombre pero con un ámbito diferente. Cuando dos elementos se declaran de esta manera y el código hace referencia al nombre que comparten, el elemento con el ámbito más restringido oculta al otro elemento (el ámbito de bloque es el más restringido).  
  
 Por ejemplo, un módulo puede definir una `Public` variable denominada `temp`, y un procedimiento en el módulo puede declarar una variable local denominada también `temp`. Las referencias a `temp` desde el procedimiento, tener acceso a la variable local, mientras que las referencias a `temp` desde fuera del procedimiento obtienen acceso a la `Public` variable. En este caso, la variable de procedimiento `temp` prevalece sobre la variable de módulo `temp`.  
  
 La ilustración siguiente muestra dos variables, ambos denominados `temp`. La variable local `temp` prevalece sobre la variable miembro `temp` cuando se tiene acceso desde dentro de su propio procedimiento `p`. Sin embargo, la `MyClass` palabra clave omite el sombreado y tiene acceso a la variable miembro.  
  
 ![Diagrama gráfico de sombreado por ámbito](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")  
Sombreado por ámbito  
  
 Para obtener un ejemplo de sombreado por ámbito, consulte [Cómo: ocultar una Variable con el mismo nombre que la Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).  
  
### <a name="shadowing-through-inheritance"></a>Sombreado por herencia  
 Si una clase derivada vuelve a definir un elemento de programación que se hereda de una clase base, el elemento que redefine ensombrece al elemento original. Puede reemplazar cualquier tipo de elemento declarado o conjunto de elementos sobrecargados, con cualquier otro tipo. Por ejemplo, un `Integer` variable puede reemplazar un `Function` procedimiento. Si sombrea un procedimiento con otro, puede utilizar una lista de parámetros distinta y un tipo de valor devuelto distinto.  
  
 La ilustración siguiente muestra una clase base `b` y una clase derivada `d` que hereda de `b`. La clase base define un procedimiento denominado `proc`, y la clase derivada lo sombrea con otro procedimiento con el mismo nombre. La primera `Call` instrucción accede al sombreado `proc` en la clase derivada. Sin embargo, la `MyBase` palabra clave omite el sombreado y tiene acceso al procedimiento sombreado en la clase base.  
  
 ![Diagrama gráfico de sombreado por herencia](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")  
Sombreado por herencia  
  
 Para obtener un ejemplo de sombreado por herencia, consulte [Cómo: ocultar una Variable con el mismo nombre que la Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) y [Cómo: ocultar una Variable heredada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).  
  
#### <a name="shadowing-and-access-level"></a>El sombreado y el nivel de acceso  
 El elemento reemplazado no siempre es accesible desde el código que utiliza la clase derivada. Por ejemplo, podría declararse `Private`. En tal caso, se rechaza el sombreado y el compilador resuelve cualquier referencia al mismo elemento tendría si no hubiera habido ningún sombreado. Este elemento es el elemento accesible menos derivación en sentido pasos hacia atrás desde la clase que sombrea. Si el elemento sombreado es un procedimiento, la resolución es la versión accesible más próxima con el mismo nombre, lista de parámetros y tipo de valor devuelto.  
  
 En el ejemplo siguiente se muestra una jerarquía de herencia de tres clases. Cada clase define un `Sub` procedimiento `display`, y cada clase derivada sombrea el `display` procedimiento en su clase base.  
  
```  
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
  
 En el ejemplo anterior, la clase derivada `secondClass` sombras `display` con un `Private` procedimiento. Al módulo `callDisplay` llamadas `display` en `secondClass`, el código que realiza la llamada está fuera de `secondClass` y, por tanto, no se puede obtener acceso a la privada `display` procedimiento. Se rechaza el sombreado y el compilador resuelve la referencia a la clase base `display` procedimiento.  
  
 Sin embargo, la otra clase derivada `thirdClass` declara `display` como `Public`, por lo que el código en `callDisplay` puede tener acceso a él.  
  
## <a name="shadowing-and-overriding"></a>Sombrear y reemplazar  
 No confunda sombrear y reemplazar. Ambos se usan cuando una clase derivada hereda de una clase base y ambos vuelven a definir un elemento declarado con otro. Pero hay diferencias significativas entre los dos. Para obtener una comparación, consulte [diferencias entre sombrear y reemplazando](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).  
  
## <a name="shadowing-and-overloading"></a>Sombreado y sobrecarga  
 Si sombrea el mismo elemento de clase base con más de un elemento de la clase derivada, los elementos sombreados se convierten en las versiones sobrecargadas de ese elemento. Para obtener más información, consulte [sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## <a name="accessing-a-shadowed-element"></a>Obtener acceso a un elemento sombreado  
 Cuando tiene acceso a un elemento de una clase derivada, normalmente se logra a través de la instancia actual de dicha clase derivada, calificando el nombre del elemento con el `Me` palabra clave. Si la clase derivada ensombrece al elemento de la clase base, puede tener acceso al elemento de clase base mediante su calificación con la `MyBase` palabra clave.  
  
 Para obtener un ejemplo de obtener acceso a un elemento reemplazado, consulte [Cómo: obtener acceso a una Variable oculta una clase derivada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
### <a name="declaration-of-the-object-variable"></a>Declaración de la Variable de objeto  
 Cómo crear la variable de objeto también puede afectar a si la clase derivada tiene acceso a un elemento de sombreado o el elemento sombreado. En el ejemplo siguiente se crea dos objetos de una clase derivada, pero un objeto se declara como la clase base y el otro como la clase derivada.  
  
```  
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
  
 En el ejemplo anterior, la variable `basObj` se declara como clase base. Asignar un `dervCls` objeto constituye una conversión de ampliación y, por tanto, es válida. Sin embargo, la clase base no puede obtener acceso a la versión de sombreado de la variable `z` en la clase derivada, por lo que el compilador resuelve `basObj.z` para el valor original de la clase base.  
  
## <a name="see-also"></a>Vea también  
 [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [Fundamentos de la herencia](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
