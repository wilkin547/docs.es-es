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
ms.openlocfilehash: 81e54875a3c1a4bbc5f5631e7ebac649a2e5afaf
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085898"
---
# <a name="shadowing-in-visual-basic"></a>Sombrear en Visual Basic

Cuando dos elementos de programación comparten el mismo nombre, uno de ellos puede ocultar, o *sombrear*, el otro. En tal situación, el elemento sombreado no está disponible como referencia; en su lugar, cuando el código usa el nombre del elemento, el compilador Visual Basic lo resuelve en el elemento de sombreado.  
  
## <a name="purpose"></a>Propósito  

 El propósito principal de la sombra es proteger la definición de los miembros de clase. La clase base puede someterse a un cambio que crea un elemento con el mismo nombre que el que ya se ha definido. Si esto ocurre, el `Shadows` modificador fuerza las referencias a través de la clase para que se resuelvan en el miembro definido, en lugar de en el nuevo elemento de clase base.  
  
## <a name="types-of-shadowing"></a>Tipos de sombreado  

 Un elemento puede prevalecer sobre otro elemento de dos maneras diferentes. El elemento de sombreado se puede declarar dentro de una subregión de la región que contiene el elemento sombreado, en cuyo caso la sombra se logra *a través del ámbito*. O una clase derivada puede volver a definir un miembro de una clase base, en cuyo caso la sombra se realiza *a través*de la herencia.  
  
### <a name="shadowing-through-scope"></a>Sombreado a través del ámbito  

 Es posible que los elementos de programación del mismo módulo, clase o estructura tengan el mismo nombre pero con un ámbito diferente. Cuando dos elementos se declaran de esta manera y el código hace referencia al nombre que comparten, el elemento con el ámbito más estrecho prevalece sobre el otro elemento (el ámbito de bloque es el más estrecho).  
  
 Por ejemplo, un módulo puede definir una `Public` variable denominada `temp` y un procedimiento dentro del módulo puede declarar una variable local denominada también `temp` . Las referencias a `temp` desde dentro del procedimiento obtienen acceso a la variable local, mientras que las referencias a `temp` desde fuera del procedimiento tienen acceso a la `Public` variable. En este caso, la variable de procedimiento `temp` prevalece sobre la variable de módulo `temp` .  
  
 En la ilustración siguiente se muestran dos variables, denominadas `temp` . La variable local `temp` prevalece sobre la variable miembro `temp` cuando se tiene acceso a ella desde dentro de su propio procedimiento `p` . Sin embargo, la `MyClass` palabra clave omite el sombreado y obtiene acceso a la variable miembro.  
  
 ![Gráfico que muestra el sombreado en el ámbito.](./media/shadowing/shadow-scope-diagram.gif)
  
 Para obtener un ejemplo de sombreado a través del ámbito, consulte [Cómo: ocultar una variable con el mismo nombre que la variable](how-to-hide-a-variable-with-the-same-name-as-your-variable.md).  
  
