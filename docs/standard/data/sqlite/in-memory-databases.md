---
title: Bases de datos en memoria
ms.date: 12/13/2019
description: Obtenga información sobre cómo usar las bases de datos de SQLite en memoria.
ms.openlocfilehash: b125ff5aa4128bd4c3ff558c5573b7d11802090a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450469"
---
# <a name="in-memory-databases"></a>Bases de datos en memoria

Las bases de datos en memoria de SQLite son bases de datos almacenadas por completo en la memoria, no en el disco. Use el nombre de archivo de origen de datos Especial `:memory:` para crear una base de datos en memoria. Cuando se cierra la conexión, se elimina la base de datos. Al utilizar `:memory:`, cada conexión crea su propia base de datos.

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a>Bases de datos en memoria que se pueden compartir

Las bases de datos en memoria se pueden compartir entre varias conexiones mediante `Mode=Memory` y `Cache=Shared` en la cadena de conexión. La palabra clave `Data Source` se usa para asignar un nombre a la base de datos en memoria. Las cadenas de conexión que usen el mismo nombre tendrán acceso a la misma base de datos en memoria. La base de datos se conserva siempre y cuando al menos una conexión con ella permanezca abierta. Un [ejemplo](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) que muestra esto está disponible en github.

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
