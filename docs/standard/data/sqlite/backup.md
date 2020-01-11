---
title: Copia de seguridad en línea
ms.date: 12/13/2019
description: Obtenga información sobre cómo usar la característica de copia de seguridad en línea de SQLite.
ms.openlocfilehash: d857dcb69f2b2d10b034a0abf222b30c2e20bb41
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901282"
---
# <a name="online-backup"></a><span data-ttu-id="281f9-103">Copia de seguridad en línea</span><span class="sxs-lookup"><span data-stu-id="281f9-103">Online backup</span></span>

<span data-ttu-id="281f9-104">SQLite puede realizar copias de seguridad de archivos de base de datos mientras se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="281f9-104">SQLite can back up database files while the app is running.</span></span> <span data-ttu-id="281f9-105">Esta funcionalidad está disponible en Microsoft. Data. SQLite como método <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> en `SqliteConnection`.</span><span class="sxs-lookup"><span data-stu-id="281f9-105">This functionality is available in Microsoft.Data.Sqlite as the <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> method on `SqliteConnection`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

<span data-ttu-id="281f9-106">Actualmente, `BackupDatabase` realizará una copia de seguridad de la base de datos lo más rápidamente posible y bloqueará la escritura de otras conexiones en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="281f9-106">Currently, `BackupDatabase` will back up the database as quickly as possible and blocks other connections from writing to the database.</span></span> <span data-ttu-id="281f9-107">Problema [#13834](https://github.com/dotnet/efcore/issues/13834) proporcionar una API alternativa para realizar una copia de seguridad de la base de datos en segundo plano y permitir que otras conexiones interrumpan la copia de seguridad y escriban en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="281f9-107">Issue [#13834](https://github.com/dotnet/efcore/issues/13834) would provide an alternative API to back up the database in the background and allow other connections to interrupt the backup and write to the database.</span></span> <span data-ttu-id="281f9-108">Si está interesado, proporcione comentarios sobre el problema.</span><span class="sxs-lookup"><span data-stu-id="281f9-108">If you're interested, provide feedback on the issue.</span></span>
