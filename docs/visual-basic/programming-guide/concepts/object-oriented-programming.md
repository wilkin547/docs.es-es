---
description: 'Más información sobre: programación orientada a objetos (Visual Basic)'
title: Programación orientada a objetos
ms.date: 07/20/2015
ms.assetid: 49794de4-64c3-473c-b8ed-fe98835df69c
ms.openlocfilehash: af2fbac16bfefc90876bf22bb8c67de162ee6459
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100486802"
---
# <a name="object-oriented-programming-visual-basic"></a>Programación orientada a objetos (Visual Basic)

Visual Basic proporciona compatibilidad total con la programación orientada a objetos, incluidos la encapsulación, la herencia y el polimorfismo.

 La *encapsulación* significa que un grupo de propiedades, métodos y otros miembros relacionados se tratan como una sola unidad u objeto.

 La *herencia* describe la posibilidad de crear nuevas clases basadas en una clase existente.

 El *polimorfismo* significa que puede tener múltiples clases que se pueden usar de manera intercambiable, aunque cada clase implementa las mismas propiedades o los mismos métodos de maneras diferentes.

 En esta sección se describen los conceptos siguientes:

- [Clases y objetos](#classes-and-objects)
  - [Miembros de clase](#class-members)
    - [Propiedades y campos](#properties-and-fields)
    - [Métodos](#methods)
    - [Constructores](#constructors)
    - [Destructores](#destructors)
    - [Eventos](#events)
    - [Clases anidadas](#nested-classes)
  - [Modificadores y niveles de acceso](#access-modifiers-and-access-levels)
    - [Creación de instancias de clases](#instantiating-classes)
    - [Clases y miembros compartidos](#shared-classes-and-members)
    - [Tipos anónimos (Guía de programación de C#)](#anonymous-types).
- [Herencia](#inheritance)
  - [Reemplazar miembros](#overriding-members)
- [Interfaces](#interfaces)
- [Genéricos](#generics)
- [Delegados](#delegates)

## <a name="classes-and-objects"></a>Clases y objetos

Los términos *clase* y *objeto* se usan a veces indistintamente pero, en realidad, las clases describen el *tipo* de los objetos, mientras que los objetos son *instancias* de clases que se pueden usar. Así, la acción de crear un objeto se denomina *creación de instancias*. Con la analogía de plano, una clase es un plano y un objeto es un edificio construido a partir de ese plano.

Para definir una clase:

```vb
Class SampleClass
End Class
```

Visual Basic también proporciona una versión ligera de las clases denominadas *estructuras* que son útiles cuando es necesario crear una matriz grande de objetos y no se desea consumir demasiada memoria para ello.

Para definir una estructura:

```vb
Structure SampleStructure
End Structure
```

Para obtener más información, consulte:

- [Instrucción Class](../../language-reference/statements/class-statement.md)
- [Structure (Instrucción)](../../language-reference/statements/structure-statement.md)

### <a name="class-members"></a>Miembros de la clase

Cada clase puede tener distintos *miembros de clase*, entre los que se incluyen las propiedades que describen los datos de clase, los métodos que definen el comportamiento de la clase y los eventos que proporcionan comunicación entre distintos objetos y clases.

#### <a name="properties-and-fields"></a>Propiedades y campos

Los campos y propiedades representan información que contiene un objeto. Los campos se parecen a las variables ya que se pueden leer y establecer directamente.

Para definir un campo:

```vb
Class SampleClass
    Public SampleField As String
End Class
```

Las propiedades tienen procedimientos get y set, que proporcionan un mayor control sobre la forma en que se establecen o devuelven los valores.

Visual Basic permite crear un campo privado para almacenar el valor de propiedad, o bien usar las denominadas propiedades implementadas automáticamente que crean este campo automáticamente en segundo plano y proporcionan la lógica básica para los procedimientos de propiedad.

Para definir una propiedad implementada automáticamente:

```vb
Class SampleClass
    Public Property SampleProperty as String
End Class
```

Si necesita realizar algunas operaciones adicionales para leer y escribir el valor de propiedad, defina un campo para almacenar el valor de propiedad y proporcione la lógica básica para almacenarlo y recuperar lo:

```vb
Class SampleClass
    Private m_Sample As String
    Public Property Sample() As String
        Get
            ' Return the value stored in the field.
            Return m_Sample
        End Get
        Set(ByVal Value As String)
            ' Store the value in the field.
            m_Sample = Value
        End Set
    End Property
End Class
```

La mayoría de las propiedades tienen métodos o procedimientos tanto para establecer como para obtener el valor de propiedad. Sin embargo, se pueden crear propiedades de solo lectura o solo escritura para restringir su modificación o lectura. En Visual Basic se pueden usar las palabras clave `ReadOnly` y `WriteOnly`. En cambio, las propiedades implementadas automáticamente no pueden ser de solo lectura o de solo escritura.

Para obtener más información, vea:

- [Property Statement](../../language-reference/statements/property-statement.md)
- [Get (Instrucción)](../../language-reference/statements/get-statement.md)
- [Set (instrucción)](../../language-reference/statements/set-statement.md)
- [ReadOnly](../../language-reference/modifiers/readonly.md)
- [WriteOnly](../../language-reference/modifiers/writeonly.md)

#### <a name="methods"></a>Métodos

 Un *método* es una acción que un objeto puede realizar.

> [!NOTE]
> En Visual Basic hay dos formas de crear un método: se usa la instrucción `Sub` si el método no devuelve un valor o bien se usa la instrucción `Function` si el método devuelve un valor.

Para definir un método de una clase:

```vb
Class SampleClass
    Public Function SampleFunc(ByVal SampleParam As String)
        ' Add code here
    End Function
End Class
```

Una clase puede tener varias implementaciones o *sobrecargas* del mismo método que se diferencian en el número de parámetros o de tipos de parámetro.

Para sobrecargar un método:

```vb
Overloads Sub Display(ByVal theChar As Char)
    ' Add code that displays Char data.
End Sub
Overloads Sub Display(ByVal theInteger As Integer)
    ' Add code that displays Integer data.
End Sub
```

En la mayoría de los casos, un método se declara dentro de una definición de clase. Sin embargo, Visual Basic también admite *métodos de extensión* que permiten agregar métodos a una clase existente fuera de la definición real de la clase.

Para obtener más información, vea:

- [Instrucción Function](../../language-reference/statements/function-statement.md)
- [Instrucción Sub](../../language-reference/statements/sub-statement.md)
- [Sobrecargas](../../language-reference/modifiers/overloads.md)
- [Métodos de extensión](../language-features/procedures/extension-methods.md)

#### <a name="constructors"></a>Constructores

Los constructores son métodos de clase que se ejecutan automáticamente cuando se crea un objeto de un tipo determinado. Normalmente, los constructores inicializan los miembros de datos del nuevo objeto. Un constructor solo puede ejecutarse una vez cuando se crea una clase. Además, el código del constructor siempre se ejecuta antes que cualquier otro código en una clase. Sin embargo, puede crear varias sobrecargas del constructor de la misma forma que para cualquier otro método.

Para definir un constructor para una clase:

```vb
Class SampleClass
    Sub New(ByVal s As String)
        // Add code here.
    End Sub
End Class
```

Para obtener más información, vea: [duración del objeto: cómo se crean y destruyen los objetos](../language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).

#### <a name="destructors"></a>Destructores

Los destructores se utilizan para destruir instancias de clases. En .NET Framework, el recolector de elementos no utilizados administra automáticamente la asignación y la liberación de memoria para los objetos administrados en la aplicación. Sin embargo, es posible que aún se necesiten destructores para limpiar cualquiera de los recursos no administrados creados por la aplicación. Solo puede haber un destructor para una clase.

Para obtener más información sobre los destructores y la recolección de elementos no utilizados en .NET Framework, vea [Garbage Collection](../../../standard/garbage-collection/index.md) (Recolección de elementos no utilizados).

#### <a name="events"></a>Events

Cuando ocurre algo interesante, los eventos habilitan una clase u objeto para notificarlo a otras clases u objetos. La clase que envía (o genera) el evento recibe el nombre de *publicador* y las clases que reciben (o controlan) el evento se denominan *suscriptores*. Para obtener más información sobre los eventos y la forma en que se generan y controlan, vea [Eventos](../../../standard/events/index.md).

- Para declarar eventos, use la [instrucción de evento](../../language-reference/statements/event-statement.md).

- Para generar eventos, use la [instrucción RaiseEvent](../../language-reference/statements/raiseevent-statement.md).

- Para especificar los controladores de eventos de forma declarativa, use la instrucción [WithEvents](../../language-reference/modifiers/withevents.md) y la cláusula [Handles](../../language-reference/statements/handles-clause.md) .

- Para poder agregar, quitar y cambiar de forma dinámica el controlador de eventos asociado a un evento, utilice la [instrucción AddHandler](../../language-reference/statements/addhandler-statement.md) y la [instrucción RemoveHandler](../../language-reference/statements/removehandler-statement.md) junto con el [operador AddressOf](../../language-reference/operators/addressof-operator.md).

#### <a name="nested-classes"></a>Clases anidadas

Una clase definida dentro de otra se denomina *anidada*. De forma predeterminada, una clase anidada es privada.

```vb
Class Container
    Class Nested
    ' Add code here.
    End Class
End Class
```

Para crear una instancia de la clase anidada, use el nombre de la clase contenedora seguido de un punto y seguido, a continuación, del nombre de la clase anidada:

```vb
Dim nestedInstance As Container.Nested = New Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a>Modificadores y niveles de acceso

Todas las clases y miembros de clase pueden especificar el nivel de acceso que proporcionan a otras clases mediante los *modificadores de acceso*.

Están disponibles los siguientes modificadores de acceso:

|Modificador de Visual Basic|Definición|
|---------------------------|----------------|
|[Público](../../language-reference/modifiers/public.md)|Puede obtener acceso al tipo o miembro cualquier otro código del mismo ensamblado o de otro ensamblado que haga referencia a éste.|
|[Privado](../../language-reference/modifiers/private.md)|Solamente puede obtener acceso al tipo o miembro el código de la misma clase.|
|[Contra](../../language-reference/modifiers/protected.md)|Solamente puede obtener acceso al tipo o miembro el código de la misma clase o de una clase derivada.|
|[Friend](../../language-reference/modifiers/friend.md)|Puede obtener acceso al tipo o miembro cualquier código del mismo ensamblado, pero no de un ensamblado distinto.|
|`Protected Friend`|Puede obtener acceso al tipo o miembro cualquier código del mismo ensamblado o cualquier clase derivada de otro ensamblado.|

Para obtener más información, consulte [niveles de acceso en Visual Basic](../language-features/declared-elements/access-levels.md).

### <a name="instantiating-classes"></a>Creación de instancias de clases

Para crear un objeto, debe crear una o varias instancias de una clase.

```vb
Dim sampleObject as New SampleClass()
```

Una vez creadas las instancias de una clase, puede asignar valores a las propiedades y los campos de la instancia, así como invocar métodos de clase.

```vb
' Set a property value.
sampleObject.SampleProperty = "Sample String"
' Call a method.
sampleObject.SampleMethod()
```

Para asignar valores a las propiedades durante el proceso de creación de instancias de una clase, use los inicializadores de objeto:

```vb
Dim sampleObject = New SampleClass With
    {.FirstProperty = "A", .SecondProperty = "B"}
```

Para obtener más información, consulte:

- [New Operator (Nuevo operador)](../../language-reference/operators/new-operator.md)
- [Inicializadores de objeto: tipos con nombre y anónimos](../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)

### <a name="shared-classes-and-members"></a>Clases y miembros compartidos

 Un miembro compartido de la clase es una propiedad, un procedimiento o un campo que comparten todas las instancias de una clase.

 Para definir un miembro compartido:

```vb
Class SampleClass
    Public Shared SampleString As String = "Sample String"
End Class
```

 Para tener acceso al miembro compartido, use el nombre de la clase sin crear un objeto de esta clase:

```vb
MsgBox(SampleClass.SampleString)
```

 Los módulos compartidos de Visual Basic solo tienen miembros compartidos y no se pueden crear instancias de ellos. Los miembros compartidos tampoco pueden tener acceso a propiedades, campos o métodos no compartidos

 Para obtener más información, vea:

- [Compartido](../../language-reference/modifiers/shared.md)
- [Module (Instrucción)](../../language-reference/statements/module-statement.md)

### <a name="anonymous-types"></a>Tipos anónimos

Los tipos anónimos permiten crear objetos sin escribir una definición de clase para el tipo de datos. En su lugar, el compilador genera una clase. La clase no tiene ningún nombre que se pueda usar y contiene las propiedades especificadas al declarar el objeto.

Para crear una instancia de un tipo anónimo:

```vb
' sampleObject is an instance of a simple anonymous type.
Dim sampleObject =
    New With {Key .FirstProperty = "A", .SecondProperty = "B"}
```

Para obtener más información, consulte: [Tipos anónimos](../language-features/objects-and-classes/anonymous-types.md).

## <a name="inheritance"></a>Herencia

La herencia permite crear una nueva clase que reutiliza, extiende y modifica el comportamiento que se define en otra clase. La clase cuyos miembros se heredan se denomina *clase base* y la clase que hereda esos miembros se denomina *clase derivada*. Sin embargo, todas las clases de Visual Basic heredan implícitamente de la <xref:System.Object> clase que admite la jerarquía de clases .net y proporciona servicios de bajo nivel a todas las clases.

> [!NOTE]
> Visual Basic no admite la herencia múltiple. Es decir, solo puede especificar una clase base para una clase derivada.

Para heredar de una clase base:

```vb
Class DerivedClass
    Inherits BaseClass
End Class
```

De forma predeterminada, todas las clases se pueden heredar. Sin embargo, puede especificar si una clase no se debe usar como clase base o bien crear una clase que solo se pueda usar como clase base.

Para especificar que una clase no se puede usar como clase base:

```vb
NotInheritable Class SampleClass
End Class
```

Para especificar que una clase se puede usar solo como clase base y no se pueden crear instancias de esta:

```vb
MustInherit Class BaseClass
End Class
```

Para obtener más información, consulte:

- [Inherits Statement](../../language-reference/statements/inherits-statement.md)
- [NotInheritable](../../language-reference/modifiers/notinheritable.md)
- [MustInherit](../../language-reference/modifiers/mustinherit.md)

### <a name="overriding-members"></a>Reemplazar miembros

De forma predeterminada, una clase derivada hereda todos los miembros de su clase base. Si desea cambiar el comportamiento del miembro heredado, debe invalidarlo. Es decir, se puede definir una nueva implementación del método, la propiedad o el evento en la clase derivada.

Los siguientes modificadores se utilizan para controlar cómo se reemplazan propiedades y métodos:

|Modificador de Visual Basic|Definición|
|---------------------------|----------------|
|[Overridable](../../language-reference/modifiers/overridable.md)|Permite invalidar un miembro de una clase derivada.|
|[Invalidaciones](../../language-reference/modifiers/overrides.md)|Invalida un miembro virtual (invalidable) definido en la clase base.|
|[NotOverridable](../../language-reference/modifiers/notoverridable.md)|Impide que un miembro se invalide en una clase heredera.|
|[MustOverride](../../language-reference/modifiers/mustoverride.md)|Requiere que se invalide un miembro de clase en la clase derivada.|
|[Shadows](../../language-reference/modifiers/shadows.md)|Oculta un miembro heredado de una clase base.|

## <a name="interfaces"></a>Interfaces

Las interfaces, como las clases, definen un conjunto de propiedades, métodos y eventos. Pero de forma contraria a las clases, las interfaces no proporcionan implementación. Se implementan como clases y se definen como entidades separadas de las clases. Una interfaz representa un contrato, en el cual una clase que implementa una interfaz debe implementar cualquier aspecto de dicha interfaz exactamente como esté definido.

Para definir una interfaz:

```vb
Public Interface ISampleInterface
    Sub DoSomething()
End Interface
```

Para implementar una interfaz en una clase:

```vb
Class SampleClass
    Implements ISampleInterface
    Sub DoSomething
        ' Method implementation.
    End Sub
End Class
```

Para obtener más información, vea:

- [Interfaces](../language-features/interfaces/index.md)
- [Instrucción Interface](../../language-reference/statements/interface-statement.md)
- [Implements (Instrucción)](../../language-reference/statements/implements-statement.md)

## <a name="generics"></a>Genéricos

Las clases, las estructuras, las interfaces y los métodos de .NET pueden incluir *parámetros de tipo* que definen los tipos de objetos que pueden almacenar o usar. El ejemplo más común de elementos genéricos es una colección, donde se puede especificar el tipo de objetos que se va a almacenar en una colección.

Para definir una clase genérica:

```vb
Class SampleGeneric(Of T)
    Public Field As T
End Class
```

Para crear una instancia de una clase genérica:

```vb
Dim sampleObject As New SampleGeneric(Of String)
sampleObject.Field = "Sample string"
```

Para obtener más información, consulte:

- [Genéricos](../../../standard/generics/index.md)
- [Tipos genéricos en Visual Basic](../language-features/data-types/generic-types.md)

## <a name="delegates"></a>Delegados

 Un *delegado* es un tipo que define una firma de método y que puede proporcionar una referencia a cualquier método con una firma compatible. Puede invocar (o llamar) al método a través del delegado. Los delegados se utilizan para pasar métodos como argumentos a otros métodos.

> [!NOTE]
> Los controladores de eventos no son más que métodos que se invocan a través de delegados. Para obtener más información sobre el uso de delegados en el control de eventos, vea [Eventos](../../../standard/events/index.md).

Para crear un delegado:

```vb
Delegate Sub SampleDelegate(ByVal str As String)
```

Para crear una referencia a un método que coincida con la firma especificada por el delegado:

```vb
Class SampleClass
    ' Method that matches the SampleDelegate signature.
    Sub SampleSub(ByVal str As String)
        ' Add code here.
    End Sub
    ' Method that instantiates the delegate.
    Sub SampleDelegateSub()
        Dim sd As SampleDelegate = AddressOf SampleSub
        sd("Sample string")
    End Sub
End Class
```

Para obtener más información, vea:

- [Delegados](../language-features/delegates/index.md)
- [Delegate (Instrucción)](../../language-reference/statements/delegate-statement.md)
- [Operador AddressOf](../../language-reference/operators/addressof-operator.md)

## <a name="see-also"></a>Consulte también

- [Guía de programación en Visual Basic](../index.md)
