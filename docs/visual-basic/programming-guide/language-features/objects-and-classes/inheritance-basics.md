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
ms.openlocfilehash: 3bf1847f618a642d26df4aa1c5247a4ba2bd3b23
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411784"
---
# <a name="inheritance-basics-visual-basic"></a>Fundamentos de la herencia (Visual Basic)

La `Inherits` instrucción se utiliza para declarar una nueva clase, denominada *clase derivada*, basada en una clase existente, conocida como *clase base*. Las clases derivadas heredan y pueden extender las propiedades, los métodos, los eventos, los campos y las constantes definidos en la clase base. En la sección siguiente se describen algunas de las reglas de herencia y los modificadores que se pueden usar para cambiar la forma en que las clases heredan o se heredan:

- De forma predeterminada, todas las clases se pueden heredar a menos que estén marcadas con la `NotInheritable` palabra clave. Las clases pueden heredar de otras clases del proyecto o de clases de otros ensamblados a los que hace referencia el proyecto.

- A diferencia de los lenguajes que permiten la herencia múltiple, Visual Basic solo permite la herencia única en las clases; es decir, las clases derivadas solo pueden tener una clase base. Aunque no se permite la herencia múltiple en las clases, las clases pueden implementar varias interfaces, lo que puede lograr de forma eficaz los mismos extremos.

- Para evitar la exposición de elementos restringidos en una clase base, el tipo de acceso de una clase derivada debe ser igual o más restrictivo que su clase base. Por ejemplo, una `Public` clase no puede heredar una `Friend` `Private` clase o, y una `Friend` clase no puede heredar una `Private` clase.

## <a name="inheritance-modifiers"></a>Modificadores de herencia

Visual Basic presenta las siguientes instrucciones y modificadores de nivel de clase para admitir la herencia:

- `Inherits`instrucción: especifica la clase base.

- `NotInheritable`modificador: impide que los programadores usen la clase como clase base.

