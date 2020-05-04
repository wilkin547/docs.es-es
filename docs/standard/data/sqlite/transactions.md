---
title: Transacciones
ms.date: 12/13/2019
description: Obtenga información sobre cómo usar las transacciones.
ms.openlocfilehash: 4b72a1573a560ffd1bfd0f54d46ab3b135280976
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450385"
---
# <a name="transactions"></a>Transacciones

Las transacciones permiten agrupar varias instrucciones SQL en una misma unidad de trabajo que se confirma en la base de datos como una unidad atómica. Si se produce un error en una instrucción de la transacción, los cambios realizados por las instrucciones anteriores se pueden revertir. Se conservará el estado inicial de la base de datos cuando se inició la transacción. El uso de una transacción también puede mejorar el rendimiento en SQLite cuando se realizan varios cambios en la base de datos a la vez.

## <a name="concurrency"></a>simultaneidad

En SQLite, solo una transacción puede tener cambios pendientes en la base de datos en un momento determinado. Por este motivo, el tiempo de espera de las llamadas a los métodos <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> y `Execute` en <xref:Microsoft.Data.Sqlite.SqliteCommand> se puede agotar si otra transacción tarda demasiado en completarse.

Para más información sobre los bloqueos, los reintentos y los tiempos de espera, vea [Errores de base de datos](database-errors.md).

## <a name="isolation-levels"></a>Niveles de aislamiento

Las transacciones se **serializan** de forma predeterminada en SQLite. Este nivel de aislamiento garantiza que los cambios realizados en una transacción estén completamente aislados. El resto de instrucciones ejecutadas fuera de la transacción no se verán afectadas por los cambios de la transacción.

SQLite también admite la **lectura no confirmada** cuando se usa una memoria caché compartida. Este nivel permite lecturas de datos sucios, lecturas no repetibles y filas fantasma:

- Una *lectura de datos sucios* es aquella que se produce cuando una consulta fuera de la transacción devuelve los cambios pendientes de una transacción, pero esos cambios en la transacción se revierten. Los resultados contienen datos que nunca se confirmaron realmente en la base de datos.

- Una *lectura no repetible* es aquella que se produce cuando una transacción consulta la misma fila dos veces, pero los resultados son diferentes porque otra transacción cambió la fila entre una consulta y la otra.

- Las *filas fantasma* son filas que se cambian o se agregan para cumplir la cláusula WHERE de una consulta durante una transacción. Si se permite, la misma consulta podría devolver filas diferentes si se ejecutase dos veces en la misma transacción.

Microsoft.Data.Sqlite trata el nivel IsolationLevel pasado a <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> como el nivel mínimo. El nivel de aislamiento real subirá a lectura no confirmada o serializable.

En el siguiente código se simula una lectura de datos sucios. Fíjese en que la cadena de conexión debe incluir `Cache=Shared`.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DirtyReadSample/Program.cs?name=snippet_DirtyRead)]
