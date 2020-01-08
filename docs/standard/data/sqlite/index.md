---
title: Información general
ms.date: 12/13/2019
description: Introducción a Microsoft.Data.Sqlite
ms.openlocfilehash: a5dc1366cc0ddfcd5501e26bf2a994456bcd5d98
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75353470"
---
# <a name="microsoftdatasqlite-overview"></a><span data-ttu-id="fc8aa-103">Introducción a Microsoft.Data.Sqlite</span><span class="sxs-lookup"><span data-stu-id="fc8aa-103">Microsoft.Data.Sqlite overview</span></span>

<span data-ttu-id="fc8aa-104">Microsoft.Data.Sqlite es un proveedor [ADO.NET](../../../framework/data/adonet/index.md) ligero para SQLite.</span><span class="sxs-lookup"><span data-stu-id="fc8aa-104">Microsoft.Data.Sqlite is a lightweight [ADO.NET](../../../framework/data/adonet/index.md) provider for SQLite.</span></span> <span data-ttu-id="fc8aa-105">El proveedor [Entity Framework Core](/ef/core/) para SQLite se basa en esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="fc8aa-105">The [Entity Framework Core](/ef/core/) provider for SQLite is built on top of this library.</span></span> <span data-ttu-id="fc8aa-106">Sin embargo, también se puede usar de forma independiente o con otras bibliotecas de acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="fc8aa-106">However, it can also be used independently or with other data access libraries.</span></span>

## <a name="installation"></a><span data-ttu-id="fc8aa-107">Instalación</span><span class="sxs-lookup"><span data-stu-id="fc8aa-107">Installation</span></span>

<span data-ttu-id="fc8aa-108">La versión estable más reciente está disponible en [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).</span><span class="sxs-lookup"><span data-stu-id="fc8aa-108">The latest stable version is available on [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).</span></span>

### <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="fc8aa-109">CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="fc8aa-109">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite
```

### <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="fc8aa-110">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fc8aa-110">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite
```

---

## <a name="usage"></a><span data-ttu-id="fc8aa-111">Uso</span><span class="sxs-lookup"><span data-stu-id="fc8aa-111">Usage</span></span>

<span data-ttu-id="fc8aa-112">Esta biblioteca implementa las abstracciones de ADO.NET comunes para conexiones, comandos, lectores de datos, etc.</span><span class="sxs-lookup"><span data-stu-id="fc8aa-112">This library implements the common ADO.NET abstractions for connections, commands, data readers, and so on.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_HelloWorld)]

## <a name="see-also"></a><span data-ttu-id="fc8aa-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc8aa-113">See also</span></span>

* [<span data-ttu-id="fc8aa-114">Cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="fc8aa-114">Connection strings</span></span>](connection-strings.md)
* [<span data-ttu-id="fc8aa-115">Referencia de API</span><span class="sxs-lookup"><span data-stu-id="fc8aa-115">API Reference</span></span>](/dotnet/api/?view=msdata-sqlite-3.0.0)
* [<span data-ttu-id="fc8aa-116">Sintaxis de SQL</span><span class="sxs-lookup"><span data-stu-id="fc8aa-116">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