- `MustInherit`modificador: especifica que la clase está pensada para usarse solo como una clase base. Las instancias de `MustInherit` clases no se pueden crear directamente; solo se pueden crear como instancias de clase base de una clase derivada. (Otros lenguajes de programación, como C++ y C#, usan el término *clase abstracta* para describir una clase de este tipo).

## <a name="overriding-properties-and-methods-in-derived-classes"></a>Reemplazar propiedades y métodos en clases derivadas

De forma predeterminada, una clase derivada hereda propiedades y métodos de su clase base. Si una propiedad o un método heredado tienen que comportarse de forma diferente en la clase derivada, se puede *invalidar*. Es decir, puede definir una nueva implementación del método en la clase derivada. Los siguientes modificadores se utilizan para controlar cómo se reemplazan propiedades y métodos:

- `Overridable`: Permite que una propiedad o un método de una clase se invalide en una clase derivada.

- `Overrides`: Reemplaza una `Overridable` propiedad o un método definidos en la clase base.

- `NotOverridable`: Impide que una propiedad o un método se invalide en una clase heredada. De forma predeterminada, `Public` los métodos son `NotOverridable` .

- `MustOverride`: Requiere que una clase derivada invalide la propiedad o el método. Cuando `MustOverride` se usa la palabra clave, la definición del método consta únicamente de la `Sub` `Function` instrucción, o `Property` . No se permiten otras instrucciones y, en concreto, no hay ninguna `End Sub` `End Function` instrucción o. `MustOverride`los métodos deben declararse en `MustInherit` clases.

Supongamos que desea definir clases para controlar la nómina. Podría definir una clase genérica `Payroll` que contiene un `RunPayroll` método que calcula la nómina para una semana típica. Después, puede usar `Payroll` como clase base para una clase más especializada `BonusPayroll` , que podría usarse al distribuir las bonificaciones de empleado.

La `BonusPayroll` clase puede heredar e invalidar el `PayEmployee` método definido en la `Payroll` clase base.

En el ejemplo siguiente se define una clase base `Payroll,` y una clase derivada, `BonusPayroll` , que invalida un método heredado, `PayEmployee` . Un procedimiento, `RunPayroll` , crea y, a continuación, pasa un `Payroll` objeto y un `BonusPayroll` objeto a una función, `Pay` , que ejecuta el `PayEmployee` método de ambos objetos.

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a>La palabra clave MyBase

La `MyBase` palabra clave se comporta como una variable de objeto que hace referencia a la clase base de la instancia actual de una clase. `MyBase`se usa con frecuencia para tener acceso a los miembros de clase base que se invalidan o se sombrean en una clase derivada. En concreto, `MyBase.New` se usa para llamar explícitamente a un constructor de clase base desde un constructor de clase derivada.

Por ejemplo, supongamos que está diseñando una clase derivada que reemplaza un método heredado de la clase base. El método invalidado puede llamar al método de la clase base y modificar el valor devuelto como se muestra en el siguiente fragmento de código:

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

En la lista siguiente se describen las restricciones en el uso de `MyBase` :

- `MyBase`hace referencia a la clase base inmediata y a sus miembros heredados. No se puede usar para tener acceso a `Private` los miembros de la clase.

- `MyBase`es una palabra clave, no un objeto real. `MyBase`no se puede asignar a una variable, pasar a procedimientos ni usar en una `Is` comparación.

- No es necesario definir el método que `MyBase` califica en la clase base inmediata; en su lugar, se puede definir en una clase base heredada indirectamente. Para que una referencia calificada por `MyBase` se compile correctamente, alguna clase base debe contener un método que coincida con el nombre y los tipos de parámetros que aparecen en la llamada.

- No se puede usar `MyBase` para llamar a `MustOverride` métodos de clase base.

- `MyBase`no se puede usar para calificarse a sí mismo. Por lo tanto, el código siguiente no es válido:

  `MyBase.MyBase.BtnOK_Click()`

- `MyBase`no se puede usar en módulos.

- `MyBase`no se puede usar para tener acceso a los miembros de clase base marcados como `Friend` si la clase base se encuentra en un ensamblado diferente.

Para obtener más información y otro ejemplo, vea [Cómo: obtener acceso a una variable oculta por una clase derivada](../declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).

## <a name="the-myclass-keyword"></a>La palabra clave MyClass

La `MyClass` palabra clave se comporta como una variable de objeto que hace referencia a la instancia actual de una clase tal y como se implementó originalmente. `MyClass`se parece a `Me` , pero todas las llamadas de método y propiedad en `MyClass` se tratan como si el método o la propiedad fueran [NotOverridable](../../../language-reference/modifiers/notoverridable.md). Por lo tanto, el método o la propiedad no se ven afectados por el reemplazo en una clase derivada.

- `MyClass`es una palabra clave, no un objeto real. `MyClass`no se puede asignar a una variable, pasar a procedimientos ni usar en una `Is` comparación.

- `MyClass`hace referencia a la clase contenedora y a sus miembros heredados.

- `MyClass`se puede utilizar como calificador para `Shared` los miembros.

- `MyClass`no se puede usar dentro de un `Shared` método, pero se puede usar dentro de un método de instancia para tener acceso a un miembro compartido de una clase.

- `MyClass`no se puede usar en módulos estándar.

- `MyClass`se puede usar para calificar un método que se define en una clase base y que no tiene ninguna implementación del método proporcionado en esa clase. Este tipo de referencia tiene el mismo significado que el `MyBase.` *método*.

En el ejemplo siguiente se comparan `Me` y `MyClass` .

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

Aunque `derivedClass` invalida `testMethod` , la `MyClass` palabra clave en anula `useMyClass` los efectos de la invalidación, y el compilador resuelve la llamada a la versión de la clase base de `testMethod` .

## <a name="see-also"></a>Consulte también

- [Inherits Statement](../../../language-reference/statements/inherits-statement.md)
- [Me, My, MyBase y MyClass](../../program-structure/me-my-mybase-and-myclass.md)
