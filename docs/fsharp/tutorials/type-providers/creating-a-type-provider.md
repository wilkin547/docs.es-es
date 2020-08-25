---
title: 'Tutorial: Creación de un proveedor de tipos'
description: 'Obtenga información sobre cómo crear sus propios proveedores de tipos de F # en F # 3,0 examinando varios proveedores de tipos simples para ilustrar los conceptos básicos.'
ms.date: 11/04/2019
ms.openlocfilehash: 71225614ed983a76d35c214faa87bbad0fbb7d24
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88810877"
---
# <a name="tutorial-create-a-type-provider"></a>Tutorial: Creación de un proveedor de tipos

El mecanismo de proveedores de tipos de F # es una parte importante de su compatibilidad con la programación enriquecida de información. Este tutorial le explica cómo crear proveedores de tipos, a la vez que le guía en el desarrollo de varios proveedores de tipo simples para ilustrar los conceptos básicos. Para obtener más información sobre el mecanismo de proveedores de tipos en F #, vea [proveedores de tipos](index.md).

El ecosistema de F # contiene una variedad de proveedores de tipo para los servicios de datos empresariales y de Internet que se usan habitualmente. Por ejemplo:

- [FSharp. Data](https://fsharp.github.io/FSharp.Data/) incluye proveedores de tipos para los formatos de documento JSON, XML, csv y HTML.

- [SQLProvider](https://fsprojects.github.io/SQLProvider/) proporciona acceso fuertemente tipado a las bases de datos SQL a través de una asignación de objetos y consultas LINQ de F # en estos orígenes de datos.

- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) tiene un conjunto de proveedores de tipos para la inserción comprobada en tiempo de compilación de T-SQL en F#.

- [FSharp. Data. TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) es un conjunto anterior de proveedores de tipo para su uso solo con .NET Framework programación para tener acceso a los servicios de datos SQL, Entity Framework, ODATA y WSDL.

En caso necesario, se pueden crear proveedores de tipos personalizados o se puede hacer referencia a proveedores de tipos creados por otros. Por ejemplo, una organización podría tener un servicio de datos que proporcionara un número elevado y creciente de conjuntos de datos con nombre, cada uno con su propio esquema de datos estable. Se puede crear un proveedor de tipos que lea los esquemas y presente los conjuntos de datos actuales al programador de una manera fuertemente tipada.

## <a name="before-you-start"></a>Antes de empezar

El mecanismo de proveedores de tipo está diseñado principalmente para insertar espacios de información de servicios y datos estables en la experiencia de programación de F#.

Este mecanismo no está diseñado para insertar espacios de información cuyo esquema cambie durante la ejecución del programa de forma relevante para la lógica del programa. El mecanismo tampoco está diseñado para la metaprogramación dentro del lenguaje, aunque ese dominio contenga algunas aplicaciones válidas. Debe utilizar este mecanismo solo en caso necesario y cuando el desarrollo de un proveedor de tipos produzca un valor muy alto.

Debe evitar escribir un proveedor de tipos cuando no hay un esquema disponible. Igualmente, debe evitar escribir un proveedor de tipo cuando una biblioteca de .NET normal (o incluso una existente) sería suficiente.

Antes de comenzar, debería hacerse las siguientes preguntas:

- ¿Tiene un esquema para su fuente de información? Si lo tiene, ¿cuál es la correspondencia entre los sistemas de tipos de F# y .NET?

- ¿Puede utilizar una API existente (dinámicamente tipada) como punto de partida para su implementación?

- ¿Usarán usted y su organización el proveedor de tipos lo suficiente como para hacer que valga la pena escribirlo? ¿Cubriría una biblioteca normal de .NET sus necesidades?

- ¿Cuánto cambiará el esquema?

- ¿Cambiará durante la escritura del código?

- ¿Cambiará entre las sesiones de escritura de código?

- ¿Cambiará durante la ejecución del programa?

Los proveedores de tipos son más adecuados en situaciones en las que el esquema es estable en runtime y durante el tiempo de vida del código compilado.

## <a name="a-simple-type-provider"></a>Un proveedor de tipos simple

Este ejemplo es samples. HelloWorldTypeProvider, similar a los ejemplos del `examples` directorio del [SDK del proveedor de tipos de F #](https://github.com/fsprojects/FSharp.TypeProviders.SDK/). El proveedor hace que esté disponible un "espacio de tipos" que contiene 100 tipos borrados, como muestra el código siguiente, en el que se usa la sintaxis de signatura de F# y se omiten los detalles de todos los tipos excepto `Type1`. Para obtener más información sobre los tipos borrados, consulte [detalles sobre los tipos de borrados proporcionados](#details-about-erased-provided-types) más adelante en este tema.

```fsharp
namespace Samples.HelloWorldTypeProvider

type Type1 =
    /// This is a static property.
    static member StaticProperty : string

    /// This constructor takes no arguments.
    new : unit -> Type1

    /// This constructor takes one argument.
    new : data:string -> Type1

    /// This is an instance property.
    member InstanceProperty : int

    /// This is an instance method.
    member InstanceMethod : x:int -> char

    nested type NestedType =
        /// This is StaticProperty1 on NestedType.
        static member StaticProperty1 : string
        …
        /// This is StaticProperty100 on NestedType.
        static member StaticProperty100 : string

type Type2 =
…
…

type Type100 =
…
```

Observe que el conjunto de tipos y miembros proporcionados se conoce de forma estática. Este ejemplo no aprovecha la capacidad de los proveedores para proporcionar tipos que dependen de un esquema. La implementación del proveedor de tipo se muestra en el código siguiente y sus detalles se tratan en secciones posteriores de este tema.

> [!WARNING]
> Puede haber diferencias entre este código y los ejemplos en línea.

```fsharp
namespace Samples.FSharp.HelloWorldTypeProvider

open System
open System.Reflection
open ProviderImplementation.ProvidedTypes
open FSharp.Core.CompilerServices
open FSharp.Quotations

// This type defines the type provider. When compiled to a DLL, it can be added
// as a reference to an F# command-line compilation, script, or project.
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =

  // Inheriting from this type provides implementations of ITypeProvider
  // in terms of the provided types below.
  inherit TypeProviderForNamespaces(config)

  let namespaceName = "Samples.HelloWorldTypeProvider"
  let thisAssembly = Assembly.GetExecutingAssembly()

  // Make one provided type, called TypeN.
  let makeOneProvidedType (n:int) =
  …
  // Now generate 100 types
  let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]

  // And add them to the namespace
  do this.AddNamespace(namespaceName, types)

[<assembly:TypeProviderAssembly>]
do()
```

Para usar este proveedor, abra una instancia independiente de Visual Studio, cree un script de F # y, a continuación, agregue una referencia al proveedor desde el script mediante #r como se muestra en el código siguiente:

```fsharp
#r @".\bin\Debug\Samples.HelloWorldTypeProvider.dll"

let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")

let obj2 = Samples.HelloWorldTypeProvider.Type1("some other data")

obj1.InstanceProperty
obj2.InstanceProperty

[ for index in 0 .. obj1.InstanceProperty-1 -> obj1.InstanceMethod(index) ]
[ for index in 0 .. obj2.InstanceProperty-1 -> obj2.InstanceMethod(index) ]

let data1 = Samples.HelloWorldTypeProvider.Type1.NestedType.StaticProperty35
```

A continuación, busque los tipos en el espacio de nombres `Samples.HelloWorldTypeProvider` generado por el proveedor de tipos.

Antes de volver a compilar el proveedor, asegúrese de que se han cerrado todas las instancias de Visual Studio y de F# Interactive que están utilizando la DLL del proveedor. De lo contrario, aparecerá un error de compilación porque la DLL de salida estará bloqueada.

Para depurar este proveedor mediante instrucciones de impresión, cree un script que exponga un problema con el proveedor y, a continuación, utilice el código siguiente:

```console
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

Para depurar este proveedor mediante Visual Studio, abra el Símbolo del sistema para desarrolladores de Visual Studio con credenciales administrativas y ejecute el siguiente comando:

```console
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

Como alternativa, abra Visual Studio, abra el menú Depurar, elija `Debug/Attach to process…` y asocie a otro `devenv` proceso en el que esté editando el script. Con este método, le resultará más fácil centrarse en la lógica particular del proveedor de tipo escribiendo interactivamente expresiones en la segunda instancia (con IntelliSense completo y otras características).

Puede deshabilitar la depuración "Solo mi código" para identificar mejor los errores en el código generado. Para obtener información sobre cómo habilitar o deshabilitar esta característica, vea [navegar por el código con el depurador](/visualstudio/debugger/navigating-through-code-with-the-debugger). Además, también puede establecer la detección de excepciones de primera oportunidad abriendo el `Debug` menú y, a continuación, eligiendo `Exceptions` las teclas Ctrl + Alt + E para abrir el `Exceptions` cuadro de diálogo. En ese cuadro de diálogo, en `Common Language Runtime Exceptions` , active la `Thrown` casilla.

### <a name="implementation-of-the-type-provider"></a>Implementación del proveedor de tipos

En esta sección se muestran las etapas principales de la implementación del proveedor de tipos. En primer lugar, defina el tipo del proveedor de tipos personalizado:

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

Este tipo debe ser público y debe marcarse con el atributo [TypeProvider](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-compilerservices-typeproviderattribute.html) para que el compilador reconozca el proveedor de tipos cuando un proyecto independiente de F # haga referencia al ensamblado que contiene el tipo. El parámetro de *configuración* es opcional y, si está presente, contiene información de configuración contextual para la instancia del proveedor de tipo que crea el compilador de F #.

A continuación, implemente la interfaz [ITypeProvider](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-compilerservices-itypeprovider.html) . En este caso, puede utilizar el tipo `TypeProviderForNamespaces` de la API `ProvidedTypes` como tipo base. Este tipo del asistente puede proporcionar una colección finita de espacios de nombres proporcionados anticipadamente, cada uno de los cuales contiene directamente un número finito de tipos fijos proporcionados anticipadamente. En este contexto, el proveedor genera *diligentemente* tipos incluso si no son necesarios o se usan.

```fsharp
inherit TypeProviderForNamespaces(config)
```

A continuación, defina los valores privados locales que especifican el espacio de nombres para los tipos proporcionados y busque el ensamblado propio del proveedor de tipos. Este ensamblado se utiliza más adelante como tipo primario lógico de los tipos borrados proporcionados.

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

A continuación, cree una función para proporcionar cada uno de los tipos Type1… Type100. Esta función se explica con más detalle más adelante en este tema.

```fsharp
let makeOneProvidedType (n:int) = …
```

A continuación, genere los 100 tipos proporcionados:

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

Después, agregue los tipos como un espacio de nombres proporcionado:

```fsharp
do this.AddNamespace(namespaceName, types)
```

Finalmente, agregue un atributo de ensamblado que indique que está creando una DLL de proveedor de tipos:

```fsharp
[<assembly:TypeProviderAssembly>]
do()
```

### <a name="providing-one-type-and-its-members"></a>Proporcionar un tipo y sus miembros

La función `makeOneProvidedType` hace el trabajo real de proporcionar uno de los tipos.

```fsharp
let makeOneProvidedType (n:int) =
…
```

En este paso se explica la implementación de esta función. En primer lugar, cree el tipo proporcionado (por ejemplo, Type1, cuando n = 1, o Type57, cuando n = 57).

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code,
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

Debe tener en cuenta los puntos siguientes:

- Este tipo proporcionado es un tipo borrado.  Dado que indica que el tipo base es `obj` , las instancias aparecerán como valores de tipo [obj](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-obj.html) en código compilado.

- Cuando especifique un tipo no anidado, deberá especificar también el ensamblado y el espacio de nombres. Para los tipos borrados, el ensamblado deberá ser el propio ensamblado del proveedor de tipos.

A continuación, agregue la documentación XML al tipo. Esta documentación se demora, es decir, se calcula a petición si el compilador host la necesita.

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

A continuación, agregue una propiedad estática proporcionada al tipo:

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty",
                                  propertyType = typeof<string>,
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

Al obtener esta propiedad, siempre se evaluará como la cadena "Hello!". La función `GetterCode` de la propiedad utiliza una expresión de código delimitada de F# que representa el código que genera el compilador host para obtener la propiedad. Para obtener más información sobre las comillas, vea [expresiones de código delimitadas (F #)](../../language-reference/code-quotations.md).

Agregue la documentación XML a la propiedad.

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

Ahora asocie la propiedad proporcionada al tipo proporcionado. Debe asociar un miembro proporcionado a un único tipo. De lo contrario, el miembro nunca será accesible.

```fsharp
t.AddMember staticProp
```

Ahora cree un constructor proporcionado que no reciba ningún parámetro.

```fsharp
let ctor = ProvidedConstructor(parameters = [ ],
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

La función `InvokeCode` del constructor devuelve una expresión de código delimitada de F# que representa el código que el compilador host genera cuando se llama al constructor. Por ejemplo, puede usar el constructor siguiente:

```fsharp
new Type10()
```

Se creará una instancia del tipo proporcionado con los datos subyacentes "The object data". El código entre comillas incluye una conversión a [obj](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-obj.html) porque ese tipo es el borrado de este tipo proporcionado (como se especificó al declarar el tipo proporcionado).

Agregue la documentación XML al constructor y agregue el constructor proporcionado al tipo proporcionado:

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

Cree un segundo constructor proporcionado que tome un parámetro:

```fsharp
let ctor2 =
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ],
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

La función `InvokeCode` del constructor devuelve de nuevo una expresión de código delimitada de F# que representa el código que el compilador host generó para una llamada al método. Por ejemplo, puede usar el constructor siguiente:

```fsharp
new Type10("ten")
```

Se crea una instancia del tipo proporcionado con los datos subyacentes "ten". Es posible que haya notado que la función `InvokeCode` devuelve una expresión de código delimitada. La entrada de esta función es una lista de expresiones, una por cada parámetro del constructor. En este caso, una expresión que representa el valor del único parámetro está disponible en `args.[0]`. El código de una llamada al constructor convierte el valor devuelto en el tipo borrado `obj`. Después de agregar el segundo constructor proporcionado al tipo, cree una propiedad de instancia proporcionada:

```fsharp
let instanceProp =
    ProvidedProperty(propertyName = "InstanceProperty",
                     propertyType = typeof<int>,
                     getterCode= (fun args ->
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

Al obtener esta propiedad, se devuelve la longitud de la cadena, que es el objeto de representación. La propiedad `GetterCode` devuelve una expresión de código delimitada de F# que especifica el código que genera el compilador host para obtener la propiedad. Al igual que la función `InvokeCode`, la función `GetterCode` devuelve una expresión de código delimitada. El compilador host llama a esta función con una lista de argumentos. En este caso, los argumentos incluyen solo la expresión única que representa la instancia en la que se llama al captador, a la que se puede tener acceso mediante `args.[0]` . La implementación de `GetterCode` después se inserta en el presupuesto de resultados en el tipo borrado `obj` y se usa una conversión para satisfacer el mecanismo del compilador para comprobar los tipos que el objeto es una cadena. La parte siguiente de `makeOneProvidedType` proporciona un método de instancia con un parámetro.

```fsharp
let instanceMeth =
    ProvidedMethod(methodName = "InstanceMethod",
                   parameters = [ProvidedParameter("x",typeof<int>)],
                   returnType = typeof<char>,
                   invokeCode = (fun args ->
                       <@@ ((%%(args.[0]) : obj) :?> string).Chars(%%(args.[1]) : int) @@>))

instanceMeth.AddXmlDocDelayed(fun () -> "This is an instance method")
// Add the instance method to the type.
t.AddMember instanceMeth
```

Finalmente, cree un tipo anidado que contenga 100 propiedades anidadas. La creación de este tipo anidado y sus propiedades se demora, es decir, se calcula a petición.

```fsharp
t.AddMembersDelayed(fun () ->
  let nestedType = ProvidedTypeDefinition("NestedType", Some typeof<obj>)

  nestedType.AddMembersDelayed (fun () ->
    let staticPropsInNestedType =
      [
          for i in 1 .. 100 ->
              let valueOfTheProperty = "I am string "  + string i

              let p =
                ProvidedProperty(propertyName = "StaticProperty" + string i,
                  propertyType = typeof<string>,
                  isStatic = true,
                  getterCode= (fun args -> <@@ valueOfTheProperty @@>))

              p.AddXmlDocDelayed(fun () ->
                  sprintf "This is StaticProperty%d on NestedType" i)

              p
      ]

    staticPropsInNestedType)

  [nestedType])
```

### <a name="details-about-erased-provided-types"></a>Detalles sobre los tipos proporcionados borrados

En el ejemplo de esta sección se proporcionan solo *tipos proporcionados borrados*, que son especialmente útiles en las situaciones siguientes:

- Cuando se escribe un proveedor para un espacio de información que solo contiene datos y métodos.

- Cuando se escribe un proveedor en el que la semántica precisa de tipos en tiempo de ejecución no es fundamental para el uso práctico del espacio de información.

- Cuando se escribe un proveedor para un espacio de información que es tan grande y está tan interconectado que no es técnicamente factible generar tipos reales de .NET para el espacio de información.

En este ejemplo, se borra cada tipo proporcionado para el tipo `obj` y todos los usos del tipo aparecen como tipo `obj` en el código compilado. De hecho, los objetos subyacentes de estos ejemplos son cadenas, pero el tipo aparecerá como `System.Object` en el código compilado de .NET. Como con todos los usos del borrado de tipos, se puede utilizar la conversión boxing explícita, la conversión unboxing y la conversión para trastocar los tipos borrados. En este caso, puede producirse una excepción de conversión no válida cuando se utiliza el objeto. Un runtime de un proveedor puede definir su propio tipo de representación privado para ayudar a protegerse contra representaciones falsas. No se pueden definir tipos borrados en F#. Solo se pueden borrar los tipos proporcionados. Se deben entender las implicaciones, tanto prácticas como semánticas, de utilizar los tipos borrados para el proveedor de tipo o un proveedor que proporcione tipos borrados. Un tipo borrado no tiene un tipo real de .NET. Por consiguiente, no se puede hacer una reflexión precisa sobre el tipo y se podrían trastocar los tipos borrados si se utilizan conversiones en tiempo de ejecución y otras técnicas que dependen de semánticas exactas de tipos en tiempo de ejecución. El trastocamiento de tipos borrados frecuentemente da lugar a excepciones de conversión de tipos en tiempo de ejecución.

### <a name="choosing-representations-for-erased-provided-types"></a>Elegir representaciones para los tipos proporcionados borrados

Para algunos usos de los tipos proporcionados borrados, no se requiere ninguna representación. Por ejemplo, el tipo proporcionado borrado podría contener únicamente propiedades y miembros estáticos y ningún constructor, por lo que ningún método ni propiedad devolvería ninguna instancia del tipo. Si puede tener acceso a instancias de un tipo proporcionado borrado, considere las preguntas siguientes:

**¿Qué es el borrado de un tipo proporcionado?**

- El borrado de un tipo proporcionado es el modo en que el tipo aparece en el código compilado de .NET.

- El borrado de una clase de un tipo proporcionado borrado siempre es el primer tipo base no borrado de la cadena de herencia del tipo.

- El borrado de una interfaz de un tipo de borrado proporcionado es siempre `System.Object`.

**¿Qué son las representaciones de un tipo proporcionado?**

- Se denomina representaciones al conjunto de objetos posibles para un tipo proporcionado borrado. En el ejemplo de este documento, las representaciones de todos los tipos proporcionados borrados `Type1..Type100` son siempre objetos de cadena.

Todas las representaciones de un tipo proporcionado deben ser compatibles con el borrado del tipo proporcionado. (De lo contrario, el compilador de F# generará un error para un uso del proveedor de tipos o se generará código no comprobable de .NET que no es válido. Un proveedor de tipos no es válido si devuelve código que proporciona una representación no válida).

Se puede elegir una representación para los objetos proporcionados mediante uno de los dos métodos siguientes, los cuales son muy comunes:

- Si lo que se hace es simplemente proporcionar un contenedor fuertemente tipado sobre un tipo existente de .NET, tiene sentido que el tipo borre ese tipo, use instancias de ese tipo como representaciones, o ambas cosas. Este enfoque es adecuado cuando la mayoría de los métodos existentes en ese tipo tienen sentido al usar la versión fuertemente tipada.

- Si lo que se desea es crear una API que difiera significativamente de cualquier API existente de .NET, tiene sentido crear tipos en tiempo de ejecución que constituyan la representación y el borrado de tipos para los tipos proporcionados.

El ejemplo de este documento utiliza cadenas como representaciones de los objetos proporcionados. Con frecuencia, puede ser adecuado utilizar otros objetos para las representaciones. Por ejemplo, se puede utilizar un diccionario como contenedor de propiedades:

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

También se puede definir un tipo en el proveedor de tipos que se usará en runtime para formar la representación, junto con una o más operaciones en runtime:

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

Entonces los miembros proporcionados podrán construir instancias de este tipo de objeto:

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

En este caso, se puede (opcionalmente) utilizar este tipo como borrado de tipos especificando este tipo como `baseType` al construir `ProvidedTypeDefinition`:

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a>Lecciones principales

En la sección anterior se explicó cómo crear un proveedor de tipos de borrado simple que proporciona una serie de tipos, propiedades y métodos. En dicha sección se explicó también el concepto de borrado de tipos, incluidas algunas de las ventajas y desventajas de proporcionar tipos borrados desde un proveedor de tipos, y se explicaron las representaciones de los tipos borrados.

## <a name="a-type-provider-that-uses-static-parameters"></a>Un proveedor de tipos que usa parámetros estáticos

La capacidad de parametrizar los proveedores de tipo mediante datos estáticos permite muchos escenarios interesantes, incluso en los casos en que el proveedor no necesita tener acceso a ningún dato local o remoto. En esta sección, aprenderá algunas técnicas básicas para construir tales proveedores.

### <a name="type-checked-regex-provider"></a>Proveedor de tipo de comprobación de expresiones regulares

Imagine que desea implementar un proveedor de tipos para expresiones regulares que contenga las bibliotecas <xref:System.Text.RegularExpressions.Regex> de .NET en una interfaz que proporcione las siguientes garantías en tiempo de compilación:

- Comprobar si una expresión regular es válida.

- Proporcionar propiedades con nombre en las coincidencias basadas en cualquier nombre de grupo de la expresión regular.

En esta sección se muestra cómo utilizar los proveedores de tipo para crear un tipo `RegexTyped` parametrizado por el patrón de expresiones regulares para proporcionar estas ventajas. El compilador notificará un error si el patrón proporcionado no es válido y el proveedor de tipos puede extraer los grupos del patrón de modo que se pueda tener acceso a ellos mediante propiedades con nombre en las coincidencias. Cuando se diseña un proveedor de tipo, se debería considerar el aspecto que debería presentar su API expuesta para los usuarios finales y cómo se traducirá este diseño a código de .NET. El ejemplo siguiente muestra cómo usar una API como esta para obtener los componentes del código de área de un número de teléfono:

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

El ejemplo siguiente muestra cómo convierte el proveedor de tipos estas llamadas:

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

Tenga en cuenta los puntos siguientes:

- El tipo estándar Regex representa el tipo parametrizado `RegexTyped`.

- El constructor `RegexTyped` produce una llamada al constructor Regex y le pasa el argumento de tipo estático para el patrón.

- Los resultados del método `Match` se representan mediante el tipo estándar <xref:System.Text.RegularExpressions.Match>.

- Cada grupo con nombre produce una propiedad proporcionada, y el acceso a la propiedad produce el uso de un indizador en la colección `Groups` de una coincidencia.

El código siguiente es la base de la lógica para implementar un proveedor como este y este ejemplo omite la adición de todos los miembros al tipo proporcionado. Para obtener información sobre cada miembro agregado, consulte la sección correspondiente más adelante en este tema. Para obtener el código completo, descargue el ejemplo del [paquete de ejemplo de F # 3,0](https://archive.codeplex.com/?p=fsharp3sample) en el sitio web de codeplex.

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams,
        instantiationFunction=(fun typeName parameterValues ->

          match parameterValues with
          | [| :? string as pattern|] ->

            // Create an instance of the regular expression.
            //
            // This will fail with System.ArgumentException if the regular expression is not valid.
            // The exception will escape the type provider and be reported in client code.
            let r = System.Text.RegularExpressions.Regex(pattern)

            // Declare the typed regex provided type.
            // The type erasure of this type is 'obj', even though the representation will always be a Regex
            // This, combined with hiding the object methods, makes the IntelliSense experience simpler.
            let ty =
              ProvidedTypeDefinition(
                thisAssembly,
                rootNamespace,
                typeName,
                baseType = Some baseTy)

            ...

            ty
          | _ -> failwith "unexpected parameter values"))

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

Tenga en cuenta los puntos siguientes:

- El proveedor de tipos toma dos parámetros estáticos: `pattern`, el patrón, que es obligatorio, y `options`, las opciones, que son opcionales (porque se proporciona un valor predeterminado).

- Después de proporcionar los argumentos estáticos, se crea una instancia de la expresión regular. Esta instancia inicia una excepción si la Regex no es correcta, y se notifica el error a los usuarios.

- El tipo que se devolverá cuando se den los argumentos se define dentro de la devolución de llamada `DefineStaticParameters`.

- Este código establece `HideObjectMethods` en true para que el uso de IntelliSense siga estando optimizado. Este atributo hace que los miembros `Equals`, `GetHashCode`, `Finalize` y `GetType` se supriman de listas de IntelliSense para un objeto proporcionado.

- Se utiliza `obj` como tipo base del método, pero se utilizará un objeto `Regex` como representación en tiempo de ejecución de este tipo, como muestra el ejemplo siguiente.

- La llamada al constructor `Regex` inicia una excepción <xref:System.ArgumentException> cuando una expresión regular no es válida. El compilador detecta esta excepción y envía un mensaje de error al usuario en tiempo de compilación o en el editor de Visual Studio. Esta excepción permite que las expresiones regulares se validen sin ejecutar una aplicación.

El tipo definido anteriormente todavía no es útil porque no contiene propiedades ni métodos significativos. En primer lugar, agregue un método `IsMatch` estático:

```fsharp
let isMatch =
    ProvidedMethod(
        methodName = "IsMatch",
        parameters = [ProvidedParameter("input", typeof<string>)],
        returnType = typeof<bool>,
        isStatic = true,
        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>)

isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string."
ty.AddMember isMatch
```

El código anterior define un método `IsMatch`, que toma una cadena como entrada y devuelve un valor `bool`. La única parte difícil es el uso del argumento `args` dentro de la definición de la función `InvokeCode`. En este ejemplo, `args` es una lista de expresiones de código delimitadas que representa los argumentos de este método. Si el método es un método de instancia, el primer argumento representa el argumento `this`. Sin embargo, para un método estático, los argumentos son simplemente los argumentos explícitos para el método. Observe que el tipo del valor de la expresión de código delimitada debe coincidir con el tipo del valor devuelto especificado (en este caso, `bool`). Observe también que este código utiliza el método `AddXmlDoc` para asegurarse de que el método proporcionado también tiene documentación útil, que se puede proporcionar con IntelliSense.

A continuación, agregue un método de instancia Match. Sin embargo, este método debe devolver un valor de un tipo `Match` proporcionado, de modo que se pueda tener acceso a los grupos de manera fuertemente tipada. Por ello, primero se declara el tipo `Match`. Como este tipo depende del patrón que se proporcionó como argumento estático, este tipo debe estar anidado dentro de la definición de tipos parametrizados:

```fsharp
let matchTy =
    ProvidedTypeDefinition(
        "MatchType",
        baseType = Some baseTy,
        hideObjectMethods = true)

ty.AddMember matchTy
```

A continuación, se agrega una propiedad al tipo Match de cada grupo. En tiempo de ejecución, una coincidencia se representa como un valor <xref:System.Text.RegularExpressions.Match>, por lo que la expresión de código delimitada que define la propiedad debe utilizar la propiedad indizada <xref:System.Text.RegularExpressions.Match.Groups> para obtener el grupo pertinente.

```fsharp
for group in r.GetGroupNames() do
    // Ignore the group named 0, which represents all input.
    if group <> "0" then
    let prop =
      ProvidedProperty(
        propertyName = group,
        propertyType = typeof<Group>,
        getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
    matchTy.AddMember prop
```

Una vez más, observe que se está agregando la documentación XML a la propiedad proporcionada. También observe que una propiedad puede leerse si se proporciona una función `GetterCode` y puede escribirse si se proporciona una función `SetterCode`, por lo que la propiedad resultante es de solo lectura.

Now you can create an instance method that returns a value of this `Match` type:

```fsharp
let matchMethod =
    ProvidedMethod(
        methodName = "Match",
        parameters = [ProvidedParameter("input", typeof<string>)],
        returnType = matchTy,
        invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)

matchMeth.AddXmlDoc "Searches the specified input string for the first occurrence of this regular expression"

ty.AddMember matchMeth
```

Como está creando un método de instancia, `args.[0]` representa la instancia de `RegexTyped` en la que se está llamando al método y `args.[1]` es el argumento de entrada.

Finalmente, proporcione un constructor para que se puedan crear instancias del tipo proporcionado.

```fsharp
let ctor =
    ProvidedConstructor(
        parameters = [],
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

El constructor simplemente borra para la creación de una Regex estándar de .NET, a la cual también se le aplica la conversión box en un objeto porque `obj` es el borrado del tipo proporcionado. Con ese cambio, el uso de la API de ejemplo especificada previamente en el tema funciona como se esperaba. A continuación se muestra la versión final del código completo:

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types.
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams,
        instantiationFunction=(fun typeName parameterValues ->

            match parameterValues with
            | [| :? string as pattern|] ->

                // Create an instance of the regular expression.

                let r = System.Text.RegularExpressions.Regex(pattern)

                // Declare the typed regex provided type.

                let ty =
                    ProvidedTypeDefinition(
                        thisAssembly,
                        rootNamespace,
                        typeName,
                        baseType = Some baseTy)

                ty.AddXmlDoc "A strongly typed interface to the regular expression '%s'"

                // Provide strongly typed version of Regex.IsMatch static method.
                let isMatch =
                    ProvidedMethod(
                        methodName = "IsMatch",
                        parameters = [ProvidedParameter("input", typeof<string>)],
                        returnType = typeof<bool>,
                        isStatic = true,
                        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>)

                isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string"

                ty.AddMember isMatch

                // Provided type for matches
                // Again, erase to obj even though the representation will always be a Match
                let matchTy =
                    ProvidedTypeDefinition(
                        "MatchType",
                        baseType = Some baseTy,
                        hideObjectMethods = true)

                // Nest the match type within parameterized Regex type.
                ty.AddMember matchTy

                // Add group properties to match type
                for group in r.GetGroupNames() do
                    // Ignore the group named 0, which represents all input.
                    if group <> "0" then
                        let prop =
                          ProvidedProperty(
                            propertyName = group,
                            propertyType = typeof<Group>,
                            getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
                        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
                        matchTy.AddMember(prop)

                // Provide strongly typed version of Regex.Match instance method.
                let matchMeth =
                  ProvidedMethod(
                    methodName = "Match",
                    parameters = [ProvidedParameter("input", typeof<string>)],
                    returnType = matchTy,
                    invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)
                matchMeth.AddXmlDoc "Searches the specified input string for the first occurrence of this regular expression"

                ty.AddMember matchMeth

                // Declare a constructor.
                let ctor =
                  ProvidedConstructor(
                    parameters = [],
                    invokeCode = fun args -> <@@ Regex(pattern) :> obj @@>)

                // Add documentation to the constructor.
                ctor.AddXmlDoc "Initializes a regular expression instance"

                ty.AddMember ctor

                ty
            | _ -> failwith "unexpected parameter values"))

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

### <a name="key-lessons"></a>Lecciones principales

En esta sección se ha explicado cómo crear un proveedor de tipos que opera con sus parámetros estáticos. El proveedor comprueba el parámetro estático y proporciona operaciones basadas en su valor.

## <a name="a-type-provider-that-is-backed-by-local-data"></a>Un proveedor de tipos que está respaldado por datos locales

Con frecuencia se requiere que los proveedores de tipos muestren API basadas no solo en parámetros estáticos sino también en información procedente de sistemas locales o remotos. Esta sección trata sobre los proveedores de tipos basados en datos locales, como los archivos de datos locales.

### <a name="simple-csv-file-provider"></a>Proveedor simple de archivos CSV

Como ejemplo sencillo, considere un proveedor de tipo para tener acceso a datos científicos con el formato de valores separados por comas (CSV). En esta sección se supone que los archivos CSV contienen una fila de encabezado seguida de datos en coma flotante, como se muestra en la tabla siguiente:

|Distancia (metros)|Tiempo (segundos)|
|----------------|-------------|
|50,0|3.7|
|100.0|5.2|
|150.0|6.4|

En esta sección se muestra cómo proporcionar un tipo que se puede usar para obtener filas con una propiedad `Distance` de tipo `float<meter>` y una propiedad `Time` de tipo `float<second>`. Para simplificar, se realizan las suposiciones siguientes:

- Los nombres de encabezado son de unidad menos o tienen el formato "nombre (unidad)" y no contienen comas.

- Las unidades son unidades internacionales (SI) del sistema, ya que el módulo [FSharp. Data. UnitSystems. Si. UnitNames (F #)](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-data-unitsystems-si-unitnames.html) define.

- Las unidades son todas simples (por ejemplo, metro) en lugar de compuestas (por ejemplo, metros por segundo).

- Todas las columnas contienen datos en coma flotante.

Un proveedor más completo relajaría estas restricciones.

De nuevo, el primer paso es considerar qué aspecto debe tener la API. Dado un archivo `info.csv` con el contenido de la tabla anterior (en formato separado por comas), los usuarios del proveedor deberían poder escribir un código similar al del ejemplo siguiente:

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

En este caso, el compilador debería convertir estas llamadas en algo similar al ejemplo siguiente:

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

La conversión óptima requerirá que el proveedor de tipos defina un tipo `CsvFile` real en el ensamblado del proveedor de tipos. Los proveedores de tipos a veces se basan en algunos tipos y métodos del asistente para contener la lógica importante. Dado que las medidas se borran en tiempo de ejecución, se puede utilizar `float[]` como el tipo borrado para una fila. El compilador considerará que las distintas columnas contienen distintos tipos de medidas. Por ejemplo, la primera columna de nuestro ejemplo contiene el tipo `float<meter>` y la segunda contiene `float<second>`. Sin embargo, la representación borrada puede seguir siendo bastante simple.

En el ejemplo de código siguiente se muestra el núcleo de la implementación.

```fsharp
// Simple type wrapping CSV data
type CsvFile(filename) =
    // Cache the sequence of all data lines (all lines but the first)
    let data =
        seq {
            for line in File.ReadAllLines(filename) |> Seq.skip 1 ->
                line.Split(',') |> Array.map float
        }
        |> Seq.cache
    member _.Data = data

[<TypeProvider>]
type public MiniCsvProvider(cfg:TypeProviderConfig) as this =
    inherit TypeProviderForNamespaces(cfg)

    // Get the assembly and namespace used to house the provided types.
    let asm = System.Reflection.Assembly.GetExecutingAssembly()
    let ns = "Samples.FSharp.MiniCsvProvider"

    // Create the main provided type.
    let csvTy = ProvidedTypeDefinition(asm, ns, "MiniCsv", Some(typeof<obj>))

    // Parameterize the type by the file to use as a template.
    let filename = ProvidedStaticParameter("filename", typeof<string>)
    do csvTy.DefineStaticParameters([filename], fun tyName [| :? string as filename |] ->

        // Resolve the filename relative to the resolution folder.
        let resolvedFilename = Path.Combine(cfg.ResolutionFolder, filename)

        // Get the first line from the file.
        let headerLine = File.ReadLines(resolvedFilename) |> Seq.head

        // Define a provided type for each row, erasing to a float[].
        let rowTy = ProvidedTypeDefinition("Row", Some(typeof<float[]>))

        // Extract header names from the file, splitting on commas.
        // use Regex matching to get the position in the row at which the field occurs
        let headers = Regex.Matches(headerLine, "[^,]+")

        // Add one property per CSV field.
        for i in 0 .. headers.Count - 1 do
            let headerText = headers.[i].Value

            // Try to decompose this header into a name and unit.
            let fieldName, fieldTy =
                let m = Regex.Match(headerText, @"(?<field>.+) \((?<unit>.+)\)")
                if m.Success then

                    let unitName = m.Groups.["unit"].Value
                    let units = ProvidedMeasureBuilder.Default.SI unitName
                    m.Groups.["field"].Value, ProvidedMeasureBuilder.Default.AnnotateType(typeof<float>,[units])

                else
                    // no units, just treat it as a normal float
                    headerText, typeof<float>

            let prop =
                ProvidedProperty(fieldName, fieldTy,
                    getterCode = fun [row] -> <@@ (%%row:float[]).[i] @@>)

            // Add metadata that defines the property's location in the referenced file.
            prop.AddDefinitionLocation(1, headers.[i].Index + 1, filename)
            rowTy.AddMember(prop)

        // Define the provided type, erasing to CsvFile.
        let ty = ProvidedTypeDefinition(asm, ns, tyName, Some(typeof<CsvFile>))

        // Add a parameterless constructor that loads the file that was used to define the schema.
        let ctor0 =
            ProvidedConstructor([],
                invokeCode = fun [] -> <@@ CsvFile(resolvedFilename) @@>)
        ty.AddMember ctor0

        // Add a constructor that takes the file name to load.
        let ctor1 = ProvidedConstructor([ProvidedParameter("filename", typeof<string>)],
            invokeCode = fun [filename] -> <@@ CsvFile(%%filename) @@>)
        ty.AddMember ctor1

        // Add a more strongly typed Data property, which uses the existing property at runtime.
        let prop =
            ProvidedProperty("Data", typedefof<seq<_>>.MakeGenericType(rowTy),
                getterCode = fun [csvFile] -> <@@ (%%csvFile:CsvFile).Data @@>)
        ty.AddMember prop

        // Add the row type as a nested type.
        ty.AddMember rowTy
        ty)

    // Add the type to the namespace.
    do this.AddNamespace(ns, [csvTy])
```

Tenga en cuenta las siguientes observaciones sobre la implementación:

- Los constructores sobrecargados permiten leer el archivo original o uno que tenga un esquema idéntico. Este patrón es habitual al escribir un proveedor de tipo para orígenes de datos locales o remotos, y además permite el uso de un archivo local como plantilla para los datos remotos.

- Puede utilizar el valor [TypeProviderConfig](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-compilerservices-typeproviderconfig.html) que se pasa al constructor del proveedor de tipos para resolver nombres de archivo relativos.

- Se puede utilizar el método `AddDefinitionLocation` para definir la ubicación de las propiedades proporcionadas. Por lo tanto, si usa `Go To Definition` en una propiedad proporcionada, el archivo CSV se abrirá en Visual Studio.

- Se puede utilizar el tipo `ProvidedMeasureBuilder` para buscar las unidades del SI y generar los tipos `float<_>` pertinentes.

### <a name="key-lessons"></a>Lecciones principales

En esta sección se ha explicado cómo crear un proveedor de tipo para un origen de datos local con un esquema simple que está contenido en el propio origen de datos.

## <a name="going-further"></a>Ampliar conocimientos

En las secciones siguientes se incluyen sugerencias para ampliar conocimientos sobre el tema.

### <a name="a-look-at-the-compiled-code-for-erased-types"></a>Un vistazo al código compilado de los tipos borrados

Para tener una idea de cómo se corresponde el uso del proveedor de tipos con el código emitido, revise la función siguiente mediante el proveedor `HelloWorldTypeProvider` utilizado anteriormente en este tema.

```fsharp
let function1 () =
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

A continuación se muestra una imagen del código resultante descompilado mediante ildasm.exe:

```il
.class public abstract auto ansi sealed Module1
extends [mscorlib]System.Object
{
.custom instance void [FSharp.Core]Microsoft.FSharp.Core.CompilationMappingAtt
ribute::.ctor(valuetype [FSharp.Core]Microsoft.FSharp.Core.SourceConstructFlags)
= ( 01 00 07 00 00 00 00 00 )
.method public static int32  function1() cil managed
{
// Code size       24 (0x18)
.maxstack  3
.locals init ([0] object obj1)
IL_0000:  nop
IL_0001:  ldstr      "some data"
IL_0006:  unbox.any  [mscorlib]System.Object
IL_000b:  stloc.0
IL_000c:  ldloc.0
IL_000d:  call       !!0 [FSharp.Core_2]Microsoft.FSharp.Core.LanguagePrimit
ives/IntrinsicFunctions::UnboxGeneric<string>(object)
IL_0012:  callvirt   instance int32 [mscorlib_3]System.String::get_Length()
IL_0017:  ret
} // end of method Module1::function1

} // end of class Module1
```

Como muestra el ejemplo, se han borrado todas las menciones del tipo `Type1` y la propiedad `InstanceProperty`, y quedan solo las operaciones para los tipos de tiempo de ejecución relacionados.

### <a name="design-and-naming-conventions-for-type-providers"></a>Diseño y convenciones de nomenclatura para los proveedores de tipos

Respete las convenciones siguientes al crear proveedores de tipos.

**Proveedores de protocolos de conectividad** En general, los nombres de la mayoría de los archivos dll de proveedor para los protocolos de datos y conectividad de servicio, como las conexiones de OData o SQL, deben acabar en `TypeProvider` o `TypeProviders` . Por ejemplo, utilice un nombre de DLL similar a la siguiente cadena:

`Fabrikam.Management.BasicTypeProviders.dll`

Asegúrese de que los tipos proporcionados son miembros del espacio de nombres correspondiente e indican el protocolo de conexión que se ha implementado:

```fsharp
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

**Proveedores de utilidades para la codificación general**.  Para un proveedor de tipos de utilidad, como el de las expresiones regulares, el proveedor de tipos puede ser parte de una biblioteca base, como se muestra en el ejemplo siguiente:

```fsharp
#r "Fabrikam.Core.Text.Utilities.dll"
```

En este caso, el tipo proporcionado aparecería en un punto adecuado según las convenciones normales de diseño de .NET:

```fsharp
  open Fabrikam.Core.Text.RegexTyped

  let regex = new RegexTyped<"a+b+a+b+">()
```

**Orígenes de datos singleton**. Algunos proveedores de tipos se conectan a un único origen de datos dedicado y solo proporcionan datos. En este caso, se debería colocar el sufijo `TypeProvider` y utilizar las convenciones normales de nomenclatura de .NET:

```fsharp
#r "Fabrikam.Data.Freebase.dll"

let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

Para obtener más información, vea la convención de diseño `GetConnection` que se describe más adelante en este tema.

### <a name="design-patterns-for-type-providers"></a>Patrones de diseño para los proveedores de tipos

En las secciones siguientes se describen los patrones de diseño que se pueden usar cuando se crean los proveedores de tipos.

#### <a name="the-getconnection-design-pattern"></a>El patrón de diseño GetConnection

La mayoría de los proveedores de tipos se deben escribir para que usen el patrón `GetConnection` utilizado por los proveedores de tipo en FSharp.Data.TypeProviders.dll, como se muestra en el ejemplo siguiente:

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a>Proveedores de tipos respaldados por datos y servicios remotos

Antes de crear un proveedor de tipos respaldado por datos y servicios remotos, se deben tener en cuenta varios problemas que son inherentes a la programación conectada. Estos problemas incluyen los siguientes aspectos:

- Asignación de esquemas

- Vida e invalidación en presencia de un cambio de esquema

- Almacenamiento en caché de esquemas

- Implementaciones asíncronas de operaciones de acceso a datos

- Consultas admitidas, incluidas las consultas LINQ

- Credenciales y autenticación

Este tema no profundiza en estos problemas.

### <a name="additional-authoring-techniques"></a>Técnicas adicionales de creación

Al escribir sus propios proveedores de tipos, quizá quiera utilizar las siguientes técnicas adicionales.

### <a name="creating-types-and-members-on-demand"></a>Crear tipos y miembros bajo demanda

La API de ProvidedType tiene versiones demoradas de AddMember.

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

Estas versiones se utilizan para crear espacios de tipos a petición.

### <a name="providing-array-types-and-generic-type-instantiations"></a>Proporcionar tipos de matriz y crear instancias de tipos genéricos

Los miembros proporcionados (cuyas firmas incluyen tipos de matriz, tipos de ByRef y creaciones de instancias de tipos genéricos) usan el normal `MakeArrayType` , `MakePointerType` y `MakeGenericType` en cualquier instancia de <xref:System.Type> , incluido `ProvidedTypeDefinitions` .

> [!NOTE]
> En algunos casos, es posible que tenga que usar el ayudante en `ProvidedTypeBuilder.MakeGenericType` .  Consulte la [documentación del SDK del proveedor de tipos](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) para obtener más detalles.

### <a name="providing-unit-of-measure-annotations"></a>Proporcionar anotaciones de unidades de medida

La API ProvidedTypes proporciona asistentes para proporcionar anotaciones de medidas. Por ejemplo, para proporcionar el tipo `float<kg>`, utilice el código siguiente:

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  Para proporcionar el tipo `Nullable<decimal<kg/m^2>>`, utilice el código siguiente:

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a>Acceder a recursos locales del proyecto o del script

A cada instancia de un proveedor de tipo se le puede asignar un valor `TypeProviderConfig` durante la construcción. Este valor contiene la "carpeta de resolución" para el proveedor (es decir, la carpeta del proyecto para la compilación o el directorio que contiene un script), la lista de ensamblados a los que se hace referencia y otra información.

### <a name="invalidation"></a>Invalidación

Los proveedores pueden generar señales de invalidación para notificar al servicio del lenguaje F# que las suposiciones acerca del esquema pueden haber cambiado. Cuando se produce la invalidación, se repite una comprobación de tipos si el proveedor se hospeda en Visual Studio. Esta señal se omite cuando el proveedor se hospeda en F# Interactive o por el compilador de F# (fsc.exe).

### <a name="caching-schema-information"></a>Almacenar en caché la información del esquema

A menudo los proveedores deben almacenar en memoria caché el acceso a la información del esquema. Los datos almacenados en caché deben almacenarse utilizando un nombre de archivo que se da como parámetro estático o como datos de usuario. Un ejemplo de almacenamiento en caché de esquema es el parámetro `LocalSchemaFile` en los proveedores de tipos del ensamblado `FSharp.Data.TypeProviders`. En la implementación de estos proveedores, este parámetro estático ordena al proveedor de tipos que use la información del esquema del archivo local especificado en lugar de acceder al origen de datos en la red. Para utilizar la información del esquema almacenada en caché, también se debe establecer el parámetro estático `ForceUpdate` en `false`. Se puede usar una técnica similar para permitir el acceso a datos en línea y sin conexión.

### <a name="backing-assembly"></a>Ensamblado de respaldo

Al compilar `.dll` un `.exe` archivo o, el archivo. dll de respaldo para los tipos generados se vincula estáticamente en el ensamblado resultante. Este vínculo se crea copiando las definiciones de tipos del lenguaje intermedio (IL) y cualquier recurso administrado del ensamblado de respaldo al ensamblado final. Cuando se usa F# Interactive, el archivo .dll de respaldo no se copia, sino que se carga directamente en el proceso de F# Interactive.

### <a name="exceptions-and-diagnostics-from-type-providers"></a>Excepciones y diagnósticos de proveedores de tipo

Todos los usos de todos los miembros de los tipos proporcionados pueden producir excepciones. En todos los casos, si un proveedor de tipos genera una excepción, el compilador host atribuye el error a un proveedor de tipos específico.

- Las excepciones de proveedores de tipos nunca deben producir errores internos del compilador.

- Los proveedores de tipo no pueden notificar advertencias.

- Cuando un proveedor de tipo se hospeda en el compilador de F#, un entorno de desarrollo de F# o F# Interactive, se detectan todas las excepciones de ese proveedor. La propiedad Message es siempre el texto del error y no aparece ningún seguimiento de pila. Si va a iniciar una excepción, puede iniciar los ejemplos siguientes: `System.NotSupportedException` , `System.IO.IOException` , `System.Exception` .

#### <a name="providing-generated-types"></a>Proporcionar tipos generados

Hasta ahora, en este documento se ha explicado cómo proporcionar tipos borrados. También se puede usar el mecanismo de proveedores de tipo de F# para proporcionar tipos generados, que se agregan como definiciones de tipo reales de .NET en el programa del usuario. Se debe hacer referencia a los tipos proporcionados generados mediante una definición de tipo.

```fsharp
open Microsoft.FSharp.TypeProviders

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

El código del asistente ProvidedTypes-0.2 que forma parte de la versión 3.0 de F# solo tiene compatibilidad limitada para proporcionar tipos generados. Los enunciados siguientes deben ser verdaderos para una definición de un tipo generado:

- `isErased` se debe establecer en `false`.

- El tipo generado se debe agregar a un recién construido `ProvidedAssembly()` , que representa un contenedor para fragmentos de código generados.

- El proveedor debe tener un ensamblado que tenga un archivo .dll de respaldo real de .NET con un archivo .dll coincidente en el disco.

## <a name="rules-and-limitations"></a>Reglas y limitaciones

Al escribir proveedores de tipos, tenga en cuenta las siguientes reglas y limitaciones.

### <a name="provided-types-must-be-reachable"></a>Los tipos proporcionados deben ser accesibles

Debe tenerse acceso a todos los tipos proporcionados desde los tipos no anidados. Los tipos no anidados se proporcionan en la llamada al constructor `TypeProviderForNamespaces` o en una llamada a `AddNamespace`. Por ejemplo, si el proveedor proporciona un tipo `StaticClass.P : T`, debe asegurarse de que T es un tipo no anidado o está anidado debajo de uno.

Por ejemplo, algunos proveedores tienen una clase estática como `DataTypes` que contiene estos tipos `T1, T2, T3, ...`. De lo contrario, el error indica que se ha encontrado una referencia al tipo T en el ensamblado A, pero el tipo no se encuentra en ese ensamblado. Si aparece este error, compruebe que se puede obtener acceso a todos los subtipos desde los tipos del proveedor. Nota: estos `T1, T2, T3...` tipos se conocen como tipos *sobre la marcha* . Recuerde colocarlos en un espacio de nombres accesible o en un tipo primario.

### <a name="limitations-of-the-type-provider-mechanism"></a>Limitaciones del mecanismo de proveedores de tipos

El mecanismo de proveedores de tipos de F# tiene las siguientes limitaciones:

- La infraestructura subyacente para los proveedores de tipos de F# no admite tipos genéricos proporcionados ni métodos genéricos proporcionados.

- El mecanismo no admite tipos anidados con parámetros estáticos.

## <a name="development-tips"></a>Sugerencias de desarrollo

Puede que le resulten útiles las siguientes sugerencias durante el proceso de desarrollo:

### <a name="run-two-instances-of-visual-studio"></a>Ejecutar dos instancias de Visual Studio

Puede desarrollar el proveedor de tipo en una instancia y probarlo en la otra porque el IDE de prueba tomará un bloqueo en el archivo .dll que evita que se recompile el proveedor de tipo. Por lo tanto, debe cerrar la segunda instancia de Visual Studio mientras se compila el proveedor en la primera y, a continuación, debe volver a abrir la segunda instancia después de compilar el proveedor.

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a>Depurar proveedores de tipos mediante invocaciones de fsc.exe

Puede invocar proveedores de tipo mediante las herramientas siguientes:

- fsc.exe (el compilador de línea de comandos de F#)

- fsi.exe (el compilador interactivo de F#)

- devenv.exe (Visual Studio)

A menudo, lo más fácil es depurar los proveedores de tipo mediante fsc.exe en un archivo de script de prueba (por ejemplo, script.fsx). Puede iniciar un depurador desde el símbolo del sistema.

```console
devenv /debugexe fsc.exe script.fsx
```

  Puede usar print-to-stdout como registro.

## <a name="see-also"></a>Consulte también

- [Proveedores de tipos](index.md)
- [SDK del proveedor de tipos](https://github.com/fsprojects/FSharp.TypeProviders.SDK)
