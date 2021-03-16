---
title: Eliminación del entorno de ejecución y el SDK de .NET
description: En este artículo se describe cómo determinar las versiones del entorno de ejecución y el SDK de .NET instaladas y, luego, cómo quitarlas en Windows, Mac, and Linux.
author: adegeo
ms.author: adegeo
ms.date: 03/02/2021
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 8ef6ab531d6c3eada5226b1682f19bfe5537bfe4
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255638"
---
# <a name="how-to-remove-the-net-runtime-and-sdk"></a><span data-ttu-id="85ed6-103">Procedimiento para quitar el entorno de ejecución y el SDK de .NET</span><span class="sxs-lookup"><span data-stu-id="85ed6-103">How to remove the .NET Runtime and SDK</span></span>

<span data-ttu-id="85ed6-104">Con el tiempo, a medida que instale versiones actualizadas del entorno de ejecución y el SDK de .NET, es posible que quiera quitar del equipo las versiones obsoletas de .NET.</span><span class="sxs-lookup"><span data-stu-id="85ed6-104">Over time, as you install updated versions of the .NET runtime and SDK, you may want to remove outdated versions of .NET from your machine.</span></span> <span data-ttu-id="85ed6-105">Al quitar versiones anteriores del entorno de ejecución es posible que se cambie el elegido para ejecutar aplicaciones de marco compartido, como se detalla en el artículo sobre [selección de la versión de .NET](../versions/selection.md).</span><span class="sxs-lookup"><span data-stu-id="85ed6-105">Removing older versions of the runtime may change the runtime chosen to run shared framework applications, as detailed in the article on [.NET version selection](../versions/selection.md).</span></span>

## <a name="should-i-remove-a-version"></a><span data-ttu-id="85ed6-106">¿Puedo quitar una versión?</span><span class="sxs-lookup"><span data-stu-id="85ed6-106">Should I remove a version?</span></span>

<span data-ttu-id="85ed6-107">Los comportamientos de la [selección de la versión de .NET](../versions/selection.md) y la compatibilidad del entorno de ejecución de .NET entre actualizaciones permite quitar de forma segura las versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="85ed6-107">The [.NET version selection](../versions/selection.md) behaviors and the runtime compatibility of .NET across updates enables safe removal of previous versions.</span></span> <span data-ttu-id="85ed6-108">Las actualizaciones del entorno de ejecución de .NET son compatibles con una **banda** de versión principal, como 1.x y 2.x.</span><span class="sxs-lookup"><span data-stu-id="85ed6-108">.NET runtime updates are compatible within a major version **band** such as 1.x and 2.x.</span></span> <span data-ttu-id="85ed6-109">Además, normalmente las versiones más recientes del SDK de .NET mantienen la capacidad de crear aplicaciones destinadas a versiones anteriores del entorno de ejecución de una forma compatible.</span><span class="sxs-lookup"><span data-stu-id="85ed6-109">Additionally, newer releases of the .NET SDK generally maintain the ability to build applications that target previous versions of the runtime in a compatible manner.</span></span>

<span data-ttu-id="85ed6-110">En general, solo se necesita el SDK más reciente y la última versión de revisión de los runtimes necesarios para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="85ed6-110">In general, you only need the latest SDK and latest patch version of the runtimes required for your application.</span></span> <span data-ttu-id="85ed6-111">Los casos en los que interesa conservar versiones anteriores del SDK o del runtime incluyen el mantenimiento de aplicaciones basadas en *project.json*.</span><span class="sxs-lookup"><span data-stu-id="85ed6-111">Instances where you might want to keep older SDK or runtime versions include maintaining *project.json*-based applications.</span></span> <span data-ttu-id="85ed6-112">A menos que la aplicación tenga motivos concretos para utilizar SDK o runtimes anteriores, puede quitar las versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="85ed6-112">Unless your application has specific reasons for earlier SDKs or runtimes, you may safely remove older versions.</span></span>

