---
title: Control del código JSON de desbordamiento con System.Text.Json
description: Aprenda a controlar el código JSON de desbordamiento durante la serialización y deserialización desde JSON en .NET.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 265ce4f77d353720419122d17c36e508a377b68f
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008921"
---
# <a name="how-to-handle-overflow-json-with-no-locsystemtextjson"></a><span data-ttu-id="8a5cc-103">Control del código JSON de desbordamiento con System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="8a5cc-103">How to handle overflow JSON with System.Text.Json</span></span>

<span data-ttu-id="8a5cc-104">En este artículo, aprenderá a controlar el código JSON de desbordamiento con el espacio de nombres `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="8a5cc-104">In this article, you will learn how to handle overflow JSON with the `System.Text.Json` namespace.</span></span>

## <a name="handle-overflow-json"></a><span data-ttu-id="8a5cc-105">JSON de desbordamiento de control</span><span class="sxs-lookup"><span data-stu-id="8a5cc-105">Handle overflow JSON</span></span>

<span data-ttu-id="8a5cc-106">Durante la deserialización, es posible que reciba datos en el archivo JSON que no están representados por las propiedades del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="8a5cc-106">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="8a5cc-107">Por ejemplo, supongamos que el tipo de destino es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="8a5cc-107">For example, suppose your target type is this:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

<span data-ttu-id="8a5cc-108">Y el JSON que se va a deserializar es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="8a5cc-108">And the JSON to be deserialized is this:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

<span data-ttu-id="8a5cc-109">Si deserializa el JSON que se muestra en el tipo mostrado, las propiedades `DatesAvailable` y `SummaryWords` no tienen a donde ir y se pierden.</span><span class="sxs-lookup"><span data-stu-id="8a5cc-109">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="8a5cc-110">Para capturar datos adicionales tales como estas propiedades, aplique el atributo [[JsonExtensionData]](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) a una propiedad de tipo `Dictionary<string,object>` o `Dictionary<string,JsonElement>`:</span><span class="sxs-lookup"><span data-stu-id="8a5cc-110">To capture extra data such as these properties, apply the [[JsonExtensionData]](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithExtensionData":::

<span data-ttu-id="8a5cc-111">Al deserializar el JSON que se muestra anteriormente en este tipo de ejemplo, los datos adicionales se convierten en pares clave-valor de la propiedad `ExtensionData`:</span><span class="sxs-lookup"><span data-stu-id="8a5cc-111">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

| <span data-ttu-id="8a5cc-112">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="8a5cc-112">Property</span></span> | <span data-ttu-id="8a5cc-113">Valor</span><span class="sxs-lookup"><span data-stu-id="8a5cc-113">Value</span></span> | <span data-ttu-id="8a5cc-114">Notas</span><span class="sxs-lookup"><span data-stu-id="8a5cc-114">Notes</span></span> |
|--|--|--|
| `Date` | `"8/1/2019 12:00:00 AM -07:00"` |  |
| `TemperatureCelsius` | `0` | <span data-ttu-id="8a5cc-115">Error de coincidencia con distinción de mayúsculas y minúsculas (`temperatureCelsius` en el JSON), por lo que no se establece la propiedad.</span><span class="sxs-lookup"><span data-stu-id="8a5cc-115">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| `Summary` | `"Hot"` |  |
| `ExtensionData` | `temperatureCelsius: 25` | <span data-ttu-id="8a5cc-116">Dado que el caso no coincidía, esta propiedad JSON es un extra y se convierte en un par clave-valor en el diccionario.</span><span class="sxs-lookup"><span data-stu-id="8a5cc-116">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span> |
| `DatesAvailable` | `[ "8/1/2019 12:00:00 AM -07:00", "8/2/2019 12:00:00 AM -07:00" ]` | <span data-ttu-id="8a5cc-117">La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="8a5cc-117">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span> |
| `SummaryWords` | `[ "Cool", "Windy", "Humid" ]` | <span data-ttu-id="8a5cc-118">La propiedad adicional del JSON se convierte en un par clave-valor, con una matriz como objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="8a5cc-118">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span> |

<span data-ttu-id="8a5cc-119">Cuando se serializa el objeto de destino, los pares clave-valor de los datos de la extensión se convierten en propiedades JSON tal y como estaban en el JSON entrante:</span><span class="sxs-lookup"><span data-stu-id="8a5cc-119">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 0,
  "Summary": "Hot",
  "temperatureCelsius": 25,
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

<span data-ttu-id="8a5cc-120">Observe que el nombre de la propiedad `ExtensionData` no aparece en el archivo JSON.</span><span class="sxs-lookup"><span data-stu-id="8a5cc-120">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="8a5cc-121">Este comportamiento permite que JSON realice un viaje de ida y vuelta sin perder ningún dato adicional que de otro modo no se deserializaría.</span><span class="sxs-lookup"><span data-stu-id="8a5cc-121">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a5cc-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a5cc-122">See also</span></span>

* [<span data-ttu-id="8a5cc-123">Información general de System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="8a5cc-123">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="8a5cc-124">Cómo serializar y deserializar JSON</span><span class="sxs-lookup"><span data-stu-id="8a5cc-124">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="8a5cc-125">Creación de instancias de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="8a5cc-125">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="8a5cc-126">Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="8a5cc-126">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="8a5cc-127">Personalización de los nombres y valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="8a5cc-127">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="8a5cc-128">Omisión de propiedades</span><span class="sxs-lookup"><span data-stu-id="8a5cc-128">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="8a5cc-129">Permiso del formato JSON no válido</span><span class="sxs-lookup"><span data-stu-id="8a5cc-129">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="8a5cc-130">Conservación de las referencias</span><span class="sxs-lookup"><span data-stu-id="8a5cc-130">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="8a5cc-131">Tipos inmutables y descriptores de acceso no públicos</span><span class="sxs-lookup"><span data-stu-id="8a5cc-131">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="8a5cc-132">Serialización polimórfica</span><span class="sxs-lookup"><span data-stu-id="8a5cc-132">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="8a5cc-133">Migración desde Newtonsoft.Json a System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="8a5cc-133">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="8a5cc-134">Personalización de la codificación de caracteres</span><span class="sxs-lookup"><span data-stu-id="8a5cc-134">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="8a5cc-135">Escritura de serializadores y deserializadores personalizados</span><span class="sxs-lookup"><span data-stu-id="8a5cc-135">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="8a5cc-136">Escritura de convertidores personalizados para la serialización de JSON</span><span class="sxs-lookup"><span data-stu-id="8a5cc-136">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="8a5cc-137">Compatibilidad con DateTime y DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="8a5cc-137">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="8a5cc-138">[Referencia de API de System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="8a5cc-138">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="8a5cc-139">[Referencia de API de System.Text.Json.Serialization](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="8a5cc-139">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
