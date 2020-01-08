---
title: Transacciones
ms.date: 12/13/2019
description: Obtenga información sobre cómo usar las transacciones.
ms.openlocfilehash: 4b72a1573a560ffd1bfd0f54d46ab3b135280976
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450385"
---
# <a name="transactions"></a>Transacciones

Las transacciones le permiten agrupar varias instrucciones SQL en una sola unidad de trabajo que se confirma en la base de datos como una unidad atómica. Si se produce un error en alguna instrucción de la transacción, se pueden revertir los cambios realizados por las instrucciones anteriores. Se conserva el estado inicial de la base de datos cuando se inició la transacción. El uso de una transacción también puede mejorar el rendimiento en SQLite al realizar numerosos cambios en la base de datos a la vez.

## <a name="concurrency"></a>simultaneidad

En SQLite, solo una transacción puede tener cambios pendientes en la base de datos a la vez. Por este motivo, se puede agotar el tiempo de espera de las llamadas a <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> y los métodos de `Execute` en <xref:Microsoft.Data.Sqlite.SqliteCommand> si otra transacción tarda demasiado en completarse.

Para obtener más información sobre el bloqueo, los reintentos y los tiempos de espera, vea [errores de base de datos](database-errors.md).

## <a name="isolation-levels"></a>Niveles de aislamiento

Las transacciones son **serializables** de forma predeterminada en SQLite. Este nivel de aislamiento garantiza que los cambios realizados en una transacción estén completamente aislados. Las demás instrucciones ejecutadas fuera de la transacción no se ven afectadas por los cambios de la transacción.

SQLite también admite la **lectura no confirmada** cuando se usa una memoria caché compartida. Este nivel permite lecturas desfasadas, lecturas no repetibles y fantasmas:

- Una *lectura desfasada* se produce cuando una consulta fuera de la transacción devuelve los cambios pendientes en una transacción, pero se revierten los cambios en la transacción. Los resultados contienen datos que nunca se confirmaron realmente en la base de datos.

- Una *lectura no repetible* se produce cuando una transacción consulta la misma fila dos veces, pero los resultados son diferentes porque se ha cambiado entre las dos consultas por otra transacción.

- Los *fantasmas* son filas que se cambian o se agregan para cumplir la cláusula WHERE de una consulta durante una transacción. Si se permite, la misma consulta podría devolver filas diferentes cuando se ejecutase dos veces en la misma transacción.

Microsoft. Data. SQLite trata el IsolationLevel pasado a <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> como un nivel mínimo. El nivel de aislamiento real se promoverá a Read uncommitd o serializable.

En el código siguiente se simula una lectura desfasada. Tenga en cuenta que la cadena de conexión debe incluir `Cache=Shared`.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DirtyReadSample/Program.cs?name=snippet_DirtyRead)]
