---
title: Bulk Insert
ms.date: 12/13/2019
description: Sugerencias de rendimiento que puede usar al realizar numerosos cambios en la base de datos.
ms.openlocfilehash: 9d87d5c8d70f8e70479f9aa02b7802f73b88de9e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450301"
---
# <a name="bulk-insert"></a>Bulk Insert

SQLite no tiene ninguna manera especial de insertar datos de forma masiva. Para obtener un rendimiento óptimo al insertar o actualizar datos, asegúrese de hacer lo siguiente:

- Usar una transacción.
- Vuelva a usar el mismo comando con parámetros. Las ejecuciones posteriores volverán a usar la compilación de la primera.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BulkInsertSample/Program.cs?name=snippet_BulkInsert)]
