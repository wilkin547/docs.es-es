---
title: Versiones personalizadas de SQLite
ms.date: 12/13/2019
description: Obtenga información sobre cómo usar una versión personalizada de la biblioteca nativa de SQLite.
ms.openlocfilehash: dd27278c1dbe17b12e5067d04d19043bf259b1e8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746994"
---
# <a name="custom-sqlite-versions"></a><span data-ttu-id="fa201-103">Versiones personalizadas de SQLite</span><span class="sxs-lookup"><span data-stu-id="fa201-103">Custom SQLite versions</span></span>

<span data-ttu-id="fa201-104">Microsoft. Data. SQLite se basa en SQLitePCLRaw.</span><span class="sxs-lookup"><span data-stu-id="fa201-104">Microsoft.Data.Sqlite is built on top of SQLitePCLRaw.</span></span> <span data-ttu-id="fa201-105">Puede usar versiones personalizadas de la biblioteca nativa de SQLite mediante una agrupación o mediante la configuración de un proveedor de SQLitePCLRaw.</span><span class="sxs-lookup"><span data-stu-id="fa201-105">You can use custom versions of the native SQLite library by using a bundle or by configuring a SQLitePCLRaw provider.</span></span>

## <a name="bundles"></a><span data-ttu-id="fa201-106">Agrupaciones</span><span class="sxs-lookup"><span data-stu-id="fa201-106">Bundles</span></span>

<span data-ttu-id="fa201-107">SQLitePCLRaw proporciona paquetes de agrupación que facilitan la inclusión de las dependencias adecuadas en distintas plataformas.</span><span class="sxs-lookup"><span data-stu-id="fa201-107">SQLitePCLRaw provides bundle packages that make it easy to bring in the right dependencies across different platforms.</span></span>

<span data-ttu-id="fa201-108">El paquete principal de Microsoft. Data. SQLite se pone en SQLitePCLRaw. bundle_e_sqlite3 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fa201-108">The main Microsoft.Data.Sqlite package brings in SQLitePCLRaw.bundle_e_sqlite3 by default.</span></span>

<span data-ttu-id="fa201-109">Para usar un paquete diferente, instale en su lugar el paquete de `Microsoft.Data.Sqlite.Core` junto con el paquete de agrupación que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="fa201-109">To use a different bundle, install the `Microsoft.Data.Sqlite.Core` package instead along with the bundle package you want to use.</span></span> <span data-ttu-id="fa201-110">Microsoft. Data. SQLite inicializa automáticamente las agrupaciones.</span><span class="sxs-lookup"><span data-stu-id="fa201-110">Bundles are automatically initialized by Microsoft.Data.Sqlite.</span></span>

