---
title: Cadenas de conexión
ms.date: 12/13/2019
description: Las palabras clave y los valores admitidos de las cadenas de conexión.
ms.openlocfilehash: bb54d152bac62a86c2a49192cf678a745159164e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450277"
---
# <a name="connection-strings"></a>Cadenas de conexión

Se utiliza una cadena de conexión para especificar cómo conectarse a la base de datos. Las cadenas de conexión de Microsoft. Data. SQLite siguen la sintaxis estándar de [ADO.net](../../../framework/data/adonet/connection-strings.md) como una lista de palabras clave y valores separadas por punto y coma.

## <a name="keywords"></a>Palabras clave

Se pueden usar las siguientes palabras clave de cadena de conexión con Microsoft. Data. SQLite:

### <a name="data-source"></a>Origen de datos

Ruta de acceso al archivo de base de datos. *DataSource* (sin espacio) y *filename* son alias de esta palabra clave.

SQLite trata las rutas de acceso relativas al directorio de trabajo actual. También se pueden especificar rutas de acceso absolutas.

Si **está vacío**, SQLite crea una base de datos temporal en disco que se elimina cuando se cierra la conexión.

Si `:memory:`, se utiliza una base de datos en memoria. Para obtener más información, vea [bases de datos en memoria](in-memory-databases.md).

Las rutas de acceso que comienzan con la cadena de sustitución `|DataDirectory|` se tratan igual que las rutas de acceso relativas. Si se establece, las rutas de acceso se realizan en relación con el valor de propiedad de dominio de aplicación DataDirectory.

Esta palabra clave también admite [nombres de archivo de URI](https://www.sqlite.org/uri.html).

### <a name="mode"></a>Modo

El modo de conexión.

| {2&gt;Value&lt;2}           | Descripción                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------- |
| ReadWriteCreate | Abre la base de datos para lectura y escritura, y la crea si no existe. Esta es la opción predeterminada. |
| ReadWrite       | Abre la base de datos para lectura y escritura.                                                        |
| ReadOnly        | Abre la base de datos en modo de solo lectura.                                                              |
| Memoria          | Abre una base de datos en memoria.                                                                       |

### <a name="cache"></a>instancias y claves

Modo de almacenamiento en caché utilizado por la conexión.

| {2&gt;Value&lt;2}   | Descripción                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------- |
| Predeterminado | Usa el modo predeterminado de la biblioteca de SQLite subyacente. Esta es la opción predeterminada.                   |
| Private | Cada conexión utiliza una caché privada.                                                          |
| Compartido  | Las conexiones comparten una caché. Este modo puede cambiar el comportamiento del bloqueo de transacciones y tablas. |

### <a name="password"></a>Password

La clave de cifrado. Cuando se especifica, `PRAGMA key` se envía inmediatamente después de abrir la conexión.

> [!WARNING]
> La contraseña no tiene ningún efecto cuando la biblioteca de SQLite nativa no admite el cifrado.

### <a name="foreign-keys"></a>Claves externas

Valor que indica si se van a habilitar las restricciones Foreign Key.

| {2&gt;Value&lt;2}   | Descripción
| ------- | --- |
| Verdadero    | Envía `PRAGMA foreign_keys = 1` inmediatamente después de abrir la conexión.
| Falso   | Envía `PRAGMA foreign_keys = 0` inmediatamente después de abrir la conexión.
| (vacío) | No envía `PRAGMA foreign_keys`. Esta es la opción predeterminada. |

No es necesario habilitar las claves externas si, como en e_sqlite3, SQLITE_DEFAULT_FOREIGN_KEYS se usó para compilar la biblioteca nativa de SQLite.

### <a name="recursive-triggers"></a>Desencadenadores recursivos

Valor que indica si se van a habilitar los desencadenadores recursivos.

| {2&gt;Value&lt;2} | Descripción                                                                 |
| ----- | --------------------------------------------------------------------------- |
| Verdadero  | Envía `PRAGMA recursive_triggers` inmediatamente después de abrir la conexión. |
| Falso | No envía `PRAGMA recursive_triggers`. Esta es la opción predeterminada.              |

## <a name="connection-string-builder"></a>Generador de cadenas de conexión

Puede usar <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> como una manera fuertemente tipada de crear cadenas de conexión. También se puede utilizar para evitar ataques de inyección de cadenas de conexión.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="examples"></a>Ejemplos

### <a name="basic"></a>Basic

Una cadena de conexión básica con una memoria caché compartida para mejorar la simultaneidad.

```ConnectionString
Data Source=Application.db;Cache=Shared
```

### <a name="encrypted"></a>Cifrado

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

Una base de datos privada en memoria.

```ConnectionString
Data Source=:memory:
```

### <a name="sharable-in-memory"></a>En memoria que se pueda compartir

Una base de datos en memoria que se pueda compartir y que se identifica mediante el nombre que se pueda *compartir*.

```ConnectionString
Data Source=Sharable;Mode=Memory;Cache=Shared
```

## <a name="see-also"></a>Vea también

* [Cadenas de conexión en ADO.NET](../../../framework/data/adonet/connection-strings.md)
* [Bases de datos en memoria](in-memory-databases.md)
* [Transacciones](transactions.md)
