---
title: Comparación con System. Data. SQLite
ms.date: 12/13/2019
description: Describe algunas de las diferencias entre las bibliotecas Microsoft. Data. SQLite y System. Data. SQLite.
ms.openlocfilehash: 076bbc6f746cf9296c96ec73047397a21a3b2558
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900710"
---
# <a name="comparison-to-systemdatasqlite"></a>Comparación con System. Data. SQLite

En 2005, Robert Simpson creó System. Data. SQLite, un proveedor de SQLite para ADO.NET 2,0. En 2010, el equipo de SQLite asumió el mantenimiento y el desarrollo del proyecto. También merece la pena mencionar que el equipo de mono ha bifurcado el código en 2007 como mono. Data. SQLite. System. Data. SQLite tiene un historial largo y ha evolucionado a un proveedor ADO.NET estable y completo con las herramientas de Visual Studio. Las nuevas versiones continúan distribuyendo los ensamblados compatibles con cada versión de .NET Framework de vuelta a la versión 2,0 e incluso .NET Compact Framework 3,5.

La primera versión de .NET Core (Publicada en 2016) era una implementación única, ligera, moderna y multiplataforma de .NET. Las API y API obsoletas con alternativas más modernas se quitaron intencionadamente. ADO.NET no incluyó ninguna de las API de conjunto de los conjuntos de los mismos (incluidos DataTable y DataAdapter).

El equipo de Entity Framework estaba algo familiarizado con el código base System. Data. SQLite. Brice Lambson, miembro del equipo de EF, había ayudado previamente al equipo de SQLite a agregar compatibilidad con las versiones 5 y 6 de Entity Framework. Brice también estaba experimentando con su propia implementación de un proveedor de ADO.NET de SQLite en torno a la misma hora en que se planificó .NET Core. Después de una discusión extensa, el equipo de Entity Framework decidió crear Microsoft. Data. SQLite basado en el prototipo de Brice. Esto les permitiría crear una nueva implementación ligera y moderna que se alinee con los objetivos de .NET Core.

Como ejemplo de lo que se significa en más moderno, este es el código para crear una [función definida por el usuario](user-defined-functions.md) tanto en System. Data. SQLite como en Microsoft. Data. SQLite.

```csharp
// System.Data.SQLite
connection.BindFunction(
    new SQLiteFunctionAttribute("ceiling", 1, FunctionType.Scalar),
    (Func<object[], object>)((object[] args) => Math.Ceiling((double)((object[])args[1])[0])),
    null);

// Microsoft.Data.Sqlite
connection.CreateFunction(
    "ceiling",
    (double arg) => Math.Ceiling(arg));
```

En 2017, .NET Core 2,0 experimentó un cambio en la estrategia. Se decidió que la compatibilidad con .NET Framework era fundamental para el éxito de .NET Core. Muchas de las API eliminadas, incluidas las API de conjunto de datos, se han vuelto a agregar. Al igual que en muchos otros, este sistema desbloqueado System. Data. SQLite permite también pasar a .NET Core. Sin embargo, el objetivo original de Microsoft. Data. SQLite es ligero y moderno. Consulte [limitaciones de ADO.net](adonet-limitations.md) para más información sobre las api de ADO.net no implementadas por Microsoft. Data. SQLite.

Cuando se agregan nuevas características a Microsoft. Data. SQLite, se tiene en cuenta el diseño de System. Data. SQLite. Si es posible, se intentan minimizar los cambios entre ambos para facilitar la transición entre ellos.

## <a name="data-types"></a>Tipos de datos

La diferencia más importante entre Microsoft. Data. SQLite y System. Data. SQLite es cómo se administran los tipos de datos. Como se describe en [tipos de datos](types.md), Microsoft. Data. SQLite no intenta ocultar la peculiaridad subyacente de SQLite, lo que permite especificar cualquier cadena arbitraria como tipo de columna y solo tiene cuatro tipos primitivos: integer, real, Text y BLOB.

System. Data. SQLite aplica la semántica adicional a los tipos de columna que los asignan directamente a los tipos de .NET. Esto proporciona al proveedor una sensación más fuertemente tipada, pero tiene algunos bordes aproximados. Por ejemplo, tenían que introducir una nueva instrucción SQL (tipos) para especificar los tipos de columna de las expresiones en las instrucciones SELECT.

## <a name="connection-strings"></a>Cadenas de conexión

Microsoft. Data. SQLite tiene muchas menos palabras clave de [cadena de conexión](connection-strings.md) . En la tabla siguiente se muestran alternativas que se pueden usar en su lugar.

| Palabra clave          | Alternativa                                         |
| ---------------- | --------------------------------------------------- |
| Tamaño de caché       | Enviar `PRAGMA cache_size = <pages>`                  |
| Tiempo de espera predeterminado  | Usar la propiedad DefaultTimeout en SqliteConnection |
| FailIfMissing    | Use `Mode=ReadWrite`                                |
| FullUri          | Usar la palabra clave de origen de datos                         |
| Modo de diario     | Enviar `PRAGMA journal_mode = <mode>`                 |
| Formato heredado    | Enviar `PRAGMA legacy_file_format = 1`                |
| Número máximo de páginas   | Enviar `PRAGMA max_page_count = <pages>`              |
| Tamaño de página        | Enviar `PRAGMA page_size = <bytes>`                   |
| Sólo lectura        | Use `Mode=ReadOnly`                                 |
| Synchronous      | Enviar `PRAGMA synchronous = <mode>`                  |
| URI              | Usar la palabra clave de origen de datos                         |
| UseUTF16Encoding | Enviar `PRAGMA encoding = 'UTF-16'`                   |

## <a name="authorization"></a>Autorización

Microsoft. Data. SQLite no tiene ninguna API que exponga la devolución de llamada de autorización de SQLite. Use el [#13835](https://github.com/dotnet/efcore/issues/13835) de problemas para proporcionar comentarios sobre esta característica.

## <a name="data-change-notifications"></a>Notificaciones de cambio de datos

Microsoft. Data. SQLite no tiene ninguna API que exponga las notificaciones de cambio de datos de SQLite. Use el [#13827](https://github.com/dotnet/efcore/issues/13827) de problemas para proporcionar comentarios sobre esta característica.

## <a name="virtual-table-modules"></a>Módulos de tabla virtual

Microsoft. Data. SQLite no tiene ninguna API para crear módulos de tabla virtual. Use el [#13823](https://github.com/dotnet/efcore/issues/13823) de problemas para proporcionar comentarios sobre esta característica.

## <a name="see-also"></a>Vea también

* [Tipos de datos](types.md)
* [Cadenas de conexión](connection-strings.md)
* [Cifrado](encryption.md)
* [Limitaciones de ADO.NET](adonet-limitations.md)
* [Limitaciones de Dapper](dapper-limitations.md)
