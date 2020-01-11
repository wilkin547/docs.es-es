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
# <a name="online-backup"></a>Copia de seguridad en línea

SQLite puede realizar copias de seguridad de archivos de base de datos mientras se ejecuta la aplicación. Esta funcionalidad está disponible en Microsoft. Data. SQLite como método <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> en `SqliteConnection`.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

Actualmente, `BackupDatabase` realizará una copia de seguridad de la base de datos lo más rápidamente posible y bloqueará la escritura de otras conexiones en la base de datos. Problema [#13834](https://github.com/dotnet/efcore/issues/13834) proporcionar una API alternativa para realizar una copia de seguridad de la base de datos en segundo plano y permitir que otras conexiones interrumpan la copia de seguridad y escriban en la base de datos. Si está interesado, proporcione comentarios sobre el problema.
