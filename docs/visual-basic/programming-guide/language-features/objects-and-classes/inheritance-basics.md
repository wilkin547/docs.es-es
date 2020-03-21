---
title: Fundamentos de la herencia
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
ms.openlocfilehash: 89fcf2a14d8938d536aa72628218242811baa1a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401464"
---
# <a name="inheritance-basics-visual-basic"></a>Fundamentos de la herencia (Visual Basic)

La `Inherits` instrucción se utiliza para declarar una nueva clase, denominada *clase derivada*, basada en una clase existente, conocida como *clase base.* Las clases derivadas heredan y pueden extender las propiedades, métodos, eventos, campos y constantes definidos en la clase base. En la siguiente sección se describen algunas de las reglas de herencia y los modificadores que puede usar para cambiar la forma en que las clases heredan o se heredan:

- De forma predeterminada, todas las clases son heredables a menos que estén marcadas con la `NotInheritable` palabra clave. Las clases pueden heredar de otras clases del proyecto o de clases de otros ensamblados a los que hace referencia el proyecto.

- A diferencia de los lenguajes que permiten la herencia múltiple, Visual Basic solo permite la herencia única en las clases; es decir, las clases derivadas solo pueden tener una clase base. Aunque no se permite la herencia múltiple en las clases, las clases pueden implementar varias interfaces, lo que puede lograr eficazmente los mismos fines.

- Para evitar exponer elementos restringidos en una clase base, el tipo de acceso de una clase derivada debe ser igual o más restrictivo que su clase base. Por ejemplo, `Public` una clase `Friend` no `Private` puede heredar una o una clase y una `Friend` clase no puede heredar una `Private` clase.

## <a name="inheritance-modifiers"></a>Modificadores de herencia

Visual Basic presenta las siguientes instrucciones y modificadores de nivel de clase para admitir la herencia:

- `Inherits`statement — Especifica la clase base.

- `NotInheritable`modificador: impide que los programadores utilicen la clase como clase base.

- `MustInherit`modificador: especifica que la clase está pensada para su uso únicamente como clase base. Las instancias de `MustInherit` clases no se pueden crear directamente; solo se pueden crear como instancias de clase base de una clase derivada. (Otros lenguajes de programación, como C++ y C, usan el término *clase abstracta* para describir dicha clase.)

## <a name="overriding-properties-and-methods-in-derived-classes"></a>Propiedades y métodos de invalidación en clases derivadas

De forma predeterminada, una clase derivada hereda propiedades y métodos de su clase base. Si una propiedad o método heredado tiene que comportarse de forma diferente en la clase derivada, se puede *invalidar.* Es decir, puede definir una nueva implementación del método en la clase derivada. Los siguientes modificadores se utilizan para controlar cómo se reemplazan propiedades y métodos:

- `Overridable`: permite que una propiedad o método de una clase se invalide en una clase derivada.

- `Overrides`: reemplaza `Overridable` una propiedad o método definido en la clase base.

- `NotOverridable`: impide que una propiedad o método se invalide en una clase heredada. De forma `Public` predeterminada, los métodos son `NotOverridable`.

- `MustOverride`: requiere que una clase derivada invalide la propiedad o el método. Cuando `MustOverride` se utiliza la palabra clave, `Sub`la `Function`definición del método consta solo de la instrucción , , o `Property` . No se permiten otras declaraciones, y `End Sub` `End Function` específicamente no hay ninguna declaración o declaración. `MustOverride`métodos deben `MustInherit` declararse en clases.

Supongamos que desea definir clases para gestionar el cálculo de la nómina. Puede definir una `Payroll` clase genérica `RunPayroll` que contenga un método que calcule el cálculo de la nómina para una semana típica. A continuación, `Payroll` podría utilizar como clase `BonusPayroll` base para una clase más especializada, que podría utilizarse al distribuir bonificaciones de empleados.

La `BonusPayroll` clase puede heredar `PayEmployee` e invalidar el `Payroll` método definido en la clase base.

