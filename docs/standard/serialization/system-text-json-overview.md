---
title: 'Serialización y deserialización de JSON con C#: .NET'
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 660a2831aa6a807486fc47eae880bcd11347c547
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159551"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="99293-102">Serialización y deserialización de JSON en .NET: información general</span><span class="sxs-lookup"><span data-stu-id="99293-102">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="99293-103">El espacio de nombres `System.Text.Json` proporciona funcionalidad para serializar y deserializar desde JSON (notaciones de objetos JavaScript).</span><span class="sxs-lookup"><span data-stu-id="99293-103">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="99293-104">El diseño de biblioteca resalta el rendimiento elevado y la asignación de memoria baja en un amplio conjunto de características.</span><span class="sxs-lookup"><span data-stu-id="99293-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="99293-105">La compatibilidad integrada con UTF-8 optimiza el proceso de lectura y escritura de texto JSON codificado como UTF-8, que es la codificación más frecuente de los datos en Internet y los archivos en disco.</span><span class="sxs-lookup"><span data-stu-id="99293-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="99293-106">La biblioteca también proporciona clases para trabajar con un Document Object Model (DOM) en memoria.</span><span class="sxs-lookup"><span data-stu-id="99293-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="99293-107">Esta característica permite el acceso de solo lectura aleatorio de los elementos de una cadena o archivo JSON.</span><span class="sxs-lookup"><span data-stu-id="99293-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span>

## <a name="how-to-get-the-library"></a><span data-ttu-id="99293-108">Cómo obtener la biblioteca</span><span class="sxs-lookup"><span data-stu-id="99293-108">How to get the library</span></span>

* <span data-ttu-id="99293-109">La biblioteca está integrada como parte del marco compartido de [.NET Core 3.0](https://aka.ms/netcore3download).</span><span class="sxs-lookup"><span data-stu-id="99293-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="99293-110">En cuanto a otros marcos de destino, instale el paquete NuGet [System.Text.Json](https://www.nuget.org/packages/System.Text.Json),</span><span class="sxs-lookup"><span data-stu-id="99293-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="99293-111">que admite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="99293-111">The package supports:</span></span>
  * <span data-ttu-id="99293-112">.NET Standard 2.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="99293-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="99293-113">.NET Framework 4.7.2 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="99293-113">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="99293-114">.NET Core 2.0, 2.1 y 2.2</span><span class="sxs-lookup"><span data-stu-id="99293-114">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="99293-115">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="99293-115">Additional resources</span></span>

* [<span data-ttu-id="99293-116">Cómo usar la biblioteca</span><span class="sxs-lookup"><span data-stu-id="99293-116">How to use the library</span></span>](system-text-json-how-to.md)
* <span data-ttu-id="99293-117">[Procedimiento para migrar desde Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="99293-117">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* [<span data-ttu-id="99293-118">Procedimiento para escribir convertidores</span><span class="sxs-lookup"><span data-stu-id="99293-118">How to write converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="99293-119">[Código fuente System.Text.Json](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="99293-119">[System.Text.Json source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)</span></span>
* <span data-ttu-id="99293-120">[Referencia de API System.Text.Json](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="99293-120">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="99293-121">[System.Text.JsonReferencia de API .Serialization](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="99293-121">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
