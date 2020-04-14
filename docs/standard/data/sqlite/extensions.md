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
# <a name="extensions"></a>Extensiones

SQLite admite la carga de extensiones en tiempo de ejecución. Las extensiones incluyen elementos como funciones SQL adicionales, intercalaciones, tablas virtuales y mucho más.

.NET Core incluye lógica adicional para localizar bibliotecas nativas en lugares adicionales, como paquetes NuGet a los que se hace referencia. Desafortunadamente, SQLite no puede aprovechar esta lógica; llama a la API de la plataforma directamente para cargar bibliotecas. Por este caso, es posible que deba modificar las variables de entorno PATH, LD_LIBRARY_PATH o DYLD_LIBRARY_PATH antes de cargar las extensiones SQLite. Hay [un ejemplo](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) en GitHub que muestra cómo encontrar archivos binarios para el tiempo de ejecución actual dentro de un paquete NuGet al que se hace referencia.

Para cargar una extensión, llame al <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> método. Microsoft.Data.Sqlite se asegurará de que la extensión permanece cargada incluso si la conexión se cierra y se vuelve a abrir.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a>Consulte también

* [Extensiones cargables en tiempo de ejecución](https://www.sqlite.org/loadext.html)
