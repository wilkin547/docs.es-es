---
title: 'Comprobación de las versiones de .NET Core instaladas en Windows, Linux y macOS: .NET Core'
description: Obtenga información sobre cómo mostrar las versiones de .NET Core que están instaladas en el equipo. Esto incluye el entorno de ejecución y el SDK de .NET Core.
author: adegeo
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: cc4d9c6a366cd0e5da4c3446536c93efdc9f5503
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324820"
---
# <a name="how-to-check-that-net-core-is-already-installed"></a><span data-ttu-id="cd1aa-104">Cómo comprobar que .NET Core ya está instalado</span><span class="sxs-lookup"><span data-stu-id="cd1aa-104">How to check that .NET Core is already installed</span></span>

<span data-ttu-id="cd1aa-105">En este artículo se explica cómo comprobar las versiones del entorno de ejecución y el SDK de .NET Core que están instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="cd1aa-105">This article teaches you how to check which versions of the .NET Core runtime and SDK are installed on your computer.</span></span> <span data-ttu-id="cd1aa-106">Es posible que .NET Core ya se haya instalado si tiene un entorno de desarrollo integrado, como Visual Studio o Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="cd1aa-106">.NET core may have already been installed if you have an integrated development environment, such as Visual Studio or Visual Studio for Mac.</span></span>

<span data-ttu-id="cd1aa-107">Al instalar un SDK, se instala el entorno de ejecución correspondiente.</span><span class="sxs-lookup"><span data-stu-id="cd1aa-107">Installing an SDK installs the corresponding runtime.</span></span>

<span data-ttu-id="cd1aa-108">Si se produce un error en alguno de los comandos de este artículo, no tendrá instalado el entorno de ejecución o el SDK.</span><span class="sxs-lookup"><span data-stu-id="cd1aa-108">If any command in this article fails, you don't have the runtime or SDK installed.</span></span> <span data-ttu-id="cd1aa-109">Para obtener más información, vea [Descarga e instalación de .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="cd1aa-109">For more information, see [Download and install .NET Core](index.md).</span></span>

## <a name="check-sdk-versions"></a><span data-ttu-id="cd1aa-110">Comprobación de las versiones del SDK</span><span class="sxs-lookup"><span data-stu-id="cd1aa-110">Check SDK versions</span></span>

<span data-ttu-id="cd1aa-111">Se pueden ver las versiones del SDK de .NET Core que están instaladas actualmente con un terminal.</span><span class="sxs-lookup"><span data-stu-id="cd1aa-111">You can see which versions of the .NET Core SDK are currently installed with a terminal.</span></span> <span data-ttu-id="cd1aa-112">Abra un terminal y ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="cd1aa-112">Open a terminal and run the following command.</span></span>

```dotnetcli
dotnet --list-sdks
```

<span data-ttu-id="cd1aa-113">Verá un resultado similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="cd1aa-113">You get output similar to the following.</span></span>

::: zone pivot="os-windows"

```console
2.1.500 [C:\program files\dotnet\sdk]
2.1.502 [C:\program files\dotnet\sdk]
2.1.504 [C:\program files\dotnet\sdk]
2.1.600 [C:\program files\dotnet\sdk]
2.1.602 [C:\program files\dotnet\sdk]
2.2.101 [C:\program files\dotnet\sdk]
3.0.100 [C:\program files\dotnet\sdk]
3.1.100 [C:\program files\dotnet\sdk]
```

::: zone-end

::: zone pivot="os-linux"

```bash
2.1.500 [/home/user/dotnet/sdk]
2.1.502 [/home/user/dotnet/sdk]
2.1.504 [/home/user/dotnet/sdk]
2.1.600 [/home/user/dotnet/sdk]
2.1.602 [/home/user/dotnet/sdk]
2.2.101 [/home/user/dotnet/sdk]
3.0.100 [/home/user/dotnet/sdk]
3.1.100 [/home/user/dotnet/sdk]
```

::: zone-end

::: zone pivot="os-macos"

```bash
2.1.500 [/usr/local/share/dotnet/sdk]
2.1.502 [/usr/local/share/dotnet/sdk]
2.1.504 [/usr/local/share/dotnet/sdk]
2.1.600 [/usr/local/share/dotnet/sdk]
2.1.602 [/usr/local/share/dotnet/sdk]
2.2.101 [/usr/local/share/dotnet/sdk]
3.0.100 [/usr/local/share/dotnet/sdk]
3.1.100 [/usr/local/share/dotnet/sdk]
```

