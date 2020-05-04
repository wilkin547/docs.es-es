---
title: Versiones personalizadas de SQLite
ms.date: 12/13/2019
description: Información sobre cómo usar una versión personalizada de la biblioteca SQLite nativa.
ms.openlocfilehash: dd27278c1dbe17b12e5067d04d19043bf259b1e8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746994"
---
# <a name="custom-sqlite-versions"></a><span data-ttu-id="f3f39-103">Versiones personalizadas de SQLite</span><span class="sxs-lookup"><span data-stu-id="f3f39-103">Custom SQLite versions</span></span>

<span data-ttu-id="f3f39-104">Microsoft.Data.Sqlite se basa en SQLitePCLRaw.</span><span class="sxs-lookup"><span data-stu-id="f3f39-104">Microsoft.Data.Sqlite is built on top of SQLitePCLRaw.</span></span> <span data-ttu-id="f3f39-105">Se pueden usar versiones personalizadas de la biblioteca SQLite nativa usando una agrupación o configurando un proveedor de SQLitePCLRaw.</span><span class="sxs-lookup"><span data-stu-id="f3f39-105">You can use custom versions of the native SQLite library by using a bundle or by configuring a SQLitePCLRaw provider.</span></span>

## <a name="bundles"></a><span data-ttu-id="f3f39-106">Agrupaciones</span><span class="sxs-lookup"><span data-stu-id="f3f39-106">Bundles</span></span>

<span data-ttu-id="f3f39-107">SQLitePCLRaw proporciona paquetes de agrupación que hacen que sea muy fácil incorporar las dependencias adecuadas en distintas plataformas.</span><span class="sxs-lookup"><span data-stu-id="f3f39-107">SQLitePCLRaw provides bundle packages that make it easy to bring in the right dependencies across different platforms.</span></span>

<span data-ttu-id="f3f39-108">El paquete Microsoft.Data.SQLite principal incorpora SQLitePCLRaw.bundle_e_sqlite3 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f3f39-108">The main Microsoft.Data.Sqlite package brings in SQLitePCLRaw.bundle_e_sqlite3 by default.</span></span>

<span data-ttu-id="f3f39-109">Para usar otra agrupación, instale el paquete `Microsoft.Data.Sqlite.Core` en su lugar junto con el paquete de agrupación que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="f3f39-109">To use a different bundle, install the `Microsoft.Data.Sqlite.Core` package instead along with the bundle package you want to use.</span></span> <span data-ttu-id="f3f39-110">Microsoft.Data.Sqlite inicializa las agrupaciones automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f3f39-110">Bundles are automatically initialized by Microsoft.Data.Sqlite.</span></span>

