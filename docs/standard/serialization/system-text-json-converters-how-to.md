---
title: 'Cómo escribir convertidores personalizados para la serialización de JSON: .NET'
author: tdykstra
ms.author: tdykstra
ms.date: 10/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: 361818a0bda8863f8878b86e5fb377dc0faf5246
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73741907"
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

```csharp
private class ExampleDateTimeOffsetConverter : JsonConverter<DateTimeOffset>
{
    public override DateTimeOffset Read(
        ref Utf8JsonReader reader, 
        Type typeToConvert, 
        JsonSerializerOptions options)
    {
        return DateTimeOffset.ParseExact(reader.GetString(), 
            "MM/dd/yyyy", CultureInfo.InvariantCulture);
    }

    public override void Write(
        Utf8JsonWriter writer, 
        DateTimeOffset value, 
        JsonSerializerOptions options)
    {
        writer.WriteStringValue(value.ToString(
            "MM/dd/yyyy", CultureInfo.InvariantCulture));
    }
}
```

## <a name="sample-factory-pattern-converter"></a>Convertidor de patrón de fábrica de ejemplo

En el código siguiente se muestra un convertidor personalizado que funciona con `Dictionary<Enum,TValue>`. El código sigue el patrón de generador porque el primer parámetro de tipo genérico es `Enum` y el segundo es abierto. El método `CanConvert` devuelve `true` solo para un `Dictionary` con dos parámetros genéricos, el primero de los cuales es un tipo de `Enum`. El convertidor interno obtiene un convertidor existente para controlar el tipo que se proporciona en tiempo de ejecución para `TValue`. 

```csharp
using System;
using System.Collections.Generic;
using System.Reflection;
using System.Text.Json;
using System.Text.Json.Serialization;

namespace SystemTextJsonSamples
{
    public class ConverterDictionaryTKeyEnumTValue : JsonConverterFactory
    {
        public override bool CanConvert(Type typeToConvert)
        {
            if (!typeToConvert.IsGenericType)
            {
                return false;
            }

            if (typeToConvert.GetGenericTypeDefinition() != typeof(Dictionary<,>))
            {
                return false;
            }

            return typeToConvert.GetGenericArguments()[0].IsEnum;
        }

        public override JsonConverter CreateConverter(
            Type type, 
            JsonSerializerOptions options)
        {
            Type keyType = type.GetGenericArguments()[0];
            Type valueType = type.GetGenericArguments()[1];

            JsonConverter converter = (JsonConverter)Activator.CreateInstance(
                typeof(DictionaryEnumConverterInner<,>).MakeGenericType(
                    new Type[] { keyType, valueType }),
                BindingFlags.Instance | BindingFlags.Public,
                binder: null,
                args: new object[] { options },
                culture: null);

            return converter;
        }

        private class DictionaryEnumConverterInner<TKey, TValue> : 
            JsonConverter<Dictionary<TKey, TValue>> where TKey : struct, Enum
        {
            private readonly JsonConverter<TValue> _valueConverter;
            private Type _keyType;
            private Type _valueType;

            public DictionaryEnumConverterInner(JsonSerializerOptions options)
            {
                // For performance, use the existing converter if available.
                _valueConverter = (JsonConverter<TValue>)options
                    .GetConverter(typeof(TValue));

                // Cache the key and value types.
                _keyType = typeof(TKey);
                _valueType = typeof(TValue);
            }

            public override Dictionary<TKey, TValue> Read(
                ref Utf8JsonReader reader, 
                Type typeToConvert, 
                JsonSerializerOptions options)
            {
                if (reader.TokenType != JsonTokenType.StartObject)
                {
                    throw new JsonException();
                }

                Dictionary<TKey, TValue> value = new Dictionary<TKey, TValue>();

                while (reader.Read())
                {
                    if (reader.TokenType == JsonTokenType.EndObject)
                    {
                        return value;
                    }

                    // Get the key.
                    if (reader.TokenType != JsonTokenType.PropertyName)
                    {
                        throw new JsonException();
                    }

                    string propertyName = reader.GetString();

                    // For performance, parse with ignoreCase:false first.
                    if (!Enum.TryParse(propertyName, ignoreCase: false, out TKey key) &&
                        !Enum.TryParse(propertyName, ignoreCase: true, out key))
                    {
                        throw new JsonException(
                            $"Unable to convert \"{propertyName}\" to Enum \"{_keyType}\".");
                    }

                    // Get the value.
                    TValue v;
                    if (_valueConverter != null)
                    {
                        reader.Read();
                        v = _valueConverter.Read(ref reader, _valueType, options);
                    }
                    else
                    {
                        v = JsonSerializer.Deserialize<TValue>(ref reader, options);
                    }

                    // Add to dictionary.
                    value.Add(key, v);
                }

                throw new JsonException();
            }

            public override void Write(
                Utf8JsonWriter writer, 
                Dictionary<TKey, TValue> value, 
                JsonSerializerOptions options)
            {
                writer.WriteStartObject();

                foreach (KeyValuePair<TKey, TValue> kvp in value)
                {
                    writer.WritePropertyName(kvp.Key.ToString());

                    if (_valueConverter != null)
                    {
                        _valueConverter.Write(writer, kvp.Value, options);
                    }
                    else
                    {
                        JsonSerializer.Serialize(writer, kvp.Value, options);
                    }
                }

                writer.WriteEndObject();
            }
        }
    }
}
```

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