## <a name="determine-what-is-installed"></a><span data-ttu-id="85ed6-113">Determinación de lo instalado</span><span class="sxs-lookup"><span data-stu-id="85ed6-113">Determine what is installed</span></span>

<span data-ttu-id="85ed6-114">La CLI de .NET tiene opciones que puede usar para enumerar las versiones del SDK y del entorno de ejecución instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="85ed6-114">The .NET CLI has options you can use to list the versions of the SDK and runtime that are installed on your machine.</span></span>  <span data-ttu-id="85ed6-115">Use [`dotnet --list-sdks`](../tools/dotnet.md#options) para ver la lista de los SDK instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="85ed6-115">Use [`dotnet --list-sdks`](../tools/dotnet.md#options) to see the list of SDKs installed on your machine.</span></span> <span data-ttu-id="85ed6-116">Use [`dotnet --list-runtimes`](../tools/dotnet.md#options) para ver la lista de los runtimes instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="85ed6-116">Use [`dotnet --list-runtimes`](../tools/dotnet.md#options) to see the list of runtimes installed on your machine.</span></span> <span data-ttu-id="85ed6-117">Para obtener más información, vea [Cómo comprobar que .NET Core ya está instalado](how-to-detect-installed-versions.md).</span><span class="sxs-lookup"><span data-stu-id="85ed6-117">For more information, see [How to check that .NET is already installed](how-to-detect-installed-versions.md).</span></span>

## <a name="uninstall-net"></a><span data-ttu-id="85ed6-118">Desinstalación de .NET</span><span class="sxs-lookup"><span data-stu-id="85ed6-118">Uninstall .NET</span></span>

::: zone pivot="os-windows"

<span data-ttu-id="85ed6-119">.NET usa el cuadro de diálogo **Aplicaciones y características** de Windows para quitar las versiones del entorno de ejecución y del SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="85ed6-119">.NET uses the Windows **Apps & features** dialog to remove versions of the .NET runtime and SDK.</span></span> <span data-ttu-id="85ed6-120">En la siguiente ilustración se muestra el cuadro de diálogo **Aplicaciones y características**.</span><span class="sxs-lookup"><span data-stu-id="85ed6-120">The following figure shows the **Apps & features** dialog.</span></span> <span data-ttu-id="85ed6-121">Puede buscar **core sdk** o **.net sdk** para filtrar y mostrar las versiones instaladas de .NET.</span><span class="sxs-lookup"><span data-stu-id="85ed6-121">You can search for **core sdk** or **.net sdk** to filter and show installed versions of .NET.</span></span>

![Agregar o quitar programas para quitar .NET](./media/remove-runtime-sdk-versions/programs-and-features.png)

<span data-ttu-id="85ed6-123">Seleccione las versiones que quiera quitar de su equipo y haga clic en **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="85ed6-123">Select any versions you want to remove from your machine and click **Uninstall**.</span></span>

::: zone-end

::: zone pivot="os-linux"

<span data-ttu-id="85ed6-124">Para desinstalar .NET (el SDK o el entorno de ejecución) en Linux tiene más opciones.</span><span class="sxs-lookup"><span data-stu-id="85ed6-124">There are more options to uninstall .NET (either SDK or runtime) on Linux.</span></span> <span data-ttu-id="85ed6-125">La mejor forma de desinstalar .NET es repetir la misma acción que se ha usado para instalarlo.</span><span class="sxs-lookup"><span data-stu-id="85ed6-125">The best way for you to uninstall .NET is to mirror the action you used to install .NET.</span></span> <span data-ttu-id="85ed6-126">Los detalles específicos dependerán de la distribución que elija y del método de instalación.</span><span class="sxs-lookup"><span data-stu-id="85ed6-126">The specifics depend on your chosen distribution and the installation method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85ed6-127">Para las instalaciones de Red Hat, consulte la [documentación del producto Red Hat para .NET](https://access.redhat.com/documentation/en-us/net/5.0/).</span><span class="sxs-lookup"><span data-stu-id="85ed6-127">For Red Hat installations, consult the [Red Hat Product Documentation for .NET](https://access.redhat.com/documentation/en-us/net/5.0/).</span></span>

<span data-ttu-id="85ed6-128">No es necesario desinstalar el SDK de .NET al actualizarlo mediante un administrador de paquetes, a menos que se actualice desde una versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="85ed6-128">There's no need to uninstall the .NET SDK when upgrading it using a package manager, unless you're upgrading from a preview version.</span></span> <span data-ttu-id="85ed6-129">Los comandos `update` o `refresh` del administrador de paquetes quitarán automáticamente la versión anterior tras la instalación correcta de una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="85ed6-129">The package manager `update` or `refresh` commands will automatically remove the older version upon the successful installation of a newer version.</span></span> <span data-ttu-id="85ed6-130">Si tiene instalada una versión preliminar, desinstálela.</span><span class="sxs-lookup"><span data-stu-id="85ed6-130">If you have a preview version installed, uninstall it.</span></span>

<span data-ttu-id="85ed6-131">Si ha instalado .NET con un administrador de paquetes, use ese mismo administrador de paquetes para desinstalar el SDK o el entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="85ed6-131">If you installed .NET using a package manager, use that same package manager to uninstall the .NET SDK or runtime.</span></span> <span data-ttu-id="85ed6-132">Las instalaciones de .NET admiten los administradores de paquetes más conocidos.</span><span class="sxs-lookup"><span data-stu-id="85ed6-132">.NET installations support most popular package managers.</span></span> <span data-ttu-id="85ed6-133">Consulte la documentación del administrador de paquetes de su distribución para conocer la sintaxis exacta en su entorno:</span><span class="sxs-lookup"><span data-stu-id="85ed6-133">Consult the documentation for your distribution's package manager for the precise syntax in your environment:</span></span>

- <span data-ttu-id="85ed6-134">[apt-get(8)](https://linux.die.net/man/8/apt-get) se utiliza en sistemas basados en Debian, incluido Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="85ed6-134">[apt-get(8)](https://linux.die.net/man/8/apt-get) is used by Debian based systems, including Ubuntu.</span></span>
- <span data-ttu-id="85ed6-135">[yum(8)](https://linux.die.net/man/8/yum) se utiliza en Fedora, CentOS y Oracle Linux.</span><span class="sxs-lookup"><span data-stu-id="85ed6-135">[yum(8)](https://linux.die.net/man/8/yum) is used on Fedora, CentOS, and Oracle Linux.</span></span>
- <span data-ttu-id="85ed6-136">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) se utiliza en openSUSE y SUSE Linux Enterprise Server (SLES).</span><span class="sxs-lookup"><span data-stu-id="85ed6-136">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) is used on openSUSE and SUSE Linux Enterprise System (SLES).</span></span>
- <span data-ttu-id="85ed6-137">[DNF(8)](https://dnf.readthedocs.io/en/latest/command_ref.html) se utiliza en Fedora.</span><span class="sxs-lookup"><span data-stu-id="85ed6-137">[dnf(8)](https://dnf.readthedocs.io/en/latest/command_ref.html) is used on Fedora.</span></span>

<span data-ttu-id="85ed6-138">En casi todos los casos, el comando para quitar un paquete es `remove`.</span><span class="sxs-lookup"><span data-stu-id="85ed6-138">In almost all cases, the command to remove a package is `remove`.</span></span>

<span data-ttu-id="85ed6-139">El nombre del paquete para la instalación del SDK de .NET en la mayoría de administradores de paquetes es `dotnet-sdk`, seguido por el número de versión.</span><span class="sxs-lookup"><span data-stu-id="85ed6-139">The package name for the .NET SDK installation for most package managers is `dotnet-sdk`, followed by the version number.</span></span> <span data-ttu-id="85ed6-140">A partir de la versión 2.1.300 del SDK de .NET y de la versión `2.1` del entorno de ejecución, solo se necesitan el primer y el segundo número de versión: por ejemplo, puede hacer referencia a la versión 2.1.300 del SDK de .NET como el paquete `dotnet-sdk-2.1`.</span><span class="sxs-lookup"><span data-stu-id="85ed6-140">Starting with the version 2.1.300 of the .NET SDK and version `2.1` of the runtime, only the major and minor version numbers are necessary: for example, the .NET SDK version 2.1.300 can be referenced as the package `dotnet-sdk-2.1`.</span></span> <span data-ttu-id="85ed6-141">Para las versiones anteriores se necesita la cadena de versión completa: por ejemplo, se necesitaría `dotnet-sdk-2.1.200` para la versión 2.1.200 del SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="85ed6-141">Prior versions require the entire version string: for example, `dotnet-sdk-2.1.200` would be required for version 2.1.200 of the .NET SDK.</span></span>

<span data-ttu-id="85ed6-142">En los equipos en los que solo se ha instalado el entorno de ejecución, y no el SDK, el nombre del paquete es `dotnet-runtime-<version>` para el entorno de ejecución de .NET y `aspnetcore-runtime-<version>` para la pila de entorno de ejecución entera.</span><span class="sxs-lookup"><span data-stu-id="85ed6-142">For machines that have installed only the runtime, and not the SDK, the package name is `dotnet-runtime-<version>` for the .NET runtime, and `aspnetcore-runtime-<version>` for the entire runtime stack.</span></span>

> [!TIP]
> <span data-ttu-id="85ed6-143">Al instalar las versiones de .NET Core anteriores a 2.0 no se desinstaló la aplicación host al desinstalar el SDK mediante el administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="85ed6-143">.NET Core installations earlier than 2.0 didn't uninstall the host application when the SDK was uninstalled using the package manager.</span></span> <span data-ttu-id="85ed6-144">Al usar `apt-get`, el comando es:</span><span class="sxs-lookup"><span data-stu-id="85ed6-144">Using `apt-get`, the command is:</span></span>
>
> ```bash
> apt-get remove dotnet-host
> ```
>
> <span data-ttu-id="85ed6-145">No hay ninguna versión conectada a `dotnet-host`.</span><span class="sxs-lookup"><span data-stu-id="85ed6-145">There's no version attached to `dotnet-host`.</span></span>

<span data-ttu-id="85ed6-146">Si ha realizado la instalación mediante un archivo tarball, debe quitar .NET mediante el método manual.</span><span class="sxs-lookup"><span data-stu-id="85ed6-146">If you installed using a tarball, you must remove .NET using the manual method.</span></span>

<span data-ttu-id="85ed6-147">En Linux, debe quitar los SDK y runtimes por separado, quitando los directorios con versiones.</span><span class="sxs-lookup"><span data-stu-id="85ed6-147">On Linux, you must remove the SDKs and runtimes separately, by removing the versioned directories.</span></span> <span data-ttu-id="85ed6-148">Estos directorios pueden variar en función de la distribución de Linux.</span><span class="sxs-lookup"><span data-stu-id="85ed6-148">These directories may vary depending on your Linux distribution.</span></span> <span data-ttu-id="85ed6-149">De esta manera, se elimina el SDK y el runtime del disco.</span><span class="sxs-lookup"><span data-stu-id="85ed6-149">Removing them deletes the SDK and runtime from disk.</span></span> <span data-ttu-id="85ed6-150">Por ejemplo, para quitar el runtime y el SDK 1.0.1, tendrá que usar los siguientes comandos de bash:</span><span class="sxs-lookup"><span data-stu-id="85ed6-150">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
version="1.0.1"
sudo rm -rf /usr/share/dotnet/sdk/$version
sudo rm -rf /usr/share/dotnet/shared/Microsoft.NETCore.App/$version
sudo rm -rf /usr/share/dotnet/shared/Microsoft.AspNetCore.All/$version
sudo rm -rf /usr/share/dotnet/shared/Microsoft.AspNetCore.App/$version
sudo rm -rf /usr/share/dotnet/host/fxr/$version
```

<span data-ttu-id="85ed6-151">Los directorios primarios para el SDK y runtime se enumeran en el resultado de los comandos `dotnet --list-sdks` y `dotnet --list-runtimes`, como se muestra en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="85ed6-151">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="85ed6-152">En Mac, debe quitar los SDK y runtimes por separado, quitando los directorios con versiones.</span><span class="sxs-lookup"><span data-stu-id="85ed6-152">On Mac, you must remove the SDKs and runtimes separately, by removing the versioned directories.</span></span> <span data-ttu-id="85ed6-153">De esta manera, se elimina el SDK y el runtime del disco.</span><span class="sxs-lookup"><span data-stu-id="85ed6-153">Removing them deletes the SDK and runtime from disk.</span></span> <span data-ttu-id="85ed6-154">Por ejemplo, para quitar el runtime y el SDK 1.0.1, tendrá que usar los siguientes comandos de bash:</span><span class="sxs-lookup"><span data-stu-id="85ed6-154">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
version="1.0.1"
sudo rm -rf /usr/local/share/dotnet/sdk/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.All/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/$version
sudo rm -rf /usr/local/share/dotnet/host/fxr/$version
```

<span data-ttu-id="85ed6-155">Los directorios primarios para el SDK y runtime se enumeran en el resultado de los comandos `dotnet --list-sdks` y `dotnet --list-runtimes`, como se muestra en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="85ed6-155">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

::: zone-end

## <a name="net-uninstall-tool"></a><span data-ttu-id="85ed6-156">Herramienta de desinstalación de .NET</span><span class="sxs-lookup"><span data-stu-id="85ed6-156">.NET Uninstall Tool</span></span>

<span data-ttu-id="85ed6-157">La [herramienta de desinstalación de .NET](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) permite quitar los SDK y los entornos de ejecución de .NET de un sistema.</span><span class="sxs-lookup"><span data-stu-id="85ed6-157">The [.NET Uninstall Tool](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) lets you remove .NET SDKs and runtimes from a system.</span></span> <span data-ttu-id="85ed6-158">Hay una colección de opciones disponible para especificar las versiones que se deben desinstalar.</span><span class="sxs-lookup"><span data-stu-id="85ed6-158">A collection of options is available to specify which versions should be uninstalled.</span></span>

::: zone pivot="os-windows"

## <a name="visual-studio-dependency-on-net-core-sdk-versions"></a><span data-ttu-id="85ed6-159">Dependencia de Visual Studio en versiones de SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="85ed6-159">Visual Studio dependency on .NET Core SDK versions</span></span>

<span data-ttu-id="85ed6-160">Antes de la versión 16.3 de Visual Studio 2019, los instaladores de Visual Studio llamaron al instalador de SDK de .NET Core independiente.</span><span class="sxs-lookup"><span data-stu-id="85ed6-160">Before Visual Studio 2019 version 16.3, Visual Studio installers called the standalone .NET Core SDK installer.</span></span> <span data-ttu-id="85ed6-161">Como resultado, las versiones del SDK aparecen en el cuadro de diálogo **Aplicaciones y características** de Windows.</span><span class="sxs-lookup"><span data-stu-id="85ed6-161">As a result, the SDK versions appear in the Windows **Apps & features** dialog.</span></span> <span data-ttu-id="85ed6-162">La eliminación de los SDK de .NET Core que se instalaron con Visual Studio mediante el instalador independiente podría interrumpir Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="85ed6-162">Removing .NET Core SDKs that were installed by Visual Studio using the standalone installer may break Visual Studio.</span></span> <span data-ttu-id="85ed6-163">Si Visual Studio tiene problemas después de desinstalar los SDK, ejecute reparar en esa versión específica de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="85ed6-163">If Visual Studio has problems after you uninstall SDKs, run Repair on that specific version of Visual Studio.</span></span> <span data-ttu-id="85ed6-164">En la tabla siguiente se muestran algunas de las dependencias de Visual Studio en las versiones de SDK de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="85ed6-164">The following table shows some of the Visual Studio dependencies on .NET Core SDK versions:</span></span>

| <span data-ttu-id="85ed6-165">Versión de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="85ed6-165">Visual Studio version</span></span>           | <span data-ttu-id="85ed6-166">Versión del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="85ed6-166">.NET Core SDK version</span></span>          |
|---------------------------------|--------------------------------|
| <span data-ttu-id="85ed6-167">Visual Studio 2019, versión 16.2</span><span class="sxs-lookup"><span data-stu-id="85ed6-167">Visual Studio 2019 version 16.2</span></span> | <span data-ttu-id="85ed6-168">SDK de .NET Core 2.2.4xx, 2.1.8xx</span><span class="sxs-lookup"><span data-stu-id="85ed6-168">.NET Core SDK 2.2.4xx, 2.1.8xx</span></span> |
| <span data-ttu-id="85ed6-169">Visual Studio 2019, versión 16.1</span><span class="sxs-lookup"><span data-stu-id="85ed6-169">Visual Studio 2019 version 16.1</span></span> | <span data-ttu-id="85ed6-170">SDK de .NET Core 2.2.3xx, 2.1.7xx</span><span class="sxs-lookup"><span data-stu-id="85ed6-170">.NET Core SDK 2.2.3xx, 2.1.7xx</span></span> |
| <span data-ttu-id="85ed6-171">Visual Studio 2019, versión 16.0</span><span class="sxs-lookup"><span data-stu-id="85ed6-171">Visual Studio 2019 version 16.0</span></span> | <span data-ttu-id="85ed6-172">SDK de .NET Core 2.2.2xx, 2.1.6xx</span><span class="sxs-lookup"><span data-stu-id="85ed6-172">.NET Core SDK 2.2.2xx, 2.1.6xx</span></span> |
| <span data-ttu-id="85ed6-173">Visual Studio 2017, versión 15.9</span><span class="sxs-lookup"><span data-stu-id="85ed6-173">Visual Studio 2017 version 15.9</span></span> | <span data-ttu-id="85ed6-174">SDK de .NET Core 2.2.1xx, 2.1.5xx</span><span class="sxs-lookup"><span data-stu-id="85ed6-174">.NET Core SDK 2.2.1xx, 2.1.5xx</span></span> |
| <span data-ttu-id="85ed6-175">Visual Studio 2017, versión 15.8</span><span class="sxs-lookup"><span data-stu-id="85ed6-175">Visual Studio 2017 version 15.8</span></span> | <span data-ttu-id="85ed6-176">SDK de .NET Core 2.1.4xx</span><span class="sxs-lookup"><span data-stu-id="85ed6-176">.NET Core SDK 2.1.4xx</span></span>          |

<span data-ttu-id="85ed6-177">A partir de la versión 16.3 de Visual Studio 2019, Visual Studio se encarga de su propia copia del SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="85ed6-177">Starting with Visual Studio 2019 version 16.3, Visual Studio is in charge of its own copy of the .NET SDK.</span></span> <span data-ttu-id="85ed6-178">Por ese motivo, ya no verá las versiones del SDK en el cuadro de diálogo **Aplicaciones y características**.</span><span class="sxs-lookup"><span data-stu-id="85ed6-178">For that reason, you no longer see those SDK versions in the **Apps & features** dialog.</span></span>

::: zone-end

## <a name="remove-the-nuget-fallback-folder"></a><span data-ttu-id="85ed6-179">Eliminación de la carpeta de reserva de NuGet</span><span class="sxs-lookup"><span data-stu-id="85ed6-179">Remove the NuGet fallback folder</span></span>

<span data-ttu-id="85ed6-180">Antes del SDK de .NET Core 3.0, los instaladores del SDK de .NET Core usaban una carpeta denominada *NuGetFallbackFolder* para almacenar una memoria caché de paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="85ed6-180">Before .NET Core 3.0 SDK, the .NET Core SDK installers used a folder named *NuGetFallbackFolder* to store a cache of NuGet packages.</span></span> <span data-ttu-id="85ed6-181">Esta memoria caché se utilizó durante operaciones como `dotnet restore` o `dotnet build /t:Restore`.</span><span class="sxs-lookup"><span data-stu-id="85ed6-181">This cache was used during operations such as `dotnet restore` or `dotnet build /t:Restore`.</span></span> <span data-ttu-id="85ed6-182">La carpeta *NuGetFallbackFolder* se encuentra en *C:\Archivos de programa\dotnet\sdk* en Windows y en */usr/local/share/dotnet/sdk* en macOS.</span><span class="sxs-lookup"><span data-stu-id="85ed6-182">The *NuGetFallbackFolder* is located at *C:\Program Files\dotnet\sdk* on Windows and at */usr/local/share/dotnet/sdk* on macOS.</span></span>

<span data-ttu-id="85ed6-183">Es posible que desee quitar esta carpeta si:</span><span class="sxs-lookup"><span data-stu-id="85ed6-183">You may want to remove this folder, if:</span></span>

- <span data-ttu-id="85ed6-184">Solo desarrolla con el SDK de .NET Core 3.0, .NET 5.0 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="85ed6-184">You're only developing using .NET Core 3.0 SDK or .NET 5.0 or later versions.</span></span>
- <span data-ttu-id="85ed6-185">Está desarrollando con versiones del SDK de .NET Core anteriores a la 3.0, pero puede trabajar en línea.</span><span class="sxs-lookup"><span data-stu-id="85ed6-185">You're developing using .NET Core SDK versions earlier than 3.0, but you can work online.</span></span>

<span data-ttu-id="85ed6-186">Si desea quitar la carpeta de reserva de NuGet, puede eliminarla, pero necesitará privilegios de administrador para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="85ed6-186">If you want to remove the NuGet fallback folder, you can delete it, but you'll need admin privileges to do so.</span></span>

<span data-ttu-id="85ed6-187">No se recomienda eliminar la carpeta *dotnet*.</span><span class="sxs-lookup"><span data-stu-id="85ed6-187">It's not recommended to delete the *dotnet* folder.</span></span> <span data-ttu-id="85ed6-188">Si lo hace, se quitarán las herramientas globales que haya instalado previamente.</span><span class="sxs-lookup"><span data-stu-id="85ed6-188">Doing so would remove any global tools you've previously installed.</span></span> <span data-ttu-id="85ed6-189">Además, en Windows:</span><span class="sxs-lookup"><span data-stu-id="85ed6-189">Also, on Windows:</span></span>

- <span data-ttu-id="85ed6-190">Interrumpirá Visual Studio 2019 versión 16.3 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="85ed6-190">You'll break Visual Studio 2019 version 16.3 and later versions.</span></span> <span data-ttu-id="85ed6-191">Puede ejecutar **Reparar** para recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="85ed6-191">You can run **Repair** to recover.</span></span>
- <span data-ttu-id="85ed6-192">Si hay entradas del SDK de .NET Core en el cuadro de diálogo **Aplicaciones y características**, se quedarán huérfanas.</span><span class="sxs-lookup"><span data-stu-id="85ed6-192">If there are .NET Core SDK entries in the **Apps & features** dialog, they'll be orphaned.</span></span>
