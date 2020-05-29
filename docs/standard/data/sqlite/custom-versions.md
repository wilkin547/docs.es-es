---
title: Versiones personalizadas de SQLite
ms.date: 05/14/2020
description: Información sobre cómo usar una versión personalizada de la biblioteca SQLite nativa.
ms.openlocfilehash: 15db10db26bc7c5017313ca020a0e1e528ba207a
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83440842"
---
# <a name="custom-sqlite-versions"></a><span data-ttu-id="7d597-103">Versiones personalizadas de SQLite</span><span class="sxs-lookup"><span data-stu-id="7d597-103">Custom SQLite versions</span></span>

<span data-ttu-id="7d597-104">`Microsoft.Data.Sqlite` se basa en `SQLitePCLRaw`.</span><span class="sxs-lookup"><span data-stu-id="7d597-104">`Microsoft.Data.Sqlite` is built on top of `SQLitePCLRaw`.</span></span> <span data-ttu-id="7d597-105">Se pueden usar versiones personalizadas de la biblioteca SQLite nativa usando una agrupación o configurando un proveedor de `SQLitePCLRaw`.</span><span class="sxs-lookup"><span data-stu-id="7d597-105">You can use custom versions of the native SQLite library by using a bundle or by configuring a `SQLitePCLRaw` provider.</span></span>

## <a name="bundles"></a><span data-ttu-id="7d597-106">Agrupaciones</span><span class="sxs-lookup"><span data-stu-id="7d597-106">Bundles</span></span>

<span data-ttu-id="7d597-107">`SQLitePCLRaw` proporciona paquetes de agrupación prácticos que hacen que sea muy fácil incorporar las dependencias adecuadas en distintas plataformas.</span><span class="sxs-lookup"><span data-stu-id="7d597-107">`SQLitePCLRaw` provides convenience-based bundle packages, that make it easy to bring in the right dependencies across different platforms.</span></span> <span data-ttu-id="7d597-108">De forma predeterminada, el paquete principal de `Microsoft.Data.Sqlite` incluye `SQLitePCLRaw.bundle_e_sqlite3`.</span><span class="sxs-lookup"><span data-stu-id="7d597-108">The main `Microsoft.Data.Sqlite` package brings in `SQLitePCLRaw.bundle_e_sqlite3` by default.</span></span> <span data-ttu-id="7d597-109">Para usar otra agrupación, instale el paquete `Microsoft.Data.Sqlite.Core` en su lugar junto con el paquete de agrupación que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="7d597-109">To use a different bundle, install the `Microsoft.Data.Sqlite.Core` package instead along with the bundle package you want to use.</span></span> <span data-ttu-id="7d597-110">`Microsoft.Data.Sqlite` inicializa las agrupaciones automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7d597-110">Bundles are automatically initialized by `Microsoft.Data.Sqlite`.</span></span>

| <span data-ttu-id="7d597-111">Agrupación</span><span class="sxs-lookup"><span data-stu-id="7d597-111">Bundle</span></span> | <span data-ttu-id="7d597-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d597-112">Description</span></span> |
|--|--|
| [<span data-ttu-id="7d597-113">SQLitePCLRaw.bundle_e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="7d597-113">SQLitePCLRaw.bundle_e_sqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlite3) | <span data-ttu-id="7d597-114">Proporciona la misma versión de SQLite en todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="7d597-114">Provides a consistent version of SQLite on all platforms.</span></span> <span data-ttu-id="7d597-115">Incluye las extensiones FTS4, FTS5, JSON1 y R\*Tree.</span><span class="sxs-lookup"><span data-stu-id="7d597-115">Includes the FTS4, FTS5, JSON1, and R\*Tree extensions.</span></span> <span data-ttu-id="7d597-116">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7d597-116">This is the default.</span></span> |
| [<span data-ttu-id="7d597-117">SQLitePCLRaw.bundle_e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="7d597-117">SQLitePCLRaw.bundle_e_sqlcipher</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlcipher) | <span data-ttu-id="7d597-118">Proporciona una compilación de código abierto no oficial de `SQLCipher`.</span><span class="sxs-lookup"><span data-stu-id="7d597-118">Provides an unofficial, open-source build of `SQLCipher`.</span></span> |
| [<span data-ttu-id="7d597-119">SQLitePCLRaw.bundle_green</span><span class="sxs-lookup"><span data-stu-id="7d597-119">SQLitePCLRaw.bundle_green</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_green) | <span data-ttu-id="7d597-120">Igual que `bundle_e_sqlite3`, salvo en iOS, donde usa la biblioteca SQLite del sistema.</span><span class="sxs-lookup"><span data-stu-id="7d597-120">Same as `bundle_e_sqlite3`, except on iOS where it uses the system SQLite library.</span></span> |
| [<span data-ttu-id="7d597-121">SQLitePCLRaw.bundle_winsqlite3</span><span class="sxs-lookup"><span data-stu-id="7d597-121">SQLitePCLRaw.bundle_winsqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_winsqlite3) | <span data-ttu-id="7d597-122">Usa `winsqlite3.dll`, la biblioteca SQLite del sistema en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="7d597-122">Uses `winsqlite3.dll`, the system SQLite library on Windows 10.</span></span> |
| [<span data-ttu-id="7d597-123">SQLitePCLRaw.bundle_zetetic</span><span class="sxs-lookup"><span data-stu-id="7d597-123">SQLitePCLRaw.bundle_zetetic</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_zetetic) | <span data-ttu-id="7d597-124">Usa las compilaciones de `SQLCipher` oficiales de Zetetic (no se incluye).</span><span class="sxs-lookup"><span data-stu-id="7d597-124">Uses the official `SQLCipher` builds from Zetetic (not included).</span></span> |

