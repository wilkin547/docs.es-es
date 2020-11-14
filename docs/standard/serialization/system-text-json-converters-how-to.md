---
title: 'Procedimiento para escribir convertidores personalizados para la serialización de JSON: .NET'
description: Aprenda a crear convertidores personalizados para las clases de serialización de JSON que se proporcionan en el espacio de nombres System.Text.Json.
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: ba6b61232ccf7ed493fe5809e5c0b8ba21091d3d
ms.sourcegitcommit: 6bef8abde346c59771a35f4f76bf037ff61c5ba3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2020
ms.locfileid: "94329812"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a>Procedimiento para escribir convertidores personalizados para la serialización de JSON (cálculo de referencias) en .NET

En este artículo se muestra cómo crear convertidores personalizados para las clases de serialización de JSON que se proporcionan en el espacio de nombres <xref:System.Text.Json>. Para disponer de una introducción a `System.Text.Json`, vea [Cómo serializar y deserializar JSON en .NET](system-text-json-how-to.md).

Un *convertidor* es una clase que convierte un objeto o un valor en JSON; también admite conversiones a partir de este formato. El espacio de nombres `System.Text.Json` tiene convertidores integrados para la mayoría de los tipos primitivos que se asignan a primitivos de JavaScript. Puede escribir convertidores personalizados:

* Para reemplazar el comportamiento predeterminado de un convertidor integrado. Por ejemplo, puede que quiera que los valores `DateTime` se representen con el formato mm/dd/aaaa, en lugar del formato ISO 8601-1:2019 predeterminado.
* Para admitir un tipo de valor personalizado. Por ejemplo, una estructura `PhoneNumber`.

También puede escribir convertidores personalizados para personalizar o extender `System.Text.Json` con funcionalidad no incluida en la versión actual. Los siguientes escenarios se describen más adelante en este artículo:

::: zone pivot="dotnet-5-0"

