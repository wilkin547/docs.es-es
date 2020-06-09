---
title: Objetos y clases
ms.date: 05/26/2020
helpviewer_keywords:
- classes [Visual Basic]
- objects [Visual Basic]
ms.assetid: c68c5752-1006-46e1-975a-6717b62a42fc
ms.openlocfilehash: 9e3cf262ef617a1ae5ee92bcc3d6fd5c691602f9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600417"
---
# <a name="objects-and-classes-in-visual-basic"></a>Objetos y clases de Visual Basic

Un *objeto* es una combinación de código y datos que se pueden tratar como una unidad. Un objeto puede ser una parte de una aplicación, como un control o un formulario. Toda la aplicación también puede ser un objeto.

Cuando se crea una aplicación en Visual Basic, se trabaja constantemente con objetos. Puede usar los objetos proporcionados por Visual Basic, como los controles, los formularios y los objetos de acceso a datos. También puede utilizar objetos de otras aplicaciones dentro de la aplicación Visual Basic. Incluso puede crear sus propios objetos y definir propiedades y métodos adicionales para ellos. Los objetos actúan como bloques de compilación prefabricados que permiten escribir un fragmento de código de una vez y utilizarlo una y otra vez.

En este tema se proporciona información detallada sobre los objetos.

## <a name="objects-and-classes"></a>Objetos y clases

Cada objeto de Visual Basic se define mediante una *clase*. Una clase describe las variables, las propiedades, los procedimientos y los eventos de un objeto. Los objetos son instancias de clases; puede crear tantos objetos como sean necesarios una vez que haya definido una clase.

Para comprender la relación entre un objeto y su clase, piense en las galletas y en su molde. El molde de la galleta es la clase. Define las características de cada galleta, por ejemplo, tamaño y forma. La clase se usa para crear objetos. Los objetos son las galletas.

Debe crear un objeto para poder tener acceso a sus miembros, salvo para [`Shared`](../../../language-reference/modifiers/shared.md) los miembros a los que se puede tener acceso sin un objeto de la clase.

### <a name="create-an-object-from-a-class"></a>Crear un objeto a partir de una clase

1. Determine en qué clase desea crear un objeto o defina su propia clase. Por ejemplo:

   ```vb
   Public Class Customer
       Public Property AccountNumber As Integer
   End Class
   ```

2. Escriba una [instrucción Dim](../../../language-reference/statements/dim-statement.md) para crear una variable a la que pueda asignar una instancia de clase. La variable debe ser del tipo de la clase deseada.

   ```vb
   Dim nextCustomer As Customer
   ```

3. Agregue la palabra clave [Nuevo operador](../../../language-reference/operators/new-operator.md) para inicializar la variable en una nueva instancia de la clase.

   ```vb
   Dim nextCustomer As New Customer
   ```

4. Ahora puede tener acceso a los miembros de la clase a través de la variable de objeto.

   ```vb
   nextCustomer.AccountNumber = lastAccountNumber + 1
   ```

> [!NOTE]
> Siempre que sea posible, debe declarar la variable para que sea del tipo de clase al que pretende asignarla. Esto se denomina *enlace anticipado*. Si no conoce el tipo de clase en tiempo de compilación, puede invocar el *enlace en tiempo de ejecución* mediante la declaración de la variable para que sea del [tipo de datos de objeto](../../../language-reference/data-types/object-data-type.md). Sin embargo, el enlace en tiempo de ejecución puede ralentizar el rendimiento y limitar el acceso a los miembros del objeto de tiempo de ejecución. Para más información, vea [Declaración de variables de objeto](../variables/object-variable-declaration.md).

### <a name="multiple-instances"></a>Varias instancias

