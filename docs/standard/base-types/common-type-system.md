---
title: Sistema de tipos comunes
description: Explore el sistema de tipos en .NET. Obtenga información sobre los tipos en .NET (tipos de valor o tipos de referencia), definición de tipos, miembros de tipos y características de miembros de tipo.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- type system
- common type system
- assemblies [.NET Framework], types
- reference types
- value types
- cross-language interoperability
- namespaces [.NET Framework], types
- types, about types
ms.assetid: 53c57c96-83e1-4ee3-9543-9ac832671a89
ms.openlocfilehash: db0ecd59f122228d33b74be6dec51371413d68b3
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84767837"
---
# <a name="common-type-system"></a>Sistema de tipos comunes

Common Type System define cómo se declaran, usan y administran los tipos en Common Language Runtime. Es también una parte importante de la compatibilidad en tiempo de ejecución con la integración entre lenguajes. El sistema de tipos común realiza las funciones siguientes:  
  
- Establece un marco de trabajo que ayuda a permitir la integración entre lenguajes, la seguridad de tipos y la ejecución de código de alto rendimiento.  
  
- Proporciona un modelo orientado a objetos que admite la implementación completa de muchos lenguajes de programación.  
  
- Define reglas que deben seguir los lenguajes, lo que ayuda a garantizar que los objetos escritos en distintos lenguajes puedan interactuar unos con otros.  
  
- Proporciona una biblioteca que contiene los tipos de datos primitivos (como <xref:System.Boolean>, <xref:System.Byte>, <xref:System.Char>, <xref:System.Int32> y <xref:System.UInt64>) que se emplean en el desarrollo de aplicaciones.
  
## <a name="types-in-net"></a>Tipos de .NET

 Todos los tipos de .NET son tipos de valor o tipos de referencia.  
  
 Los tipos de valor son tipos de datos cuyos objetos se representan mediante el valor real del objeto. Si se asigna una instancia de un tipo de valor a una variable, esa variable obtiene una copia reciente del valor.  
  
 Los tipos de referencia son tipos de datos cuyos objetos se representan mediante una referencia (similar a un puntero) al valor real del objeto. Si se asigna un tipo de referencia a una variable, esa variable hace referencia (o apunta) al valor original. No se realiza ninguna copia.  
  
 Common Type System en .NET admite las cinco categorías de tipos siguientes:  
  
