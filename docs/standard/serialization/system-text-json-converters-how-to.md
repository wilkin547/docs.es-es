---
title: 'Procedimiento para escribir convertidores personalizados para la serialización de JSON: .NET'
description: Aprenda a crear convertidores personalizados para las clases de serialización de JSON que se proporcionan en el espacio de nombres System.Text.Json.
ms.date: 12/09/2020
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
ms.openlocfilehash: 33334ccd8bad4ac5a9f5dccde79ff3ae09ca8f89
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008869"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a><span data-ttu-id="aa5a8-103">Procedimiento para escribir convertidores personalizados para la serialización de JSON (cálculo de referencias) en .NET</span><span class="sxs-lookup"><span data-stu-id="aa5a8-103">How to write custom converters for JSON serialization (marshalling) in .NET</span></span>

<span data-ttu-id="aa5a8-104">En este artículo se muestra cómo crear convertidores personalizados para las clases de serialización de JSON que se proporcionan en el espacio de nombres <xref:System.Text.Json>.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-104">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:System.Text.Json> namespace.</span></span> <span data-ttu-id="aa5a8-105">Para disponer de una introducción a `System.Text.Json`, vea [Cómo serializar y deserializar JSON en .NET](system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="aa5a8-105">For an introduction to `System.Text.Json`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="aa5a8-106">Un *convertidor* es una clase que convierte un objeto o un valor en JSON; también admite conversiones a partir de este formato.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-106">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="aa5a8-107">El espacio de nombres `System.Text.Json` tiene convertidores integrados para la mayoría de los tipos primitivos que se asignan a primitivos de JavaScript.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-107">The `System.Text.Json` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="aa5a8-108">Puede escribir convertidores personalizados:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-108">You can write custom converters:</span></span>