Los objetos recién creados a partir de una clase suelen ser idénticos entre sí. Una vez que existen como objetos individuales, sin embargo, sus variables y propiedades se pueden cambiar independientemente de las otras instancias. Por ejemplo, si agrega tres casillas a un formulario, cada objeto de casilla es una instancia de la clase <xref:System.Windows.Forms.CheckBox>. Los objetos <xref:System.Windows.Forms.CheckBox> individuales comparten un conjunto común de características y funciones (propiedades, variables, procedimientos y eventos) que define la clase. Sin embargo, cada uno tiene su propio nombre, pueden habilitarse y deshabilitarse por separado y se pueden colocar en una ubicación distinta en el formulario.

## <a name="object-members"></a>Miembros de objetos

Un objeto es un elemento de una aplicación, que representa una *instancia* de una clase. Los campos, las propiedades, los métodos y los eventos son los bloques de compilación de objetos y constituyen sus *miembros*.

### <a name="member-access"></a>Acceso a miembros

Para acceder al miembro de un objeto, especifique, en este mismo orden, el nombre de la variable de objeto, un punto (`.`) y el nombre del miembro. En el ejemplo siguiente se establece la propiedad <xref:System.Windows.Forms.Control.Text%2A> de un objeto <xref:System.Windows.Forms.Label>.

```vb
warningLabel.Text = "Data not saved"
```

#### <a name="intellisense-listing-of-members"></a>Lista de miembros de IntelliSense

IntelliSense muestra los miembros de una clase cuando invoca su opción Lista de miembros, por ejemplo, al escribir un punto (`.`) como un operador de acceso a miembros. Si escribe el punto después del nombre de una variable declarada como una instancia de esa clase, IntelliSense muestra todos los miembros de instancia y ningún miembro compartido. Si escribe el punto después del nombre de clase, IntelliSense muestra todos los miembros compartidos y ningún miembro de instancia. Para obtener más información, vea [Usar IntelliSense](/visualstudio/ide/using-intellisense).

### <a name="fields-and-properties"></a>Campos y propiedades

Los *campos* y las *propiedades* representan información almacenada en un objeto. Puede recuperar y establecer sus valores con instrucciones de asignación de la misma forma en que se recuperan y establecen las variables locales en un procedimiento. En el ejemplo siguiente se recupera la propiedad <xref:System.Windows.Forms.Control.Width%2A> y se establece la propiedad <xref:System.Windows.Forms.Control.ForeColor%2A> de un objeto <xref:System.Windows.Forms.Label>.

```vb
Dim warningWidth As Integer = warningLabel.Width
warningLabel.ForeColor = System.Drawing.Color.Red
```

Tenga en cuenta que a un campo también se le denomina *variable de miembro*.

Use procedimientos de propiedad cuando:

- Necesite controlar cuándo y cómo se establece o recupera un valor.

- La propiedad tiene un conjunto bien definido de valores que precisan de validación.

- La configuración del valor genera algún cambio perceptible en el estado del objeto, como una propiedad `IsVisible`.

- La configuración de la propiedad provoca cambios en otras variables internas o en los valores de otras propiedades.

- Es necesario realizar una serie de pasos antes de que la propiedad se pueda establecer o recuperar.

Utilice campos cuando:

- El valor sea de un tipo de autovalidación. Por ejemplo, se produce un error o una conversión de datos automática si un valor distinto de `True` o `False` se asigna a una variable `Boolean`.

- Cualquier valor del intervalo admitido por el tipo de datos es válido. Esto mismo sucede con muchas propiedades del tipo `Single` o `Double`.

- La propiedad es un tipo de datos `String`, y no hay ninguna restricción del tamaño o el valor de la cadena.

- Para más información, vea [Procedimientos de propiedad](../procedures/property-procedures.md).

> [!TIP]
> Mantenga siempre los campos no constantes privados. Si desea que sea público, use una propiedad en su lugar.

### <a name="methods"></a>Métodos

Un *método* es una acción que un objeto puede realizar. Por ejemplo, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A> es un método del objeto <xref:System.Windows.Forms.ComboBox> que agrega una entrada nueva al cuadro combinado.

En el ejemplo siguiente se muestra el método <xref:System.Windows.Forms.Timer.Start%2A> de un objeto <xref:System.Windows.Forms.Timer>.

