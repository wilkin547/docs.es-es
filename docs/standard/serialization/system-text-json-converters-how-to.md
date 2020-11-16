---
title: 'Procedimiento para escribir convertidores personalizados para la serialización de JSON: .NET'
description: Aprenda a crear convertidores personalizados para las clases de serialización de JSON que se proporcionan en el espacio de nombres System.Text.Json.
ms.date: 01/10/2020
no-loc:
- 'System.Text.Json'
- 'Newtonsoft.Json'
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
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a><span data-ttu-id="2b4a1-103">Procedimiento para escribir convertidores personalizados para la serialización de JSON (cálculo de referencias) en .NET</span><span class="sxs-lookup"><span data-stu-id="2b4a1-103">How to write custom converters for JSON serialization (marshalling) in .NET</span></span>

<span data-ttu-id="2b4a1-104">En este artículo se muestra cómo crear convertidores personalizados para las clases de serialización de JSON que se proporcionan en el espacio de nombres <xref:System.Text.Json>.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-104">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:System.Text.Json> namespace.</span></span> <span data-ttu-id="2b4a1-105">Para disponer de una introducción a `System.Text.Json`, vea [Cómo serializar y deserializar JSON en .NET](system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="2b4a1-105">For an introduction to `System.Text.Json`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="2b4a1-106">Un *convertidor* es una clase que convierte un objeto o un valor en JSON; también admite conversiones a partir de este formato.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-106">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="2b4a1-107">El espacio de nombres `System.Text.Json` tiene convertidores integrados para la mayoría de los tipos primitivos que se asignan a primitivos de JavaScript.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-107">The `System.Text.Json` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="2b4a1-108">Puede escribir convertidores personalizados:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-108">You can write custom converters:</span></span>

