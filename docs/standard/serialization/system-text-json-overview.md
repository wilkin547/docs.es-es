---
title: Serialización y deserialización de C# JSON mediante .net
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 6561d5e1580e1170369622ebc7bb330ff4e0964f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705787"
---
# <a name="json-serialization-in-net---overview"></a><span data-ttu-id="e718e-102">Serialización de JSON en .NET: información general</span><span class="sxs-lookup"><span data-stu-id="e718e-102">JSON serialization in .NET - overview</span></span>

<span data-ttu-id="e718e-103">El espacio de nombres `System.Text.Json` proporciona funcionalidad para serializar y deserializar a partir de notación de objetos JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="e718e-103">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="e718e-104">El diseño de biblioteca enfatiza el alto rendimiento y la asignación de memoria baja en un conjunto de características amplio.</span><span class="sxs-lookup"><span data-stu-id="e718e-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="e718e-105">La compatibilidad integrada con UTF-8 optimiza el proceso de lectura y escritura de texto JSON codificado como UTF-8, que es la codificación más frecuente de los datos en la web y los archivos en disco.</span><span class="sxs-lookup"><span data-stu-id="e718e-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="e718e-106">La biblioteca también proporciona clases para trabajar con un modelo de objetos de documento (DOM) en memoria.</span><span class="sxs-lookup"><span data-stu-id="e718e-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="e718e-107">Esta característica permite el acceso aleatorio de solo lectura de los elementos de una cadena o un archivo JSON.</span><span class="sxs-lookup"><span data-stu-id="e718e-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span> 

## <a name="how-to-get-the-library"></a><span data-ttu-id="e718e-108">Cómo obtener la biblioteca</span><span class="sxs-lookup"><span data-stu-id="e718e-108">How to get the library</span></span>

* <span data-ttu-id="e718e-109">La biblioteca está integrada como parte del marco de trabajo compartido de [.net Core 3,0](https://aka.ms/netcore3download) .</span><span class="sxs-lookup"><span data-stu-id="e718e-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="e718e-110">En el caso de otras plataformas de destino, instale el paquete NuGet [System. Text. JSON](https://www.nuget.org/packages/System.Text.Json) .</span><span class="sxs-lookup"><span data-stu-id="e718e-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="e718e-111">El paquete admite:</span><span class="sxs-lookup"><span data-stu-id="e718e-111">The package supports:</span></span>
  * <span data-ttu-id="e718e-112">.NET Standard 2,0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="e718e-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="e718e-113">.NET Framework 4.6.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="e718e-113">.NET Framework 4.6.1 and later versions</span></span>
  * <span data-ttu-id="e718e-114">.NET Core 2,0, 2,1 y 2,2</span><span class="sxs-lookup"><span data-stu-id="e718e-114">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e718e-115">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e718e-115">Additional resources</span></span>

* [<span data-ttu-id="e718e-116">Cómo usar la biblioteca</span><span class="sxs-lookup"><span data-stu-id="e718e-116">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="e718e-117">Código fuente</span><span class="sxs-lookup"><span data-stu-id="e718e-117">Source code</span></span>](https://github.com/dotnet/runtime/tree/master/src/libraries/System.Text.Json)
* [<span data-ttu-id="e718e-118">Referencia de API</span><span class="sxs-lookup"><span data-stu-id="e718e-118">API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="e718e-119">Guía básica</span><span class="sxs-lookup"><span data-stu-id="e718e-119">Roadmap</span></span>](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Text.Json/roadmap/README.md)
* <span data-ttu-id="e718e-120">Problemas de GitHub en el repositorio dotnet/corefx</span><span class="sxs-lookup"><span data-stu-id="e718e-120">GitHub issues in the dotnet/corefx repository</span></span>
  * [<span data-ttu-id="e718e-121">Debate sobre el desarrollo de System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="e718e-121">Discussion about the development of System.Text.Json</span></span>](https://github.com/dotnet/corefx/issues/33115) <!-- TODO: Issues are still not moved to the new repo-->
  * [<span data-ttu-id="e718e-122">Todos los problemas de System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="e718e-122">All System.Text.Json issues</span></span>](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)
  * [<span data-ttu-id="e718e-123">Problemas de System. Text. JSON con la etiqueta JSON-funcionalidad-doc</span><span class="sxs-lookup"><span data-stu-id="e718e-123">System.Text.Json issues labeled json-functionality-doc</span></span>](https://github.com/dotnet/runtime/labels/json-functionality-doc)
