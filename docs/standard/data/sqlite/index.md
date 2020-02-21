---
title: Información general
ms.date: 12/13/2019
description: Introducción a Microsoft.Data.Sqlite
ms.openlocfilehash: e84c68f0615f187e8dea7ab87ac917c0ad796a1c
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543604"
---
# <a name="microsoftdatasqlite-overview"></a>Introducción a Microsoft.Data.Sqlite

Microsoft.Data.Sqlite es un proveedor [ADO.NET](../../../framework/data/adonet/index.md) ligero para SQLite. El proveedor [Entity Framework Core](/ef/core/) para SQLite se basa en esta biblioteca. Sin embargo, también se puede usar de forma independiente o con otras bibliotecas de acceso a datos.

## <a name="installation"></a>Instalación

La versión estable más reciente está disponible en [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).

### <a name="net-core-cli"></a>[CLI de .NET Core](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite
```

---

## <a name="usage"></a>Uso

Esta biblioteca implementa las abstracciones de ADO.NET comunes para conexiones, comandos, lectores de datos, etc.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_HelloWorld)]

## <a name="see-also"></a>Vea también

* [Cadenas de conexión](connection-strings.md)
* [Referencia de API](/dotnet/api/?view=msdata-sqlite-3.0)
* [Sintaxis de SQL](https://www.sqlite.org/lang.html)
