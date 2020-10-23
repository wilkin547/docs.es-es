---
title: Cambios importantes de la serialización
description: En este artículo se enumeran los cambios importantes en la categoría de serialización en .NET Core y .NET 5.0 y versiones posteriores.
ms.date: 07/30/2020
ms.openlocfilehash: bb6bd650afeba426edc6e102076f05f97f8e0598
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050483"
---
# <a name="serialization-breaking-changes"></a><span data-ttu-id="bcdf4-103">Cambios importantes de la serialización</span><span class="sxs-lookup"><span data-stu-id="bcdf4-103">Serialization breaking changes</span></span>

<span data-ttu-id="bcdf4-104">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="bcdf4-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="bcdf4-105">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="bcdf4-105">Breaking change</span></span> | <span data-ttu-id="bcdf4-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="bcdf4-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="bcdf4-107">Se admiten las opciones PropertyNamingPolicy, PropertyNameCaseInsensitive y Encoder al serializar y deserializar pares clave-valor</span><span class="sxs-lookup"><span data-stu-id="bcdf4-107">PropertyNamingPolicy, PropertyNameCaseInsensitive, and Encoder options are honored when serializing and deserializing key-value pairs</span></span>](#propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs) | <span data-ttu-id="bcdf4-108">5.0</span><span class="sxs-lookup"><span data-stu-id="bcdf4-108">5.0</span></span> |
| [<span data-ttu-id="bcdf4-109">Constructores no públicos sin parámetros que no se usan para la deserialización</span><span class="sxs-lookup"><span data-stu-id="bcdf4-109">Non-public, parameterless constructors not used for deserialization</span></span>](#non-public-parameterless-constructors-not-used-for-deserialization) | <span data-ttu-id="bcdf4-110">5.0</span><span class="sxs-lookup"><span data-stu-id="bcdf4-110">5.0</span></span> |
| [<span data-ttu-id="bcdf4-111">JsonSerializer.Serialize inicia la excepción ArgumentNullException cuando el parámetro de tipo es NULL</span><span class="sxs-lookup"><span data-stu-id="bcdf4-111">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | <span data-ttu-id="bcdf4-112">5.0</span><span class="sxs-lookup"><span data-stu-id="bcdf4-112">5.0</span></span> |
| [<span data-ttu-id="bcdf4-113">JsonSerializer.Deserialize requiere una cadena de un solo carácter</span><span class="sxs-lookup"><span data-stu-id="bcdf4-113">JsonSerializer.Deserialize requires single-character string</span></span>](#jsonserializerdeserialize-requires-single-character-string) | <span data-ttu-id="bcdf4-114">5.0</span><span class="sxs-lookup"><span data-stu-id="bcdf4-114">5.0</span></span> |
| [<span data-ttu-id="bcdf4-115">BinaryFormatter.Deserialize vuelve a encapsular algunas excepciones en SerializationException</span><span class="sxs-lookup"><span data-stu-id="bcdf4-115">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | <span data-ttu-id="bcdf4-116">5.0</span><span class="sxs-lookup"><span data-stu-id="bcdf4-116">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="bcdf4-117">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="bcdf4-117">.NET 5.0</span></span>

[!INCLUDE [options-honored-when-serializing-key-value-pairs](../../../includes/core-changes/serialization/5.0/options-honored-when-serializing-key-value-pairs.md)]

***

[!INCLUDE [non-public-parameterless-constructors-not-used-for-deserialization](../../../includes/core-changes/serialization/5.0/non-public-parameterless-constructors-not-used-for-deserialization.md)]

***

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

***

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

***

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