* Cree una clase que derive de <xref:System.Text.Json.Serialization.JsonConverterFactory>.
* Invalide el método `CanConvert` para devolver true cuando el tipo que se va a convertir es uno que el convertidor puede controlar. Por ejemplo, si el convertidor es para `List<T>` solo puede controlar `List<int>`, `List<string>`y `List<DateTime>`. 
* Invalide el método `CreateConverter` para devolver una instancia de una clase de convertidor que controlará el tipo de conversión que se proporciona en tiempo de ejecución.
* Cree la clase de convertidor en la que crea instancias el método `CreateConverter`. 

El patrón de generador es necesario para los genéricos abiertos porque el código para convertir un objeto en una cadena y desde una cadena no es el mismo para todos los tipos. Un convertidor para un tipo genérico abierto (`List<T>`, por ejemplo) tiene que crear un convertidor para un tipo genérico cerrado (por ejemplo,`List<DateTime>`) en segundo plano. Debe escribirse código para controlar cada tipo genérico cerrado que el convertidor puede controlar.

El tipo de `Enum` es similar a un tipo genérico abierto: un convertidor para `Enum` tiene que crear un convertidor para un `Enum` específico (`WeekdaysEnum`, por ejemplo) en segundo plano. 

## <a name="error-handling"></a>Control de errores

Si necesita producir una excepción en el código de control de errores, considere la posibilidad de iniciar una <xref:System.Text.Json.JsonException> sin un mensaje. Este tipo de excepción crea automáticamente un mensaje que incluye la ruta de acceso a la parte del JSON que causó el error. Por ejemplo, la instrucción `throw new JsonException();` genera un mensaje de error como el ejemplo siguiente:

