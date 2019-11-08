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
# <a name="how-to-write-custom-converters-for-json-serialization-in-net"></a><span data-ttu-id="63f38-102">Cómo escribir convertidores personalizados para la serialización de JSON en .NET</span><span class="sxs-lookup"><span data-stu-id="63f38-102">How to write custom converters for JSON serialization in .NET</span></span>

<span data-ttu-id="63f38-103">En este artículo se muestra cómo crear convertidores personalizados para las clases de serialización de JSON que se proporcionan en el espacio de nombres <xref:System.Text.Json>.</span><span class="sxs-lookup"><span data-stu-id="63f38-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:System.Text.Json> namespace.</span></span> <span data-ttu-id="63f38-104">Para obtener una introducción a `System.Text.Json`, vea [Cómo serializar y deserializar JSON en .net](system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="63f38-104">For an introduction to `System.Text.Json`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="63f38-105">Un *convertidor* es una clase que convierte un objeto o un valor a y desde JSON.</span><span class="sxs-lookup"><span data-stu-id="63f38-105">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="63f38-106">El espacio de nombres `System.Text.Json` tiene convertidores integrados para la mayoría de los tipos primitivos que se asignan a primitivos de JavaScript.</span><span class="sxs-lookup"><span data-stu-id="63f38-106">The `System.Text.Json` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="63f38-107">Puede escribir convertidores personalizados:</span><span class="sxs-lookup"><span data-stu-id="63f38-107">You can write custom converters:</span></span>

* <span data-ttu-id="63f38-108">Para reemplazar el comportamiento predeterminado de un convertidor integrado.</span><span class="sxs-lookup"><span data-stu-id="63f38-108">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="63f38-109">Por ejemplo, puede que desee que los valores de `DateTime` se representen con el formato mm/dd/aaaa en lugar del formato ISO 8601-1:2019 predeterminado.</span><span class="sxs-lookup"><span data-stu-id="63f38-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="63f38-110">Para admitir un tipo de valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="63f38-110">To support a custom value type.</span></span> <span data-ttu-id="63f38-111">Por ejemplo, un struct de `PhoneNumber`.</span><span class="sxs-lookup"><span data-stu-id="63f38-111">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="63f38-112">También puede escribir convertidores personalizados para extender `System.Text.Json` con funcionalidad no incluida en la versión actual.</span><span class="sxs-lookup"><span data-stu-id="63f38-112">You can also write custom converters to extend `System.Text.Json` with functionality not included in the current release.</span></span> <span data-ttu-id="63f38-113">Los siguientes escenarios se describen más adelante en este artículo:</span><span class="sxs-lookup"><span data-stu-id="63f38-113">The following scenarios are covered later in this article:</span></span>

