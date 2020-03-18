---
title: Información general
ms.date: 12/13/2019
description: Introducción a Microsoft.Data.Sqlite
ms.openlocfilehash: e84c68f0615f187e8dea7ab87ac917c0ad796a1c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "77543604"
---
# <a name="microsoftdatasqlite-overview"></a><span data-ttu-id="eb261-103">Introducción a Microsoft.Data.Sqlite</span><span class="sxs-lookup"><span data-stu-id="eb261-103">Microsoft.Data.Sqlite overview</span></span>

<span data-ttu-id="eb261-104">Microsoft.Data.Sqlite es un proveedor [ADO.NET](../../../framework/data/adonet/index.md) ligero para SQLite.</span><span class="sxs-lookup"><span data-stu-id="eb261-104">Microsoft.Data.Sqlite is a lightweight [ADO.NET](../../../framework/data/adonet/index.md) provider for SQLite.</span></span> <span data-ttu-id="eb261-105">El proveedor [Entity Framework Core](/ef/core/) para SQLite se basa en esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="eb261-105">The [Entity Framework Core](/ef/core/) provider for SQLite is built on top of this library.</span></span> <span data-ttu-id="eb261-106">Sin embargo, también se puede usar de forma independiente o con otras bibliotecas de acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="eb261-106">However, it can also be used independently or with other data access libraries.</span></span>

## <a name="installation"></a><span data-ttu-id="eb261-107">Instalación</span><span class="sxs-lookup"><span data-stu-id="eb261-107">Installation</span></span>

<span data-ttu-id="eb261-108">La versión estable más reciente está disponible en [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).</span><span class="sxs-lookup"><span data-stu-id="eb261-108">The latest stable version is available on [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="eb261-109">CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="eb261-109">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite
```

### <a name="visual-studio"></a>[<span data-ttu-id="eb261-110">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="eb261-110">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite
```

---

## <a name="usage"></a><span data-ttu-id="eb261-111">Uso</span><span class="sxs-lookup"><span data-stu-id="eb261-111">Usage</span></span>

<span data-ttu-id="eb261-112">Esta biblioteca implementa las abstracciones de ADO.NET comunes para conexiones, comandos, lectores de datos, etc.</span><span class="sxs-lookup"><span data-stu-id="eb261-112">This library implements the common ADO.NET abstractions for connections, commands, data readers, and so on.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_HelloWorld)]

## <a name="see-also"></a><span data-ttu-id="eb261-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb261-113">See also</span></span>

* [<span data-ttu-id="eb261-114">Cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="eb261-114">Connection strings</span></span>](connection-strings.md)
* [<span data-ttu-id="eb261-115">Referencia de API</span><span class="sxs-lookup"><span data-stu-id="eb261-115">API Reference</span></span>](/dotnet/api/?view=msdata-sqlite-3.0)
* [<span data-ttu-id="eb261-116">Sintaxis de SQL</span><span class="sxs-lookup"><span data-stu-id="eb261-116">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
