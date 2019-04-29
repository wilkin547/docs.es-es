---
title: Fundamentos de la herencia (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- derived classes [Visual Basic], inheritance
- MyClass keyword [Visual Basic], using
- MyBase keyword [Visual Basic], using
- Inherits statement [Visual Basic], inheritance
- overriding, Overridable keyword
- MustInherit keyword [Visual Basic], using
- Overrides keyword [Visual Basic], using
- inheritance
- MustInherit classes [Visual Basic]
- MustOverride keyword [Visual Basic], using
- classes [Visual Basic], derived
- NotInheritable keyword [Visual Basic], using
- base classes [Visual Basic], extending properties and methods [Visual Basic]
- NotOverridable keyword [Visual Basic], using
- base classes [Visual Basic], inheritance
- abstract classes [Visual Basic], inheritance
- overriding, Overrides keyword
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
ms.openlocfilehash: 5e4b8511145e758bf3d6328141be0e526965dccf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758475"
---
# <a name="inheritance-basics-visual-basic"></a>Fundamentos de la herencia (Visual Basic)
El `Inherits` instrucción se utiliza para declarar una nueva clase denominada una *clase derivada*, basándose en una clase existente, conocida como un *clase base*. Las clases derivadas heredan y pueden extender las propiedades, métodos, eventos, campos y constantes definidas en la clase base. La siguiente sección describe algunas de las reglas de herencia y los modificadores que se puede usar para cambiar las clases de manera heredan o se heredan:  
  
- De forma predeterminada, todas las clases son heredables a menos que marque con el `NotInheritable` palabra clave. Las clases pueden heredar de otras clases en el proyecto o de clases en otros ensamblados que se hace referencia su proyecto.  
  
- A diferencia de los lenguajes que permiten la herencia múltiple, Visual Basic permite la herencia única solo en las clases; es decir, las clases derivadas pueden tener sólo una clase base. Aunque no se permite la herencia múltiple en las clases, las clases pueden implementar varias interfaces, que pueden conseguir los mismos extremos de manera eficaz.  
  
- Para evitar la exposición de elementos restringidos en una clase base, el tipo de acceso de una clase derivada debe ser igual o más restrictivo que su clase base. Por ejemplo, un `Public` clase no puede heredar un `Friend` o un `Private` (clase) y un `Friend` clase no puede heredar un `Private` clase.  
  
## <a name="inheritance-modifiers"></a>Modificadores de herencia  
 Visual Basic presenta las siguientes instrucciones de nivel de clase y los modificadores para admitir la herencia:  
  
- `Inherits` instrucción: especifica la clase base.  
  
- `NotInheritable` modificador: evita que los programadores mediante la clase como clase base.  
  
- `MustInherit` modificador: Especifica que la clase está diseñada para su uso como clase base. Las instancias de `MustInherit` clases no se pueden crear directamente; solo se pueden crear instancias de clase como base de una clase derivada. (Otros lenguajes de programación, como C++ y C#, uso el término *clase abstracta* para describir esta clase.)  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a>Reemplazar propiedades y métodos en clases derivadas  
 De forma predeterminada, una clase derivada hereda las propiedades y métodos de su clase base. Si tiene una propiedad o método heredado para comportarse de manera diferente en la clase derivada puede ser *invalidar*. Es decir, puede definir una nueva implementación del método en la clase derivada. Los siguientes modificadores se utilizan para controlar cómo se reemplazan propiedades y métodos:  
  
- `Overridable` Permite una propiedad o método en una clase que se invalide en una clase derivada.  
  
- `Overrides` : Invalida un `Overridable` propiedad o método definido en la clase base.  
  
- `NotOverridable` : Impide que una propiedad o método que se invalida en una clase heredera. De forma predeterminada, `Public` métodos son `NotOverridable`.  
  
- `MustOverride` : Requiere que una clase derivada invalide la propiedad o método. Cuando el `MustOverride` se usa la palabra clave, la definición del método consta de solamente el `Sub`, `Function`, o `Property` instrucción. Se permite ninguna otra instrucción y, específicamente no hay ningún `End Sub` o `End Function` instrucción. `MustOverride` los métodos deben declararse en `MustInherit` clases.  
  
 Suponga que desea definir clases para controlar la nómina. Puede definir un tipo genérico `Payroll` clase que contiene un `RunPayroll` método que calcula la nómina de una semana típica. Se podría utilizar `Payroll` como una clase base para un método más especializado `BonusPayroll` (clase), que podría usarse al distribuir las bonificaciones del empleado.  
  
 El `BonusPayroll` clase puede heredar y reemplazar, el `PayEmployee` método definido en la base de `Payroll` clase.  
  
 En el ejemplo siguiente se define una clase base, `Payroll,` y una clase derivada, `BonusPayroll`, que reemplaza un método heredado, `PayEmployee`. Un procedimiento, `RunPayroll`, crea y, a continuación, pasa un `Payroll` objeto y un `BonusPayroll` objeto a una función, `Pay`, que se ejecuta el `PayEmployee` método de ambos objetos.  
  
 [!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]  
  
## <a name="the-mybase-keyword"></a>La palabra clave MyBase  
 El `MyBase` palabra clave se comporta como una variable de objeto que hace referencia a la clase de la instancia actual de una clase base. `MyBase` se suele utilizar para tener acceso a miembros de clase base que se reemplazan o sombrean en una clase derivada. En concreto, `MyBase.New` se usa para llamar explícitamente a un constructor de clase base desde un constructor de clase derivada.  
  
 Por ejemplo, suponga que está diseñando una clase derivada que reemplaza un método heredado de la clase base. El método invalidado puede llamar al método en la clase base y modificar el valor devuelto, tal como se muestra en el siguiente fragmento de código:  
  
 [!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]  
  
 La siguiente lista describe las restricciones sobre el uso de `MyBase`:  
  
- `MyBase` hace referencia a la clase base inmediata y sus miembros heredados. No se puede utilizar para tener acceso a `Private` miembros de la clase.  
  
- `MyBase` es una palabra clave, no un objeto real. `MyBase` no se asigna a una variable, pasar a los procedimientos o usado en un `Is` comparación.  
  
- El método que `MyBase` califica no tiene que definirse en la clase base inmediata; en su lugar puede definirse en una clase base heredada indirectamente. En una referencia calificada por `MyBase` se compilen correctamente, alguna clase base debe contener un método que coincide con el nombre y los tipos de parámetros que aparecen en la llamada.  
  
- No puede usar `MyBase` para llamar a `MustOverride` los métodos de clase base.  
  
- `MyBase` no se puede usar para calificar a sí mismo. Por lo tanto, no es válido el código siguiente:  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
- `MyBase` no se puede usar en los módulos.  
  
- `MyBase` no se puede usar para tener acceso a los miembros de clase base que están marcados como `Friend` si la clase base se encuentra en un ensamblado diferente.  
  
 Para obtener más información y otro ejemplo, vea [Cómo: Obtener acceso a una Variable que oculta una clase derivada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
## <a name="the-myclass-keyword"></a>La palabra clave MyClass  
 El `MyClass` palabra clave se comporta como una variable de objeto que hace referencia a la instancia actual de una clase como se implementaron originalmente. `MyClass` es similar a `Me`, pero llama cada método y propiedad en `MyClass` se tratan como si fuera el método o propiedad [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md). Por lo tanto, el método o propiedad no se ve afectado por el reemplazo de una clase derivada.  
  
- `MyClass` es una palabra clave, no un objeto real. `MyClass` no se asigna a una variable, pasar a los procedimientos o usado en un `Is` comparación.  
  
- `MyClass` hace referencia a la clase contenedora y sus miembros heredados.  
  
- `MyClass` se puede usar como un calificador para `Shared` miembros.  
  
- `MyClass` no se puede usar dentro de un `Shared` método, pero puede utilizarse para tener acceso a un miembro compartido de una clase dentro de un método de instancia.  
  
- `MyClass` no se puede usar en los módulos estándar.  
  
- `MyClass` puede usarse para calificar un método que se define en una clase base y que no tiene ninguna implementación del método proporcionado en esa clase. Este tipo de referencia tiene el mismo significado que `MyBase.` *método*.  
  
 En el ejemplo siguiente se comparan `Me` y `MyClass`.  
  
```vb
Class baseClass  
    Public Overridable Sub testMethod()  
        MsgBox("Base class string")  
    End Sub  
    Public Sub useMe()  
        ' The following call uses the calling class's method, even if   
        ' that method is an override.  
        Me.testMethod()  
    End Sub  
    Public Sub useMyClass()  
        ' The following call uses this instance's method and not any  
        ' override.  
        MyClass.testMethod()  
    End Sub  
End Class  
Class derivedClass : Inherits baseClass  
    Public Overrides Sub testMethod()  
        MsgBox("Derived class string")  
    End Sub  
End Class  
Class testClasses  
    Sub startHere()  
        Dim testObj As derivedClass = New derivedClass()  
        ' The following call displays "Derived class string".  
        testObj.useMe()  
        ' The following call displays "Base class string".  
        testObj.useMyClass()  
    End Sub  
End Class  
```  
  
 Aunque `derivedClass` invalida `testMethod`, `MyClass` palabra clave en `useMyClass` anula el efecto de reemplazo y el compilador se resuelve la llamada a la versión de la clase base `testMethod`.  
  
## <a name="see-also"></a>Vea también

- [Inherits (instrucción)](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