::: zone-end

## <a name="check-runtime-versions"></a><span data-ttu-id="cd1aa-114">Comprobación de las versiones del entorno de ejecución</span><span class="sxs-lookup"><span data-stu-id="cd1aa-114">Check runtime versions</span></span>

<span data-ttu-id="cd1aa-115">Se pueden ver las versiones del entorno de ejecución de .NET Core que están instaladas actualmente con el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="cd1aa-115">You can see which versions of the .NET Core runtime are currently installed with the following command.</span></span>

```dotnetcli
dotnet --list-runtimes
```

<span data-ttu-id="cd1aa-116">Verá un resultado similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="cd1aa-116">You get output similar to the following.</span></span>

::: zone pivot="os-windows"

```console
Microsoft.AspNetCore.All 2.1.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.3 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.6 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.3 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.7 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.WindowsDesktop.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
Microsoft.WindowsDesktop.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
```

::: zone-end

::: zone pivot="os-linux"

```bash
Microsoft.AspNetCore.All 2.1.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.3 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.6 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.0.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.3 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.7 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.0.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
```

::: zone-end

::: zone pivot="os-macos"

```bash
Microsoft.AspNetCore.All 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.3 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.6 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.0.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.3 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.7 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.0.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
```

::: zone-end

## <a name="check-for-install-folders"></a><span data-ttu-id="cd1aa-117">Buscar carpetas de instalación</span><span class="sxs-lookup"><span data-stu-id="cd1aa-117">Check for install folders</span></span>

<span data-ttu-id="cd1aa-118">Es posible que .NET Core esté instalado pero no se haya agregado a la variable `PATH` del sistema operativo o el perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="cd1aa-118">It's possible that .NET Core is installed but not added to the `PATH` variable for your operating system or user profile.</span></span> <span data-ttu-id="cd1aa-119">Es posible que no funcione la ejecución de los comandos de las secciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="cd1aa-119">Running the commands from the previous sections may not work.</span></span> <span data-ttu-id="cd1aa-120">Como alternativa, puede comprobar que existen las carpetas de instalación de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cd1aa-120">As an alternative, you can check that the .NET Core install folders exist.</span></span>

<span data-ttu-id="cd1aa-121">Al instalar .NET Core desde un instalador o un script, se instala en una carpeta estándar.</span><span class="sxs-lookup"><span data-stu-id="cd1aa-121">When you install .NET Core from an installer or script, it's installed to a standard folder.</span></span> <span data-ttu-id="cd1aa-122">La mayor parte del tiempo, el instalador o el script que usa para instalar .NET Core le ofrece la opción de instalar en una carpeta diferente.</span><span class="sxs-lookup"><span data-stu-id="cd1aa-122">Much of the time the installer or script you're using to install .NET Core gives you an option to install to a different folder.</span></span> <span data-ttu-id="cd1aa-123">Si decide instalar en una carpeta diferente, ajuste el inicio de la ruta de acceso de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="cd1aa-123">If you choose to install to a different folder, adjust the start of the folder path.</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="cd1aa-124">**archivo ejecutable de dotnet**</span><span class="sxs-lookup"><span data-stu-id="cd1aa-124">**dotnet executable**</span></span>\
<span data-ttu-id="cd1aa-125">_C:\\archivos de programa\\dotnet\\dotnet.exe_</span><span class="sxs-lookup"><span data-stu-id="cd1aa-125">_C:\\program files\\dotnet\\dotnet.exe_</span></span>

- <span data-ttu-id="cd1aa-126">**.NET SDK**</span><span class="sxs-lookup"><span data-stu-id="cd1aa-126">**.NET SDK**</span></span>\
<span data-ttu-id="cd1aa-127">_C:\\archivos de programa\\dotnet\\sdk\\{versión}\\_</span><span class="sxs-lookup"><span data-stu-id="cd1aa-127">_C:\\program files\\dotnet\\sdk\\{version}\\_</span></span>

- <span data-ttu-id="cd1aa-128">**Runtime de .NET**</span><span class="sxs-lookup"><span data-stu-id="cd1aa-128">**.NET Runtime**</span></span>\
<span data-ttu-id="cd1aa-129">_C:\\archivos de programa\\dotnet\\shared\\{tipo de runtime}\\{versión}\\_</span><span class="sxs-lookup"><span data-stu-id="cd1aa-129">_C:\\program files\\dotnet\\shared\\{runtime-type}\\{version}\\_</span></span>

