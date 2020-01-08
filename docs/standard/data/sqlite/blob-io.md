---
title: E/s de BLOB
ms.date: 12/13/2019
description: Obtenga información sobre cómo usar la característica de e/s de BLOB de SQLite.
ms.openlocfilehash: 0c133deacdc19684eca3a6724fb398dc01fda558
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450307"
---
# <a name="blob-io"></a>E/s de BLOB

Puede reducir el uso de memoria mientras lee y escribe objetos grandes transmitiendo los datos dentro y fuera de la base de datos. Esto puede ser especialmente útil cuando se analizan o transforman los datos.

Empiece por insertar una fila como normal. Utilice la función SQL `zeroblob()` para asignar espacio en la base de datos para que contenga el objeto grande. La función `last_insert_rowid()` proporciona una manera cómoda de obtener el ROWID.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

Después de insertar la fila, abra una secuencia para escribir el objeto grande mediante <xref:Microsoft.Data.Sqlite.SqliteBlob>.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

Para transmitir el objeto grande fuera de la base de datos, debe seleccionar el ROWID o uno de sus alias como se muestra aquí además de la columna del objeto grande. Si no selecciona ROWID, todo el objeto se cargará en la memoria. El objeto devuelto por `GetStream()` será una `SqliteBlob` cuando se haya realizado correctamente.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