```text
Unhandled exception. System.Text.Json.JsonException: 
The JSON value could not be converted to System.Object. 
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

Si proporciona un mensaje (por ejemplo, `throw new JsonException("Error occurred)`, la excepción sigue proporcionando la ruta de acceso en la propiedad <xref:System.Text.Json.JsonException.Path>.

## <a name="register-a-custom-converter"></a>Registrar un convertidor personalizado

*Registre* un convertidor personalizado para que los métodos `Serialize` y `Deserialize` lo utilicen. Elija uno de los métodos siguientes:

* Agregue una instancia de la clase de convertidor a la colección de <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType>.
* Aplique el atributo [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) a las propiedades que requieren el convertidor personalizado.
* Aplique el atributo [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) a una clase o un struct que represente un tipo de valor personalizado.

## <a name="registration-sample---converters-collection"></a>Ejemplo de registro: colección de convertidores 

Este es un ejemplo que hace que la `ExampleDateTimeOffsetConverter` predeterminada para las propiedades de tipo `DateTimeOffset`:

```csharp
//...
JsonSerializerOptions options = new JsonSerializerOptions();
options.Converters.Add(new ExampleDateTimeOffsetConverter());
string json = JsonSerializer.Serialize(weatherForecast, options);
```

Suponga que serializa el tipo siguiente:

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

Este es un ejemplo de salida JSON que muestra que se ha usado el convertidor personalizado:

```json
{
  "Date": "08/01/2019",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

En el código siguiente se usa el mismo enfoque para deserializar utilizando el convertidor de `DateTimeOffset` personalizado:

```csharp
//...
JsonSerializerOptions options = new JsonSerializerOptions();
options.Converters.Add(new ExampleDateTimeOffsetConverter());
weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json, options);
```

## <a name="registration-sample---jsonconverter-on-a-property"></a>Ejemplo de registro-[JsonConverter] en una propiedad

El código siguiente selecciona un convertidor personalizado para la propiedad `Date`:

```csharp
class WeatherForecastWithConverter
{
    [JsonConverter(typeof(ExampleDateTimeOffsetConverter))]
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

El código para serializar y deserializar `WeatherForecastWithConverter` no requiere el uso de `JsonSerializeOptions.Converters`:

```csharp
string json = JsonSerializer.Serialize(weatherForecastWithConverter);
```

```csharp
weatherForecast = JsonSerializer.Deserialize<WeatherForecastWithConverter>(json);
```

## <a name="registration-sample---jsonconverter-on-a-type"></a>Ejemplo de registro-[JsonConverter] en un tipo

Este es el código que crea un struct y le aplica el `[JsonConverter]` atributo:

```csharp
[JsonConverter(typeof(TemperatureConverter))]
public struct Temperature
{
    public Temperature(int degrees, bool celsius)
    {
        _degrees = degrees;
        _isCelsius = celsius;
    }
    private bool _isCelsius;
    private int _degrees;
    public int Degrees => _degrees;
    public bool IsCelsius => _isCelsius; 
    public bool IsFahrenheit => !_isCelsius;
    public override string ToString() =>
        $"{_degrees.ToString()}{(_isCelsius ? "C" : "F")}";
    public static Temperature Parse(string input)
    {
        int degrees = int.Parse(input.Substring(0, input.Length - 1));
        bool celsius = (input.Substring(input.Length - 1) == "C");
        return new Temperature(degrees, celsius);
    }
}
```

Este es el convertidor personalizado para el struct anterior:

```csharp
public class TemperatureConverter : JsonConverter<Temperature>
{
    public override Temperature Read(
        ref Utf8JsonReader reader,
        Type typeToConvert,
        JsonSerializerOptions options)
    {
        Debug.Assert(typeToConvert == typeof(Temperature));
        return Temperature.Parse(reader.GetString());
    }

    public override void Write(
        Utf8JsonWriter writer,
        Temperature value,
        JsonSerializerOptions options)
    {
        writer.WriteStringValue(value.ToString());
    }
}
```

El atributo `[JsonConvert]` del struct registra el convertidor personalizado como valor predeterminado para las propiedades de tipo `Temperature`. El convertidor se utiliza automáticamente en la propiedad `TemperatureC` del tipo siguiente al serializar o deserializar:

```csharp
class WeatherForecastWithTemperatureStruct
{
    public DateTimeOffset Date { get; set; }
    public Temperature TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

## <a name="converter-registration-precedence"></a>Prioridad de registro del convertidor

Durante la serialización o la deserialización, se elige un convertidor para cada elemento JSON en el orden siguiente, que se muestra de la prioridad más alta a la más baja:

* `[JsonConverter]` aplicado a una propiedad.
* Convertidor agregado a la colección de `Converters`.
* `[JsonConverter]` aplica a un tipo de valor personalizado o POCO.

Si se registran varios convertidores personalizados para un tipo en la colección `Converters`, se usa el primer convertidor que devuelve true para `CanConvert`.

Solo se elige un convertidor integrado si no se registra ningún convertidor personalizado aplicable.

## <a name="converter-samples-for-common-scenarios"></a>Ejemplos de convertidor para escenarios comunes

En las secciones siguientes se proporcionan ejemplos de convertidor que abordan algunos escenarios comunes que la funcionalidad integrada no controla.

### <a name="deserialize-inferred-types-to-object-properties"></a>Deserializar los tipos deducidos en propiedades de objeto

Al deserializar a una propiedad de tipo `Object`, se crea un objeto `JsonElement`. La razón es que el deserializador no sabe qué tipo de CLR crear y no intenta adivinar. Por ejemplo, si una propiedad JSON tiene "true", el deserializador no infiere que el valor es un `Boolean`y, si un elemento tiene "01/01/2019", el deserializador no deduce que es un `DateTime`.

La inferencia de tipos puede ser incorrecta. Si el deserializador analiza un número JSON que no tiene un separador decimal como `long`, esto podría producir problemas fuera del intervalo si el valor se serializó originalmente como `ulong` o `BigInteger`. El análisis de un número que tiene un separador decimal como `double` podría perder precisión si el número se serializó originalmente como `decimal`.

En escenarios que requieren inferencia de tipos, el código siguiente muestra un convertidor personalizado para `Object` propiedades. El código convierte:

* `true` y `false` a `Boolean`
* Números que se van a `long` o `double`
* Fechas para `DateTime`
* Cadenas que se van a `string`
* Todo lo demás que se va a `JsonElement`

```csharp
using System;
using System.Text.Json;
using System.Text.Json.Serialization;

namespace SystemTextJsonSamples
{
    public class ObjectToInferredTypesConverter
        : JsonConverter<object>
    {
        public override object Read(
            ref Utf8JsonReader reader,
            Type typeToConvert,
            JsonSerializerOptions options)
        {
            if (reader.TokenType == JsonTokenType.True)
            {
                return true;
            }

            if (reader.TokenType == JsonTokenType.False)
            {
                return false;
            }

            if (reader.TokenType == JsonTokenType.Number)
            {
                if (reader.TryGetInt64(out long l))
                {
                    return l;
                }

                return reader.GetDouble();
            }

            if (reader.TokenType == JsonTokenType.String)
            {
                if (reader.TryGetDateTime(out DateTime datetime))
                {
                    return datetime;
                }

                return reader.GetString();
            }

            // Use JsonElement as fallback.
            // Newtonsoft uses JArray or JObject.
            using (JsonDocument document = JsonDocument.ParseValue(ref reader))
            {
                return document.RootElement.Clone();
            }
        }

        public override void Write(
            Utf8JsonWriter writer,
            object value,
            JsonSerializerOptions options)
        {
            throw new InvalidOperationException("Should not get here.");
        }
    }
}
```

El código siguiente registra el convertidor:

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new ObjectToInferredTypesConverter());
```

A continuación se muestra un ejemplo de tipo con una propiedad de objeto:

```csharp
public class WeatherForecastWithObjectProperties
{
    public object Date { get; set; }
    public object TemperatureC { get; set; }
    public object Summary { get; set; }
}
```

El siguiente ejemplo de JSON para deserializar contiene valores que se deserializarán como `DateTime`, `long`y `string`:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
}
```

Sin el convertidor personalizado, la deserialización coloca un `JsonElement` en cada propiedad.

La [carpeta pruebas unitarias](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) del espacio de nombres `System.Text.Json.Serialization` tiene más ejemplos de convertidores personalizados que controlan la deserialización de las propiedades de objeto.

### <a name="support-dictionary-with-non-string-key"></a>Diccionario de soporte con clave que no es de cadena

La compatibilidad integrada con colecciones de diccionario es para `Dictionary<string, TValue>`. Es decir, la clave debe ser una cadena. Para admitir un diccionario con un entero o algún otro tipo como clave, se requiere un convertidor personalizado.

En el código siguiente se muestra un convertidor personalizado que funciona con `Dictionary<Enum,TValue>`:

```csharp
using System;
using System.Collections.Generic;
using System.Reflection;
using System.Text.Json;
using System.Text.Json.Serialization;

