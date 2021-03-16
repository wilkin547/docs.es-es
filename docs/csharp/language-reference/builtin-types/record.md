---
title: Registros (referencia de C#)
description: Obtenga información sobre el tipo de registro en C#.
ms.date: 02/25/2021
f1_keywords:
- record_CSharpKeyword
helpviewer_keywords:
- record keyword [C#]
- record type [C#]
ms.openlocfilehash: 10fe7bcc1f3239b7a6bde0abcac41b177467cf0a
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102260039"
---
# <a name="records-c-reference"></a>Registros (referencia de C#)

A partir de C# 9, se usa la palabra clave `record` para definir un [tipo de referencia](reference-types.md) que proporciona funcionalidad integrada para encapsular los datos. Puede crear tipos de registros con propiedades inmutables mediante parámetros posicionales o sintaxis de propiedades estándar:

:::code language="csharp" source="snippets/shared/RecordType.cs" id="PositionalRecord":::
:::code language="csharp" source="snippets/shared/RecordType.cs" id="ImmutableRecord":::

También puede crear tipos de registros con propiedades y campos mutables:

:::code language="csharp" source="snippets/shared/RecordType.cs" id="MutableRecord":::

Aunque los registros pueden ser mutables, están destinados principalmente a admitir modelos de datos inmutables. El tipo de registro ofrece las siguientes características:

* [Sintaxis concisa para crear un tipo de referencia con propiedades inmutables](#positional-syntax-for-property-definition)
* Comportamiento integrado útil para un tipo de referencia centrado en datos:
  * [Igualdad de valores](#value-equality)
  * [Sintaxis concisa para la mutación no destructiva](#nondestructive-mutation)
  * [Formato integrado para la presentación](#built-in-formatting-for-display)
* [Compatibilidad con las jerarquías de herencia](#inheritance)

También puede utilizar [tipos de estructura](struct.md) para diseñar tipos centrados en datos que proporcionen igualdad de valores y un comportamiento escaso o inexistente. Pero, en el caso de los modelos de datos relativamente grandes, los tipos de estructura tienen algunas desventajas:

* No admiten la herencia.
* Son menos eficaces a la hora de determinar la igualdad de valores. En el caso de los tipos de valor, el método <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> usa la reflexión para buscar todos los campos. En el caso de los registros, el compilador genera el método `Equals`. En la práctica, la implementación de la igualdad de valores en los registros es bastante más rápida.
* Usan más memoria en algunos escenarios, ya que cada instancia tiene una copia completa de todos los datos. Los tipos de registro son [tipos de referencia](reference-types.md), por lo que una instancia de registro solo contiene una referencia a los datos.

## <a name="positional-syntax-for-property-definition"></a>Sintaxis posicional para la definición de propiedad

Puede usar parámetros posicionales para declarar propiedades de un registro e inicializar los valores de propiedad al crear una instancia:

:::code language="csharp" source="snippets/shared/RecordType.cs" id="InstantiatePositional":::

Cuando se usa la sintaxis posicional para la definición de propiedad, el compilador crea lo siguiente:

* Una propiedad pública implementada automáticamente de solo inicialización para cada parámetro posicional proporcionado en la declaración de registro. Una propiedad de [solo inicialización](../../whats-new/csharp-9.md#init-only-setters) solo se puede establecer en el constructor o mediante un inicializador de propiedad.
* Un constructor primario cuyos parámetros coinciden con los parámetros posicionales en la declaración del registro.
* Un método `Deconstruct` con un parámetro `out` para cada parámetro posicional proporcionado en la declaración de registro. Este método solo se proporciona si hay dos o más parámetros posicionales. El método deconstruye las propiedades definidas mediante la sintaxis posicional; omite las propiedades que se definen mediante la sintaxis de propiedades estándar.

Si la definición de propiedad implementada automáticamente generada no es la que desea, puede definir su propia propiedad con el mismo nombre. Si lo hace, el constructor y el deconstructor generados usarán su definición de propiedad. Por ejemplo, en el ejemplo siguiente se crea la propiedad posicional `FirstName` `internal` en lugar de `public`.

:::code language="csharp" source="snippets/shared/RecordType.cs" id="PositionalWithManualProperty":::

Un tipo de registro no tiene que declarar ninguna propiedad posicional. Puede declarar un registro sin propiedades posicionales y también campos y propiedades adicionales, como en el ejemplo siguiente:

:::code language="csharp" source="snippets/shared/RecordType.cs" id="MixedSyntax":::

Si define propiedades mediante la sintaxis de propiedades estándar, pero omite el modificador de acceso, las propiedades son `public` implícitamente.
<!-- Todo -- Explain issues surrounding use of attributes on positional properties. -->

## <a name="immutability"></a>Inmutabilidad

Un tipo de registro no es necesariamente inmutable. Puede declarar propiedades con descriptores de acceso `set` y campos que no sean `readonly`. Sin embargo, aunque los registros pueden ser mutables, facilitan la creación de modelos de datos inmutables.

La inmutabilidad puede resultar útil si necesita que un tipo centrado en datos sea seguro para subprocesos o si depende de que un código hash quede igual en una tabla hash. Sin embargo, la inmutabilidad no es adecuada para todos los escenarios de datos. Por ejemplo, [Entity Framework Core](/ef/core/) no admite la actualización con tipos de entidad inmutables.

Las propiedades de solo inicialización, tanto si se crean a partir de parámetros posicionales como al especificar descriptores de acceso `init`, tienen una *inmutabilidad superficial*. Después de la inicialización, no se puede cambiar el valor de las propiedades de tipo de valor ni la referencia de las propiedades de tipo de referencia. Sin embargo, se pueden cambiar los datos a los que hace referencia una propiedad de tipo de referencia. En el ejemplo siguiente se muestra que el contenido de una propiedad inmutable de tipo de referencia (una matriz en este caso) es mutable:

:::code language="csharp" source="snippets/shared/RecordType.cs" id="ShallowImmutability":::

Las características exclusivas de los tipos de registro se implementan mediante métodos sintetizados por el compilador, y ninguno de estos métodos pone en peligro la inmutabilidad mediante la modificación del estado del objeto.

## <a name="value-equality"></a>Igualdad de valores

La igualdad de valores significa que dos variables de un tipo de registro son iguales si los tipos coinciden y todos los valores de propiedad y campo coinciden. Para otros tipos de referencia, la igualdad significa identidad. Es decir, dos variables de un tipo de referencia son iguales si hacen referencia al mismo objeto.

Se requiere la igualdad de referencia en algunos modelos de datos. Por ejemplo, [Entity Framework Core](/ef/core/) depende de la igualdad de referencia para garantizar que solo usa una instancia de un tipo de entidad para lo que es conceptualmente una entidad. Por esta razón, los tipos de registro no son adecuados para su uso como tipos de entidad en Entity Framework Core.

En el ejemplo siguiente se muestra la igualdad de valores de tipos de registro:

:::code language="csharp" source="snippets/shared/RecordType.cs" id="Equality":::

Para implementar la igualdad de valores, el compilador sintetiza los métodos siguientes:

* Una invalidación de <xref:System.Object.Equals(System.Object)?displayProperty=nameWithType>.

  Este método se utiliza como base para el método estático <xref:System.Object.Equals(System.Object,System.Object)?displayProperty=nameWithType> cuando ambos parámetros no son NULL.

* Un método `Equals` virtual cuyo parámetro es el tipo de registro. Este método implementa <xref:System.IEquatable%601>.

* Una invalidación de <xref:System.Object.GetHashCode?displayProperty=nameWithType>.

* Invalidaciones de los operadores `==` y `!=`.

En los tipos `class`, podría invalidar manualmente los métodos y los operadores de igualdad para lograr la igualdad de valores, pero el desarrollo y las pruebas de ese código serían lentos y propensos a errores. Al tener esta funcionalidad integrada, se evitan los errores que resultarían de olvidarse de actualizar el código de invalidación personalizado cuando se agreguen o cambien propiedades o campos.

Puede escribir sus propias implementaciones para reemplazar cualquiera de estos métodos sintetizados. Si un tipo de registro tiene un método que coincide con la signatura de cualquier método sintetizado, el compilador no sintetiza ese método.

Si proporciona su propia implementación de `Equals` en un tipo de registro, proporcione también una implementación de `GetHashCode`.

## <a name="nondestructive-mutation"></a>Mutación no destructiva

Si necesita mutar propiedades inmutables de una instancia de registro, puede usar una expresión `with` para lograr una *mutación no destructiva*. Una expresión `with` crea una instancia de registro que es una copia de una instancia de registro existente, con las propiedades y los campos especificados modificados. Use la sintaxis del [inicializador de objeto](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) para especificar los valores que se van a cambiar, como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/shared/RecordType.cs" id="WithExpressions":::

La expresión `with` puede establecer propiedades posicionales o propiedades creadas con la sintaxis de propiedades estándar. Las propiedades no posicionales deben tener un descriptor de acceso `init` o `set` para cambiar en una expresión `with`.

El resultado de una expresión `with` es una *copia superficial*, lo que significa que, para una propiedad de referencia, solo se copia la referencia a una instancia. Tanto el registro original como la copia terminan con una referencia a la misma instancia.

Para implementar esta característica, el compilador sintetiza un método de clon y un constructor de copias. El constructor adopta una instancia del registro que se va a copiar y llama al método de clon. Cuando se usa una expresión `with`, el compilador crea código que llama al constructor de copia y, a continuación, establece las propiedades que se especifican en la expresión `with`.

Si necesita un comportamiento de copia diferente, puede escribir su propio constructor de copia. Si lo hace, el compilador no sintetizará un método. Cree su constructor `private` si el registro es `sealed`; de lo contrario, conviértalo en `protected`.

No puede invalidar el método de clon y no puede crear un miembro denominado `Clone`. El nombre real del método de clon lo genera el compilador.

## <a name="built-in-formatting-for-display"></a>Formato integrado para la presentación

Los tipos de registros tienen un método <xref:System.Object.ToString%2A> generado por el compilador que muestra los nombres y los valores de las propiedades y los campos públicos. El método `ToString` devuelve una cadena con el formato siguiente:

> \<record type name> { \<property name> = \<value>, \<property name> = \<value>, ...}

En el caso de los tipos de referencia, se muestra el nombre del tipo del objeto al que hace referencia la propiedad en lugar del valor de propiedad. En el ejemplo siguiente, la matriz es un tipo de referencia, por lo que se muestra `System.String[]` en lugar de los valores de los elementos de matriz reales:

```
Person { FirstName = Nancy, LastName = Davolio, ChildNames = System.String[] } 
```

Para implementar esta característica, el compilador sintetiza un método `PrintMembers` virtual y una invalidación <xref:System.Object.ToString%2A>.
La invalidación `ToString` crea un objeto <xref:System.Text.StringBuilder> con el nombre de tipo seguido de un corchete de apertura. Llama a `PrintMembers` para agregar nombres y valores de propiedad y, a continuación, agrega el corchete de cierre. En el ejemplo siguiente se muestra código similar al que contiene la invalidación sintetizada:

:::code language="csharp" source="snippets/shared/RecordType.cs" id="ToStringOverrideDefault":::

Puede proporcionar su propia implementación de `PrintMembers` o la invalidación `ToString`. En la sección [Formato `PrintMembers` en registros derivados](#printmembers-formatting-in-derived-records) que se encuentra más adelante en este artículo se proporcionan ejemplos.

## <a name="inheritance"></a>Herencia

Un registro puede heredar de otro registro. Sin embargo, un registro no puede heredar de una clase, y una clase no puede heredar de un registro.

### <a name="positional-parameters-in-derived-record-types"></a>Parámetros posicionales en tipos de registro derivados

El registro derivado declara parámetros para todos los parámetros del constructor primario del registro base. El registro base declara e inicializa esas propiedades. El registro derivado no las oculta, sino que solo crea e inicializa propiedades para los parámetros que no se han declarado en su registro base.

En el ejemplo siguiente se muestra la herencia con la sintaxis de la propiedad posicional:

:::code language="csharp" source="snippets/shared/RecordType.cs" id="PositionalInheritance":::

### <a name="equality-in-inheritance-hierarchies"></a>Igualdad en las jerarquías de herencia

Para que dos variables de registro sean iguales, el tipo en tiempo de ejecución debe ser el mismo. Los tipos de las variables contenedoras podrían ser diferentes. Esto se muestra en el siguiente código de ejemplo:

:::code language="csharp" source="snippets/shared/RecordType.cs" id="InheritanceEquality":::

En el ejemplo, todas las instancias tienen las mismas propiedades y los mismos valores de propiedad. Pero `student == teacher` devuelve `False`, aunque ambas son variables de tipo `Person`, y `student == student2` devuelve `True`, aunque una es una variable `Person` y otra es una variable `Student`.

Para implementar este comportamiento, el compilador sintetiza una propiedad `EqualityContract` que devuelve un objeto <xref:System.Type> que coincide con el tipo del registro. Esto permite a los métodos de igualdad comparar el tipo en tiempo de ejecución de los objetos cuando están comprobando la igualdad. Si el tipo base de un registro es `object`, esta propiedad es `virtual`. Si el tipo base es otro tipo de registro, la propiedad es una invalidación. Si el tipo de registro es `sealed`, esta propiedad es `sealed`.

Al comparar dos instancias de un tipo derivado, los métodos de igualdad sintetizados comprueban la igualdad de todas las propiedades de los tipos base y derivados. El método `GetHashCode` sintetizado usa el método `GetHashCode` de todas las propiedades y los campos declarados en el tipo base y el tipo de registro derivado.

### <a name="with-expressions-in-derived-records"></a>Expresiones `with` en registros derivados

Dado que el método de clon sintetizado utiliza un [tipo de valor devuelto covariante](~/_csharplang/proposals/csharp-9.0/covariant-returns.md), el resultado de una expresión `with` tiene el mismo tipo en tiempo de ejecución que el operando de la expresión. Se copian todas las propiedades del tipo en tiempo de ejecución, pero solo se pueden establecer las propiedades del tipo en tiempo de compilación, como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/shared/RecordType.cs" id="WithExpressionInheritance":::

### <a name="printmembers-formatting-in-derived-records"></a>Formato `PrintMembers` en registros derivados

El método sintetizado `PrintMembers` de un tipo de registro derivado llama a la implementación base. El resultado es que todas las propiedades y los campos públicos de los tipos derivados y base se incluyen en la salida `ToString`, como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/shared/RecordType.cs" id="ToStringInheritance":::

Puede proporcionar su propia implementación del método `PrintMembers`. Si lo hace, use la siguiente firma:

* Para un registro `sealed` que deriva de `object` (no declara un registro base): `private bool PrintMembers(StringBuilder builder)`.
* Para un registro `sealed` que deriva de otro registro: `protected sealed override bool PrintMembers(StringBuilder builder)`.
* Para un registro que no es `sealed` y que deriva del objeto: `protected virtual bool PrintMembers(StringBuilder builder);`.
* Para un registro que no es `sealed` y que deriva de otro registro: `protected override bool PrintMembers(StringBuilder builder);`.

Este es un ejemplo de código que reemplaza los métodos sintetizados `PrintMembers`, uno para un tipo de registro que deriva de un objeto y otro para un tipo de registro que deriva de otro registro:

:::code language="csharp" source="snippets/shared/RecordType.cs" id="PrintMembersImplementation":::

### <a name="deconstructor-behavior-in-derived-records"></a>Comportamiento del deconstructor en registros derivados

El método `Deconstruct` de un registro derivado devuelve los valores de todas las propiedades posicionales del tipo en tiempo de compilación. Si el tipo de variable es un registro base, solo se deconstruyen las propiedades del registro base a menos que el objeto se convierta en el tipo derivado. En el ejemplo siguiente se muestra cómo llamar a un deconstructor en un registro derivado.

:::code language="csharp" source="snippets/shared/RecordType.cs" id="DeconstructorInheritance":::

## <a name="generic-constraints"></a>Restricciones genéricas

No hay ninguna restricción genérica que requiera que un tipo sea un registro. Los registros cumplen la restricción `class`. Para realizar una restricción en una jerarquía específica de tipos de registro, coloque la restricción en el registro base como lo haría con una clase base. Para obtener más información, vea [Restricciones de tipos de parámetros](../../programming-guide/generics/constraints-on-type-parameters.md).

## <a name="c-language-specification"></a>especificación del lenguaje C#

Para más información, vea la sección [Clases](~/_csharplang/spec/classes.md) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

Para obtener más información sobre de las características presentadas en C# 9 y versiones posteriores, vea las siguientes notas de propuesta de características:

- [Registros](~/_csharplang/proposals/csharp-9.0/records.md)
- [Establecedores de solo inicialización](~/_csharplang/proposals/csharp-9.0/init.md)
- [Valores devueltos de covariante](~/_csharplang/proposals/csharp-9.0/covariant-returns.md)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Instrucciones de diseño: elección entre clase y estructura](../../../standard/design-guidelines/choosing-between-class-and-struct.md)
- [Instrucciones de diseño: diseño de estructuras](../../../standard/design-guidelines/struct.md)
- [Clases y estructuras](../../programming-guide/classes-and-structs/index.md)
- [Expresión `with`](../operators/with-expression.md)