### <a name="shadowing-through-inheritance"></a>Sombrear a través de la herencia  

 Si una clase derivada vuelve a definir un elemento de programación heredado de una clase base, el elemento que se va a redefinir prevalecerá sobre el elemento original. Puede sombrear cualquier tipo de elemento declarado, o bien un conjunto de elementos sobrecargados, con cualquier otro tipo. Por ejemplo, una `Integer` variable puede prevalecer sobre un `Function` procedimiento. Si sombrea un procedimiento con otro procedimiento, puede usar una lista de parámetros diferente y un tipo de valor devuelto diferente.  
  
 En la ilustración siguiente se muestra una clase base `b` y una clase derivada `d` que hereda de `b` . La clase base define un procedimiento denominado `proc` y la clase derivada lo sombrea con otro procedimiento con el mismo nombre. La primera `Call` instrucción tiene acceso al sombreado `proc` en la clase derivada. Sin embargo, la `MyBase` palabra clave omite el sombreado y obtiene acceso al procedimiento sombreado en la clase base.  
  
 ![Diagrama gráfico de sombreado por herencia](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 Para obtener un ejemplo de sombreado a través de la herencia, vea [Cómo: ocultar una variable con el mismo nombre que la variable](how-to-hide-a-variable-with-the-same-name-as-your-variable.md) y [Cómo: ocultar una variable heredada](how-to-hide-an-inherited-variable.md).  
  
#### <a name="shadowing-and-access-level"></a>Nivel de acceso y sombreado  

 No siempre se puede obtener acceso al elemento de sombreado desde el código mediante la clase derivada. Por ejemplo, podría declararse `Private` . En tal caso, la sombra es derrotada y el compilador resuelve cualquier referencia al mismo elemento que tendría si no hubiese ninguna sombra. Este elemento es el elemento accesible el menos pasos de derivación hacia atrás desde la clase de sombreado. Si el elemento sombreado es un procedimiento, la resolución es a la versión accesible más cercana con el mismo nombre, lista de parámetros y tipo de valor devuelto.  
  
 En el ejemplo siguiente se muestra una jerarquía de herencia de tres clases. Cada clase define un `Sub` procedimiento `display` y cada clase derivada sombrea el `display` procedimiento en su clase base.  
  
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
  
 En el ejemplo anterior, la clase derivada `secondClass` prevalece sobre `display` un `Private` procedimiento. Cuando `callDisplay` el módulo llama a `display` en `secondClass` , el código de llamada está fuera `secondClass` y, por tanto, no puede tener acceso al `display` procedimiento privado. La sombra es derrotada y el compilador resuelve la referencia al procedimiento de la clase base `display` .  
  
 Sin embargo, la clase derivada adicional `thirdClass` declara `display` como `Public` , por lo que el código de `callDisplay` puede tener acceso a ella.  
  
## <a name="shadowing-and-overriding"></a>Sombrear e invalidar  

 No confunda el sombreado con la invalidación. Ambos se usan cuando una clase derivada hereda de una clase base y ambos vuelven a definir un elemento declarado con otro. Pero hay diferencias significativas entre los dos. Para obtener una comparación, vea [diferencias entre la sombra y el reemplazo](differences-between-shadowing-and-overriding.md).  
  
## <a name="shadowing-and-overloading"></a>Sombreado y sobrecarga  

 Si sombrea el mismo elemento de clase base con más de un elemento en la clase derivada, los elementos de sombreado pasan a ser versiones sobrecargadas de ese elemento. Para obtener más información, consulta [Procedure Overloading](../procedures/procedure-overloading.md).  
  
## <a name="accessing-a-shadowed-element"></a>Obtener acceso a un elemento con sombra  

 Al tener acceso a un elemento desde una clase derivada, normalmente lo hace a través de la instancia actual de esa clase derivada, calificando el nombre del elemento con la `Me` palabra clave. Si la clase derivada sombrea el elemento en la clase base, puede tener acceso al elemento de clase base si lo califica con la `MyBase` palabra clave.  
  
 Para obtener un ejemplo de acceso a un elemento con sombra, vea [Cómo: obtener acceso a una variable oculta por una clase derivada](how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
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
  
 En el ejemplo anterior, la variable `basObj` se declara como la clase base. Asignar un `dervCls` objeto a él constituye una conversión de ampliación y, por tanto, es válida. Sin embargo, la clase base no puede tener acceso a la versión de sombreado de la variable `z` en la clase derivada, por lo que el compilador se resuelve `basObj.z` en el valor de la clase base original.  
  
## <a name="see-also"></a>Vea también

- [References to Declared Elements](references-to-declared-elements.md)
- [Ámbito en Visual Basic](scope.md)
- [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)
- [Shadows](../../../language-reference/modifiers/shadows.md)
- [Invalidaciones](../../../language-reference/modifiers/overrides.md)
- [Me, My, MyBase y MyClass](../../program-structure/me-my-mybase-and-myclass.md)
- [Fundamentos de la herencia](../objects-and-classes/inheritance-basics.md)
