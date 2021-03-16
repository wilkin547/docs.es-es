---
title: 'Cambio importante: Deserialize char necesita una cadena de un solo carácter'
description: Obtenga información sobre el cambio importante en .NET 5, por el que System.Text.Json requiere una cadena de un solo elemento char en JSON al realizar una deserialización a un destino de un carácter.
ms.date: 12/15/2020
ms.openlocfilehash: e901f8ee7e7521af948a3bcde5cf969640436f7f
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256340"
---
# <a name="systemtextjson-requires-single-char-string-to-deserialize-a-char"></a><span data-ttu-id="8ece5-103">System.Text.Json requiere una cadena de un solo elemento char para deserializar a un elemento char</span><span class="sxs-lookup"><span data-stu-id="8ece5-103">System.Text.Json requires single-char string to deserialize a char</span></span>

<span data-ttu-id="8ece5-104">Para deserializar correctamente un elemento <xref:System.Char> mediante <xref:System.Text.Json>, la cadena JSON debe contener un solo carácter.</span><span class="sxs-lookup"><span data-stu-id="8ece5-104">To successfully deserialize a <xref:System.Char> using <xref:System.Text.Json>, the JSON string must contain a single character.</span></span>

## <a name="change-description"></a><span data-ttu-id="8ece5-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="8ece5-105">Change description</span></span>

<span data-ttu-id="8ece5-106">En versiones anteriores de .NET, una cadena de varios elementos `char` en JSON se deserializaba correctamente en una propiedad o campo `char`.</span><span class="sxs-lookup"><span data-stu-id="8ece5-106">In previous .NET versions, a multi-`char` string in the JSON is successfully deserialized to a `char` property or field.</span></span> <span data-ttu-id="8ece5-107">Solo se usa el primer elemento `char` de la cadena, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ece5-107">Only the first `char` of the string is used, as in the following example:</span></span>

```csharp
// .NET Core 3.0 and 3.1: Returns the first char 'a'.
// .NET 5 and later: Throws JsonException because payload has more than one char.
char deserializedChar = JsonSerializer.Deserialize<char>("\"abc\"");
```

<span data-ttu-id="8ece5-108">En .NET 5 y versiones posteriores, si se pasa algo distinto a una cadena de un solo elemento `char`, se inicia una excepción <xref:System.Text.Json.JsonException> cuando el parámetro de tipo es un elemento `char`.</span><span class="sxs-lookup"><span data-stu-id="8ece5-108">In .NET 5 and later, anything other than a single-`char` string causes a <xref:System.Text.Json.JsonException> to be thrown when the deserialization target is a `char`.</span></span> <span data-ttu-id="8ece5-109">La siguiente cadena de ejemplo se deserializa correctamente en todas las versiones de .NET:</span><span class="sxs-lookup"><span data-stu-id="8ece5-109">The following example string is successfully deserialized in all .NET versions:</span></span>

```csharp
// Correct usage.
char deserializedChar = JsonSerializer.Deserialize<char>("\"a\"");
```

## <a name="version-introduced"></a><span data-ttu-id="8ece5-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="8ece5-110">Version introduced</span></span>

<span data-ttu-id="8ece5-111">5.0</span><span class="sxs-lookup"><span data-stu-id="8ece5-111">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="8ece5-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="8ece5-112">Reason for change</span></span>

<span data-ttu-id="8ece5-113">El análisis para la deserialización solo se realiza correctamente si la carga proporcionada es válida para el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="8ece5-113">Parsing for deserialization should only succeed when the provided payload is valid for the target type.</span></span> <span data-ttu-id="8ece5-114">Para un tipo `char`, la única carga válida es una cadena de un solo elemento `char`.</span><span class="sxs-lookup"><span data-stu-id="8ece5-114">For a `char` type, the only valid payload is a single-`char` string.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="8ece5-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="8ece5-115">Recommended action</span></span>

<span data-ttu-id="8ece5-116">Al deserializar JSON en un destino `char`, asegúrese de que la cadena se compone de un solo elemento `char`.</span><span class="sxs-lookup"><span data-stu-id="8ece5-116">When you deserialize JSON into a `char` target, make sure the string consists of a single `char`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="8ece5-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="8ece5-117">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`

### Category

Serialization

-->
