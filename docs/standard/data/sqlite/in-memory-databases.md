---
title: Bases de datos en memoria
ms.date: 12/13/2019
description: Aprenda a usar bases de datos SQLite en memoria.
ms.openlocfilehash: 408c81f538e27dcfffad20db74b7809912b7905f
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391213"
---
# <a name="in-memory-databases"></a>Bases de datos en memoria

Las bases de datos en memoria de SQLite son bases de datos almacenadas completamente en memoria, no en disco. Utilice el nombre `:memory:` de archivo de origen de datos especial para crear una base de datos en memoria. Cuando se cierra la conexión, se elimina la base de datos. Cuando `:memory:`se utiliza , cada conexión crea su propia base de datos.

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a>Bases de datos en memoria compartibles

Las bases de datos en memoria `Mode=Memory` se `Cache=Shared` pueden compartir entre varias conexiones mediante el uso y la cadena de conexión. La `Data Source` palabra clave se utiliza para asignar un nombre a la base de datos en memoria. Las cadenas de conexión con el mismo nombre tendrán acceso a la misma base de datos en memoria. La base de datos persiste mientras al menos una conexión a ella permanezca abierta. Un [ejemplo](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) que demuestra esto está disponible en GitHub.

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
