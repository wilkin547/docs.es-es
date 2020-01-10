---
title: 'Cómo escribir convertidores personalizados para la serialización de JSON: .NET'
ms.date: 10/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: efbaf852f07b2b59111f0e330cf52470e3eca4c3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705813"
---
# <a name="how-to-write-custom-converters-for-json-serialization-in-net"></a>Cómo escribir convertidores personalizados para la serialización de JSON en .NET

En este artículo se muestra cómo crear convertidores personalizados para las clases de serialización de JSON que se proporcionan en el espacio de nombres <xref:System.Text.Json>. Para obtener una introducción a `System.Text.Json`, vea [Cómo serializar y deserializar JSON en .net](system-text-json-how-to.md).

Un *convertidor* es una clase que convierte un objeto o un valor a y desde JSON. El espacio de nombres `System.Text.Json` tiene convertidores integrados para la mayoría de los tipos primitivos que se asignan a primitivos de JavaScript. Puede escribir convertidores personalizados:

* Para reemplazar el comportamiento predeterminado de un convertidor integrado. Por ejemplo, puede que desee que los valores de `DateTime` se representen con el formato mm/dd/aaaa en lugar del formato ISO 8601-1:2019 predeterminado.
* Para admitir un tipo de valor personalizado. Por ejemplo, un struct de `PhoneNumber`.

También puede escribir convertidores personalizados para extender `System.Text.Json` con funcionalidad no incluida en la versión actual. Los siguientes escenarios se describen más adelante en este artículo:

* [Deserializar los tipos deducidos en las propiedades de objeto](#deserialize-inferred-types-to-object-properties).
* [Diccionario de soporte con clave que no es de cadena](#support-dictionary-with-non-string-key).
* [Admitir la deserialización polimórfica](#support-polymorphic-deserialization).

## <a name="custom-converter-patterns"></a>Patrones de convertidor personalizados

Hay dos patrones para crear un convertidor personalizado: el patrón básico y el patrón de fábrica. El patrón de generador es para los convertidores que controlan el tipo `Enum` o genéricos abiertos. El patrón básico es para los tipos genéricos no genéricos y cerrados.  Por ejemplo, los convertidores de los siguientes tipos requieren el patrón de fábrica:

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

Entre los ejemplos de tipos que puede controlar el patrón básico se incluyen los siguientes:

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

El patrón básico crea una clase que puede controlar un tipo. El modelo de generador crea una clase que determina en tiempo de ejecución qué tipo específico es necesario y crea dinámicamente el convertidor adecuado.

## <a name="sample-basic-converter"></a>Convertidor básico de ejemplo

El ejemplo siguiente es un convertidor que reemplaza la serialización predeterminada para un tipo de datos existente. El convertidor usa el formato mm/dd/aaaa para `DateTimeOffset` propiedades.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a>Convertidor de patrón de fábrica de ejemplo

En el código siguiente se muestra un convertidor personalizado que funciona con `Dictionary<Enum,TValue>`. El código sigue el patrón de generador porque el primer parámetro de tipo genérico es `Enum` y el segundo es abierto. El método `CanConvert` devuelve `true` solo para un `Dictionary` con dos parámetros genéricos, el primero de los cuales es un tipo de `Enum`. El convertidor interno obtiene un convertidor existente para controlar el tipo que se proporciona en tiempo de ejecución para `TValue`. 

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

El código anterior es el mismo que el que se muestra en el [Diccionario de soporte con clave que no es de cadena](#support-dictionary-with-non-string-key) , más adelante en este artículo.

## <a name="steps-to-follow-the-basic-pattern"></a>Pasos para seguir el patrón básico

En los pasos siguientes se explica cómo crear un convertidor siguiendo el patrón básico:

* Cree una clase que derive de <xref:System.Text.Json.Serialization.JsonConverter%601> donde `T` es el tipo que se va a serializar y deserializar.
* Invalide el método `Read` para deserializar el JSON de entrada y convertirlo al tipo `T`. Use el <xref:System.Text.Json.Utf8JsonReader> que se pasa al método para leer el JSON.
* Invalide el método `Write` para serializar el objeto de entrada de tipo `T`. Use el <xref:System.Text.Json.Utf8JsonWriter> que se pasa al método para escribir el JSON.
* Invalide el método `CanConvert` solo si es necesario. La implementación predeterminada devuelve `true` cuando el tipo que se va a convertir es `T`de tipo. Por lo tanto, los convertidores que solo admiten el tipo `T` no necesitan invalidar este método. Para obtener un ejemplo de un convertidor que necesita invalidar este método, consulte la sección [deserialización polimórfica](#support-polymorphic-deserialization) más adelante en este artículo.

Puede hacer referencia al [código fuente de los convertidores integrados](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/) como implementaciones de referencia para escribir convertidores personalizados.

## <a name="steps-to-follow-the-factory-pattern"></a>Pasos para seguir el patrón de fábrica

En los pasos siguientes se explica cómo crear un convertidor siguiendo el patrón de fábrica:

* Cree una clase que provenga de <xref:System.Text.Json.Serialization.JsonConverterFactory>.
* Invalide el método `CanConvert` para devolver true cuando el tipo que se va a convertir es uno que el convertidor puede controlar. Por ejemplo, si el convertidor es para `List<T>` solo puede controlar `List<int>`, `List<string>`y `List<DateTime>`. 
* Invalide el método `CreateConverter` para devolver una instancia de una clase de convertidor que controlará el tipo de conversión que se proporciona en tiempo de ejecución.
* Cree la clase de convertidor en la que crea instancias el método `CreateConverter`. 

El patrón de generador es necesario para los genéricos abiertos porque el código para convertir un objeto en una cadena y desde una cadena no es el mismo para todos los tipos. Un convertidor para un tipo genérico abierto (`List<T>`, por ejemplo) tiene que crear un convertidor para un tipo genérico cerrado (por ejemplo,`List<DateTime>`) en segundo plano. Debe escribirse código para controlar cada tipo genérico cerrado que el convertidor puede controlar.

El tipo de `Enum` es similar a un tipo genérico abierto: un convertidor para `Enum` tiene que crear un convertidor para un `Enum` específico (`WeekdaysEnum`, por ejemplo) en segundo plano. 

## <a name="error-handling"></a>Control de errores

Si necesita producir una excepción en el código de control de errores, considere la posibilidad de iniciar una <xref:System.Text.Json.JsonException> sin un mensaje. Este tipo de excepción crea automáticamente un mensaje que incluye la ruta de acceso a la parte del JSON que causó el error. Por ejemplo, la instrucción `throw new JsonException();` genera un mensaje de error como el ejemplo siguiente:

```
Unhandled exception. System.Text.Json.JsonException: 
The JSON value could not be converted to System.Object. 
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

Si proporciona un mensaje (por ejemplo, `throw new JsonException("Error occurred")`, la excepción sigue proporcionando la ruta de acceso en la propiedad <xref:System.Text.Json.JsonException.Path>.

## <a name="register-a-custom-converter"></a>Registrar un convertidor personalizado

*Registre* un convertidor personalizado para que los métodos `Serialize` y `Deserialize` lo utilicen. Elija uno de los métodos siguientes:

* Agregue una instancia de la clase de convertidor a la colección de <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType>.
* Aplique el atributo [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) a las propiedades que requieren el convertidor personalizado.
* Aplique el atributo [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) a una clase o un struct que represente un tipo de valor personalizado.

## <a name="registration-sample---converters-collection"></a>Ejemplo de registro: colección de convertidores 

Este es un ejemplo que hace que la <xref:System.ComponentModel.DateTimeOffsetConverter> predeterminada para las propiedades de tipo <xref:System.DateTimeOffset>:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

Suponga que serializa una instancia del tipo siguiente:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

Este es un ejemplo de salida JSON que muestra que se ha usado el convertidor personalizado:

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

En el código siguiente se usa el mismo enfoque para deserializar utilizando el convertidor de `DateTimeOffset` personalizado:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a>Ejemplo de registro-[JsonConverter] en una propiedad

El código siguiente selecciona un convertidor personalizado para la propiedad `Date`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

El código para serializar `WeatherForecastWithConverterAttribute` no requiere el uso de `JsonSerializeOptions.Converters`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

El código que se va a deserializar tampoco requiere el uso de `Converters`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a>Ejemplo de registro-[JsonConverter] en un tipo

Este es el código que crea un struct y le aplica el `[JsonConverter]` atributo:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Temperature.cs)]

Este es el convertidor personalizado para el struct anterior:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/TemperatureConverter.cs)]

El atributo `[JsonConvert]` del struct registra el convertidor personalizado como valor predeterminado para las propiedades de tipo `Temperature`. El convertidor se utiliza automáticamente en la propiedad `TemperatureCelsius` del tipo siguiente al serializar o deserializar:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a>Prioridad de registro del convertidor

Durante la serialización o la deserialización, se elige un convertidor para cada elemento JSON en el orden siguiente, que se muestra de la prioridad más alta a la más baja:

* `[JsonConverter]` aplicado a una propiedad.
* Convertidor agregado a la colección de `Converters`.
* `[JsonConverter]` aplica a un tipo de valor personalizado o POCO.

Si se registran varios convertidores personalizados para un tipo en la colección `Converters`, se usa el primer convertidor que devuelve true para `CanConvert`.

Solo se elige un convertidor integrado si no se registra ningún convertidor personalizado aplicable.

## <a name="converter-samples-for-common-scenarios"></a>Ejemplos de convertidor para escenarios comunes

En las secciones siguientes se proporcionan ejemplos de convertidor que abordan algunos escenarios comunes que la funcionalidad integrada no controla.

* [Deserializar los tipos deducidos en propiedades de objeto](#deserialize-inferred-types-to-object-properties)
* [Diccionario de soporte con clave que no es de cadena](#support-dictionary-with-non-string-key)
* [Compatibilidad con la deserialización polimórfica](#support-polymorphic-deserialization)

### <a name="deserialize-inferred-types-to-object-properties"></a>Deserializar los tipos deducidos en propiedades de objeto

Al deserializar a una propiedad de tipo `Object`, se crea un objeto `JsonElement`. La razón es que el deserializador no sabe qué tipo de CLR crear y no intenta adivinar. Por ejemplo, si una propiedad JSON tiene "true", el deserializador no infiere que el valor es un `Boolean`y, si un elemento tiene "01/01/2019", el deserializador no deduce que es un `DateTime`.

La inferencia de tipos puede ser incorrecta. Si el deserializador analiza un número JSON que no tiene un separador decimal como `long`, esto podría producir problemas fuera del intervalo si el valor se serializó originalmente como `ulong` o `BigInteger`. El análisis de un número que tiene un separador decimal como `double` podría perder precisión si el número se serializó originalmente como `decimal`.

En escenarios que requieren inferencia de tipos, el código siguiente muestra un convertidor personalizado para `Object` propiedades. El código convierte:

* `true` y `false` a `Boolean`
* Números que se van a `long` o `double`
* Fechas para `DateTime`
* Cadenas que se van a `string`
* Todo lo demás que se va a `JsonElement`

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ObjectToInferredTypesConverter.cs)]

El código siguiente registra el convertidor:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertInferredTypesToObject.cs?name=SnippetRegister)]

Este es un ejemplo de tipo con propiedades de `Object`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

El siguiente ejemplo de JSON para deserializar contiene valores que se deserializarán como `DateTime`, `long`y `string`:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

Sin el convertidor personalizado, la deserialización coloca un `JsonElement` en cada propiedad.

La [carpeta pruebas unitarias](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) del espacio de nombres `System.Text.Json.Serialization` tiene más ejemplos de convertidores personalizados que controlan la deserialización de las propiedades de objeto.

### <a name="support-dictionary-with-non-string-key"></a>Diccionario de soporte con clave que no es de cadena

La compatibilidad integrada con colecciones de diccionario es para `Dictionary<string, TValue>`. Es decir, la clave debe ser una cadena. Para admitir un diccionario con un entero o algún otro tipo como clave, se requiere un convertidor personalizado.

En el código siguiente se muestra un convertidor personalizado que funciona con `Dictionary<Enum,TValue>`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

El código siguiente registra el convertidor:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

El convertidor puede serializar y deserializar la propiedad `TemperatureRanges` de la siguiente clase que usa el `Enum`siguiente:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

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

La [carpeta pruebas unitarias](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) del espacio de nombres `System.Text.Json.Serialization` tiene más ejemplos de convertidores personalizados que controlan diccionarios que no son de clave de cadena.

### <a name="support-polymorphic-deserialization"></a>Compatibilidad con la deserialización polimórfica

La [serialización polimórfica](system-text-json-how-to.md#serialize-properties-of-derived-classes) no requiere un convertidor personalizado, pero la deserialización requiere un convertidor personalizado.

Suponga, por ejemplo, que tiene una `Person` clase base abstracta, con `Employee` y `Customer` clases derivadas. La deserialización polimórfica significa que, en tiempo de diseño, puede especificar `Person` como destino de la deserialización y `Customer` y `Employee` objetos en el JSON se deserializan correctamente en tiempo de ejecución. Durante la deserialización, debe buscar pistas que identifiquen el tipo requerido en JSON. Los tipos de pistas disponibles varían con cada escenario. Por ejemplo, una propiedad de discriminador podría estar disponible o podría tener que confiar en la presencia o ausencia de una propiedad determinada. La versión actual de `System.Text.Json` no proporciona atributos para especificar cómo administrar escenarios de deserialización polimórficos, por lo que se requieren convertidores personalizados.

En el código siguiente se muestra una clase base, dos clases derivadas y un convertidor personalizado para ellas. El convertidor usa una propiedad de discriminador para realizar la deserialización polimórfica. El discriminador de tipo no se encuentra en las definiciones de clase, pero se crea durante la serialización y se lee durante la deserialización.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/PersonConverterWithTypeDiscriminator.cs)]

El código siguiente registra el convertidor:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ConvertPolymorphic.cs?name=SnippetRegister)]

El convertidor puede deserializar JSON que se creó con el mismo convertidor para serializar, por ejemplo:

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

## <a name="other-custom-converter-samples"></a>Otros ejemplos de convertidor personalizado

La [carpeta pruebas unitarias](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) del código fuente de `System.Text.Json.Serialization` incluye otros ejemplos de convertidor personalizados, como:

* `Int32` convertidor que convierte null en 0 en la deserialización
* `Int32` convertidor que permite valores numéricos y de cadena en la deserialización
* convertidor de `Enum`
* `List<T>` convertidor que acepta datos externos
* `Long[]` convertidor que funciona con una lista delimitada por comas de números 

## <a name="additional-resources"></a>Recursos adicionales

* [Información general de System. Text. JSON](system-text-json-overview.md)
* [Referencia de la API System. Text. JSON](xref:System.Text.Json)
* [Cómo usar System. Text. JSON](system-text-json-how-to.md)
* [Código fuente para convertidores integrados](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/)
* Problemas de GitHub relacionados con los convertidores personalizados para `System.Text.Json`
  * [36639 Introducción a convertidores personalizados](https://github.com/dotnet/corefx/issues/36639)
  * [38713 acerca de la deserialización del objeto](https://github.com/dotnet/corefx/issues/38713)
  * [40120 acerca de los diccionarios que no son de clave de cadena](https://github.com/dotnet/corefx/issues/40120)
  * [37787 acerca de la deserialización polimórfica](https://github.com/dotnet/corefx/issues/37787)
