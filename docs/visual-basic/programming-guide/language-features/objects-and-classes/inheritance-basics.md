---
title: Fundamentos de la herencia (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- derived classes, inheritance
- MyClass keyword, using
- MyBase keyword, using
- Inherits statement, inheritance
- overriding, Overridable keyword
- MustInherit keyword, using
- Overrides keyword, using
- inheritance
- MustInherit classes
- MustOverride keyword, using
- classes [Visual Basic], derived
- NotInheritable keyword, using
- base classes, extending properties and methods
- NotOverridable keyword, using
- base classes, inheritance
- abstract classes, inheritance
- overriding, Overrides keyword
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 58aee9f8c348eb06daec2b8c9e332f3f2775bcb6
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="inheritance-basics-visual-basic"></a>Fundamentos de la herencia (Visual Basic)
El `Inherits` instrucción se utiliza para declarar una nueva clase, denominada una *clase derivada*, en función de una clase existente, conocida como un *clase base*. Las clases derivadas heredan y pueden extender, las propiedades, métodos, eventos, campos y constantes definidas en la clase base. La siguiente sección describe algunas de las reglas para la herencia y los modificadores que puede utilizar para cambiar las clases de manera heredan o son heredados:  
  
-   De forma predeterminada, todas las clases son heredables a menos que se marca con el `NotInheritable` (palabra clave). Las clases pueden heredar de otras clases en el proyecto o de clases en otros ensamblados a los que hace referencia a su proyecto.  
  
-   A diferencia de los lenguajes que permiten herencia múltiple, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] permite herencia única sólo en las clases; es decir, las clases derivadas pueden tener sólo una clase base. Aunque no se permite la herencia múltiple en las clases, las clases pueden implementar varias interfaces, que se pueden lograr de manera eficaz los mismos fines.  
  
-   Para evitar la exposición de elementos restringidos en una clase base, el tipo de acceso de una clase derivada debe ser igual o más restrictivo que su clase base. Por ejemplo, un `Public` clase no puede heredar una `Friend` o un `Private` (clase) y un `Friend` clase no puede heredar una `Private` clase.  
  
## <a name="inheritance-modifiers"></a>Modificadores de herencia  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]presenta las siguientes instrucciones de nivel de clase y modificadores para admitir la herencia:  
  
-   `Inherits`instrucción: especifica la clase base.  
  
-   `NotInheritable`modificador: evita que los programadores utilicen la clase como una clase base.  
  
