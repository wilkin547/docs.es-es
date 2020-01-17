---
title: Serialización y deserialización de C# JSON mediante .net
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: acb83be9b20a155b6b6a9fb5ade38e099f54e71d
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163597"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="f0a3e-102">Serialización y deserialización de JSON (cálculo de referencias y desserialización) en .NET: información general</span><span class="sxs-lookup"><span data-stu-id="f0a3e-102">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="f0a3e-103">El espacio de nombres `System.Text.Json` proporciona funcionalidad para serializar y deserializar a partir de notación de objetos JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="f0a3e-103">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="f0a3e-104">El diseño de biblioteca enfatiza el alto rendimiento y la asignación de memoria baja en un conjunto de características amplio.</span><span class="sxs-lookup"><span data-stu-id="f0a3e-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="f0a3e-105">La compatibilidad integrada con UTF-8 optimiza el proceso de lectura y escritura de texto JSON codificado como UTF-8, que es la codificación más frecuente de los datos en la web y los archivos en disco.</span><span class="sxs-lookup"><span data-stu-id="f0a3e-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="f0a3e-106">La biblioteca también proporciona clases para trabajar con un modelo de objetos de documento (DOM) en memoria.</span><span class="sxs-lookup"><span data-stu-id="f0a3e-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="f0a3e-107">Esta característica permite el acceso aleatorio de solo lectura de los elementos de una cadena o un archivo JSON.</span><span class="sxs-lookup"><span data-stu-id="f0a3e-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span> 

## <a name="how-to-get-the-library"></a><span data-ttu-id="f0a3e-108">Cómo obtener la biblioteca</span><span class="sxs-lookup"><span data-stu-id="f0a3e-108">How to get the library</span></span>

* <span data-ttu-id="f0a3e-109">La biblioteca está integrada como parte del marco de trabajo compartido de [.net Core 3,0](https://aka.ms/netcore3download) .</span><span class="sxs-lookup"><span data-stu-id="f0a3e-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="f0a3e-110">En el caso de otras plataformas de destino, instale el paquete NuGet [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) .</span><span class="sxs-lookup"><span data-stu-id="f0a3e-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="f0a3e-111">El paquete admite:</span><span class="sxs-lookup"><span data-stu-id="f0a3e-111">The package supports:</span></span>
  * <span data-ttu-id="f0a3e-112">.NET Standard 2,0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="f0a3e-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="f0a3e-113">.NET Framework 4.7.2 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="f0a3e-113">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="f0a3e-114">.NET Core 2,0, 2,1 y 2,2</span><span class="sxs-lookup"><span data-stu-id="f0a3e-114">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f0a3e-115">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f0a3e-115">Additional resources</span></span>

* [<span data-ttu-id="f0a3e-116">Cómo usar la biblioteca</span><span class="sxs-lookup"><span data-stu-id="f0a3e-116">How to use the library</span></span>](system-text-json-how-to.md)
* <span data-ttu-id="f0a3e-117">[Cómo migrar desde Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="f0a3e-117">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* [<span data-ttu-id="f0a3e-118">Cómo escribir convertidores</span><span class="sxs-lookup"><span data-stu-id="f0a3e-118">How to write converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="f0a3e-119">[código fuente de System.Text.Json](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="f0a3e-119">[System.Text.Json source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span></span>
* <span data-ttu-id="f0a3e-120">[referencia de API de System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="f0a3e-120">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="f0a3e-121">[System.Text.Json. Referencia de API de serialización](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="f0a3e-121">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
