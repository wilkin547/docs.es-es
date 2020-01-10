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
# <a name="extensions"></a>Extensiones de

SQLite admite la carga de extensiones en tiempo de ejecución. Las extensiones incluyen elementos como funciones SQL adicionales, intercalaciones, tablas virtuales, etc.

.NET Core incluye lógica adicional para buscar bibliotecas nativas en otros lugares, como los paquetes NuGet a los que se hace referencia. Desafortunadamente, SQLite no puede aprovechar esta lógica; llama directamente a la API de la plataforma para cargar bibliotecas. Por este motivo, es posible que la aplicación tenga que modificar las variables de entorno PATH, LD_LIBRARY_PATH o DYLD_LIBRARY_PATH antes de cargar las extensiones de SQLite. Hay [un ejemplo](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) en github que muestra cómo buscar archivos binarios para el tiempo de ejecución actual dentro de un paquete NuGet al que se hace referencia.

Para cargar una extensión, llame al método <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A>. Microsoft. Data. SQLite garantizará que la extensión permanece cargada incluso si la conexión se cierra y se vuelve a abrir.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a>Vea también

* [Extensiones de carga en tiempo de ejecución](https://www.sqlite.org/loadext.html)
