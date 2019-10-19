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
ms.openlocfilehash: 8a75b75ef9acb4c89f4c7d05f1410d4ca70e680b
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582747"
---
# <a name="inheritance-basics-visual-basic"></a>Fundamentos de la herencia (Visual Basic)

La instrucción `Inherits` se utiliza para declarar una nueva clase, denominada *clase derivada*, basada en una clase existente, conocida como *clase base*. Las clases derivadas heredan y pueden extender las propiedades, los métodos, los eventos, los campos y las constantes definidos en la clase base. En la sección siguiente se describen algunas de las reglas de herencia y los modificadores que se pueden usar para cambiar la forma en que las clases heredan o se heredan:

- De forma predeterminada, todas las clases se pueden heredar a menos que estén marcadas con la palabra clave `NotInheritable`. Las clases pueden heredar de otras clases del proyecto o de clases de otros ensamblados a los que hace referencia el proyecto.

- A diferencia de los lenguajes que permiten la herencia múltiple, Visual Basic solo permite la herencia única en las clases; es decir, las clases derivadas solo pueden tener una clase base. Aunque no se permite la herencia múltiple en las clases, las clases pueden implementar varias interfaces, lo que puede lograr de forma eficaz los mismos extremos.

- Para evitar la exposición de elementos restringidos en una clase base, el tipo de acceso de una clase derivada debe ser igual o más restrictivo que su clase base. Por ejemplo, una clase `Public` no puede heredar un `Friend` o una clase `Private`, y una clase `Friend` no puede heredar una clase `Private`.

## <a name="inheritance-modifiers"></a>Modificadores de herencia

Visual Basic presenta las siguientes instrucciones y modificadores de nivel de clase para admitir la herencia:

- instrucción `Inherits`: especifica la clase base.

- `NotInheritable` modificador: impide que los programadores usen la clase como clase base.

- `MustInherit` modificador: especifica que la clase está pensada para usarse solo como una clase base. Las instancias de clases de `MustInherit` no se pueden crear directamente. solo se pueden crear como instancias de clase base de una clase derivada. (Otros lenguajes de programación, C++ como C#y, usan el término *clase abstracta* para describir este tipo de clase).

## <a name="overriding-properties-and-methods-in-derived-classes"></a>Reemplazar propiedades y métodos en clases derivadas

De forma predeterminada, una clase derivada hereda propiedades y métodos de su clase base. Si una propiedad o un método heredado tienen que comportarse de forma diferente en la clase derivada, se puede *invalidar*. Es decir, puede definir una nueva implementación del método en la clase derivada. Los siguientes modificadores se utilizan para controlar cómo se reemplazan propiedades y métodos:

- `Overridable`: permite que una propiedad o un método de una clase se invalide en una clase derivada.

- `Overrides`: reemplaza una propiedad de `Overridable` o un método definido en la clase base.

- `NotOverridable`: impide que una propiedad o un método se invalide en una clase heredada. De forma predeterminada, `Public` métodos son `NotOverridable`.

- `MustOverride`: requiere que una clase derivada invalide la propiedad o el método. Cuando se usa la palabra clave `MustOverride`, la definición del método consta únicamente de la instrucción `Sub`, `Function` o `Property`. No se permiten otras instrucciones y, en concreto, no hay ninguna instrucción `End Sub` o `End Function`. `MustOverride` métodos deben declararse en clases `MustInherit`.

Supongamos que desea definir clases para controlar la nómina. Puede definir una clase `Payroll` genérica que contenga un método `RunPayroll` que calcule la nómina para una semana típica. Después, podría utilizar `Payroll` como una clase base para una clase `BonusPayroll` más especializada, que podría usarse al distribuir las primas de los empleados.

La clase `BonusPayroll` puede heredar, e invalidar, el método `PayEmployee` definido en la clase base `Payroll`.

En el ejemplo siguiente se define una clase base, `Payroll,` y una clase derivada, `BonusPayroll`, que invalida un método heredado, `PayEmployee`. Un procedimiento, `RunPayroll`, crea y, a continuación, pasa un objeto `Payroll` y un objeto `BonusPayroll` a una función, `Pay`, que ejecuta el método `PayEmployee` de ambos objetos.

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a>La palabra clave MyBase

La palabra clave `MyBase` se comporta como una variable de objeto que hace referencia a la clase base de la instancia actual de una clase. `MyBase` se usa con frecuencia para tener acceso a los miembros de clase base que se invalidan o se sombrean en una clase derivada. En concreto, `MyBase.New` se usa para llamar explícitamente a un constructor de clase base desde un constructor de clase derivada.

Por ejemplo, supongamos que está diseñando una clase derivada que reemplaza un método heredado de la clase base. El método invalidado puede llamar al método de la clase base y modificar el valor devuelto como se muestra en el siguiente fragmento de código:

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

En la lista siguiente se describen las restricciones en el uso de `MyBase`:

- `MyBase` hace referencia a la clase base inmediata y a sus miembros heredados. No se puede usar para tener acceso a `Private` miembros en la clase.

- `MyBase` es una palabra clave, no un objeto real. `MyBase` no se puede asignar a una variable, se puede pasar a procedimientos o usarse en una comparación de `Is`.

- No es necesario definir el método que `MyBase` califica en la clase base inmediata; en su lugar, se puede definir en una clase base heredada indirectamente. Para que una referencia calificada por `MyBase` se compile correctamente, alguna clase base debe contener un método que coincida con el nombre y los tipos de parámetros que aparecen en la llamada.

- No se puede usar `MyBase` para llamar a métodos de clase base `MustOverride`.

- no se puede usar `MyBase` para calificarse a sí mismo. Por lo tanto, el código siguiente no es válido:

  `MyBase.MyBase.BtnOK_Click()`

- no se puede usar `MyBase` en módulos.

- no se puede usar `MyBase` para tener acceso a los miembros de clase base marcados como `Friend` si la clase base está en un ensamblado diferente.

Para obtener más información y otro ejemplo, vea [Cómo: obtener acceso a una variable oculta por una clase derivada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).

## <a name="the-myclass-keyword"></a>La palabra clave MyClass

La palabra clave `MyClass` se comporta como una variable de objeto que hace referencia a la instancia actual de una clase como se implementó originalmente. `MyClass` es similar a `Me`, pero todas las llamadas de método y propiedad en `MyClass` se tratan como si el método o la propiedad fueran [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md). Por lo tanto, el método o la propiedad no se ven afectados por el reemplazo en una clase derivada.

- `MyClass` es una palabra clave, no un objeto real. `MyClass` no se puede asignar a una variable, se puede pasar a procedimientos o usarse en una comparación de `Is`.

- `MyClass` hace referencia a la clase contenedora y a sus miembros heredados.

- `MyClass` puede usarse como calificador para `Shared` miembros.

- `MyClass` no se puede usar dentro de un método de `Shared`, pero se puede usar dentro de un método de instancia para tener acceso a un miembro compartido de una clase.

- no se puede usar `MyClass` en módulos estándar.

- `MyClass` puede usarse para calificar un método que se define en una clase base y que no tiene ninguna implementación del método proporcionado en esa clase. Este tipo de referencia tiene el mismo significado que `MyBase.`*método*.

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

Aunque `derivedClass` invalidaciones `testMethod`, la palabra clave `MyClass` en `useMyClass` anula los efectos de la invalidación, y el compilador resuelve la llamada a la versión de la clase base de `testMethod`.

## <a name="see-also"></a>Vea también

- [Inherits (instrucción)](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
