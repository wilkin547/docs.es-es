---
title: Extensiones de
ms.date: 12/13/2019
description: Obtenga información sobre cómo cargar las extensiones de SQLite.
ms.openlocfilehash: 74b207205492bac48c89cb756470326f8e4a13c4
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777372"
---
# <a name="extensions"></a><span data-ttu-id="67f00-103">Extensiones de</span><span class="sxs-lookup"><span data-stu-id="67f00-103">Extensions</span></span>

<span data-ttu-id="67f00-104">SQLite admite la carga de extensiones en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="67f00-104">SQLite supports loading extensions at run time.</span></span> <span data-ttu-id="67f00-105">Las extensiones incluyen elementos como funciones SQL adicionales, intercalaciones, tablas virtuales, etc.</span><span class="sxs-lookup"><span data-stu-id="67f00-105">Extensions include things like additional SQL functions, collations, virtual tables, and more.</span></span>

<span data-ttu-id="67f00-106">.NET Core incluye lógica adicional para buscar bibliotecas nativas en otros lugares, como los paquetes NuGet a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="67f00-106">.NET Core includes additional logic for locating native libraries in additional places like referenced NuGet packages.</span></span> <span data-ttu-id="67f00-107">Desafortunadamente, SQLite no puede aprovechar esta lógica; llama directamente a la API de la plataforma para cargar bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="67f00-107">Unfortunately, SQLite can't leverage this logic; it calls the platform API directly to load libraries.</span></span> <span data-ttu-id="67f00-108">Por este motivo, es posible que la aplicación tenga que modificar las variables de entorno PATH, LD_LIBRARY_PATH o DYLD_LIBRARY_PATH antes de cargar las extensiones de SQLite.</span><span class="sxs-lookup"><span data-stu-id="67f00-108">Because of this, your app may need to modify the PATH, LD_LIBRARY_PATH, or DYLD_LIBRARY_PATH environment variables before loading SQLite extensions.</span></span> <span data-ttu-id="67f00-109">Hay [un ejemplo](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) en github que muestra cómo buscar archivos binarios para el tiempo de ejecución actual dentro de un paquete NuGet al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="67f00-109">There's [a sample](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) on GitHub that demonstrates finding binaries for the current runtime inside a referenced NuGet package.</span></span>

<span data-ttu-id="67f00-110">Para cargar una extensión, llame al método <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A>.</span><span class="sxs-lookup"><span data-stu-id="67f00-110">To load an extension, call the <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> method.</span></span> <span data-ttu-id="67f00-111">Microsoft. Data. SQLite garantizará que la extensión permanece cargada incluso si la conexión se cierra y se vuelve a abrir.</span><span class="sxs-lookup"><span data-stu-id="67f00-111">Microsoft.Data.Sqlite will ensure that the extension remains loaded even if the connection is closed and reopened.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a><span data-ttu-id="67f00-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="67f00-112">See also</span></span>

* [<span data-ttu-id="67f00-113">Extensiones de carga en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="67f00-113">Run-Time Loadable Extensions</span></span>](https://www.sqlite.org/loadext.html)