```vb
Dim safetyTimer As New System.Windows.Forms.Timer
safetyTimer.Start()
```

Tenga en cuenta que un método es simplemente un *procedimiento* que se expone mediante un objeto.

Para más información, vea [Procedimientos en Visual Basic](../procedures/index.md).

### <a name="events"></a>Eventos

Un evento es una acción reconocida por un objeto, como hacer clic con el ratón o presionar una tecla, para la que puede escribir código para que responda. Los eventos pueden producirse como resultado de una acción del usuario o código de programa, o puede provocarlos el sistema. Se dice que el código que señala un evento *genera* el evento y el código que responde a él se dice que lo *controla*.

También puede desarrollar sus propios eventos personalizados para que los generen sus objetos y los controlen otros objetos. Para más información, vea [Eventos](../events/index.md).

### <a name="instance-members-and-shared-members"></a>Miembros de instancia y miembros compartidos

Cuando se crea un objeto de una clase, el resultado es una instancia de esa clase. Los miembros no declarados con la palabra clave [Shared](../../../language-reference/modifiers/shared.md) son *miembros de instancia*, que pertenecen estrictamente a esa instancia concreta. Un miembro de instancia en una instancia es independiente del mismo miembro en otra instancia de la misma clase. Por ejemplo, una variable de miembro de instancia puede tener valores diferentes en instancias distintas.

Los miembros declarados con la palabra clave `Shared` son *miembros compartidos*, que pertenecen a la clase como un todo y no a una instancia determinada. Un miembro compartido existe solo una vez, independientemente del número de instancias de su clase, o incluso si no crea ninguna. Una variable de miembro compartido, por ejemplo, tiene un único valor, que está disponible para todo el código que puede tener acceso a la clase.

#### <a name="accessing-non-shared-members"></a>Obtener acceso a miembros no compartidos

1. Asegúrese de que el objeto se crea a partir de su clase y de que se asigna a una variable de objeto.

   ```vb
   Dim secondForm As New System.Windows.Forms.Form
   ```

2. En la instrucción que tiene acceso al miembro, siga el nombre de la variable de objeto con el *operador de acceso a miembro* ( `.` ) y, a continuación, el nombre del miembro.

   ```vb
   secondForm.Show()
   ```

#### <a name="accessing-shared-members"></a>Acceso a miembros compartidos

- Siga el nombre de clase con el *operador de acceso a miembros* ( `.` ) y, a continuación, el nombre del miembro. Siempre debe acceder a un miembro `Shared` del objeto directamente a través del nombre de clase.

   ```vb
   Console.WriteLine("This computer is called " & Environment.MachineName)
   ```

- Si ya ha creado un objeto de la clase, también puede acceder a un miembro `Shared` a través de la variable del objeto.

### <a name="differences-between-classes-and-modules"></a>Diferencias entre clases y módulos

La diferencia principal entre clases y módulos es que pueden crearse instancias de clases como objetos, pero no de los módulos estándar. Como solo hay una copia de los datos de un módulo estándar, cuando una parte del programa cambia una variable pública en un módulo estándar, cualquier otra parte del programa obtiene el mismo valor si lee luego esa variable. En cambio, los datos de objeto existen por separado para cada objeto con instancias. Otra diferencia es que, a diferencia de los módulos estándar, las clases pueden implementar interfaces. Si una clase está marcada con el modificador [MustInherit](../../../language-reference/modifiers/mustinherit.md) , no se pueden crear instancias de ella directamente. Sin embargo, todavía es diferente de un módulo, ya que se puede heredar, mientras que los módulos no se pueden heredar.

> [!NOTE]
> Cuando el modificador `Shared` se aplica a un miembro de clase, se asocia a la propia clase, en lugar de a una instancia particular de una clase. Al miembro se accede directamente con el nombre de clase, de la misma forma que se accede a los miembros del módulo.

