---
title: Serialización y deserialización de C# JSON mediante .net
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: c05783963ba521109fb542f247ec9e62fdb5c2d9
ms.sourcegitcommit: dfad244ba549702b649bfef3bb057e33f24a8fb2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2020
ms.locfileid: "75904644"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="cf741-102">Serialización y deserialización de JSON (cálculo de referencias y desserialización) en .NET: información general</span><span class="sxs-lookup"><span data-stu-id="cf741-102">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="cf741-103">El espacio de nombres `System.Text.Json` proporciona funcionalidad para serializar y deserializar a partir de notación de objetos JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="cf741-103">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="cf741-104">El diseño de biblioteca enfatiza el alto rendimiento y la asignación de memoria baja en un conjunto de características amplio.</span><span class="sxs-lookup"><span data-stu-id="cf741-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="cf741-105">La compatibilidad integrada con UTF-8 optimiza el proceso de lectura y escritura de texto JSON codificado como UTF-8, que es la codificación más frecuente de los datos en la web y los archivos en disco.</span><span class="sxs-lookup"><span data-stu-id="cf741-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="cf741-106">La biblioteca también proporciona clases para trabajar con un modelo de objetos de documento (DOM) en memoria.</span><span class="sxs-lookup"><span data-stu-id="cf741-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="cf741-107">Esta característica permite el acceso aleatorio de solo lectura de los elementos de una cadena o un archivo JSON.</span><span class="sxs-lookup"><span data-stu-id="cf741-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span> 

## <a name="how-to-get-the-library"></a><span data-ttu-id="cf741-108">Cómo obtener la biblioteca</span><span class="sxs-lookup"><span data-stu-id="cf741-108">How to get the library</span></span>

* <span data-ttu-id="cf741-109">La biblioteca está integrada como parte del marco de trabajo compartido de [.net Core 3,0](https://aka.ms/netcore3download) .</span><span class="sxs-lookup"><span data-stu-id="cf741-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="cf741-110">En el caso de otras plataformas de destino, instale el paquete NuGet [System. Text. JSON](https://www.nuget.org/packages/System.Text.Json) .</span><span class="sxs-lookup"><span data-stu-id="cf741-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="cf741-111">El paquete admite:</span><span class="sxs-lookup"><span data-stu-id="cf741-111">The package supports:</span></span>
  * <span data-ttu-id="cf741-112">.NET Standard 2,0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="cf741-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="cf741-113">.NET Framework 4.7.2 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="cf741-113">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="cf741-114">.NET Core 2,0, 2,1 y 2,2</span><span class="sxs-lookup"><span data-stu-id="cf741-114">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cf741-115">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="cf741-115">Additional resources</span></span>

* [<span data-ttu-id="cf741-116">Cómo usar la biblioteca</span><span class="sxs-lookup"><span data-stu-id="cf741-116">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="cf741-117">Cómo migrar desde Newtonsoft. JSON</span><span class="sxs-lookup"><span data-stu-id="cf741-117">How to migrate from Newtonsoft.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="cf741-118">Cómo escribir convertidores</span><span class="sxs-lookup"><span data-stu-id="cf741-118">How to write converters</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="cf741-119">Código fuente de System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="cf741-119">System.Text.Json source code</span></span>](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)
* [<span data-ttu-id="cf741-120">Referencia de la API System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="cf741-120">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="cf741-121">Referencia de API de System. Text. JSON. Serialization</span><span class="sxs-lookup"><span data-stu-id="cf741-121">System.Text.Json.Serialization API reference</span></span>](xref:System.Text.Json.Serialization)
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
