---
title: Extensiones de
ms.date: 12/13/2019
description: Obtenga información sobre cómo cargar las extensiones de SQLite.
ms.openlocfilehash: ab00ccf31b8a22407fc177c18149fe4825a19091
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450481"
---
# <a name="extensions"></a>Extensiones de

SQLite admite la carga de extensiones en tiempo de ejecución. Las extensiones incluyen elementos como funciones SQL adicionales, intercalaciones, tablas virtuales, etc.

.NET Core incluye lógica adicional para buscar bibliotecas nativas en otros lugares, como los paquetes NuGet a los que se hace referencia. Desafortunadamente, SQLite no puede aprovechar esta lógica; llama directamente a la API de la plataforma para cargar bibliotecas. Por este motivo, es posible que la aplicación tenga que modificar las variables de entorno PATH, LD_LIBRARY_PATH o DYLD_LIBRARY_PATH antes de cargar las extensiones de SQLite. Hay [un ejemplo](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) en github que muestra cómo buscar archivos binarios para el tiempo de ejecución actual dentro de un paquete NuGet al que se hace referencia.

Para cargar una extensión, llame al método <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A>. Microsoft. Data. SQLite garantizará que la extensión permanece cargada incluso si la conexión se cierra y se vuelve a abrir.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a>Vea también

* [Extensiones de carga en tiempo de ejecución](https://www.sqlite.org/loadext.html)