- [Clases](#classes)  
  
- [Estructuras](#structures)  
  
- [Enumeraciones](#enumerations)  
  
- [Interfaces](#interfaces)  
  
- [Delegados](#delegates)  
  
### <a name="classes"></a>Clases

 Una clase es un tipo de referencia que se puede derivar directamente de otra clase y que se deriva implícitamente de <xref:System.Object?displayProperty=nameWithType>. La clase define las operaciones que un objeto (que es una instancia de la clase) puede realizar (métodos, eventos o propiedades) y los datos que el objeto contiene (campos). Aunque una clase suele incluir una definición y una implementación (a diferencia, por ejemplo, de las interfaces, que solo contienen una definición sin implementación), puede tener uno o varios miembros sin implementación.  
  
 En la tabla siguiente se describen algunas de las características que una clase puede tener. Cada lenguaje compatible con el motor en tiempo de ejecución proporciona una forma de indicar que una clase o un miembro de clase tiene una o varias de estas características. En cambio, puede que no estén disponibles todas estas características en los lenguajes de programación orientados a .NET.  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|sealed|Especifica que no se puede derivar otra clase de este tipo.|  
|implementa|Indica que la clase utiliza una o varias interfaces proporcionando implementaciones de miembros de la interfaz.|  
|abstract|Indica que no se pueden crear instancias de la clase. Para utilizarla se debe derivar de ella otra clase.|  
|hereda|Indica que las instancias de la clase se pueden utilizar en cualquier lugar en que se especifique la clase base. Una clase derivada que hereda de una clase base puede usar la implementación de cualquier miembro público proporcionado por la clase base o la clase derivada puede invalidar la implementación de los miembros públicos con su propia implementación.|  
|exported o not exported|Indica si una clase está visible fuera del ensamblado en el que se define. Esta característica se aplica únicamente a las clases de nivel superior y no a las clases anidadas.|  
  
> [!NOTE]
> Una clase también puede estar anidada en una estructura o clase primaria. Las clases anidadas tienen también características de miembro. Para obtener más información, consulte [Tipos anidados](#nested-types).  
  
 Los miembros de clase que no tienen implementación son miembros abstractos. Una clase que tiene uno o varios miembros abstractos es abstracta y no se pueden crear nuevas instancias de ella. Algunos lenguajes destinados al motor en tiempo de ejecución permiten marcar una clase como abstracta incluso aunque no tenga ningún miembro abstracto. Se puede usar una clase abstracta cuando se desea encapsular un conjunto básico de funcionalidad que las clases derivadas pueden heredar o invalidar según corresponda. Las clases que no son abstractas se conocen como clases concretas.  
  
 Una clase puede implementar cualquier número de interfaces pero puede heredar solo de una clase base además de la clase <xref:System.Object?displayProperty=nameWithType>, de la que todas las clases heredan implícitamente. Todas las clases deben tener al menos un constructor, que inicializa nuevas instancias de la clase. Si no se define explícitamente un constructor, la mayoría de los compiladores proporcionarán automáticamente un constructor sin parámetros.  
  
### <a name="structures"></a>Estructuras

 Una estructura es un tipo de valor que se deriva implícitamente de <xref:System.ValueType?displayProperty=nameWithType>, que a su vez se deriva de <xref:System.Object?displayProperty=nameWithType>. Una estructura es útil para representar valores cuyos requisitos de memoria sean reducidos y para pasar valores como parámetros por valor a los métodos que tengan parámetros fuertemente tipados. En .NET, todos los tipos de datos primitivos (<xref:System.Boolean>, <xref:System.Byte>, <xref:System.Char>, <xref:System.DateTime>, <xref:System.Decimal>, <xref:System.Double>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.SByte>, <xref:System.Single>, <xref:System.UInt16>, <xref:System.UInt32> y <xref:System.UInt64>) se definen como estructuras.  
  
 Al igual que las clases, las estructuras definen datos (los campos de la estructura) y las operaciones que se pueden realizar con esos datos (los métodos de la estructura). Esto significa que se puede llamar a los métodos en las estructuras, incluso a los métodos virtuales definidos en las clases <xref:System.Object?displayProperty=nameWithType> y <xref:System.ValueType?displayProperty=nameWithType>, y a cualquier método definido en el propio tipo de valor. Es decir, las estructuras pueden tener campos, propiedades y eventos, así como métodos estáticos y no estáticos. Se pueden crear instancias de las estructuras, pasarlas como parámetros, almacenarlas como variables locales o almacenarlas en un campo de otro tipo de valor o tipo de referencia. Las estructuras también pueden implementar interfaces.  
  
 Los tipos de valor también difieren de las clases en varios aspectos. En primer lugar, aunque heredan implícitamente de <xref:System.ValueType?displayProperty=nameWithType>, no pueden heredar directamente de ningún tipo. De manera similar, todos los tipos de valor están sellados, lo que quiere decir que de ellos no se puede derivar ningún otro tipo. Tampoco necesitan constructores.  
  
 Para cada tipo de valor, Common Language Runtime proporciona un tipo correspondiente al que se ha aplicado la conversión boxing, que es una clase que tiene el mismo estado y comportamiento que el tipo de valor. A una instancia de un tipo de valor se le aplica la conversión boxing cuando se pasa a un método que acepta un parámetro de tipo <xref:System.Object?displayProperty=nameWithType>. Se le aplica la conversión unboxing (es decir, se vuelve a convertir la instancia de una clase en una instancia de un tipo de valor) cuando se devuelve el control de una llamada a un método que acepta un tipo de valor como parámetro por referencia. En el caso de algunos lenguajes, se debe usar una sintaxis especial cuando se necesita el tipo al que se haya aplicado la conversión boxing, mientras que otros emplean el tipo automáticamente cuando es necesario. Cuando se define un tipo de valor, se definen los dos tipos: al que se ha aplicado la conversión boxing y al que se ha aplicado la conversión unboxing.  
  
### <a name="enumerations"></a>Enumeraciones

 Una enumeración es un tipo de valor que hereda directamente de <xref:System.Enum?displayProperty=nameWithType> y proporciona nombres alternativos para los valores de un tipo primitivo subyacente. Un tipo de enumeración tiene un nombre, un tipo subyacente que debe ser uno de los tipos de enteros con o sin signo integrados (como <xref:System.Byte>, <xref:System.Int32> o <xref:System.UInt64>) y un conjunto de campos. Los campos son campos literales estáticos, cada uno de los cuales representa una constante. El mismo valor se puede asignar a varios campos. Cuando esto sucede, se debe marcar uno de los valores como valor de enumeración primario para la reflexión y la conversión de cadenas.  
  
 Se puede asignar un valor del tipo subyacente a una enumeración y viceversa, y no es necesario que el motor en tiempo de ejecución realice una conversión. Se puede crear una instancia de una enumeración y llamar a los métodos de <xref:System.Enum?displayProperty=nameWithType>, además de llamar a cualquier método definido en el tipo subyacente de la enumeración. Sin embargo, algunos lenguajes no permiten pasar una enumeración como parámetro cuando se necesita una instancia del tipo subyacente (o viceversa).  
  
 A las enumeraciones se les aplican las restricciones siguientes:  
  
- No pueden definir sus propios métodos.  
  
- No pueden implementar interfaces.  
  
- No pueden definir propiedades ni eventos.  
  
- No pueden ser genéricas, a menos que sean genéricas solo porque están anidadas dentro de un tipo genérico. Es decir, una enumeración no puede tener parámetros de tipo propios.  
  
    > [!NOTE]
    > Los tipos anidados (incluidas las enumeraciones) creados con Visual Basic, C# y C++ incluyen los parámetros de tipo de todos los tipos genéricos envolventes, por lo que son genéricos aunque no tengan parámetros de tipo propios. Para obtener más información, vea la sección "Tipos anidados" en el tema de referencia del método <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType>.  
  
 El atributo <xref:System.FlagsAttribute> indica una clase especial de enumeración denominada campo de bits. El motor en tiempo de ejecución no distingue entre enumeraciones tradicionales y campos de bits, pero el lenguaje podría hacerlo. Cuando se hace esta distinción, se pueden utilizar operadores bit a bit en estos campos de bits, para generar valores sin nombre, pero no en las enumeraciones. Normalmente, las enumeraciones se utilizan para listas de elementos únicos, como los días de la semana, los nombres de países o regiones, etc. Los campos de bits se utilizan, en general, para listas de calidades o cantidades que pueden producirse en combinaciones, como `Red And Big And Fast`.  
  
 En el ejemplo siguiente se muestra cómo utilizar los campos de bits y las enumeraciones tradicionales.  
  
 [!code-csharp[Conceptual.Types.Enum#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.enum/cs/example.cs#1)]
 [!code-vb[Conceptual.Types.Enum#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.enum/vb/example.vb#1)]  

### <a name="interfaces"></a>Interfaces

 Una interfaz define un contrato que especifica una relación de lo que se puede hacer o una relación de lo que se tiene. Las interfaces se utilizan a menudo para implementar una funcionalidad, como comparar y ordenar (interfaces <xref:System.IComparable> e <xref:System.IComparable%601>), comprobar la igualdad (interfaz <xref:System.IEquatable%601>) o enumerar los elementos de una colección (interfaces <xref:System.Collections.IEnumerable> e <xref:System.Collections.Generic.IEnumerable%601>). Las interfaces pueden tener propiedades, métodos y eventos, que son todos miembros abstractos; es decir, aunque la interfaz define los miembros y sus firmas, deja que el tipo encargado de implementar la interfaz defina la funcionalidad de cada miembro de la interfaz. Esto significa que cualquier clase o estructura que implemente una interfaz debe proporcionar definiciones de los miembros abstractos declarados en la interfaz. Una interfaz puede necesitar que cualquier clase o estructura que implemente una interfaz implemente también otras interfaces.  
  
 A las interfaces se les aplican las restricciones siguientes:  
  
- Una interfaz se puede declarar con cualquier tipo de accesibilidad, pero los miembros de la interfaz deben tener todos accesibilidad pública.  
  
- Las interfaces no pueden definir constructores  
  
- Las interfaces no pueden definir campos.  
  
- Las interfaces solo pueden definir miembros de instancia. No pueden definir miembros estáticos.  
  
 Cada lenguaje debe proporcionar reglas para asignar una implementación a la interfaz que necesita el miembro, ya que varias interfaces pueden declarar un miembro con la misma firma y esos miembros pueden tener implementaciones independientes.  

### <a name="delegates"></a>Delegados

 Los delegados son tipos de referencia con una finalidad similar a la de los punteros a función de C++. Se usan para los controladores de eventos y las funciones de devolución de llamada en .NET. A diferencia de los punteros a función, los delegados son seguros, se pueden comprobar y proporcionan seguridad de tipos. Un tipo de delegado puede representar cualquier método de instancia o método estático que tenga una firma compatible.  
  
 Un parámetro de un delegado es compatible con el parámetro correspondiente de un método si el tipo del parámetro del delegado es más restrictivo que el del método, porque así se garantiza que el argumento que se pase al delegado también se podrá pasar de forma segura al método.  
  
 De forma similar, el tipo de valor devuelto de un delegado es compatible con el tipo de valor devuelto de un método si el del método es más restrictivo que el del delegado, porque así se garantiza que el tipo de valor devuelto por el método se puede convertir con seguridad al tipo de valor devuelto del delegado.  
  
 Por ejemplo, un delegado que tiene un parámetro de tipo <xref:System.Collections.IEnumerable> y un tipo de valor devuelto <xref:System.Object> puede representar un método que tiene un parámetro de tipo <xref:System.Object> y un valor devuelto de tipo <xref:System.Collections.IEnumerable>. Para obtener más información y un código de ejemplo, vea <xref:System.Delegate.CreateDelegate%28System.Type%2CSystem.Object%2CSystem.Reflection.MethodInfo%29?displayProperty=nameWithType>.  
  
 Se dice que un delegado está enlazado al método que representa. Además de estar enlazado al método, un delegado puede estar enlazado a un objeto. El objeto representa el primer parámetro del método y se pasa al método cada vez que se invoca el delegado. Si el método es un método de instancia, el objeto enlazado se pasa como el parámetro `this` implícito (`Me` en Visual Basic); si el método es estático, el objeto se pasa como primer parámetro formal del método y la firma del delegado debe coincidir con los parámetros restantes. Para obtener más información y un código de ejemplo, vea <xref:System.Delegate?displayProperty=nameWithType>.  
  
 Todos los delegados heredan de <xref:System.MulticastDelegate?displayProperty=nameWithType>, que hereda de <xref:System.Delegate?displayProperty=nameWithType>. Los lenguajes C#, Visual Basic y C++ no permiten que se herede de estos tipos. En su lugar, proporcionan palabras clave para declarar los delegados.  
  
 Dado que los delegados heredan de <xref:System.MulticastDelegate>, un delegado tiene una lista de invocación, que es una lista de métodos que representa el delegado y que se ejecutan cuando se llama al delegado. Todos los métodos de la lista reciben los argumentos proporcionados cuando se invoca al delegado.  
  
> [!NOTE]
> El valor devuelto no se define para los delegados que tienen más de un método en su lista de invocación, aunque el delegado tenga un tipo de valor devuelto.  
  
 En muchos casos, como en el de los métodos de devolución de llamada, un delegado solo representa un método y las únicas acciones que se deben llevar a cabo son la creación y la invocación del delegado.  
  
 Por lo que se refiere a los delegados que representan varios métodos, .NET proporciona métodos de las clases de delegado <xref:System.Delegate> y <xref:System.MulticastDelegate> para operaciones tales como agregar un método a una lista de invocación del delegado (el método <xref:System.Delegate.Combine%2A?displayProperty=nameWithType>), quitar un método (el método <xref:System.Delegate.Remove%2A?displayProperty=nameWithType>) y obtener la lista de invocación (el método <xref:System.Delegate.GetInvocationList%2A?displayProperty=nameWithType>).  
  
> [!NOTE]
> No es preciso usar estos métodos para los delegados de controladores de eventos en C#, C++ ni Visual Basic, ya que estos lenguajes proporcionan sintaxis para agregar y quitar controladores de eventos.  

## <a name="type-definitions"></a>Definiciones de tipo

 Una definición de tipo incluye lo siguiente:  
  
- Los atributos definidos en el tipo.  
  
- La accesibilidad del tipo (visibilidad).  
  
- El nombre del tipo.  
  
- El tipo base del tipo.  
  
- Las interfaces que implementa el tipo.  
  
- Las definiciones de todos los miembros del tipo  
  
### <a name="attributes"></a>Atributos  
 Los atributos proporcionan metadatos adicionales definidos por el usuario . Normalmente, se emplean para almacenar información adicional sobre un tipo en su ensamblado o para modificar el comportamiento de un miembro de tipo en tiempo de diseño o en tiempo de ejecución.  
  
 Los atributos son clases que heredan de <xref:System.Attribute?displayProperty=nameWithType>. Los lenguajes que admiten el uso de atributos tienen su propia sintaxis para aplicar atributos a un elemento del lenguaje. Los atributos se pueden aplicar a casi cualquier elemento del lenguaje; los elementos específicos a los que se puede aplicar un atributo los define la clase <xref:System.AttributeUsageAttribute> aplicada a esa clase de atributos.  
  
### <a name="type-accessibility"></a>Accesibilidad a tipos  
 Todos los tipos tienen un modificador que rige su accesibilidad desde otros tipos. En la tabla siguiente se describen las accesibilidades a tipos que admite el motor en tiempo de ejecución.  
  
|Accesibilidad|Descripción|  
|-------------------|-----------------|  
|public|Todos los ensamblados pueden tener acceso al tipo.|  
|ensamblado|El tipo sólo es accesible desde su ensamblado.|  
  
 La accesibilidad de un tipo anidado depende de su dominio de accesibilidad, que viene determinado por la accesibilidad declarada del miembro y el dominio de accesibilidad del tipo contenedor inmediato. Sin embargo, el dominio de accesibilidad de un tipo anidado no puede superar al del tipo contenedor.  
  
 El dominio de accesibilidad de un miembro anidado `M` declarado en un tipo `T` dentro de un programa `P` se define de la manera siguiente (teniendo en cuenta que el propio miembro `M` puede ser un tipo):  
  
- Si la accesibilidad declarada de `M` es `public`, el dominio de accesibilidad de `M` es el dominio de accesibilidad de `T`.  
  
- Si la accesibilidad declarada de `M` es `protected internal`, el dominio de accesibilidad de `M` es la intersección del dominio de accesibilidad de `T` con el texto de programa de `P` y el texto de programa de cualquier tipo derivado de `T` declarado fuera de `P`.  
  
- Si la accesibilidad declarada de `M` es `protected`, el dominio de accesibilidad de `M` es la intersección del dominio de accesibilidad de `T` con el texto de programa de `T` y cualquier tipo derivado de `T`.  
  
- Si la accesibilidad declarada de `M` es `internal`, el dominio de accesibilidad de `M` es la intersección del dominio de accesibilidad de `T` con el texto de programa de `P`.  
  
- Si la accesibilidad declarada de `M` es `private`, el dominio de accesibilidad de `M` es el texto de programa de `T`.  
  
### <a name="type-names"></a>Nombres de tipo  
 El sistema de tipos común sólo impone dos restricciones en los nombres:  
  
- Todos los nombres se codifican como cadenas de caracteres Unicode (de 16 bits).  
  
- Los nombres no pueden tener un valor incrustado (de 16 bits) de 0x0000.  
  
 Sin embargo, la mayoría de los lenguajes imponen restricciones adicionales sobre los nombres de tipo. Todas las comparaciones se realizan byte a byte, por lo que distinguen entre mayúsculas y minúsculas y son independientes de la configuración regional.  
  
 Aunque un tipo puede hacer referencia a tipos de otros módulos y ensamblados, es preciso que se defina íntegramente en un solo módulo de .NET. (Sin embargo, según la compatibilidad del compilador, se puede dividir en varios archivos de código fuente.) Los nombres de tipo solo tienen que ser únicos dentro de un espacio de nombres. Para identificar íntegramente un tipo, su nombre debe calificarse con el espacio de nombres que contiene la implementación del tipo.  
  
### <a name="base-types-and-interfaces"></a>Tipos base e interfaces  
 Un tipo puede heredar valores y comportamientos de otro. El sistema de tipos común no permite que los tipos hereden de más de un tipo base.  
  
 Un tipo puede implementar cualquier número de interfaces. Para implementar una interfaz, un tipo debe implementar todos los miembros virtuales de la interfaz. Un tipo derivado puede implementar un método virtual, que se puede invocar estática o dinámicamente.  

## <a name="type-members"></a>Miembros de tipos

 El motor en tiempo de ejecución permite definir miembros de tipos, que especifican el comportamiento y el estado de los tipos. Los miembros de tipos incluyen lo siguiente:  
  
- [Campos](#fields)  
  
- [Propiedades](#properties)  
  
- [Métodos](#methods)  
  
- [Constructores](#constructors)  
  
- [Eventos](#events)  
  
- [Tipos anidados](#nested-types)  

### <a name="fields"></a>Campos

 Un campo describe y contiene parte del estado del tipo. Los campos pueden ser de cualquier tipo que admita el motor en tiempo de ejecución. Normalmente, los campos son de tipo `private` o `protected`, por lo que son accesibles únicamente desde la clase o desde una clase derivada. Si el valor de un campo se puede modificar desde fuera de su tipo, se suele emplear un descriptor de acceso set de una propiedad. Los campos expuestos públicamente suelen ser de solo lectura y pueden ser de dos tipos:  
  
- Constantes, cuyo valor se asigna en tiempo de diseño. Se trata de miembros estáticos de una clase, aunque no se definen mediante la palabra clave `static` (`Shared` en Visual Basic).  
  
- Variables de solo lectura, cuyos valores se pueden asignar en el constructor de clase.  
  
 En el ejemplo siguiente se muestran estos dos usos de los campos de solo lectura.  
  
 [!code-csharp[Conceptual.Types.Members.Fields#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.members.fields/cs/example.cs#1)]
 [!code-vb[Conceptual.Types.Members.Fields#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.members.fields/vb/example.vb#1)]  

### <a name="properties"></a>Propiedades

 Una propiedad identifica un valor o un estado del tipo y define los métodos para obtener o establecer el valor de la propiedad. Las propiedades pueden ser tipos primitivos, colecciones de tipos primitivos, tipos definidos por el usuario o colecciones de tipos definidos por el usuario. Las propiedades se usan a menudo para que la interfaz pública de un tipo se mantenga independiente de la representación real del tipo. De este modo, las propiedades pueden reflejar valores que no están almacenados directamente en la clase (por ejemplo, cuando una propiedad devuelve un valor calculado) o realizar la validación antes de que se asignen valores a campos privados. En el ejemplo siguiente se muestra el último modelo.  
  
 [!code-csharp[Conceptual.Types.Members.Properties#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.members.properties/cs/example.cs#1)]
 [!code-vb[Conceptual.Types.Members.Properties#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.members.properties/vb/example.vb#1)]  
  
 Además de incluir la propiedad propiamente dicha, el Lenguaje Intermedio de Microsoft (MSIL) de un tipo que contiene una propiedad de lectura incluye un método `get_`*propertyname* y el lenguaje MSIL de un tipo que contiene una propiedad de escritura incluye un método `set_`*propertyname*.  

### <a name="methods"></a>Métodos

 Un método describe las operaciones que están disponibles en el tipo. La firma de un método especifica los tipos permitidos de todos sus parámetros y de su valor devuelto.  
  
 Aunque la mayoría de los métodos definen el número exacto de los parámetros necesarios para las llamadas a métodos, algunos admiten un número de parámetros que es variable. El último parámetro declarado de estos métodos se marca con el atributo <xref:System.ParamArrayAttribute>. Normalmente, los compiladores de lenguaje proporcionan una palabra clave, como `params` en C# y `ParamArray` en Visual Basic, que hace que sea innecesario el uso explícito de <xref:System.ParamArrayAttribute>.  

### <a name="constructors"></a>Constructores

 Un constructor es un tipo de método especial que crea nuevas instancias de una clase o una estructura. Al igual que cualquier otro método, un constructor puede incluir parámetros; sin embargo, los constructores no tienen ningún valor devuelto (es decir, devuelven `void`).  
  
 Si el código fuente de una clase no define explícitamente un constructor, el compilador incluye un constructor sin parámetros. Sin embargo, si el código fuente de una clase define solo constructores parametrizados, los compiladores de Visual Basic y C# no generan un constructor sin parámetros.  
  
 Si el código fuente de una estructura define constructores, estos deben tener parámetros; una estructura no puede definir un constructor sin parámetros y los compiladores no generan constructores sin parámetros para las estructuras u otros tipos de valor. Todos los tipos de valor tienen un constructor sin parámetros implícito. Common Language Runtime implementa este constructor, que inicializa todos los campos de la estructura en sus valores predeterminados.  

### <a name="events"></a>Events

 Un evento define un incidente al que se puede responder, así como los métodos para suscribirse a un evento, anular la suscripción y generar el evento. Los eventos se usan con frecuencia para informar a otros tipos de cambios de estado. Para más información, vea [Eventos](../events/index.md).  

### <a name="nested-types"></a>Tipos anidados

 Un tipo anidado es un tipo que es un miembro de algún otro tipo. Los tipos anidados deben estar estrechamente acoplados a su tipo contenedor y no deben ser útiles como tipos de uso general. Los tipos anidados son útiles cuando el tipo declarativo utiliza y crea instancias del tipo anidado y el uso de dicho tipo anidado no se expone en miembros públicos.  
  
 Los tipos anidados resultan confusos para algunos desarrolladores y no deben estar públicamente visibles a menos que haya una razón de peso. En una biblioteca bien diseñada, los desarrolladores rara vez deberían tener que utilizar tipos anidados para crear instancias de objetos o declarar variables.  

## <a name="characteristics-of-type-members"></a>Características de los miembros de tipos

 Common Type System permite que los miembros de tipos tengan diversas características; sin embargo, no es necesario que los lenguajes admitan todas estas características. En la siguiente tabla se describen las características de los miembros.  
  
|Característica|Se puede aplicar a|Descripción|  
|--------------------|------------------|-----------------|  
|abstract|Métodos, propiedades y eventos|El tipo no proporciona la implementación del método. Los tipos que heredan o implementan métodos abstractos deben proporcionar una implementación para el método. La única excepción es que el tipo derivado sea un tipo abstracto. Todos lo métodos abstractos son virtuales.|  
|private, family, assembly, family y assembly, family o assembly, o public|Todas|Define la accesibilidad del miembro:<br /><br /> private<br /> Solo es accesible desde el mismo tipo que el miembro o desde un tipo anidado.<br /><br /> family<br /> Accesible desde el mismo tipo que el miembro y desde tipos derivados que heredan de él.<br /><br /> ensamblado<br /> Accesible sólo en el ensamblado en que está definido el tipo.<br /><br /> family y assembly<br /> Accesible sólo desde los tipos que estén calificados para el acceso de familia y ensamblado.<br /><br /> family o assembly<br /> Accesible sólo desde los tipos que califican el acceso de familia o ensamblado.<br /><br /> public<br /> Accesible desde cualquier tipo.|  
|final|Métodos, propiedades y eventos|El método virtual no puede ser reemplazado en un tipo derivado.|  
|initialize-only|Campos|El valor sólo se puede inicializar y no se puede escribir en él después de la inicialización.|  
|instancia|Campos, métodos, propiedades y eventos|Si un miembro no está marcado como `static` (C# y C++), `Shared` (Visual Basic), `virtual` (C# y C++) u `Overridable` (Visual Basic), es un miembro de instancia (no hay palabra clave de la instancia). En la memoria habrá tantas copias de estos miembros como objetos que los utilicen.|  
|Literal|Campos|El valor asignado al campo es un valor fijo, conocido en tiempo de compilación, de un tipo de valor integrado. Los campos literales, a veces, se conocen como constantes.|  
|newslot u override|Todas|Define cómo interactúa el miembro con los miembros heredados que tienen la misma firma:<br /><br /> newslot<br /> Oculta los miembros heredados que tienen la misma firma.<br /><br /> override<br /> Reemplaza la definición de un método virtual heredado.<br /><br /> El valor predeterminado es newslot.|  
|estático|Campos, métodos, propiedades y eventos|El miembro pertenece al tipo en que está definido, no a una instancia particular del tipo. El miembro existe incluso si no se ha creado ninguna instancia del tipo y lo comparten todas las instancias del tipo.|  
|virtual|Métodos, propiedades y eventos|Un tipo derivado puede implementar el método, que se puede invocar estática o dinámicamente. Si se usa la invocación dinámica, el tipo de la instancia que hace la llamada en tiempo de ejecución (en lugar del tipo conocido en tiempo de compilación) determina a qué implementación del método se llama. Para invocar un método virtual de manera estática, es posible que haya que convertir la variable en un tipo que use la versión deseada del método.|  
  
### <a name="overloading"></a>Sobrecarga  
 Cada miembro de tipo tiene una firma única. Las firmas de método están formadas por el nombre del método y una lista de parámetros (el orden y los tipos de los argumentos del método). Se pueden definir varios métodos con el mismo nombre dentro un tipo, siempre y cuando sus firmas sean distintas. Cuando se definen dos o más métodos con el mismo nombre se dice que el método está sobrecargado. Por ejemplo, en <xref:System.Char?displayProperty=nameWithType>, se reemplaza el método <xref:System.Char.IsDigit%2A>. Un método toma un argumento de tipo <xref:System.Char>. El otro método toma un argumento de tipo <xref:System.String> y un argumento de tipo <xref:System.Int32>.  
  
> [!NOTE]
> El tipo de valor devuelto no se considera parte de la firma de un método. Es decir, no se pueden sobrecargar los métodos si solo difieren en el tipo de valor devuelto.  
  
### <a name="inherit-override-and-hide-members"></a>Herencia, invalidación y ocultación de miembros  
 Un tipo derivado hereda todos los miembros de su tipo base, es decir, estos miembros se definen en el tipo derivado y están disponibles para él. El comportamiento o cualidades de los miembros heredados se puede modificar de dos maneras:  
  
- Un tipo derivado puede ocultar un miembro heredado definiendo un nuevo miembro con la misma firma. Esto puede hacerse para convertir un miembro público en privado o para definir un nuevo comportamiento para un método heredado que está marcado como `final`.  
  
- Un tipo derivado puede reemplazar a un método virtual heredado. El método de reemplazo proporciona una nueva definición del método que se invocará según el tipo del valor en tiempo de ejecución y no el tipo de la variable conocido en tiempo de compilación. Un método puede invalidar un método virtual únicamente si el método virtual no está marcado como `final` y el nuevo método es, al menos, tan accesible como el método virtual.  
  
## <a name="see-also"></a>Vea también

- [Explorador de API de .NET](/dotnet/api)
- [Common Language Runtime](../clr.md)
- [Conversión de tipos en .NET](type-conversion.md)
