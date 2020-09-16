---
title: Información general
ms.date: 12/13/2019
description: Introducción a Microsoft.Data.Sqlite
ms.openlocfilehash: 7c952848f7e7ea04f11fe9340f77a1f376a1be07
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552445"
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
* [Referencia de API](../../../../api/index.md?view=msdata-sqlite-3.0)
* [Sintaxis de SQL](https://www.sqlite.org/lang.html)