namespace SystemTextJsonSamples
{
    public class ConverterDictionaryTKeyEnumTValue : JsonConverterFactory
    {
        public override bool CanConvert(Type typeToConvert)
        {
            if (!typeToConvert.IsGenericType)
            {
                return false;
            }

            if (typeToConvert.GetGenericTypeDefinition() != typeof(Dictionary<,>))
            {
                return false;
            }

            return typeToConvert.GetGenericArguments()[0].IsEnum;
        }

        public override JsonConverter CreateConverter(
            Type type, 
            JsonSerializerOptions options)
        {
            Type keyType = type.GetGenericArguments()[0];
            Type valueType = type.GetGenericArguments()[1];

            JsonConverter converter = (JsonConverter)Activator.CreateInstance(
                typeof(DictionaryEnumConverterInner<,>).MakeGenericType(
                    new Type[] { keyType, valueType }),
                BindingFlags.Instance | BindingFlags.Public,
                binder: null,
                args: new object[] { options },
                culture: null);

            return converter;
        }

        private class DictionaryEnumConverterInner<TKey, TValue> : 
            JsonConverter<Dictionary<TKey, TValue>> where TKey : struct, Enum
        {
            private readonly JsonConverter<TValue> _valueConverter;
            private Type _keyType;
            private Type _valueType;

            public DictionaryEnumConverterInner(JsonSerializerOptions options)
            {
                // For performance, use the existing converter if available.
                _valueConverter = (JsonConverter<TValue>)options
                    .GetConverter(typeof(TValue));

                // Cache the key and value types.
                _keyType = typeof(TKey);
                _valueType = typeof(TValue);
            }

            public override Dictionary<TKey, TValue> Read(
                ref Utf8JsonReader reader, 
                Type typeToConvert, 
                JsonSerializerOptions options)
            {
                if (reader.TokenType != JsonTokenType.StartObject)
                {
                    throw new JsonException();
                }

                Dictionary<TKey, TValue> value = new Dictionary<TKey, TValue>();

                while (reader.Read())
                {
                    if (reader.TokenType == JsonTokenType.EndObject)
                    {
                        return value;
                    }

                    // Get the key.
                    if (reader.TokenType != JsonTokenType.PropertyName)
                    {
                        throw new JsonException();
                    }

                    string propertyName = reader.GetString();

                    // For performance, parse with ignoreCase:false first.
                    if (!Enum.TryParse(propertyName, ignoreCase: false, out TKey key) &&
                        !Enum.TryParse(propertyName, ignoreCase: true, out key))
                    {
                        throw new JsonException(
                            $"Unable to convert \"{propertyName}\" to Enum \"{_keyType}\".");
                    }

                    // Get the value.
                    TValue v;
                    if (_valueConverter != null)
                    {
                        reader.Read();
                        v = _valueConverter.Read(ref reader, _valueType, options);
                    }
                    else
                    {
                        v = JsonSerializer.Deserialize<TValue>(ref reader, options);
                    }

                    // Add to dictionary.
                    value.Add(key, v);
                }

                throw new JsonException();
            }

            public override void Write(
                Utf8JsonWriter writer, 
                Dictionary<TKey, TValue> value, 
                JsonSerializerOptions options)
            {
                writer.WriteStartObject();

                foreach (KeyValuePair<TKey, TValue> kvp in value)
                {
                    writer.WritePropertyName(kvp.Key.ToString());

                    if (_valueConverter != null)
                    {
                        _valueConverter.Write(writer, kvp.Value, options);
                    }
                    else
                    {
                        JsonSerializer.Serialize(writer, kvp.Value, options);
                    }
                }

                writer.WriteEndObject();
            }
        }
    }
}
```

El código siguiente registra el convertidor:

```csharp
var serializeOptions = new JsonSerializerOptions();
serializeOptions.Converters.Add(new ConverterDictionaryTKeyEnumTValue());
```

El convertidor puede serializar y deserializar la propiedad `TemperatureRanges` de la siguiente clase que usa el `Enum`siguiente:

```csharp
public class WeatherForecastWithEnumDictionary
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public Dictionary<SummaryWordsEnum, int> TemperatureRanges { get; set; }
}

