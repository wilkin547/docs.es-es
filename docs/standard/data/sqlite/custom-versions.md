---
title: Versiones personalizadas de SQLite
ms.date: 12/13/2019
description: Obtenga información sobre cómo usar una versión personalizada de la biblioteca nativa de SQLite.
ms.openlocfilehash: 8a2646138ea9dbecf412a2e8e0e347e2d71a5b0b
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450391"
---
# <a name="custom-sqlite-versions"></a><span data-ttu-id="26e54-103">Versiones personalizadas de SQLite</span><span class="sxs-lookup"><span data-stu-id="26e54-103">Custom SQLite versions</span></span>

<span data-ttu-id="26e54-104">Microsoft. Data. SQLite se basa en SQLitePCLRaw.</span><span class="sxs-lookup"><span data-stu-id="26e54-104">Microsoft.Data.Sqlite is built on top of SQLitePCLRaw.</span></span> <span data-ttu-id="26e54-105">Puede usar versiones personalizadas de la biblioteca nativa de SQLite mediante una agrupación o mediante la configuración de un proveedor de SQLitePCLRaw.</span><span class="sxs-lookup"><span data-stu-id="26e54-105">You can use custom versions of the native SQLite library by using a bundle or by configuring a SQLitePCLRaw provider.</span></span>

## <a name="bundles"></a><span data-ttu-id="26e54-106">Agrupaciones</span><span class="sxs-lookup"><span data-stu-id="26e54-106">Bundles</span></span>

<span data-ttu-id="26e54-107">SQLitePCLRaw proporciona paquetes de agrupación que facilitan la inclusión de las dependencias adecuadas en distintas plataformas.</span><span class="sxs-lookup"><span data-stu-id="26e54-107">SQLitePCLRaw provides bundle packages that make it easy to bring in the right dependencies across different platforms.</span></span>

<span data-ttu-id="26e54-108">El paquete principal de Microsoft. Data. SQLite se pone en SQLitePCLRaw. bundle_e_sqlite3 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="26e54-108">The main Microsoft.Data.Sqlite package brings in SQLitePCLRaw.bundle_e_sqlite3 by default.</span></span>

<span data-ttu-id="26e54-109">Para usar un paquete diferente, instale en su lugar el paquete de `Microsoft.Data.Sqlite.Core` junto con el paquete de agrupación que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="26e54-109">To use a different bundle, install the `Microsoft.Data.Sqlite.Core` package instead along with the bundle package you want to use.</span></span> <span data-ttu-id="26e54-110">Microsoft. Data. SQLite inicializa automáticamente las agrupaciones.</span><span class="sxs-lookup"><span data-stu-id="26e54-110">Bundles are automatically initialized by Microsoft.Data.Sqlite.</span></span>

