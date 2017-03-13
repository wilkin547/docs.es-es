---
title: "Fundamentos de la herencia (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "clases abstractas, herencia"
  - "clases base, extender propiedades y métodos"
  - "clases base, herencia"
  - "clases [Visual Basic], derivadas"
  - "clases derivadas, herencia"
  - "herencia"
  - "Inherits (instrucción), herencia"
  - "MustInherit (clases)"
  - "MustInherit (palabra clave), utilizar"
  - "MustOverride (palabra clave), utilizar"
  - "MyBase (palabra clave), utilizar"
  - "MyClass (palabra clave), utilizar"
  - "NotInheritable (palabra clave), utilizar"
  - "NotOverridable (palabra clave), utilizar"
  - "Overrides (palabra clave), utilizar"
  - "reemplazar, Overridable (palabra clave)"
  - "reemplazar, Overrides (palabra clave)"
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# Fundamentos de la herencia (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

La instrucción `Inherits` se utiliza para declarar una nueva clase, denominada *clase derivada*, basada en una clase existente conocida como *clase base*.  Las clases derivadas heredan, y pueden extender, las propiedades, métodos, eventos, campos y constantes definidos en la clase base.  En la siguiente sección se describen algunas de las reglas de herencia, así como los modificadores que se pueden utilizar para cambiar la forma en que las clases heredan o son heredadas:  
  
-   De forma predeterminada, todas las clases son heredables a menos que se marquen con la palabra clave `NotInheritable`.  Las clases pueden heredar de otras clases del proyecto o de clases en otros ensamblados a los que hace referencia el proyecto.  
  
-   A diferencia de los lenguajes que permiten la herencia múltiple, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] solamente permite la herencia simple en las clases; es decir, las clases derivadas solo pueden tener una clase base.  Aunque no se permite la herencia múltiple en las clases, éstas pueden implementar múltiples interfaces, lo que permite lograr de manera eficaz los mismos fines.  
  
-   Para evitar la exposición de elementos restringidos en una clase base, el tipo de acceso de una clase derivada debe ser igual o más restrictivo que el de su clase base.  Por ejemplo, una clase `Public` no puede heredar una clase `Friend` o `Private`, y una clase `Friend` no puede heredar una clase `Private`.  
  
## Modificadores de herencia  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] presenta las siguientes instrucciones y modificadores de nivel de clase para ofrecer compatibilidad con la herencia:  
  
-   Instrucción `Inherits`: especifica la clase base.  
  
-   Modificador `NotInheritable`: impide que los programadores utilicen la clase como clase base.  
  
-   Modificador `MustInherit`: especifica que la clase sólo se debe utilizar como clase base.  Las instancias de las clases `MustInherit` no se pueden crear directamente; sólo se pueden crear como instancias de clase base de una clase derivada.  Otros lenguajes de programación, como C\+\+ y C\#, utilizan el término *clase abstracta* para describir tal clase.  
  
## Reemplazar propiedades y métodos en clases derivadas  
 De forma predeterminada, una clase derivada hereda los métodos y propiedades de su clase base.  Si una propiedad o método heredados tienen que comportarse de manera diferente en la clase derivada, se pueden *invalidar*.  Es decir, se puede definir una nueva implementación del método en la clase derivada.  Los siguientes modificadores se utilizan para controlar cómo se reemplazan propiedades y métodos:  
  
-   `Overridable`: permite reemplazar una propiedad o un método de una clase en una clase derivada.  
  
-   `Overrides`: reemplaza una propiedad o un método `Overridable` definido en la clase base.  
  
-   `NotOverridable`: evita que una propiedad o un método se invaliden en una clase que hereda.  De forma predeterminada, los métodos `Public` son `NotOverridable`.  
  