* <span data-ttu-id="2b4a1-109">Para reemplazar el comportamiento predeterminado de un convertidor integrado.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-109">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="2b4a1-110">Por ejemplo, puede que quiera que los valores `DateTime` se representen con el formato mm/dd/aaaa, en lugar del formato ISO 8601-1:2019 predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-110">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="2b4a1-111">Para admitir un tipo de valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-111">To support a custom value type.</span></span> <span data-ttu-id="2b4a1-112">Por ejemplo, una estructura `PhoneNumber`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-112">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="2b4a1-113">También puede escribir convertidores personalizados para personalizar o extender `System.Text.Json` con funcionalidad no incluida en la versión actual.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-113">You can also write custom converters to customize or extend `System.Text.Json` with functionality not included in the current release.</span></span> <span data-ttu-id="2b4a1-114">Los siguientes escenarios se describen más adelante en este artículo:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-114">The following scenarios are covered later in this article:</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="2b4a1-115">[Deserialización de tipos inferidos en las propiedades de objeto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="2b4a1-115">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="2b4a1-116">[Compatibilidad con la deserialización polimórfica](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="2b4a1-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="2b4a1-117">[Compatibilidad con el recorrido de ida y vuelta para Stack\<T>](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="2b4a1-117">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="2b4a1-118">[Deserialización de tipos inferidos en las propiedades de objeto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="2b4a1-118">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="2b4a1-119">[Compatibilidad para diccionarios con una clave que no sea de cadena](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="2b4a1-119">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="2b4a1-120">[Compatibilidad con la deserialización polimórfica](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="2b4a1-120">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="2b4a1-121">[Compatibilidad con el recorrido de ida y vuelta para Stack\<T>](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="2b4a1-121">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>
::: zone-end

## <a name="custom-converter-patterns"></a><span data-ttu-id="2b4a1-122">Patrones de convertidores personalizados</span><span class="sxs-lookup"><span data-stu-id="2b4a1-122">Custom converter patterns</span></span>

<span data-ttu-id="2b4a1-123">Hay dos patrones para crear un convertidor personalizado: el patrón básico y el patrón de fábrica.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-123">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="2b4a1-124">El patrón de fábrica es para los convertidores que controlan el tipo `Enum` o los valores genéricos abiertos.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-124">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="2b4a1-125">El patrón básico es para los tipos no genéricos y los tipos genéricos y cerrados.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-125">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="2b4a1-126">Por ejemplo, los convertidores de los siguientes tipos requieren el patrón de fábrica:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-126">For example, converters for the following types require the factory pattern:</span></span>

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

<span data-ttu-id="2b4a1-127">Entre los ejemplos de tipos que puede controlar el patrón básico se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-127">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

<span data-ttu-id="2b4a1-128">El patrón básico crea una clase que puede controlar un tipo.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-128">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="2b4a1-129">El patrón de fábrica crea una clase que determina, en tiempo de ejecución, qué tipo específico es necesario y crea dinámicamente el convertidor adecuado.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-129">The factory pattern creates a class that determines, at run time, which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="2b4a1-130">Convertidor básico de ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b4a1-130">Sample basic converter</span></span>

<span data-ttu-id="2b4a1-131">El ejemplo siguiente es un convertidor que reemplaza la serialización predeterminada para un tipo de datos existente.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-131">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="2b4a1-132">El convertidor usa el formato mm/dd/aaaa para las propiedades `DateTimeOffset`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-132">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="2b4a1-133">Convertidor de patrones de fábrica de ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b4a1-133">Sample factory pattern converter</span></span>

<span data-ttu-id="2b4a1-134">En el código siguiente se muestra un convertidor personalizado que funciona con `Dictionary<Enum,TValue>`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-134">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="2b4a1-135">El código sigue el patrón de fábrica porque el primer parámetro de tipo genérico es `Enum` y el segundo es abierto.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-135">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="2b4a1-136">El método `CanConvert` devuelve `true` solo para un elemento `Dictionary` con dos parámetros genéricos, el primero de los cuales es un tipo `Enum`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-136">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="2b4a1-137">El convertidor interno obtiene un convertidor existente para controlar el tipo que se proporciona en tiempo de ejecución para `TValue`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-137">The inner converter gets an existing converter to handle whichever type is provided at run time for `TValue`.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="2b4a1-138">El código anterior es el mismo que el que se muestra en [Compatibilidad para diccionarios con una clave que no sea de cadena](#support-dictionary-with-non-string-key), más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-138">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="2b4a1-139">Pasos para seguir el patrón básico</span><span class="sxs-lookup"><span data-stu-id="2b4a1-139">Steps to follow the basic pattern</span></span>

<span data-ttu-id="2b4a1-140">En los pasos siguientes se explica cómo crear un convertidor siguiendo el patrón básico:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-140">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="2b4a1-141">Cree una clase que derive de <xref:System.Text.Json.Serialization.JsonConverter%601>, donde `T` es el tipo que se va a serializar y deserializar.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-141">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="2b4a1-142">Reemplace el método `Read` para deserializar el JSON de entrada y convertirlo al tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-142">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="2b4a1-143">Use el elemento <xref:System.Text.Json.Utf8JsonReader> que se pasa al método para leer el JSON.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-143">Use the <xref:System.Text.Json.Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="2b4a1-144">Invalide el método `Write` para serializar el objeto de entrada de tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-144">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="2b4a1-145">Use el elemento <xref:System.Text.Json.Utf8JsonWriter> que se pasa al método para escribir el JSON.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-145">Use the <xref:System.Text.Json.Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="2b4a1-146">Reemplace el método `CanConvert` solo si es necesario.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-146">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="2b4a1-147">La implementación predeterminada devuelve `true` cuando el tipo que se va a convertir es de tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-147">The default implementation returns `true` when the type to convert is of type `T`.</span></span> <span data-ttu-id="2b4a1-148">Por lo tanto, los convertidores que solo admiten el tipo `T` no necesitan reemplazar este método.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-148">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="2b4a1-149">Para obtener un ejemplo de un convertidor que necesita reemplazar este método, consulte la sección sobre la [deserialización polimórfica](#support-polymorphic-deserialization), más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-149">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="2b4a1-150">Puede hacer referencia al [código fuente de convertidores integrados](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) como implementaciones de referencia para escribir convertidores personalizados.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-150">You can refer to the [built-in converters source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="2b4a1-151">Pasos para seguir el patrón de fábrica</span><span class="sxs-lookup"><span data-stu-id="2b4a1-151">Steps to follow the factory pattern</span></span>

<span data-ttu-id="2b4a1-152">En los pasos siguientes se explica cómo crear un convertidor siguiendo el patrón de fábrica:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-152">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="2b4a1-153">Cree una clase que derive de <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-153">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="2b4a1-154">Reemplace el método `CanConvert` para devolver "true" cuando el tipo que se va a convertir sea uno que el convertidor puede controlar.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-154">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="2b4a1-155">Por ejemplo, si el convertidor es para `List<T>`, solo puede controlar `List<int>`, `List<string>` y `List<DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-155">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span>
* <span data-ttu-id="2b4a1-156">Invalide el método `CreateConverter` para devolver una instancia de una clase de convertidor que controlará el tipo de conversión que se proporciona en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-156">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at run time.</span></span>
* <span data-ttu-id="2b4a1-157">Cree la clase de convertidor de la que el método `CreateConverter` crea instancias.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-157">Create the converter class that the `CreateConverter` method instantiates.</span></span>

<span data-ttu-id="2b4a1-158">El patrón de fábrica es necesario para los genéricos abiertos porque el código para convertir un objeto en una cadena (y también para realizar una conversión a partir de esta) no es el mismo para todos los tipos.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-158">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="2b4a1-159">Un convertidor para un tipo genérico abierto (`List<T>`, por ejemplo) tiene que crear un convertidor para un tipo genérico cerrado (`List<DateTime>`, por ejemplo) en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-159">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="2b4a1-160">Es necesario escribir código para controlar cada tipo genérico cerrado que el convertidor puede controlar.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-160">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="2b4a1-161">El tipo `Enum` es similar a un tipo genérico abierto: un convertidor para `Enum` tiene que crear un convertidor para un elemento `Enum` específico (`WeekdaysEnum`, por ejemplo) en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-161">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span>

## <a name="error-handling"></a><span data-ttu-id="2b4a1-162">Control de errores</span><span class="sxs-lookup"><span data-stu-id="2b4a1-162">Error handling</span></span>

<span data-ttu-id="2b4a1-163">Si necesita producir una excepción en el código de control de errores, considere la posibilidad de iniciar una excepción <xref:System.Text.Json.JsonException> sin un mensaje.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-163">If you need to throw an exception in error-handling code, consider throwing a <xref:System.Text.Json.JsonException> without a message.</span></span> <span data-ttu-id="2b4a1-164">Este tipo de excepción crea automáticamente un mensaje que incluye la ruta de acceso a la parte del JSON que causó el error.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-164">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="2b4a1-165">Por ejemplo, la instrucción `throw new JsonException();` genera un mensaje de error como el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-165">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```output
Unhandled exception. System.Text.Json.JsonException:
The JSON value could not be converted to System.Object.
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="2b4a1-166">Si proporciona un mensaje (por ejemplo, `throw new JsonException("Error occurred")`), la excepción sigue proporcionando la ruta de acceso en la propiedad <xref:System.Text.Json.JsonException.Path>.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-166">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the exception still provides the path in the <xref:System.Text.Json.JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="2b4a1-167">Registro de un convertidor personalizado</span><span class="sxs-lookup"><span data-stu-id="2b4a1-167">Register a custom converter</span></span>

<span data-ttu-id="2b4a1-168">*Registre* un convertidor personalizado para que los métodos `Serialize` y `Deserialize` lo utilicen.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-168">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="2b4a1-169">Elija uno de los enfoques siguientes:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-169">Choose one of the following approaches:</span></span>

* <span data-ttu-id="2b4a1-170">Agregue una instancia de la clase de convertidor a la colección <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-170">Add an instance of the converter class to the <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="2b4a1-171">Aplique el atributo [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) a las propiedades que requieren el convertidor personalizado.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-171">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="2b4a1-172">Aplique el atributo [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) a una clase o una estructura que represente un tipo de valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-172">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="2b4a1-173">Ejemplo de registro: colección de convertidores</span><span class="sxs-lookup"><span data-stu-id="2b4a1-173">Registration sample - Converters collection</span></span>

<span data-ttu-id="2b4a1-174">Este es un ejemplo que hace que <xref:System.ComponentModel.DateTimeOffsetConverter> sea el valor predeterminado para propiedades de tipo <xref:System.DateTimeOffset>:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-174">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

<span data-ttu-id="2b4a1-175">Suponga que serializa una instancia del tipo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-175">Suppose you serialize an instance of the following type:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="2b4a1-176">Este es un ejemplo de salida JSON que muestra que se ha usado el convertidor personalizado:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-176">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="2b4a1-177">En el código siguiente se usa el mismo enfoque para realizar una deserialización mediante el convertidor `DateTimeOffset` personalizado:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-177">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="2b4a1-178">Ejemplo de registro: [JsonConverter] en una propiedad</span><span class="sxs-lookup"><span data-stu-id="2b4a1-178">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="2b4a1-179">El código siguiente selecciona un convertidor personalizado para la propiedad `Date`:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-179">The following code selects a custom converter for the `Date` property:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

<span data-ttu-id="2b4a1-180">El código para serializar `WeatherForecastWithConverterAttribute` no requiere el uso de `JsonSerializeOptions.Converters`:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-180">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

<span data-ttu-id="2b4a1-181">El código que se va a deserializar tampoco requiere el uso de `Converters`:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-181">The code to deserialize also doesn't require the use of `Converters`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="2b4a1-182">Ejemplo de registro: [JsonConverter] en un tipo</span><span class="sxs-lookup"><span data-stu-id="2b4a1-182">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="2b4a1-183">Este es el código que crea una estructura y le aplica el atributo `[JsonConverter]`:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-183">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Temperature.cs)]

<span data-ttu-id="2b4a1-184">Este es el convertidor personalizado para la estructura anterior:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-184">Here's the custom converter for the preceding struct:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/TemperatureConverter.cs)]

<span data-ttu-id="2b4a1-185">El atributo `[JsonConvert]` de la estructura registra el convertidor personalizado como valor predeterminado para las propiedades de tipo `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-185">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="2b4a1-186">El convertidor se usa automáticamente en la propiedad `TemperatureCelsius` del tipo siguiente al serializarla o deserializarla:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-186">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a><span data-ttu-id="2b4a1-187">Prioridad de registro del convertidor</span><span class="sxs-lookup"><span data-stu-id="2b4a1-187">Converter registration precedence</span></span>

<span data-ttu-id="2b4a1-188">Durante la serialización o la deserialización, se elige un convertidor para cada elemento JSON en el orden siguiente, que se muestra de la prioridad más alta a la más baja:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-188">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="2b4a1-189">Elemento `[JsonConverter]` aplicado a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-189">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="2b4a1-190">Convertidor agregado a la colección `Converters`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-190">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="2b4a1-191">Elemento `[JsonConverter]` aplicado a un tipo de valor personalizado o POCO.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-191">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="2b4a1-192">Si se registran varios convertidores personalizados para un tipo en la colección `Converters`, se usa el primer convertidor que devuelve "true" para `CanConvert`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-192">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="2b4a1-193">Solo se elige un convertidor integrado si no se registra ningún convertidor personalizado aplicable.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-193">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="2b4a1-194">Ejemplos de convertidor para escenarios comunes</span><span class="sxs-lookup"><span data-stu-id="2b4a1-194">Converter samples for common scenarios</span></span>

<span data-ttu-id="2b4a1-195">En las secciones siguientes se proporcionan ejemplos de convertidor que abordan algunos escenarios comunes que la funcionalidad integrada no controla.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-195">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="2b4a1-196">[Deserialización de tipos inferidos en las propiedades de objeto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="2b4a1-196">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="2b4a1-197">[Compatibilidad con la deserialización polimórfica](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="2b4a1-197">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="2b4a1-198">[Compatibilidad con el recorrido de ida y vuelta para Stack\<T>](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="2b4a1-198">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="2b4a1-199">[Deserialización de tipos inferidos en las propiedades de objeto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="2b4a1-199">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="2b4a1-200">[Compatibilidad para diccionarios con una clave que no sea de cadena](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="2b4a1-200">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="2b4a1-201">[Compatibilidad con la deserialización polimórfica](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="2b4a1-201">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="2b4a1-202">[Compatibilidad con el recorrido de ida y vuelta para Stack\<T>](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="2b4a1-202">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>
::: zone-end

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="2b4a1-203">Deserialización de los tipos inferidos en propiedades de objeto</span><span class="sxs-lookup"><span data-stu-id="2b4a1-203">Deserialize inferred types to object properties</span></span>

<span data-ttu-id="2b4a1-204">Al realizar una deserialización en una propiedad de tipo `object`, se crea un objeto `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-204">When deserializing to a property of type `object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="2b4a1-205">La razón es que el deserializador no sabe qué tipo de CLR debe crear, y tampoco intenta averiguarlo.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-205">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="2b4a1-206">Por ejemplo, si una propiedad JSON tiene "true", el deserializador no infiere que el valor es de tipo `Boolean`, y si un elemento tiene "01/01/2019", el deserializador no infiere que es de tipo `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-206">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="2b4a1-207">La inferencia de tipos puede ser incorrecta.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-207">Type inference can be inaccurate.</span></span> <span data-ttu-id="2b4a1-208">Si el deserializador analiza un número JSON que no tiene un separador decimal como `long`, pueden producirse problemas de salida del intervalo si el valor se serializó originalmente como `ulong` o `BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-208">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="2b4a1-209">El análisis de un número que tiene un separador decimal como `double` puede perder precisión si el número se ha serializado originalmente como `decimal`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-209">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="2b4a1-210">En escenarios que requieren inferencia de tipos, el código siguiente muestra un convertidor personalizado para las propiedades `object`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-210">For scenarios that require type inference, the following code shows a custom converter for `object` properties.</span></span> <span data-ttu-id="2b4a1-211">El código convierte:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-211">The code converts:</span></span>

* <span data-ttu-id="2b4a1-212">`true` y `false`, en `Boolean`</span><span class="sxs-lookup"><span data-stu-id="2b4a1-212">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="2b4a1-213">Números sin decimales, en `long`</span><span class="sxs-lookup"><span data-stu-id="2b4a1-213">Numbers without a decimal to `long`</span></span>
* <span data-ttu-id="2b4a1-214">Números con un decimal, en `double`</span><span class="sxs-lookup"><span data-stu-id="2b4a1-214">Numbers with a decimal to `double`</span></span>
* <span data-ttu-id="2b4a1-215">Fechas, en `DateTime`</span><span class="sxs-lookup"><span data-stu-id="2b4a1-215">Dates to `DateTime`</span></span>
* <span data-ttu-id="2b4a1-216">Cadenas, en `string`</span><span class="sxs-lookup"><span data-stu-id="2b4a1-216">Strings to `string`</span></span>
* <span data-ttu-id="2b4a1-217">Todo lo demás, en `JsonElement`</span><span class="sxs-lookup"><span data-stu-id="2b4a1-217">Everything else to `JsonElement`</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/ObjectToInferredTypesConverter.cs)]