-   `MustInherit`modificador: Especifica que la clase está diseñada para su uso como clase base. Instancias de `MustInherit` clases no se pueden crear directamente; sólo se pueden crear instancias de clase como base de una clase derivada. (Otros lenguajes de programación, como C++ y C#, utilizan el término *clase abstracta* para describir tal clase.)  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a>Reemplazar propiedades y métodos en clases derivadas  
 De forma predeterminada, una clase derivada hereda las propiedades y métodos de su clase base. Si una propiedad o método heredado debe comportarse de forma diferente en la clase derivada puede ser *se reemplaza*. Es decir, puede definir una nueva implementación del método en la clase derivada. Los siguientes modificadores se utilizan para controlar cómo se reemplazan propiedades y métodos:  
  
-   `Overridable`Permite un método o propiedad en una clase para invalidarse en una clase derivada.  
  
-   `Overrides`: Reemplaza una `Overridable` propiedad o método definido en la clase base.  
  
-   `NotOverridable`: Impide que una propiedad o método se invalide en una clase heredera. De forma predeterminada, `Public` métodos son `NotOverridable`.  
  
-   `MustOverride`: Requiere que una clase derivada reemplace la propiedad o método. Cuando el `MustOverride` se utiliza la palabra clave, la definición del método consta de solamente el `Sub`, `Function`, o `Property` instrucción. Se permite ninguna otra instrucción y, específicamente no hay ningún `End Sub` o `End Function` instrucción. `MustOverride`métodos deben declararse en `MustInherit` clases.  
  
 Suponga que desea definir clases para controlar la nómina. Puede definir un tipo genérico `Payroll` clase que contiene un `RunPayroll` método calcular la nómina de una semana típica. Se podría utilizar `Payroll` como una clase base para más especializadas `BonusPayroll` clase, que se utilizaría para distribuir bonificaciones del empleado.  
  
 El `BonusPayroll` clase puede heredar y reemplazar, el `PayEmployee` método definido en la base de `Payroll` clase.  
  
 En el ejemplo siguiente se define una clase base, `Payroll,` y una clase derivada, `BonusPayroll`, que reemplaza un método heredado, `PayEmployee`. Un procedimiento, `RunPayroll`, crea y, a continuación, se pasa un `Payroll` objeto y un `BonusPayroll` objeto a una función, `Pay`, que se ejecuta el `PayEmployee` método de ambos objetos.  
  
 [!code-vb[VbVbalrOOP&#28;](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]  
  
## <a name="the-mybase-keyword"></a>La palabra clave MyBase  
 El `MyBase` (palabra clave) se comporta como una variable de objeto que hace referencia a la clase base de la instancia actual de una clase. `MyBase`se suele utilizar para tener acceso a miembros de clase base que se reemplazan o se sombrean en una clase derivada. En particular, `MyBase.New` se utiliza para llamar explícitamente a un constructor de clase base desde un constructor de clase derivada.  
  
 Por ejemplo, suponga que está diseñando una clase derivada que reemplaza un método heredado de la clase base. El método reemplazado puede llamar al método en la clase base y modificar el valor devuelto como se muestra en el siguiente fragmento de código:  
  
 [!code-vb[VbVbalrOOP&#109;](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]  
  
 La siguiente lista describe las restricciones sobre el uso de `MyBase`:  
  
-   `MyBase`hace referencia a la clase base inmediata y a sus miembros heredados. No se puede utilizar para tener acceso a `Private` miembros de la clase.  
  
-   `MyBase`es una palabra clave, no un objeto real. `MyBase`no se asigna a una variable, pasar a procedimientos ni utilizar en una `Is` comparación.  
  
-   El método que `MyBase` se consideran no tienen que definirse en la clase base inmediata; en su lugar puede definirse en una clase base heredada indirectamente. En una referencia calificada por `MyBase` para compilar correctamente, alguna clase base debe contener un método correspondiente al nombre y tipos de parámetros que aparecen en la llamada.  
  
-   No puede usar `MyBase` para llamar a `MustOverride` métodos de la clase de base.  
  
-   `MyBase`no se puede usar para calificar a sí mismo. Por lo tanto, el código siguiente no es válido:  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   `MyBase`no se puede utilizar en módulos.  
  
-   `MyBase`no se puede utilizar para tener acceso a miembros de clase base que están marcados como `Friend` si la clase base está en un ensamblado diferente.  
  
 Para obtener más información y otro ejemplo, vea [Cómo: obtener acceso a una Variable oculta una clase derivada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
## <a name="the-myclass-keyword"></a>La palabra clave MyClass  
 El `MyClass` (palabra clave) se comporta como una variable de objeto que hace referencia a la instancia actual de una clase se implementó originalmente. `MyClass`es similar a `Me`, pero llama cada método y propiedad en `MyClass` se trata como si el método o propiedad fuesen [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md). Por lo tanto, el método o propiedad no se ve afectado por el reemplazo de una clase derivada.  
  
-   `MyClass`es una palabra clave, no un objeto real. `MyClass`no se asigna a una variable, pasar a procedimientos ni utilizar en una `Is` comparación.  
  
-   `MyClass`hace referencia a la clase contenedora y sus miembros heredados.  
  
-   `MyClass`se puede utilizar como calificador para `Shared` miembros.  
  
-   `MyClass`no se puede utilizar dentro de un `Shared` (método), pero se puede utilizar dentro de un método de instancia para tener acceso a un miembro compartido de una clase.  
  
-   `MyClass`no se puede utilizar en módulos estándar.  
  
-   `MyClass`puede utilizarse para calificar un método que se define en una clase base y que no tiene ninguna implementación del método proporcionado en esa clase. Este tipo de referencia tiene el mismo significado que `MyBase.` *método*.  
  
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
  
 Aunque `derivedClass` reemplaza `testMethod`, `MyClass` palabra clave en `useMyClass` anula el efecto del reemplazo y el compilador se resuelve la llamada a la versión de la clase base `testMethod`.  
  
## <a name="see-also"></a>Vea también  
 [Inherits (instrucción)](../../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)