* [Deserialización de tipos inferidos en las propiedades de objeto](#deserialize-inferred-types-to-object-properties).
* [Compatibilidad con la deserialización polimórfica](#support-polymorphic-deserialization).
* [Compatibilidad con el recorrido de ida y vuelta para Stack\<T>](#support-round-trip-for-stackt).
::: zone-end

::: zone pivot="dotnet-core-3-1"

* [Deserialización de tipos inferidos en las propiedades de objeto](#deserialize-inferred-types-to-object-properties).
* [Compatibilidad para diccionarios con una clave que no sea de cadena](#support-dictionary-with-non-string-key).
* [Compatibilidad con la deserialización polimórfica](#support-polymorphic-deserialization).
* [Compatibilidad con el recorrido de ida y vuelta para Stack\<T>](#support-round-trip-for-stackt).
::: zone-end

## <a name="custom-converter-patterns"></a>Patrones de convertidores personalizados

Hay dos patrones para crear un convertidor personalizado: el patrón básico y el patrón de fábrica. El patrón de fábrica es para los convertidores que controlan el tipo `Enum` o los valores genéricos abiertos. El patrón básico es para los tipos no genéricos y los tipos genéricos y cerrados.  Por ejemplo, los convertidores de los siguientes tipos requieren el patrón de fábrica:

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

Entre los ejemplos de tipos que puede controlar el patrón básico se incluyen los siguientes:

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

El patrón básico crea una clase que puede controlar un tipo. El patrón de fábrica crea una clase que determina, en tiempo de ejecución, qué tipo específico es necesario y crea dinámicamente el convertidor adecuado.

## <a name="sample-basic-converter"></a>Convertidor básico de ejemplo

El ejemplo siguiente es un convertidor que reemplaza la serialización predeterminada para un tipo de datos existente. El convertidor usa el formato mm/dd/aaaa para las propiedades `DateTimeOffset`.

[!code-csharp[](snippets/system-text-json-how-to/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a>Convertidor de patrones de fábrica de ejemplo

En el código siguiente se muestra un convertidor personalizado que funciona con `Dictionary<Enum,TValue>`. El código sigue el patrón de fábrica porque el primer parámetro de tipo genérico es `Enum` y el segundo es abierto. El método `CanConvert` devuelve `true` solo para un elemento `Dictionary` con dos parámetros genéricos, el primero de los cuales es un tipo `Enum`. El convertidor interno obtiene un convertidor existente para controlar el tipo que se proporciona en tiempo de ejecución para `TValue`.

[!code-csharp[](snippets/system-text-json-how-to/csharp/DictionaryTKeyEnumTValueConverter.cs)]

El código anterior es el mismo que el que se muestra en [Compatibilidad para diccionarios con una clave que no sea de cadena](#support-dictionary-with-non-string-key), más adelante en este artículo.

## <a name="steps-to-follow-the-basic-pattern"></a>Pasos para seguir el patrón básico

En los pasos siguientes se explica cómo crear un convertidor siguiendo el patrón básico:

* Cree una clase que derive de <xref:System.Text.Json.Serialization.JsonConverter%601>, donde `T` es el tipo que se va a serializar y deserializar.
* Reemplace el método `Read` para deserializar el JSON de entrada y convertirlo al tipo `T`. Use el elemento <xref:System.Text.Json.Utf8JsonReader> que se pasa al método para leer el JSON.
* Invalide el método `Write` para serializar el objeto de entrada de tipo `T`. Use el elemento <xref:System.Text.Json.Utf8JsonWriter> que se pasa al método para escribir el JSON.
* Reemplace el método `CanConvert` solo si es necesario. La implementación predeterminada devuelve `true` cuando el tipo que se va a convertir es de tipo `T`. Por lo tanto, los convertidores que solo admiten el tipo `T` no necesitan reemplazar este método. Para obtener un ejemplo de un convertidor que necesita reemplazar este método, consulte la sección sobre la [deserialización polimórfica](#support-polymorphic-deserialization), más adelante en este artículo.

Puede hacer referencia al [código fuente de convertidores integrados](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) como implementaciones de referencia para escribir convertidores personalizados.

## <a name="steps-to-follow-the-factory-pattern"></a>Pasos para seguir el patrón de fábrica

En los pasos siguientes se explica cómo crear un convertidor siguiendo el patrón de fábrica:

* Cree una clase que derive de <xref:System.Text.Json.Serialization.JsonConverterFactory>.
* Reemplace el método `CanConvert` para devolver "true" cuando el tipo que se va a convertir sea uno que el convertidor puede controlar. Por ejemplo, si el convertidor es para `List<T>`, solo puede controlar `List<int>`, `List<string>` y `List<DateTime>`.
* Invalide el método `CreateConverter` para devolver una instancia de una clase de convertidor que controlará el tipo de conversión que se proporciona en tiempo de ejecución.
* Cree la clase de convertidor de la que el método `CreateConverter` crea instancias.

El patrón de fábrica es necesario para los genéricos abiertos porque el código para convertir un objeto en una cadena (y también para realizar una conversión a partir de esta) no es el mismo para todos los tipos. Un convertidor para un tipo genérico abierto (`List<T>`, por ejemplo) tiene que crear un convertidor para un tipo genérico cerrado (`List<DateTime>`, por ejemplo) en segundo plano. Es necesario escribir código para controlar cada tipo genérico cerrado que el convertidor puede controlar.

El tipo `Enum` es similar a un tipo genérico abierto: un convertidor para `Enum` tiene que crear un convertidor para un elemento `Enum` específico (`WeekdaysEnum`, por ejemplo) en segundo plano.

## <a name="error-handling"></a>Control de errores

Si necesita producir una excepción en el código de control de errores, considere la posibilidad de iniciar una excepción <xref:System.Text.Json.JsonException> sin un mensaje. Este tipo de excepción crea automáticamente un mensaje que incluye la ruta de acceso a la parte del JSON que causó el error. Por ejemplo, la instrucción `throw new JsonException();` genera un mensaje de error como el ejemplo siguiente:

```output
Unhandled exception. System.Text.Json.JsonException:
The JSON value could not be converted to System.Object.
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

Si proporciona un mensaje (por ejemplo, `throw new JsonException("Error occurred")`), la excepción sigue proporcionando la ruta de acceso en la propiedad <xref:System.Text.Json.JsonException.Path>.

## <a name="register-a-custom-converter"></a>Registro de un convertidor personalizado

*Registre* un convertidor personalizado para que los métodos `Serialize` y `Deserialize` lo utilicen. Elija uno de los enfoques siguientes:

* Agregue una instancia de la clase de convertidor a la colección <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType>.
* Aplique el atributo [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) a las propiedades que requieren el convertidor personalizado.
* Aplique el atributo [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) a una clase o una estructura que represente un tipo de valor personalizado.

## <a name="registration-sample---converters-collection"></a>Ejemplo de registro: colección de convertidores

Este es un ejemplo que hace que <xref:System.ComponentModel.DateTimeOffsetConverter> sea el valor predeterminado para propiedades de tipo <xref:System.DateTimeOffset>:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

Suponga que serializa una instancia del tipo siguiente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

Este es un ejemplo de salida JSON que muestra que se ha usado el convertidor personalizado:

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

En el código siguiente se usa el mismo enfoque para realizar una deserialización mediante el convertidor `DateTimeOffset` personalizado:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a>Ejemplo de registro: [JsonConverter] en una propiedad

El código siguiente selecciona un convertidor personalizado para la propiedad `Date`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

El código para serializar `WeatherForecastWithConverterAttribute` no requiere el uso de `JsonSerializeOptions.Converters`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

El código que se va a deserializar tampoco requiere el uso de `Converters`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a>Ejemplo de registro: [JsonConverter] en un tipo

Este es el código que crea una estructura y le aplica el atributo `[JsonConverter]`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/Temperature.cs)]

Este es el convertidor personalizado para la estructura anterior:

[!code-csharp[](snippets/system-text-json-how-to/csharp/TemperatureConverter.cs)]

El atributo `[JsonConvert]` de la estructura registra el convertidor personalizado como valor predeterminado para las propiedades de tipo `Temperature`. El convertidor se usa automáticamente en la propiedad `TemperatureCelsius` del tipo siguiente al serializarla o deserializarla:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a>Prioridad de registro del convertidor

Durante la serialización o la deserialización, se elige un convertidor para cada elemento JSON en el orden siguiente, que se muestra de la prioridad más alta a la más baja:

* Elemento `[JsonConverter]` aplicado a una propiedad.
* Convertidor agregado a la colección `Converters`.
* Elemento `[JsonConverter]` aplicado a un tipo de valor personalizado o POCO.

Si se registran varios convertidores personalizados para un tipo en la colección `Converters`, se usa el primer convertidor que devuelve "true" para `CanConvert`.

Solo se elige un convertidor integrado si no se registra ningún convertidor personalizado aplicable.

## <a name="converter-samples-for-common-scenarios"></a>Ejemplos de convertidor para escenarios comunes

En las secciones siguientes se proporcionan ejemplos de convertidor que abordan algunos escenarios comunes que la funcionalidad integrada no controla.

::: zone pivot="dotnet-5-0"

* [Deserialización de tipos inferidos en las propiedades de objeto](#deserialize-inferred-types-to-object-properties).
* [Compatibilidad con la deserialización polimórfica](#support-polymorphic-deserialization).
* [Compatibilidad con el recorrido de ida y vuelta para Stack\<T>](#support-round-trip-for-stackt).
::: zone-end

::: zone pivot="dotnet-core-3-1"

* [Deserialización de tipos inferidos en las propiedades de objeto](#deserialize-inferred-types-to-object-properties).
* [Compatibilidad para diccionarios con una clave que no sea de cadena](#support-dictionary-with-non-string-key).
* [Compatibilidad con la deserialización polimórfica](#support-polymorphic-deserialization).
* [Compatibilidad con el recorrido de ida y vuelta para Stack\<T>](#support-round-trip-for-stackt).
::: zone-end

### <a name="deserialize-inferred-types-to-object-properties"></a>Deserialización de los tipos inferidos en propiedades de objeto

Al realizar una deserialización en una propiedad de tipo `object`, se crea un objeto `JsonElement`. La razón es que el deserializador no sabe qué tipo de CLR debe crear, y tampoco intenta averiguarlo. Por ejemplo, si una propiedad JSON tiene "true", el deserializador no infiere que el valor es de tipo `Boolean`, y si un elemento tiene "01/01/2019", el deserializador no infiere que es de tipo `DateTime`.

La inferencia de tipos puede ser incorrecta. Si el deserializador analiza un número JSON que no tiene un separador decimal como `long`, pueden producirse problemas de salida del intervalo si el valor se serializó originalmente como `ulong` o `BigInteger`. El análisis de un número que tiene un separador decimal como `double` puede perder precisión si el número se ha serializado originalmente como `decimal`.

En escenarios que requieren inferencia de tipos, el código siguiente muestra un convertidor personalizado para las propiedades `object`. El código convierte:

* `true` y `false`, en `Boolean`
* Números sin decimales, en `long`
* Números con un decimal, en `double`
* Fechas, en `DateTime`
* Cadenas, en `string`
* Todo lo demás, en `JsonElement`

[!code-csharp[](snippets/system-text-json-how-to/csharp/ObjectToInferredTypesConverter.cs)]

El código siguiente registra el convertidor:

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeInferredTypesToObject.cs?name=SnippetRegister)]

Este es un ejemplo de tipo con propiedades `object`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

El siguiente ejemplo de JSON para deserializar contiene valores que se deserializarán como `DateTime`, `long` y `string`:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

Sin el convertidor personalizado, la deserialización coloca un elemento `JsonElement` en cada propiedad.

La [carpeta de pruebas unitarias](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) en el espacio de nombres `System.Text.Json.Serialization` tiene más ejemplos de convertidores personalizados que controlan la deserialización en propiedades `object`.

::: zone pivot="dotnet-core-3-1"

### <a name="support-dictionary-with-non-string-key"></a>Compatibilidad para diccionarios con una clave que no sea de cadena

La compatibilidad integrada con colecciones de diccionarios es para `Dictionary<string, TValue>`. Por lo tanto, la clave debe ser una cadena. Para admitir un diccionario con un entero o algún otro tipo como clave, se requiere un convertidor personalizado.

En el código siguiente se muestra un convertidor personalizado que funciona con `Dictionary<Enum,TValue>`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/DictionaryTKeyEnumTValueConverter.cs)]

El código siguiente registra el convertidor:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

El convertidor puede serializar y deserializar la propiedad `TemperatureRanges` de la siguiente clase que usa el elemento `Enum` siguiente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

La salida JSON de la serialización es similar al ejemplo siguiente:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "Cold": 20,
    "Hot": 40
  }
}
```

La [carpeta de pruebas unitarias](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) en el espacio de nombres `System.Text.Json.Serialization` tiene más ejemplos de convertidores personalizados que controlan los diccionarios con una clave que no sea de cadena.
::: zone-end

### <a name="support-polymorphic-deserialization"></a>Compatibilidad con la deserialización polimórfica

Las características integradas proporcionan una gama limitada de [serialización polimórfica](system-text-json-how-to.md#serialize-properties-of-derived-classes), pero no admiten ningún tipo de deserialización. La deserialización requiere un convertidor personalizado.

Suponga, por ejemplo, que tiene una clase base abstracta `Person`, con clases derivadas `Employee` y `Customer`. La deserialización polimórfica significa que puede especificar `Person` como destino de la deserialización en tiempo de diseño, y los objetos `Customer` y `Employee` en el JSON se deserializan correctamente en tiempo de ejecución. Durante la deserialización, debe buscar pistas que identifiquen el tipo requerido en JSON. Los tipos de pistas disponibles varían según cada escenario. Por ejemplo, una propiedad de discriminador puede estar disponible o puede tener que confiar en la presencia o ausencia de una propiedad determinada. La versión actual de `System.Text.Json` no proporciona atributos para especificar cómo controlar los escenarios de deserialización polimórficos, por lo que se requieren convertidores personalizados.

En el código siguiente se muestra una clase base, dos clases derivadas y un convertidor personalizado para ellas. El convertidor usa una propiedad de discriminador para realizar la deserialización polimórfica. El discriminador de tipo no se encuentra en las definiciones de clase, pero se crea durante la serialización y se lee durante la deserialización.

[!code-csharp[](snippets/system-text-json-how-to/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/PersonConverterWithTypeDiscriminator.cs)]

El código siguiente registra el convertidor:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPolymorphic.cs?name=SnippetRegister)]

El convertidor puede deserializar el JSON que se creó con el mismo convertidor para serializar, por ejemplo:

```json
[
  {
    "TypeDiscriminator": 1,
    "CreditLimit": 10000,
    "Name": "John"
  },
  {
    "TypeDiscriminator": 2,
    "OfficeNumber": "555-1234",
    "Name": "Nancy"
  }
]
```

El código del convertidor en el ejemplo anterior lee y escribe cada propiedad manualmente. Una alternativa es llamar a `Deserialize` o `Serialize` para realizar parte del trabajo. Para obtener un ejemplo, vea [esta publicación de StackOverflow](https://stackoverflow.com/a/59744873/12509023).

### <a name="support-round-trip-for-stackt"></a>Compatibilidad con el recorrido de ida y vuelta para Stack\<T>

Si deserializa una cadena JSON en un objeto <xref:System.Collections.Generic.Stack%601> y después serializa ese objeto, el contenido de la pila está en orden inverso. Este comportamiento se aplica a los siguientes tipos e interfaz, así como a los tipos definidos por el usuario que derivan de ellos:

* <xref:System.Collections.Stack>
* <xref:System.Collections.Generic.Stack%601>
* <xref:System.Collections.Concurrent.ConcurrentStack%601>
* <xref:System.Collections.Immutable.ImmutableStack%601>
* <xref:System.Collections.Immutable.IImmutableStack%601>

Para admitir la serialización y deserialización que conserva el orden original en la pila, se requiere un convertidor personalizado.

En el código siguiente se muestra un convertidor personalizado que permite el recorrido de ida y vuelta hacia y desde objetos `Stack<T>`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonConverterFactoryForStackOfT.cs)]

El código siguiente registra el convertidor:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripStackOfT.cs?name=SnippetRegister)]

## <a name="handle-null-values"></a>Control de valores NULL

De forma predeterminada, el serializador controla los valores NULL de la siguiente manera:

* Para tipos de referencia y tipos de `Nullable<T>`:

  * No pasa `null` a los convertidores personalizados en la serialización.
  * No pasa `JsonTokenType.Null` a los convertidores personalizados en la deserialización.
  * Devuelve una instancia de `null` en la deserialización.
  * Escribe `null` directamente con el escritor en la serialización.

* Para los tipos de valor distintos a NULL:

  * Pasa `JsonTokenType.Null` a los convertidores personalizados en la deserialización. (Si no hay ningún convertidor personalizado disponible, el convertidor interno produce una excepción `JsonException` para el tipo).

Este comportamiento de administración de valores NULL sirve principalmente para optimizar el rendimiento omitiendo una llamada adicional al convertidor. Además, evita la aplicación de convertidores para tipos que aceptan valores NULL que comprobar para `null` al principio de cada invalidación de método `Read` y `Write`.

::: zone pivot="dotnet-5-0"
Para permitir que un convertidor personalizado administre `null` para un tipo de valor o referencia, invalide <xref:System.Text.Json.Serialization.JsonConverter%601.HandleNull%2A?displayProperty=nameWithType> para devolver `true`, como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CustomConverterHandleNull.cs" highlight="19":::
::: zone-end

## <a name="other-custom-converter-samples"></a>Otros ejemplos de convertidor personalizado

El artículo [Migración de Newtonsoft.Json a System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) contiene ejemplos adicionales de convertidores personalizados.

La [carpeta de pruebas unitarias](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) en el código fuente de `System.Text.Json.Serialization` incluye otros ejemplos de convertidor personalizado, como:

* [Convertidor Int32 que convierte valores nulos en 0 al realizar la deserialización](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)
* [Convertidor Int32 que permite valores de cadena y número al realizar la deserialización](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)
* [Convertidor Enum](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)
* [Convertidor List\<T> que acepta datos externos](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)
* [Convertidor Long[] que funciona con una lista de números delimitados por comas](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)

Si necesita crear un convertidor que modifique el comportamiento de un convertidor integrado existente, puede obtener el [código fuente del convertidor existente](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) para que sirva como punto de partida para la personalización.

## <a name="additional-resources"></a>Recursos adicionales

* [Código fuente para convertidores integrados](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)
* [Compatibilidad con DateTime y DateTimeOffset en System.Text.Json](../datetime/system-text-json-support.md)
* [Información general sobre System.Text.Json](system-text-json-overview.md)
* [Procedimiento para usar System.Text.Json](system-text-json-how-to.md)
* [Procedimiento para migrar de Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Referencia de API de System.Text.Json](xref:System.Text.Json)
* [Referencia de API de System.Text.Json.Serialization](xref:System.Text.Json.Serialization)
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