| <span data-ttu-id="fa201-111">Lotes</span><span class="sxs-lookup"><span data-stu-id="fa201-111">Bundle</span></span> | <span data-ttu-id="fa201-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa201-112">Description</span></span> |
| --- | --- |
| <span data-ttu-id="fa201-113">SQLitePCLRaw. bundle_e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="fa201-113">SQLitePCLRaw.bundle_e_sqlite3</span></span> | <span data-ttu-id="fa201-114">Proporciona una versión coherente de SQLite en todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="fa201-114">Provides a consistent version of SQLite on all platforms.</span></span> <span data-ttu-id="fa201-115">Incluye las extensiones de árbol FTS4, FTS5, JSON1 y R \*.</span><span class="sxs-lookup"><span data-stu-id="fa201-115">Includes the FTS4, FTS5, JSON1, and R\*Tree extensions.</span></span> <span data-ttu-id="fa201-116">Esta es la opción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fa201-116">This is the default.</span></span> |
| <span data-ttu-id="fa201-117">SQLitePCLRaw. bundle_green</span><span class="sxs-lookup"><span data-stu-id="fa201-117">SQLitePCLRaw.bundle_green</span></span> | <span data-ttu-id="fa201-118">Igual que bundle_e_sqlite3, excepto en iOS donde usa la biblioteca de SQLite del sistema.</span><span class="sxs-lookup"><span data-stu-id="fa201-118">Same as bundle_e_sqlite3, except on iOS where it uses the system SQLite library.</span></span> |
| <span data-ttu-id="fa201-119">SQLitePCLRaw. bundle_zetetic</span><span class="sxs-lookup"><span data-stu-id="fa201-119">SQLitePCLRaw.bundle_zetetic</span></span> | <span data-ttu-id="fa201-120">Usa las compilaciones oficiales de SQLCipher de Zetetic (no se incluye).</span><span class="sxs-lookup"><span data-stu-id="fa201-120">Uses the official SQLCipher builds from Zetetic (not included).</span></span> |
| <span data-ttu-id="fa201-121">SQLitePCLRaw. bundle_winsqlite3</span><span class="sxs-lookup"><span data-stu-id="fa201-121">SQLitePCLRaw.bundle_winsqlite3</span></span> | <span data-ttu-id="fa201-122">Usa winsqlite3. dll, la biblioteca SQLite del sistema en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="fa201-122">Uses winsqlite3.dll, the system SQLite library on Windows 10.</span></span> |
| <span data-ttu-id="fa201-123">SQLitePCLRaw. bundle_e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="fa201-123">SQLitePCLRaw.bundle_e_sqlcipher</span></span> | <span data-ttu-id="fa201-124">Proporciona una compilación no oficial de código abierto de SQLCipher.</span><span class="sxs-lookup"><span data-stu-id="fa201-124">Provides an unofficial, open-source build of SQLCipher.</span></span> |

<span data-ttu-id="fa201-125">Por ejemplo, para usar la compilación de código abierto no oficial de SQLCipher, use los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="fa201-125">For example, to use the unofficial, open-source build of SQLCipher use the following commands.</span></span>

### <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="fa201-126">CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="fa201-126">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="fa201-127">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fa201-127">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a><span data-ttu-id="fa201-128">Proveedores de SQLitePCLRaw</span><span class="sxs-lookup"><span data-stu-id="fa201-128">SQLitePCLRaw providers</span></span>

<span data-ttu-id="fa201-129">Puede usar su propia compilación de SQLite aprovechando el paquete de `SQLitePCLRaw.provider.dynamic_cdecl`.</span><span class="sxs-lookup"><span data-stu-id="fa201-129">You can use your own build of SQLite by leveraging the `SQLitePCLRaw.provider.dynamic_cdecl` package.</span></span> <span data-ttu-id="fa201-130">En este caso, es responsable de implementar la biblioteca nativa con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fa201-130">In this case, you're responsible for deploying the native library with your app.</span></span> <span data-ttu-id="fa201-131">Tenga en cuenta que los detalles de la implementación de bibliotecas nativas con la aplicación varían considerablemente en función de la plataforma .NET y el tiempo de ejecución que esté usando.</span><span class="sxs-lookup"><span data-stu-id="fa201-131">Note, the details of deploying native libraries with your app vary considerably depending on which .NET platform and runtime you're using.</span></span>

<span data-ttu-id="fa201-132">En primer lugar, debe implementar IGetFunctionPointer.</span><span class="sxs-lookup"><span data-stu-id="fa201-132">First, you'll need to implement IGetFunctionPointer.</span></span> <span data-ttu-id="fa201-133">La implementación es bastante trivial en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fa201-133">The implementation is fairly trivial on .NET Core.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

<span data-ttu-id="fa201-134">A continuación, configure el proveedor SQLitePCLRaw.</span><span class="sxs-lookup"><span data-stu-id="fa201-134">Next, configure the SQLitePCLRaw provider.</span></span> <span data-ttu-id="fa201-135">Asegúrese de que esto se realiza antes de que se use Microsoft. Data. SQLite en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fa201-135">Ensure this is done before Microsoft.Data.Sqlite is used in your app.</span></span> <span data-ttu-id="fa201-136">Además, evite usar un paquete de agrupación de SQLitePCLRaw que puede invalidar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="fa201-136">Also, avoid using a SQLitePCLRaw bundle package which might override your provider.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