<span data-ttu-id="2b4a1-218">El código siguiente registra el convertidor:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-218">The following code registers the converter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeInferredTypesToObject.cs?name=SnippetRegister)]

<span data-ttu-id="2b4a1-219">Este es un ejemplo de tipo con propiedades `object`:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-219">Here's an example type with `object` properties:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

<span data-ttu-id="2b4a1-220">El siguiente ejemplo de JSON para deserializar contiene valores que se deserializarán como `DateTime`, `long` y `string`:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-220">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="2b4a1-221">Sin el convertidor personalizado, la deserialización coloca un elemento `JsonElement` en cada propiedad.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-221">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="2b4a1-222">La [carpeta de pruebas unitarias](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) en el espacio de nombres `System.Text.Json.Serialization` tiene más ejemplos de convertidores personalizados que controlan la deserialización en propiedades `object`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-222">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to `object` properties.</span></span>

::: zone pivot="dotnet-core-3-1"

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="2b4a1-223">Compatibilidad para diccionarios con una clave que no sea de cadena</span><span class="sxs-lookup"><span data-stu-id="2b4a1-223">Support Dictionary with non-string key</span></span>

<span data-ttu-id="2b4a1-224">La compatibilidad integrada con colecciones de diccionarios es para `Dictionary<string, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-224">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="2b4a1-225">Por lo tanto, la clave debe ser una cadena.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-225">That is, the key must be a string.</span></span> <span data-ttu-id="2b4a1-226">Para admitir un diccionario con un entero o algún otro tipo como clave, se requiere un convertidor personalizado.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-226">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="2b4a1-227">En el código siguiente se muestra un convertidor personalizado que funciona con `Dictionary<Enum,TValue>`:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-227">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DictionaryTKeyEnumTValueConverter.cs)]

<span data-ttu-id="2b4a1-228">El código siguiente registra el convertidor:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-228">The following code registers the converter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

<span data-ttu-id="2b4a1-229">El convertidor puede serializar y deserializar la propiedad `TemperatureRanges` de la siguiente clase que usa el elemento `Enum` siguiente:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-229">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

<span data-ttu-id="2b4a1-230">La salida JSON de la serialización es similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-230">The JSON output from serialization looks like the following example:</span></span>

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

<span data-ttu-id="2b4a1-231">La [carpeta de pruebas unitarias](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) en el espacio de nombres `System.Text.Json.Serialization` tiene más ejemplos de convertidores personalizados que controlan los diccionarios con una clave que no sea de cadena.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-231">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>
::: zone-end

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="2b4a1-232">Compatibilidad con la deserialización polimórfica</span><span class="sxs-lookup"><span data-stu-id="2b4a1-232">Support polymorphic deserialization</span></span>

<span data-ttu-id="2b4a1-233">Las características integradas proporcionan una gama limitada de [serialización polimórfica](system-text-json-how-to.md#serialize-properties-of-derived-classes), pero no admiten ningún tipo de deserialización.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-233">Built-in features provide a limited range of [polymorphic serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) but no support for deserialization at all.</span></span> <span data-ttu-id="2b4a1-234">La deserialización requiere un convertidor personalizado.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-234">Deserialization requires a custom converter.</span></span>

<span data-ttu-id="2b4a1-235">Suponga, por ejemplo, que tiene una clase base abstracta `Person`, con clases derivadas `Employee` y `Customer`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-235">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="2b4a1-236">La deserialización polimórfica significa que puede especificar `Person` como destino de la deserialización en tiempo de diseño, y los objetos `Customer` y `Employee` en el JSON se deserializan correctamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-236">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at run time.</span></span> <span data-ttu-id="2b4a1-237">Durante la deserialización, debe buscar pistas que identifiquen el tipo requerido en JSON.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-237">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="2b4a1-238">Los tipos de pistas disponibles varían según cada escenario.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-238">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="2b4a1-239">Por ejemplo, una propiedad de discriminador puede estar disponible o puede tener que confiar en la presencia o ausencia de una propiedad determinada.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-239">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="2b4a1-240">La versión actual de `System.Text.Json` no proporciona atributos para especificar cómo controlar los escenarios de deserialización polimórficos, por lo que se requieren convertidores personalizados.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-240">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="2b4a1-241">En el código siguiente se muestra una clase base, dos clases derivadas y un convertidor personalizado para ellas.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-241">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="2b4a1-242">El convertidor usa una propiedad de discriminador para realizar la deserialización polimórfica.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-242">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="2b4a1-243">El discriminador de tipo no se encuentra en las definiciones de clase, pero se crea durante la serialización y se lee durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-243">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/PersonConverterWithTypeDiscriminator.cs)]

<span data-ttu-id="2b4a1-244">El código siguiente registra el convertidor:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-244">The following code registers the converter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPolymorphic.cs?name=SnippetRegister)]

<span data-ttu-id="2b4a1-245">El convertidor puede deserializar el JSON que se creó con el mismo convertidor para serializar, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-245">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

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

<span data-ttu-id="2b4a1-246">El código del convertidor en el ejemplo anterior lee y escribe cada propiedad manualmente.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-246">The converter code in the preceding example reads and writes each property manually.</span></span> <span data-ttu-id="2b4a1-247">Una alternativa es llamar a `Deserialize` o `Serialize` para realizar parte del trabajo.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-247">An alternative is to call `Deserialize` or `Serialize` to do some of the work.</span></span> <span data-ttu-id="2b4a1-248">Para obtener un ejemplo, vea [esta publicación de StackOverflow](https://stackoverflow.com/a/59744873/12509023).</span><span class="sxs-lookup"><span data-stu-id="2b4a1-248">For an example, see [this StackOverflow post](https://stackoverflow.com/a/59744873/12509023).</span></span>

### <a name="support-round-trip-for-stackt"></a><span data-ttu-id="2b4a1-249">Compatibilidad con el recorrido de ida y vuelta para Stack\<T></span><span class="sxs-lookup"><span data-stu-id="2b4a1-249">Support round trip for Stack\<T></span></span>

<span data-ttu-id="2b4a1-250">Si deserializa una cadena JSON en un objeto <xref:System.Collections.Generic.Stack%601> y después serializa ese objeto, el contenido de la pila está en orden inverso.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-250">If you deserialize a JSON string into a <xref:System.Collections.Generic.Stack%601> object and then serialize that object, the contents of the stack are in reverse order.</span></span> <span data-ttu-id="2b4a1-251">Este comportamiento se aplica a los siguientes tipos e interfaz, así como a los tipos definidos por el usuario que derivan de ellos:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-251">This behavior applies to the following types and interface, and user-defined types that derive from them:</span></span>

* <xref:System.Collections.Stack>
* <xref:System.Collections.Generic.Stack%601>
* <xref:System.Collections.Concurrent.ConcurrentStack%601>
* <xref:System.Collections.Immutable.ImmutableStack%601>
* <xref:System.Collections.Immutable.IImmutableStack%601>

<span data-ttu-id="2b4a1-252">Para admitir la serialización y deserialización que conserva el orden original en la pila, se requiere un convertidor personalizado.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-252">To support serialization and deserialization that retains the original order in the stack, a custom converter is required.</span></span>

<span data-ttu-id="2b4a1-253">En el código siguiente se muestra un convertidor personalizado que permite el recorrido de ida y vuelta hacia y desde objetos `Stack<T>`:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-253">The following code shows a custom converter that enables round-tripping to and from `Stack<T>` objects:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonConverterFactoryForStackOfT.cs)]

<span data-ttu-id="2b4a1-254">El código siguiente registra el convertidor:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-254">The following code registers the converter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripStackOfT.cs?name=SnippetRegister)]

## <a name="handle-null-values"></a><span data-ttu-id="2b4a1-255">Control de valores NULL</span><span class="sxs-lookup"><span data-stu-id="2b4a1-255">Handle null values</span></span>

<span data-ttu-id="2b4a1-256">De forma predeterminada, el serializador controla los valores NULL de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-256">By default, the serializer handles null values as follows:</span></span>

* <span data-ttu-id="2b4a1-257">Para tipos de referencia y tipos de `Nullable<T>`:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-257">For reference types and `Nullable<T>` types:</span></span>

  * <span data-ttu-id="2b4a1-258">No pasa `null` a los convertidores personalizados en la serialización.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-258">It does not pass `null` to custom converters on serialization.</span></span>
  * <span data-ttu-id="2b4a1-259">No pasa `JsonTokenType.Null` a los convertidores personalizados en la deserialización.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-259">It does not pass `JsonTokenType.Null` to custom converters on deserialization.</span></span>
  * <span data-ttu-id="2b4a1-260">Devuelve una instancia de `null` en la deserialización.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-260">It returns a `null` instance on deserialization.</span></span>
  * <span data-ttu-id="2b4a1-261">Escribe `null` directamente con el escritor en la serialización.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-261">It writes `null` directly with the writer on serialization.</span></span>

* <span data-ttu-id="2b4a1-262">Para los tipos de valor distintos a NULL:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-262">For non-nullable value types:</span></span>

  * <span data-ttu-id="2b4a1-263">Pasa `JsonTokenType.Null` a los convertidores personalizados en la deserialización.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-263">It passes `JsonTokenType.Null` to custom converters on deserialization.</span></span> <span data-ttu-id="2b4a1-264">(Si no hay ningún convertidor personalizado disponible, el convertidor interno produce una excepción `JsonException` para el tipo).</span><span class="sxs-lookup"><span data-stu-id="2b4a1-264">(If no custom converter is available, a `JsonException` exception is thrown by the internal converter for the type.)</span></span>

<span data-ttu-id="2b4a1-265">Este comportamiento de administración de valores NULL sirve principalmente para optimizar el rendimiento omitiendo una llamada adicional al convertidor.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-265">This null-handling behavior is primarily to optimize performance by skipping an extra call to the converter.</span></span> <span data-ttu-id="2b4a1-266">Además, evita la aplicación de convertidores para tipos que aceptan valores NULL que comprobar para `null` al principio de cada invalidación de método `Read` y `Write`.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-266">In addition, it avoids forcing converters for nullable types to check for `null` at the start of every `Read` and `Write` method override.</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="2b4a1-267">Para permitir que un convertidor personalizado administre `null` para un tipo de valor o referencia, invalide <xref:System.Text.Json.Serialization.JsonConverter%601.HandleNull%2A?displayProperty=nameWithType> para devolver `true`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-267">To enable a custom converter to handle `null` for a reference or value type, override <xref:System.Text.Json.Serialization.JsonConverter%601.HandleNull%2A?displayProperty=nameWithType> to return `true`, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CustomConverterHandleNull.cs" highlight="19":::
::: zone-end

## <a name="other-custom-converter-samples"></a><span data-ttu-id="2b4a1-268">Otros ejemplos de convertidor personalizado</span><span class="sxs-lookup"><span data-stu-id="2b4a1-268">Other custom converter samples</span></span>

<span data-ttu-id="2b4a1-269">El artículo [Migración de Newtonsoft.Json a System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) contiene ejemplos adicionales de convertidores personalizados.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-269">The [Migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) article contains additional samples of custom converters.</span></span>

<span data-ttu-id="2b4a1-270">La [carpeta de pruebas unitarias](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) en el código fuente de `System.Text.Json.Serialization` incluye otros ejemplos de convertidor personalizado, como:</span><span class="sxs-lookup"><span data-stu-id="2b4a1-270">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="2b4a1-271">[Convertidor Int32 que convierte valores nulos en 0 al realizar la deserialización](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span><span class="sxs-lookup"><span data-stu-id="2b4a1-271">[Int32 converter that converts null to 0 on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span></span>
* <span data-ttu-id="2b4a1-272">[Convertidor Int32 que permite valores de cadena y número al realizar la deserialización](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span><span class="sxs-lookup"><span data-stu-id="2b4a1-272">[Int32 converter that allows both string and number values on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span></span>
* <span data-ttu-id="2b4a1-273">[Convertidor Enum](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span><span class="sxs-lookup"><span data-stu-id="2b4a1-273">[Enum converter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span></span>
* <span data-ttu-id="2b4a1-274">[Convertidor List\<T> que acepta datos externos](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span><span class="sxs-lookup"><span data-stu-id="2b4a1-274">[List\<T> converter that accepts external data](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span></span>
* <span data-ttu-id="2b4a1-275">[Convertidor Long[] que funciona con una lista de números delimitados por comas](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span><span class="sxs-lookup"><span data-stu-id="2b4a1-275">[Long[] converter that works with a comma-delimited list of numbers](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span></span>

<span data-ttu-id="2b4a1-276">Si necesita crear un convertidor que modifique el comportamiento de un convertidor integrado existente, puede obtener el [código fuente del convertidor existente](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) para que sirva como punto de partida para la personalización.</span><span class="sxs-lookup"><span data-stu-id="2b4a1-276">If you need to make a converter that modifies the behavior of an existing built-in converter, you can get [the source code of the existing converter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) to serve as a starting point for customization.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2b4a1-277">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2b4a1-277">Additional resources</span></span>

* <span data-ttu-id="2b4a1-278">[Código fuente para convertidores integrados](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span><span class="sxs-lookup"><span data-stu-id="2b4a1-278">[Source code for built-in converters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span></span>
* [<span data-ttu-id="2b4a1-279">Compatibilidad con DateTime y DateTimeOffset en System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="2b4a1-279">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* [<span data-ttu-id="2b4a1-280">Información general sobre System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="2b4a1-280">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="2b4a1-281">Procedimiento para usar System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="2b4a1-281">How to use System.Text.Json</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="2b4a1-282">Procedimiento para migrar de Newtonsoft.Json</span><span class="sxs-lookup"><span data-stu-id="2b4a1-282">How to migrate from Newtonsoft.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* <span data-ttu-id="2b4a1-283">[Referencia de API de System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="2b4a1-283">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="2b4a1-284">[Referencia de API de System.Text.Json.Serialization](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="2b4a1-284">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