-   `MustOverride`: requiere que una clase derivada reemplace una propiedad o un método.  Cuando se utiliza la palabra clave `MustOverride`, la definición del método está formada simplemente por la instrucción `Sub`, `Function` o `Property`.  No se permite ninguna otra instrucción y, en concreto, no hay ninguna instrucción `End Function` ni `End Sub`.  Los métodos `MustOverride` se deben declarar en las clases `MustInherit`.  
  
 Suponga que desea definir clases para controlar la nómina.  Podría definir una clase genérica `Payroll` que contenga un método `RunPayroll` para calcular la nómina de una semana típica.  Podría utilizar `Payroll` como clase base de una clase más especializada `BonusPayroll` que se utilizaría para distribuir bonificaciones entre los empleados.  
  
 La clase `BonusPayroll` puede heredar y reemplazar al método `PayEmployee` definido en la clase base `Payroll`.  
  
 En el siguiente ejemplo se define una clase base, `Payroll,` y una clase derivada, `BonusPayroll`, que reemplaza a un método heredado, `PayEmployee`.  Un procedimiento, `RunPayroll` crea y luego pasa un objeto `Payroll` y un objeto `BonusPayroll` a una función, `Pay`, que ejecuta el método `PayEmployee` de ambos objetos.  
  
 [!code-vb[VbVbalrOOP#28](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]  
  
## La palabra clave MyBase  
 La palabra clave `MyBase` se comporta como una variable de objeto que hace referencia a la clase base de la instancia actual de una clase.  `MyBase` suele usarse para obtener acceso a los miembros de la clase base que se reemplazan o se sombrean en una clase derivada.  En particular, `MyBase.New` se utiliza para llamar explícitamente a un constructor de una clase base desde un constructor de una clase derivada.  
  
 Por ejemplo, suponga que diseña una clase derivada que reemplaza un método heredado de la clase base.  El método reemplazado puede llamar al método de la clase base y modificar el valor devuelto como se muestra en el fragmento de código siguiente:  
  
 [!code-vb[VbVbalrOOP#109](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]  
  
 En la lista siguiente se describen las restricciones de uso de `MyBase`:  
  
-   `MyBase` hace referencia a la clase base inmediata y a sus miembros heredados.  No se puede utilizar para tener acceso a miembros `Private` de la clase.  
  
-   `MyBase` es una palabra clave; no es un objeto real.  `MyBase` no se puede asignar a una variable, pasar a los procedimientos ni usar en una comparación `Is`.  
  
-   No es necesario definir el método al que califica `MyBase` en la clase base inmediata; puede definirse en una clase base heredada indirectamente.  Para compilar correctamente una referencia calificada con `MyBase`, alguna clase base debe contener un método que se corresponda con el nombre y los tipos de los parámetros que aparecen en la llamada.  
  
-   No puede utilizar `MyBase` para llamar a métodos de clase base con el modificador `MustOverride`.  
  
-   No se puede utilizar `MyBase` para calificarse a sí misma.  Por tanto, el siguiente código no es válido:  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   No se puede utilizar `MyBase` en módulos.  
  
-   No se puede utilizar `MyBase` para tener acceso a miembros de clase base marcados como `Friend` si la clase base está en un ensamblado diferente.  
  
 Para obtener más información y otro ejemplo, vea [Cómo: Obtener acceso a una variable que oculta una clase derivada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
## La palabra clave MyClass  
 La palabra clave `MyClass` se comporta como una variable de objeto que hace referencia a la instancia actual de una clase tal y como se implementó originalmente.  `MyClass` es similar a `Me`, pero todas las llamadas a métodos y propiedades en `MyClass` se tratan como si el método o la propiedad fuesen [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).  Por lo tanto, el método o propiedad no se ve afectado por el reemplazo de una clase derivada.  
  
-   `MyClass` es una palabra clave; no es un objeto real.  `MyClass` no se puede asignar a una variable, pasar a los procedimientos ni usar en una comparación `Is`.  
  
-   `MyClass` hace referencia a la clase base inmediata y a sus miembros heredados.  
  
-   `MyClass` puede utilizarse como calificador de miembros `Shared`.  
  
-   `MyClass` no se puede utilizar dentro de un método `Shared`, pero puede utilizarse en un método de instancia para obtener acceso a un miembro compartido de una clase.  
  
-   `MyClass` no se puede utilizar en módulos estándar.  
  
-   `MyClass` puede utilizarse para calificar un método que está definido en un clase base y que no tiene ninguna implementación del método proporcionado en esa clase.  Este tipo de referencia tiene el mismo significado que `MyBase.`*Método*.  
  
 En el siguiente ejemplo se comparan `Me` y `MyClass`.  
  
```  
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
  
 Aunque `derivedClass` reemplaza a `testMethod`, la palabra clave `MyClass` en `useMyClass` anula el efecto del reemplazo y el compilador resuelve la llamada a la versión de la clase base de `testMethod`.  
  
## Vea también  
 [Inherits \(Instrucción\)](../../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)