* <span data-ttu-id="63f38-114">[Deserializar los tipos deducidos en las propiedades de objeto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="63f38-114">[Deserialize inferred types to Object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="63f38-115">[Diccionario de soporte con clave que no es de cadena](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="63f38-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="63f38-116">[Admitir la deserialización polimórfica](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="63f38-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="63f38-117">Patrones de convertidor personalizados</span><span class="sxs-lookup"><span data-stu-id="63f38-117">Custom converter patterns</span></span>

<span data-ttu-id="63f38-118">Hay dos patrones para crear un convertidor personalizado: el patrón básico y el patrón de fábrica.</span><span class="sxs-lookup"><span data-stu-id="63f38-118">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="63f38-119">El patrón de generador es para los convertidores que controlan el tipo `Enum` o genéricos abiertos.</span><span class="sxs-lookup"><span data-stu-id="63f38-119">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="63f38-120">El patrón básico es para los tipos genéricos no genéricos y cerrados.</span><span class="sxs-lookup"><span data-stu-id="63f38-120">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="63f38-121">Por ejemplo, los convertidores de los siguientes tipos requieren el patrón de fábrica:</span><span class="sxs-lookup"><span data-stu-id="63f38-121">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="63f38-122">Entre los ejemplos de tipos que puede controlar el patrón básico se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="63f38-122">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="63f38-123">El patrón básico crea una clase que puede controlar un tipo.</span><span class="sxs-lookup"><span data-stu-id="63f38-123">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="63f38-124">El modelo de generador crea una clase que determina en tiempo de ejecución qué tipo específico es necesario y crea dinámicamente el convertidor adecuado.</span><span class="sxs-lookup"><span data-stu-id="63f38-124">The factory pattern creates a class that determines at runtime which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="63f38-125">Convertidor básico de ejemplo</span><span class="sxs-lookup"><span data-stu-id="63f38-125">Sample basic converter</span></span>

<span data-ttu-id="63f38-126">El ejemplo siguiente es un convertidor que reemplaza la serialización predeterminada para un tipo de datos existente.</span><span class="sxs-lookup"><span data-stu-id="63f38-126">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="63f38-127">El convertidor usa el formato mm/dd/aaaa para `DateTimeOffset` propiedades.</span><span class="sxs-lookup"><span data-stu-id="63f38-127">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

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

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="63f38-128">Convertidor de patrón de fábrica de ejemplo</span><span class="sxs-lookup"><span data-stu-id="63f38-128">Sample factory pattern converter</span></span>

<span data-ttu-id="63f38-129">En el código siguiente se muestra un convertidor personalizado que funciona con `Dictionary<Enum,TValue>`.</span><span class="sxs-lookup"><span data-stu-id="63f38-129">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="63f38-130">El código sigue el patrón de generador porque el primer parámetro de tipo genérico es `Enum` y el segundo es abierto.</span><span class="sxs-lookup"><span data-stu-id="63f38-130">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="63f38-131">El método `CanConvert` devuelve `true` solo para un `Dictionary` con dos parámetros genéricos, el primero de los cuales es un tipo de `Enum`.</span><span class="sxs-lookup"><span data-stu-id="63f38-131">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="63f38-132">El convertidor interno obtiene un convertidor existente para controlar el tipo que se proporciona en tiempo de ejecución para `TValue`.</span><span class="sxs-lookup"><span data-stu-id="63f38-132">The inner converter gets an existing converter to handle whichever type is provided at runtime for `TValue`.</span></span> 

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

<span data-ttu-id="63f38-133">El código anterior es el mismo que el que se muestra en el [Diccionario de soporte con clave que no es de cadena](#support-dictionary-with-non-string-key) , más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="63f38-133">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="63f38-134">Pasos para seguir el patrón básico</span><span class="sxs-lookup"><span data-stu-id="63f38-134">Steps to follow the basic pattern</span></span>

<span data-ttu-id="63f38-135">En los pasos siguientes se explica cómo crear un convertidor siguiendo el patrón básico:</span><span class="sxs-lookup"><span data-stu-id="63f38-135">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="63f38-136">Cree una clase que derive de <xref:System.Text.Json.Serialization.JsonConverter%601> donde `T` es el tipo que se va a serializar y deserializar.</span><span class="sxs-lookup"><span data-stu-id="63f38-136">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="63f38-137">Invalide el método `Read` para deserializar el JSON de entrada y convertirlo al tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="63f38-137">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="63f38-138">Use el <xref:System.Text.Json.Utf8JsonReader> que se pasa al método para leer el JSON.</span><span class="sxs-lookup"><span data-stu-id="63f38-138">Use the <xref:System.Text.Json.Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="63f38-139">Invalide el método `Write` para serializar el objeto de entrada de tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="63f38-139">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="63f38-140">Use el <xref:System.Text.Json.Utf8JsonWriter> que se pasa al método para escribir el JSON.</span><span class="sxs-lookup"><span data-stu-id="63f38-140">Use the <xref:System.Text.Json.Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="63f38-141">Invalide el método `CanConvert` solo si es necesario.</span><span class="sxs-lookup"><span data-stu-id="63f38-141">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="63f38-142">La implementación predeterminada devuelve `true` cuando el tipo que se va a convertir es `T`de tipo.</span><span class="sxs-lookup"><span data-stu-id="63f38-142">The default implementation returns `true` when the type to convert is type `T`.</span></span> <span data-ttu-id="63f38-143">Por lo tanto, los convertidores que solo admiten el tipo `T` no necesitan invalidar este método.</span><span class="sxs-lookup"><span data-stu-id="63f38-143">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="63f38-144">Para obtener un ejemplo de un convertidor que necesita invalidar este método, consulte la sección [deserialización polimórfica](#support-polymorphic-deserialization) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="63f38-144">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="63f38-145">Puede hacer referencia al [código fuente de los convertidores integrados](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/) como implementaciones de referencia para escribir convertidores personalizados.</span><span class="sxs-lookup"><span data-stu-id="63f38-145">You can refer to the [built-in converters source code](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="63f38-146">Pasos para seguir el patrón de fábrica</span><span class="sxs-lookup"><span data-stu-id="63f38-146">Steps to follow the factory pattern</span></span>

<span data-ttu-id="63f38-147">En los pasos siguientes se explica cómo crear un convertidor siguiendo el patrón de fábrica:</span><span class="sxs-lookup"><span data-stu-id="63f38-147">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="63f38-148">Cree una clase que derive de <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span><span class="sxs-lookup"><span data-stu-id="63f38-148">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="63f38-149">Invalide el método `CanConvert` para devolver true cuando el tipo que se va a convertir es uno que el convertidor puede controlar.</span><span class="sxs-lookup"><span data-stu-id="63f38-149">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="63f38-150">Por ejemplo, si el convertidor es para `List<T>` solo puede controlar `List<int>`, `List<string>`y `List<DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="63f38-150">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span> 
* <span data-ttu-id="63f38-151">Invalide el método `CreateConverter` para devolver una instancia de una clase de convertidor que controlará el tipo de conversión que se proporciona en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="63f38-151">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at runtime.</span></span>
* <span data-ttu-id="63f38-152">Cree la clase de convertidor en la que crea instancias el método `CreateConverter`.</span><span class="sxs-lookup"><span data-stu-id="63f38-152">Create the converter class that the `CreateConverter` method instantiates.</span></span> 

<span data-ttu-id="63f38-153">El patrón de generador es necesario para los genéricos abiertos porque el código para convertir un objeto en una cadena y desde una cadena no es el mismo para todos los tipos.</span><span class="sxs-lookup"><span data-stu-id="63f38-153">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="63f38-154">Un convertidor para un tipo genérico abierto (`List<T>`, por ejemplo) tiene que crear un convertidor para un tipo genérico cerrado (por ejemplo,`List<DateTime>`) en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="63f38-154">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="63f38-155">Debe escribirse código para controlar cada tipo genérico cerrado que el convertidor puede controlar.</span><span class="sxs-lookup"><span data-stu-id="63f38-155">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="63f38-156">El tipo de `Enum` es similar a un tipo genérico abierto: un convertidor para `Enum` tiene que crear un convertidor para un `Enum` específico (`WeekdaysEnum`, por ejemplo) en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="63f38-156">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span> 

## <a name="error-handling"></a><span data-ttu-id="63f38-157">Control de errores</span><span class="sxs-lookup"><span data-stu-id="63f38-157">Error handling</span></span>

<span data-ttu-id="63f38-158">Si necesita producir una excepción en el código de control de errores, considere la posibilidad de iniciar una <xref:System.Text.Json.JsonException> sin un mensaje.</span><span class="sxs-lookup"><span data-stu-id="63f38-158">If you need to throw an exception in error-handling code, consider throwing a <xref:System.Text.Json.JsonException> without a message.</span></span> <span data-ttu-id="63f38-159">Este tipo de excepción crea automáticamente un mensaje que incluye la ruta de acceso a la parte del JSON que causó el error.</span><span class="sxs-lookup"><span data-stu-id="63f38-159">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="63f38-160">Por ejemplo, la instrucción `throw new JsonException();` genera un mensaje de error como el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="63f38-160">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```text
Unhandled exception. System.Text.Json.JsonException: 
The JSON value could not be converted to System.Object. 
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="63f38-161">Si proporciona un mensaje (por ejemplo, `throw new JsonException("Error occurred)`, la excepción sigue proporcionando la ruta de acceso en la propiedad <xref:System.Text.Json.JsonException.Path>.</span><span class="sxs-lookup"><span data-stu-id="63f38-161">If you do provide a message (for example, `throw new JsonException("Error occurred)`, the exception still provides the path in the <xref:System.Text.Json.JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="63f38-162">Registrar un convertidor personalizado</span><span class="sxs-lookup"><span data-stu-id="63f38-162">Register a custom converter</span></span>

<span data-ttu-id="63f38-163">*Registre* un convertidor personalizado para que los métodos `Serialize` y `Deserialize` lo utilicen.</span><span class="sxs-lookup"><span data-stu-id="63f38-163">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="63f38-164">Elija uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="63f38-164">Choose one of the following approaches:</span></span>

* <span data-ttu-id="63f38-165">Agregue una instancia de la clase de convertidor a la colección de <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="63f38-165">Add an instance of the converter class to the <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="63f38-166">Aplique el atributo [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) a las propiedades que requieren el convertidor personalizado.</span><span class="sxs-lookup"><span data-stu-id="63f38-166">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="63f38-167">Aplique el atributo [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) a una clase o un struct que represente un tipo de valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="63f38-167">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="63f38-168">Ejemplo de registro: colección de convertidores</span><span class="sxs-lookup"><span data-stu-id="63f38-168">Registration sample - Converters collection</span></span> 

<span data-ttu-id="63f38-169">Este es un ejemplo que hace que la `ExampleDateTimeOffsetConverter` predeterminada para las propiedades de tipo `DateTimeOffset`:</span><span class="sxs-lookup"><span data-stu-id="63f38-169">Here's an example that makes the `ExampleDateTimeOffsetConverter` the default for properties of type `DateTimeOffset`:</span></span>

```csharp
//...
JsonSerializerOptions options = new JsonSerializerOptions();
options.Converters.Add(new ExampleDateTimeOffsetConverter());
string json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="63f38-170">Suponga que serializa el tipo siguiente:</span><span class="sxs-lookup"><span data-stu-id="63f38-170">Suppose you serialize the following type:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="63f38-171">Este es un ejemplo de salida JSON que muestra que se ha usado el convertidor personalizado:</span><span class="sxs-lookup"><span data-stu-id="63f38-171">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="63f38-172">En el código siguiente se usa el mismo enfoque para deserializar utilizando el convertidor de `DateTimeOffset` personalizado:</span><span class="sxs-lookup"><span data-stu-id="63f38-172">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

```csharp
//...
JsonSerializerOptions options = new JsonSerializerOptions();
options.Converters.Add(new ExampleDateTimeOffsetConverter());
weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json, options);
```

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="63f38-173">Ejemplo de registro-[JsonConverter] en una propiedad</span><span class="sxs-lookup"><span data-stu-id="63f38-173">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="63f38-174">El código siguiente selecciona un convertidor personalizado para la propiedad `Date`:</span><span class="sxs-lookup"><span data-stu-id="63f38-174">The following code selects a custom converter for the `Date` property:</span></span>

```csharp
class WeatherForecastWithConverter
{
    [JsonConverter(typeof(ExampleDateTimeOffsetConverter))]
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="63f38-175">El código para serializar y deserializar `WeatherForecastWithConverter` no requiere el uso de `JsonSerializeOptions.Converters`:</span><span class="sxs-lookup"><span data-stu-id="63f38-175">The code to serialize and deserialize `WeatherForecastWithConverter` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

```csharp
string json = JsonSerializer.Serialize(weatherForecastWithConverter);
```

```csharp
weatherForecast = JsonSerializer.Deserialize<WeatherForecastWithConverter>(json);
```

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="63f38-176">Ejemplo de registro-[JsonConverter] en un tipo</span><span class="sxs-lookup"><span data-stu-id="63f38-176">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="63f38-177">Este es el código que crea un struct y le aplica el `[JsonConverter]` atributo:</span><span class="sxs-lookup"><span data-stu-id="63f38-177">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

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

<span data-ttu-id="63f38-178">Este es el convertidor personalizado para el struct anterior:</span><span class="sxs-lookup"><span data-stu-id="63f38-178">Here's the custom converter for the preceding struct:</span></span>

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

<span data-ttu-id="63f38-179">El atributo `[JsonConvert]` del struct registra el convertidor personalizado como valor predeterminado para las propiedades de tipo `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="63f38-179">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="63f38-180">El convertidor se utiliza automáticamente en la propiedad `TemperatureC` del tipo siguiente al serializar o deserializar:</span><span class="sxs-lookup"><span data-stu-id="63f38-180">The converter is automatically used on the `TemperatureC` property of the following type when you serialize or deserialize it:</span></span>

```csharp
class WeatherForecastWithTemperatureStruct
{
    public DateTimeOffset Date { get; set; }
    public Temperature TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

## <a name="converter-registration-precedence"></a><span data-ttu-id="63f38-181">Prioridad de registro del convertidor</span><span class="sxs-lookup"><span data-stu-id="63f38-181">Converter registration precedence</span></span>

<span data-ttu-id="63f38-182">Durante la serialización o la deserialización, se elige un convertidor para cada elemento JSON en el orden siguiente, que se muestra de la prioridad más alta a la más baja:</span><span class="sxs-lookup"><span data-stu-id="63f38-182">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="63f38-183">`[JsonConverter]` aplicado a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="63f38-183">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="63f38-184">Convertidor agregado a la colección de `Converters`.</span><span class="sxs-lookup"><span data-stu-id="63f38-184">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="63f38-185">`[JsonConverter]` aplica a un tipo de valor personalizado o POCO.</span><span class="sxs-lookup"><span data-stu-id="63f38-185">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="63f38-186">Si se registran varios convertidores personalizados para un tipo en la colección `Converters`, se usa el primer convertidor que devuelve true para `CanConvert`.</span><span class="sxs-lookup"><span data-stu-id="63f38-186">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="63f38-187">Solo se elige un convertidor integrado si no se registra ningún convertidor personalizado aplicable.</span><span class="sxs-lookup"><span data-stu-id="63f38-187">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="63f38-188">Ejemplos de convertidor para escenarios comunes</span><span class="sxs-lookup"><span data-stu-id="63f38-188">Converter samples for common scenarios</span></span>

<span data-ttu-id="63f38-189">En las secciones siguientes se proporcionan ejemplos de convertidor que abordan algunos escenarios comunes que la funcionalidad integrada no controla.</span><span class="sxs-lookup"><span data-stu-id="63f38-189">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="63f38-190">Deserializar los tipos deducidos en propiedades de objeto</span><span class="sxs-lookup"><span data-stu-id="63f38-190">Deserialize inferred types to Object properties</span></span>

<span data-ttu-id="63f38-191">Al deserializar a una propiedad de tipo `Object`, se crea un objeto `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="63f38-191">When deserializing to a property of type `Object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="63f38-192">La razón es que el deserializador no sabe qué tipo de CLR crear y no intenta adivinar.</span><span class="sxs-lookup"><span data-stu-id="63f38-192">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="63f38-193">Por ejemplo, si una propiedad JSON tiene "true", el deserializador no infiere que el valor es un `Boolean`y, si un elemento tiene "01/01/2019", el deserializador no deduce que es un `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="63f38-193">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="63f38-194">La inferencia de tipos puede ser incorrecta.</span><span class="sxs-lookup"><span data-stu-id="63f38-194">Type inference can be inaccurate.</span></span> <span data-ttu-id="63f38-195">Si el deserializador analiza un número JSON que no tiene un separador decimal como `long`, esto podría producir problemas fuera del intervalo si el valor se serializó originalmente como `ulong` o `BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="63f38-195">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="63f38-196">El análisis de un número que tiene un separador decimal como `double` podría perder precisión si el número se serializó originalmente como `decimal`.</span><span class="sxs-lookup"><span data-stu-id="63f38-196">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="63f38-197">En escenarios que requieren inferencia de tipos, el código siguiente muestra un convertidor personalizado para `Object` propiedades.</span><span class="sxs-lookup"><span data-stu-id="63f38-197">For scenarios that require type inference, the following code shows a custom converter for `Object` properties.</span></span> <span data-ttu-id="63f38-198">El código convierte:</span><span class="sxs-lookup"><span data-stu-id="63f38-198">The code converts:</span></span>

* <span data-ttu-id="63f38-199">`true` y `false` a `Boolean`</span><span class="sxs-lookup"><span data-stu-id="63f38-199">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="63f38-200">Números que se van a `long` o `double`</span><span class="sxs-lookup"><span data-stu-id="63f38-200">Numbers to `long` or `double`</span></span>
* <span data-ttu-id="63f38-201">Fechas para `DateTime`</span><span class="sxs-lookup"><span data-stu-id="63f38-201">Dates to `DateTime`</span></span>
* <span data-ttu-id="63f38-202">Cadenas que se van a `string`</span><span class="sxs-lookup"><span data-stu-id="63f38-202">Strings to `string`</span></span>
* <span data-ttu-id="63f38-203">Todo lo demás que se va a `JsonElement`</span><span class="sxs-lookup"><span data-stu-id="63f38-203">Everything else to `JsonElement`</span></span>

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

<span data-ttu-id="63f38-204">El código siguiente registra el convertidor:</span><span class="sxs-lookup"><span data-stu-id="63f38-204">The following code registers the converter:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new ObjectToInferredTypesConverter());
```

<span data-ttu-id="63f38-205">A continuación se muestra un ejemplo de tipo con una propiedad de objeto:</span><span class="sxs-lookup"><span data-stu-id="63f38-205">Here's an example type with an Object property:</span></span>

```csharp
public class WeatherForecastWithObjectProperties
{
    public object Date { get; set; }
    public object TemperatureC { get; set; }
    public object Summary { get; set; }
}
```

<span data-ttu-id="63f38-206">El siguiente ejemplo de JSON para deserializar contiene valores que se deserializarán como `DateTime`, `long`y `string`:</span><span class="sxs-lookup"><span data-stu-id="63f38-206">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="63f38-207">Sin el convertidor personalizado, la deserialización coloca un `JsonElement` en cada propiedad.</span><span class="sxs-lookup"><span data-stu-id="63f38-207">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="63f38-208">La [carpeta pruebas unitarias](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) del espacio de nombres `System.Text.Json.Serialization` tiene más ejemplos de convertidores personalizados que controlan la deserialización de las propiedades de objeto.</span><span class="sxs-lookup"><span data-stu-id="63f38-208">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to Object properties.</span></span>

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="63f38-209">Diccionario de soporte con clave que no es de cadena</span><span class="sxs-lookup"><span data-stu-id="63f38-209">Support Dictionary with non-string key</span></span>

<span data-ttu-id="63f38-210">La compatibilidad integrada con colecciones de diccionario es para `Dictionary<string, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="63f38-210">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="63f38-211">Es decir, la clave debe ser una cadena.</span><span class="sxs-lookup"><span data-stu-id="63f38-211">That is, the key must be a string.</span></span> <span data-ttu-id="63f38-212">Para admitir un diccionario con un entero o algún otro tipo como clave, se requiere un convertidor personalizado.</span><span class="sxs-lookup"><span data-stu-id="63f38-212">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="63f38-213">En el código siguiente se muestra un convertidor personalizado que funciona con `Dictionary<Enum,TValue>`:</span><span class="sxs-lookup"><span data-stu-id="63f38-213">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

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

<span data-ttu-id="63f38-214">El código siguiente registra el convertidor:</span><span class="sxs-lookup"><span data-stu-id="63f38-214">The following code registers the converter:</span></span>

```csharp
var serializeOptions = new JsonSerializerOptions();
serializeOptions.Converters.Add(new ConverterDictionaryTKeyEnumTValue());
```

<span data-ttu-id="63f38-215">El convertidor puede serializar y deserializar la propiedad `TemperatureRanges` de la siguiente clase que usa el `Enum`siguiente:</span><span class="sxs-lookup"><span data-stu-id="63f38-215">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

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

<span data-ttu-id="63f38-216">La salida JSON de la serialización es similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="63f38-216">The JSON output from serialization looks like the following example:</span></span>

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

<span data-ttu-id="63f38-217">La [carpeta pruebas unitarias](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) del espacio de nombres `System.Text.Json.Serialization` tiene más ejemplos de convertidores personalizados que controlan diccionarios que no son de clave de cadena.</span><span class="sxs-lookup"><span data-stu-id="63f38-217">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="63f38-218">Compatibilidad con la deserialización polimórfica</span><span class="sxs-lookup"><span data-stu-id="63f38-218">Support polymorphic deserialization</span></span>

<span data-ttu-id="63f38-219">La [serialización polimórfica](system-text-json-how-to.md#serialize-properties-of-derived-classes) no requiere un convertidor personalizado, pero la deserialización requiere un convertidor personalizado.</span><span class="sxs-lookup"><span data-stu-id="63f38-219">[Polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) doesn't require a custom converter, but deserialization does require a custom converter.</span></span>

<span data-ttu-id="63f38-220">Suponga, por ejemplo, que tiene una `Person` clase base abstracta, con `Employee` y `Customer` clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="63f38-220">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="63f38-221">La deserialización polimórfica significa que, en tiempo de diseño, puede especificar `Person` como destino de la deserialización y `Customer` y `Employee` objetos en el JSON se deserializan correctamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="63f38-221">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at runtime.</span></span> <span data-ttu-id="63f38-222">Durante la deserialización, debe buscar pistas que identifiquen el tipo requerido en JSON.</span><span class="sxs-lookup"><span data-stu-id="63f38-222">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="63f38-223">Los tipos de pistas disponibles varían con cada escenario.</span><span class="sxs-lookup"><span data-stu-id="63f38-223">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="63f38-224">Por ejemplo, una propiedad de discriminador podría estar disponible o podría tener que confiar en la presencia o ausencia de una propiedad determinada.</span><span class="sxs-lookup"><span data-stu-id="63f38-224">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="63f38-225">La versión actual de `System.Text.Json` no proporciona atributos para especificar cómo administrar escenarios de deserialización polimórficos, por lo que se requieren convertidores personalizados.</span><span class="sxs-lookup"><span data-stu-id="63f38-225">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="63f38-226">En el código siguiente se muestra una clase base, dos clases derivadas y un convertidor personalizado para ellas.</span><span class="sxs-lookup"><span data-stu-id="63f38-226">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="63f38-227">El convertidor usa una propiedad de discriminador para realizar la deserialización polimórfica.</span><span class="sxs-lookup"><span data-stu-id="63f38-227">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="63f38-228">El discriminador de tipo no se encuentra en las definiciones de clase, pero se crea durante la serialización y se lee durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="63f38-228">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

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

<span data-ttu-id="63f38-229">El código siguiente registra el convertidor:</span><span class="sxs-lookup"><span data-stu-id="63f38-229">The following code registers the converter:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new PersonConverterWithTypeDiscriminator());
```

<span data-ttu-id="63f38-230">El convertidor puede deserializar JSON que se creó con el mismo convertidor para serializar, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="63f38-230">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

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

## <a name="other-custom-converter-samples"></a><span data-ttu-id="63f38-231">Otros ejemplos de convertidor personalizado</span><span class="sxs-lookup"><span data-stu-id="63f38-231">Other custom converter samples</span></span>

<span data-ttu-id="63f38-232">La [carpeta pruebas unitarias](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) del código fuente de `System.Text.Json.Serialization` incluye otros ejemplos de convertidor personalizados, como:</span><span class="sxs-lookup"><span data-stu-id="63f38-232">The [unit tests folder](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="63f38-233">`Int32` convertidor que convierte null en 0 en la deserialización</span><span class="sxs-lookup"><span data-stu-id="63f38-233">`Int32` converter that converts null to 0 on deserialize</span></span>
* <span data-ttu-id="63f38-234">`Int32` convertidor que permite valores numéricos y de cadena en la deserialización</span><span class="sxs-lookup"><span data-stu-id="63f38-234">`Int32` converter that allows both string and number values on deserialize</span></span>
* <span data-ttu-id="63f38-235">convertidor de `Enum`</span><span class="sxs-lookup"><span data-stu-id="63f38-235">`Enum` converter</span></span>
* <span data-ttu-id="63f38-236">`List<T>` convertidor que acepta datos externos</span><span class="sxs-lookup"><span data-stu-id="63f38-236">`List<T>` converter that accepts external data</span></span>
* <span data-ttu-id="63f38-237">`Long[]` convertidor que funciona con una lista delimitada por comas de números</span><span class="sxs-lookup"><span data-stu-id="63f38-237">`Long[]` converter that works with a comma-delimited list of numbers</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="63f38-238">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="63f38-238">Additional resources</span></span>

* [<span data-ttu-id="63f38-239">Información general de System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="63f38-239">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="63f38-240">Referencia de la API System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="63f38-240">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="63f38-241">Cómo usar System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="63f38-241">How to use System.Text.Json</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="63f38-242">Código fuente para convertidores integrados</span><span class="sxs-lookup"><span data-stu-id="63f38-242">Source code for built-in converters</span></span>](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json/src/System/Text/Json/Serialization/Converters/)
* <span data-ttu-id="63f38-243">Problemas de GitHub relacionados con los convertidores personalizados para `System.Text.Json`</span><span class="sxs-lookup"><span data-stu-id="63f38-243">GitHub issues related to custom converters for `System.Text.Json`</span></span>
  * [<span data-ttu-id="63f38-244">36639 Introducción a convertidores personalizados</span><span class="sxs-lookup"><span data-stu-id="63f38-244">36639 Introducing custom converters</span></span>](https://github.com/dotnet/corefx/issues/36639)
  * [<span data-ttu-id="63f38-245">38713 acerca de la deserialización del objeto</span><span class="sxs-lookup"><span data-stu-id="63f38-245">38713 About deserializing to Object</span></span>](https://github.com/dotnet/corefx/issues/38713)
  * [<span data-ttu-id="63f38-246">40120 acerca de los diccionarios que no son de clave de cadena</span><span class="sxs-lookup"><span data-stu-id="63f38-246">40120 About non-string-key dictionaries</span></span>](https://github.com/dotnet/corefx/issues/40120)
  * [<span data-ttu-id="63f38-247">37787 acerca de la deserialización polimórfica</span><span class="sxs-lookup"><span data-stu-id="63f38-247">37787 About polymorphic deserialization</span></span>](https://github.com/dotnet/corefx/issues/37787)
