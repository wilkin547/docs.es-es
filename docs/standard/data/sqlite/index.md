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
# <a name="microsoftdatasqlite-overview"></a><span data-ttu-id="012a0-103">Introducción a Microsoft.Data.Sqlite</span><span class="sxs-lookup"><span data-stu-id="012a0-103">Microsoft.Data.Sqlite overview</span></span>

<span data-ttu-id="012a0-104">Microsoft.Data.Sqlite es un proveedor [ADO.NET](../../../framework/data/adonet/index.md) ligero para SQLite.</span><span class="sxs-lookup"><span data-stu-id="012a0-104">Microsoft.Data.Sqlite is a lightweight [ADO.NET](../../../framework/data/adonet/index.md) provider for SQLite.</span></span> <span data-ttu-id="012a0-105">El proveedor [Entity Framework Core](/ef/core/) para SQLite se basa en esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="012a0-105">The [Entity Framework Core](/ef/core/) provider for SQLite is built on top of this library.</span></span> <span data-ttu-id="012a0-106">Sin embargo, también se puede usar de forma independiente o con otras bibliotecas de acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="012a0-106">However, it can also be used independently or with other data access libraries.</span></span>

## <a name="installation"></a><span data-ttu-id="012a0-107">Instalación</span><span class="sxs-lookup"><span data-stu-id="012a0-107">Installation</span></span>

<span data-ttu-id="012a0-108">La versión estable más reciente está disponible en [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).</span><span class="sxs-lookup"><span data-stu-id="012a0-108">The latest stable version is available on [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="012a0-109">CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="012a0-109">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite
```

### <a name="visual-studio"></a>[<span data-ttu-id="012a0-110">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="012a0-110">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite
```

---

## <a name="usage"></a><span data-ttu-id="012a0-111">Uso</span><span class="sxs-lookup"><span data-stu-id="012a0-111">Usage</span></span>

<span data-ttu-id="012a0-112">Esta biblioteca implementa las abstracciones de ADO.NET comunes para conexiones, comandos, lectores de datos, etc.</span><span class="sxs-lookup"><span data-stu-id="012a0-112">This library implements the common ADO.NET abstractions for connections, commands, data readers, and so on.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_HelloWorld)]

## <a name="see-also"></a><span data-ttu-id="012a0-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="012a0-113">See also</span></span>

* [<span data-ttu-id="012a0-114">Cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="012a0-114">Connection strings</span></span>](connection-strings.md)
* [<span data-ttu-id="012a0-115">Referencia de API</span><span class="sxs-lookup"><span data-stu-id="012a0-115">API Reference</span></span>](../../../../api/index.md?view=msdata-sqlite-3.0)
* [<span data-ttu-id="012a0-116">Sintaxis de SQL</span><span class="sxs-lookup"><span data-stu-id="012a0-116">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
