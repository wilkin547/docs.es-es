---
title: Cadenas de conexión
ms.date: 12/13/2019
description: Las palabras clave y los valores admitidos de las cadenas de conexión.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401200"
---
# <a name="connection-strings"></a>Cadenas de conexión

Una cadena de conexión que se usa para especificar cómo conectarse a la base de datos. Las cadenas de conexión de Microsoft.Data.SQLite siguen la [sintaxis de ADO.NET](../../../framework/data/adonet/connection-strings.md) estándar como una lista de palabras clave y valores separados por punto y coma.

## <a name="keywords"></a>Palabras clave

Se pueden usar las palabras clave de cadena de conexión siguientes con Microsoft.Data.SQLite:

### <a name="data-source"></a>Origen de datos

Ruta de acceso al archivo de base de datos. *DataSource* (sin espacio) y *Filename* son alias de esta palabra clave.

SQLite trata las rutas de acceso relativas al directorio de trabajo actual. También se pueden especificar rutas de acceso absolutas.

Si está **vacío**, SQLite crea una base de datos temporal en disco que se elimina al cerrar la conexión.

Si es `:memory:`, se usa una base de datos en memoria. Para más información, vea [Bases de datos en memoria](in-memory-databases.md).

Las rutas de acceso que comienzan con la cadena de sustitución `|DataDirectory|` se tratan igual que las rutas de acceso relativas. Si se establecen, las rutas de acceso son relativas al valor de propiedad de dominio de aplicación DataDirectory.

Esta palabra clave también admite [nombres de archivo de URI](https://www.sqlite.org/uri.html).

### <a name="mode"></a>Modo

Modo de conexión.

| Valor           | Descripción                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| ReadWriteCreate | Abre la base de datos para lectura y escritura, y la crea si no existe. Este es el valor predeterminado. |
| ReadWrite       | Abre la base de datos para lectura y escritura.                                                        |
| ReadOnly        | Abre la base de datos en modo de solo lectura.                                                              |
| Memoria          | Abre una base de datos en memoria.                                                                       |

### <a name="cache"></a>instancias y claves

Modo de almacenamiento en caché que usa la conexión.

| Valor   | Descripción                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| Default | Usa el modo predeterminado de la biblioteca de SQLite subyacente. Este es el valor predeterminado.                   |
| Private | Cada conexión usa una caché privada.                                                          |
| Shared  | Las conexiones comparten una caché. Este modo puede cambiar el comportamiento del bloqueo de transacciones y tablas. |

### <a name="password"></a>Contraseña

La clave de cifrado. Cuando se especifica, `PRAGMA key` se envía inmediatamente después de abrir la conexión.

> [!WARNING]
> La contraseña no tiene ningún efecto cuando la biblioteca de SQLite nativa no admite el cifrado.

### <a name="foreign-keys"></a>Claves externas

Un valor que indica si se deben habilitar restricciones de clave externa.

| Valor   | Descripción
| ------- | --- |
| True    | Se envía `PRAGMA foreign_keys = 1` inmediatamente después de abrir la conexión.
| False   | Se envía `PRAGMA foreign_keys = 0` inmediatamente después de abrir la conexión.
| (vacío) | No se envía `PRAGMA foreign_keys`. Este es el valor predeterminado. |

No es necesario habilitar las claves externas si, como en e_sqlite3, se ha usado SQLITE_DEFAULT_FOREIGN_KEYS para compilar la biblioteca nativa de SQLite.

### <a name="recursive-triggers"></a>Desencadenadores recursivos

Un valor que indica si se van a habilitar los desencadenadores recursivos.

| Valor | Descripción                                                                 |
| ----- | --------------------------------------------------------------------------- |
| True  | Se envía `PRAGMA recursive_triggers` inmediatamente después de abrir la conexión. |
| False | No se envía `PRAGMA recursive_triggers`. Este es el valor predeterminado.              |

## <a name="connection-string-builder"></a>Generador de cadenas de conexión

Puede usar <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> como una manera fuertemente tipada de crear cadenas de conexión. También se pueda usar para evitar ataques de inyección de cadenas de conexión.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a>Ejemplos

### <a name="basic"></a>Básico

Una cadena de conexión básica con una memoria caché compartida para mejorar la simultaneidad.

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a>Cifrados

Una base de datos cifrada.

```ConnectionString
Data Source=Encrypted.db;Password=MyEncryptionKey
```

### <a name="read-only"></a>De sólo lectura

Una base de datos de solo lectura que la aplicación no puede modificar.

```ConnectionString
Data Source=Reference.db;Mode=ReadOnly
```

### <a name="in-memory"></a>En memoria

Una base de datos en memoria privada.

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a>En memoria que se pueda compartir

Una base de datos en memoria que se puede compartir y que se identifica mediante el nombre *Compartible*.

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a>Vea también

* [Cadenas de conexión de ADO.NET](../../../framework/data/adonet/connection-strings.md)
* [Bases de datos en memoria](in-memory-databases.md)
* [Transacciones](transactions.md)
