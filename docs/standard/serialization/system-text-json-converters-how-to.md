---
title: 'Procedimiento para escribir convertidores personalizados para la serialización de JSON: .NET'
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: 310967f39c3aa7a46d79087bcbf0cb016f7d7284
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159577"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a><span data-ttu-id="30219-102">Procedimiento para escribir convertidores personalizados para la serialización de JSON (cálculo de referencias) en .NET</span><span class="sxs-lookup"><span data-stu-id="30219-102">How to write custom converters for JSON serialization (marshalling) in .NET</span></span>

<span data-ttu-id="30219-103">En este artículo se muestra cómo crear convertidores personalizados para las clases de serialización de JSON que se proporcionan en el espacio de nombres <xref:[!OP.NO-LOC(System.Text.Json)]>.</span><span class="sxs-lookup"><span data-stu-id="30219-103">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:[!OP.NO-LOC(System.Text.Json)]> namespace.</span></span> <span data-ttu-id="30219-104">Para disponer de una introducción a `[!OP.NO-LOC(System.Text.Json)]`, vea [Cómo serializar y deserializar JSON en .NET](system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="30219-104">For an introduction to `[!OP.NO-LOC(System.Text.Json)]`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="30219-105">Un *convertidor* es una clase que convierte un objeto o un valor en JSON; también admite conversiones a partir de este formato.</span><span class="sxs-lookup"><span data-stu-id="30219-105">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="30219-106">El espacio de nombres `[!OP.NO-LOC(System.Text.Json)]` tiene convertidores integrados para la mayoría de los tipos primitivos que se asignan a primitivos de JavaScript.</span><span class="sxs-lookup"><span data-stu-id="30219-106">The `[!OP.NO-LOC(System.Text.Json)]` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="30219-107">Puede escribir convertidores personalizados:</span><span class="sxs-lookup"><span data-stu-id="30219-107">You can write custom converters:</span></span>

* <span data-ttu-id="30219-108">Para reemplazar el comportamiento predeterminado de un convertidor integrado.</span><span class="sxs-lookup"><span data-stu-id="30219-108">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="30219-109">Por ejemplo, puede que quiera que los valores `DateTime` se representen con el formato mm/dd/aaaa, en lugar del formato ISO 8601-1:2019 predeterminado.</span><span class="sxs-lookup"><span data-stu-id="30219-109">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="30219-110">Para admitir un tipo de valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="30219-110">To support a custom value type.</span></span> <span data-ttu-id="30219-111">Por ejemplo, una estructura `PhoneNumber`.</span><span class="sxs-lookup"><span data-stu-id="30219-111">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="30219-112">También puede escribir convertidores personalizados para personalizar o extender `[!OP.NO-LOC(System.Text.Json)]` con funcionalidad no incluida en la versión actual.</span><span class="sxs-lookup"><span data-stu-id="30219-112">You can also write custom converters to customize or extend `[!OP.NO-LOC(System.Text.Json)]` with functionality not included in the current release.</span></span> <span data-ttu-id="30219-113">Los siguientes escenarios se describen más adelante en este artículo:</span><span class="sxs-lookup"><span data-stu-id="30219-113">The following scenarios are covered later in this article:</span></span>

* <span data-ttu-id="30219-114">[Deserialización de tipos inferidos en las propiedades de objeto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="30219-114">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="30219-115">[Compatibilidad para diccionarios con una clave que no sea de cadena](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="30219-115">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="30219-116">[Compatibilidad con la deserialización polimórfica](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="30219-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="30219-117">Patrones de convertidores personalizados</span><span class="sxs-lookup"><span data-stu-id="30219-117">Custom converter patterns</span></span>

<span data-ttu-id="30219-118">Hay dos patrones para crear un convertidor personalizado: el patrón básico y el patrón de fábrica.</span><span class="sxs-lookup"><span data-stu-id="30219-118">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="30219-119">El patrón de fábrica es para los convertidores que controlan el tipo `Enum` o los valores genéricos abiertos.</span><span class="sxs-lookup"><span data-stu-id="30219-119">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="30219-120">El patrón básico es para los tipos no genéricos y los tipos genéricos y cerrados.</span><span class="sxs-lookup"><span data-stu-id="30219-120">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="30219-121">Por ejemplo, los convertidores de los siguientes tipos requieren el patrón de fábrica:</span><span class="sxs-lookup"><span data-stu-id="30219-121">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="30219-122">Entre los ejemplos de tipos que puede controlar el patrón básico se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="30219-122">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="30219-123">El patrón básico crea una clase que puede controlar un tipo.</span><span class="sxs-lookup"><span data-stu-id="30219-123">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="30219-124">El patrón de fábrica crea una clase que determina en tiempo de ejecución qué tipo específico es necesario y crea dinámicamente el convertidor adecuado.</span><span class="sxs-lookup"><span data-stu-id="30219-124">The factory pattern creates a class that determines at runtime which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="30219-125">Convertidor básico de ejemplo</span><span class="sxs-lookup"><span data-stu-id="30219-125">Sample basic converter</span></span>

<span data-ttu-id="30219-126">El ejemplo siguiente es un convertidor que reemplaza la serialización predeterminada para un tipo de datos existente.</span><span class="sxs-lookup"><span data-stu-id="30219-126">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="30219-127">El convertidor usa el formato mm/dd/aaaa para las propiedades `DateTimeOffset`.</span><span class="sxs-lookup"><span data-stu-id="30219-127">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="30219-128">Convertidor de patrones de fábrica de ejemplo</span><span class="sxs-lookup"><span data-stu-id="30219-128">Sample factory pattern converter</span></span>

<span data-ttu-id="30219-129">En el código siguiente se muestra un convertidor personalizado que funciona con `Dictionary<Enum,TValue>`.</span><span class="sxs-lookup"><span data-stu-id="30219-129">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="30219-130">El código sigue el patrón de fábrica porque el primer parámetro de tipo genérico es `Enum` y el segundo es abierto.</span><span class="sxs-lookup"><span data-stu-id="30219-130">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="30219-131">El método `CanConvert` devuelve `true` solo para un elemento `Dictionary` con dos parámetros genéricos, el primero de los cuales es un tipo `Enum`.</span><span class="sxs-lookup"><span data-stu-id="30219-131">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="30219-132">El convertidor interno obtiene un convertidor existente para controlar el tipo que se proporciona en tiempo de ejecución para `TValue`.</span><span class="sxs-lookup"><span data-stu-id="30219-132">The inner converter gets an existing converter to handle whichever type is provided at runtime for `TValue`.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="30219-133">El código anterior es el mismo que el que se muestra en [Compatibilidad para diccionarios con una clave que no sea de cadena](#support-dictionary-with-non-string-key), más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="30219-133">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="30219-134">Pasos para seguir el patrón básico</span><span class="sxs-lookup"><span data-stu-id="30219-134">Steps to follow the basic pattern</span></span>

<span data-ttu-id="30219-135">En los pasos siguientes se explica cómo crear un convertidor siguiendo el patrón básico:</span><span class="sxs-lookup"><span data-stu-id="30219-135">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="30219-136">Cree una clase que derive de <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverter%601>, donde `T` es el tipo que se va a serializar y deserializar.</span><span class="sxs-lookup"><span data-stu-id="30219-136">Create a class that derives from <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="30219-137">Reemplace el método `Read` para deserializar el JSON de entrada y convertirlo al tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="30219-137">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="30219-138">Use el elemento <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonReader> que se pasa al método para leer el JSON.</span><span class="sxs-lookup"><span data-stu-id="30219-138">Use the <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="30219-139">Invalide el método `Write` para serializar el objeto de entrada de tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="30219-139">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="30219-140">Use el elemento <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonWriter> que se pasa al método para escribir el JSON.</span><span class="sxs-lookup"><span data-stu-id="30219-140">Use the <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="30219-141">Reemplace el método `CanConvert` solo si es necesario.</span><span class="sxs-lookup"><span data-stu-id="30219-141">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="30219-142">La implementación predeterminada devuelve `true` cuando el tipo que se va a convertir es de tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="30219-142">The default implementation returns `true` when the type to convert is of type `T`.</span></span> <span data-ttu-id="30219-143">Por lo tanto, los convertidores que solo admiten el tipo `T` no necesitan reemplazar este método.</span><span class="sxs-lookup"><span data-stu-id="30219-143">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="30219-144">Para obtener un ejemplo de un convertidor que necesita reemplazar este método, consulte la sección sobre la [deserialización polimórfica](#support-polymorphic-deserialization), más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="30219-144">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="30219-145">Puede hacer referencia al [código fuente de convertidores integrados](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/[!OP.NO-LOC(System.Text.Json)]/src/[!OP.NO-LOC(System/Text/Json)]/Serialization/Converters/) como implementaciones de referencia para escribir convertidores personalizados.</span><span class="sxs-lookup"><span data-stu-id="30219-145">You can refer to the [built-in converters source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/[!OP.NO-LOC(System.Text.Json)]/src/[!OP.NO-LOC(System/Text/Json)]/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="30219-146">Pasos para seguir el patrón de fábrica</span><span class="sxs-lookup"><span data-stu-id="30219-146">Steps to follow the factory pattern</span></span>

<span data-ttu-id="30219-147">En los pasos siguientes se explica cómo crear un convertidor siguiendo el patrón de fábrica:</span><span class="sxs-lookup"><span data-stu-id="30219-147">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="30219-148">Cree una clase que derive de <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterFactory>.</span><span class="sxs-lookup"><span data-stu-id="30219-148">Create a class that derives from <xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="30219-149">Reemplace el método `CanConvert` para devolver "true" cuando el tipo que se va a convertir sea uno que el convertidor puede controlar.</span><span class="sxs-lookup"><span data-stu-id="30219-149">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="30219-150">Por ejemplo, si el convertidor es para `List<T>`, solo puede controlar `List<int>`, `List<string>` y `List<DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="30219-150">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span>
* <span data-ttu-id="30219-151">Invalide el método `CreateConverter` para devolver una instancia de una clase de convertidor que controlará el tipo de conversión que se proporciona en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="30219-151">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at runtime.</span></span>
* <span data-ttu-id="30219-152">Cree la clase de convertidor de la que el método `CreateConverter` crea instancias.</span><span class="sxs-lookup"><span data-stu-id="30219-152">Create the converter class that the `CreateConverter` method instantiates.</span></span>

<span data-ttu-id="30219-153">El patrón de fábrica es necesario para los genéricos abiertos porque el código para convertir un objeto en una cadena (y también para realizar una conversión a partir de esta) no es el mismo para todos los tipos.</span><span class="sxs-lookup"><span data-stu-id="30219-153">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="30219-154">Un convertidor para un tipo genérico abierto (`List<T>`, por ejemplo) tiene que crear un convertidor para un tipo genérico cerrado (`List<DateTime>`, por ejemplo) en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="30219-154">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="30219-155">Es necesario escribir código para controlar cada tipo genérico cerrado que el convertidor puede controlar.</span><span class="sxs-lookup"><span data-stu-id="30219-155">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="30219-156">El tipo `Enum` es similar a un tipo genérico abierto: un convertidor para `Enum` tiene que crear un convertidor para un elemento `Enum` específico (`WeekdaysEnum`, por ejemplo) en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="30219-156">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span>

## <a name="error-handling"></a><span data-ttu-id="30219-157">Control de errores</span><span class="sxs-lookup"><span data-stu-id="30219-157">Error handling</span></span>

<span data-ttu-id="30219-158">Si necesita producir una excepción en el código de control de errores, considere la posibilidad de iniciar una excepción <xref:[!OP.NO-LOC(System.Text.Json)].JsonException> sin un mensaje.</span><span class="sxs-lookup"><span data-stu-id="30219-158">If you need to throw an exception in error-handling code, consider throwing a <xref:[!OP.NO-LOC(System.Text.Json)].JsonException> without a message.</span></span> <span data-ttu-id="30219-159">Este tipo de excepción crea automáticamente un mensaje que incluye la ruta de acceso a la parte del JSON que causó el error.</span><span class="sxs-lookup"><span data-stu-id="30219-159">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="30219-160">Por ejemplo, la instrucción `throw new JsonException();` genera un mensaje de error como el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="30219-160">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```
Unhandled exception. [!OP.NO-LOC(System.Text.Json)].JsonException:
The JSON value could not be converted to System.Object.
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="30219-161">Si proporciona un mensaje (por ejemplo, `throw new JsonException("Error occurred")`), la excepción sigue proporcionando la ruta de acceso en la propiedad <xref:[!OP.NO-LOC(System.Text.Json)].JsonException.Path>.</span><span class="sxs-lookup"><span data-stu-id="30219-161">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the exception still provides the path in the <xref:[!OP.NO-LOC(System.Text.Json)].JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="30219-162">Registro de un convertidor personalizado</span><span class="sxs-lookup"><span data-stu-id="30219-162">Register a custom converter</span></span>

<span data-ttu-id="30219-163">*Registre* un convertidor personalizado para que los métodos `Serialize` y `Deserialize` lo utilicen.</span><span class="sxs-lookup"><span data-stu-id="30219-163">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="30219-164">Elija uno de los enfoques siguientes:</span><span class="sxs-lookup"><span data-stu-id="30219-164">Choose one of the following approaches:</span></span>

* <span data-ttu-id="30219-165">Agregue una instancia de la clase de convertidor a la colección <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="30219-165">Add an instance of the converter class to the <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="30219-166">Aplique el atributo [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute) a las propiedades que requieren el convertidor personalizado.</span><span class="sxs-lookup"><span data-stu-id="30219-166">Apply the [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="30219-167">Aplique el atributo [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute) a una clase o una estructura que represente un tipo de valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="30219-167">Apply the [[JsonConverter]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="30219-168">Ejemplo de registro: colección de convertidores</span><span class="sxs-lookup"><span data-stu-id="30219-168">Registration sample - Converters collection</span></span>

<span data-ttu-id="30219-169">Este es un ejemplo que hace que <xref:System.ComponentModel.DateTimeOffsetConverter> sea el valor predeterminado para propiedades de tipo <xref:System.DateTimeOffset>:</span><span class="sxs-lookup"><span data-stu-id="30219-169">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

<span data-ttu-id="30219-170">Suponga que serializa una instancia del tipo siguiente:</span><span class="sxs-lookup"><span data-stu-id="30219-170">Suppose you serialize an instance of the following type:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="30219-171">Este es un ejemplo de salida JSON que muestra que se ha usado el convertidor personalizado:</span><span class="sxs-lookup"><span data-stu-id="30219-171">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="30219-172">En el código siguiente se usa el mismo enfoque para realizar una deserialización mediante el convertidor `DateTimeOffset` personalizado:</span><span class="sxs-lookup"><span data-stu-id="30219-172">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="30219-173">Ejemplo de registro: [JsonConverter] en una propiedad</span><span class="sxs-lookup"><span data-stu-id="30219-173">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="30219-174">El código siguiente selecciona un convertidor personalizado para la propiedad `Date`:</span><span class="sxs-lookup"><span data-stu-id="30219-174">The following code selects a custom converter for the `Date` property:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

<span data-ttu-id="30219-175">El código para serializar `WeatherForecastWithConverterAttribute` no requiere el uso de `JsonSerializeOptions.Converters`:</span><span class="sxs-lookup"><span data-stu-id="30219-175">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

<span data-ttu-id="30219-176">El código que se va a deserializar tampoco requiere el uso de `Converters`:</span><span class="sxs-lookup"><span data-stu-id="30219-176">The code to deserialize also doesn't require the use of `Converters`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="30219-177">Ejemplo de registro: [JsonConverter] en un tipo</span><span class="sxs-lookup"><span data-stu-id="30219-177">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="30219-178">Este es el código que crea una estructura y le aplica el atributo `[JsonConverter]`:</span><span class="sxs-lookup"><span data-stu-id="30219-178">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Temperature.cs)]

<span data-ttu-id="30219-179">Este es el convertidor personalizado para la estructura anterior:</span><span class="sxs-lookup"><span data-stu-id="30219-179">Here's the custom converter for the preceding struct:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/TemperatureConverter.cs)]

<span data-ttu-id="30219-180">El atributo `[JsonConvert]` de la estructura registra el convertidor personalizado como valor predeterminado para las propiedades de tipo `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="30219-180">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="30219-181">El convertidor se usa automáticamente en la propiedad `TemperatureCelsius` del tipo siguiente al serializarla o deserializarla:</span><span class="sxs-lookup"><span data-stu-id="30219-181">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a><span data-ttu-id="30219-182">Prioridad de registro del convertidor</span><span class="sxs-lookup"><span data-stu-id="30219-182">Converter registration precedence</span></span>

<span data-ttu-id="30219-183">Durante la serialización o la deserialización, se elige un convertidor para cada elemento JSON en el orden siguiente, que se muestra de la prioridad más alta a la más baja:</span><span class="sxs-lookup"><span data-stu-id="30219-183">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="30219-184">Elemento `[JsonConverter]` aplicado a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="30219-184">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="30219-185">Convertidor agregado a la colección `Converters`.</span><span class="sxs-lookup"><span data-stu-id="30219-185">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="30219-186">Elemento `[JsonConverter]` aplicado a un tipo de valor personalizado o POCO.</span><span class="sxs-lookup"><span data-stu-id="30219-186">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="30219-187">Si se registran varios convertidores personalizados para un tipo en la colección `Converters`, se usa el primer convertidor que devuelve "true" para `CanConvert`.</span><span class="sxs-lookup"><span data-stu-id="30219-187">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="30219-188">Solo se elige un convertidor integrado si no se registra ningún convertidor personalizado aplicable.</span><span class="sxs-lookup"><span data-stu-id="30219-188">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="30219-189">Ejemplos de convertidor para escenarios comunes</span><span class="sxs-lookup"><span data-stu-id="30219-189">Converter samples for common scenarios</span></span>

<span data-ttu-id="30219-190">En las secciones siguientes se proporcionan ejemplos de convertidor que abordan algunos escenarios comunes que la funcionalidad integrada no controla.</span><span class="sxs-lookup"><span data-stu-id="30219-190">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

* [<span data-ttu-id="30219-191">Deserialización de los tipos inferidos en propiedades de objeto</span><span class="sxs-lookup"><span data-stu-id="30219-191">Deserialize inferred types to object properties</span></span>](#deserialize-inferred-types-to-object-properties)
* [<span data-ttu-id="30219-192">Compatibilidad para diccionarios con una clave que no sea de cadena</span><span class="sxs-lookup"><span data-stu-id="30219-192">Support Dictionary with non-string key</span></span>](#support-dictionary-with-non-string-key)
* [<span data-ttu-id="30219-193">Compatibilidad con la deserialización polimórfica</span><span class="sxs-lookup"><span data-stu-id="30219-193">Support polymorphic deserialization</span></span>](#support-polymorphic-deserialization)

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="30219-194">Deserialización de los tipos inferidos en propiedades de objeto</span><span class="sxs-lookup"><span data-stu-id="30219-194">Deserialize inferred types to object properties</span></span>

<span data-ttu-id="30219-195">Al realizar una deserialización en una propiedad de tipo `object`, se crea un objeto `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="30219-195">When deserializing to a property of type `object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="30219-196">La razón es que el deserializador no sabe qué tipo de CLR debe crear, y tampoco intenta averiguarlo.</span><span class="sxs-lookup"><span data-stu-id="30219-196">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="30219-197">Por ejemplo, si una propiedad JSON tiene "true", el deserializador no infiere que el valor es de tipo `Boolean`, y si un elemento tiene "01/01/2019", el deserializador no infiere que es de tipo `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="30219-197">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="30219-198">La inferencia de tipos puede ser incorrecta.</span><span class="sxs-lookup"><span data-stu-id="30219-198">Type inference can be inaccurate.</span></span> <span data-ttu-id="30219-199">Si el deserializador analiza un número JSON que no tiene un separador decimal como `long`, pueden producirse problemas de salida del intervalo si el valor se serializó originalmente como `ulong` o `BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="30219-199">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="30219-200">El análisis de un número que tiene un separador decimal como `double` puede perder precisión si el número se ha serializado originalmente como `decimal`.</span><span class="sxs-lookup"><span data-stu-id="30219-200">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="30219-201">En escenarios que requieren inferencia de tipos, el código siguiente muestra un convertidor personalizado para las propiedades `object`.</span><span class="sxs-lookup"><span data-stu-id="30219-201">For scenarios that require type inference, the following code shows a custom converter for `object` properties.</span></span> <span data-ttu-id="30219-202">El código convierte:</span><span class="sxs-lookup"><span data-stu-id="30219-202">The code converts:</span></span>

* <span data-ttu-id="30219-203">`true` y `false`, en `Boolean`</span><span class="sxs-lookup"><span data-stu-id="30219-203">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="30219-204">Números sin decimales, en `long`</span><span class="sxs-lookup"><span data-stu-id="30219-204">Numbers without a decimal to `long`</span></span>
* <span data-ttu-id="30219-205">Números con un decimal, en `double`</span><span class="sxs-lookup"><span data-stu-id="30219-205">Numbers with a decimal to `double`</span></span>
* <span data-ttu-id="30219-206">Fechas, en `DateTime`</span><span class="sxs-lookup"><span data-stu-id="30219-206">Dates to `DateTime`</span></span>
* <span data-ttu-id="30219-207">Cadenas, en `string`</span><span class="sxs-lookup"><span data-stu-id="30219-207">Strings to `string`</span></span>
* <span data-ttu-id="30219-208">Todo lo demás, en `JsonElement`</span><span class="sxs-lookup"><span data-stu-id="30219-208">Everything else to `JsonElement`</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ObjectToInferredTypesConverter.cs)]

<span data-ttu-id="30219-209">El código siguiente registra el convertidor:</span><span class="sxs-lookup"><span data-stu-id="30219-209">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeInferredTypesToObject.cs?name=SnippetRegister)]

<span data-ttu-id="30219-210">Este es un ejemplo de tipo con propiedades `object`:</span><span class="sxs-lookup"><span data-stu-id="30219-210">Here's an example type with `object` properties:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

<span data-ttu-id="30219-211">El siguiente ejemplo de JSON para deserializar contiene valores que se deserializarán como `DateTime`, `long` y `string`:</span><span class="sxs-lookup"><span data-stu-id="30219-211">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="30219-212">Sin el convertidor personalizado, la deserialización coloca un elemento `JsonElement` en cada propiedad.</span><span class="sxs-lookup"><span data-stu-id="30219-212">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="30219-213">La [carpeta de pruebas unitarias](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) en el espacio de nombres `System.Text.Json.Serialization` tiene más ejemplos de convertidores personalizados que controlan la deserialización en propiedades `object`.</span><span class="sxs-lookup"><span data-stu-id="30219-213">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to `object` properties.</span></span>

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="30219-214">Compatibilidad para diccionarios con una clave que no sea de cadena</span><span class="sxs-lookup"><span data-stu-id="30219-214">Support Dictionary with non-string key</span></span>

<span data-ttu-id="30219-215">La compatibilidad integrada con colecciones de diccionarios es para `Dictionary<string, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="30219-215">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="30219-216">Por lo tanto, la clave debe ser una cadena.</span><span class="sxs-lookup"><span data-stu-id="30219-216">That is, the key must be a string.</span></span> <span data-ttu-id="30219-217">Para admitir un diccionario con un entero o algún otro tipo como clave, se requiere un convertidor personalizado.</span><span class="sxs-lookup"><span data-stu-id="30219-217">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="30219-218">En el código siguiente se muestra un convertidor personalizado que funciona con `Dictionary<Enum,TValue>`:</span><span class="sxs-lookup"><span data-stu-id="30219-218">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="30219-219">El código siguiente registra el convertidor:</span><span class="sxs-lookup"><span data-stu-id="30219-219">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

<span data-ttu-id="30219-220">El convertidor puede serializar y deserializar la propiedad `TemperatureRanges` de la siguiente clase que usa el elemento `Enum` siguiente:</span><span class="sxs-lookup"><span data-stu-id="30219-220">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

<span data-ttu-id="30219-221">La salida JSON de la serialización es similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="30219-221">The JSON output from serialization looks like the following example:</span></span>

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

<span data-ttu-id="30219-222">La [carpeta de pruebas unitarias](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) en el espacio de nombres `System.Text.Json.Serialization` tiene más ejemplos de convertidores personalizados que controlan los diccionarios con una clave que no sea de cadena.</span><span class="sxs-lookup"><span data-stu-id="30219-222">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="30219-223">Compatibilidad con la deserialización polimórfica</span><span class="sxs-lookup"><span data-stu-id="30219-223">Support polymorphic deserialization</span></span>

<span data-ttu-id="30219-224">Las características integradas proporcionan una gama limitada de [serialización polimórfica](system-text-json-how-to.md#serialize-properties-of-derived-classes), pero no admiten ningún tipo de deserialización.</span><span class="sxs-lookup"><span data-stu-id="30219-224">Built-in features provide a limited range of [polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) but no support for deserialization at all.</span></span> <span data-ttu-id="30219-225">La deserialización requiere un convertidor personalizado.</span><span class="sxs-lookup"><span data-stu-id="30219-225">Deserialization requires a custom converter.</span></span>

<span data-ttu-id="30219-226">Suponga, por ejemplo, que tiene una clase base abstracta `Person`, con clases derivadas `Employee` y `Customer`.</span><span class="sxs-lookup"><span data-stu-id="30219-226">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="30219-227">La deserialización polimórfica significa que, al realizar el diseño, puede especificar `Person` como destino de la deserialización, y los objetos `Customer` y `Employee` en el JSON se deserializan correctamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="30219-227">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at runtime.</span></span> <span data-ttu-id="30219-228">Durante la deserialización, debe buscar pistas que identifiquen el tipo requerido en JSON.</span><span class="sxs-lookup"><span data-stu-id="30219-228">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="30219-229">Los tipos de pistas disponibles varían según cada escenario.</span><span class="sxs-lookup"><span data-stu-id="30219-229">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="30219-230">Por ejemplo, una propiedad de discriminador puede estar disponible o puede tener que confiar en la presencia o ausencia de una propiedad determinada.</span><span class="sxs-lookup"><span data-stu-id="30219-230">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="30219-231">La versión actual de `System.Text.Json` no proporciona atributos para especificar cómo controlar los escenarios de deserialización polimórficos, por lo que se requieren convertidores personalizados.</span><span class="sxs-lookup"><span data-stu-id="30219-231">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="30219-232">En el código siguiente se muestra una clase base, dos clases derivadas y un convertidor personalizado para ellas.</span><span class="sxs-lookup"><span data-stu-id="30219-232">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="30219-233">El convertidor usa una propiedad de discriminador para realizar la deserialización polimórfica.</span><span class="sxs-lookup"><span data-stu-id="30219-233">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="30219-234">El discriminador de tipo no se encuentra en las definiciones de clase, pero se crea durante la serialización y se lee durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="30219-234">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/PersonConverterWithTypeDiscriminator.cs)]

<span data-ttu-id="30219-235">El código siguiente registra el convertidor:</span><span class="sxs-lookup"><span data-stu-id="30219-235">The following code registers the converter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPolymorphic.cs?name=SnippetRegister)]

<span data-ttu-id="30219-236">El convertidor puede deserializar el JSON que se creó con el mismo convertidor para serializar, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="30219-236">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

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

<span data-ttu-id="30219-237">El código del convertidor en el ejemplo anterior lee y escribe cada propiedad manualmente.</span><span class="sxs-lookup"><span data-stu-id="30219-237">The converter code in the preceding example reads and writes each property manually.</span></span> <span data-ttu-id="30219-238">Una alternativa es llamar a `Deserialize` o `Serialize` para realizar parte del trabajo.</span><span class="sxs-lookup"><span data-stu-id="30219-238">An alternative is to call `Deserialize` or `Serialize` to do some of the work.</span></span> <span data-ttu-id="30219-239">Para obtener un ejemplo, vea [esta publicación de StackOverflow](https://stackoverflow.com/a/59744873/12509023).</span><span class="sxs-lookup"><span data-stu-id="30219-239">For an example, see [this StackOverflow post](https://stackoverflow.com/a/59744873/12509023).</span></span>

## <a name="other-custom-converter-samples"></a><span data-ttu-id="30219-240">Otros ejemplos de convertidor personalizado</span><span class="sxs-lookup"><span data-stu-id="30219-240">Other custom converter samples</span></span>

<span data-ttu-id="30219-241">El artículo [Migración de Newtonsoft.Json a System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) contiene ejemplos adicionales de convertidores personalizados.</span><span class="sxs-lookup"><span data-stu-id="30219-241">The [Migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) article contains additional samples of custom converters.</span></span>

<span data-ttu-id="30219-242">La [carpeta de pruebas unitarias](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) en el código fuente de `System.Text.Json.Serialization` incluye otros ejemplos de convertidor personalizado, como:</span><span class="sxs-lookup"><span data-stu-id="30219-242">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="30219-243">[Convertidor Int32 que convierte valores nulos en 0 al realizar la deserialización](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span><span class="sxs-lookup"><span data-stu-id="30219-243">[Int32 converter that converts null to 0 on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span></span>
* <span data-ttu-id="30219-244">[Convertidor Int32 que permite valores de cadena y número al realizar la deserialización](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span><span class="sxs-lookup"><span data-stu-id="30219-244">[Int32 converter that allows both string and number values on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span></span>
* <span data-ttu-id="30219-245">[Convertidor Enum](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span><span class="sxs-lookup"><span data-stu-id="30219-245">[Enum converter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span></span>
* <span data-ttu-id="30219-246">[Convertidor List\<T > que acepta datos externos](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span><span class="sxs-lookup"><span data-stu-id="30219-246">[List\<T> converter that accepts external data](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span></span>
* <span data-ttu-id="30219-247">[Convertidor Long[] que funciona con una lista de números delimitados por comas](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span><span class="sxs-lookup"><span data-stu-id="30219-247">[Long[] converter that works with a comma-delimited list of numbers](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span></span>

<span data-ttu-id="30219-248">Si necesita crear un convertidor que modifique el comportamiento de un convertidor integrado existente, puede obtener el [código fuente del convertidor existente](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) para que sirva como punto de partida para la personalización.</span><span class="sxs-lookup"><span data-stu-id="30219-248">If you need to make a converter that modifies the behavior of an existing built-in converter, you can get [the source code of the existing converter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) to serve as a starting point for customization.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="30219-249">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="30219-249">Additional resources</span></span>

* <span data-ttu-id="30219-250">[Código fuente para convertidores integrados](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span><span class="sxs-lookup"><span data-stu-id="30219-250">[Source code for built-in converters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span></span>
* <span data-ttu-id="30219-251">[Compatibilidad con DateTime y DateTimeOffset en System.Text.Json](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="30219-251">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="30219-252">[Información general sobre System.Text.Json](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="30219-252">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* <span data-ttu-id="30219-253">[Procedimiento para usar System.Text.Json](system-text-json-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="30219-253">[How to use System.Text.Json](system-text-json-how-to.md)</span></span>
* <span data-ttu-id="30219-254">[Procedimiento para migrar de Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="30219-254">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* <span data-ttu-id="30219-255">[Referencia de API de System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="30219-255">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="30219-256">[Referencia de API de System.Text.Json.Serialization](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="30219-256">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