::: zone-end

::: zone pivot="os-linux"

- <span data-ttu-id="cd1aa-130">**archivo ejecutable de dotnet**</span><span class="sxs-lookup"><span data-stu-id="cd1aa-130">**dotnet executable**</span></span>\
<span data-ttu-id="cd1aa-131">_/home/user/share/dotnet/dotnet_</span><span class="sxs-lookup"><span data-stu-id="cd1aa-131">_/home/user/share/dotnet/dotnet_</span></span>

- <span data-ttu-id="cd1aa-132">**.NET SDK**</span><span class="sxs-lookup"><span data-stu-id="cd1aa-132">**.NET SDK**</span></span>\
<span data-ttu-id="cd1aa-133">_/home/user/share/dotnet/sdk/{versión}/_</span><span class="sxs-lookup"><span data-stu-id="cd1aa-133">_/home/user/share/dotnet/sdk/{version}/_</span></span>

- <span data-ttu-id="cd1aa-134">**Runtime de .NET**</span><span class="sxs-lookup"><span data-stu-id="cd1aa-134">**.NET Runtime**</span></span>\
<span data-ttu-id="cd1aa-135">_/home/user/share/dotnet/shared/{tipo de runtime}/{versión}/_</span><span class="sxs-lookup"><span data-stu-id="cd1aa-135">_/home/user/share/dotnet/shared/{runtime-type}/{version}/_</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="cd1aa-136">**archivo ejecutable de dotnet**</span><span class="sxs-lookup"><span data-stu-id="cd1aa-136">**dotnet executable**</span></span>\
<span data-ttu-id="cd1aa-137">_/usr/local/share/dotnet/dotnet_</span><span class="sxs-lookup"><span data-stu-id="cd1aa-137">_/usr/local/share/dotnet/dotnet_</span></span>

- <span data-ttu-id="cd1aa-138">**.NET SDK**</span><span class="sxs-lookup"><span data-stu-id="cd1aa-138">**.NET SDK**</span></span>\
<span data-ttu-id="cd1aa-139">_/usr/local/share/dotnet/sdk/{versión}/_</span><span class="sxs-lookup"><span data-stu-id="cd1aa-139">_/usr/local/share/dotnet/sdk/{version}/_</span></span>

- <span data-ttu-id="cd1aa-140">**Runtime de .NET**</span><span class="sxs-lookup"><span data-stu-id="cd1aa-140">**.NET Runtime**</span></span>\
<span data-ttu-id="cd1aa-141">_/usr/local/share/dotnet/shared/{tipo de runtime}/{versión}/_</span><span class="sxs-lookup"><span data-stu-id="cd1aa-141">_/usr/local/share/dotnet/shared/{runtime-type}/{version}/_</span></span>

::: zone-end

## <a name="more-information"></a><span data-ttu-id="cd1aa-142">Más información</span><span class="sxs-lookup"><span data-stu-id="cd1aa-142">More information</span></span>

<span data-ttu-id="cd1aa-143">Se pueden ver las versiones del SDK y del entorno de ejecución con el comando `dotnet --info`.</span><span class="sxs-lookup"><span data-stu-id="cd1aa-143">You can see both the SDK versions and runtime versions with the command `dotnet --info`.</span></span> <span data-ttu-id="cd1aa-144">También obtendrá otra información relacionada con el entorno, como la versión del sistema operativo y el identificador del entorno de ejecución (RID).</span><span class="sxs-lookup"><span data-stu-id="cd1aa-144">You'll also get other environmental related information, such as the operating system version and runtime identifier (RID).</span></span>

## <a name="next-steps"></a><span data-ttu-id="cd1aa-145">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="cd1aa-145">Next steps</span></span>

- <span data-ttu-id="cd1aa-146">[Instalar el entorno de ejecución de .NET Core](runtime.md).</span><span class="sxs-lookup"><span data-stu-id="cd1aa-146">[Install the .NET Core Runtime](runtime.md).</span></span>
- <span data-ttu-id="cd1aa-147">[Instalar el SDK de .NET Core](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="cd1aa-147">[Install the .NET Core SDK](sdk.md).</span></span>
