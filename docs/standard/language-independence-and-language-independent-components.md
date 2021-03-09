---
description: 'Más información acerca de: Independencia del lenguaje y componentes independientes del lenguaje'
title: Independencia del lenguaje y componentes independientes del lenguaje
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- language interoperability
- Common Language Specification
- cross-language interoperability
- CLS
- runtime, language interoperability
- common language runtime, language interoperability
ms.assetid: 4f0b77d0-4844-464f-af73-6e06bedeafc6
ms.openlocfilehash: 69fd1a1944987d08a6ce1aee2790d0dbe06b9452
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106376"
---
# <a name="language-independence-and-language-independent-components"></a>Independencia del lenguaje y componentes independientes del lenguaje

.NET es independiente del lenguaje. Esto significa que, como desarrollador, puede usar uno de los muchos lenguajes que tienen como destino .NET; por ejemplo, C#, C++/CLI, Eiffel, F#, IronPython, IronRuby, PowerBuilder, Visual Basic, Visual COBOL y Windows PowerShell. Puede acceder a los tipos y miembros de bibliotecas de clases desarrollados para .NET sin necesidad de conocer el lenguaje en el que se han escrito originalmente y sin tener que seguir las convenciones del lenguaje original. Si es un desarrollador de componentes, se puede acceder al componente desde cualquier aplicación .NET, con independencia de su lenguaje.

