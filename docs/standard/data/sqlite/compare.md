---
title: Comparación con System.Data.SQLite
ms.date: 12/13/2019
description: Describe algunas de las diferencias entre las bibliotecas Microsoft.Data.Sqlite y System.Data.Sqlite.
ms.openlocfilehash: 076bbc6f746cf9296c96ec73047397a21a3b2558
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900710"
---
# <a name="comparison-to-systemdatasqlite"></a>Comparación con System.Data.SQLite

En 2005, Robert Simpson creó System.Data.SQLite, un proveedor de SQLite para ADO.NET 2.0. En 2010, el equipo de SQLite se hizo cargo del mantenimiento y el desarrollo del proyecto. También merece la pena mencionar que el equipo de Mono bifurcó el código en 2007 como Mono.Data.Sqlite. System.Data.SQLite tiene un historial largo y ha evolucionado en un proveedor ADO.NET estable y completo con las herramientas de Visual Studio. Las nuevas versiones continúan distribuyendo los ensamblados compatibles con cada versión de .NET Framework hasta la versión 2.0 e incluso .NET Compact Framework 3.5.

La primera versión de .NET Core (publicada en 2016) era una implementación única, ligera, moderna y multiplataforma de .NET. Las API obsoletas y las API con alternativas más modernas se quitaron deliberadamente. ADO.NET no incluyó ninguna de las API de conjunto de datos (como DataTable y DataAdapter).

El equipo de Entity Framework estaba algo familiarizado con el código base System.Data.SQLite. Brice Lambson, miembro del equipo de EF, había ayudado anteriormente al equipo de SQLite a agregar compatibilidad con las versiones 5 y 6 de Entity Framework. Brice también estaba experimentando con su propia implementación de un proveedor de ADO.NET de SQLite más o menos al mismo tiempo en que se planeaba .NET Core. Después de un largo debate, el equipo de Entity Framework decidió crear Microsoft.Data.Sqlite según el prototipo de Brice. Esto les permitiría crear una implementación ligera y moderna que se alinearía con los objetivos de .NET Core.

Como ejemplo de lo que entendemos por más moderno, aquí se incluye el código para crear una [función definida por el usuario](user-defined-functions.md) tanto en System.Data.SQLite como en Microsoft.Data.Sqlite.

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

En 2017, .NET Core 2.0 experimentó un cambio de estrategia. Se decidió que la compatibilidad con .NET Framework era fundamental para el éxito de .NET Core. Muchas de las API que se quitaron, incluidas las API de conjunto de datos, se volvieron a agregar. Como hizo con muchos otros, este System.Data.SQLite desbloqueado permitía que también se portase a .NET Core. Si bien, el objetivo original de Microsoft.Data.Sqlite de que fuera ligero y moderno sigue vigente. Consulte [Limitaciones de ADO.NET](adonet-limitations.md) para más información sobre las API de ADO.NET no implementadas por Microsoft.Data.Sqlite.

Cuando se agregan nuevas características a Microsoft.Data.SQLite, se tiene en cuenta el diseño de System.Data.Sqlite. Se procura, cuando es posible, minimizar los cambios entre ambas para facilitar la transición entre ellas.

## <a name="data-types"></a>Tipos de datos

La diferencia más importante entre Microsoft.Data.Sqlite y System.Data.SQLite es la forma en que se controlan los tipos de datos. Como se describe en [Tipos de datos](types.md), Microsoft.Data.Sqlite no intenta ocultar la peculiaridad subyacente de SQLite, lo que permite especificar cualquier cadena arbitraria como tipo de columna y solo tiene cuatro tipos primitivos: INTEGER, REAL, TEXT y BLOB.

System.Data.SQLite aplica semántica adicional a los tipos de columna que los asignan directamente a los tipos .NET. Esto proporciona al proveedor una mayor sensación de fuertemente tipado, pero tiene algunas asperezas. Por ejemplo, hubo que introducir una nueva instrucción SQL (TYPES) para especificar los tipos de columna de las expresiones en las instrucciones SELECT.

## <a name="connection-strings"></a>Cadenas de conexión

Microsoft.Data.Sqlite tiene muchas menos palabras clave de [cadena de conexión](connection-strings.md). En la tabla siguiente se muestran alternativas que se pueden usar en su lugar.

| Palabra clave          | Alternativa                                         |
| ---------------- | --------------------------------------------------- |
| Tamaño de caché       | Enviar `PRAGMA cache_size = <pages>`                  |
| Tiempo de espera predeterminado  | Usar la propiedad DefaultTimeout en SqliteConnection |
| FailIfMissing    | Use `Mode=ReadWrite`                                |
| FullUri          | Usar la palabra clave de origen de datos                         |
| Modo de diario     | Enviar `PRAGMA journal_mode = <mode>`                 |
| Formato heredado    | Enviar `PRAGMA legacy_file_format = 1`                |
| Número máximo de páginas   | Enviar `PRAGMA max_page_count = <pages>`              |
| Tamaño de página        | Enviar `PRAGMA page_size = <bytes>`                   |
| Solo lectura        | Use `Mode=ReadOnly`                                 |
| Sincrónica      | Enviar `PRAGMA synchronous = <mode>`                  |
| URI              | Usar la palabra clave de origen de datos                         |
| UseUTF16Encoding | Enviar `PRAGMA encoding = 'UTF-16'`                   |

## <a name="authorization"></a>Autorización

Microsoft.Data.Sqlite no tiene ninguna API que exponga la devolución de llamada de autorización de SQLite. Use la incidencia [#13835](https://github.com/dotnet/efcore/issues/13835) para proporcionar comentarios sobre esta característica.

## <a name="data-change-notifications"></a>Notificaciones de cambio de datos

Microsoft.Data.Sqlite no tiene ninguna API que exponga las notificaciones de cambio de datos de SQLite. Use la incidencia [#13827](https://github.com/dotnet/efcore/issues/13827) para proporcionar comentarios sobre esta característica.

## <a name="virtual-table-modules"></a>Módulos de tabla virtual

Microsoft.Data.Sqlite no tiene ninguna API para crear módulos de tabla virtual. Use la incidencia [#13823](https://github.com/dotnet/efcore/issues/13823) para proporcionar comentarios sobre esta característica.

## <a name="see-also"></a>Vea también

* [Tipos de datos](types.md)
* [Cadenas de conexión](connection-strings.md)
* [Cifrado](encryption.md)
* [Limitaciones de ADO.NET](adonet-limitations.md)
* [Limitaciones de Dapper](dapper-limitations.md)
