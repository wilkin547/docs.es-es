---
title: 'Definición de tipos y sus miembros: un recorrido por C#'
description: Los bloques de creación de los programas son los tipos. Aprenda a crear clases, estructuras, interfaces y mucho más en C#.
ms.date: 08/06/2020
ms.openlocfilehash: b1ce24611fec6fdf01d5ecb8d6ae974e147c78c5
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "99216608"
---
# <a name="types-and-members"></a>Tipos y miembros

En cuanto lenguaje orientado a objetos, C# admite los conceptos de encapsulación, herencia y polimorfismo. Una clase puede heredar directamente de una clase primaria e implementar cualquier número de interfaces. Los métodos que invalidan los métodos virtuales en una clase primaria requieren la palabra clave `override` como una manera de evitar redefiniciones accidentales. En C#, un struct es como una clase ligera; es un tipo asignado en la pila que puede implementar interfaces pero que no admite la herencia. C# también proporciona registros, que son tipos de clase cuyo propósito es, principalmente, almacenar valores de datos.

## <a name="classes-and-objects"></a>Clases y objetos

Las *clases* son los tipos más fundamentales de C#. Una clase es una estructura de datos que combina estados (campos) y acciones (métodos y otros miembros de función) en una sola unidad. Una clase proporciona una definición para *instancias* de la clase, también conocidas como *objetos*. Las clases admiten *herencia* y *polimorfismo*, mecanismos por los que las *clases derivadas* pueden extender y especializar *clases base*.

Las clases nuevas se crean mediante declaraciones de clase. Una declaración de clase comienza con un encabezado. El encabezado especifica lo siguiente:

- Atributos y modificadores de la clase
- Nombre de la clase
- Clase base (al heredar de una [clase base](#base-classes))
- Interfaces implementadas por la clase

Al encabezado le sigue el cuerpo de la clase, que consta de una lista de declaraciones de miembros escritas entre los delimitadores `{` y `}`.

En el código siguiente se muestra una declaración de una clase simple denominada `Point`:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="PointClass":::

Las instancias de clases se crean mediante el operador `new`, que asigna memoria para una nueva instancia, invoca un constructor para inicializar la instancia y devuelve una referencia a la instancia. Las instrucciones siguientes crean dos objetos `Point` y almacenan las referencias en esos objetos en dos variables:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="CreatePoints":::

La memoria ocupada por un objeto se reclama automáticamente cuando el objeto ya no es accesible. En C#, no es necesario ni posible desasignar objetos de forma explícita.

### <a name="type-parameters"></a>Parámetros de tipo

Las clases genéricas definen [***parámetros de tipo** _](../programming-guide/generics/index.md). Los parámetros de tipo son una lista de nombres de parámetros de tipo entre paréntesis angulares. Los parámetros de tipo siguen el nombre de la clase. Los parámetros de tipo pueden usarse luego en el cuerpo de las declaraciones de clase para definir a los miembros de la clase. En el ejemplo siguiente, los parámetros de tipo de `Pair` son `TFirst` y `TSecond`:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="DefinePairClass":::

Un tipo de clase que se declara para tomar parámetros de tipo se denomina _tipo de clase genérica*. Los tipos de estructura, interfaz y delegado también pueden ser genéricos.
Cuando se usa la clase genérica, se deben proporcionar argumentos de tipo para cada uno de los parámetros de tipo:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="CreatePairObject":::

Un tipo genérico con argumentos de tipo proporcionado, como `Pair<int,string>` anteriormente, se conoce como *tipo construido*.

### <a name="base-classes"></a>Clases base

Una declaración de clase puede especificar una clase base. Tras el nombre de clase y los parámetros de tipo, agregue un signo de dos puntos y el nombre de la clase base. Omitir una especificación de la clase base es igual que derivarla del tipo `object`. En el ejemplo siguiente, la clase base de `Point3D` es `Point`. En el primer ejemplo, la clase base de `Point` es `object`:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="Create3DPoint":::

Una clase hereda a los miembros de su clase base. La herencia significa que una clase contiene implícitamente casi todos los miembros de su clase base. Una clase no hereda la instancia, los constructores estáticos ni el finalizador. Una clase derivada puede agregar nuevos miembros a aquellos de los que hereda, pero no puede quitar la definición de un miembro heredado. En el ejemplo anterior, `Point3D` hereda los miembros `X` y `Y` de `Point`, y cada instancia de `Point3D` contiene tres miembros: `X`, `Y` y `Z`.

Existe una conversión implícita de un tipo de clase a cualquiera de sus tipos de clase base. Una variable de un tipo de clase puede hacer referencia a una instancia de esa clase o a una instancia de cualquier clase derivada. Por ejemplo, dadas las declaraciones de clase anteriores, una variable de tipo `Point` puede hacer referencia a una instancia de `Point` o `Point3D`:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="ImplicitCastToBase":::

## <a name="structs"></a>Estructuras

Las clases definen tipos que admiten la herencia y el polimorfismo. Permiten crear comportamientos sofisticados basados en jerarquías de clases derivadas. Por el contrario, los tipos [***struct** _](../language-reference/builtin-types/struct.md) son tipos más sencillos cuyo propósito principal es almacenar valores de datos. Dichos tipos struct no pueden declarar un tipo base; se derivan implícitamente de <xref:System.ValueType?displayProperty=nameWithType>. No se pueden derivar otros tipos de `struct` a partir de un tipo de `struct`. Están sellados implícitamente.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="PointStruct":::

## <a name="interfaces"></a>Interfaces

Una [_*_interfaz_*_](../programming-guide/interfaces/index.md) define un contrato que se puede implementar mediante clases y estructuras. Una interfaz puede contener métodos, propiedades, eventos e indexadores. Normalmente, una interfaz no proporciona implementaciones de los miembros que define, sino que simplemente especifica los miembros que se deben proporcionar mediante clases o estructuras que implementan la interfaz.

Las interfaces pueden usar la _*_herencia múltiple_*_. En el ejemplo siguiente, la interfaz `IComboBox` hereda de `ITextBox` y `IListBox`.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="FirstInterfaces":::

Las clases y los structs pueden implementar varias interfaces. En el ejemplo siguiente, la clase `EditBox` implementa `IControl` y `IDataBound`.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="ImplementInterfaces":::

Cuando una clase o un struct implementan una interfaz determinada, las instancias de esa clase o struct se pueden convertir implícitamente a ese tipo de interfaz. Por ejemplo

:::code language="csharp" source="./snippets/shared/Types.cs" ID="UseInterfaces":::

## <a name="enums"></a>Enumeraciones

Un tipo de [_*_enumeración_*_](../language-reference/builtin-types/enum.md) define un conjunto de valores constantes. En el elemento `enum` siguiente se declaran constantes que definen diferentes verduras de raíz:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="EnumDeclaration":::

También puede definir un elemento `enum` que se usará de forma combinada como marcas. La declaración siguiente declara un conjunto de marcas para las cuatro estaciones. Se puede aplicar cualquier combinación de estaciones, incluido un valor `All` que incluya todas las estaciones:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="FlagsEnumDeclaration":::

En el ejemplo siguiente se muestran las declaraciones de ambas enumeraciones anteriores:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="UsingEnums":::

## <a name="nullable-types"></a>Tipos que aceptan valores NULL

Las variables de cualquier tipo se pueden declarar como _*_que no aceptan valores NULL_*_ o _*_que admiten un valor NULL_*_. Una variable que acepta valores NULL puede contener un valor `null` adicional que no indica valor alguno. Los tipos de valor que aceptan valores NULL (estructuras o enumeraciones) se representan mediante <xref:System.Nullable%601?displayProperty=nameWithType>. Los tipos de referencia que no aceptan valores NULL y los que sí aceptan valores NULL se representan mediante el tipo de referencia subyacente. La distinción se representa mediante metadatos leídos por el compilador y algunas bibliotecas. El compilador proporciona advertencias cuando se desreferencian las referencias que aceptan valores NULL sin comprobar primero su valor con `null`. El compilador también proporciona advertencias cuando las referencias que no aceptan valores NULL se asignan a un valor que puede ser `null`. En el ejemplo siguiente se declara un elemento _*_int que admite un valor NULL_*_, y que se inicializa en `null`. A continuación, establece el valor en `5`. Muestra el mismo concepto con una _*_cadena que admite un valor NULL_*_. Para más información, consulte [Tipos de valor que admiten un valor NULL](../language-reference/builtin-types/nullable-value-types.md) y [Tipos de referencia que aceptan valores NULL](../nullable-references.md).

:::code language="csharp" source="./snippets/shared/Types.cs" ID="DeclareNullable":::

## <a name="tuples"></a>Tuplas

C# admite [_ *_tuplas_**](../language-reference/builtin-types/value-tuples.md), lo que proporciona una sintaxis concisa para agrupar varios elementos de datos en una estructura de datos ligera. Puede crear una instancia de una tupla declarando los tipos y los nombres de los miembros entre `(` y `)`, como se muestra en el ejemplo siguiente:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="DeclareTuples":::

Las tuplas proporcionan una alternativa para la estructura de datos con varios miembros sin usar los bloques de creación que se describen en el siguiente artículo.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](program-building-blocks.md)
