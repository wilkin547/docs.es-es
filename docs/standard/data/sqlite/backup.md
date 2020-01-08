---
title: Copia de seguridad en línea
ms.date: 12/13/2019
description: Obtenga información sobre cómo usar la característica de copia de seguridad en línea de SQLite.
ms.openlocfilehash: 885aa2c5555b58deb2551c0a4e6933742a093457
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450349"
---
# <a name="online-backup"></a><span data-ttu-id="7085a-103">Copia de seguridad en línea</span><span class="sxs-lookup"><span data-stu-id="7085a-103">Online backup</span></span>

<span data-ttu-id="7085a-104">SQLite puede realizar copias de seguridad de archivos de base de datos mientras se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7085a-104">SQLite can back up database files while the app is running.</span></span> <span data-ttu-id="7085a-105">Esta funcionalidad está disponible en Microsoft. Data. SQLite como método <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> en `SqliteConnection`.</span><span class="sxs-lookup"><span data-stu-id="7085a-105">This functionality is available in Microsoft.Data.Sqlite as the <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> method on `SqliteConnection`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

<span data-ttu-id="7085a-106">Actualmente, `BackupDatabase` realizará una copia de seguridad de la base de datos lo más rápidamente posible y bloqueará la escritura de otras conexiones en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7085a-106">Currently, `BackupDatabase` will back up the database as quickly as possible and blocks other connections from writing to the database.</span></span> <span data-ttu-id="7085a-107">Problema [#13834](https://github.com/aspnet/EntityFrameworkCore/issues/13834) proporcionar una API alternativa para realizar una copia de seguridad de la base de datos en segundo plano y permitir que otras conexiones interrumpan la copia de seguridad y escriban en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7085a-107">Issue [#13834](https://github.com/aspnet/EntityFrameworkCore/issues/13834) would provide an alternative API to back up the database in the background and allow other connections to interrupt the backup and write to the database.</span></span> <span data-ttu-id="7085a-108">Si está interesado, proporcione comentarios sobre el problema.</span><span class="sxs-lookup"><span data-stu-id="7085a-108">If you're interested, provide feedback on the issue.</span></span>