public enum SummaryWordsEnum
{
    Cold, Hot
}
```

La salida JSON de la serialización es similar al ejemplo siguiente:

```json
{

  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
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

```csharp
public class Person
{
    public string Name { get; set; }
}

public class Customer : Person
{
    public decimal CreditLimit { get; set; }
}

public class Employee : Person
{
    public string OfficeNumber { get; set; }
}
```

```csharp
using System;
using System.Text.Json;
using System.Text.Json.Serialization;

namespace SystemTextJsonSamples
{
    public class PersonConverterWithTypeDiscriminator : JsonConverter<Person>
    {
        enum TypeDiscriminator
        {
            Customer = 1,
            Employee = 2
        }

        public override bool CanConvert(Type typeToConvert)
        {
            return typeof(Person).IsAssignableFrom(typeToConvert);
        }

        public override Person Read(ref Utf8JsonReader reader, Type typeToConvert, JsonSerializerOptions options)
        {
            if (reader.TokenType != JsonTokenType.StartObject)
            {
                throw new JsonException();
            }

            reader.Read();
            if (reader.TokenType != JsonTokenType.PropertyName)
            {
                throw new JsonException();
            }

            string propertyName = reader.GetString();
            if (propertyName != "TypeDiscriminator")
            {
                throw new JsonException();
            }

            reader.Read();
            if (reader.TokenType != JsonTokenType.Number)
            {
                throw new JsonException();
            }

            Person value;
            TypeDiscriminator typeDiscriminator = (TypeDiscriminator)reader.GetInt32();
            switch (typeDiscriminator)
            {
                case TypeDiscriminator.Customer:
                    value = new Customer();
                    break;

                case TypeDiscriminator.Employee:
                    value = new Employee();
                    break;

                default:
                    throw new JsonException();
            }

            while (reader.Read())
            {
                if (reader.TokenType == JsonTokenType.EndObject)
                {
                    return value;
                }

                if (reader.TokenType == JsonTokenType.PropertyName)
                {
                    propertyName = reader.GetString();
                    reader.Read();
                    switch (propertyName)
                    {
                        case "CreditLimit":
                            decimal creditLimit = reader.GetDecimal();
                            ((Customer)value).CreditLimit = creditLimit;
                            break;
                        case "OfficeNumber":
                            string officeNumber = reader.GetString();
                            ((Employee)value).OfficeNumber = officeNumber;
                            break;
                        case "Name":
                            string name = reader.GetString();
                            value.Name = name;
                            break;
                    }
                }
            }

            throw new JsonException();
        }

        public override void Write(Utf8JsonWriter writer, Person value, JsonSerializerOptions options)
        {
            writer.WriteStartObject();

            if (value is Customer customer)
            {
                writer.WriteNumber("TypeDiscriminator", (int)TypeDiscriminator.Customer);
                writer.WriteNumber("CreditLimit", customer.CreditLimit);
            }
            else if (value is Employee employee)
            {
                writer.WriteNumber("TypeDiscriminator", (int)TypeDiscriminator.Employee);
                writer.WriteString("OfficeNumber", employee.OfficeNumber);
            }

            writer.WriteString("Name", value.Name);

            writer.WriteEndObject();
        }
    }
}
```

El código siguiente registra el convertidor:

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new PersonConverterWithTypeDiscriminator());
```

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