<span data-ttu-id="7d597-125">Por ejemplo, para usar la compilación de código abierto no oficial de `SQLCipher`, use los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="7d597-125">For example, to use the unofficial, open-source build of `SQLCipher` use the following commands.</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="7d597-126">CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="7d597-126">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="7d597-127">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7d597-127">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-available-providers"></a><span data-ttu-id="7d597-128">Proveedores de SQLitePCLRaw disponibles</span><span class="sxs-lookup"><span data-stu-id="7d597-128">SQLitePCLRaw available providers</span></span>

<span data-ttu-id="7d597-129">Cuando no se basa en un paquete, puede usar los proveedores disponibles de SQLite con el ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="7d597-129">When not relying on a bundle, you can use the available providers of SQLite with the core assembly.</span></span>

| <span data-ttu-id="7d597-130">Proveedor</span><span class="sxs-lookup"><span data-stu-id="7d597-130">Provider</span></span> | <span data-ttu-id="7d597-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d597-131">Description</span></span> |
|--|--|
| [<span data-ttu-id="7d597-132">SQLitePCLRaw.provider.dynamic</span><span class="sxs-lookup"><span data-stu-id="7d597-132">SQLitePCLRaw.provider.dynamic</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.dynamic) | <span data-ttu-id="7d597-133">El proveedor de `dynamic` carga la biblioteca nativa en lugar de utilizar los atributos de <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7d597-133">The `dynamic` provider loads the native library instead of using <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType> attributes.</span></span> <span data-ttu-id="7d597-134">Para obtener más información sobre el uso de este proveedor, vea el [uso del proveedor dinámico](#use-the-dynamic-provider).</span><span class="sxs-lookup"><span data-stu-id="7d597-134">For more information on using this provider, see [use the dynamic provider](#use-the-dynamic-provider).</span></span> |
| [<span data-ttu-id="7d597-135">SQLitePCLRaw.provider.e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="7d597-135">SQLitePCLRaw.provider.e_sqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlite3) | <span data-ttu-id="7d597-136">`e_sqlite3` es el proveedor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7d597-136">The `e_sqlite3` is the default provider.</span></span> |
| [<span data-ttu-id="7d597-137">SQLitePCLRaw.provider.e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="7d597-137">SQLitePCLRaw.provider.e_sqlcipher</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlcipher) | <span data-ttu-id="7d597-138">El proveedor `e_sqlcipher` es el `SQLCipher` no oficial y no compatible.</span><span class="sxs-lookup"><span data-stu-id="7d597-138">The `e_sqlcipher` provider is the unofficial and unsupported `SQLCipher`.</span></span> |
| [<span data-ttu-id="7d597-139">SQLitePCLRaw.provider.sqlite3</span><span class="sxs-lookup"><span data-stu-id="7d597-139">SQLitePCLRaw.provider.sqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlite3) | <span data-ttu-id="7d597-140">El proveedor `sqlite3` es un elemento `SQLite` proporcionado por el sistema para iOS, macOS y Linux.</span><span class="sxs-lookup"><span data-stu-id="7d597-140">The `sqlite3` provider is a system-provided `SQLite` for iOS, macOS, and Linux.</span></span> |
| [<span data-ttu-id="7d597-141">SQLitePCLRaw.provider.sqlcipher</span><span class="sxs-lookup"><span data-stu-id="7d597-141">SQLitePCLRaw.provider.sqlcipher</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlcipher) | <span data-ttu-id="7d597-142">El proveedor `sqlcipher` es para las compilaciones `SQLCipher` oficiales de `Zetetic`.</span><span class="sxs-lookup"><span data-stu-id="7d597-142">The `sqlcipher` provider is for official `SQLCipher` builds from `Zetetic`.</span></span> |
| [<span data-ttu-id="7d597-143">SQLitePCLRaw.provider.winsqlite3</span><span class="sxs-lookup"><span data-stu-id="7d597-143">SQLitePCLRaw.provider.winsqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.winsqlite3) | <span data-ttu-id="7d597-144">El proveedor `winsqlite3` es para entornos de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="7d597-144">The `winsqlite3` provider is for Windows 10 environments.</span></span> |

