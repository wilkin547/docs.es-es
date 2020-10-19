---
title: Cambios importantes de la serialización
description: En este artículo se enumeran los cambios importantes en la categoría de serialización en .NET Core y .NET 5.0 y versiones posteriores.
ms.date: 07/30/2020
ms.openlocfilehash: 65006e6fb45ed2d54699c9972e0489e3ac5ac8bc
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955346"
---
# <a name="serialization-breaking-changes"></a><span data-ttu-id="2d739-103">Cambios importantes de la serialización</span><span class="sxs-lookup"><span data-stu-id="2d739-103">Serialization breaking changes</span></span>

<span data-ttu-id="2d739-104">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="2d739-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="2d739-105">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="2d739-105">Breaking change</span></span> | <span data-ttu-id="2d739-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="2d739-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="2d739-107">JsonSerializer.Serialize inicia la excepción ArgumentNullException cuando el parámetro de tipo es NULL</span><span class="sxs-lookup"><span data-stu-id="2d739-107">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | <span data-ttu-id="2d739-108">5.0</span><span class="sxs-lookup"><span data-stu-id="2d739-108">5.0</span></span> |
| [<span data-ttu-id="2d739-109">JsonSerializer.Deserialize requiere una cadena de un solo carácter</span><span class="sxs-lookup"><span data-stu-id="2d739-109">JsonSerializer.Deserialize requires single-character string</span></span>](#jsonserializerdeserialize-requires-single-character-string) | <span data-ttu-id="2d739-110">5.0</span><span class="sxs-lookup"><span data-stu-id="2d739-110">5.0</span></span> |
| [<span data-ttu-id="2d739-111">BinaryFormatter.Deserialize vuelve a encapsular algunas excepciones en SerializationException</span><span class="sxs-lookup"><span data-stu-id="2d739-111">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | <span data-ttu-id="2d739-112">5.0</span><span class="sxs-lookup"><span data-stu-id="2d739-112">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="2d739-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="2d739-113">.NET 5.0</span></span>

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

***

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

***

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
