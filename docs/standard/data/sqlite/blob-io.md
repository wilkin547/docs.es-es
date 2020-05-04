---
title: E/S de blob
ms.date: 12/13/2019
description: Obtenga información sobre cómo usar la característica de E/S de blob de SQLite.
ms.openlocfilehash: 0c133deacdc19684eca3a6724fb398dc01fda558
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450307"
---
# <a name="blob-io"></a>E/S de blob

El uso de memoria mientras se leen y escriben objetos grandes se puede reducir transmitiendo los datos dentro y fuera de la base de datos. Esto puede ser especialmente útil al analizar o transformar los datos.

Empiece insertando una fila del modo habitual. Use la función SQL `zeroblob()` para asignar espacio en la base de datos para que contenga el objeto grande. La función `last_insert_rowid()` proporciona un método cómodo de obtener el ROWID.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

Después de insertar la fila, abra una secuencia para escribir el objeto grande usando <xref:Microsoft.Data.Sqlite.SqliteBlob>.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

Para transmitir el objeto grande fuera de la base de datos, hay que seleccionar el ROWID o uno de sus alias como se muestra aquí, además de la columna del objeto grande. Si no se selecciona el ROWID, se cargará en la memoria el objeto entero. El objeto devuelto por `GetStream()` será un elemento `SqliteBlob` si el proceso se realiza correctamente.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
