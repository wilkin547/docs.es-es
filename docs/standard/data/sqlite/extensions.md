---
title: Extensiones
ms.date: 12/13/2019
description: Obtenga información sobre cómo cargar extensiones SQLite.
ms.openlocfilehash: 51c705349c25240fe42e0edda8004a3e3b013ca3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242964"
---
# <a name="extensions"></a><span data-ttu-id="5a8e1-103">Extensiones</span><span class="sxs-lookup"><span data-stu-id="5a8e1-103">Extensions</span></span>

<span data-ttu-id="5a8e1-104">SQLite admite la carga de extensiones en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5a8e1-104">SQLite supports loading extensions at run time.</span></span> <span data-ttu-id="5a8e1-105">Las extensiones incluyen elementos como funciones SQL adicionales, intercalaciones, tablas virtuales y mucho más.</span><span class="sxs-lookup"><span data-stu-id="5a8e1-105">Extensions include things like additional SQL functions, collations, virtual tables, and more.</span></span>

<span data-ttu-id="5a8e1-106">.NET Core incluye lógica adicional para localizar bibliotecas nativas en lugares adicionales, como paquetes NuGet a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="5a8e1-106">.NET Core includes additional logic for locating native libraries in additional places like referenced NuGet packages.</span></span> <span data-ttu-id="5a8e1-107">Desafortunadamente, SQLite no puede aprovechar esta lógica; llama a la API de la plataforma directamente para cargar bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="5a8e1-107">Unfortunately, SQLite can't leverage this logic; it calls the platform API directly to load libraries.</span></span> <span data-ttu-id="5a8e1-108">Por este caso, es posible que deba modificar las variables de entorno PATH, LD_LIBRARY_PATH o DYLD_LIBRARY_PATH antes de cargar las extensiones SQLite.</span><span class="sxs-lookup"><span data-stu-id="5a8e1-108">Because of this, you may need to modify the PATH, LD_LIBRARY_PATH, or DYLD_LIBRARY_PATH environment variables before loading SQLite extensions.</span></span> <span data-ttu-id="5a8e1-109">Hay [un ejemplo](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) en GitHub que muestra cómo encontrar archivos binarios para el tiempo de ejecución actual dentro de un paquete NuGet al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="5a8e1-109">There's [a sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) on GitHub that demonstrates finding binaries for the current runtime inside a referenced NuGet package.</span></span>

<span data-ttu-id="5a8e1-110">Para cargar una extensión, llame al <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> método.</span><span class="sxs-lookup"><span data-stu-id="5a8e1-110">To load an extension, call the <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> method.</span></span> <span data-ttu-id="5a8e1-111">Microsoft.Data.Sqlite se asegurará de que la extensión permanece cargada incluso si la conexión se cierra y se vuelve a abrir.</span><span class="sxs-lookup"><span data-stu-id="5a8e1-111">Microsoft.Data.Sqlite will ensure that the extension remains loaded even if the connection is closed and reopened.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a><span data-ttu-id="5a8e1-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5a8e1-112">See also</span></span>

* [<span data-ttu-id="5a8e1-113">Extensiones cargables en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="5a8e1-113">Run-Time Loadable Extensions</span></span>](https://www.sqlite.org/loadext.html)