Las clases y los módulos también emplean ámbitos diferentes para sus miembros. Los miembros definidos dentro de una clase tienen el ámbito de una instancia específica de la clase y solo durante la vigencia del objeto. Para acceder a miembros de clase desde fuera de una clase, debe utilizar nombres completos con el formato de *Objeto*.*Miembro*.

Por otro lado, los miembros declarados dentro de un módulo son de acceso público de forma predeterminada a través de cualquier código que pueda tener acceso al módulo. Esto significa que las variables de un módulo estándar son variables globales porque son visibles desde cualquier parte del proyecto y, además, existen durante la vigencia del programa.

## <a name="reusing-classes-and-objects"></a>Reutilización de clases y objetos

Los objetos permiten declarar variables y procedimientos una vez, para luego reutilizarlos siempre que sea necesario. Por ejemplo, si desea agregar un corrector ortográfico a una aplicación, podría definir todas las variables y funciones compatibles para proporcionar la funcionalidad de revisión ortográfica. Si crea el corrector ortográfico como una clase, puede reutilizarlo en otras aplicaciones mediante la incorporación de una referencia al ensamblado compilado. Mejor aún, puede ahorrarse trabajo mediante el uso de una clase de corrector ortográfico que otra persona ya ha desarrollado.

.NET proporciona muchos ejemplos de componentes que están disponibles para su uso. En el ejemplo siguiente se usa la clase <xref:System.TimeZone> en el espacio de nombres <xref:System>. <xref:System.TimeZone> proporciona miembros que permiten recuperar información sobre la zona horaria del equipo actual.

```vb
Public Sub ExamineTimeZone()
    Dim tz As System.TimeZone = System.TimeZone.CurrentTimeZone
    Dim s As String = "Current time zone is "
    s &= CStr(tz.GetUtcOffset(Now).Hours) & " hours and "
    s &= CStr(tz.GetUtcOffset(Now).Minutes) & " minutes "
    s &= "different from UTC (coordinated universal time)"
    s &= vbCrLf & "and is currently "
    If tz.IsDaylightSavingTime(Now) = False Then s &= "not "
    s &= "on ""summer time""."
    Console.WriteLine(s)
End Sub
```

En el ejemplo anterior, la primera [instrucción Dim](../../../language-reference/statements/dim-statement.md) declara una variable de objeto del tipo <xref:System.TimeZone> y le asigna un objeto <xref:System.TimeZone> que devuelve la propiedad <xref:System.TimeZone.CurrentTimeZone%2A>.

## <a name="relationships-among-objects"></a>Relaciones entre objetos

Los objetos pueden relacionarse entre sí de varias maneras. Los tipos principales de relación son *jerárquica* y de *contención*.

### <a name="hierarchical-relationship"></a>Relación jerárquica

Cuando las clases se derivan de clases más fundamentales, se dice que tienen una *relación jerárquica*. Las jerarquías de clases son útiles cuando se describen elementos que constituyen un subtipo de una clase más general.

En el ejemplo siguiente, suponga que quiere definir un tipo especial de <xref:System.Windows.Forms.Button> que actúa como un <xref:System.Windows.Forms.Button> normal, pero también expone un método que invierte los colores de primer plano y de fondo.

#### <a name="define-a-class-that-is-derived-from-an-already-existing-class"></a>Definir una clase que se deriva de una clase ya existente

1. Use una [instrucción Class](../../../language-reference/statements/class-statement.md) para definir una clase desde la que crear el objeto que necesita.

   ```vb
   Public Class ReversibleButton
   ```

   Asegúrese de que una instrucción `End Class` sigue a la última línea de código de la clase. De forma predeterminada, el entorno de desarrollo integrado (IDE) genera automáticamente `End Class` al escribir una instrucción `Class`.

2. Siga a la instrucción `Class` inmediatamente con una [instrucción Inherits](../../../language-reference/statements/inherits-statement.md). Especifique la clase de la que deriva la nueva clase.

   ```vb
   Inherits System.Windows.Forms.Button
   ```

   La nueva clase hereda todos los miembros definidos por la clase base.