En el ejemplo siguiente `Payroll,` se define una `BonusPayroll`clase base y una `PayEmployee`clase derivada, , que reemplaza un método heredado, . `RunPayroll`Un procedimiento, , crea y, a continuación, pasa un `Payroll` objeto y un `BonusPayroll` objeto a una función, `Pay`, que ejecuta el `PayEmployee` método de ambos objetos.

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a>La palabra clave MyBase

La `MyBase` palabra clave se comporta como una variable de objeto que hace referencia a la clase base de la instancia actual de una clase. `MyBase`se utiliza con frecuencia para tener acceso a los miembros de la clase base que se reemplazan o sombrean en una clase derivada. En concreto, `MyBase.New` se utiliza para llamar explícitamente a un constructor de clase base desde un constructor de clase derivada.

Por ejemplo, supongamos que está diseñando una clase derivada que reemplaza un método heredado de la clase base. El método invalidado puede llamar al método en la clase base y modificar el valor devuelto como se muestra en el siguiente fragmento de código:

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

La siguiente lista describe las `MyBase`restricciones en el uso de:

- `MyBase`se refiere a la clase base inmediata y sus miembros heredados. No se puede `Private` usar para tener acceso a los miembros de la clase.

- `MyBase`es una palabra clave, no un objeto real. `MyBase`no se puede asignar a una variable, `Is` pasar a procedimientos o utilizarse en una comparación.

- El método `MyBase` que califica no tiene que definirse en la clase base inmediata; en su lugar puede definirse en una clase base hereditaria indirectamente. Para que una referencia `MyBase` calificada para compilar correctamente, alguna clase base debe contener un método que coincida con el nombre y los tipos de parámetros que aparecen en la llamada.

- No se `MyBase` puede `MustOverride` utilizar para llamar a métodos de clase base.

- `MyBase`no se puede utilizar para calificarse a sí mismo. Por lo tanto, el código siguiente no es válido:

  `MyBase.MyBase.BtnOK_Click()`

- `MyBase`no se puede utilizar en módulos.

- `MyBase`no se puede utilizar para tener `Friend` acceso a los miembros de la clase base que están marcados como si la clase base estuviera en un ensamblado diferente.

Para obtener más información y otro ejemplo, vea [Cómo: obtener acceso a una variable oculta por una clase derivada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).

## <a name="the-myclass-keyword"></a>La palabra clave MyClass

La `MyClass` palabra clave se comporta como una variable de objeto que hace referencia a la instancia actual de una clase como implementada originalmente. `MyClass`se `Me`asemeja , pero cada `MyClass` método y propiedad en la que se llama se trata como si el método o la propiedad [fueraNotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md). Por lo tanto, el método o propiedad no se ve afectada por la invalidación en una clase derivada.

- `MyClass`es una palabra clave, no un objeto real. `MyClass`no se puede asignar a una variable, `Is` pasar a procedimientos o utilizarse en una comparación.

- `MyClass`se refiere a la clase contenedora y sus miembros heredados.

- `MyClass`se puede utilizar como `Shared` calificador para los miembros.

- `MyClass`no se puede `Shared` utilizar dentro de un método, pero se puede utilizar dentro de un método de instancia para tener acceso a un miembro compartido de una clase.

- `MyClass`no se puede utilizar en módulos estándar.

- `MyClass`se puede usar para calificar un método que se define en una clase base y que no tiene ninguna implementación del método proporcionado en esa clase. Dicha referencia tiene el `MyBase.`mismo significado que *Method*.

En el ejemplo `Me` `MyClass`siguiente se comparan y .

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

Aunque `derivedClass` invalida `testMethod`, `MyClass` la `useMyClass` palabra clave en anula los efectos de invalidación y `testMethod`el compilador resuelve la llamada a la versión de clase base de .

## <a name="see-also"></a>Consulte también

- [Inherits (instrucción)](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
