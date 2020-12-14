---
title: Personalización de la codificación de caracteres con System.Text.Json
description: Aprenda a personalizar la codificación de caracteres durante la serialización y deserialización de JSON en .NET.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: cfb83af0c58e0c9dfb73ecb8e2177d255e403fae
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009630"
---
# <a name="how-to-customize-character-encoding-with-no-locsystemtextjson"></a><span data-ttu-id="d29fc-103">Personalización de la codificación de caracteres con System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="d29fc-103">How to customize character encoding with System.Text.Json</span></span>

<span data-ttu-id="d29fc-104">De forma predeterminada, el serializador escapa a todos los caracteres que no sean ASCII.</span><span class="sxs-lookup"><span data-stu-id="d29fc-104">By default, the serializer escapes all non-ASCII characters.</span></span> <span data-ttu-id="d29fc-105">Es decir, los reemplaza por `\uxxxx` donde `xxxx` es el código Unicode del carácter.</span><span class="sxs-lookup"><span data-stu-id="d29fc-105">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span> <span data-ttu-id="d29fc-106">Por ejemplo, si la propiedad `Summary` del siguiente código JSON está establecida en cirílico `жарко`, el objeto `WeatherForecast` se serializa tal y como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d29fc-106">For example, if the `Summary` property in the following JSON is set to Cyrillic `жарко`, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

## <a name="serialize-language-character-sets"></a><span data-ttu-id="d29fc-107">Serialización de juegos de caracteres de idioma</span><span class="sxs-lookup"><span data-stu-id="d29fc-107">Serialize language character sets</span></span>

<span data-ttu-id="d29fc-108">Para serializar los juegos de caracteres de uno o más idiomas sin escape, especifique [intervalos Unicode](xref:System.Text.Unicode.UnicodeRanges) al crear una instancia de <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d29fc-108">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="LanguageSets":::

<span data-ttu-id="d29fc-109">Este código no escapa a los caracteres cirílicos o griegos.</span><span class="sxs-lookup"><span data-stu-id="d29fc-109">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="d29fc-110">Si la propiedad `Summary` está establecida en cirílico `жарко`, el objeto `WeatherForecast` se serializa tal y como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d29fc-110">If the `Summary` property is set to Cyrillic `жарко`, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="d29fc-111">Para serializar todos los conjuntos de lenguaje sin escape, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d29fc-111">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

## <a name="serialize-specific-characters"></a><span data-ttu-id="d29fc-112">Serialización de caracteres específicos</span><span class="sxs-lookup"><span data-stu-id="d29fc-112">Serialize specific characters</span></span>

<span data-ttu-id="d29fc-113">Una alternativa consiste en especificar caracteres individuales que se quieren dejar pasar sin secuencia de escape.</span><span class="sxs-lookup"><span data-stu-id="d29fc-113">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="d29fc-114">En el ejemplo siguiente se serializan solo los dos primeros caracteres de `жарко`:</span><span class="sxs-lookup"><span data-stu-id="d29fc-114">The following example serializes only the first two characters of `жарко`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="SelectedCharacters":::

<span data-ttu-id="d29fc-115">Aquí se muestra un ejemplo de JSON producido por el código anterior:</span><span class="sxs-lookup"><span data-stu-id="d29fc-115">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

## <a name="serialize-all-characters"></a><span data-ttu-id="d29fc-116">Serialización de todos los caracteres</span><span class="sxs-lookup"><span data-stu-id="d29fc-116">Serialize all characters</span></span>

<span data-ttu-id="d29fc-117">Para minimizar el escape, puede usar <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType> tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d29fc-117">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="UnsafeRelaxed":::

> [!CAUTION]
> <span data-ttu-id="d29fc-118">En comparación con el codificador predeterminado, el codificador `UnsafeRelaxedJsonEscaping` es más permisivo sobre dejar que los caracteres pasen sin secuencia de escape:</span><span class="sxs-lookup"><span data-stu-id="d29fc-118">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="d29fc-119">No escapa a caracteres que distinguen HTML, tales como `<`, `>`, `&` y `'`.</span><span class="sxs-lookup"><span data-stu-id="d29fc-119">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="d29fc-120">No ofrece ninguna protección adicional de defensa en profundidad contra ataques de divulgación de información y XSS, tales como los que podrían traducirse en un desacuerdo entre el cliente y el servidor sobre el *juego de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="d29fc-120">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="d29fc-121">Use el codificador no seguro solo cuando sepa que el cliente va a interpretar la carga resultante como JSON con codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="d29fc-121">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="d29fc-122">Por ejemplo, puede utilizarlo si el servidor envía el encabezado de respuesta `Content-Type: application/json; charset=utf-8`.</span><span class="sxs-lookup"><span data-stu-id="d29fc-122">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="d29fc-123">No permita nunca que la salida de `UnsafeRelaxedJsonEscaping` sin formato se emita en una página HTML o en un elemento `<script>`.</span><span class="sxs-lookup"><span data-stu-id="d29fc-123">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="d29fc-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="d29fc-124">See also</span></span>

* [<span data-ttu-id="d29fc-125">Información general de System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="d29fc-125">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="d29fc-126">Cómo serializar y deserializar JSON</span><span class="sxs-lookup"><span data-stu-id="d29fc-126">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="d29fc-127">Creación de instancias de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="d29fc-127">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="d29fc-128">Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="d29fc-128">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="d29fc-129">Personalización de los nombres y valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="d29fc-129">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="d29fc-130">Omisión de propiedades</span><span class="sxs-lookup"><span data-stu-id="d29fc-130">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="d29fc-131">Permiso del formato JSON no válido</span><span class="sxs-lookup"><span data-stu-id="d29fc-131">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="d29fc-132">JSON de desbordamiento de control</span><span class="sxs-lookup"><span data-stu-id="d29fc-132">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="d29fc-133">Conservación de las referencias</span><span class="sxs-lookup"><span data-stu-id="d29fc-133">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="d29fc-134">Tipos inmutables y descriptores de acceso no públicos</span><span class="sxs-lookup"><span data-stu-id="d29fc-134">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="d29fc-135">Serialización polimórfica</span><span class="sxs-lookup"><span data-stu-id="d29fc-135">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="d29fc-136">Migración desde Newtonsoft.Json a System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="d29fc-136">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="d29fc-137">Escritura de serializadores y deserializadores personalizados</span><span class="sxs-lookup"><span data-stu-id="d29fc-137">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="d29fc-138">Escritura de convertidores personalizados para la serialización de JSON</span><span class="sxs-lookup"><span data-stu-id="d29fc-138">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="d29fc-139">Compatibilidad con DateTime y DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="d29fc-139">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="d29fc-140">[Referencia de API de System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="d29fc-140">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="d29fc-141">[Referencia de API de System.Text.Json.Serialization](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="d29fc-141">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