3. Agregue el código para los miembros adicionales que la clase derivada expone. Por ejemplo, puede agregar un método `ReverseColors` y la clase derivada podría tener el aspecto siguiente:

   ```vb
   Public Class ReversibleButton
       Inherits System.Windows.Forms.Button
           Public Sub ReverseColors()
               Dim saveColor As System.Drawing.Color = Me.BackColor
               Me.BackColor = Me.ForeColor
               Me.ForeColor = saveColor
          End Sub
   End Class
   ```

   Si crea un objeto a partir de la `ReversibleButton` clase, puede tener acceso a todos los miembros de la <xref:System.Windows.Forms.Button> clase, así como al método y a todos los `ReverseColors` miembros nuevos que defina en `ReversibleButton` .

Las clases derivadas heredan miembros de la clase en que se basan, lo que permite agregar complejidad a medida que progresa en una jerarquía de clases. Para más información, vea [Fundamentos de la herencia](inheritance-basics.md).

### <a name="compile-the-code"></a>Compilar el código

Asegúrese de que el compilador puede tener acceso a la clase de la que pretende derivar la nueva clase. Esto puede conllevar su nombre completo, como en el ejemplo anterior, o la identificación de su espacio de nombres en una [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md). Si la clase está en un proyecto diferente, tendrá que agregar una referencia a ese proyecto. Para más información, vea [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project).

### <a name="containment-relationship"></a>Relaciones de contención

Otra forma de relacionar ese objeto es mediante una *relación de contención*. Los objetos contenedores lógicamente encapsulan otros objetos. Por ejemplo, el objeto <xref:System.OperatingSystem> contiene lógicamente un objeto <xref:System.Version>, el cual devuelve a través de su propiedad <xref:System.OperatingSystem.Version%2A>. Tenga en cuenta que el objeto contenedor no contiene ningún otro objeto físicamente.

#### <a name="collections"></a>Colecciones

Un tipo concreto de contención de objeto se representa mediante *colecciones*. Las colecciones son grupos de objetos similares que se pueden enumerar. Visual Basic admite una sintaxis específica en la [... Instrucción siguiente](../../../language-reference/statements/for-each-next-statement.md) que permite recorrer en iteración los elementos de una colección. Además, las colecciones suelen permitir usar un <xref:Microsoft.VisualBasic.Collection.Item%2A> para recuperar elementos en función de su índice o asociándolos con una cadena única. Las colecciones pueden ser más fáciles de utilizar que las matrices puesto que permiten agregar o quitar elementos sin utilizar índices. Debido a su facilidad de uso, las colecciones se utilizan a menudo para almacenar formularios y controles.

## <a name="related-topics"></a>Temas relacionados

[Tutorial: definir clases](walkthrough-defining-classes.md)\
Proporciona una descripción detallada sobre cómo crear una clase.

[Propiedades y métodos sobrecargados](overloaded-properties-and-methods.md)\
Propiedades y métodos sobrecargados

[Fundamentos de la herencia](inheritance-basics.md)\
Se tratan los modificadores de herencia, con la sustitución de métodos y propiedades, MyClass y MyBase.

[Duración de los objetos: cómo se crean y destruyen](object-lifetime-how-objects-are-created-and-destroyed.md)\
Describe cómo crear y eliminar instancias de clase.

[Tipos anónimos](anonymous-types.md)\
Describe cómo crear y usar tipos anónimos que permiten crear objetos sin escribir una definición de clase para el tipo de datos.

[Inicializadores de objeto: tipos con nombre y anónimos](object-initializers-named-and-anonymous-types.md)\
Explica los inicializadores de objeto, que se usan para crear instancias de tipos con nombre y anónimos mediante una sola expresión.

[Cómo: deducir tipos y nombres de propiedades en declaraciones de tipos anónimos](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)\
Explica cómo deducir tipos y nombres de propiedades en declaraciones de tipos anónimos. Proporciona ejemplos de inferencia correcta e incorrecta.
