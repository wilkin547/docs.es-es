---
title: Interoperabilidad
ms.date: 12/13/2019
description: Obtenga información sobre cómo interoperar con otras bibliotecas de SQLite.
ms.openlocfilehash: 486e2a8e00999b8ebe9c85a5fcc1539c514676d3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450463"
---
# <a name="interoperability"></a><span data-ttu-id="d2cff-103">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="d2cff-103">Interoperability</span></span>

<span data-ttu-id="d2cff-104">Microsoft.Data.SQLite usa SQLitePCLRaw para interactuar con la biblioteca nativa de SQLite.</span><span class="sxs-lookup"><span data-stu-id="d2cff-104">Microsoft.Data.Sqlite uses SQLitePCLRaw to interact with the native SQLite library.</span></span> <span data-ttu-id="d2cff-105">SQLitePCLRaw proporciona una API de .NET ligera a través de la API SQLite nativa.</span><span class="sxs-lookup"><span data-stu-id="d2cff-105">SQLitePCLRaw provides a thin .NET API over the native SQLite API.</span></span> <span data-ttu-id="d2cff-106">SqliteConnection y SqliteDataReader proporcionan acceso a los objetos SQLitePCLRaw subyacentes, lo que permite llamar a estas API directamente.</span><span class="sxs-lookup"><span data-stu-id="d2cff-106">SqliteConnection and SqliteDataReader provide access to the underlying SQLitePCLRaw objects letting you call these APIs directly.</span></span>

<span data-ttu-id="d2cff-107">En el ejemplo siguiente se muestra cómo llamar a `sqlite3_trace` para escribir instrucciones SQL ejecutadas en la consola:</span><span class="sxs-lookup"><span data-stu-id="d2cff-107">The following example shows how to call `sqlite3_trace` to write executed SQL statements to the console:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_Trace)]

<span data-ttu-id="d2cff-108">Y en el ejemplo siguiente se muestra la llamada a `sqlite3_stmt_status` para ver en cuántos pasos de máquina virtual de SQLite se ha compilado una instrucción SQL:</span><span class="sxs-lookup"><span data-stu-id="d2cff-108">And the following example shows calling `sqlite3_stmt_status` to see how many SQLite virtual machine steps a SQL statement compiled into:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_StatementStatus)]

<span data-ttu-id="d2cff-109">Los objetos SQLitePCLRaw incluso exponen un puntero a los objetos nativos que permiten invocar otras API de SQLite nativas.</span><span class="sxs-lookup"><span data-stu-id="d2cff-109">The SQLitePCLRaw objects even expose a pointer to the native objects letting you P/Invoke additional native SQLite APIs.</span></span>
