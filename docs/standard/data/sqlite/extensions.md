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
# <a name="extensions"></a>Extensiones

SQLite admite la carga de extensiones en tiempo de ejecución. Las extensiones incluyen elementos como funciones SQL adicionales, intercalaciones, tablas virtuales, etc.

.NET Core incluye lógica adicional para buscar bibliotecas nativas en otros lugares, como los paquetes NuGet a los que se hace referencia. Desafortunadamente, SQLite no puede aprovechar esta lógica; llama directamente a la API de la plataforma para cargar las bibliotecas. Por este motivo, es posible que tenga que modificar las variables de entorno PATH, LD_LIBRARY_PATH o DYLD_LIBRARY_PATH antes de cargar las extensiones de SQLite. En GitHub hay [un ejemplo](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) en el que se muestra la búsqueda de archivos binarios para el tiempo de ejecución actual dentro de un paquete NuGet al que se hace referencia.

Para cargar una extensión, llame al método <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A>. Microsoft.Data.SQLite garantizará que la extensión permanece cargada incluso si la conexión se cierra y se vuelve a abrir.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a>Vea también

* [Extensiones de carga en tiempo de ejecución](https://www.sqlite.org/loadext.html)
