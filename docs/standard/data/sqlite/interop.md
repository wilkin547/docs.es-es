---
title: Interoperabilidad
ms.date: 12/13/2019
description: Obtenga información sobre cómo interoperar con otras bibliotecas de SQLite.
ms.openlocfilehash: 486e2a8e00999b8ebe9c85a5fcc1539c514676d3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450463"
---
# <a name="interoperability"></a>Interoperabilidad

Microsoft. Data. SQLite usa SQLitePCLRaw para interactuar con la biblioteca nativa de SQLite. SQLitePCLRaw proporciona una API de .NET fina a través de la API nativa de SQLite. SqliteConnection y SqliteDataReader proporcionan acceso a los objetos SQLitePCLRaw subyacentes, lo que permite llamar a estas API directamente.

En el ejemplo siguiente se muestra cómo llamar a `sqlite3_trace` para escribir instrucciones SQL ejecutadas en la consola:

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_Trace)]

Y en el ejemplo siguiente se muestra la llamada a `sqlite3_stmt_status` para ver cuántos pasos de máquina virtual de SQLite se compilaron en una instrucción SQL:

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_StatementStatus)]

Los objetos SQLitePCLRaw incluso exponen un puntero a los objetos nativos que permiten P/Invoke API de SQLite nativas adicionales.