* <span data-ttu-id="aa5a8-109">Para reemplazar el comportamiento predeterminado de un convertidor integrado.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-109">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="aa5a8-110">Por ejemplo, puede que quiera que los valores de `DateTime` se representen con el formato mm/dd/aaaa.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-110">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format.</span></span> <span data-ttu-id="aa5a8-111">De forma predeterminada, se admite ISO 8601-1:2019, incluido el perfil RFC 3339.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-111">By default, ISO 8601-1:2019 is supported, including the RFC 3339 profile.</span></span> <span data-ttu-id="aa5a8-112">Para obtener más información, consulte [Compatibilidad con DateTime y DateTimeOffset en System.Text.Json](../datetime/system-text-json-support.md).</span><span class="sxs-lookup"><span data-stu-id="aa5a8-112">For more information, see [DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md).</span></span>
* <span data-ttu-id="aa5a8-113">Para admitir un tipo de valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-113">To support a custom value type.</span></span> <span data-ttu-id="aa5a8-114">Por ejemplo, una estructura `PhoneNumber`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-114">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="aa5a8-115">También puede escribir convertidores personalizados para personalizar o extender `System.Text.Json` con funcionalidad no incluida en la versión actual.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-115">You can also write custom converters to customize or extend `System.Text.Json` with functionality not included in the current release.</span></span> <span data-ttu-id="aa5a8-116">Los siguientes escenarios se describen más adelante en este artículo:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-116">The following scenarios are covered later in this article:</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="aa5a8-117">[Deserialización de tipos inferidos en las propiedades de objeto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="aa5a8-117">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="aa5a8-118">[Compatibilidad con la deserialización polimórfica](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="aa5a8-118">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="aa5a8-119">[Compatibilidad con el recorrido de ida y vuelta para Stack\<T>](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="aa5a8-119">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="aa5a8-120">[Deserialización de tipos inferidos en las propiedades de objeto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="aa5a8-120">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="aa5a8-121">[Compatibilidad para diccionarios con una clave que no sea de cadena](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="aa5a8-121">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="aa5a8-122">[Compatibilidad con la deserialización polimórfica](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="aa5a8-122">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="aa5a8-123">[Compatibilidad con el recorrido de ida y vuelta para Stack\<T>](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="aa5a8-123">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>
::: zone-end

<span data-ttu-id="aa5a8-124">En el código que escriba para un convertidor personalizado, tenga en cuenta la importante penalización de rendimiento para el uso de nuevas instancias de <xref:System.Text.Json.JsonSerializerOptions>.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-124">In the code you write for a custom converter, be aware of the substantial performance penalty for using new <xref:System.Text.Json.JsonSerializerOptions> instances.</span></span> <span data-ttu-id="aa5a8-125">Para obtener más información, vea [Reutilización de instancias de JsonSerializerOptions](system-text-json-configure-options.md#reuse-jsonserializeroptions-instances).</span><span class="sxs-lookup"><span data-stu-id="aa5a8-125">For more information, see [Reuse JsonSerializerOptions instances](system-text-json-configure-options.md#reuse-jsonserializeroptions-instances).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="aa5a8-126">Patrones de convertidores personalizados</span><span class="sxs-lookup"><span data-stu-id="aa5a8-126">Custom converter patterns</span></span>

<span data-ttu-id="aa5a8-127">Hay dos patrones para crear un convertidor personalizado: el patrón básico y el patrón de fábrica.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-127">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="aa5a8-128">El patrón de fábrica es para los convertidores que controlan el tipo `Enum` o los valores genéricos abiertos.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-128">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="aa5a8-129">El patrón básico es para los tipos no genéricos y los tipos genéricos y cerrados.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-129">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="aa5a8-130">Por ejemplo, los convertidores de los siguientes tipos requieren el patrón de fábrica:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-130">For example, converters for the following types require the factory pattern:</span></span>

* <xref:System.Collections.Generic.Dictionary%602>
* <xref:System.Enum>
* <xref:System.Collections.Generic.List%601>

<span data-ttu-id="aa5a8-131">Entre los ejemplos de tipos que puede controlar el patrón básico se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-131">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* <xref:System.DateTime>
* <xref:System.Int32>

<span data-ttu-id="aa5a8-132">El patrón básico crea una clase que puede controlar un tipo.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-132">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="aa5a8-133">El patrón de fábrica crea una clase que determina, en tiempo de ejecución, qué tipo específico es necesario y crea dinámicamente el convertidor adecuado.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-133">The factory pattern creates a class that determines, at run time, which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="aa5a8-134">Convertidor básico de ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa5a8-134">Sample basic converter</span></span>

<span data-ttu-id="aa5a8-135">El ejemplo siguiente es un convertidor que reemplaza la serialización predeterminada para un tipo de datos existente.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-135">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="aa5a8-136">El convertidor usa el formato mm/dd/aaaa para las propiedades `DateTimeOffset`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-136">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DateTimeOffsetConverter.cs":::

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="aa5a8-137">Convertidor de patrones de fábrica de ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa5a8-137">Sample factory pattern converter</span></span>

<span data-ttu-id="aa5a8-138">En el código siguiente se muestra un convertidor personalizado que funciona con `Dictionary<Enum,TValue>`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-138">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="aa5a8-139">El código sigue el patrón de fábrica porque el primer parámetro de tipo genérico es `Enum` y el segundo es abierto.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-139">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="aa5a8-140">El método `CanConvert` devuelve `true` solo para un elemento `Dictionary` con dos parámetros genéricos, el primero de los cuales es un tipo `Enum`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-140">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="aa5a8-141">El convertidor interno obtiene un convertidor existente para controlar el tipo que se proporciona en tiempo de ejecución para `TValue`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-141">The inner converter gets an existing converter to handle whichever type is provided at run time for `TValue`.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DictionaryTKeyEnumTValueConverter.cs":::

<span data-ttu-id="aa5a8-142">El código anterior es el mismo que el que se muestra en [Compatibilidad para diccionarios con una clave que no sea de cadena](#support-dictionary-with-non-string-key), más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-142">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="aa5a8-143">Pasos para seguir el patrón básico</span><span class="sxs-lookup"><span data-stu-id="aa5a8-143">Steps to follow the basic pattern</span></span>

<span data-ttu-id="aa5a8-144">En los pasos siguientes se explica cómo crear un convertidor siguiendo el patrón básico:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-144">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="aa5a8-145">Cree una clase que derive de <xref:System.Text.Json.Serialization.JsonConverter%601>, donde `T` es el tipo que se va a serializar y deserializar.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-145">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="aa5a8-146">Reemplace el método `Read` para deserializar el JSON de entrada y convertirlo al tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-146">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="aa5a8-147">Use el elemento <xref:System.Text.Json.Utf8JsonReader> que se pasa al método para leer el JSON.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-147">Use the <xref:System.Text.Json.Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="aa5a8-148">Invalide el método `Write` para serializar el objeto de entrada de tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-148">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="aa5a8-149">Use el elemento <xref:System.Text.Json.Utf8JsonWriter> que se pasa al método para escribir el JSON.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-149">Use the <xref:System.Text.Json.Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="aa5a8-150">Reemplace el método `CanConvert` solo si es necesario.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-150">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="aa5a8-151">La implementación predeterminada devuelve `true` cuando el tipo que se va a convertir es de tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-151">The default implementation returns `true` when the type to convert is of type `T`.</span></span> <span data-ttu-id="aa5a8-152">Por lo tanto, los convertidores que solo admiten el tipo `T` no necesitan reemplazar este método.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-152">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="aa5a8-153">Para obtener un ejemplo de un convertidor que necesita reemplazar este método, consulte la sección sobre la [deserialización polimórfica](#support-polymorphic-deserialization), más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-153">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="aa5a8-154">Puede hacer referencia al [código fuente de convertidores integrados](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) como implementaciones de referencia para escribir convertidores personalizados.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-154">You can refer to the [built-in converters source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="aa5a8-155">Pasos para seguir el patrón de fábrica</span><span class="sxs-lookup"><span data-stu-id="aa5a8-155">Steps to follow the factory pattern</span></span>

<span data-ttu-id="aa5a8-156">En los pasos siguientes se explica cómo crear un convertidor siguiendo el patrón de fábrica:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-156">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="aa5a8-157">Cree una clase que derive de <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-157">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="aa5a8-158">Reemplace el método `CanConvert` para devolver "true" cuando el tipo que se va a convertir sea uno que el convertidor puede controlar.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-158">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="aa5a8-159">Por ejemplo, si el convertidor es para `List<T>`, solo puede controlar `List<int>`, `List<string>` y `List<DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-159">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span>
* <span data-ttu-id="aa5a8-160">Invalide el método `CreateConverter` para devolver una instancia de una clase de convertidor que controlará el tipo de conversión que se proporciona en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-160">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at run time.</span></span>
* <span data-ttu-id="aa5a8-161">Cree la clase de convertidor de la que el método `CreateConverter` crea instancias.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-161">Create the converter class that the `CreateConverter` method instantiates.</span></span>

<span data-ttu-id="aa5a8-162">El patrón de fábrica es necesario para los genéricos abiertos porque el código para convertir un objeto en una cadena (y también para realizar una conversión a partir de esta) no es el mismo para todos los tipos.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-162">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="aa5a8-163">Un convertidor para un tipo genérico abierto (`List<T>`, por ejemplo) tiene que crear un convertidor para un tipo genérico cerrado (`List<DateTime>`, por ejemplo) en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-163">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="aa5a8-164">Es necesario escribir código para controlar cada tipo genérico cerrado que el convertidor puede controlar.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-164">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="aa5a8-165">El tipo `Enum` es similar a un tipo genérico abierto: un convertidor para `Enum` tiene que crear un convertidor para un elemento `Enum` específico (`WeekdaysEnum`, por ejemplo) en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-165">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span>

## <a name="error-handling"></a><span data-ttu-id="aa5a8-166">Control de errores</span><span class="sxs-lookup"><span data-stu-id="aa5a8-166">Error handling</span></span>

<span data-ttu-id="aa5a8-167">El serializador proporciona un control especial para los tipos de excepción <xref:System.Text.Json.JsonException> y <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-167">The serializer provides special handling for exception types <xref:System.Text.Json.JsonException> and <xref:System.NotSupportedException>.</span></span>

### <a name="jsonexception"></a><span data-ttu-id="aa5a8-168">JsonException</span><span class="sxs-lookup"><span data-stu-id="aa5a8-168">JsonException</span></span>

<span data-ttu-id="aa5a8-169">Si produce una excepción `JsonException` sin ningún mensaje, el serializador crea un mensaje que incluye la ruta a la parte del JSON que causó el error.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-169">If you throw a `JsonException` without a message, the serializer creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="aa5a8-170">Por ejemplo, la instrucción `throw new JsonException()` genera un mensaje de error como el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-170">For example, the statement `throw new JsonException()` produces an error message like the following example:</span></span>

```output
Unhandled exception. System.Text.Json.JsonException:
The JSON value could not be converted to System.Object.
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="aa5a8-171">Si proporciona un mensaje (por ejemplo, `throw new JsonException("Error occurred")`), el serializador establece igualmente las propiedades <xref:System.Text.Json.JsonException.Path>, <xref:System.Text.Json.JsonException.LineNumber> y <xref:System.Text.Json.JsonException.BytePositionInLine>.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-171">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the serializer still sets the <xref:System.Text.Json.JsonException.Path>, <xref:System.Text.Json.JsonException.LineNumber>, and <xref:System.Text.Json.JsonException.BytePositionInLine> properties.</span></span>

### <a name="notsupportedexception"></a><span data-ttu-id="aa5a8-172">NotSupportedException</span><span class="sxs-lookup"><span data-stu-id="aa5a8-172">NotSupportedException</span></span>

<span data-ttu-id="aa5a8-173">Si produce una excepción `NotSupportedException`, siempre obtendrá la información de la ruta en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-173">If you throw a `NotSupportedException`, you always get the path information in the message.</span></span> <span data-ttu-id="aa5a8-174">Si proporciona un mensaje, la información de la ruta estará anexada.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-174">If you provide a message, the path information is appended to it.</span></span> <span data-ttu-id="aa5a8-175">Por ejemplo, la instrucción `throw new NotSupportedException("Error occurred.")` genera un mensaje de error como el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-175">For example, the statement `throw new NotSupportedException("Error occurred.")` produces an error message like the following example:</span></span>

```output
Error occurred. The unsupported member type is located on type
'System.Collections.Generic.Dictionary`2[Samples.SummaryWords,System.Int32]'.
Path: $.TemperatureRanges | LineNumber: 4 | BytePositionInLine: 24
```

### <a name="when-to-throw-which-exception-type"></a><span data-ttu-id="aa5a8-176">Cuándo se debe producir cada tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="aa5a8-176">When to throw which exception type</span></span>

<span data-ttu-id="aa5a8-177">Cuando la carga de JSON contiene tokens que no son válidos para el tipo que se está deserializando, produzca una excepción `JsonException`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-177">When the JSON payload contains tokens that are not valid for the type being deserialized, throw a `JsonException`.</span></span>

<span data-ttu-id="aa5a8-178">Si quiere impedir determinados tipos, produzca una excepción `NotSupportedException`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-178">When you want to disallow certain types, throw a `NotSupportedException`.</span></span> <span data-ttu-id="aa5a8-179">Esta excepción es lo que el serializador produce de forma automática para los tipos que no se admiten.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-179">This exception is what the serializer automatically throws for types that are not supported.</span></span> <span data-ttu-id="aa5a8-180">Por ejemplo, `System.Type` no se admite por motivos de seguridad, por lo que un intento de deserializarlo da como resultado una excepción `NotSupportedException`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-180">For example, `System.Type` is not supported for security reasons, so an attempt to deserialize it results in a `NotSupportedException`.</span></span>

<span data-ttu-id="aa5a8-181">Puede iniciar otras excepciones según sea necesario, pero no incluyen automáticamente la información de la ruta de JSON.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-181">You can throw other exceptions as needed, but they don't automatically include JSON path information.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="aa5a8-182">Registro de un convertidor personalizado</span><span class="sxs-lookup"><span data-stu-id="aa5a8-182">Register a custom converter</span></span>

<span data-ttu-id="aa5a8-183">*Registre* un convertidor personalizado para que los métodos `Serialize` y `Deserialize` lo utilicen.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-183">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="aa5a8-184">Elija uno de los enfoques siguientes:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-184">Choose one of the following approaches:</span></span>

* <span data-ttu-id="aa5a8-185">Agregue una instancia de la clase de convertidor a la colección <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-185">Add an instance of the converter class to the <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="aa5a8-186">Aplique el atributo [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) a las propiedades que requieren el convertidor personalizado.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-186">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="aa5a8-187">Aplique el atributo [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) a una clase o una estructura que represente un tipo de valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-187">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="aa5a8-188">Ejemplo de registro: colección de convertidores</span><span class="sxs-lookup"><span data-stu-id="aa5a8-188">Registration sample - Converters collection</span></span>

<span data-ttu-id="aa5a8-189">Este es un ejemplo que hace que <xref:System.ComponentModel.DateTimeOffsetConverter> sea el valor predeterminado para propiedades de tipo <xref:System.DateTimeOffset>:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-189">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RegisterConverterWithConvertersCollection.cs" id="Serialize":::

<span data-ttu-id="aa5a8-190">Suponga que serializa una instancia del tipo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-190">Suppose you serialize an instance of the following type:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

<span data-ttu-id="aa5a8-191">Este es un ejemplo de salida JSON que muestra que se ha usado el convertidor personalizado:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-191">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="aa5a8-192">En el código siguiente se usa el mismo enfoque para realizar una deserialización mediante el convertidor `DateTimeOffset` personalizado:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-192">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RegisterConverterWithConvertersCollection.cs" id="Deserialize":::

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="aa5a8-193">Ejemplo de registro: [JsonConverter] en una propiedad</span><span class="sxs-lookup"><span data-stu-id="aa5a8-193">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="aa5a8-194">El código siguiente selecciona un convertidor personalizado para la propiedad `Date`:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-194">The following code selects a custom converter for the `Date` property:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithConverterAttribute":::

<span data-ttu-id="aa5a8-195">El código para serializar `WeatherForecastWithConverterAttribute` no requiere el uso de `JsonSerializeOptions.Converters`:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-195">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RegisterConverterWithAttributeOnProperty.cs" id="Serialize":::

<span data-ttu-id="aa5a8-196">El código que se va a deserializar tampoco requiere el uso de `Converters`:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-196">The code to deserialize also doesn't require the use of `Converters`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RegisterConverterWithAttributeOnProperty.cs" id="Deserialize":::

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="aa5a8-197">Ejemplo de registro: [JsonConverter] en un tipo</span><span class="sxs-lookup"><span data-stu-id="aa5a8-197">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="aa5a8-198">Este es el código que crea una estructura y le aplica el atributo `[JsonConverter]`:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-198">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Temperature.cs":::

<span data-ttu-id="aa5a8-199">Este es el convertidor personalizado para la estructura anterior:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-199">Here's the custom converter for the preceding struct:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/TemperatureConverter.cs":::

<span data-ttu-id="aa5a8-200">El atributo `[JsonConvert]` de la estructura registra el convertidor personalizado como valor predeterminado para las propiedades de tipo `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-200">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="aa5a8-201">El convertidor se usa automáticamente en la propiedad `TemperatureCelsius` del tipo siguiente al serializarla o deserializarla:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-201">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithTemperatureStruct":::

## <a name="converter-registration-precedence"></a><span data-ttu-id="aa5a8-202">Prioridad de registro del convertidor</span><span class="sxs-lookup"><span data-stu-id="aa5a8-202">Converter registration precedence</span></span>

<span data-ttu-id="aa5a8-203">Durante la serialización o la deserialización, se elige un convertidor para cada elemento JSON en el orden siguiente, que se muestra de la prioridad más alta a la más baja:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-203">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="aa5a8-204">Elemento `[JsonConverter]` aplicado a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-204">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="aa5a8-205">Convertidor agregado a la colección `Converters`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-205">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="aa5a8-206">Elemento `[JsonConverter]` aplicado a un tipo de valor personalizado o POCO.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-206">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="aa5a8-207">Si se registran varios convertidores personalizados para un tipo en la colección `Converters`, se usa el primer convertidor que devuelve "true" para `CanConvert`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-207">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="aa5a8-208">Solo se elige un convertidor integrado si no se registra ningún convertidor personalizado aplicable.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-208">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="aa5a8-209">Ejemplos de convertidor para escenarios comunes</span><span class="sxs-lookup"><span data-stu-id="aa5a8-209">Converter samples for common scenarios</span></span>

<span data-ttu-id="aa5a8-210">En las secciones siguientes se proporcionan ejemplos de convertidor que abordan algunos escenarios comunes que la funcionalidad integrada no controla.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-210">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="aa5a8-211">[Deserialización de tipos inferidos en las propiedades de objeto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="aa5a8-211">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="aa5a8-212">[Compatibilidad con la deserialización polimórfica](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="aa5a8-212">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="aa5a8-213">[Compatibilidad con el recorrido de ida y vuelta para Stack\<T>](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="aa5a8-213">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="aa5a8-214">[Deserialización de tipos inferidos en las propiedades de objeto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="aa5a8-214">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="aa5a8-215">[Compatibilidad para diccionarios con una clave que no sea de cadena](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="aa5a8-215">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="aa5a8-216">[Compatibilidad con la deserialización polimórfica](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="aa5a8-216">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="aa5a8-217">[Compatibilidad con el recorrido de ida y vuelta para Stack\<T>](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="aa5a8-217">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>
::: zone-end

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="aa5a8-218">Deserialización de los tipos inferidos en propiedades de objeto</span><span class="sxs-lookup"><span data-stu-id="aa5a8-218">Deserialize inferred types to object properties</span></span>

<span data-ttu-id="aa5a8-219">Al realizar una deserialización en una propiedad de tipo `object`, se crea un objeto `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-219">When deserializing to a property of type `object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="aa5a8-220">La razón es que el deserializador no sabe qué tipo de CLR debe crear, y tampoco intenta averiguarlo.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-220">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="aa5a8-221">Por ejemplo, si una propiedad JSON tiene "true", el deserializador no infiere que el valor es de tipo `Boolean`, y si un elemento tiene "01/01/2019", el deserializador no infiere que es de tipo `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-221">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="aa5a8-222">La inferencia de tipos puede ser incorrecta.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-222">Type inference can be inaccurate.</span></span> <span data-ttu-id="aa5a8-223">Si el deserializador analiza un número JSON que no tiene un separador decimal como `long`, pueden producirse problemas de salida del intervalo si el valor se serializó originalmente como `ulong` o `BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-223">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="aa5a8-224">El análisis de un número que tiene un separador decimal como `double` puede perder precisión si el número se ha serializado originalmente como `decimal`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-224">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="aa5a8-225">En escenarios que requieren inferencia de tipos, el código siguiente muestra un convertidor personalizado para las propiedades `object`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-225">For scenarios that require type inference, the following code shows a custom converter for `object` properties.</span></span> <span data-ttu-id="aa5a8-226">El código convierte:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-226">The code converts:</span></span>

* <span data-ttu-id="aa5a8-227">`true` y `false`, en `Boolean`</span><span class="sxs-lookup"><span data-stu-id="aa5a8-227">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="aa5a8-228">Números sin decimales, en `long`</span><span class="sxs-lookup"><span data-stu-id="aa5a8-228">Numbers without a decimal to `long`</span></span>
* <span data-ttu-id="aa5a8-229">Números con un decimal, en `double`</span><span class="sxs-lookup"><span data-stu-id="aa5a8-229">Numbers with a decimal to `double`</span></span>
* <span data-ttu-id="aa5a8-230">Fechas, en `DateTime`</span><span class="sxs-lookup"><span data-stu-id="aa5a8-230">Dates to `DateTime`</span></span>
* <span data-ttu-id="aa5a8-231">Cadenas, en `string`</span><span class="sxs-lookup"><span data-stu-id="aa5a8-231">Strings to `string`</span></span>
* <span data-ttu-id="aa5a8-232">Todo lo demás, en `JsonElement`</span><span class="sxs-lookup"><span data-stu-id="aa5a8-232">Everything else to `JsonElement`</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/ObjectToInferredTypesConverter.cs":::

<span data-ttu-id="aa5a8-233">El código siguiente registra el convertidor:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-233">The following code registers the converter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeInferredTypesToObject.cs" id="Register":::

<span data-ttu-id="aa5a8-234">Este es un ejemplo de tipo con propiedades `object`:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-234">Here's an example type with `object` properties:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithObjectProperties":::

<span data-ttu-id="aa5a8-235">El siguiente ejemplo de JSON para deserializar contiene valores que se deserializarán como `DateTime`, `long` y `string`:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-235">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="aa5a8-236">Sin el convertidor personalizado, la deserialización coloca un elemento `JsonElement` en cada propiedad.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-236">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="aa5a8-237">La [carpeta de pruebas unitarias](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) en el espacio de nombres `System.Text.Json.Serialization` tiene más ejemplos de convertidores personalizados que controlan la deserialización en propiedades `object`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-237">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to `object` properties.</span></span>

::: zone pivot="dotnet-core-3-1"

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="aa5a8-238">Compatibilidad para diccionarios con una clave que no sea de cadena</span><span class="sxs-lookup"><span data-stu-id="aa5a8-238">Support Dictionary with non-string key</span></span>

<span data-ttu-id="aa5a8-239">La compatibilidad integrada con colecciones de diccionarios es para `Dictionary<string, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-239">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="aa5a8-240">Por lo tanto, la clave debe ser una cadena.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-240">That is, the key must be a string.</span></span> <span data-ttu-id="aa5a8-241">Para admitir un diccionario con un entero o algún otro tipo como clave, se requiere un convertidor personalizado.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-241">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="aa5a8-242">En el código siguiente se muestra un convertidor personalizado que funciona con `Dictionary<Enum,TValue>`:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-242">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DictionaryTKeyEnumTValueConverter.cs":::

<span data-ttu-id="aa5a8-243">El código siguiente registra el convertidor:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-243">The following code registers the converter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripDictionaryTkeyEnumTValue.cs" id="Register":::

<span data-ttu-id="aa5a8-244">El convertidor puede serializar y deserializar la propiedad `TemperatureRanges` de la siguiente clase que usa el elemento `Enum` siguiente:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-244">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithEnumDictionary":::

<span data-ttu-id="aa5a8-245">La salida JSON de la serialización es similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-245">The JSON output from serialization looks like the following example:</span></span>

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

<span data-ttu-id="aa5a8-246">La [carpeta de pruebas unitarias](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) en el espacio de nombres `System.Text.Json.Serialization` tiene más ejemplos de convertidores personalizados que controlan los diccionarios con una clave que no sea de cadena.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-246">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>
::: zone-end

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="aa5a8-247">Compatibilidad con la deserialización polimórfica</span><span class="sxs-lookup"><span data-stu-id="aa5a8-247">Support polymorphic deserialization</span></span>

<span data-ttu-id="aa5a8-248">Las características integradas proporcionan una gama limitada de [serialización polimórfica](system-text-json-polymorphism.md), pero no admiten ningún tipo de deserialización.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-248">Built-in features provide a limited range of [polymorphic serialization](system-text-json-polymorphism.md) but no support for deserialization at all.</span></span> <span data-ttu-id="aa5a8-249">La deserialización requiere un convertidor personalizado.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-249">Deserialization requires a custom converter.</span></span>

<span data-ttu-id="aa5a8-250">Suponga, por ejemplo, que tiene una clase base abstracta `Person`, con clases derivadas `Employee` y `Customer`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-250">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="aa5a8-251">La deserialización polimórfica significa que puede especificar `Person` como destino de la deserialización en tiempo de diseño, y los objetos `Customer` y `Employee` en el JSON se deserializan correctamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-251">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at run time.</span></span> <span data-ttu-id="aa5a8-252">Durante la deserialización, debe buscar pistas que identifiquen el tipo requerido en JSON.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-252">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="aa5a8-253">Los tipos de pistas disponibles varían según cada escenario.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-253">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="aa5a8-254">Por ejemplo, una propiedad de discriminador puede estar disponible o puede tener que confiar en la presencia o ausencia de una propiedad determinada.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-254">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="aa5a8-255">La versión actual de `System.Text.Json` no proporciona atributos para especificar cómo controlar los escenarios de deserialización polimórficos, por lo que se requieren convertidores personalizados.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-255">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="aa5a8-256">En el código siguiente se muestra una clase base, dos clases derivadas y un convertidor personalizado para ellas.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-256">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="aa5a8-257">El convertidor usa una propiedad de discriminador para realizar la deserialización polimórfica.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-257">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="aa5a8-258">El discriminador de tipo no se encuentra en las definiciones de clase, pero se crea durante la serialización y se lee durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-258">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Person.cs" id="Person":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/PersonConverterWithTypeDiscriminator.cs":::

<span data-ttu-id="aa5a8-259">El código siguiente registra el convertidor:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-259">The following code registers the converter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripPolymorphic.cs" id="Register":::

<span data-ttu-id="aa5a8-260">El convertidor puede deserializar el JSON que se creó con el mismo convertidor para serializar, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-260">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

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

<span data-ttu-id="aa5a8-261">El código del convertidor en el ejemplo anterior lee y escribe cada propiedad manualmente.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-261">The converter code in the preceding example reads and writes each property manually.</span></span> <span data-ttu-id="aa5a8-262">Una alternativa es llamar a `Deserialize` o `Serialize` para realizar parte del trabajo.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-262">An alternative is to call `Deserialize` or `Serialize` to do some of the work.</span></span> <span data-ttu-id="aa5a8-263">Para obtener un ejemplo, vea [esta publicación de StackOverflow](https://stackoverflow.com/a/59744873/12509023).</span><span class="sxs-lookup"><span data-stu-id="aa5a8-263">For an example, see [this StackOverflow post](https://stackoverflow.com/a/59744873/12509023).</span></span>

### <a name="support-round-trip-for-stackt"></a><span data-ttu-id="aa5a8-264">Compatibilidad con el recorrido de ida y vuelta para Stack\<T></span><span class="sxs-lookup"><span data-stu-id="aa5a8-264">Support round trip for Stack\<T></span></span>

<span data-ttu-id="aa5a8-265">Si deserializa una cadena JSON en un objeto <xref:System.Collections.Generic.Stack%601> y después serializa ese objeto, el contenido de la pila está en orden inverso.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-265">If you deserialize a JSON string into a <xref:System.Collections.Generic.Stack%601> object and then serialize that object, the contents of the stack are in reverse order.</span></span> <span data-ttu-id="aa5a8-266">Este comportamiento se aplica a los siguientes tipos e interfaz, así como a los tipos definidos por el usuario que derivan de ellos:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-266">This behavior applies to the following types and interface, and user-defined types that derive from them:</span></span>

* <xref:System.Collections.Stack>
* <xref:System.Collections.Generic.Stack%601>
* <xref:System.Collections.Concurrent.ConcurrentStack%601>
* <xref:System.Collections.Immutable.ImmutableStack%601>
* <xref:System.Collections.Immutable.IImmutableStack%601>

<span data-ttu-id="aa5a8-267">Para admitir la serialización y deserialización que conserva el orden original en la pila, se requiere un convertidor personalizado.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-267">To support serialization and deserialization that retains the original order in the stack, a custom converter is required.</span></span>

<span data-ttu-id="aa5a8-268">En el código siguiente se muestra un convertidor personalizado que permite el recorrido de ida y vuelta hacia y desde objetos `Stack<T>`:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-268">The following code shows a custom converter that enables round-tripping to and from `Stack<T>` objects:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/JsonConverterFactoryForStackOfT.cs":::

<span data-ttu-id="aa5a8-269">El código siguiente registra el convertidor:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-269">The following code registers the converter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripStackOfT.cs" id="Register":::

## <a name="handle-null-values"></a><span data-ttu-id="aa5a8-270">Control de valores NULL</span><span class="sxs-lookup"><span data-stu-id="aa5a8-270">Handle null values</span></span>

<span data-ttu-id="aa5a8-271">De forma predeterminada, el serializador controla los valores NULL de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-271">By default, the serializer handles null values as follows:</span></span>

* <span data-ttu-id="aa5a8-272">Para tipos de referencia y tipos de <xref:System.Nullable%601>:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-272">For reference types and <xref:System.Nullable%601> types:</span></span>

  * <span data-ttu-id="aa5a8-273">No pasa `null` a los convertidores personalizados en la serialización.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-273">It does not pass `null` to custom converters on serialization.</span></span>
  * <span data-ttu-id="aa5a8-274">No pasa `JsonTokenType.Null` a los convertidores personalizados en la deserialización.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-274">It does not pass `JsonTokenType.Null` to custom converters on deserialization.</span></span>
  * <span data-ttu-id="aa5a8-275">Devuelve una instancia de `null` en la deserialización.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-275">It returns a `null` instance on deserialization.</span></span>
  * <span data-ttu-id="aa5a8-276">Escribe `null` directamente con el escritor en la serialización.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-276">It writes `null` directly with the writer on serialization.</span></span>

* <span data-ttu-id="aa5a8-277">Para los tipos de valor distintos a NULL:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-277">For non-nullable value types:</span></span>

  * <span data-ttu-id="aa5a8-278">Pasa `JsonTokenType.Null` a los convertidores personalizados en la deserialización.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-278">It passes `JsonTokenType.Null` to custom converters on deserialization.</span></span> <span data-ttu-id="aa5a8-279">(Si no hay ningún convertidor personalizado disponible, el convertidor interno produce una excepción `JsonException` para el tipo).</span><span class="sxs-lookup"><span data-stu-id="aa5a8-279">(If no custom converter is available, a `JsonException` exception is thrown by the internal converter for the type.)</span></span>

<span data-ttu-id="aa5a8-280">Este comportamiento de administración de valores NULL sirve principalmente para optimizar el rendimiento omitiendo una llamada adicional al convertidor.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-280">This null-handling behavior is primarily to optimize performance by skipping an extra call to the converter.</span></span> <span data-ttu-id="aa5a8-281">Además, evita la aplicación de convertidores para tipos que aceptan valores NULL que comprobar para `null` al principio de cada invalidación de método `Read` y `Write`.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-281">In addition, it avoids forcing converters for nullable types to check for `null` at the start of every `Read` and `Write` method override.</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="aa5a8-282">Para permitir que un convertidor personalizado administre `null` para un tipo de valor o referencia, invalide <xref:System.Text.Json.Serialization.JsonConverter%601.HandleNull%2A?displayProperty=nameWithType> para devolver `true`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-282">To enable a custom converter to handle `null` for a reference or value type, override <xref:System.Text.Json.Serialization.JsonConverter%601.HandleNull%2A?displayProperty=nameWithType> to return `true`, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CustomConverterHandleNull.cs" highlight="19":::
::: zone-end

## <a name="other-custom-converter-samples"></a><span data-ttu-id="aa5a8-283">Otros ejemplos de convertidor personalizado</span><span class="sxs-lookup"><span data-stu-id="aa5a8-283">Other custom converter samples</span></span>

<span data-ttu-id="aa5a8-284">El artículo [Migración de Newtonsoft.Json a System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) contiene ejemplos adicionales de convertidores personalizados.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-284">The [Migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) article contains additional samples of custom converters.</span></span>

<span data-ttu-id="aa5a8-285">La [carpeta de pruebas unitarias](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) en el código fuente de `System.Text.Json.Serialization` incluye otros ejemplos de convertidor personalizado, como:</span><span class="sxs-lookup"><span data-stu-id="aa5a8-285">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="aa5a8-286">[Convertidor Int32 que convierte valores nulos en 0 al realizar la deserialización](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span><span class="sxs-lookup"><span data-stu-id="aa5a8-286">[Int32 converter that converts null to 0 on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span></span>
* <span data-ttu-id="aa5a8-287">[Convertidor Int32 que permite valores de cadena y número al realizar la deserialización](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span><span class="sxs-lookup"><span data-stu-id="aa5a8-287">[Int32 converter that allows both string and number values on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span></span>
* <span data-ttu-id="aa5a8-288">[Convertidor Enum](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span><span class="sxs-lookup"><span data-stu-id="aa5a8-288">[Enum converter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span></span>
* <span data-ttu-id="aa5a8-289">[Convertidor List\<T> que acepta datos externos](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span><span class="sxs-lookup"><span data-stu-id="aa5a8-289">[List\<T> converter that accepts external data](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span></span>
* <span data-ttu-id="aa5a8-290">[Convertidor Long[] que funciona con una lista de números delimitados por comas](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span><span class="sxs-lookup"><span data-stu-id="aa5a8-290">[Long[] converter that works with a comma-delimited list of numbers](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span></span>

<span data-ttu-id="aa5a8-291">Si necesita crear un convertidor que modifique el comportamiento de un convertidor integrado existente, puede obtener el [código fuente del convertidor existente](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) para que sirva como punto de partida para la personalización.</span><span class="sxs-lookup"><span data-stu-id="aa5a8-291">If you need to make a converter that modifies the behavior of an existing built-in converter, you can get [the source code of the existing converter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) to serve as a starting point for customization.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="aa5a8-292">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="aa5a8-292">Additional resources</span></span>

* <span data-ttu-id="aa5a8-293">[Código fuente para convertidores integrados](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span><span class="sxs-lookup"><span data-stu-id="aa5a8-293">[Source code for built-in converters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span></span>
* [<span data-ttu-id="aa5a8-294">Información general de System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="aa5a8-294">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="aa5a8-295">Cómo serializar y deserializar JSON</span><span class="sxs-lookup"><span data-stu-id="aa5a8-295">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="aa5a8-296">Creación de instancias de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="aa5a8-296">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="aa5a8-297">Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="aa5a8-297">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="aa5a8-298">Personalización de los nombres y valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="aa5a8-298">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="aa5a8-299">Omisión de propiedades</span><span class="sxs-lookup"><span data-stu-id="aa5a8-299">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="aa5a8-300">Permiso del formato JSON no válido</span><span class="sxs-lookup"><span data-stu-id="aa5a8-300">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="aa5a8-301">JSON de desbordamiento de control</span><span class="sxs-lookup"><span data-stu-id="aa5a8-301">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="aa5a8-302">Conservación de las referencias</span><span class="sxs-lookup"><span data-stu-id="aa5a8-302">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="aa5a8-303">Tipos inmutables y descriptores de acceso no públicos</span><span class="sxs-lookup"><span data-stu-id="aa5a8-303">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="aa5a8-304">Serialización polimórfica</span><span class="sxs-lookup"><span data-stu-id="aa5a8-304">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="aa5a8-305">Migración desde Newtonsoft.Json a System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="aa5a8-305">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="aa5a8-306">Personalización de la codificación de caracteres</span><span class="sxs-lookup"><span data-stu-id="aa5a8-306">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="aa5a8-307">Escritura de serializadores y deserializadores personalizados</span><span class="sxs-lookup"><span data-stu-id="aa5a8-307">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="aa5a8-308">Compatibilidad con DateTime y DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="aa5a8-308">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="aa5a8-309">[Referencia de API de System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="aa5a8-309">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="aa5a8-310">[Referencia de API de System.Text.Json.Serialization](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="aa5a8-310">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
