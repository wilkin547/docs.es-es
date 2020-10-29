---
title: Cambios importantes de la serialización
description: En este artículo se enumeran los cambios importantes en la categoría de serialización en .NET Core y .NET 5.0 y versiones posteriores.
ms.date: 07/30/2020
ms.openlocfilehash: 67608c8e7a9745c060b7eb179fe5a956ede9f80f
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "92332890"
---
# <a name="serialization-breaking-changes"></a><span data-ttu-id="bec7a-103">Cambios importantes de la serialización</span><span class="sxs-lookup"><span data-stu-id="bec7a-103">Serialization breaking changes</span></span>

<span data-ttu-id="bec7a-104">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="bec7a-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="bec7a-105">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="bec7a-105">Breaking change</span></span> | <span data-ttu-id="bec7a-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="bec7a-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="bec7a-107">Las aplicaciones ASP.NET Core permiten deserializar los números entrecomillados</span><span class="sxs-lookup"><span data-stu-id="bec7a-107">ASP.NET Core apps allow deserializing quoted numbers</span></span>](#aspnet-core-apps-allow-deserializing-quoted-numbers) | <span data-ttu-id="bec7a-108">5.0</span><span class="sxs-lookup"><span data-stu-id="bec7a-108">5.0</span></span> |
| [<span data-ttu-id="bec7a-109">Se admiten las opciones PropertyNamingPolicy, PropertyNameCaseInsensitive y Encoder al serializar y deserializar pares clave-valor</span><span class="sxs-lookup"><span data-stu-id="bec7a-109">PropertyNamingPolicy, PropertyNameCaseInsensitive, and Encoder options are honored when serializing and deserializing key-value pairs</span></span>](#propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs) | <span data-ttu-id="bec7a-110">5.0</span><span class="sxs-lookup"><span data-stu-id="bec7a-110">5.0</span></span> |
| [<span data-ttu-id="bec7a-111">Constructores no públicos sin parámetros que no se usan para la deserialización</span><span class="sxs-lookup"><span data-stu-id="bec7a-111">Non-public, parameterless constructors not used for deserialization</span></span>](#non-public-parameterless-constructors-not-used-for-deserialization) | <span data-ttu-id="bec7a-112">5.0</span><span class="sxs-lookup"><span data-stu-id="bec7a-112">5.0</span></span> |
| [<span data-ttu-id="bec7a-113">JsonSerializer.Serialize inicia la excepción ArgumentNullException cuando el parámetro de tipo es NULL</span><span class="sxs-lookup"><span data-stu-id="bec7a-113">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | <span data-ttu-id="bec7a-114">5.0</span><span class="sxs-lookup"><span data-stu-id="bec7a-114">5.0</span></span> |
| [<span data-ttu-id="bec7a-115">JsonSerializer.Deserialize requiere una cadena de un solo carácter</span><span class="sxs-lookup"><span data-stu-id="bec7a-115">JsonSerializer.Deserialize requires single-character string</span></span>](#jsonserializerdeserialize-requires-single-character-string) | <span data-ttu-id="bec7a-116">5.0</span><span class="sxs-lookup"><span data-stu-id="bec7a-116">5.0</span></span> |
| [<span data-ttu-id="bec7a-117">BinaryFormatter.Deserialize vuelve a encapsular algunas excepciones en SerializationException</span><span class="sxs-lookup"><span data-stu-id="bec7a-117">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | <span data-ttu-id="bec7a-118">5.0</span><span class="sxs-lookup"><span data-stu-id="bec7a-118">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="bec7a-119">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="bec7a-119">.NET 5.0</span></span>

[!INCLUDE [jsonserializer-allows-reading-numbers-as-strings](../../../includes/core-changes/serialization/5.0/jsonserializer-allows-reading-numbers-as-strings.md)]

***

[!INCLUDE [options-honored-when-serializing-key-value-pairs](../../../includes/core-changes/serialization/5.0/options-honored-when-serializing-key-value-pairs.md)]

<span data-ttu-id="bec7a-120">\*\*_</span><span class="sxs-lookup"><span data-stu-id="bec7a-120">\*\*_</span></span>

[!INCLUDE [non-public-parameterless-constructors-not-used-for-deserialization](../../../includes/core-changes/serialization/5.0/non-public-parameterless-constructors-not-used-for-deserialization.md)]

_*_

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

_*_

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

_*_

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

<span data-ttu-id="bec7a-121">_\*\*</span><span class="sxs-lookup"><span data-stu-id="bec7a-121">_\*\*</span></span>