| <span data-ttu-id="f3f39-111">Agrupación</span><span class="sxs-lookup"><span data-stu-id="f3f39-111">Bundle</span></span> | <span data-ttu-id="f3f39-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3f39-112">Description</span></span> |
| --- | --- |
| <span data-ttu-id="f3f39-113">SQLitePCLRaw.bundle_e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="f3f39-113">SQLitePCLRaw.bundle_e_sqlite3</span></span> | <span data-ttu-id="f3f39-114">Proporciona la misma versión de SQLite en todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="f3f39-114">Provides a consistent version of SQLite on all platforms.</span></span> <span data-ttu-id="f3f39-115">Incluye las extensiones FTS4, FTS5, JSON1 y R\*Tree.</span><span class="sxs-lookup"><span data-stu-id="f3f39-115">Includes the FTS4, FTS5, JSON1, and R\*Tree extensions.</span></span> <span data-ttu-id="f3f39-116">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f3f39-116">This is the default.</span></span> |
| <span data-ttu-id="f3f39-117">SQLitePCLRaw.bundle_green</span><span class="sxs-lookup"><span data-stu-id="f3f39-117">SQLitePCLRaw.bundle_green</span></span> | <span data-ttu-id="f3f39-118">Igual que bundle_e_sqlite3, salvo en iOS, donde usa la biblioteca SQLite del sistema.</span><span class="sxs-lookup"><span data-stu-id="f3f39-118">Same as bundle_e_sqlite3, except on iOS where it uses the system SQLite library.</span></span> |
| <span data-ttu-id="f3f39-119">SQLitePCLRaw.bundle_zetetic</span><span class="sxs-lookup"><span data-stu-id="f3f39-119">SQLitePCLRaw.bundle_zetetic</span></span> | <span data-ttu-id="f3f39-120">Usa las compilaciones de SQLCipher oficiales de Zetetic (no se incluye).</span><span class="sxs-lookup"><span data-stu-id="f3f39-120">Uses the official SQLCipher builds from Zetetic (not included).</span></span> |
| <span data-ttu-id="f3f39-121">SQLitePCLRaw.bundle_winsqlite3</span><span class="sxs-lookup"><span data-stu-id="f3f39-121">SQLitePCLRaw.bundle_winsqlite3</span></span> | <span data-ttu-id="f3f39-122">Usa winsqlite3.dll, la biblioteca SQLite del sistema en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f3f39-122">Uses winsqlite3.dll, the system SQLite library on Windows 10.</span></span> |
| <span data-ttu-id="f3f39-123">SQLitePCLRaw.bundle_e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="f3f39-123">SQLitePCLRaw.bundle_e_sqlcipher</span></span> | <span data-ttu-id="f3f39-124">Proporciona una compilación de código abierto no oficial de SQLCipher.</span><span class="sxs-lookup"><span data-stu-id="f3f39-124">Provides an unofficial, open-source build of SQLCipher.</span></span> |

<span data-ttu-id="f3f39-125">Por ejemplo, para usar la compilación de código abierto no oficial de SQLCipher, use los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="f3f39-125">For example, to use the unofficial, open-source build of SQLCipher use the following commands.</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="f3f39-126">CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="f3f39-126">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="f3f39-127">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f3f39-127">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a><span data-ttu-id="f3f39-128">Proveedores de SQLitePCLRaw</span><span class="sxs-lookup"><span data-stu-id="f3f39-128">SQLitePCLRaw providers</span></span>

<span data-ttu-id="f3f39-129">Para usar su propia compilación de SQLite, use el paquete `SQLitePCLRaw.provider.dynamic_cdecl`.</span><span class="sxs-lookup"><span data-stu-id="f3f39-129">You can use your own build of SQLite by leveraging the `SQLitePCLRaw.provider.dynamic_cdecl` package.</span></span> <span data-ttu-id="f3f39-130">En este caso, será su responsabilidad implementar la biblioteca nativa con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f3f39-130">In this case, you're responsible for deploying the native library with your app.</span></span> <span data-ttu-id="f3f39-131">Tenga en cuenta que los detalles de la implementación de bibliotecas nativas con su aplicación variarán considerablemente en función de la plataforma .NET y del runtime que use.</span><span class="sxs-lookup"><span data-stu-id="f3f39-131">Note, the details of deploying native libraries with your app vary considerably depending on which .NET platform and runtime you're using.</span></span>

<span data-ttu-id="f3f39-132">En primer lugar, debe implementar IGetFunctionPointer.</span><span class="sxs-lookup"><span data-stu-id="f3f39-132">First, you'll need to implement IGetFunctionPointer.</span></span> <span data-ttu-id="f3f39-133">La implementación es bastante fácil en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f3f39-133">The implementation is fairly trivial on .NET Core.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

<span data-ttu-id="f3f39-134">Luego, configure el proveedor de SQLitePCLRaw.</span><span class="sxs-lookup"><span data-stu-id="f3f39-134">Next, configure the SQLitePCLRaw provider.</span></span> <span data-ttu-id="f3f39-135">Asegúrese de llevar esto a cabo antes de que Microsoft.Data.SQLite se use en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f3f39-135">Ensure this is done before Microsoft.Data.Sqlite is used in your app.</span></span> <span data-ttu-id="f3f39-136">Evite también usar un paquete de agrupación de SQLitePCLRaw, lo que podría invalidar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="f3f39-136">Also, avoid using a SQLitePCLRaw bundle package which might override your provider.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
