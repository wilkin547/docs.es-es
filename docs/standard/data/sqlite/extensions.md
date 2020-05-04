---
title: Extensiones
ms.date: 12/13/2019
description: Obtenga información sobre cómo cargar extensiones de SQLite.
ms.openlocfilehash: 51c705349c25240fe42e0edda8004a3e3b013ca3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242964"
---
# <a name="extensions"></a><span data-ttu-id="b5bea-103">Extensiones</span><span class="sxs-lookup"><span data-stu-id="b5bea-103">Extensions</span></span>

<span data-ttu-id="b5bea-104">SQLite admite la carga de extensiones en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b5bea-104">SQLite supports loading extensions at run time.</span></span> <span data-ttu-id="b5bea-105">Las extensiones incluyen elementos como funciones SQL adicionales, intercalaciones, tablas virtuales, etc.</span><span class="sxs-lookup"><span data-stu-id="b5bea-105">Extensions include things like additional SQL functions, collations, virtual tables, and more.</span></span>

<span data-ttu-id="b5bea-106">.NET Core incluye lógica adicional para buscar bibliotecas nativas en otros lugares, como los paquetes NuGet a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="b5bea-106">.NET Core includes additional logic for locating native libraries in additional places like referenced NuGet packages.</span></span> <span data-ttu-id="b5bea-107">Desafortunadamente, SQLite no puede aprovechar esta lógica; llama directamente a la API de la plataforma para cargar las bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="b5bea-107">Unfortunately, SQLite can't leverage this logic; it calls the platform API directly to load libraries.</span></span> <span data-ttu-id="b5bea-108">Por este motivo, es posible que tenga que modificar las variables de entorno PATH, LD_LIBRARY_PATH o DYLD_LIBRARY_PATH antes de cargar las extensiones de SQLite.</span><span class="sxs-lookup"><span data-stu-id="b5bea-108">Because of this, you may need to modify the PATH, LD_LIBRARY_PATH, or DYLD_LIBRARY_PATH environment variables before loading SQLite extensions.</span></span> <span data-ttu-id="b5bea-109">En GitHub hay [un ejemplo](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) en el que se muestra la búsqueda de archivos binarios para el tiempo de ejecución actual dentro de un paquete NuGet al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="b5bea-109">There's [a sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) on GitHub that demonstrates finding binaries for the current runtime inside a referenced NuGet package.</span></span>

<span data-ttu-id="b5bea-110">Para cargar una extensión, llame al método <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A>.</span><span class="sxs-lookup"><span data-stu-id="b5bea-110">To load an extension, call the <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> method.</span></span> <span data-ttu-id="b5bea-111">Microsoft.Data.SQLite garantizará que la extensión permanece cargada incluso si la conexión se cierra y se vuelve a abrir.</span><span class="sxs-lookup"><span data-stu-id="b5bea-111">Microsoft.Data.Sqlite will ensure that the extension remains loaded even if the connection is closed and reopened.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a><span data-ttu-id="b5bea-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5bea-112">See also</span></span>

* [<span data-ttu-id="b5bea-113">Extensiones de carga en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b5bea-113">Run-Time Loadable Extensions</span></span>](https://www.sqlite.org/loadext.html)