<span data-ttu-id="7d597-145">Para usar el proveedor `sqlite3`, use los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="7d597-145">To use the `sqlite3` provider use the following commands:</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="7d597-146">CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="7d597-146">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.core
dotnet add package SQLitePCLRaw.provider.sqlite3
```

### <a name="visual-studio"></a>[<span data-ttu-id="7d597-147">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7d597-147">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.core
Install-Package SQLitePCLRaw.provider.sqlite3
```

---

<span data-ttu-id="7d597-148">Con los paquetes instalados, establezca el proveedor en la instancia de `sqlite3`.</span><span class="sxs-lookup"><span data-stu-id="7d597-148">With the packages installed, you then set the provider to the `sqlite3` instance.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SqliteProviderSample/Program.cs)]

## <a name="use-the-dynamic-provider"></a><span data-ttu-id="7d597-149">Uso del proveedor dinámico</span><span class="sxs-lookup"><span data-stu-id="7d597-149">Use the dynamic provider</span></span>

<span data-ttu-id="7d597-150">Para usar su propia compilación de SQLite, use el paquete `SQLitePCLRaw.provider.dynamic_cdecl`.</span><span class="sxs-lookup"><span data-stu-id="7d597-150">You can use your own build of SQLite by leveraging the `SQLitePCLRaw.provider.dynamic_cdecl` package.</span></span> <span data-ttu-id="7d597-151">En este caso, será su responsabilidad implementar la biblioteca nativa con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d597-151">In this case, you're responsible for deploying the native library with your app.</span></span> <span data-ttu-id="7d597-152">Tenga en cuenta que los detalles de la implementación de bibliotecas nativas con su aplicación variarán considerablemente en función de la plataforma .NET y del runtime que use.</span><span class="sxs-lookup"><span data-stu-id="7d597-152">Note, the details of deploying native libraries with your app vary considerably depending on which .NET platform and runtime you're using.</span></span>

<span data-ttu-id="7d597-153">En primer lugar, deberá implementar `IGetFunctionPointer`.</span><span class="sxs-lookup"><span data-stu-id="7d597-153">First, you'll need to implement `IGetFunctionPointer`.</span></span> <span data-ttu-id="7d597-154">La implementación en .NET Core es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="7d597-154">The implementation on .NET Core is as follows:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

<span data-ttu-id="7d597-155">A continuación, configure el proveedor `SQLitePCLRaw`.</span><span class="sxs-lookup"><span data-stu-id="7d597-155">Next, configure the `SQLitePCLRaw` provider.</span></span> <span data-ttu-id="7d597-156">Asegúrese de llevar esto a cabo antes de que `Microsoft.Data.Sqlite` se use en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d597-156">Ensure this is done before `Microsoft.Data.Sqlite` is used in your app.</span></span> <span data-ttu-id="7d597-157">Evite también usar un paquete de agrupación de `SQLitePCLRaw`, lo que podría invalidar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="7d597-157">Also, avoid using a `SQLitePCLRaw` bundle package which might override your provider.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