> [!NOTE]
> En la primera parte de este artículo, se explica cómo se crean componentes independientes del lenguaje, es decir, componentes que pueden utilizarse en aplicaciones escritas en cualquier lenguaje. También puede crear una aplicación o componente únicos de código fuente escrito en varios lenguajes; consulte [Interoperabilidad entre lenguajes](#CrossLang) en la segunda parte de este artículo.

Para que los objetos puedan tener una interacción total con otros objetos escritos en cualquier lenguaje, estos objetos solo deben exponer a los llamadores las características que son comunes a todos los lenguajes. Este conjunto común de características se define mediante Common Language Specification (CLS), que es un conjunto de reglas que se aplican a los ensamblados generados. Common Language Specification se define en el apartado I, cláusulas 7 a 11 del [estándar ECMA-335: Common Language Infrastructure](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/).

Si el componente se ajusta a Common Language Specification, existe la garantía de que será conforme a CLS y que será accesible desde el código de un ensamblado escrito en cualquier lenguaje de programación que admita CLS. Para determinar si el componente se ajusta o no a Common Language Specification en tiempo de compilación, puede aplicar el atributo <xref:System.CLSCompliantAttribute> en el código fuente. Para más información, consulte [CLSCompliantAttribute (Atributo)](#CLSAttribute).

En este artículo:

- [Reglas de conformidad con CLS](#Rules)

  - [Signaturas de tipos y miembros de tipo](#Types)

  - [Convenciones de nomenclatura](#naming)

  - [Conversión de tipos](#conversion)

  - [Matrices](#arrays)

  - [Interfaces](#Interfaces)

  - [Enumeraciones](#enums)

  - [Miembros de tipos en general](#members)

  - [Accesibilidad de miembros](#MemberAccess)

  - [Miembros y tipos genéricos](#Generics)

  - [Constructores](#ctors)

  - [Propiedades](#properties)

  - [Eventos](#events)

  - [Sobrecargas](#overloads)

  - [Excepciones](#exceptions)

  - [Atributos](#attributes)

- [CLSCompliantAttribute (Atributo)](#CLSAttribute)

- [Interoperabilidad entre lenguajes](#CrossLang)

<a name="Rules"></a>

## <a name="cls-compliance-rules"></a>Reglas de conformidad con CLS

En esta sección se explican las reglas para crear un componente conforme a CLS. Para obtener una lista completa de las normas, vea el apartado I, cláusula 11 del [estándar ECMA-335: Common Language Infrastructure](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/).

> [!NOTE]
> Common Language Specification describe en cada regla la conformidad con CLS en referencia a los consumidores (desarrolladores que acceden mediante programación a un componente que es conforme a CLS), los marcos (desarrolladores que usan un compilador de lenguaje para crear bibliotecas conformes a CLS) y los extensores (desarrolladores que crean una herramienta, como un compilador de lenguaje o un analizador de código, que crea componentes conformes a CLS). Este artículo se centra en las reglas que se aplican a los marcos. Sin embargo, observe que algunas de las reglas que se aplican a los extensores también se pueden aplicar a los ensamblados que se crean mediante Reflection.Emit.

Para diseñar un componente que sea independiente del lenguaje, solo tiene que aplicar las reglas de conformidad con CLS a la interfaz pública del componente. La implementación privada no tiene que ajustarse a la especificación.

> [!IMPORTANT]
> Las reglas de conformidad con CLS solo se aplican a la interfaz pública de un componente, y no a su implementación privada.

Por ejemplo, los números enteros sin signo distintos de <xref:System.Byte> no son conformes a CLS. Dado que la clase `Person` del siguiente ejemplo expone una propiedad `Age` del tipo <xref:System.UInt16>, el código siguiente desencadena una advertencia del compilador.

[!code-csharp[Conceptual.CLSCompliant#1](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/public1.cs#1)]
[!code-vb[Conceptual.CLSCompliant#1](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/public1.vb#1)]

Para hacer que la clase `Person` sea conforme a CLS, puede cambiar el tipo de la propiedad `Age` de <xref:System.UInt16> a <xref:System.Int16>, que es un entero de 16 bits con signo conforme a CLS. No es necesario que cambie el tipo del campo privado `personAge`.

[!code-csharp[Conceptual.CLSCompliant#2](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/public2.cs#2)]
[!code-vb[Conceptual.CLSCompliant#2](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/public2.vb#2)]

Las interfaces públicas de una biblioteca se componen de los elementos siguientes:

- Definiciones de clases públicas.

- Definiciones de los miembros públicos de las clases públicas y de los miembros accesibles por las clases derivadas (es decir, miembros protegidos).

- Parámetros y tipos devueltos de los métodos públicos de las clases públicas y parámetros y tipos devueltos de los métodos accesibles por las clases derivadas.

Las reglas de conformidad con CLS se muestran en la tabla siguiente. El texto de las normas se toma literalmente del [estándar ECMA-335: Common Language Infrastructure](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/), Copyright de 2012 de Ecma International. En las secciones siguientes encontrará información más detallada sobre estas reglas.

|Categoría|Vea|Regla|Número de regla|
|--------------|---------|----------|-----------------|
|Accesibilidad|[Accesibilidad de miembros](#MemberAccess)|Cuando se reemplacen métodos heredados, no debe modificarse la accesibilidad, excepto cuando se reemplace un método heredado de un ensamblado diferente cuya accesibilidad sea `family-or-assembly`. En este caso, el reemplazo debe tener accesibilidad `family`.|10|
|Accesibilidad|[Accesibilidad de miembros](#MemberAccess)|La visibilidad y accesibilidad de los tipos y miembros se establecerá de modo que los tipos de la signatura de cualquier miembro sean visibles y accesibles siempre que el propio miembro sea visible y accesible. Por ejemplo, un método público que sea visible fuera del ensamblado no debe tener ningún argumento cuyo tipo solamente sea visible en el interior del ensamblado. La visibilidad y la accesibilidad de los tipos que conforman un tipo genérico con instancias que se utilice en la signatura de cualquier miembro deben establecerse de forma que serán visibles y accesibles siempre que el propio miembro sea visible y accesible. Por ejemplo, un tipo genérico con instancias que esté presente en la signatura de un miembro que sea visible fuera del ensamblado no debe tener ningún argumento genérico cuyo tipo solamente sea visible en el interior del ensamblado.|12|
|Matrices|[Matrices](#arrays)|Las matrices deben tener elementos con un tipo conforme a CLS y los límites inferiores de todas las dimensiones de la matriz deben ser iguales a cero. Para distinguir entre sobrecargas, solo se tendrá en cuenta el hecho de que el elemento es una matriz y el tipo de elementos de la matriz. Cuando la sobrecarga se basa en dos o varios tipos de matrices, los tipos de elementos deben ser tipos con nombre.|16|
|Atributos|[Atributos](#attributes)|Los atributos deben ser del tipo <xref:System.Attribute?displayProperty=nameWithType> o de un tipo que se herede de este.|41|
|Atributos|[Atributos](#attributes)|CLS solo permite un subconjunto de codificaciones de atributos personalizados. Los únicos tipos que deben aparecer en estas codificaciones son (consulte el apartado IV): <xref:System.Type?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Char?displayProperty=nameWithType>, <xref:System.Boolean?displayProperty=nameWithType>, <xref:System.Byte?displayProperty=nameWithType>, <xref:System.Int16?displayProperty=nameWithType>, <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.Single?displayProperty=nameWithType>, <xref:System.Double?displayProperty=nameWithType> y cualquier tipo de enumeración basada en un tipo de entero base conforme a CLS.|34|
|Atributos|[Atributos](#attributes)|CLS no admite modificadores obligatorios que sean visibles públicamente (`modreq`, vea el Apartado II), pero sí admite modificadores opcionales (`modopt`, vea el apartado II) que no comprenda.|35|
|Constructores|[Constructores](#ctors)|Un constructor de objetos debe llamar a un constructor de instancias de su clase base antes de que tenga lugar cualquier acceso a los datos de instancia heredados. (Esto no se aplica a los tipos de valor, que no necesitan constructores.)|21|
|Constructores|[Constructores](#ctors)|No debe llamarse a los constructores de objetos excepto durante la creación de un objeto y no podrá iniciarse dos veces un objeto.|22|
|Enumeraciones|[Enumeraciones](#enums)|El tipo subyacente de una enumeración debe ser un tipo de entero integrado en CLS, el nombre del campo debe ser “value__” y dicho campo debe marcarse como `RTSpecialName`.|7|
|Enumeraciones|[Enumeraciones](#enums)|Hay dos tipos distintos de enumeraciones, que se indican mediante la presencia o ausencia del atributo personalizado <xref:System.FlagsAttribute?displayProperty=nameWithType> (vea la biblioteca del apartado IV). Uno representa valores enteros con nombre; el otro representa los marcadores de bit con nombre que se pueden combinar para generar un valor sin nombre. El valor de `enum` no se limita a los valores especificados.|8|
|Enumeraciones|[Enumeraciones](#enums)|Los campos estáticos literales de una enumeración deben contener el tipo de la propia enumeración.|9|
|Events|[Eventos](#events)|Los métodos que implementen un evento se marcarán como `SpecialName` en los metadatos.|29|
|Events|[Eventos](#events)|La accesibilidad de un evento y sus descriptores de acceso será idéntica.|30|
|Events|[Eventos](#events)|Los métodos `add` y `remove` de un evento deben estar presentes o ausentes a la vez.|31|
|Events|[Eventos](#events)|Los métodos `add` y `remove` de un evento deben tomar un parámetro cuyo tipo defina el tipo del evento, y ese tipo debe derivarse de <xref:System.Delegate?displayProperty=nameWithType>.|32|
|Events|[Eventos](#events)|Los eventos deben adherirse a un patrón de asignación de nombres concreto. En las comparaciones de nombres correspondientes, se omitirá el atributo `SpecialName` mencionado en la regla 29 de CLS y se seguirán las reglas del identificador.|33|
|Excepciones|[Excepciones](#exceptions)|Los objetos que se inicien deberán ser de tipo <xref:System.Exception?displayProperty=nameWithType> o de un tipo que herede de él. No obstante, los métodos conformes a CLS no necesitan bloquear la propagación de otros tipos de excepciones.|40|
|General|[Conformidad con CLS: reglas](#Rules)|Las reglas de CLS solo se aplican a las partes de los tipos que son accesibles o visibles desde fuera del ensamblado de definición.|1|
|General|[Conformidad con CLS: reglas](#Rules)|Los miembros de tipos no conformes con CLS no deben marcarse como conformes con CLS.|2|
|Genéricos|[Miembros y tipos genéricos](#Generics)|Los tipos anidados deben tener, como mínimo, el mismo número de parámetros genéricos que el tipo envolvente. Los parámetros genéricos de un tipo anidado se corresponden por posición con los parámetros genéricos del tipo contenedor.|42|
|Genéricos|[Miembros y tipos genéricos](#Generics)|El nombre de un tipo genérico debe codificar el número de parámetros de tipo declarados en el tipo no anidado o que se acaban de introducir en el tipo, si este está anidado, según las reglas definidas anteriormente.|43|
|Genéricos|[Miembros y tipos genéricos](#Generics)|Todo tipo genérico deberá volver a declarar restricciones suficientes como para garantizar que cualquier restricción de las interfaces o del tipo base se vea satisfecha por las restricciones del tipo genérico.|4444|
|Genéricos|[Miembros y tipos genéricos](#Generics)|Los tipos que se utilicen como restricciones en parámetros genéricos deben ser conformes a CLS.|45|
|Genéricos|[Miembros y tipos genéricos](#Generics)|Se entiende que la visibilidad y accesibilidad de los miembros (incluidos los tipos anidados) de un tipo genérico con instancias deben quedar restringidas al ámbito específico de la creación de instancias, y no a la declaración de tipos genéricos en general. Suponiendo que esto sea cierto, se seguirán aplicando las especificaciones de accesibilidad y visibilidad de la regla 12 de CLS.|46|
|Genéricos|[Miembros y tipos genéricos](#Generics)|Cada método genérico abstracto o virtual deberá tener su propia implementación concreta (no abstracta) predeterminada.|47|
|Interfaces|[Interfaces](#Interfaces)|Las interfaces conformes a CLS no deben requerir la definición de métodos no conformes a CLS para su implementación.|18|
|Interfaces|[Interfaces](#Interfaces)|Las interfaces conformes a CLS no pueden definir métodos estáticos ni pueden definir campos.|19|
|Miembros|[Miembros de tipos en general](#members)|Los campos y métodos static globales no son conformes a CLS.|36|
|Miembros|--|El valor de un estático literal se especifica mediante el uso de metadatos de inicialización de campos. Un literal conforme a CLS debe tener un valor especificado en los metadatos de inicialización de campos que sea exactamente del mismo tipo que el literal (o el tipo subyacente, si el literal es `enum`).|13|
|Miembros|[Miembros de tipos en general](#members)|La restricción vararg no forma parte de CLS y la única convención de llamada admitida por CLS es la convención de llamada administrada estándar.|15|
|Convenciones de nomenclatura|[Convenciones de nomenclatura](#naming)|Los ensamblados seguirán las directrices del anexo 7 del informe técnico 15 del estándar Unicode 3.0, que rige el conjunto de caracteres permitidos que pueden usarse como iniciales e incluirse en los identificadores. Estas directrices están disponibles en línea en <https://www.unicode.org/reports/tr15/tr15-18.html>. Los identificadores deben aparecer en el formato canónico definido por el Formulario C de normalización Unicode. En aras de la conformidad con CLS, dos identificadores se considerarán iguales si sus asignaciones de minúsculas (tal y como se especificó en las asignaciones unívocas de minúsculas de Unicode en las que no se tiene en cuenta la configuración regional) son iguales. Es decir, para que dos identificadores se consideren diferentes según CLS, tendrán que diferenciarse en algo más que en el uso de mayúsculas y minúsculas. Pero para invalidar una definición heredada, CLI requiere que se use la codificación exacta de la declaración original.|4|
|Sobrecarga|[Convenciones de nomenclatura](#naming)|Todos los nombres especificados en un ámbito conforme a CLS deben ser distintos independientemente del tipo, salvo en los casos en los que los nombres sean idénticos y se resuelvan mediante sobrecarga. Es decir, mientras CTS permite que un tipo único use el mismo nombre para un método y un campo, CLS no.|5|
|Sobrecarga|[Convenciones de nomenclatura](#naming)|Los campos y los tipos anidados deben distinguirse únicamente por la comparación de identificadores, aunque CTS permita que se distingan signaturas diferentes. Los métodos, las propiedades y los eventos que tengan el mismo nombre (por comparación de identificadores) deben distinguirse por algo más que el tipo de valor devuelto, excepto según lo especificado en la regla 39 de CLS.|6|
|Sobrecarga|[Sobrecargas](#overloads)|Solo las propiedades y los métodos se pueden sobrecargar.|37|
|Sobrecarga|[Sobrecargas](#overloads)|Las propiedades y los métodos se pueden sobrecargar únicamente en función del número y los tipos de sus parámetros, excepto los operadores de conversión denominados `op_Implicit` y `op_Explicit`, que también se pueden sobrecargar en función del tipo de valor devuelto.|38|
|Sobrecarga|--|Si dos o más de los métodos conformes a CLS declarados en un tipo tienen el mismo nombre y, en un conjunto específico de instancias de tipos, tienen los mismos tipos de valor devuelto y parámetros, todos estos métodos serán semánticamente equivalentes en esas instancias de tipos.|48|
|Tipos|[Signaturas de tipos y miembros de tipo](#Types)|<xref:System.Object?displayProperty=nameWithType> es conforme a CLS. Cualquier otra clase conforme a CLS se heredará de una clase conforme a CLS.|23|
|Propiedades|[Propiedades](#properties)|Los métodos que implementan los métodos de captador y establecedor de una propiedad deben estar marcados con `SpecialName` en los metadatos.|24|
|Propiedades|[Propiedades](#properties)|Todos los descriptores de acceso de una propiedad deben ser estáticos, virtuales o de instancia.|26|
|Propiedades|[Propiedades](#properties)|El tipo de una propiedad es el tipo de valor devuelto del método captador y el tipo del último argumento del método establecedor. Los tipos de los parámetros de la propiedad deben ser los tipos de los parámetros del método captador y los tipos de todos los parámetros del método establecedor, excepto el último. Todos estos tipos deben ser conformes a CLS y no pueden ser punteros administrados (es decir, no deben pasarse por referencia).|27|
|Propiedades|[Propiedades](#properties)|Las propiedades deben ajustarse a un patrón de asignación de nombres concreto. En las comparaciones de nombres correspondientes se omitirá el atributo `SpecialName` mencionado en la regla 24 de CLS y se seguirán las reglas del identificador. Una propiedad tendrá un método de captador, un método de establecedor o ambos.|28|
|Conversión de tipos|[Conversión de tipos](#conversion)|Si se proporciona `op_Implicit` u `op_Explicit`, deben darse medios alternativos para realizar la conversión.|39|
|Tipos|[Signaturas de tipos y miembros de tipo](#Types)|Los tipos de valor a los que se les ha aplicado la conversión boxing no son conformes a CLS.|3|
|Tipos|[Signaturas de tipos y miembros de tipo](#Types)|Todos los tipos que aparecen en una signatura deben ser conformes a CLS. Todos los tipos que forman un tipo genérico con instancias deben ser conformes a CLS.|11|
|Tipos|[Signaturas de tipos y miembros de tipo](#Types)|Las referencias a tipos no son conformes a CLS.|14|
|Tipos|[Signaturas de tipos y miembros de tipo](#Types)|Los tipos de puntero no administrados no son conformes a CLS.|17|
|Tipos|[Signaturas de tipos y miembros de tipo](#Types)|Las interfaces, los tipos de valor y las clases conformes a CLS no deben requerir la implementación de miembros no conformes a CLS.|20|

<a name="Types"></a>

### <a name="types-and-type-member-signatures"></a>Signaturas de tipos y miembros de tipo

El tipo <xref:System.Object?displayProperty=nameWithType> es conforme a CLS y es el tipo base de todos los tipos de objetos del sistema de tipos de .NET. La herencia de .NET es implícita (por ejemplo, la clase <xref:System.String> hereda implícitamente de la clase <xref:System.Object>) o explícita (por ejemplo, la clase <xref:System.Globalization.CultureNotFoundException> hereda explícitamente de la clase <xref:System.ArgumentException>, que a su vez hereda explícitamente de la clase <xref:System.SystemException>, que a su vez hereda también explícitamente de la clase <xref:System.Exception>). Para que un tipo derivado sea conforme a CLS, su tipo base también debe ser conforme a CLS.

En el ejemplo siguiente se muestra un tipo derivado cuyo tipo base no es conforme a CLS. En el ejemplo, se define una clase base `Counter` que usa un entero de 32 bits sin signo como contador. Dado que la clase proporciona la funcionalidad de contador ajustando un entero sin signo, la clase se marca como no conforme a CLS. Como resultado, la clase derivada, `NonZeroCounter`, tampoco es conforme a CLS.

[!code-csharp[Conceptual.CLSCompliant#12](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/type3.cs#12)]
[!code-vb[Conceptual.CLSCompliant#12](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/type3.vb#12)]

Todos los tipos que aparecen en las signaturas de miembros, incluidos los tipos de propiedades y los tipos de valores devueltos de un método, deben ser conformes a CLS. Además, en el caso de los tipos genéricos:

- Todos los tipos que forman un tipo genérico con instancias deben ser conformes a CLS.

- Todos los tipos que se utilizan como restricciones en parámetros genéricos deben ser conformes a CLS.

El [sistema de tipos común](base-types/common-type-system.md) de .NET incluye varios tipos integrados que se admiten directamente en Common Language Runtime y que se codifican de forma especial en los metadatos de un ensamblado. De estos tipos intrínsecos, los tipos enumerados en la tabla siguiente son conformes a CLS.

|Tipo conforme a CLS|Descripción|
|-------------------------|-----------------|
|<xref:System.Byte>|Entero de 8 bits sin signo|
|<xref:System.Int16>|Entero de 16 bits con signo|
|<xref:System.Int32>|Entero de 32 bits con signo|
|<xref:System.Int64>|Entero de 64 bits con signo|
|<xref:System.Single>|Valor de punto flotante de precisión sencilla|
|<xref:System.Double>|Valor de punto flotante de precisión doble|
|<xref:System.Boolean>|Tipo de valor `true` o `false`|
|<xref:System.Char>|Unidad de código con la codificación UTF-16|
|<xref:System.Decimal>|Número decimal de punto no flotante|
|<xref:System.IntPtr>|Puntero o identificador de un tamaño definido por la plataforma|
|<xref:System.String>|Colección de cero, uno o varios objetos <xref:System.Char>|

Los tipos intrínsecos enumerados en la tabla siguiente no son conformes a CLS.

|Tipo no conforme|Descripción|Alternativa conforme a CLS|
|-------------------------|-----------------|--------------------------------|
|<xref:System.SByte>|Tipo de datos enteros de 8 bits con signo|<xref:System.Int16>|
|<xref:System.TypedReference>|Puntero a un objeto y su tipo en tiempo de ejecución|None|
|<xref:System.UInt16>|Entero de 16 bits sin signo|<xref:System.Int32>|
|<xref:System.UInt32>|Entero de 32 bits sin signo|<xref:System.Int64>|
|<xref:System.UInt64>|Entero de 64 bits sin signo|<xref:System.Int64> (se puede desbordar), <xref:System.Numerics.BigInteger> o <xref:System.Double>|
|<xref:System.UIntPtr>|Puntero o identificador sin signo|<xref:System.IntPtr>|

La biblioteca de clases de .NET o cualquier otra biblioteca de clases puede incluir otros tipos que no sean conformes a CLS; por ejemplo:

- Tipos de valor a los que se les ha aplicado la conversión boxing. En el siguiente ejemplo de C# se crea una clase con una propiedad pública de tipo `int*` denominada `Value`. Dado que `int*` es un tipo de valor al que se le ha aplicado la conversión boxing, el compilador lo marca como no conforme a CLS.

  [!code-csharp[Conceptual.CLSCompliant#26](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/box2.cs#26)]

- Referencias con establecimiento de tipos, que son construcciones especiales que contienen una referencia a un objeto y una referencia a un tipo. En .NET, las referencias con establecimiento de tipos se representan mediante la clase <xref:System.TypedReference>.

Si un tipo no es conforme a CLS, deberá aplicarle el atributo <xref:System.CLSCompliantAttribute> con el valor de `isCompliant` establecido en `false`. Para obtener más información, vea la sección [CLSCompliantAttribute (Atributo)](#CLSAttribute).

En el ejemplo siguiente se muestra el problema de la conformidad con CLS en la creación de instancias de tipos genéricos y signaturas de métodos. En este ejemplo, se define una clase `InvoiceItem` con una propiedad de tipo <xref:System.UInt32>, una propiedad de tipo `Nullable(Of UInt32)` y un constructor con parámetros de tipo <xref:System.UInt32> y `Nullable(Of UInt32)`. Cuando intente compilar este ejemplo, aparecerán cuatro advertencias del compilador.

[!code-csharp[Conceptual.CLSCompliant#3](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/type1.cs#3)]
[!code-vb[Conceptual.CLSCompliant#3](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/type1.vb#3)]

Para eliminar las advertencias del compilador, reemplace los tipos no conformes a CLS de la interfaz pública de `InvoiceItem` por tipos conformes:

[!code-csharp[Conceptual.CLSCompliant#4](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/type2.cs#4)]
[!code-vb[Conceptual.CLSCompliant#4](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/type2.vb#4)]

Además de los tipos específicos indicados, algunas categorías de tipos no son conformes a CLS. Entre estas categorías se incluyen tipos de punteros no administrados y tipos de punteros de función. En el ejemplo siguiente se genera una advertencia del compilador, ya que se utiliza un puntero a un entero para crear una matriz de enteros.

[!code-csharp[Conceptual.CLSCompliant#5](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/unmanagedptr1.cs#5)]

En las clases abstractas conformes a CLS (es decir, clases marcadas como `abstract` en C# o como `MustInherit` en Visual Basic), todos los miembros de dichas clases deben ser también conformes a CLS.

<a name="naming"></a>

### <a name="naming-conventions"></a>Convenciones de nomenclatura

Dado que algunos lenguajes de programación distinguen entre mayúsculas y minúsculas, los identificadores (como los nombres de espacios de nombres, los tipos y los miembros) deben tener otro elemento distintivo aparte del uso de mayúsculas. Dos identificadores se consideran equivalentes si sus asignaciones de minúsculas son iguales. En el ejemplo de C# siguiente, se definen dos clases públicas: `Person` y `person`. Como solo se distinguen por el uso de mayúsculas, el compilador de C# las marca como no conformes a CLS.

[!code-csharp[Conceptual.CLSCompliant#16](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/naming1.cs#16)]

Los identificadores de los lenguajes de programación, como los nombres de los espacios de nombres, tipos y miembros, deben ajustarse al [Estándar Unicode 3.0, Informe técnico 15, Anexo 7](https://www.unicode.org/reports/tr15/tr15-18.html). Esto significa que:

- El primer carácter de un identificador puede ser cualquier letra en mayúscula, letra en minúscula, letra de inicial en mayúscula, letra modificadora, otra letra o número de letra. Para obtener información acerca de las categorías de caracteres Unicode, vea la enumeración <xref:System.Globalization.UnicodeCategory?displayProperty=nameWithType>.

- Los caracteres siguientes pueden proceder de cualquier categoría cuando funcionan como primer carácter y también pueden incluir marcas no espaciadas, marcas de combinación de espaciado, números decimales, puntuaciones de conexión y códigos de formato.

Antes de comparar los identificadores, debe filtrar los códigos de formato y convertir los identificadores a la forma de normalización Unicode C, ya que un mismo carácter se puede representar mediante diferentes unidades de código UTF-16. Las secuencias de caracteres que producen las mismas unidades de código en la forma de normalización Unicode C no son conformes a CLS. En el ejemplo siguiente se define una propiedad llamada `Å`, que se compone del carácter SIGNO DE ANGSTROM (U+212B) y una segunda propiedad llamada `Å`, que se compone de la LETRA MAYÚSCULA A LATINA CON UN ANILLO ENCIMA (U+00C5). Los compiladores de C# y Visual Basic identifican el código fuente como no conforme a CLS.

[!code-csharp[Conceptual.CLSCompliant#17](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/naming1.cs#17)]
[!code-vb[Conceptual.CLSCompliant#17](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/naming1.vb#17)]

Los nombres de miembros con un ámbito determinado (como los espacios de nombres de un ensamblado, los tipos de un espacio de nombres o los miembros de un tipo) deben ser únicos, excepto los nombres que se resuelven a través de la sobrecarga. Este requisito es más estricto que el del sistema de tipos comunes, que permite a varios miembros de un ámbito tener nombres idénticos siempre que sean diferentes tipos de miembros (por ejemplo, que uno sea un método y otro, un campo). En particular, en el caso de los miembros de tipo:

- Los campos y los tipos anidados solo se distinguen por el nombre.

- Los métodos, las propiedades y los eventos que tienen el mismo nombre deben distinguirse por algo más que el tipo de valor devuelto.

En el ejemplo siguiente se muestra el requisito que establece que los nombres de miembro deben ser únicos dentro de su ámbito. En este ejemplo se define una clase denominada `Converter`, que incluye cuatro miembros denominados `Conversion`. Tres son métodos y uno es una propiedad. El método que incluye un parámetro <xref:System.Int64> recibe un nombre único, pero no ocurre lo mismo con los dos métodos que tienen un parámetro <xref:System.Int32>, ya que el valor devuelto no se considera parte de la signatura del miembro. La propiedad `Conversion` también infringe este requisito, ya que las propiedades no pueden tener el mismo nombre que los métodos sobrecargados.

[!code-csharp[Conceptual.CLSCompliant#19](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/naming3.cs#19)]
[!code-vb[Conceptual.CLSCompliant#19](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/naming3.vb#19)]

Todos los lenguajes contienen palabras claves únicas, de modo que los lenguajes dirigidos a Common Language Runtime también deben proporcionar un mecanismo para hacer referencia a identificadores (como nombres de tipo) que coincidan con las palabras clave. Por ejemplo, `case` es una palabra clave en C# y Visual Basic. Sin embargo, en el siguiente ejemplo de Visual Basic se elimina la ambigüedad entre una clase denominada `case` y la palabra clave `case` mediante llaves de apertura y cierre. De lo contrario, el ejemplo produciría el mensaje de error "Una palabra clave no es válida como identificador" y no se compilaría.

[!code-vb[Conceptual.CLSCompliant#22](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/keyword1.vb#22)]

En el siguiente ejemplo de C# se crean instancias de la clase `case` utilizando el símbolo `@` para eliminar la ambigüedad entre el identificador y la palabra clave del lenguaje. Sin él, el compilador de C# mostraría dos mensajes de error similares a los siguientes: "Se esperaba un tipo" y "'Término 'case' de expresión no válido".

[!code-csharp[Conceptual.CLSCompliant#23](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/keyword2.cs#23)]

<a name="conversion"></a>

### <a name="type-conversion"></a>Conversión de tipos

Common Language Specification define dos operadores de conversión:

- `op_Implicit`, que se utiliza en las conversiones de ampliación que no dan lugar a la pérdida de datos o de precisión. Por ejemplo, la estructura <xref:System.Decimal> contiene un operador sobrecargado `op_Implicit` para convertir valores de tipos enteros y valores <xref:System.Char> en valores <xref:System.Decimal>.

- `op_Explicit`, que se utiliza en las conversiones de restricción que pueden producir una pérdida de magnitud (un valor se convierte en un valor que tiene un intervalo menor) o de precisión. Por ejemplo, la estructura <xref:System.Decimal> contiene un operador sobrecargado `op_Explicit` para convertir los valores <xref:System.Double> y <xref:System.Single> en <xref:System.Decimal> y convertir <xref:System.Decimal> en los valores integrales <xref:System.Double>, <xref:System.Single> y <xref:System.Char>.

Sin embargo, no todos los lenguajes admiten la sobrecarga de operadores o la definición de operadores personalizados. Si decide implementar estos operadores de conversión, debe proporcionar un mecanismo alternativo para realizar la conversión. Se recomienda proporcionar los métodos `From`*Xxx* y `To`*Xxx*.

En el ejemplo siguiente se definen conversiones implícitas y explícitas conformes a CLS. En este ejemplo, se crea una clase `UDouble` que representa un número de punto flotante con signo de precisión doble. En las conversiones implícitas, pasa de `UDouble` a <xref:System.Double> y, en las conversiones explícitas, de `UDouble` a <xref:System.Single>, de <xref:System.Double> a `UDouble` y de <xref:System.Single> a `UDouble`. También define un método `ToDouble` como alternativa al operador de conversión implícita y los métodos `ToSingle`, `FromDouble` y `FromSingle` como alternativas a los operadores de conversión explícitos.

[!code-csharp[Conceptual.CLSCompliant#15](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/convert1.cs#15)]
[!code-vb[Conceptual.CLSCompliant#15](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/convert1.vb#15)]

<a name="arrays"></a>

### <a name="arrays"></a>Matrices

Las matrices conformes a CLS cumplen las reglas siguientes:

- Todas las dimensiones de una matriz deben tener un límite inferior igual a cero. En el ejemplo siguiente se crea una matriz no conforme a CLS cuyo límite inferior es uno. Observe que, a pesar de la presencia del atributo <xref:System.CLSCompliantAttribute>, el compilador no detecta que la matriz devuelta por el método `Numbers.GetTenPrimes` no es conforme a CLS.

  [!code-csharp[Conceptual.CLSCompliant#8](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/array1.cs#8)]
  [!code-vb[Conceptual.CLSCompliant#8](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/array1.vb#8)]

- Todos los elementos de la matriz deben componerse de tipos conformes a CLS. En el ejemplo siguiente se definen dos métodos que devuelven matrices no conformes a CLS. El primero devuelve una matriz de valores <xref:System.UInt32>. El segundo devuelve una matriz <xref:System.Object> que contiene los valores <xref:System.Int32> y <xref:System.UInt32>. Aunque el compilador identifica la primera matriz como no conforme debido a su tipo <xref:System.UInt32>, no reconoce que la segunda matriz incluye elementos no conformes a CLS.

  [!code-csharp[Conceptual.CLSCompliant#9](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/array2.cs#9)]
  [!code-vb[Conceptual.CLSCompliant#9](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/array2.vb#9)]

- La resolución de desbordamiento de los métodos que tienen parámetros de matriz se basa en el hecho de que son matrices y en su tipo de elemento. Por esta razón, la siguiente definición de un método `GetSquares` sobrecargado es conforme a CLS.

  [!code-csharp[Conceptual.CLSCompliant#10](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/array3.cs#10)]
  [!code-vb[Conceptual.CLSCompliant#10](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/array3.vb#10)]

<a name="Interfaces"></a>

### <a name="interfaces"></a>Interfaces

Las interfaces conformes a CLS pueden definir propiedades, eventos y métodos virtuales (métodos sin implementación). Una interfaz conforme a CLS no puede tener ninguno de los elementos siguientes:

- Métodos estáticos o campos estáticos. Los compiladores de C# y Visual Basic generan errores de compilación si se define un miembro estático en una interfaz.

- Campos. Los compiladores de C# y Visual Basic generan errores de compilación si se define un campo en una interfaz.

- Métodos que no son conformes a CLS. Por ejemplo, la siguiente definición de interfaz incluye un método, `INumber.GetUnsigned`, que está marcado como no conforme a CLS. Este ejemplo genera una advertencia del compilador.

  [!code-csharp[Conceptual.CLSCompliant#6](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/interface2.cs#6)]
  [!code-vb[Conceptual.CLSCompliant#6](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/interface2.vb#6)]

  Debido a esta regla, no se necesitan tipos conformes a CLS para implementar miembros no conformes a CLS. Si un marco conforme a CLS expone una clase que implementa una interfaz no conforme a CLS, también debe proporcionar implementaciones concretas de todos los miembros no conformes a CLS.

Los compiladores de lenguaje conformes a CLS también deben permitir que una clase proporcione implementaciones independientes de miembros con el mismo nombre y la misma signatura en varias interfaces.  C# y Visual Basic admiten [implementaciones de interfaz explícitas](../csharp/programming-guide/interfaces/explicit-interface-implementation.md) para proporcionar diferentes implementaciones de métodos con el mismo nombre. Visual Basic también admite la palabra clave `Implements`, que permite designar explícitamente qué interfaz y miembro implementa un determinado miembro. En el ejemplo siguiente se muestra este escenario con la definición de una clase `Temperature` que implementa las interfaces `ICelsius` y `IFahrenheit` como implementaciones de interfaces explícitas.

[!code-csharp[Conceptual.CLSCompliant#24](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/eii1.cs#24)]
[!code-vb[Conceptual.CLSCompliant#24](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/eii1.vb#24)]

<a name="enums"></a>

### <a name="enumerations"></a>Enumeraciones

Las enumeraciones conformes a CLS deben seguir estas reglas:

- El tipo subyacente de una enumeración debe ser un entero intrínseco conforme a CLS (<xref:System.Byte>, <xref:System.Int16>, <xref:System.Int32> o <xref:System.Int64>). Por ejemplo, el código siguiente intenta definir una enumeración cuyo tipo subyacente es <xref:System.UInt32> y genera una advertencia del compilador.

  [!code-csharp[Conceptual.CLSCompliant#7](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/enum3.cs#7)]
  [!code-vb[Conceptual.CLSCompliant#7](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/enum3.vb#7)]

- Un tipo de enumeración debe tener un campo de instancia único denominado `Value__` marcado con el atributo <xref:System.Reflection.FieldAttributes.RTSpecialName?displayProperty=nameWithType>. Esto permite hacer referencia al valor del campo de forma implícita.

- Las enumeraciones incluyen campos estáticos literales del mismo tipo que el de la enumeración. Por ejemplo, si define una enumeración `State` con los valores `State.On` y `State.Off`, `State.On` y `State.Off` son campos estáticos literales cuyo tipo será `State`.

- Hay dos tipos de enumeraciones:

  - Las enumeraciones que representan un conjunto de valores enteros con nombre mutuamente excluyentes. Este tipo de enumeración se indica por la ausencia del atributo personalizado <xref:System.FlagsAttribute?displayProperty=nameWithType>.

  - Las enumeraciones que representan un conjunto de marcadores de bits que se pueden combinar para generar un valor sin nombre. Este tipo de enumeración se indica por la presencia del atributo personalizado <xref:System.FlagsAttribute?displayProperty=nameWithType>.

  Para obtener más información, consulte la documentación de la estructura <xref:System.Enum>.

- El valor de una enumeración no se limita al intervalo de sus valores especificados. Es decir, el intervalo de valores de una enumeración es el intervalo de su valor subyacente. Puede utilizar el método <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> para determinar si un valor especificado es miembro de una enumeración.

<a name="members"></a>

### <a name="type-members-in-general"></a>Miembros de tipos en general

Common Language Specification necesita todos los campos y métodos accesibles como miembros de una clase determinada. Por tanto, los métodos y los campos estáticos globales (es decir, los métodos o los campos que se definen con independencia de un tipo) no son conformes a CLS. Si intenta incluir un campo o un método global en el código fuente, tanto el compilador de C# como el de Visual Basic generarán un error de compilación.

Common Language Specification solo admite la convención de llamada administrada estándar. No admite convenciones de llamada ni métodos no administrados con listas de argumentos variables marcados con la palabra clave `varargs`. En el caso de las listas de argumentos variables que son compatibles con la convención de llamada administrada estándar, utilice el atributo <xref:System.ParamArrayAttribute> o la implementación del lenguaje específico, como la palabra clave `params` en C# y la palabra clave `ParamArray` en Visual Basic.

<a name="MemberAccess"></a>

### <a name="member-accessibility"></a>Accesibilidad de miembros

Al reemplazar un miembro heredado no se puede cambiar la accesibilidad de dicho miembro. Por ejemplo, un método público de una clase base no se puede reemplazar por un método privado de una clase derivada. Existe una excepción: un miembro `protected internal` (en C#) o `Protected Friend` (en Visual Basic) de un ensamblado que se haya reemplazado por un tipo de un ensamblado diferente. En ese caso, la accesibilidad del reemplazo es `Protected`.

En el ejemplo siguiente se muestra el error que se genera cuando el atributo <xref:System.CLSCompliantAttribute> se establece en `true` y `Human`, que es una clase derivada de `Animal`, intenta cambiar la accesibilidad de la propiedad `Species` de pública a privada. El ejemplo se compila correctamente si su accesibilidad se cambia a pública.

[!code-csharp[Conceptual.CLSCompliant#28](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/accessibility1.cs#28)]
[!code-vb[Conceptual.CLSCompliant#28](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/accessibility1.vb#28)]

Los tipos de la signatura de un miembro deben estar accesibles siempre que dicho miembro esté accesible. Esto significa, por ejemplo, que un miembro público no puede incluir un parámetro cuyo tipo sea privado, protegido o interno. En el ejemplo siguiente se muestra el error del compilador que se produce cuando un constructor de clase `StringWrapper` expone un valor de enumeración `StringOperationType` interno que determina cómo debe ajustarse un valor de cadena.

[!code-csharp[Conceptual.CLSCompliant#27](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/accessibility3.cs#27)]
[!code-vb[Conceptual.CLSCompliant#27](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/accessibility3.vb#27)]

<a name="Generics"></a>

### <a name="generic-types-and-members"></a>Miembros y tipos genéricos

Los tipos anidados siempre tienen, como mínimo, el mismo número de parámetros genéricos que el tipo envolvente. Estos se corresponden por posición con los parámetros genéricos del tipo envolvente. El tipo genérico también puede incluir nuevos parámetros genéricos.

Las relaciones entre los parámetros de tipo genérico de un tipo envolvente y sus tipos anidados se pueden ocultar en la sintaxis de cada lenguaje. En el ejemplo siguiente, un tipo genérico `Outer<T>` contiene dos clases anidadas: `Inner1A` e `Inner1B<U>`. Las llamadas al método `ToString`, donde cada clase hereda de <xref:System.Object.ToString%2A?displayProperty=nameWithType>, muestran que cada clase anidada contiene los parámetros de tipo de la clase contenedora.

[!code-csharp[Conceptual.CLSCompliant#29](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/nestedgenerics2.cs#29)]
[!code-vb[Conceptual.CLSCompliant#29](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/nestedgenerics2.vb#29)]

Los nombres de tipos genéricos se codifican con el formato *nombre\`n*, donde *nombre* es el nombre del tipo, \` es un carácter literal y *n* es el número de parámetros declarados en el tipo o, en el caso de tipos genéricos anidados, el número de parámetros de tipo recién incorporados. Esta codificación de nombres de tipo genérico tiene interés fundamentalmente para los desarrolladores que utilizan la reflexión a fin de acceder a los tipos genéricos conformes a CLS de una biblioteca.

Si las restricciones se aplican a un tipo genérico, los tipos utilizados como restricciones también deben ser conformes a CLS. En el ejemplo siguiente se define una clase denominada `BaseClass` que no es conforme a CLS y una clase genérica denominada `BaseCollection` cuyo parámetro de tipo debe derivarse de `BaseClass`. Sin embargo, puesto que `BaseClass` no es conforme a CLS, el compilador emite una advertencia.

[!code-csharp[Conceptual.CLSCompliant#34](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/generics5.cs#34)]
[!code-vb[Conceptual.CLSCompliant#34](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/generics5.vb#34)]

Si un tipo genérico se deriva de un tipo base genérico, es necesario volver a declarar las restricciones para que se pueda garantizar que las restricciones del tipo base también se cumplen. En el ejemplo siguiente se define un objeto `Number<T>` que puede representar cualquier tipo numérico. También se define una clase `FloatingPoint<T>` que representa un valor de punto flotante. Sin embargo, el código fuente no puede compilarse, ya que no aplica la restricción de `Number<T>` (T debe ser un tipo de valor) en `FloatingPoint<T>`.

[!code-csharp[Conceptual.CLSCompliant#30](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/generics2a.cs#30)]
[!code-vb[Conceptual.CLSCompliant#30](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/generics2a.vb#30)]

El ejemplo se compila correctamente si se agrega la restricción a la clase `FloatingPoint<T>`.

[!code-csharp[Conceptual.CLSCompliant#31](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/generics2.cs#31)]
[!code-vb[Conceptual.CLSCompliant#31](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/generics2.vb#31)]

Common Language Specification impone un modelo conservador adaptado a cada instancia en los tipos anidados y los miembros protegidos. Los tipos genéricos abiertos no pueden exponer campos ni miembros con signaturas que contengan una instancia específica de un tipo genérico anidado y protegido. Los tipos no genéricos que amplíen una instancia específica de una interfaz o clase base genérica no pueden exponer campos ni miembros con signaturas que contengan otra instancia de un tipo genérico anidado y protegido.

En el ejemplo siguiente se define un tipo genérico, `C1<T>` (o `C1(Of T)` en Visual Basic) y una clase protegida, `C1<T>.N` (o `C1(Of T).N` en Visual Basic). `C1<T>` tiene dos métodos: `M1` y `M2`. Sin embargo, `M1` no es conforme a CLS porque intenta devolver un objeto `C1<int>.N` (o `C1(Of Integer).N`) a partir de C1\<T> (o `C1(Of T)`). Una segunda clase, `C2`, se deriva de `C1<long>` (o `C1(Of Long)`). Esta clase tiene dos métodos, `M3` y `M4`. El objeto `M3` no es conforme a CLS porque intenta devolver un objeto `C1<int>.N` (o `C1(Of Integer).N`) a partir de una subclase de `C1<long>`. Observe que los compiladores del lenguaje pueden ser aun más restrictivos. En este ejemplo, Visual Basic muestra un error cuando intenta compilar `M4`.

[!code-csharp[Conceptual.CLSCompliant#32](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/generics4.cs#32)]
[!code-vb[Conceptual.CLSCompliant#32](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/generics4.vb#32)]

<a name="ctors"></a>

### <a name="constructors"></a>Constructores

Los constructores de clases y estructuras conformes a CLS deben seguir estas reglas:

- Un constructor de una clase derivada debe llamar al constructor de instancia de su clase base antes de tener acceso a datos de instancia heredados. Este requisito se debe al hecho de que los constructores de clase base no se heredan por sus clases derivadas. Esta regla no se aplica a las estructuras, que no admiten la herencia directa.

  Normalmente, los compiladores aplican esta regla independientemente de la conformidad con CLS, como se muestra en el ejemplo siguiente. En este ejemplo, se crea una clase `Doctor` que se deriva de una clase `Person`, pero la clase `Doctor` no consigue llamar al constructor de la clase `Person` para inicializar los campos de instancia heredados.

  [!code-csharp[Conceptual.CLSCompliant#11](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/ctor1.cs#11)]
  [!code-vb[Conceptual.CLSCompliant#11](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/ctor1.vb#11)]

- No se puede llamar a un constructor de objetos excepto para crear un objeto. Además, un objeto no se puede inicializar dos veces. Esto significa, por ejemplo, que el método <xref:System.Object.MemberwiseClone%2A?displayProperty=nameWithType> y los métodos de deserialización, como <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>, no deben llamar a constructores.

<a name="properties"></a>

### <a name="properties"></a>Propiedades

Las propiedades de los tipos conformes a CLS deben seguir estas reglas:

- Una propiedad debe tener un establecedor, un captador o ambos. En un ensamblado, estos elementos se implementan como métodos especiales, lo que significa que aparecerán como métodos independientes (el captador se llama `get_`*propertyname* y el establecedor es `set_`*propertyname*) marcados como `SpecialName` en los metadatos del ensamblado. Los compiladores de C# y Visual Basic aplican esta regla automáticamente sin necesidad de aplicar el atributo <xref:System.CLSCompliantAttribute>.

- El tipo de una propiedad es el tipo de valor devuelto del captador de la propiedad y el último argumento del establecedor. Estos tipos deben ser conformes a CLS y los argumentos no se pueden asignar a la propiedad por referencia (es decir, no pueden ser punteros administrados).

- Si una propiedad tiene un captador y un establecedor, estos deben ser virtuales, estáticos o de instancia. Los compiladores de C# y Visual Basic aplican automáticamente esta regla a través de la sintaxis de definición de la propiedad.

<a name="events"></a>

### <a name="events"></a>Events

Un evento se define por su nombre y su tipo. El tipo de evento es un delegado que se utiliza para indicar el evento. Por ejemplo, el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> es del tipo <xref:System.ResolveEventHandler>. Además del propio evento, hay tres métodos con nombres basados en el nombre de evento que proporcionan la implementación del evento y que se marcan como `SpecialName` en los metadatos de ensamblado:

- Un método para agregar un controlador de eventos, llamado `add_`*EventName*. Por ejemplo, el método de suscripción de eventos del evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> se denomina `add_AssemblyResolve`.

- Un método para quitar un controlador de eventos, llamado `remove_`*EventName*. Por ejemplo, el método de eliminación del evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> se denomina `remove_AssemblyResolve`.

- Un método para indicar que el evento se produjo, llamado `raise_`*EventName*.

> [!NOTE]
> La mayoría de las reglas de Common Language Specification relacionadas con los eventos se implementan mediante compiladores del lenguaje y son transparentes para los desarrolladores de componentes.

Los métodos para agregar, quitar y generar el evento deben tener la misma accesibilidad. Además, todos deben ser estáticos, virtuales o de instancia. Los métodos para agregar y quitar un evento tienen un parámetro cuyo tipo es el mismo que el del delegado de eventos. Los métodos para agregar y quitar deben estar presentes o ausentes al mismo tiempo.

En el ejemplo siguiente se define una clase conforme a CLS denominada `Temperature` que genera un evento `TemperatureChanged` si el cambio de temperatura entre dos lecturas es igual o mayor que el valor de umbral. La clase `Temperature` define de manera explícita un método `raise_TemperatureChanged` para que pueda ejecutar controladores de eventos de forma selectiva.

[!code-csharp[Conceptual.CLSCompliant#20](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/event1.cs#20)]
[!code-vb[Conceptual.CLSCompliant#20](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/event1.vb#20)]

<a name="overloads"></a>

### <a name="overloads"></a>Overloads

Common Language Specification impone los siguientes requisitos a los miembros sobrecargados:

- Los miembros se pueden sobrecargar según el número de parámetros y el tipo de cualquiera de los parámetros. A la hora de distinguir entre sobrecargas, no se tienen en cuenta los factores de convención de llamada, el tipo de valor devuelto, los modificadores personalizados aplicados al método o a su parámetro, ni si los parámetros se pasan por valor o por referencia. Para consultar un ejemplo, vea el código del requisito que establece que los nombres deben ser únicos en cada ámbito que se incluye en la sección [Convenciones de nomenclatura](#naming).

- Solo las propiedades y los métodos se pueden sobrecargar. Los campos y eventos no se pueden sobrecargar.

- Los métodos genéricos pueden sobrecargarse en función del número de parámetros genéricos.

> [!NOTE]
> Los operadores `op_Explicit` y `op_Implicit` son una excepción de la regla que establece que el valor devuelto no se considera parte de la signatura de un método en la resolución de la sobrecarga. Estos dos operadores se pueden sobrecargar según sus parámetros y su valor devuelto.

<a name="exceptions"></a>

### <a name="exceptions"></a>Excepciones

Los objetos de excepción deben derivar de <xref:System.Exception?displayProperty=nameWithType> o de otro tipo derivado de <xref:System.Exception?displayProperty=nameWithType>. En el ejemplo siguiente se muestra el error de compilador que se produce cuando una clase personalizada denominada `ErrorClass` se utiliza para el control de excepciones.

[!code-csharp[Conceptual.CLSCompliant#13](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/exceptions1.cs#13)]
[!code-vb[Conceptual.CLSCompliant#13](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/exceptions1.vb#13)]

Para corregir este error, la clase `ErrorClass` debe heredar de <xref:System.Exception?displayProperty=nameWithType>. Además, la propiedad `Message` debe invalidarse. En el ejemplo siguiente se corrigen estos errores para definir una clase `ErrorClass` que sea conforme a CLS.

[!code-csharp[Conceptual.CLSCompliant#14](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/exceptions2.cs#14)]
[!code-vb[Conceptual.CLSCompliant#14](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/exceptions2.vb#14)]

<a name="attributes"></a>

### <a name="attributes"></a>Atributos

En los ensamblados de .NET, los atributos personalizados proporcionan un mecanismo extensible para almacenar atributos personalizados y recuperar metadatos sobre objetos de programación, como ensamblados, tipos, miembros y parámetros de métodos. Los atributos personalizados deben derivar de <xref:System.Attribute?displayProperty=nameWithType> o de un tipo derivado de <xref:System.Attribute?displayProperty=nameWithType>.

En el ejemplo siguiente se infringe esta regla. Define una clase `NumericAttribute` que no se deriva de <xref:System.Attribute?displayProperty=nameWithType>. Tenga en cuenta que un error del compilador solo se produce cuando se aplica el atributo no conforme a CLS, y no cuando se define la clase.

[!code-csharp[Conceptual.CLSCompliant#18](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/attribute1.cs#18)]
[!code-vb[Conceptual.CLSCompliant#18](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/attribute1.vb#18)]

El constructor o las propiedades de un atributo conforme a CLS pueden exponer solo los tipos siguientes:

- <xref:System.Boolean>

- <xref:System.Byte>

- <xref:System.Char>

- <xref:System.Double>

- <xref:System.Int16>

- <xref:System.Int32>

- <xref:System.Int64>

- <xref:System.Single>

- <xref:System.String>

- <xref:System.Type>

- Cualquier tipo de enumeración cuyo tipo subyacente sea <xref:System.Byte>, <xref:System.Int16>, <xref:System.Int32> o <xref:System.Int64>.

En el ejemplo siguiente se define una clase `DescriptionAttribute` que se deriva de <xref:System.Attribute>. El constructor de clase tiene un parámetro de tipo `Descriptor`, de modo que la clase no es conforme a CLS. Observe que el compilador de C# emite una advertencia, aunque realiza la compilación correctamente, mientras que el compilador de Visual Basic no emite ninguna una advertencia ni ningún error.

[!code-csharp[Conceptual.CLSCompliant#33](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/attribute2.cs#33)]
[!code-vb[Conceptual.CLSCompliant#33](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/attribute2.vb#33)]

<a name="CLSAttribute"></a>

## <a name="the-clscompliantattribute-attribute"></a>CLSCompliantAttribute (Atributo)

El atributo <xref:System.CLSCompliantAttribute> se usa para indicar si un elemento del programa es conforme a Common Language Specification. El constructor <xref:System.CLSCompliantAttribute.%23ctor%28System.Boolean%29> contiene un único parámetro obligatorio, `isCompliant`, que indica si el elemento del programa es conforme a CLS.

En tiempo de compilación, el compilador detecta los elementos que supuestamente deberían ser conformes a CLS y emite una advertencia. El compilador no emite advertencias relacionadas con los tipos o miembros cuya no conformidad se declara explícitamente.

Los desarrolladores de componentes pueden usar el atributo <xref:System.CLSCompliantAttribute> de dos maneras:

- Para definir las partes de la interfaz pública expuestas por un componente que son conformes a CLS y las que no lo son. Cuando el atributo se usa para marcar determinados elementos del programa como conformes a CLS, su uso garantiza que esos elementos sean accesibles desde todos los lenguajes y herramientas que tienen como destino .NET.

- Para garantizar que la interfaz pública de la biblioteca de componentes expone solo elementos del programa que son conformes a CLS. Si los elementos no son conformes a CLS, los compiladores normalmente emitirán una advertencia.

> [!WARNING]
> En algunos casos, los compiladores de lenguaje aplican reglas conformes a CLS independientemente de si se usa el atributo <xref:System.CLSCompliantAttribute> o no. Por ejemplo, la definición de un miembro estático en una interfaz infringe una regla de CLS. En este sentido, si se define un miembro `static` (en C#) o `Shared` (en Visual Basic) en una interfaz, los compiladores de C# y Visual Basic mostrarán un mensaje de error y no podrán compilar la aplicación.

El atributo <xref:System.CLSCompliantAttribute> está marcado con un atributo <xref:System.AttributeUsageAttribute> que tiene el valor <xref:System.AttributeTargets.All?displayProperty=nameWithType>. Este valor le permite aplicar el atributo <xref:System.CLSCompliantAttribute> a cualquier elemento de programa, incluidos los ensamblados, módulos, tipos (clases, estructuras, enumeraciones, interfaces, delegados), miembros de tipo (constructores, métodos, propiedades, campos y eventos), parámetros, parámetros genéricos y valores devueltos. Sin embargo, en la práctica, solo debe aplicar el atributo a los ensamblados, tipos y miembros del tipo. De lo contrario, los compiladores omitirán el atributo y seguirán generando advertencias de compilación siempre que encuentren un parámetro no conforme, un parámetro genérico o un valor devuelto en la interfaz pública de la biblioteca.

El valor del atributo <xref:System.CLSCompliantAttribute> lo heredan los elementos del programa contenidos. Por ejemplo, si se marca un ensamblado como conforme a CLS, sus tipos también son conformes a CLS. Si un tipo se marca como conforme a CLS, sus tipos anidados y miembros también serán conformes a CLS.

Puede invalidar explícitamente la conformidad heredada aplicando el atributo <xref:System.CLSCompliantAttribute> a un elemento del programa contenido. Por ejemplo, puede utilizar el atributo <xref:System.CLSCompliantAttribute> con el valor `isCompliant` establecido en `false` para definir un tipo no conforme en un ensamblado conforme, y puede utilizar el atributo con el valor `isCompliant` establecido en `true` para definir un tipo conforme en un ensamblado no conforme. También puede definir miembros no conformes en un tipo conforme. Sin embargo, un tipo no conforme no puede tener miembros conformes, por lo que no puede utilizar el atributo con el valor `isCompliant` establecido en `true` para invalidar la herencia de un tipo no conforme.

Cuando desarrolle componentes, debe utilizar siempre el atributo <xref:System.CLSCompliantAttribute> para indicar si el ensamblado, sus tipos y sus miembros son conformes a CLS.

Para crear componentes conformes a CLS:

1. Utilice <xref:System.CLSCompliantAttribute> para marcar el ensamblado como conforme a CLS.

2. Marque como no conforme los tipos expuestos públicamente en el ensamblado que no sean conformes a CLS.

3. Marque como no conforme los miembros expuestos públicamente en tipos conformes a CLS.

4. Proporcione una alternativa conforme a CLS para los miembros que no sean conformes a CLS.

Si ha marcado correctamente todos los tipos y miembros no conformes, el compilador no debe emitir ninguna advertencia de no conformidad. Sin embargo, debe indicar qué miembros no son conformes a CLS y mostrar las alternativas conformes a CLS en la documentación del producto.

En el ejemplo siguiente se usa el atributo <xref:System.CLSCompliantAttribute> para definir un ensamblado conforme a CLS y un tipo, `CharacterUtilities`, que tiene dos miembros no conformes a CLS. Dado que ambos miembros están etiquetados con el atributo `CLSCompliant(false)`, el compilador no genera ninguna advertencia. La clase también proporciona una alternativa conforme a CLS para ambos métodos. Por lo general, simplemente se agregarían dos sobrecargas al método `ToUTF16` para proporcionar alternativas conformes a CLS. Sin embargo, puesto que no se pueden sobrecargar los métodos en función de un valor devuelto, los nombres de los métodos conformes a CLS son distintos de los nombres de los métodos no conformes.

[!code-csharp[Conceptual.CLSCompliant#35](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/indicator3.cs#35)]
[!code-vb[Conceptual.CLSCompliant#35](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/indicator3.vb#35)]

Si está desarrollando una aplicación en lugar de una biblioteca (es decir, si no expone los tipos o miembros que pueden consumir otros desarrolladores de aplicaciones), la conformidad con CLS de los elementos del programa usados por la aplicación solo tendrá interés si su lenguaje admite estos elementos. En ese caso, el compilador del lenguaje generará un error cuando intente utilizar un elemento no conforme a CLS.

<a name="CrossLang"></a>

## <a name="cross-language-interoperability"></a>Interoperabilidad entre lenguajes

La independencia de lenguaje tiene varios significados posibles. Un significado, descrito en el artículo [Independencia del lenguaje y componentes independientes del lenguaje](language-independence-and-language-independent-components.md), implica el uso sin problemas de tipos escritos en un lenguaje desde una aplicación escrita en otro lenguaje. Un segundo significado, que es el descrito en este artículo, implica combinar código escrito en varios lenguajes en un único ensamblado de .NET.

El ejemplo siguiente muestra la interoperabilidad entre lenguajes creando una biblioteca de clases de denominada Utilities.dll que incluye dos clases, `NumericLib` y `StringLib`. La clase `NumericLib` está escrita en C#, y la clase `StringLib` está escrita en Visual Basic. A continuación se muestra el código fuente para StringUtil.vb, que incluye un solo miembro, `ToTitleCase`, en su clase `StringLib`.

[!code-vb[Conceptual.CrossLanguage#1](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.crosslanguage/vb/stringutil.vb#1)]

A continuación se muestra el código fuente para NumberUtil.cs, que define una clase `NumericLib` con dos miembros, `IsEven` y `NearZero`.

[!code-csharp[Conceptual.CrossLanguage#2](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.crosslanguage/cs/numberutil.cs#2)]

Para empaquetar las dos clases en un solo ensamblado, debe compilarlas en módulos. Para compilar el archivo de código fuente de Visual Basic en un módulo, use este comando:

```console
vbc /t:module StringUtil.vb
```

Para más información sobre la sintaxis de la línea de comandos del compilador de Visual Basic, consulte [Compilación desde la línea de comandos](../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).

Para compilar el archivo de código fuente de C# en un módulo, use este comando:

```console
csc /t:module NumberUtil.cs
```

Para más información sobre la sintaxis de la línea de comandos del compilador de C#, consulte [Compilación de la línea de comandos con csc.exe](../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).

Utilice luego las [opciones del enlazador](/cpp/build/reference/linker-options) para compilar los dos módulos en un ensamblado:

```console
link numberutil.netmodule stringutil.netmodule /out:UtilityLib.dll /dll
```

El ejemplo siguiente llama a los métodos `NumericLib.NearZero` y `StringLib.ToTitleCase`. Observe que el código de Visual Basic y el código de C# pueden tener acceso a los métodos en ambas clases.

[!code-csharp[Conceptual.CrossLanguage#3](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.crosslanguage/cs/useutilities1.cs#3)]
[!code-vb[Conceptual.CrossLanguage#3](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.crosslanguage/vb/useutilities1.vb#3)]

Para compilar el código de Visual Basic, use este comando:

```console
vbc example.vb /r:UtilityLib.dll
```

Para compilar con C#, cambie el nombre del compilador de **vbc** a **csc** y cambie la extensión de archivo .vb a .cs:

```console
csc example.cs /r:UtilityLib.dll
```

## <a name="see-also"></a>Vea también

- <xref:System.CLSCompliantAttribute>
