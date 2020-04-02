---
title: Independencia del lenguaje y componentes independientes del lenguaje
description: Obtenga información sobre cómo puede desarrollar en uno de los muchos lenguajes admitidos en .NET, como C#, C++/CLI, F#, IronPython, VB, Visual COBOL y PowerShell.
ms.date: 07/22/2016
dev_langs:
- csharp
- vb
ms.technology: dotnet-standard
ms.assetid: 2dbed1bc-86f5-43cd-9a57-adbb1c5efba4
ms.openlocfilehash: 03751fa3758c239cb9eea5fe826dff66c1c1605b
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249583"
---
# <a name="language-independence-and-language-independent-components"></a>Independencia del lenguaje y componentes independientes del lenguaje

.NET es independiente del lenguaje. Esto significa que, como desarrollador, puede desarrollar en uno de los muchos lenguajes que tienen como destino las implementaciones de .NET, como C#, F# y Visual Basic. Puede tener acceso a los tipos y miembros de bibliotecas de clases desarrollados para implementaciones de .NET sin tener que conocer el lenguaje en el que se escribieron originalmente y sin tener que seguir las convenciones del lenguaje original. Si es un desarrollador de componentes, puede tener acceso al componente desde cualquier aplicación .NET independientemente de su lenguaje.

> [!NOTE]
> La primera parte de este artículo describe la creación de componentes independientes del lenguaje; es decir, los componentes que pueden usarse en aplicaciones escritas en cualquier lenguaje. También puede crear una aplicación o componente únicos de código fuente escrito en varios lenguajes; consulte [Interoperabilidad entre lenguajes](#cross-language-interoperability) en la segunda parte de este artículo.

Para que los objetos puedan tener una interacción total con otros objetos escritos en cualquier lenguaje, estos objetos solo deben exponer a los llamadores las características que son comunes a todos los lenguajes. Este conjunto común de características se define mediante Common Language Specification (CLS), que es un conjunto de reglas que se aplican a los ensamblados generados. Common Language Specification se define en el apartado I, cláusulas 7 a 11 del [estándar ECMA-335: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm).

Si el componente se ajusta a Common Language Specification, existe la garantía de que será conforme a CLS y que será accesible desde el código de un ensamblado escrito en cualquier lenguaje de programación que admita CLS. Para determinar si el componente se ajusta o no a Common Language Specification en tiempo de compilación, puede aplicar el atributo [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) en el código fuente. Para obtener más información, consulte [CLSCompliantAttribute (Atributo)](#the-clscompliantattribute-attribute).

En este artículo:

* [Reglas de conformidad con CLS](#cls-compliance-rules)

  * [Signaturas de tipos y miembros de tipo](#types-and-type-member-signatures)

  * [Convenciones de nomenclatura](#naming-conventions)

  * [Conversión de tipos](#type-conversion)

  * [Matrices](#arrays)

  * [Interfaces](#interfaces)

  * [Enumeraciones](#enumerations)

  * [Miembros de tipos en general](#type-members-in-general)

  * [Accesibilidad de miembros](#member-accessibility)

  * [Miembros y tipos genéricos](#generic-types-and-members)

  * [Constructores](#constructors)

  * [Propiedades](#properties)

  * [Eventos](#events)

  * [Sobrecargas](#overloads)

  * [Excepciones](#exceptions)

  * [Atributos](#attributes)

* [CLSCompliantAttribute (Atributo)](#the-clscompliantattribute-attribute)

* [Interoperabilidad entre lenguajes](#cross-language-interoperability)

## <a name="cls-compliance-rules"></a>Reglas de conformidad con CLS

En esta sección se explican las reglas para crear un componente conforme a CLS. Para obtener una lista completa de las normas, vea el apartado I, cláusula 11 del [estándar ECMA-335: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm).

> [!NOTE]
> Common Language Specification describe en cada regla la conformidad con CLS en referencia a los consumidores (desarrolladores que acceden mediante programación a un componente que es conforme a CLS), los marcos (desarrolladores que usan un compilador de lenguaje para crear bibliotecas conformes a CLS) y los extensores (desarrolladores que crean una herramienta, como un compilador de lenguaje o un analizador de código, que crea componentes conformes a CLS). Este artículo se centra en las reglas que se aplican a los marcos. Pero observe que algunas de las reglas que se aplican a los extensores también se pueden aplicar a los ensamblados que se crean mediante [Reflection.Emit](xref:System.Reflection.Emit).

Para diseñar un componente que sea independiente del lenguaje, solo tiene que aplicar las reglas de conformidad con CLS a la interfaz pública del componente. La implementación privada no tiene que ajustarse a la especificación.

> [!IMPORTANT]
> Las reglas de conformidad con CLS solo se aplican a la interfaz pública de un componente, y no a su implementación privada.

Por ejemplo, los números enteros sin signo distintos de [Byte](xref:System.Byte) no son conformes a CLS. Dado que la clase `Person` del siguiente ejemplo expone una propiedad `Age` del tipo [UInt16](xref:System.UInt16), el código siguiente desencadena una advertencia del compilador.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person
{
   private UInt16 personAge = 0;

   public UInt16 Age
   { get { return personAge; } }
}
// The attempt to compile the example displays the following compiler warning:
//    Public1.cs(10,18): warning CS3003: Type of 'Person.Age' is not CLS-compliant
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Person
   Private personAge As UInt16

   Public ReadOnly Property Age As UInt16
      Get
         Return personAge
      End Get
   End Property
End Class
' The attempt to compile the example displays the following compiler warning:
'    Public1.vb(9) : warning BC40027: Return type of function 'Age' is not CLS-compliant.
'
'       Public ReadOnly Property Age As UInt16
'                                ~~~
```

Para hacer que la clase Person sea conforme a CLS, puede cambiar el tipo de la propiedad `Age` de `UInt16` a [Int16](xref:System.Int16), que es un entero de 16 bits con signo conforme a CLS. No es necesario que cambie el tipo del campo privado `personAge`.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person
{
   private Int16 personAge = 0;

   public Int16 Age
   { get { return personAge; } }
}
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Person
   Private personAge As UInt16

   Public ReadOnly Property Age As Int16
      Get
         Return CType(personAge, Int16)
      End Get
   End Property
End Class
```

Las interfaces públicas de una biblioteca se componen de los elementos siguientes:

* Definiciones de clases públicas.

* Definiciones de los miembros públicos de las clases públicas y de los miembros accesibles por las clases derivadas (es decir, miembros protegidos).

* Parámetros y tipos devueltos de los métodos públicos de las clases públicas y parámetros y tipos devueltos de los métodos accesibles por las clases derivadas.

Las reglas de conformidad con CLS se muestran en la tabla siguiente. El texto de las normas se toma literalmente del [estándar ECMA-335: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm), Copyright de 2012 de Ecma International. En las secciones siguientes encontrará información más detallada sobre estas reglas.

Categoría | Vea | Regla | Número de regla
-------- | --- | ---- | -----------
Accesibilidad | [Accesibilidad de miembros](#member-accessibility) | Cuando se reemplacen métodos heredados, no debe modificarse la accesibilidad, excepto cuando se reemplace un método heredado de un ensamblado diferente cuya accesibilidad sea `family-or-assembly`. En este caso, el reemplazo debe tener accesibilidad `family`. | 10
Accesibilidad | [Accesibilidad de miembros](#member-accessibility) | La visibilidad y accesibilidad de los tipos y miembros se establecerá de modo que los tipos de la signatura de cualquier miembro sean visibles y accesibles siempre que el propio miembro sea visible y accesible. Por ejemplo, un método público que sea visible fuera del ensamblado no debe tener ningún argumento cuyo tipo solamente sea visible en el interior del ensamblado. La visibilidad y la accesibilidad de los tipos que conforman un tipo genérico con instancias que se utilice en la signatura de cualquier miembro deben establecerse de forma que serán visibles y accesibles siempre que el propio miembro sea visible y accesible. Por ejemplo, un tipo genérico con instancias que esté presente en la signatura de un miembro que sea visible fuera del ensamblado no debe tener ningún argumento genérico cuyo tipo solamente sea visible en el interior del ensamblado. | 12
Matrices | [Matrices](#arrays) | Las matrices deben tener elementos con un tipo conforme a CLS y los límites inferiores de todas las dimensiones de la matriz deben ser iguales a cero. Para distinguir entre sobrecargas, solo se tendrá en cuenta el hecho de que el elemento es una matriz y el tipo de elementos de la matriz. Cuando la sobrecarga se basa en dos o varios tipos de matrices, los tipos de elementos deben ser tipos con nombre. | 16
Atributos | [Atributos](#attributes) | Los atributos deben ser del tipo [System.Attribute](xref:System.Attribute) o heredarse de este. | 41
Atributos | [Atributos](#attributes) | CLS solo permite un subconjunto de codificaciones de atributos personalizados. Los únicos tipos que deben aparecer en estas codificaciones son (vea el apartado IV): [System.Type](xref:System.Type), [System.String](xref:System.String), [System.Char](xref:System.Char), [System.Boolean](xref:System.Boolean), [System.Byte](xref:System.Byte), [System.Int16](xref:System.Int16), [System.Int32](xref:System.Int32), [System.Int64](xref:System.Int64), [System.Single](xref:System.Single), [System.Double](xref:System.Double) y cualquier tipo de enumeración basada en un tipo entero base compatible con CLS. | 34
Atributos | [Atributos](#attributes) | CLS no admite modificadores obligatorios que sean visibles públicamente (`modreq`, vea el Apartado II), pero sí admite modificadores opcionales (`modopt`, vea el apartado II) que no comprenda. | 35
Constructores | [Constructores](#constructors) | Un constructor de objetos debe llamar a un constructor de instancias de su clase base antes de que tenga lugar cualquier acceso a los datos de instancia heredados. (Esto no se aplica a los tipos de valor, que no necesitan constructores.)  | 21
Constructores | [Constructores](#constructors) | No debe llamarse a los constructores de objetos excepto durante la creación de un objeto y no podrá iniciarse dos veces un objeto. | 22
Enumeraciones | [Enumeraciones](#enumerations) | El tipo subyacente de una enumeración debe ser un tipo de entero integrado en CLS, el nombre del campo debe ser “value__” y dicho campo debe marcarse como `RTSpecialName`. |  7
Enumeraciones | [Enumeraciones](#enumerations) | Hay dos tipos distintos de enumeraciones, que se indican mediante la presencia o ausencia del atributo personalizado [System.FlagsAttribute](xref:System.FlagsAttribute) (consulte la biblioteca del apartado IV). Uno representa valores enteros con nombre; el otro representa los marcadores de bit con nombre que se pueden combinar para generar un valor sin nombre. El valor de `enum` no se limita a los valores especificados. |  8
Enumeraciones | [Enumeraciones](#enumerations) | Los campos estáticos literales de una enumeración deben contener el tipo de la propia enumeración. |  9
Events | [Eventos](#events) | Los métodos que implementen un evento se marcarán como `SpecialName` en los metadatos. |29
Events | [Eventos](#events) | La accesibilidad de un evento y sus descriptores de acceso será idéntica. |30
Events | [Eventos](#events) | Los métodos `add` y `remove` de un evento deben estar presentes o ausentes a la vez. |31
Events | [Eventos](#events) | Los métodos `add` y `remove` de un evento deben tomar un parámetro cuyo tipo defina el tipo del evento, y ese tipo debe derivarse de [System.Delegate](xref:System.Delegate). |32
Events | [Eventos](#events) | Los eventos deben adherirse a un patrón de asignación de nombres concreto. En las comparaciones de nombres correspondientes se omitirá el atributo SpecialName mencionado en la regla 29 de CLS y se seguirán las reglas del identificador.  |33
Excepciones | [Excepciones](#exceptions) | Los objetos que se inicien deberán ser de tipo [System.Exception](xref:System.Exception) o de un tipo que herede de él. No obstante, los métodos conformes a CLS no necesitan bloquear la propagación de otros tipos de excepciones. | 40
General | [Reglas de conformidad con CLS](#cls-compliance-rules) | Las reglas de CLS solo se aplican a las partes de los tipos que son accesibles o visibles desde fuera del ensamblado de definición. | 1
General | [Reglas de conformidad con CLS](#cls-compliance-rules) | Los miembros de tipos no conformes con CLS no deben marcarse como conformes con CLS. | 2
Genéricos | [Miembros y tipos genéricos](#generic-types-and-members) | Los tipos anidados deben tener, como mínimo, el mismo número de parámetros genéricos que el tipo envolvente. Los parámetros genéricos de un tipo anidado se corresponden por posición con los parámetros genéricos del tipo contenedor.  | 42
Genéricos | [Miembros y tipos genéricos](#generic-types-and-members) | El nombre de un tipo genérico debe codificar el número de parámetros de tipo declarados en el tipo no anidado o que se acaban de introducir en el tipo, si este está anidado, según las reglas definidas anteriormente. | 43
Genéricos | [Miembros y tipos genéricos](#generic-types-and-members) | Todo tipo genérico deberá volver a declarar restricciones suficientes como para garantizar que cualquier restricción de las interfaces o del tipo base se vea satisfecha por las restricciones del tipo genérico. | 44
Genéricos | [Miembros y tipos genéricos](#generic-types-and-members) | Los tipos que se utilicen como restricciones en parámetros genéricos deben ser conformes a CLS. | 45
Genéricos | [Miembros y tipos genéricos](#generic-types-and-members) | Se entiende que la visibilidad y accesibilidad de los miembros (incluidos los tipos anidados) de un tipo genérico con instancias deben quedar restringidas al ámbito específico de la creación de instancias, y no a la declaración de tipos genéricos en general. Suponiendo que esto sea cierto, se seguirán aplicando las especificaciones de accesibilidad y visibilidad de la regla 12 de CLS. | 46
Genéricos | [Miembros y tipos genéricos](#generic-types-and-members) | Cada método genérico abstracto o virtual deberá tener su propia implementación concreta (no abstracta) predeterminada | 47
Interfaces | [Interfaces](#interfaces) | Las interfaces conformes a CLS no deben requerir la definición de métodos no conformes a CLS para su implementación. | 18
Interfaces | [Interfaces](#interfaces) | Las interfaces conformes a CLS no pueden definir métodos estáticos ni pueden definir campos. | 19
Miembros | [Miembros de tipos en general](#type-members-in-general) | Los campos y métodos static globales no son conformes a CLS. | 36
Miembros | -- | El valor de un estático literal se especifica mediante el uso de metadatos de inicialización de campos. Un literal conforme a CLS debe tener un valor especificado en los metadatos de inicialización de campos que sea exactamente del mismo tipo que el literal (o el tipo subyacente, si el literal es `enum`). | 13
Miembros | [Miembros de tipos en general](#type-members-in-general) | La restricción vararg no forma parte de CLS y la única convención de llamada admitida por CLS es la convención de llamada administrada estándar. | 15
Convenciones de nomenclatura | [Convenciones de nomenclatura](#naming-conventions) | Los ensamblados seguirán las directrices del anexo 7 del informe técnico 15 del estándar Unicode 3.0, que rige el conjunto de caracteres permitidos que pueden usarse como iniciales e incluirse en los identificadores. Estas directrices están disponibles en línea en [Formularios de normalización Unicode](https://www.unicode.org/unicode/reports/tr15/tr15-18.html). Los identificadores deben aparecer en el formato canónico definido por el Formulario C de normalización Unicode. En aras de la conformidad con CLS, dos identificadores se considerarán iguales si sus asignaciones de minúsculas (tal y como se especificó en las asignaciones unívocas de minúsculas de Unicode en las que no se tiene en cuenta la configuración regional) son iguales. Es decir, para que dos identificadores se consideren diferentes según CLS, tendrán que diferenciarse en algo más que en el uso de mayúsculas y minúsculas. Pero para invalidar una definición heredada, CLI requiere que se use la codificación exacta de la declaración original. | 4
Sobrecarga | [Convenciones de nomenclatura](#naming-conventions) | Todos los nombres especificados en un ámbito conforme a CLS deben ser distintos independientemente del tipo, salvo en los casos en los que los nombres sean idénticos y se resuelvan mediante sobrecarga. Es decir, mientras CTS permite que un tipo único use el mismo nombre para un método y un campo, CLS no. | 5
Sobrecarga | [Convenciones de nomenclatura](#naming-conventions) | Los campos y los tipos anidados deben distinguirse únicamente por la comparación de identificadores, aunque CTS permita que se distingan signaturas diferentes. Los métodos, las propiedades y los eventos que tengan el mismo nombre (por comparación de identificadores) deben distinguirse por algo más que el tipo de valor devuelto, excepto según lo especificado en la regla 39 de CLS | 6
Sobrecarga | [Sobrecargas](#overloads) | Solo las propiedades y los métodos se pueden sobrecargar. | 37
Sobrecarga | [Sobrecargas](#overloads) |Las propiedades y los métodos se pueden sobrecargar únicamente en función del número y los tipos de sus parámetros, excepto los operadores de conversión denominados `op_Implicit` y `op_Explicit`, que también se pueden sobrecargar en función del tipo de valor devuelto. | 38
Sobrecarga | -- | Si dos o más de los métodos conformes a CLS declarados en un tipo tienen el mismo nombre y, en un conjunto específico de instancias de tipos, tienen los mismos tipos de valor devuelto y parámetros, todos estos métodos serán semánticamente equivalentes en esas instancias de tipos. | 48
Propiedades | [Propiedades](#properties) | Los métodos que implementan los métodos de captador y establecedor de una propiedad deben estar marcados con `SpecialName` en los metadatos. | 24
Propiedades | [Propiedades](#properties) | Todos los descriptores de acceso de una propiedad deben ser estáticos, virtuales o de instancia. | 26
Propiedades | [Propiedades](#properties) | El tipo de una propiedad es el tipo de valor devuelto del método captador y el tipo del último argumento del método establecedor. Los tipos de los parámetros de la propiedad deben ser los tipos de los parámetros del método captador y los tipos de todos los parámetros del método establecedor, excepto el último. Todos estos tipos deben ser conformes a CLS y no pueden ser punteros administrados (es decir, no deben pasarse por referencia). | 27
Propiedades | [Propiedades](#properties) | Las propiedades deben ajustarse a un patrón de asignación de nombres concreto. En las comparaciones de nombres correspondientes se omitirá el atributo `SpecialName` mencionado en la regla 24 de CLS y se seguirán las reglas del identificador. Una propiedad tendrá un método de captador, un método de establecedor o ambos. | 28
Conversión de tipos | [Conversión de tipos](#type-conversion) | Si se proporciona op_Implicit u op_Explicit, deben darse medios alternativos para realizar la conversión. | 39
Tipos | [Signaturas de tipos y miembros de tipo](#types-and-type-member-signatures) | Los tipos de valor a los que se les ha aplicado la conversión boxing no son conformes a CLS. | 3
Tipos | [Signaturas de tipos y miembros de tipo](#types-and-type-member-signatures) | Todos los tipos que aparecen en una signatura deben ser conformes a CLS. Todos los tipos que forman un tipo genérico con instancias deben ser conformes a CLS. | 11
Tipos | [Signaturas de tipos y miembros de tipo](#types-and-type-member-signatures) | Las referencias a tipos no son conformes a CLS. | 14
Tipos | [Signaturas de tipos y miembros de tipo](#types-and-type-member-signatures) | Los tipos de puntero no administrados no son conformes a CLS. | 17
Tipos | [Signaturas de tipos y miembros de tipo](#types-and-type-member-signatures) | Las interfaces, los tipos de valor y las clases conformes a CLS no deben requerir la implementación de miembros no conformes a CLS | 20
Tipos | [Signaturas de tipos y miembros de tipo](#types-and-type-member-signatures) | [System.Object](xref:System.Object) es conforme a CLS. Cualquier otra clase conforme a CLS se heredará de una clase conforme a CLS. | 23

### <a name="types-and-type-member-signatures"></a>Signaturas de tipos y miembros de tipo

El tipo [System.Object](xref:System.Object) es conforme a CLS y es el tipo base de todos los tipos de objetos del sistema de tipos de .NET Framework. La herencia de .NET Framework es implícita (por ejemplo, la clase [String](xref:System.String) hereda implícitamente de la clase `Object`) o explícita (por ejemplo, la clase [CultureNotFoundException](xref:System.Globalization.CultureNotFoundException) hereda explícitamente de la clase [ArgumentException](xref:System.ArgumentException), que a su vez hereda también explícitamente de la clase [Exception](xref:System.Exception)). Para que un tipo derivado sea conforme a CLS, su tipo base también debe ser conforme a CLS.

En el ejemplo siguiente se muestra un tipo derivado cuyo tipo base no es conforme a CLS. En el ejemplo, se define una clase base `Counter` que usa un entero de 32 bits sin signo como contador. Dado que la clase proporciona la funcionalidad de contador ajustando un entero sin signo, la clase se marca como no conforme a CLS. Como resultado, la clase derivada, `NonZeroCounter`, tampoco es conforme a CLS.

```csharp
using System;

[assembly: CLSCompliant(true)]

[CLSCompliant(false)]
public class Counter
{
   UInt32 ctr;

   public Counter()
   {
      ctr = 0;
   }

   protected Counter(UInt32 ctr)
   {
      this.ctr = ctr;
   }

   public override string ToString()
   {
      return $"{ctr}). ";
   }

   public UInt32 Value
   {
      get { return ctr; }
   }

   public void Increment()
   {
      ctr += (uint) 1;
   }
}

public class NonZeroCounter : Counter
{
   public NonZeroCounter(int startIndex) : this((uint) startIndex)
   {
   }

   private NonZeroCounter(UInt32 startIndex) : base(startIndex)
   {
   }
}
// Compilation produces a compiler warning like the following:
//    Type3.cs(37,14): warning CS3009: 'NonZeroCounter': base type 'Counter' is not
//            CLS-compliant
//    Type3.cs(7,14): (Location of symbol related to previous warning)
```

```vb
<Assembly: CLSCompliant(True)>

<CLSCompliant(False)> _
Public Class Counter
   Dim ctr As UInt32

   Public Sub New
      ctr = 0
   End Sub

   Protected Sub New(ctr As UInt32)
      ctr = ctr
   End Sub

   Public Overrides Function ToString() As String
      Return $"{ctr}). "
   End Function

   Public ReadOnly Property Value As UInt32
      Get
         Return ctr
      End Get
   End Property

   Public Sub Increment()
      ctr += CType(1, UInt32)
   End Sub
End Class

Public Class NonZeroCounter : Inherits Counter
   Public Sub New(startIndex As Integer)
      MyClass.New(CType(startIndex, UInt32))
   End Sub

   Private Sub New(startIndex As UInt32)
      MyBase.New(CType(startIndex, UInt32))
   End Sub
End Class
' Compilation produces a compiler warning like the following:
'    Type3.vb(34) : warning BC40026: 'NonZeroCounter' is not CLS-compliant
'    because it derives from 'Counter', which is not CLS-compliant.
'
'    Public Class NonZeroCounter : Inherits Counter
'                 ~~~~~~~~~~~~~~
```

Todos los tipos que aparecen en las signaturas de miembros, incluidos los tipos de propiedades y los tipos de valores devueltos de un método, deben ser conformes a CLS. Además, en el caso de los tipos genéricos:

* Todos los tipos que forman un tipo genérico con instancias deben ser conformes a CLS.

* Todos los tipos que se utilizan como restricciones en parámetros genéricos deben ser conformes a CLS.

El [sistema de tipos común](common-type-system.md) de .NET incluye varios tipos integrados que se admiten directamente en Common Language Runtime y que se codifican de forma especial en los metadatos de un ensamblado. De estos tipos intrínsecos, los tipos enumerados en la tabla siguiente son conformes a CLS.

Tipo conforme a CLS | Descripción
------------------ | -----------
[Byte](xref:System.Byte) | Entero de 8 bits sin signo
[Int16](xref:System.Int16) | Entero de 16 bits con signo
[Int32](xref:System.Int32) | Entero de 32 bits con signo
[Int64](xref:System.Int64) | Entero de 64 bits con signo
[Single](xref:System.Single) | Valor de punto flotante de precisión sencilla
[Double](xref:System.Double) | Valor de punto flotante de precisión doble
[Boolean](xref:System.Boolean) | tipo de valor true o false
[Char](xref:System.Char) | Unidad de código con la codificación UTF-16
[Decimal](xref:System.Decimal) | Número decimal de punto no flotante
[IntPtr](xref:System.IntPtr) | Puntero o identificador de un tamaño definido por la plataforma
[String](xref:System.String) | Colección de cero, uno o varios objetos Char

Los tipos intrínsecos enumerados en la tabla siguiente no son conformes a CLS.

Tipo no conforme | Descripción | Alternativa conforme a CLS
------------------ | ----------- | -------------------------
[SByte](xref:System.SByte) | Tipo de datos enteros de 8 bits con signo | [Int16](xref:System.Int16)
[UInt16](xref:System.UInt16) | Entero de 16 bits sin signo | [Int32](xref:System.Int32)
[UInt32](xref:System.UInt32) | Entero de 32 bits sin signo | [Int64](xref:System.Int64)
[UInt64](xref:System.UInt64) | Entero de 64 bits sin signo | [Int64](xref:System.Int64) (se puede desbordar), [BigInteger](xref:System.Numerics.BigInteger) o [Double](xref:System.Double)
[UIntPtr](xref:System.UIntPtr) | Puntero o identificador sin signo | [IntPtr](xref:System.IntPtr)

La biblioteca de clases de .NET Framework o cualquier otra biblioteca de clases puede incluir otros tipos que no sean conformes a CLS; por ejemplo:

* Tipos de valor a los que se les ha aplicado la conversión boxing. En el siguiente ejemplo de C#, se crea una clase con una propiedad pública de tipo `int`* denominada `Value`. Dado que `int`* es un tipo de valor al que se le ha aplicado la conversión boxing, el compilador lo marca como no conforme a CLS.

```csharp
using System;

[assembly:CLSCompliant(true)]

public unsafe class TestClass
{
   private int* val;

   public TestClass(int number)
   {
      val = (int*) number;
   }

   public int* Value {
      get { return val; }
   }
}
// The compiler generates the following output when compiling this example:
//        warning CS3003: Type of 'TestClass.Value' is not CLS-compliant
```

* Referencias con establecimiento de tipos, que son construcciones especiales que contienen una referencia a un objeto y una referencia a un tipo.

Si un tipo no es conforme a CLS, debe aplicar el atributo [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) con un parámetro *isCompliant* con un valor de `false` en él. Para obtener más información, consulte la sección [CLSCompliantAttribute (Atributo)](#the-clscompliantattribute-attribute).

En el ejemplo siguiente se muestra el problema de la conformidad con CLS en la creación de instancias de tipos genéricos y signaturas de métodos. En este ejemplo, se define una clase `InvoiceItem` con una propiedad de tipo [UInt32](xref:System.UInt32), una propiedad de tipo [Nullable(Of UInt32)](xref:System.Nullable%601) y un constructor con parámetros de tipo `UInt32` y `Nullable(Of UInt32)`. Cuando intente compilar este ejemplo, aparecerán cuatro advertencias del compilador.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class InvoiceItem
{
   private uint invId = 0;
   private uint itemId = 0;
   private Nullable<uint> qty;

   public InvoiceItem(uint sku, Nullable<uint> quantity)
   {
      itemId = sku;
      qty = quantity;
   }

   public Nullable<uint> Quantity
   {
      get { return qty; }
      set { qty = value; }
   }

   public uint InvoiceId
   {
      get { return invId; }
      set { invId = value; }
   }
}
// The attempt to compile the example displays the following output:
//    Type1.cs(13,23): warning CS3001: Argument type 'uint' is not CLS-compliant
//    Type1.cs(13,33): warning CS3001: Argument type 'uint?' is not CLS-compliant
//    Type1.cs(19,26): warning CS3003: Type of 'InvoiceItem.Quantity' is not CLS-compliant
//    Type1.cs(25,16): warning CS3003: Type of 'InvoiceItem.InvoiceId' is not CLS-compliant
```

```vb
<Assembly: CLSCompliant(True)>

Public Class InvoiceItem

   Private invId As UInteger = 0
   Private itemId As UInteger = 0
   Private qty AS Nullable(Of UInteger)

   Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
      itemId = sku
      qty = quantity
   End Sub

   Public Property Quantity As Nullable(Of UInteger)
      Get
         Return qty
      End Get
      Set
         qty = value
      End Set
   End Property

   Public Property InvoiceId As UInteger
      Get
         Return invId
      End Get
      Set
         invId = value
      End Set
   End Property
End Class
' The attempt to compile the example displays output similar to the following:
'    Type1.vb(13) : warning BC40028: Type of parameter 'sku' is not CLS-compliant.
'
'       Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
'                      ~~~
'    Type1.vb(13) : warning BC40041: Type 'UInteger' is not CLS-compliant.
'
'       Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
'                                                               ~~~~~~~~
'    Type1.vb(18) : warning BC40041: Type 'UInteger' is not CLS-compliant.
'
'       Public Property Quantity As Nullable(Of UInteger)
'                                               ~~~~~~~~
'    Type1.vb(27) : warning BC40027: Return type of function 'InvoiceId' is not CLS-compliant.
'
'       Public Property InvoiceId As UInteger
```

Para eliminar las advertencias del compilador, reemplace los tipos no conformes a CLS de la interfaz pública de `InvoiceItem` por tipos conformes:

```csharp
using System;

[assembly: CLSCompliant(true)]

public class InvoiceItem
{
   private uint invId = 0;
   private uint itemId = 0;
   private Nullable<int> qty;

   public InvoiceItem(int sku, Nullable<int> quantity)
   {
      if (sku <= 0)
         throw new ArgumentOutOfRangeException("The item number is zero or negative.");
      itemId = (uint) sku;

      qty = quantity;
   }

   public Nullable<int> Quantity
   {
      get { return qty; }
      set { qty = value; }
   }

   public int InvoiceId
   {
      get { return (int) invId; }
      set {
         if (value <= 0)
            throw new ArgumentOutOfRangeException("The invoice number is zero or negative.");
         invId = (uint) value; }
   }
}
```

```vb
Assembly: CLSCompliant(True)>

Public Class InvoiceItem

   Private invId As UInteger = 0
   Private itemId As UInteger = 0
   Private qty AS Nullable(Of Integer)

   Public Sub New(sku As Integer, quantity As Nullable(Of Integer))
      If sku <= 0 Then
         Throw New ArgumentOutOfRangeException("The item number is zero or negative.")
      End If
      itemId = CUInt(sku)
      qty = quantity
   End Sub

   Public Property Quantity As Nullable(Of Integer)
      Get
         Return qty
      End Get
      Set
         qty = value
      End Set
   End Property

   Public Property InvoiceId As Integer
      Get
         Return CInt(invId)
      End Get
      Set
         invId = CUInt(value)
      End Set
   End Property
End Class
```

Además de los tipos específicos indicados, algunas categorías de tipos no son conformes a CLS. Entre estas categorías se incluyen tipos de punteros no administrados y tipos de punteros de función. En el ejemplo siguiente se genera una advertencia del compilador, ya que se utiliza un puntero a un entero para crear una matriz de enteros.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ArrayHelper
{
   unsafe public static Array CreateInstance(Type type, int* ptr, int items)
   {
      Array arr = Array.CreateInstance(type, items);
      int* addr = ptr;
      for (int ctr = 0; ctr < items; ctr++) {
          int value = *addr;
          arr.SetValue(value, ctr);
          addr++;
      }
      return arr;
   }
}
// The attempt to compile this example displays the following output:
//    UnmanagedPtr1.cs(8,57): warning CS3001: Argument type 'int*' is not CLS-compliant
```

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ArrayHelper
{
   unsafe public static Array CreateInstance(Type type, int* ptr, int items)
   {
      Array arr = Array.CreateInstance(type, items);
      int* addr = ptr;
      for (int ctr = 0; ctr < items; ctr++) {
          int value = *addr;
          arr.SetValue(value, ctr);
          addr++;
      }
      return arr;
   }
}
// The attempt to compile this example displays the following output:
//    UnmanagedPtr1.cs(8,57): warning CS3001: Argument type 'int*' is not CLS-compliant
```

En las clases abstractas conformes a CLS (es decir, clases marcadas como `abstract` en C#), todos los miembros de dichas clases deben ser también conformes a CLS.

### <a name="naming-conventions"></a>Convenciones de nomenclatura

Dado que algunos lenguajes de programación distinguen entre mayúsculas y minúsculas, los identificadores (como los nombres de espacios de nombres, los tipos y los miembros) deben tener otro elemento distintivo aparte del uso de mayúsculas. Dos identificadores se consideran equivalentes si sus asignaciones de minúsculas son iguales. En el ejemplo de C# siguiente, se definen dos clases públicas: `Person` y `person`. Como solo se distinguen por el uso de mayúsculas, el compilador de C# las marca como no conformes a CLS.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person : person
{

}

public class person
{

}
// Compilation produces a compiler warning like the following:
//    Naming1.cs(11,14): warning CS3005: Identifier 'person' differing
//                       only in case is not CLS-compliant
//    Naming1.cs(6,14): (Location of symbol related to previous warning)
```

Los identificadores de los lenguajes de programación, como los nombres de los espacios de nombres, tipos y miembros, deben ajustarse al [Estándar Unicode 3.0, Informe técnico 15, Anexo 7](https://www.unicode.org/reports/tr15/tr15-18.html). Esto significa que:

* El primer carácter de un identificador puede ser cualquier letra en mayúscula, letra en minúscula, letra de inicial en mayúscula, letra modificadora, otra letra o número de letra. Para obtener información acerca de las categorías de caracteres Unicode, consulte la enumeración [System.Globalization.UnicodeCategory](xref:System.Globalization.UnicodeCategory).

* Los caracteres siguientes pueden proceder de cualquier categoría cuando funcionan como primer carácter y también pueden incluir marcas no espaciadas, marcas de combinación de espaciado, números decimales, puntuaciones de conexión y códigos de formato.

Antes de comparar los identificadores, debe filtrar los códigos de formato y convertir los identificadores a la forma de normalización Unicode C, ya que un mismo carácter se puede representar mediante diferentes unidades de código UTF-16. Las secuencias de caracteres que producen las mismas unidades de código en la forma de normalización Unicode C no son conformes a CLS. En el ejemplo siguiente se define una propiedad llamada `Å`, que se compone del carácter SIGNO DE ANGSTROM (U+212B) y una segunda propiedad llamada `Å`, que se compone de la LETRA MAYÚSCULA A LATINA CON UN ANILLO ENCIMA (U+00C5). El compilador de C# marca el código fuente como no conforme a CLS.

```csharp
public class Size
{
   private double a1;
   private double a2;

   public double Å
   {
       get { return a1; }
       set { a1 = value; }
   }

   public double Å
   {
       get { return a2; }
       set { a2 = value; }
   }
}
// Compilation produces a compiler warning like the following:
//    Naming2a.cs(16,18): warning CS3005: Identifier 'Size.Å' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(10,18): (Location of symbol related to previous warning)
//    Naming2a.cs(18,8): warning CS3005: Identifier 'Size.Å.get' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(12,8): (Location of symbol related to previous warning)
//    Naming2a.cs(19,8): warning CS3005: Identifier 'Size.Å.set' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(13,8): (Location of symbol related to previous warning)
```

```vb
<Assembly: CLSCompliant(True)>
Public Class Size
   Private a1 As Double
   Private a2 As Double

   Public Property Å As Double
       Get
          Return a1
       End Get
       Set
          a1 = value
       End Set
   End Property

   Public Property Å As Double
       Get
          Return a2
       End Get
       Set
          a2 = value
       End Set
   End Property
End Class
' Compilation produces a compiler warning like the following:
'    Naming1.vb(9) : error BC30269: 'Public Property Å As Double' has multiple definitions
'     with identical signatures.
'
'       Public Property Å As Double
'                       ~
```

Los nombres de miembros con un ámbito determinado (como los espacios de nombres de un ensamblado, los tipos de un espacio de nombres o los miembros de un tipo) deben ser únicos, excepto los nombres que se resuelven a través de la sobrecarga. Este requisito es más estricto que el del sistema de tipos comunes, que permite a varios miembros de un ámbito tener nombres idénticos siempre que sean diferentes tipos de miembros (por ejemplo, que uno sea un método y otro, un campo). En particular, en el caso de los miembros de tipo:

* Los campos y los tipos anidados solo se distinguen por el nombre.

* Los métodos, las propiedades y los eventos que tienen el mismo nombre deben distinguirse por algo más que el tipo de valor devuelto.

En el ejemplo siguiente se muestra el requisito que establece que los nombres de miembro deben ser únicos dentro de su ámbito. En este ejemplo se define una clase denominada `Converter`, que incluye cuatro miembros denominados `Conversion`. Tres son métodos y uno es una propiedad. El método que incluye un parámetro `Int64` recibe un nombre único, pero no ocurre lo mismo con los dos métodos que tienen un parámetro `Int32`, ya que el valor devuelto no se considera parte de la signatura del miembro. La propiedad `Conversion` también infringe este requisito, ya que las propiedades no pueden tener el mismo nombre que los métodos sobrecargados.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Converter
{
   public double Conversion(int number)
   {
      return (double) number;
   }

   public float Conversion(int number)
   {
      return (float) number;
   }

   public double Conversion(long number)
   {
      return (double) number;
   }

   public bool Conversion
   {
      get { return true; }
   }
}
// Compilation produces a compiler error like the following:
//    Naming3.cs(13,17): error CS0111: Type 'Converter' already defines a member called
//            'Conversion' with the same parameter types
//    Naming3.cs(8,18): (Location of symbol related to previous error)
//    Naming3.cs(23,16): error CS0102: The type 'Converter' already contains a definition for
//            'Conversion'
//    Naming3.cs(8,18): (Location of symbol related to previous error)
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Converter
   Public Function Conversion(number As Integer) As Double
      Return CDbl(number)
   End Function

   Public Function Conversion(number As Integer) As Single
      Return CSng(number)
   End Function

   Public Function Conversion(number As Long) As Double
      Return CDbl(number)
   End Function

   Public ReadOnly Property Conversion As Boolean
      Get
         Return True
      End Get
   End Property
End Class
' Compilation produces a compiler error like the following:
'    Naming3.vb(8) : error BC30301: 'Public Function Conversion(number As Integer) As Double'
'                    and 'Public Function Conversion(number As Integer) As Single' cannot
'                    overload each other because they differ only by return types.
'
'       Public Function Conversion(number As Integer) As Double
'                       ~~~~~~~~~~
'    Naming3.vb(20) : error BC30260: 'Conversion' is already declared as 'Public Function
'                     Conversion(number As Integer) As Single' in this class.
'
'       Public ReadOnly Property Conversion As Boolean
'                                ~~~~~~~~~~
```

Todos los lenguajes contienen palabras claves únicas, de modo que los lenguajes dirigidos a Common Language Runtime también deben proporcionar un mecanismo para hacer referencia a identificadores (como nombres de tipo) que coincidan con las palabras clave. Por ejemplo, `case` es una palabra clave en C# y Visual Basic. Sin embargo, en el siguiente ejemplo de Visual Basic se elimina la ambigüedad entre una clase denominada `case` y la palabra clave `case` mediante llaves de apertura y cierre. De lo contrario, el ejemplo produciría el mensaje de error "Una palabra clave no es válida como identificador" y no se compilaría.

```vb
Public Class [case]
   Private _id As Guid
   Private name As String

   Public Sub New(name As String)
      _id = Guid.NewGuid()
      Me.name = name
   End Sub

   Public ReadOnly Property ClientName As String
      Get
         Return name
      End Get
   End Property
End Class
```

En el siguiente ejemplo de C# se crean instancias de la clase `case` usando el símbolo @ para eliminar la ambigüedad entre el identificador y la palabra clave del lenguaje. Sin él, el compilador de C# mostraría dos mensajes de error similares a los siguientes: "Se esperaba un tipo" y "'Término 'case' de expresión no válido".

```csharp
using System;

public class Example
{
   public static void Main()
   {
      @case c = new @case("John");
      Console.WriteLine(c.ClientName);
   }
}
```

### <a name="type-conversion"></a>Conversión de tipos

Common Language Specification define dos operadores de conversión:

* `op_Implicit`, que se utiliza en las conversiones de ampliación que no dan lugar a la pérdida de datos o de precisión. Por ejemplo, la estructura [Decimal](xref:System.Decimal) contiene un operador sobrecargado `op_Implicit` para convertir valores de tipos enteros y valores [Char](xref:System.Char) en valores `Decimal`.

* `op_Explicit`, que se utiliza en las conversiones de restricción que pueden producir una pérdida de magnitud (un valor se convierte en un valor que tiene un intervalo menor) o de precisión. Por ejemplo, la estructura `Decimal` contiene un operador sobrecargado `op_Explicit` para convertir los valores [Double](xref:System.Double) y [Single](xref:System.Single) en `Decimal`, y convertir los valores `Decimal` en los valores integrales`Double`, `Single` y `Char`.

Sin embargo, no todos los lenguajes admiten la sobrecarga de operadores o la definición de operadores personalizados. Si decide implementar estos operadores de conversión, debe proporcionar un mecanismo alternativo para realizar la conversión. Se recomienda proporcionar los métodos `From`Xxx y `To`Xxx.

En el ejemplo siguiente se definen conversiones implícitas y explícitas conformes a CLS. En este ejemplo, se crea una clase `UDouble` que representa un número de punto flotante con signo de precisión doble. En las conversiones implícitas, pasa de `UDouble` a `Double` y, en las conversiones explícitas, de `UDouble` a `Single`, de `Double` a `UDouble` y de `Single` a `UDouble`. También define un método `ToDouble` como alternativa al operador de conversión implícita y los métodos `ToSingle`, `FromDouble` y `FromSingle` como alternativas a los operadores de conversión explícitos.

```csharp
using System;

public struct UDouble
{
   private double number;

   public UDouble(double value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      number = value;
   }

   public UDouble(float value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      number = value;
   }

   public static readonly UDouble MinValue = (UDouble) 0.0;
   public static readonly UDouble MaxValue = (UDouble) Double.MaxValue;

   public static explicit operator Double(UDouble value)
   {
      return value.number;
   }

   public static implicit operator Single(UDouble value)
   {
      if (value.number > (double) Single.MaxValue)
         throw new InvalidCastException("A UDouble value is out of range of the Single type.");

      return (float) value.number;
   }

   public static explicit operator UDouble(double value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      return new UDouble(value);
   }

   public static implicit operator UDouble(float value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      return new UDouble(value);
   }

   public static Double ToDouble(UDouble value)
   {
      return (Double) value;
   }

   public static float ToSingle(UDouble value)
   {
      return (float) value;
   }

   public static UDouble FromDouble(double value)
   {
      return new UDouble(value);
   }

   public static UDouble FromSingle(float value)
   {
      return new UDouble(value);
   }
}
```

```vb
Public Structure UDouble
   Private number As Double

   Public Sub New(value As Double)
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      number = value
   End Sub

   Public Sub New(value As Single)
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      number = value
   End Sub

   Public Shared ReadOnly MinValue As UDouble = CType(0.0, UDouble)
   Public Shared ReadOnly MaxValue As UDouble = Double.MaxValue

   Public Shared Widening Operator CType(value As UDouble) As Double
      Return value.number
   End Operator

   Public Shared Narrowing Operator CType(value As UDouble) As Single
      If value.number > CDbl(Single.MaxValue) Then
         Throw New InvalidCastException("A UDouble value is out of range of the Single type.")
      End If
      Return CSng(value.number)
   End Operator

   Public Shared Narrowing Operator CType(value As Double) As UDouble
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      Return New UDouble(value)
   End Operator

   Public Shared Narrowing Operator CType(value As Single) As UDouble
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      Return New UDouble(value)
   End Operator

   Public Shared Function ToDouble(value As UDouble) As Double
      Return CType(value, Double)
   End Function

   Public Shared Function ToSingle(value As UDouble) As Single
      Return CType(value, Single)
   End Function

   Public Shared Function FromDouble(value As Double) As UDouble
      Return New UDouble(value)
   End Function

   Public Shared Function FromSingle(value As Single) As UDouble
      Return New UDouble(value)
   End Function
End Structure
```

### <a name="arrays"></a>Matrices

Las matrices conformes a CLS cumplen las reglas siguientes:

* Todas las dimensiones de una matriz deben tener un límite inferior igual a cero. En el ejemplo siguiente se crea una matriz no conforme a CLS cuyo límite inferior es uno. Observe que, a pesar de la presencia del atributo [CLSCompliantAttribute](xref:System.CLSCompliantAttribute), el compilador no detecta que la matriz devuelta por el método `Numbers.GetTenPrimes` no es conforme a CLS.

  ```csharp
  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static Array GetTenPrimes()
    {
        Array arr = Array.CreateInstance(typeof(Int32), new int[] {10}, new int[] {1});
        arr.SetValue(1, 1);
        arr.SetValue(2, 2);
        arr.SetValue(3, 3);
        arr.SetValue(5, 4);
        arr.SetValue(7, 5);
        arr.SetValue(11, 6);
        arr.SetValue(13, 7);
        arr.SetValue(17, 8);
        arr.SetValue(19, 9);
        arr.SetValue(23, 10);

        return arr;
    }
  }
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Class Numbers
     Public Shared Function GetTenPrimes() As Array
        Dim arr As Array = Array.CreateInstance(GetType(Int32), {10}, {1})
        arr.SetValue(1, 1)
        arr.SetValue(2, 2)
        arr.SetValue(3, 3)
        arr.SetValue(5, 4)
        arr.SetValue(7, 5)
        arr.SetValue(11, 6)
        arr.SetValue(13, 7)
        arr.SetValue(17, 8)
        arr.SetValue(19, 9)
        arr.SetValue(23, 10)
        Return arr
     End Function
  End Class
  ```

* Todos los elementos de la matriz deben componerse de tipos conformes a CLS. En el ejemplo siguiente se definen dos métodos que devuelven matrices no conformes a CLS. El primero devuelve una matriz de valores [UInt32](xref:System.UInt32). El segundo devuelve una matriz [Object](xref:System.Object) que contiene los valores [Int32](xref:System.Int32) y `UInt32`. Aunque el compilador identifica la primera matriz como no conforme debido a su tipo `UInt32`, no reconoce que la segunda matriz incluye elementos no conformes a CLS.

  ```csharp
  using System;

  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static UInt32[] GetTenPrimes()
    {
        uint[] arr = { 1u, 2u, 3u, 5u, 7u, 11u, 13u, 17u, 19u };
        return arr;
    }

    public static Object[] GetFivePrimes()
    {
        Object[] arr = { 1, 2, 3, 5u, 7u };
        return arr;
    }
  }
  // Compilation produces a compiler warning like the following:
  //    Array2.cs(8,27): warning CS3002: Return type of 'Numbers.GetTenPrimes()' is not
  //            CLS-compliant
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Class Numbers
     Public Shared Function GetTenPrimes() As UInt32()
        Return { 1ui, 2ui, 3ui, 5ui, 7ui, 11ui, 13ui, 17ui, 19ui }
     End Function
     Public Shared Function GetFivePrimes() As Object()
        Dim arr() As Object = { 1, 2, 3, 5ui, 7ui }
        Return arr
     End Function
  End Class
  ' Compilation produces a compiler warning like the following:
  '    warning BC40027: Return type of function 'GetTenPrimes' is not CLS-compliant.
  ```

* La resolución de desbordamiento de los métodos que tienen parámetros de matriz se basa en el hecho de que son matrices y en su tipo de elemento. Por esta razón, la siguiente definición de un método `GetSquares` sobrecargado es conforme a CLS.

  ```csharp
  using System;
  using System.Numerics;

  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static byte[] GetSquares(byte[] numbers)
    {
        byte[] numbersOut = new byte[numbers.Length];
        for (int ctr = 0; ctr < numbers.Length; ctr++) {
            int square = ((int) numbers[ctr]) * ((int) numbers[ctr]);
            if (square <= Byte.MaxValue)
                numbersOut[ctr] = (byte) square;
            // If there's an overflow, assign MaxValue to the corresponding
            // element.
            else
                numbersOut[ctr] = Byte.MaxValue;

        }
        return numbersOut;
    }

    public static BigInteger[] GetSquares(BigInteger[] numbers)
  {
        BigInteger[] numbersOut = new BigInteger[numbers.Length];
        for (int ctr = 0; ctr < numbers.Length; ctr++)
            numbersOut[ctr] = numbers[ctr] * numbers[ctr];

       return numbersOut;
    }
  }
  ```

  ```vb
  Imports System.Numerics

  <Assembly: CLSCompliant(True)>

  Public Module Numbers
     Public Function GetSquares(numbers As Byte()) As Byte()
        Dim numbersOut(numbers.Length - 1) As Byte
        For ctr As Integer = 0 To numbers.Length - 1
           Dim square As Integer = (CInt(numbers(ctr)) * CInt(numbers(ctr)))
           If square <= Byte.MaxValue Then
              numbersOut(ctr) = CByte(square)
           ' If there's an overflow, assign MaxValue to the corresponding
           ' element.
           Else
              numbersOut(ctr) = Byte.MaxValue
           End If
        Next
        Return numbersOut
     End Function

     Public Function GetSquares(numbers As BigInteger()) As BigInteger()
         Dim numbersOut(numbers.Length - 1) As BigInteger
         For ctr As Integer = 0 To numbers.Length - 1
            numbersOut(ctr) = numbers(ctr) * numbers(ctr)
         Next
         Return numbersOut
     End Function
  End Module
  ```

### <a name="interfaces"></a>Interfaces

Las interfaces conformes a CLS pueden definir propiedades, eventos y métodos virtuales (métodos sin implementación). Una interfaz conforme a CLS no puede tener ninguno de los elementos siguientes:

* Métodos estáticos o campos estáticos. El compilador de C# genera errores de compilador si se define un miembro estático en una interfaz.

* Campos. El compilador de C# genera errores de compilador si se define un campo en una interfaz.

* Métodos que no son conformes a CLS. Por ejemplo, la siguiente definición de interfaz incluye un método, `INumber.GetUnsigned`, que está marcado como no conforme a CLS. Este ejemplo genera una advertencia del compilador.

  ```csharp
  using System;

  [assembly:CLSCompliant(true)]

  public interface INumber
  {
      int Length();
      [CLSCompliant(false)] ulong GetUnsigned();
  }
  // Attempting to compile the example displays output like the following:
  //    Interface2.cs(8,32): warning CS3010: 'INumber.GetUnsigned()': CLS-compliant interfaces
  //            must have only CLS-compliant members
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Interface INumber
    Function Length As Integer
      <CLSCompliant(False)> Function GetUnsigned As ULong
    End Interface
    ' Attempting to compile the example displays output like the following:
    '    Interface2.vb(9) : warning BC40033: Non CLS-compliant 'function' is not allowed in a
    '    CLS-compliant interface.
    '
    '       <CLSCompliant(False)> Function GetUnsigned As ULong
    '                                      ~~~~~~~~~~~
  ```

  Debido a esta regla, no se necesitan tipos conformes a CLS para implementar miembros no conformes a CLS. Si un marco conforme a CLS expone una clase que implementa una interfaz no conforme a CLS, también debe proporcionar implementaciones concretas de todos los miembros no conformes a CLS.

Los compiladores de lenguaje conformes a CLS también deben permitir que una clase proporcione implementaciones independientes de miembros con el mismo nombre y la misma signatura en varias interfaces. C# admite implementaciones de interfaz explícitas para proporcionar diferentes implementaciones de métodos con el mismo nombre. En el ejemplo siguiente se muestra este escenario con la definición de una clase `Temperature` que implementa las interfaces `ICelsius` y `IFahrenheit` como implementaciones de interfaces explícitas.

```csharp
using System;

[assembly: CLSCompliant(true)]

public interface IFahrenheit
{
   decimal GetTemperature();
}

public interface ICelsius
{
   decimal GetTemperature();
}

public class Temperature : ICelsius, IFahrenheit
{
   private decimal _value;

   public Temperature(decimal value)
   {
      // We assume that this is the Celsius value.
      _value = value;
   }

   decimal IFahrenheit.GetTemperature()
   {
      return _value * 9 / 5 + 32;
   }

   decimal ICelsius.GetTemperature()
   {
      return _value;
   }
}
public class Example
{
   public static void Main()
   {
      Temperature temp = new Temperature(100.0m);
      ICelsius cTemp = temp;
      IFahrenheit fTemp = temp;
      Console.WriteLine("Temperature in Celsius: {0} degrees",
                        cTemp.GetTemperature());
      Console.WriteLine("Temperature in Fahrenheit: {0} degrees",
                        fTemp.GetTemperature());
   }
}
// The example displays the following output:
//       Temperature in Celsius: 100.0 degrees
//       Temperature in Fahrenheit: 212.0 degrees
```

```vb
Assembly: CLSCompliant(True)>

Public Interface IFahrenheit
   Function GetTemperature() As Decimal
End Interface

Public Interface ICelsius
   Function GetTemperature() As Decimal
End Interface

Public Class Temperature : Implements ICelsius, IFahrenheit
   Private _value As Decimal

   Public Sub New(value As Decimal)
      ' We assume that this is the Celsius value.
      _value = value
   End Sub

   Public Function GetFahrenheit() As Decimal _
          Implements IFahrenheit.GetTemperature
      Return _value * 9 / 5 + 32
   End Function

   Public Function GetCelsius() As Decimal _
          Implements ICelsius.GetTemperature
      Return _value
   End Function
End Class

Module Example
   Public Sub Main()
      Dim temp As New Temperature(100.0d)
      Console.WriteLine("Temperature in Celsius: {0} degrees",
                        temp.GetCelsius())
      Console.WriteLine("Temperature in Fahrenheit: {0} degrees",
                        temp.GetFahrenheit())
   End Sub
End Module
' The example displays the following output:
'       Temperature in Celsius: 100.0 degrees
'       Temperature in Fahrenheit: 212.0 degrees
```

### <a name="enumerations"></a>Enumeraciones

Las enumeraciones conformes a CLS deben seguir estas reglas:

* El tipo subyacente de una enumeración debe ser un entero intrínseco conforme a CLS ([Byte](xref:System.Byte), [Int16](xref:System.Int16), [Int32](xref:System.Int32) o [Int64](xref:System.Int64)). Por ejemplo, el código siguiente intenta definir una enumeración cuyo tipo subyacente es [UInt32](xref:System.UInt32) y genera una advertencia del compilador.

    ```csharp
    using System;

    [assembly: CLSCompliant(true)]

    public enum Size : uint {
        Unspecified = 0,
        XSmall = 1,
        Small = 2,
        Medium = 3,
        Large = 4,
        XLarge = 5
    };

    public class Clothing
    {
        public string Name;
        public string Type;
        public string Size;
    }
    // The attempt to compile the example displays a compiler warning like the following:
    //    Enum3.cs(6,13): warning CS3009: 'Size': base type 'uint' is not CLS-compliant
    ```

    ```vb
    <Assembly: CLSCompliant(True)>

    Public Enum Size As UInt32
       Unspecified = 0
       XSmall = 1
       Small = 2
       Medium = 3
       Large = 4
       XLarge = 5
    End Enum

    Public Class Clothing
       Public Name As String
       Public Type As String
       Public Size As Size
    End Class
    ' The attempt to compile the example displays a compiler warning like the following:
    '    Enum3.vb(6) : warning BC40032: Underlying type 'UInt32' of Enum is not CLS-compliant.
    '
    '    Public Enum Size As UInt32
    '                ~~~~
    ```

* Un tipo de enumeración debe tener un campo de instancia único denominado `Value__` marcado con el atributo `FieldAttributes.RTSpecialName`. Esto permite hacer referencia al valor del campo de forma implícita.

* Las enumeraciones incluyen campos estáticos literales del mismo tipo que el de la enumeración. Por ejemplo, si define una enumeración `State` con los valores `State.On` y `State.Off`, `State.On` y `State.Off` son campos estáticos literales cuyo tipo será `State`.

* Hay dos tipos de enumeraciones:

  * Las enumeraciones que representan un conjunto de valores enteros con nombre mutuamente excluyentes. Este tipo de enumeración se indica por la ausencia del atributo personalizado [System.FlagsAttribute](xref:System.FlagsAttribute).

  * Las enumeraciones que representan un conjunto de marcadores de bits que se pueden combinar para generar un valor sin nombre. Este tipo de enumeración se indica por la presencia del atributo personalizado [System.FlagsAttribute](xref:System.FlagsAttribute).

Para obtener más información, consulte la documentación de la estructura [Enum](xref:System.Enum).

* El valor de una enumeración no se limita al intervalo de sus valores especificados. Es decir, el intervalo de valores de una enumeración es el intervalo de su valor subyacente. Puede utilizar el método `Enum.IsDefined` para determinar si un valor especificado es miembro de una enumeración.

### <a name="type-members-in-general"></a>Miembros de tipos en general

Common Language Specification necesita todos los campos y métodos accesibles como miembros de una clase determinada. Por tanto, los métodos y los campos estáticos globales (es decir, los métodos o los campos que se definen con independencia de un tipo) no son conformes a CLS. Si intenta incluir un campo o un método global en el código fuente, el compilador de C# generará un error de compilación.

Common Language Specification solo admite la convención de llamada administrada estándar. No admite convenciones de llamada ni métodos no administrados con listas de argumentos variables marcados con la palabra clave `varargs`. En el caso de las listas de argumentos variables que son compatibles con la convención de llamada administrada estándar, use el atributo [ParamArrayAttribute](xref:System.ParamArrayAttribute) o la implementación del lenguaje específico, como la palabra clave `params` en C# y la palabra clave `ParamArray` en Visual Basic.

### <a name="member-accessibility"></a>Accesibilidad de miembros

Al reemplazar un miembro heredado no se puede cambiar la accesibilidad de dicho miembro. Por ejemplo, un método público de una clase base no se puede reemplazar por un método privado de una clase derivada. Existe una excepción: un miembro `protected internal` (en C#) o `Protected Friend` (en Visual Basic) de un ensamblado que se haya reemplazado por un tipo de un ensamblado diferente.  En ese caso, la accesibilidad del reemplazo es `Protected`.

En el ejemplo siguiente se muestra el error que se genera cuando el atributo [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) se establece en `true` y `Person`, que es una clase derivada de `Animal`, intenta cambiar la accesibilidad de la propiedad `Species` de pública a privada. El ejemplo se compila correctamente si su accesibilidad se cambia a pública.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Animal
{
   private string _species;

   public Animal(string species)
   {
      _species = species;
   }

   public virtual string Species
   {
      get { return _species; }
   }

   public override string ToString()
   {
      return _species;
   }
}

public class Human : Animal
{
   private string _name;

   public Human(string name) : base("Homo Sapiens")
   {
      _name = name;
   }

   public string Name
   {
      get { return _name; }
   }

   private override string Species
   {
      get { return base.Species; }
   }

   public override string ToString()
   {
      return _name;
   }
}

public class Example
{
   public static void Main()
   {
      Human p = new Human("John");
      Console.WriteLine(p.Species);
      Console.WriteLine(p.ToString());
   }
}
// The example displays the following output:
//    error CS0621: 'Human.Species': virtual or abstract members cannot be private
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Animal
   Private _species As String

   Public Sub New(species As String)
      _species = species
   End Sub

   Public Overridable ReadOnly Property Species As String
      Get
         Return _species
      End Get
   End Property

   Public Overrides Function ToString() As String
      Return _species
   End Function
End Class

Public Class Human : Inherits Animal
   Private _name As String

   Public Sub New(name As String)
      MyBase.New("Homo Sapiens")
      _name = name
   End Sub

   Public ReadOnly Property Name As String
      Get
         Return _name
      End Get
   End Property

   Private Overrides ReadOnly Property Species As String
      Get
         Return MyBase.Species
      End Get
   End Property

   Public Overrides Function ToString() As String
      Return _name
   End Function
End Class

Public Module Example
   Public Sub Main()
      Dim p As New Human("John")
      Console.WriteLine(p.Species)
      Console.WriteLine(p.ToString())
   End Sub
End Module
' The example displays the following output:
'     'Private Overrides ReadOnly Property Species As String' cannot override
'     'Public Overridable ReadOnly Property Species As String' because
'      they have different access levels.
'
'         Private Overrides ReadOnly Property Species As String
```

Los tipos de la signatura de un miembro deben estar accesibles siempre que dicho miembro esté accesible. Esto significa, por ejemplo, que un miembro público no puede incluir un parámetro cuyo tipo sea privado, protegido o interno. En el ejemplo siguiente se muestra el error del compilador que se produce cuando un constructor de clase `StringWrapper` expone un valor de enumeración `StringOperationType` interno que determina cómo debe ajustarse un valor de cadena.

```csharp
using System;
using System.Text;

public class StringWrapper
{
   string internalString;
   StringBuilder internalSB = null;
   bool useSB = false;

   public StringWrapper(StringOperationType type)
   {
      if (type == StringOperationType.Normal) {
         useSB = false;
      }
      else {
         useSB = true;
         internalSB = new StringBuilder();
      }
   }

   // The remaining source code...
}

internal enum StringOperationType { Normal, Dynamic }
// The attempt to compile the example displays the following output:
//    error CS0051: Inconsistent accessibility: parameter type
//            'StringOperationType' is less accessible than method
//            'StringWrapper.StringWrapper(StringOperationType)'
```

```vb
Imports System.Text

<Assembly:CLSCompliant(True)>

Public Class StringWrapper

   Dim internalString As String
   Dim internalSB As StringBuilder = Nothing
   Dim useSB As Boolean = False

   Public Sub New(type As StringOperationType)
      If type = StringOperationType.Normal Then
         useSB = False
      Else
         internalSB = New StringBuilder()
         useSB = True
      End If
   End Sub

   ' The remaining source code...
End Class

Friend Enum StringOperationType As Integer
   Normal = 0
   Dynamic = 1
End Enum
' The attempt to compile the example displays the following output:
'    error BC30909: 'type' cannot expose type 'StringOperationType'
'     outside the project through class 'StringWrapper'.
'
'       Public Sub New(type As StringOperationType)
'                              ~~~~~~~~~~~~~~~~~~~
```

### <a name="generic-types-and-members"></a>Miembros y tipos genéricos

Los tipos anidados siempre tienen, como mínimo, el mismo número de parámetros genéricos que el tipo envolvente. Estos se corresponden por posición con los parámetros genéricos del tipo envolvente. El tipo genérico también puede incluir nuevos parámetros genéricos.

Las relaciones entre los parámetros de tipo genérico de un tipo envolvente y sus tipos anidados se pueden ocultar en la sintaxis de cada lenguaje. En el ejemplo siguiente, un tipo genérico `Outer<T>` contiene dos clases anidadas: `Inner1A` e `Inner1B<U>`. Las llamadas al método `ToString`, donde cada clase hereda de `Object.ToString`, muestran que cada clase anidada contiene los parámetros de tipo de la clase contenedora.

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Outer<T>
{
   T value;

   public Outer(T value)
   {
      this.value = value;
   }

   public class Inner1A : Outer<T>
   {
      public Inner1A(T value) : base(value)
      {  }
   }

   public class Inner1B<U> : Outer<T>
   {
      U value2;

      public Inner1B(T value1, U value2) : base(value1)
      {
         this.value2 = value2;
      }
   }
}

public class Example
{
   public static void Main()
   {
      var inst1 = new Outer<String>("This");
      Console.WriteLine(inst1);

      var inst2 = new Outer<String>.Inner1A("Another");
      Console.WriteLine(inst2);

      var inst3 = new Outer<String>.Inner1B<int>("That", 2);
      Console.WriteLine(inst3);
   }
}
// The example displays the following output:
//       Outer`1[System.String]
//       Outer`1+Inner1A[System.String]
//       Outer`1+Inner1B`1[System.String,System.Int32]
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Outer(Of T)
   Dim value As T

   Public Sub New(value As T)
      Me.value = value
   End Sub

   Public Class Inner1A : Inherits Outer(Of T)
      Public Sub New(value As T)
         MyBase.New(value)
      End Sub
   End Class

   Public Class Inner1B(Of U) : Inherits Outer(Of T)
      Dim value2 As U

      Public Sub New(value1 As T, value2 As U)
         MyBase.New(value1)
         Me.value2 = value2
      End Sub
   End Class
End Class

Public Module Example
   Public Sub Main()
      Dim inst1 As New Outer(Of String)("This")
      Console.WriteLine(inst1)

      Dim inst2 As New Outer(Of String).Inner1A("Another")
      Console.WriteLine(inst2)

      Dim inst3 As New Outer(Of String).Inner1B(Of Integer)("That", 2)
      Console.WriteLine(inst3)
   End Sub
End Module
' The example displays the following output:
'       Outer`1[System.String]
'       Outer`1+Inner1A[System.String]
'       Outer`1+Inner1B`1[System.String,System.Int32]
```

Los nombres de tipos genéricos se codifican con el formato *name* *n*, donde *name* es el nombre del tipo, *`* es un carácter literal y *n* es el número de parámetros declarados en el tipo o, en el caso de tipos genéricos anidados, el número de parámetros de tipo recién incorporados. Esta codificación de nombres de tipo genérico tiene interés fundamentalmente para los desarrolladores que utilizan la reflexión a fin de acceder a los tipos genéricos conformes a CLS de una biblioteca.

Si las restricciones se aplican a un tipo genérico, los tipos utilizados como restricciones también deben ser conformes a CLS. En el ejemplo siguiente se define una clase denominada `BaseClass` que no es conforme a CLS y una clase genérica denominada `BaseCollection` cuyo parámetro de tipo debe derivarse de `BaseClass`. Sin embargo, puesto que `BaseClass` no es conforme a CLS, el compilador emite una advertencia.

```csharp
using System;

[assembly:CLSCompliant(true)]

[CLSCompliant(false)] public class BaseClass
{}

public class BaseCollection<T> where T : BaseClass
{}
// Attempting to compile the example displays the following output:
//    warning CS3024: Constraint type 'BaseClass' is not CLS-compliant
```

```vb
Assembly: CLSCompliant(True)>

<CLSCompliant(False)> Public Class BaseClass
End Class

Public Class BaseCollection(Of T As BaseClass)
End Class
' Attempting to compile the example displays the following output:
'    warning BC40040: Generic parameter constraint type 'BaseClass' is not
'    CLS-compliant.
'
'    Public Class BaseCollection(Of T As BaseClass)
'                                        ~~~~~~~~~
```

Si un tipo genérico se deriva de un tipo base genérico, es necesario volver a declarar las restricciones para que se pueda garantizar que las restricciones del tipo base también se cumplen. En el ejemplo siguiente se define un objeto `Number<T>` que puede representar cualquier tipo numérico. También se define una clase `FloatingPoint<T>` que representa un valor de punto flotante. Sin embargo, el código fuente no puede compilarse, ya que no aplica la restricción de `Number<T>` (T debe ser un tipo de valor) en `FloatingPoint<T>`.

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Number<T> where T : struct
{
   // use Double as the underlying type, since its range is a superset of
   // the ranges of all numeric types except BigInteger.
   protected double number;

   public Number(T value)
   {
      try {
         this.number = Convert.ToDouble(value);
      }
      catch (OverflowException e) {
         throw new ArgumentException("value is too large.", e);
      }
      catch (InvalidCastException e) {
         throw new ArgumentException("The value parameter is not numeric.", e);
      }
   }

   public T Add(T value)
   {
      return (T) Convert.ChangeType(number + Convert.ToDouble(value), typeof(T));
   }

   public T Subtract(T value)
   {
      return (T) Convert.ChangeType(number - Convert.ToDouble(value), typeof(T));
   }
}

public class FloatingPoint<T> : Number<T>
{
   public FloatingPoint(T number) : base(number)
   {
      if (typeof(float) == number.GetType() ||
          typeof(double) == number.GetType() ||
          typeof(decimal) == number.GetType())
         this.number = Convert.ToDouble(number);
      else
         throw new ArgumentException("The number parameter is not a floating-point number.");
   }
}
// The attempt to compile the example displays the following output:
//       error CS0453: The type 'T' must be a non-nullable value type in
//               order to use it as parameter 'T' in the generic type or method 'Number<T>'
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Number(Of T As Structure)
   ' Use Double as the underlying type, since its range is a superset of
   ' the ranges of all numeric types except BigInteger.
   Protected number As Double

   Public Sub New(value As T)
      Try
         Me.number = Convert.ToDouble(value)
      Catch e As OverflowException
         Throw New ArgumentException("value is too large.", e)
      Catch e As InvalidCastException
         Throw New ArgumentException("The value parameter is not numeric.", e)
      End Try
   End Sub

   Public Function Add(value As T) As T
      Return CType(Convert.ChangeType(number + Convert.ToDouble(value), GetType(T)), T)
   End Function

   Public Function Subtract(value As T) As T
      Return CType(Convert.ChangeType(number - Convert.ToDouble(value), GetType(T)), T)
   End Function
End Class

Public Class FloatingPoint(Of T) : Inherits Number(Of T)
   Public Sub New(number As T)
      MyBase.New(number)
      If TypeOf number Is Single Or
               TypeOf number Is Double Or
               TypeOf number Is Decimal Then
         Me.number = Convert.ToDouble(number)
      Else
         throw new ArgumentException("The number parameter is not a floating-point number.")
      End If
   End Sub
End Class
' The attempt to compile the example displays the following output:
'    error BC32105: Type argument 'T' does not satisfy the 'Structure'
'    constraint for type parameter 'T'.
'
'    Public Class FloatingPoint(Of T) : Inherits Number(Of T)
'                                                          ~
```

El ejemplo se compila correctamente si se agrega la restricción a la clase `FloatingPoint<T>`.

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Number<T> where T : struct
{
   // use Double as the underlying type, since its range is a superset of
   // the ranges of all numeric types except BigInteger.
   protected double number;

   public Number(T value)
   {
      try {
         this.number = Convert.ToDouble(value);
      }
      catch (OverflowException e) {
         throw new ArgumentException("value is too large.", e);
      }
      catch (InvalidCastException e) {
         throw new ArgumentException("The value parameter is not numeric.", e);
      }
   }

   public T Add(T value)
   {
      return (T) Convert.ChangeType(number + Convert.ToDouble(value), typeof(T));
   }

   public T Subtract(T value)
   {
      return (T) Convert.ChangeType(number - Convert.ToDouble(value), typeof(T));
   }
}

public class FloatingPoint<T> : Number<T> where T : struct
{
   public FloatingPoint(T number) : base(number)
   {
      if (typeof(float) == number.GetType() ||
          typeof(double) == number.GetType() ||
          typeof(decimal) == number.GetType())
         this.number = Convert.ToDouble(number);
      else
         throw new ArgumentException("The number parameter is not a floating-point number.");
   }
}
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Number(Of T As Structure)
   ' Use Double as the underlying type, since its range is a superset of
   ' the ranges of all numeric types except BigInteger.
   Protected number As Double

   Public Sub New(value As T)
      Try
         Me.number = Convert.ToDouble(value)
      Catch e As OverflowException
         Throw New ArgumentException("value is too large.", e)
      Catch e As InvalidCastException
         Throw New ArgumentException("The value parameter is not numeric.", e)
      End Try
   End Sub

   Public Function Add(value As T) As T
      Return CType(Convert.ChangeType(number + Convert.ToDouble(value), GetType(T)), T)
   End Function

   Public Function Subtract(value As T) As T
      Return CType(Convert.ChangeType(number - Convert.ToDouble(value), GetType(T)), T)
   End Function
End Class

Public Class FloatingPoint(Of T As Structure) : Inherits Number(Of T)
   Public Sub New(number As T)
      MyBase.New(number)
      If TypeOf number Is Single Or
               TypeOf number Is Double Or
               TypeOf number Is Decimal Then
         Me.number = Convert.ToDouble(number)
      Else
         throw new ArgumentException("The number parameter is not a floating-point number.")
      End If
   End Sub
End Class
```

Common Language Specification impone un modelo conservador adaptado a cada instancia en los tipos anidados y los miembros protegidos. Los tipos genéricos abiertos no pueden exponer campos ni miembros con signaturas que contengan una instancia específica de un tipo genérico anidado y protegido. Los tipos no genéricos que amplíen una instancia específica de una interfaz o clase base genérica no pueden exponer campos ni miembros con signaturas que contengan otra instancia de un tipo genérico anidado y protegido.

En el ejemplo siguiente se define un tipo genérico, `C1<T>`, y una clase protegida, `C1<T>.N`. `C1<T>` tiene dos métodos: `M1` y `M2`. Pero `M1` no es conforme a CLS porque intenta devolver un objeto `C1<int>.N` a partir de `C1<T>`. Una segunda clase, `C2`, se deriva de `C1<long>`. Esta clase tiene dos métodos, `M3` y `M4`. `M3` o es conforme a CLS porque intenta devolver un objeto `C1<int>.N` a partir de una subclase de `C1<long>`. Observe que los compiladores del lenguaje pueden ser aun más restrictivos. En este ejemplo, Visual Basic muestra un error cuando intenta compilar `M4`.

```csharp
using System;

[assembly:CLSCompliant(true)]

public class C1<T>
{
   protected class N { }

   protected void M1(C1<int>.N n) { } // Not CLS-compliant - C1<int>.N not
                                      // accessible from within C1<T> in all
                                      // languages
   protected void M2(C1<T>.N n) { }   // CLS-compliant – C1<T>.N accessible
                                      // inside C1<T>
}

public class C2 : C1<long>
{
   protected void M3(C1<int>.N n) { }  // Not CLS-compliant – C1<int>.N is not
                                       // accessible in C2 (extends C1<long>)

   protected void M4(C1<long>.N n) { } // CLS-compliant, C1<long>.N is
                                       // accessible in C2 (extends C1<long>)
}
// Attempting to compile the example displays output like the following:
//       Generics4.cs(9,22): warning CS3001: Argument type 'C1<int>.N' is not CLS-compliant
//       Generics4.cs(18,22): warning CS3001: Argument type 'C1<int>.N' is not CLS-compliant
```

```vb
<Assembly:CLSCompliant(True)>

Public Class C1(Of T)
   Protected Class N
   End Class

   Protected Sub M1(n As C1(Of Integer).N)   ' Not CLS-compliant - C1<int>.N not
                                             ' accessible from within C1(Of T) in all
   End Sub                                   ' languages

   Protected Sub M2(n As C1(Of T).N)     ' CLS-compliant – C1(Of T).N accessible
   End Sub                               ' inside C1(Of T)
End Class

Public Class C2 : Inherits C1(Of Long)
   Protected Sub M3(n As C1(Of Integer).N)   ' Not CLS-compliant – C1(Of Integer).N is not
   End Sub                                   ' accessible in C2 (extends C1(Of Long))

   Protected Sub M4(n As C1(Of Long).N)
   End Sub
End Class
' Attempting to compile the example displays output like the following:
'    error BC30508: 'n' cannot expose type 'C1(Of Integer).N' in namespace
'    '<Default>' through class 'C1'.
'
'       Protected Sub M1(n As C1(Of Integer).N)   ' Not CLS-compliant - C1<int>.N not
'                             ~~~~~~~~~~~~~~~~
'    error BC30389: 'C1(Of T).N' is not accessible in this context because
'    it is 'Protected'.
'
'       Protected Sub M3(n As C1(Of Integer).N)   ' Not CLS-compliant - C1(Of Integer).N is not
'
'                             ~~~~~~~~~~~~~~~~
'
'    error BC30389: 'C1(Of T).N' is not accessible in this context because it is 'Protected'.
'
'       Protected Sub M4(n As C1(Of Long).N)
'                             ~~~~~~~~~~~~~
```

### <a name="constructors"></a>Constructores

Los constructores de clases y estructuras conformes a CLS deben seguir estas reglas:

* Un constructor de una clase derivada debe llamar al constructor de instancia de su clase base antes de tener acceso a datos de instancia heredados. Este requisito se debe al hecho de que los constructores de clase base no se heredan por sus clases derivadas. Esta regla no se aplica a las estructuras, que no admiten la herencia directa.

  Normalmente, los compiladores aplican esta regla independientemente de la conformidad con CLS, como se muestra en el ejemplo siguiente. En este ejemplo, se crea una clase `Doctor` que se deriva de una clase `Person`, pero la clase `Doctor` no consigue llamar al constructor de la clase `Person` para inicializar los campos de instancia heredados.

    ```csharp
    using System;

    [assembly: CLSCompliant(true)]

    public class Person
    {
    private string fName, lName, _id;

    public Person(string firstName, string lastName, string id)
    {
        if (String.IsNullOrEmpty(firstName + lastName))
            throw new ArgumentNullException("Either a first name or a last name must be provided.");

        fName = firstName;
        lName = lastName;
        _id = id;
    }

    public string FirstName
    {
        get { return fName; }
    }

    public string LastName
    {
        get { return lName; }
    }

    public string Id
    {
        get { return _id; }
    }

    public override string ToString()
    {
        return String.Format("{0}{1}{2}", fName,
                            String.IsNullOrEmpty(fName) ?  "" : " ",
                            lName);
    }
    }

    public class Doctor : Person
    {
    public Doctor(string firstName, string lastName, string id)
    {
    }

    public override string ToString()
    {
        return "Dr. " + base.ToString();
    }
    }
    // Attempting to compile the example displays output like the following:
    //    ctor1.cs(45,11): error CS1729: 'Person' does not contain a constructor that takes 0
    //            arguments
    //    ctor1.cs(10,11): (Location of symbol related to previous error)
    ```

    ```vb
    <Assembly: CLSCompliant(True)>

    Public Class Person
       Private fName, lName, _id As String

       Public Sub New(firstName As String, lastName As String, id As String)
          If String.IsNullOrEmpty(firstName + lastName) Then
             Throw New ArgumentNullException("Either a first name or a last name must be provided.")
          End If

          fName = firstName
          lName = lastName
          _id = id
       End Sub

       Public ReadOnly Property FirstName As String
          Get
             Return fName
          End Get
       End Property

       Public ReadOnly Property LastName As String
          Get
             Return lName
          End Get
       End Property

       Public ReadOnly Property Id As String
          Get
             Return _id
          End Get
       End Property

       Public Overrides Function ToString() As String
          Return String.Format("{0}{1}{2}", fName,
                               If(String.IsNullOrEmpty(fName), "", " "),
                               lName)
       End Function
    End Class

    Public Class Doctor : Inherits Person
       Public Sub New(firstName As String, lastName As String, id As String)
       End Sub

       Public Overrides Function ToString() As String
          Return "Dr. " + MyBase.ToString()
       End Function
    End Class
    ' Attempting to compile the example displays output like the following:
    '    Ctor1.vb(46) : error BC30148: First statement of this 'Sub New' must be a call
    '    to 'MyBase.New' or 'MyClass.New' because base class 'Person' of 'Doctor' does
    '    not have an accessible 'Sub New' that can be called with no arguments.
    '
    '       Public Sub New()
    '                  ~~~
    ````

* No se puede llamar a un constructor de objetos excepto para crear un objeto. Además, un objeto no se puede inicializar dos veces. Por ejemplo, esto significa que `Object.MemberwiseClone` no debe llamar a los constructores.

### <a name="properties"></a>Propiedades

Las propiedades de los tipos conformes a CLS deben seguir estas reglas:

* Una propiedad debe tener un establecedor, un captador o ambos. En un ensamblado, estos elementos se implementan como métodos especiales, lo que significa que aparecerán como métodos independientes (el captador se llama `get`\_*propertyname* y el establecedor es `set`\_*propertyname*) marcados como `SpecialName` en los metadatos del ensamblado. El compilador de C# aplica esta regla automáticamente sin necesidad de aplicar el atributo <xref:System.CLSCompliantAttribute>.

* El tipo de una propiedad es el tipo de valor devuelto del captador de la propiedad y el último argumento del establecedor. Estos tipos deben ser conformes a CLS y los argumentos no se pueden asignar a la propiedad por referencia (es decir, no pueden ser punteros administrados).

* Si una propiedad tiene un captador y un establecedor, estos deben ser virtuales, estáticos o de instancia. El compilador de C# aplica automáticamente esta regla mediante la sintaxis de la definición de la propiedad.

### <a name="events"></a>Events

Un evento se define por su nombre y su tipo. El tipo de evento es un delegado que se utiliza para indicar el evento. Por ejemplo, el evento `DbConnection.StateChange` es del tipo `StateChangeEventHandler`. Además del propio evento, hay tres métodos con nombres basados en el nombre de evento que proporcionan la implementación del evento y que se marcan como `SpecialName` en los metadatos de ensamblado:

* Un método para agregar un controlador de eventos, llamado `add`_*EventName*. Por ejemplo, el método de suscripción de eventos del evento `DbConnection.StateChange` se denomina `add_StateChange`.

* Un método para quitar un controlador de eventos, llamado `remove`_*EventName*. Por ejemplo, el método de eliminación del evento `DbConnection.StateChange` se denomina `remove_StateChange`.

* Un método para indicar que el evento se ha producido, llamado `raise`\_*EventName*.

> [!NOTE]
> La mayoría de las reglas de Common Language Specification relacionadas con los eventos se implementan mediante compiladores del lenguaje y son transparentes para los desarrolladores de componentes.

Los métodos para agregar, quitar y generar el evento deben tener la misma accesibilidad. Además, todos deben ser estáticos, virtuales o de instancia. Los métodos para agregar y quitar un evento tienen un parámetro cuyo tipo es el mismo que el del delegado de eventos. Los métodos para agregar y quitar deben estar presentes o ausentes al mismo tiempo.

En el ejemplo siguiente se define una clase conforme a CLS denominada `Temperature` que genera un evento `TemperatureChanged` si el cambio de temperatura entre dos lecturas es igual o mayor que el valor de umbral. La clase `Temperature` define de manera explícita un método `raise_TemperatureChanged` para que pueda ejecutar controladores de eventos de forma selectiva.

```csharp
using System;
using System.Collections;
using System.Collections.Generic;

[assembly: CLSCompliant(true)]

public class TemperatureChangedEventArgs : EventArgs
{
   private Decimal originalTemp;
   private Decimal newTemp;
   private DateTimeOffset when;

   public TemperatureChangedEventArgs(Decimal original, Decimal @new, DateTimeOffset time)
   {
      originalTemp = original;
      newTemp = @new;
      when = time;
   }

   public Decimal OldTemperature
   {
      get { return originalTemp; }
   }

   public Decimal CurrentTemperature
   {
      get { return newTemp; }
   }

   public DateTimeOffset Time
   {
      get { return when; }
   }
}

public delegate void TemperatureChanged(Object sender, TemperatureChangedEventArgs e);

public class Temperature
{
   private struct TemperatureInfo
   {
      public Decimal Temperature;
      public DateTimeOffset Recorded;
   }

   public event TemperatureChanged TemperatureChanged;

   private Decimal previous;
   private Decimal current;
   private Decimal tolerance;
   private List<TemperatureInfo> tis = new List<TemperatureInfo>();

   public Temperature(Decimal temperature, Decimal tolerance)
   {
      current = temperature;
      TemperatureInfo ti = new TemperatureInfo();
      ti.Temperature = temperature;
      tis.Add(ti);
      ti.Recorded = DateTimeOffset.UtcNow;
      this.tolerance = tolerance;
   }

   public Decimal CurrentTemperature
   {
      get { return current; }
      set {
         TemperatureInfo ti = new TemperatureInfo();
         ti.Temperature = value;
         ti.Recorded = DateTimeOffset.UtcNow;
         previous = current;
         current = value;
         if (Math.Abs(current - previous) >= tolerance)
            raise_TemperatureChanged(new TemperatureChangedEventArgs(previous, current, ti.Recorded));
      }
   }

   public void raise_TemperatureChanged(TemperatureChangedEventArgs eventArgs)
   {
      if (TemperatureChanged == null)
         return;

      foreach (TemperatureChanged d in TemperatureChanged.GetInvocationList()) {
         if (d.Method.Name.Contains("Duplicate"))
            Console.WriteLine("Duplicate event handler; event handler not executed.");
         else
            d.Invoke(this, eventArgs);
      }
   }
}

public class Example
{
   public Temperature temp;

   public static void Main()
   {
      Example ex = new Example();
   }

   public Example()
   {
      temp = new Temperature(65, 3);
      temp.TemperatureChanged += this.TemperatureNotification;
      RecordTemperatures();
      Example ex = new Example(temp);
      ex.RecordTemperatures();
   }

   public Example(Temperature t)
   {
      temp = t;
      RecordTemperatures();
   }

   public void RecordTemperatures()
   {
      temp.TemperatureChanged += this.DuplicateTemperatureNotification;
      temp.CurrentTemperature = 66;
      temp.CurrentTemperature = 63;
   }

   internal void TemperatureNotification(Object sender, TemperatureChangedEventArgs e)
   {
      Console.WriteLine("Notification 1: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature);
   }

   public void DuplicateTemperatureNotification(Object sender, TemperatureChangedEventArgs e)
   {
      Console.WriteLine("Notification 2: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature);
   }
}
```

```vb
Imports System.Collections
Imports System.Collections.Generic

<Assembly: CLSCompliant(True)>

Public Class TemperatureChangedEventArgs   : Inherits EventArgs
   Private originalTemp As Decimal
   Private newTemp As Decimal
   Private [when] As DateTimeOffset

   Public Sub New(original As Decimal, [new] As Decimal, [time] As DateTimeOffset)
      originalTemp = original
      newTemp = [new]
      [when] = [time]
   End Sub

   Public ReadOnly Property OldTemperature As Decimal
      Get
         Return originalTemp
      End Get
   End Property

   Public ReadOnly Property CurrentTemperature As Decimal
      Get
         Return newTemp
      End Get
   End Property

   Public ReadOnly Property [Time] As DateTimeOffset
      Get
         Return [when]
      End Get
   End Property
End Class

Public Delegate Sub TemperatureChanged(sender As Object, e As TemperatureChangedEventArgs)

Public Class Temperature
   Private Structure TemperatureInfo
      Dim Temperature As Decimal
      Dim Recorded As DateTimeOffset
   End Structure

   Public Event TemperatureChanged As TemperatureChanged

   Private previous As Decimal
   Private current As Decimal
   Private tolerance As Decimal
   Private tis As New List(Of TemperatureInfo)

   Public Sub New(temperature As Decimal, tolerance As Decimal)
      current = temperature
      Dim ti As New TemperatureInfo()
      ti.Temperature = temperature
      ti.Recorded = DateTimeOffset.UtcNow
      tis.Add(ti)
      Me.tolerance = tolerance
   End Sub

   Public Property CurrentTemperature As Decimal
      Get
         Return current
      End Get
      Set
         Dim ti As New TemperatureInfo
         ti.Temperature = value
         ti.Recorded = DateTimeOffset.UtcNow
         previous = current
         current = value
         If Math.Abs(current - previous) >= tolerance Then
            raise_TemperatureChanged(New TemperatureChangedEventArgs(previous, current, ti.Recorded))
         End If
      End Set
   End Property

   Public Sub raise_TemperatureChanged(eventArgs As TemperatureChangedEventArgs)
      If TemperatureChangedEvent Is Nothing Then Exit Sub

      Dim ListenerList() As System.Delegate = TemperatureChangedEvent.GetInvocationList()
      For Each d As TemperatureChanged In TemperatureChangedEvent.GetInvocationList()
         If d.Method.Name.Contains("Duplicate") Then
            Console.WriteLine("Duplicate event handler; event handler not executed.")
         Else
            d.Invoke(Me, eventArgs)
         End If
      Next
   End Sub
End Class

Public Class Example
   Public WithEvents temp As Temperature

   Public Shared Sub Main()
      Dim ex As New Example()
   End Sub

   Public Sub New()
      temp = New Temperature(65, 3)
      RecordTemperatures()
      Dim ex As New Example(temp)
      ex.RecordTemperatures()
   End Sub

   Public Sub New(t As Temperature)
      temp = t
      RecordTemperatures()
   End Sub

   Public Sub RecordTemperatures()
      temp.CurrentTemperature = 66
      temp.CurrentTemperature = 63

   End Sub

   Friend Shared Sub TemperatureNotification(sender As Object, e As TemperatureChangedEventArgs) _
          Handles temp.TemperatureChanged
      Console.WriteLine("Notification 1: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature)
   End Sub

   Friend Shared Sub DuplicateTemperatureNotification(sender As Object, e As TemperatureChangedEventArgs) _
          Handles temp.TemperatureChanged
      Console.WriteLine("Notification 2: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature)
   End Sub
End Class
```

### <a name="overloads"></a>Overloads

Common Language Specification impone los siguientes requisitos a los miembros sobrecargados:

* Los miembros se pueden sobrecargar según el número de parámetros y el tipo de cualquiera de los parámetros. A la hora de distinguir entre sobrecargas, no se tienen en cuenta los factores de convención de llamada, el tipo de valor devuelto, los modificadores personalizados aplicados al método o a su parámetro, ni si los parámetros se pasan por valor o por referencia. Para consultar un ejemplo, vea el código del requisito que establece que los nombres deben ser únicos en cada ámbito que se incluye en la sección [Convenciones de nomenclatura](#naming-conventions).

* Solo las propiedades y los métodos se pueden sobrecargar. Los campos y eventos no se pueden sobrecargar.

* Los métodos genéricos pueden sobrecargarse en función del número de parámetros genéricos.

> [!NOTE]
> Los operadores `op_Explicit` y `op_Implicit` son una excepción de la regla que establece que el valor devuelto no se considera parte de la signatura de un método en la resolución de la sobrecarga. Estos dos operadores se pueden sobrecargar según sus parámetros y su valor devuelto.

### <a name="exceptions"></a>Excepciones

Los objetos de excepción deben derivar de [System.Exception](xref:System.Exception) o de otro tipo derivado de `System.Exception`. En el ejemplo siguiente se muestra el error de compilador que se produce cuando una clase personalizada denominada `ErrorClass` se utiliza para el control de excepciones.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ErrorClass
{
   string msg;

   public ErrorClass(string errorMessage)
   {
      msg = errorMessage;
   }

   public string Message
   {
      get { return msg; }
   }
}

public static class StringUtilities
{
   public static string[] SplitString(this string value, int index)
   {
      if (index < 0 | index > value.Length) {
         ErrorClass badIndex = new ErrorClass("The index is not within the string.");
         throw badIndex;
      }
      string[] retVal = { value.Substring(0, index - 1),
                          value.Substring(index) };
      return retVal;
   }
}
// Compilation produces a compiler error like the following:
//    Exceptions1.cs(26,16): error CS0155: The type caught or thrown must be derived from
//            System.Exception
```

```vb
Imports System.Runtime.CompilerServices

<Assembly: CLSCompliant(True)>

Public Class ErrorClass
   Dim msg As String

   Public Sub New(errorMessage As String)
      msg = errorMessage
   End Sub

   Public ReadOnly Property Message As String
      Get
         Return msg
      End Get
   End Property
End Class

Public Module StringUtilities
   <Extension()> Public Function SplitString(value As String, index As Integer) As String()
      If index < 0 Or index > value.Length Then
         Dim BadIndex As New ErrorClass("The index is not within the string.")
         Throw BadIndex
      End If
      Dim retVal() As String = { value.Substring(0, index - 1),
                                 value.Substring(index) }
      Return retVal
   End Function
End Module
' Compilation produces a compiler error like the following:
'    Exceptions1.vb(27) : error BC30665: 'Throw' operand must derive from 'System.Exception'.
'
'             Throw BadIndex
'             ~~~~~~~~~~~~~~
```

Para corregir este error, la clase `ErrorClass` debe heredar de `System.Exception`. Además, la propiedad Message debe invalidarse. En el ejemplo siguiente se corrigen estos errores para definir una clase `ErrorClass` que sea conforme a CLS.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ErrorClass : Exception
{
   string msg;

   public ErrorClass(string errorMessage)
   {
      msg = errorMessage;
   }

   public override string Message
   {
      get { return msg; }
   }
}

public static class StringUtilities
{
   public static string[] SplitString(this string value, int index)
   {
      if (index < 0 | index > value.Length) {
         ErrorClass badIndex = new ErrorClass("The index is not within the string.");
         throw badIndex;
      }
      string[] retVal = { value.Substring(0, index - 1),
                          value.Substring(index) };
      return retVal;
   }
}
```

```vb
Imports System.Runtime.CompilerServices

<Assembly: CLSCompliant(True)>

Public Class ErrorClass : Inherits Exception
   Dim msg As String

   Public Sub New(errorMessage As String)
      msg = errorMessage
   End Sub

   Public Overrides ReadOnly Property Message As String
      Get
         Return msg
      End Get
   End Property
End Class

Public Module StringUtilities
   <Extension()> Public Function SplitString(value As String, index As Integer) As String()
      If index < 0 Or index > value.Length Then
         Dim BadIndex As New ErrorClass("The index is not within the string.")
         Throw BadIndex
      End If
      Dim retVal() As String = { value.Substring(0, index - 1),
                                 value.Substring(index) }
      Return retVal
   End Function
End Module
```

### <a name="attributes"></a>Atributos

En los ensamblados de .NET Framework, los atributos personalizados proporcionan un mecanismo extensible para almacenar atributos personalizados y recuperar metadatos sobre objetos de programación, tales como ensamblados, tipos, miembros y parámetros de método. Los atributos personalizados deben derivar de [System.Attribute](xref:System.Attribute) o de un tipo derivado de `System.Attribute`.

En el ejemplo siguiente se infringe esta regla. Define una clase `NumericAttribute` que no se deriva de `System.Attribute`. Tenga en cuenta que un error del compilador solo se produce cuando se aplica el atributo no conforme a CLS, y no cuando se define la clase.

```csharp
using System;

[assembly: CLSCompliant(true)]

[AttributeUsageAttribute(AttributeTargets.Class | AttributeTargets.Struct)]
public class NumericAttribute
{
   private bool _isNumeric;

   public NumericAttribute(bool isNumeric)
   {
      _isNumeric = isNumeric;
   }

   public bool IsNumeric
   {
      get { return _isNumeric; }
   }
}

[Numeric(true)] public struct UDouble
{
   double Value;
}
// Compilation produces a compiler error like the following:
//    Attribute1.cs(22,2): error CS0616: 'NumericAttribute' is not an attribute class
//    Attribute1.cs(7,14): (Location of symbol related to previous error)
```

```vb
<Assembly: CLSCompliant(True)>

<AttributeUsageAttribute(AttributeTargets.Class Or AttributeTargets.Struct)> _
Public Class NumericAttribute
   Private _isNumeric As Boolean

   Public Sub New(isNumeric As Boolean)
      _isNumeric = isNumeric
   End Sub

   Public ReadOnly Property IsNumeric As Boolean
      Get
         Return _isNumeric
      End Get
   End Property
End Class

<Numeric(True)> Public Structure UDouble
   Dim Value As Double
End Structure
' Compilation produces a compiler error like the following:
'    error BC31504: 'NumericAttribute' cannot be used as an attribute because it
'    does not inherit from 'System.Attribute'.
'
'    <Numeric(True)> Public Structure UDouble
'     ~~~~~~~~~~~~~
```

El constructor o las propiedades de un atributo conforme a CLS pueden exponer solo los tipos siguientes:

* [Boolean](xref:System.Boolean)

* [Byte](xref:System.Byte)

* [Char](xref:System.Char)

* [Double](xref:System.Double)

* [Int16](xref:System.Int16)

* [Int32](xref:System.Int32)

* [Int64](xref:System.Int64)

* [Single](xref:System.Single)

* [String](xref:System.String)

* [Type](xref:System.Type)

* Cualquier tipo de enumeración cuyo tipo subyacente sea `Byte`, `Int16`, `Int32` o `Int64`.

En el ejemplo siguiente se define una clase `DescriptionAttribute` que se deriva de [Attribute](xref:System.Attribute). El constructor de clase tiene un parámetro de tipo `Descriptor`, de modo que la clase no es conforme a CLS. Tenga en cuenta que el compilador de C# emite una advertencia pero se compila correctamente.

```csharp
using System;

[assembly:CLSCompliantAttribute(true)]

public enum DescriptorType { type, member };

public class Descriptor
{
   public DescriptorType Type;
   public String Description;
}

[AttributeUsage(AttributeTargets.All)]
public class DescriptionAttribute : Attribute
{
   private Descriptor desc;

   public DescriptionAttribute(Descriptor d)
   {
      desc = d;
   }

   public Descriptor Descriptor
   { get { return desc; } }
}
// Attempting to compile the example displays output like the following:
//       warning CS3015: 'DescriptionAttribute' has no accessible
//               constructors which use only CLS-compliant types
```

```vb
<Assembly:CLSCompliantAttribute(True)>

Public Enum DescriptorType As Integer
   Type = 0
   Member = 1
End Enum

Public Class Descriptor
   Public Type As DescriptorType
   Public Description As String
End Class

<AttributeUsage(AttributeTargets.All)> _
Public Class DescriptionAttribute : Inherits Attribute
   Private desc As Descriptor

   Public Sub New(d As Descriptor)
      desc = d
   End Sub

   Public ReadOnly Property Descriptor As Descriptor
      Get
         Return desc
      End Get
   End Property
End Class
```

## <a name="the-clscompliantattribute-attribute"></a>CLSCompliantAttribute (Atributo)

El atributo [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) se usa para indicar si un elemento del programa es conforme a Common Language Specification. El constructor `CLSCompliantAttribute.CLSCompliantAttribute(Boolean)` contiene un único parámetro obligatorio, *isCompliant*, que indica si el elemento del programa es conforme a CLS.

En tiempo de compilación, el compilador detecta los elementos que supuestamente deberían ser conformes a CLS y emite una advertencia. El compilador no emite advertencias relacionadas con los tipos o miembros cuya no conformidad se declara explícitamente.

Los desarrolladores de componentes pueden usar el atributo `CLSCompliantAttribute` de dos maneras:

* Para definir las partes de la interfaz pública expuestas por un componente que son conformes a CLS y las que no lo son. Cuando el atributo se utiliza para marcar determinados elementos del programa como conformes a CLS, este uso garantiza que dichos elementos son accesibles desde todos los lenguajes y herramientas que tienen como destino .NET Framework.

* Para garantizar que la interfaz pública de la biblioteca de componentes expone solo elementos del programa que son conformes a CLS. Si los elementos no son conformes a CLS, los compiladores normalmente emitirán una advertencia.

> [!WARNING]
> En algunos casos, los compiladores de lenguaje aplican reglas conformes a CLS independientemente de si se usa el atributo `CLSCompliantAttribute` o no. Por ejemplo, la definición de un miembro `*static` en una interfaz infringe una regla de CLS. Pero si define un miembro `*static` en una interfaz, el compilador de C# muestra un mensaje de error y se produce un error al compilar la aplicación.

El atributo `CLSCompliantAttribute` está marcado con un atributo [AttributeUsageAttribute](xref:System.AttributeUsageAttribute) que tiene el valor `AttributeTargets.All`. Este valor le permite aplicar el atributo `CLSCompliantAttribute` a cualquier elemento de programa, incluidos los ensamblados, módulos, tipos (clases, estructuras, enumeraciones, interfaces, delegados), miembros de tipo (constructores, métodos, propiedades, campos y eventos), parámetros, parámetros genéricos y valores devueltos. Sin embargo, en la práctica, solo debe aplicar el atributo a los ensamblados, tipos y miembros del tipo. De lo contrario, los compiladores omitirán el atributo y seguirán generando advertencias de compilación siempre que encuentren un parámetro no conforme, un parámetro genérico o un valor devuelto en la interfaz pública de la biblioteca.

El valor del atributo `CLSCompliantAttribute` lo heredan los elementos del programa contenidos. Por ejemplo, si se marca un ensamblado como conforme a CLS, sus tipos también son conformes a CLS. Si un tipo se marca como conforme a CLS, sus tipos anidados y miembros también serán conformes a CLS.

Puede invalidar explícitamente la conformidad heredada aplicando el atributo `CLSCompliantAttribute` a un elemento del programa contenido. Por ejemplo, puede usar el atributo `CLSCompliantAttribute` con el valor *isCompliant* establecido en `false` para definir un tipo no conforme en un ensamblado conforme, y puede usar el atributo con el valor *isCompliant* establecido en `true` para definir un tipo conforme en un ensamblado no conforme. También puede definir miembros no conformes en un tipo conforme. Pero un tipo no conforme no puede tener miembros conformes, por lo que no puede usar el atributo con el valor *isCompliant* establecido en `true` para invalidar la herencia de un tipo no conforme.

Cuando desarrolle componentes, debe utilizar siempre el atributo `CLSCompliantAttribute` para indicar si el ensamblado, sus tipos y sus miembros son conformes a CLS.

Para crear componentes conformes a CLS:

1. Utilice `CLSCompliantAttribute` para marcar el ensamblado como conforme a CLS.

2. Marque como no conforme los tipos expuestos públicamente en el ensamblado que no sean conformes a CLS.

3. Marque como no conforme los miembros expuestos públicamente en tipos conformes a CLS.

4. Proporcione una alternativa conforme a CLS para los miembros que no sean conformes a CLS.

Si ha marcado correctamente todos los tipos y miembros no conformes, el compilador no debe emitir ninguna advertencia de no conformidad. Sin embargo, debe indicar qué miembros no son conformes a CLS y mostrar las alternativas conformes a CLS en la documentación del producto.

En el ejemplo siguiente se usa el atributo `CLSCompliantAttribute` para definir un ensamblado conforme a CLS y un tipo, `CharacterUtilities`, que tiene dos miembros no conformes a CLS. Dado que ambos miembros están etiquetados con el atributo `CLSCompliant(false)`, el compilador no genera ninguna advertencia. La clase también proporciona una alternativa conforme a CLS para ambos métodos. Por lo general, simplemente se agregarían dos sobrecargas al método `ToUTF16` para proporcionar alternativas conformes a CLS. Sin embargo, puesto que no se pueden sobrecargar los métodos en función de un valor devuelto, los nombres de los métodos conformes a CLS son distintos de los nombres de los métodos no conformes.

```csharp
using System;
using System.Text;

[assembly:CLSCompliant(true)]

public class CharacterUtilities
{
   [CLSCompliant(false)] public static ushort ToUTF16(String s)
   {
      s = s.Normalize(NormalizationForm.FormC);
      return Convert.ToUInt16(s[0]);
   }

   [CLSCompliant(false)] public static ushort ToUTF16(Char ch)
   {
      return Convert.ToUInt16(ch);
   }

   // CLS-compliant alternative for ToUTF16(String).
   public static int ToUTF16CodeUnit(String s)
   {
      s = s.Normalize(NormalizationForm.FormC);
      return (int) Convert.ToUInt16(s[0]);
   }

   // CLS-compliant alternative for ToUTF16(Char).
   public static int ToUTF16CodeUnit(Char ch)
   {
      return Convert.ToInt32(ch);
   }

   public bool HasMultipleRepresentations(String s)
   {
      String s1 = s.Normalize(NormalizationForm.FormC);
      return s.Equals(s1);
   }

   public int GetUnicodeCodePoint(Char ch)
   {
      if (Char.IsSurrogate(ch))
         throw new ArgumentException("ch cannot be a high or low surrogate.");

      return Char.ConvertToUtf32(ch.ToString(), 0);
   }

   public int GetUnicodeCodePoint(Char[] chars)
   {
      if (chars.Length > 2)
         throw new ArgumentException("The array has too many characters.");

      if (chars.Length == 2) {
         if (! Char.IsSurrogatePair(chars[0], chars[1]))
            throw new ArgumentException("The array must contain a low and a high surrogate.");
         else
            return Char.ConvertToUtf32(chars[0], chars[1]);
      }
      else {
         return Char.ConvertToUtf32(chars.ToString(), 0);
      }
   }
}
```

```vb
Imports System.Text

<Assembly:CLSCompliant(True)>

Public Class CharacterUtilities
   <CLSCompliant(False)> Public Shared Function ToUTF16(s As String) As UShort
      s = s.Normalize(NormalizationForm.FormC)
      Return Convert.ToUInt16(s(0))
   End Function

   <CLSCompliant(False)> Public Shared Function ToUTF16(ch As Char) As UShort
      Return Convert.ToUInt16(ch)
   End Function

   ' CLS-compliant alternative for ToUTF16(String).
   Public Shared Function ToUTF16CodeUnit(s As String) As Integer
      s = s.Normalize(NormalizationForm.FormC)
      Return CInt(Convert.ToInt16(s(0)))
   End Function

   ' CLS-compliant alternative for ToUTF16(Char).
   Public Shared Function ToUTF16CodeUnit(ch As Char) As Integer
      Return Convert.ToInt32(ch)
   End Function

   Public Function HasMultipleRepresentations(s As String) As Boolean
      Dim s1 As String = s.Normalize(NormalizationForm.FormC)
      Return s.Equals(s1)
   End Function

   Public Function GetUnicodeCodePoint(ch As Char) As Integer
      If Char.IsSurrogate(ch) Then
         Throw New ArgumentException("ch cannot be a high or low surrogate.")
      End If
      Return Char.ConvertToUtf32(ch.ToString(), 0)
   End Function

   Public Function GetUnicodeCodePoint(chars() As Char) As Integer
      If chars.Length > 2 Then
         Throw New ArgumentException("The array has too many characters.")
      End If
      If chars.Length = 2 Then
         If Not Char.IsSurrogatePair(chars(0), chars(1)) Then
            Throw New ArgumentException("The array must contain a low and a high surrogate.")
         Else
            Return Char.ConvertToUtf32(chars(0), chars(1))
         End If
      Else
         Return Char.ConvertToUtf32(chars.ToString(), 0)
      End If
   End Function
End Class
```

Si está desarrollando una aplicación en lugar de una biblioteca (es decir, si no expone los tipos o miembros que pueden consumir otros desarrolladores de aplicaciones), la conformidad con CLS de los elementos del programa usados por la aplicación solo tendrá interés si su lenguaje admite estos elementos. En ese caso, el compilador del lenguaje generará un error cuando intente utilizar un elemento no conforme a CLS.

## <a name="cross-language-interoperability"></a>Interoperabilidad entre lenguajes

La independencia de lenguaje tiene varios significados posibles. Un significado implica perfectamente tipos escritos en un lenguaje desde una aplicación escrita en otro lenguaje. Un segundo significado, que es el descrito en este artículo, implica combinar código escrito en varios lenguajes en un único ensamblado de .NET Framework.

El ejemplo siguiente muestra la interoperabilidad entre lenguajes creando una biblioteca de clases de denominada Utilities.dll que incluye dos clases, `NumericLib` y `StringLib`. La clase `NumericLib` está escrita en C#, y la clase `StringLib` está escrita en Visual Basic. A continuación se muestra el código fuente para `StringUtil.vb`, que incluye un solo miembro, `ToTitleCase`, en su clase `StringLib`.

```vb
Imports System.Collections.Generic
Imports System.Runtime.CompilerServices

Public Module StringLib
   Private exclusions As List(Of String)

   Sub New()
      Dim words() As String = { "a", "an", "and", "of", "the" }
      exclusions = New List(Of String)
      exclusions.AddRange(words)
   End Sub

   <Extension()> _
   Public Function ToTitleCase(title As String) As String
      Dim words() As String = title.Split()
      Dim result As String = String.Empty

      For ctr As Integer = 0 To words.Length - 1
         Dim word As String = words(ctr)
         If ctr = 0 OrElse Not exclusions.Contains(word.ToLower()) Then
            result += word.Substring(0, 1).ToUpper() + _
                      word.Substring(1).ToLower()
         Else
            result += word.ToLower()
         End If
         If ctr <= words.Length - 1 Then
            result += " "
         End If
      Next
      Return result
   End Function
End Module
```

A continuación se muestra el código fuente para NumberUtil.cs, que define una clase `NumericLib` con dos miembros, `IsEven` y `NearZero`.

```csharp
using System;

public static class NumericLib
{
   public static bool IsEven(this IConvertible number)
   {
      if (number is Byte ||
          number is SByte ||
          number is Int16 ||
          number is UInt16 ||
          number is Int32 ||
          number is UInt32 ||
          number is Int64)
         return ((long) number) % 2 == 0;
      else if (number is UInt64)
         return ((ulong) number) %2 == 0;
      else
         throw new NotSupportedException("IsEven called for a non-integer value.");
   }

   public static bool NearZero(double number)
   {
      return number < .00001;
   }
}
```

Para empaquetar las dos clases en un solo ensamblado, debe compilarlas en módulos. Para compilar el archivo de código fuente de Visual Basic en un módulo, use este comando:

```console
vbc /t:module StringUtil.vb
```

Para compilar el archivo de código fuente de C# en un módulo, use este comando:

```console
csc /t:module NumberUtil.cs
```

A continuación, use la herramienta de vinculación (Link.exe) para compilar los dos módulos en un ensamblado:

```console
link numberutil.netmodule stringutil.netmodule /out:UtilityLib.dll /dll
```

El ejemplo siguiente llama a los métodos `NumericLib.NearZero` y `StringLib.ToTitleCase`. Observe que el código de Visual Basic y el código de C# pueden tener acceso a los métodos en ambas clases.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      Double dbl = 0.0 - Double.Epsilon;
      Console.WriteLine(NumericLib.NearZero(dbl));

      string s = "war and peace";
      Console.WriteLine(s.ToTitleCase());
   }
}
// The example displays the following output:
//       True
//       War and Peace
```

```vb
Module Example
   Public Sub Main()
      Dim dbl As Double = 0.0 - Double.Epsilon
      Console.WriteLine(NumericLib.NearZero(dbl))

      Dim s As String = "war and peace"
      Console.WriteLine(s.ToTitleCase())
   End Sub
End Module
' The example displays the following output:
'       True
'       War and Peace
```

Para compilar el código de Visual Basic, use este comando:

```console
vbc example.vb /r:UtilityLib.dll
```

Para compilar con C#, cambie el nombre del compilador de vbc a csc y cambie la extensión de archivo .vb a .cs:

```console
csc example.cs /r:UtilityLib.dll
```