| <span data-ttu-id="26e54-111">Agrupación</span><span class="sxs-lookup"><span data-stu-id="26e54-111">Bundle</span></span> | <span data-ttu-id="26e54-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="26e54-112">Description</span></span> |
| --- | --- |
| <span data-ttu-id="26e54-113">SQLitePCLRaw. bundle_e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="26e54-113">SQLitePCLRaw.bundle_e_sqlite3</span></span> | <span data-ttu-id="26e54-114">Proporciona una versión coherente de SQLite en todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="26e54-114">Provides a consistent version of SQLite on all platforms.</span></span> <span data-ttu-id="26e54-115">Incluye FTS4, FTS5, JSON1 y</span><span class="sxs-lookup"><span data-stu-id="26e54-115">Includes the FTS4, FTS5, JSON1, and</span></span> | <span data-ttu-id="26e54-116">Extensiones de árbol de R \*.</span><span class="sxs-lookup"><span data-stu-id="26e54-116">R\*Tree extensions.</span></span> <span data-ttu-id="26e54-117">Esta es la opción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="26e54-117">This is the default.</span></span> |
| <span data-ttu-id="26e54-118">SQLitePCLRaw. bundle_green</span><span class="sxs-lookup"><span data-stu-id="26e54-118">SQLitePCLRaw.bundle_green</span></span> | <span data-ttu-id="26e54-119">Igual que bundle_e_sqlite3, excepto en iOS donde usa la biblioteca de SQLite del sistema.</span><span class="sxs-lookup"><span data-stu-id="26e54-119">Same as bundle_e_sqlite3, except on iOS where it uses the system SQLite library.</span></span> |
| <span data-ttu-id="26e54-120">SQLitePCLRaw. bundle_zetetic</span><span class="sxs-lookup"><span data-stu-id="26e54-120">SQLitePCLRaw.bundle_zetetic</span></span> | <span data-ttu-id="26e54-121">Usa las compilaciones oficiales de SQLCipher de Zetetic (no se incluye).</span><span class="sxs-lookup"><span data-stu-id="26e54-121">Uses the official SQLCipher builds from Zetetic (not included).</span></span> |
| <span data-ttu-id="26e54-122">SQLitePCLRaw. bundle_winsqlite3</span><span class="sxs-lookup"><span data-stu-id="26e54-122">SQLitePCLRaw.bundle_winsqlite3</span></span> | <span data-ttu-id="26e54-123">Usa winsqlite3. dll, la biblioteca SQLite del sistema en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="26e54-123">Uses winsqlite3.dll, the system SQLite library on Windows 10.</span></span> |
| <span data-ttu-id="26e54-124">SQLitePCLRaw. bundle_e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="26e54-124">SQLitePCLRaw.bundle_e_sqlcipher</span></span> | <span data-ttu-id="26e54-125">Proporciona una compilación no oficial de código abierto de SQLCipher.</span><span class="sxs-lookup"><span data-stu-id="26e54-125">Provides an unofficial, open-source build of SQLCipher.</span></span> |

<span data-ttu-id="26e54-126">Por ejemplo, para usar la compilación de código abierto no oficial de SQLCipher, use los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="26e54-126">For example, to use the unofficial, open-source build of SQLCipher use the following commands.</span></span>

### <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="26e54-127">CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="26e54-127">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="26e54-128">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="26e54-128">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a><span data-ttu-id="26e54-129">Proveedores de SQLitePCLRaw</span><span class="sxs-lookup"><span data-stu-id="26e54-129">SQLitePCLRaw providers</span></span>

<span data-ttu-id="26e54-130">Puede usar su propia compilación de SQLite aprovechando el paquete de `SQLitePCLRaw.provider.dynamic_cdecl`.</span><span class="sxs-lookup"><span data-stu-id="26e54-130">You can use your own build of SQLite by leveraging the `SQLitePCLRaw.provider.dynamic_cdecl` package.</span></span> <span data-ttu-id="26e54-131">En este caso, es responsable de implementar la biblioteca nativa con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="26e54-131">In this case, you're responsible for deploying the native library with your app.</span></span> <span data-ttu-id="26e54-132">Tenga en cuenta que los detalles de la implementación de bibliotecas nativas con la aplicación varían considerablemente en función de la plataforma .NET y el tiempo de ejecución que esté usando.</span><span class="sxs-lookup"><span data-stu-id="26e54-132">Note, the details of deploying native libraries with your app vary considerably depending on which .NET platform and runtime you're using.</span></span>

<span data-ttu-id="26e54-133">En primer lugar, debe implementar IGetFunctionPointer.</span><span class="sxs-lookup"><span data-stu-id="26e54-133">First, you'll need to implement IGetFunctionPointer.</span></span> <span data-ttu-id="26e54-134">La implementación es bastante trivial en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="26e54-134">The implementation is fairly trivial on .NET Core.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

<span data-ttu-id="26e54-135">A continuación, configure el proveedor SQLitePCLRaw.</span><span class="sxs-lookup"><span data-stu-id="26e54-135">Next, configure the SQLitePCLRaw provider.</span></span> <span data-ttu-id="26e54-136">Asegúrese de que esto se realiza antes de que se use Microsoft. Data. SQLite en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="26e54-136">Ensure this is done before Microsoft.Data.Sqlite is used in your app.</span></span> <span data-ttu-id="26e54-137">Además, evite usar un paquete de agrupación de SQLitePCLRaw que puede invalidar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="26e54-137">Also, avoid using a SQLitePCLRaw bundle package which might override your provider.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
