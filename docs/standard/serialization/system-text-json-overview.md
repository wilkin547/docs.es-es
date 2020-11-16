---
title: 'Serialización y deserialización de JSON con C#: .NET'
description: 'En esta introducción se describe la funcionalidad del espacio de nombres System.Text.Json para serializar y deserializar con JSON en .NET.'
ms.date: 01/10/2020
no-loc:
- 'System.Text.Json'
- 'Newtonsoft.Json'
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: d8bd5bcf78db534bd722972db01253cbd13a7a06
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282403"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="4ba60-103">Serialización y deserialización de JSON en .NET: información general</span><span class="sxs-lookup"><span data-stu-id="4ba60-103">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="4ba60-104">El espacio de nombres `System.Text.Json` proporciona funcionalidad para serializar y deserializar desde JSON (notaciones de objetos JavaScript).</span><span class="sxs-lookup"><span data-stu-id="4ba60-104">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="4ba60-105">El diseño de biblioteca resalta el rendimiento elevado y la asignación de memoria baja en un amplio conjunto de características.</span><span class="sxs-lookup"><span data-stu-id="4ba60-105">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="4ba60-106">La compatibilidad integrada con UTF-8 optimiza el proceso de lectura y escritura de texto JSON codificado como UTF-8, que es la codificación más frecuente de los datos en Internet y los archivos en disco.</span><span class="sxs-lookup"><span data-stu-id="4ba60-106">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="4ba60-107">La biblioteca también proporciona clases para trabajar con un Document Object Model (DOM) en memoria.</span><span class="sxs-lookup"><span data-stu-id="4ba60-107">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="4ba60-108">Esta característica permite el acceso de solo lectura aleatorio de los elementos de una cadena o archivo JSON.</span><span class="sxs-lookup"><span data-stu-id="4ba60-108">This feature enables random read-only access of the elements in a JSON file or string.</span></span>

## <a name="how-to-get-the-library"></a><span data-ttu-id="4ba60-109">Cómo obtener la biblioteca</span><span class="sxs-lookup"><span data-stu-id="4ba60-109">How to get the library</span></span>

* <span data-ttu-id="4ba60-110">La biblioteca está integrada como parte del marco compartido para .NET Core 3.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="4ba60-110">The library is built-in as part of the shared framework for .NET Core 3.0 and later versions.</span></span>
* <span data-ttu-id="4ba60-111">Para versiones anteriores del marco, instale el paquete [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) de NuGet,</span><span class="sxs-lookup"><span data-stu-id="4ba60-111">For earlier framework versions, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="4ba60-112">que admite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4ba60-112">The package supports:</span></span>

  * <span data-ttu-id="4ba60-113">.NET Standard 2.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="4ba60-113">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="4ba60-114">.NET Framework 4.7.2 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="4ba60-114">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="4ba60-115">.NET Core 2.0, 2.1 y 2.2</span><span class="sxs-lookup"><span data-stu-id="4ba60-115">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4ba60-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4ba60-116">Additional resources</span></span>

* [<span data-ttu-id="4ba60-117">Cómo usar la biblioteca</span><span class="sxs-lookup"><span data-stu-id="4ba60-117">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="4ba60-118">Procedimiento para migrar desde Newtonsoft.Json</span><span class="sxs-lookup"><span data-stu-id="4ba60-118">How to migrate from Newtonsoft.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="4ba60-119">Procedimiento para escribir convertidores</span><span class="sxs-lookup"><span data-stu-id="4ba60-119">How to write converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="4ba60-120">[Código fuente System.Text.Json](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="4ba60-120">[System.Text.Json source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span></span>
* <span data-ttu-id="4ba60-121">[Referencia de API System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="4ba60-121">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="4ba60-122">[Referencia de API de System.Text.Json.Serialization](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="4ba60-122">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
