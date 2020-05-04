---
title: Errores de base de datos
ms.date: 12/13/2019
description: Se describe cómo se controlan en la biblioteca los errores y las retiradas de la base de datos.
ms.openlocfilehash: 9a613b6f94a89dc40e627c14f46836be77080035
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450493"
---
# <a name="database-errors"></a>Errores de base de datos

<xref:Microsoft.Data.Sqlite.SqliteException> se inicia cuando se encuentra un error de SQLite. El mensaje lo proporciona SQLite. Las propiedades `SqliteErrorCode` y `SqliteExtendedErrorCode` contienen el [código de resultado](https://www.sqlite.org/rescode.html) SQLite del error.

Es posible que se produzcan errores cada vez que Microsoft.Data.SQLite interactúe con la biblioteca nativa de SQLite. En la lista siguiente se muestran los escenarios comunes en los que se pueden producir errores:

* Apertura de una conexión.
* Inicio de una transacción.
* Ejecutar un comando.
* Llamada a <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>.

Considere detenidamente cómo controlará la aplicación estos errores.

## <a name="locking-retries-and-timeouts"></a>Bloqueo, reintentos y tiempos de expiración

SQLite es agresivo en lo que respecta al bloqueo de tablas y archivos de base de datos. Si la aplicación habilita el acceso simultáneo a bases de datos, es probable que se produzcan errores de estado ocupado y bloqueado. Puede mitigar muchos errores mediante una [caché compartida](connection-strings.md#cache) y el [registro de escritura anticipada](async.md).

Siempre que Microsoft.Data.SQLite encuentra un error de estado ocupado o bloqueado, realizará reintentos automáticos hasta que se ejecute correctamente o se alcance el tiempo de expiración del comando.

Puede aumentar el tiempo de expiración del comando si establece <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>. El tiempo de expiración predeterminado es de 30 segundos. Un valor de `0` significa que no hay tiempo de expiración.

```csharp
// Retry for 60 seconds while locked
command.CommandTimeout = 60;
```

En ocasiones, Microsoft.Data.SQLitetiene que crear un objeto de comando implícito. Por ejemplo, durante BeginTransaction. Para establecer el tiempo de expiración para estos comandos, use <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>.

```csharp
// Set the default timeout of all commands on this connection
connection.DefaultTimeout = 60;
```

## <a name="see-also"></a>Vea también

* [Códigos de error de SQLite](https://www.sqlite.org/rescode.html)
* [Bloqueo de archivos en SQLite](https://www.sqlite.org/lockingv3.html)
* [Modo de caché compartida](https://www.sqlite.org/sharedcache.html)
* [Registro de escritura anticipada](https://www.sqlite.org/wal.html)
