---
title: Scripts de dotnet-install
description: Obtenga información sobre los scripts de dotnet-install para instalar el SDK de .NET Core y el entorno de ejecución compartido.
ms.date: 04/30/2020
ms.openlocfilehash: 9f5cef9cfcca1d8b344021efe803c063a7393f8e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802722"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="3334c-103">referencia de scripts de dotnet-install</span><span class="sxs-lookup"><span data-stu-id="3334c-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="3334c-104">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="3334c-104">Name</span></span>

<span data-ttu-id="3334c-105">`dotnet-install.ps1` | `dotnet-install.sh`: script usado para instalar el SDK de .NET Core y el entorno de ejecución compartido.</span><span class="sxs-lookup"><span data-stu-id="3334c-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core SDK and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3334c-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="3334c-106">Synopsis</span></span>

<span data-ttu-id="3334c-107">Windows:</span><span class="sxs-lookup"><span data-stu-id="3334c-107">Windows:</span></span>

```powershell
dotnet-install.ps1 [-Architecture <ARCHITECTURE>] [-AzureFeed]
    [-Channel <CHANNEL>] [-DryRun] [-FeedCredential]
    [-InstallDir <DIRECTORY>] [-JSonFile <JSONFILE>]
    [-NoCdn] [-NoPath] [-ProxyAddress]
    [-ProxyUseDefaultCredentials] [-Runtime <RUNTIME>]
    [-SkipNonVersionedFiles] [-UncachedFeed] [-Verbose]
    [-Version <VERSION>]

dotnet-install.ps1 -Help
```

<span data-ttu-id="3334c-108">Linux/macOS:</span><span class="sxs-lookup"><span data-stu-id="3334c-108">Linux/macOS:</span></span>

```bash
dotnet-install.sh  [--architecture <ARCHITECTURE>] [--azure-feed]
    [--channel <CHANNEL>] [--dry-run] [--feed-credential]
    [--install-dir <DIRECTORY>] [--jsonfile <JSONFILE>]
    [--no-cdn] [--no-path] [--runtime <RUNTIME>] [--runtime-id <RID>]
    [--skip-non-versioned-files] [--uncached-feed] [--verbose]
    [--version <VERSION>]

dotnet-install.sh --help
```

## <a name="description"></a><span data-ttu-id="3334c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="3334c-109">Description</span></span>

<span data-ttu-id="3334c-110">Los scripts `dotnet-install` se usan para realizar una instalación sin derechos administrativos del SDK de .NET Core, que incluye la CLI de .NET Core y el entorno de tiempo de ejecución compartido.</span><span class="sxs-lookup"><span data-stu-id="3334c-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI and the shared runtime.</span></span>

<span data-ttu-id="3334c-111">Se recomienda usar la versión estable de los scripts:</span><span class="sxs-lookup"><span data-stu-id="3334c-111">We recommend that you use the stable version of the scripts:</span></span>

- <span data-ttu-id="3334c-112">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span><span class="sxs-lookup"><span data-stu-id="3334c-112">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span></span>
- <span data-ttu-id="3334c-113">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span><span class="sxs-lookup"><span data-stu-id="3334c-113">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span></span>

<span data-ttu-id="3334c-114">La utilidad principal de estos scripts está en los escenarios de automatización y las instalaciones sin derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="3334c-114">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="3334c-115">Existen dos scripts: uno es un script de PowerShell que funciona en Windows y el otro es un script de Bash que funciona en Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="3334c-115">There are two scripts: one is a PowerShell script that works on Windows, and the other is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="3334c-116">Ambos scripts tienen el mismo comportamiento.</span><span class="sxs-lookup"><span data-stu-id="3334c-116">Both scripts have the same behavior.</span></span> <span data-ttu-id="3334c-117">El script de bash también lee modificadores de PowerShell, por lo que puede usar modificadores de PowerShell con el script en sistemas Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="3334c-117">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="3334c-118">Los scripts de instalación descargan el archivo ZIP o tarball desde las entregas de compilación de la CLI y proceden a instalarlo en la ubicación predeterminada o en una ubicación especificada por `-InstallDir|--install-dir`.</span><span class="sxs-lookup"><span data-stu-id="3334c-118">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="3334c-119">De forma predeterminada, los scripts de instalación descargan el SDK y lo instalan.</span><span class="sxs-lookup"><span data-stu-id="3334c-119">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="3334c-120">Si desea obtener solo el tiempo de ejecución compartido, especifique el argumento `-Runtime|--runtime`.</span><span class="sxs-lookup"><span data-stu-id="3334c-120">If you wish to only obtain the shared runtime, specify the `-Runtime|--runtime` argument.</span></span>

<span data-ttu-id="3334c-121">De forma predeterminada, el script agrega la ubicación de instalación a $PATH para la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="3334c-121">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="3334c-122">Para invalidar este comportamiento, especifique el argumento `-NoPath|--no-path`.</span><span class="sxs-lookup"><span data-stu-id="3334c-122">Override this default behavior by specifying the `-NoPath|--no-path` argument.</span></span>

<span data-ttu-id="3334c-123">Antes de ejecutar el script, instale las [dependencias](../install/dependencies.md) necesarias.</span><span class="sxs-lookup"><span data-stu-id="3334c-123">Before running the script, install the required [dependencies](../install/dependencies.md).</span></span>

<span data-ttu-id="3334c-124">Puede instalar una versión específica mediante el argumento `-Version|--version`.</span><span class="sxs-lookup"><span data-stu-id="3334c-124">You can install a specific version using the `-Version|--version` argument.</span></span> <span data-ttu-id="3334c-125">La versión debe especificarse como una versión de tres partes (por ejemplo, `2.1.0`).</span><span class="sxs-lookup"><span data-stu-id="3334c-125">The version must be specified as a three-part version (for example, `2.1.0`).</span></span> <span data-ttu-id="3334c-126">Si no se proporciona, usa la versión `latest`.</span><span class="sxs-lookup"><span data-stu-id="3334c-126">If not provided, it uses the `latest` version.</span></span>

<span data-ttu-id="3334c-127">Los scripts de instalación no actualizan el Registro en Windows.</span><span class="sxs-lookup"><span data-stu-id="3334c-127">The install scripts do not update the registry on Windows.</span></span> <span data-ttu-id="3334c-128">Solo descargan los archivos binarios comprimidos y los copian en una carpeta.</span><span class="sxs-lookup"><span data-stu-id="3334c-128">They just download the zipped binaries and copy them to a folder.</span></span> <span data-ttu-id="3334c-129">Si desea que se actualicen los valores de las claves del Registro, use los instaladores de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3334c-129">If you want registry key values to be updated, use the .NET Core installers.</span></span>

## <a name="options"></a><span data-ttu-id="3334c-130">Opciones</span><span class="sxs-lookup"><span data-stu-id="3334c-130">Options</span></span>

- **`-Architecture|--architecture <ARCHITECTURE>`**

  <span data-ttu-id="3334c-131">Arquitectura de los archivos binarios de .NET Core para instalar.</span><span class="sxs-lookup"><span data-stu-id="3334c-131">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="3334c-132">Los valores posibles son `<auto>`, `amd64`, `x64`, `x86`, `arm64` y `arm`.</span><span class="sxs-lookup"><span data-stu-id="3334c-132">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="3334c-133">El valor predeterminado es `<auto>`, que representa la arquitectura de SO que se ejecuta en ese momento.</span><span class="sxs-lookup"><span data-stu-id="3334c-133">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-AzureFeed|--azure-feed`**

  <span data-ttu-id="3334c-134">Especifica la dirección URL de la fuente de Azure al instalador.</span><span class="sxs-lookup"><span data-stu-id="3334c-134">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="3334c-135">Le recomendamos que no cambie este valor.</span><span class="sxs-lookup"><span data-stu-id="3334c-135">We recommended that you don't change this value.</span></span> <span data-ttu-id="3334c-136">El valor predeterminado es `https://dotnetcli.azureedge.net/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="3334c-136">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-Channel|--channel <CHANNEL>`**

  <span data-ttu-id="3334c-137">Especifica el canal de origen para la instalación.</span><span class="sxs-lookup"><span data-stu-id="3334c-137">Specifies the source channel for the installation.</span></span> <span data-ttu-id="3334c-138">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="3334c-138">The possible values are:</span></span>

  - <span data-ttu-id="3334c-139">`Current`: versión más actual.</span><span class="sxs-lookup"><span data-stu-id="3334c-139">`Current` - Most current release.</span></span>
  - <span data-ttu-id="3334c-140">`LTS`: canal de soporte técnico a largo plazo (versión compatible más actual).</span><span class="sxs-lookup"><span data-stu-id="3334c-140">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="3334c-141">Versión de dos partes en formato X.Y que representa una versión específica (por ejemplo, `2.1` o `3.0`).</span><span class="sxs-lookup"><span data-stu-id="3334c-141">Two-part version in X.Y format representing a specific release (for example, `2.1` or `3.0`).</span></span>
  - <span data-ttu-id="3334c-142">Nombre de rama: por ejemplo, `release/3.1.1xx` o `master` (para versiones nocturnas).</span><span class="sxs-lookup"><span data-stu-id="3334c-142">Branch name: for example, `release/3.1.1xx` or `master` (for nightly releases).</span></span> <span data-ttu-id="3334c-143">Use esta opción para instalar una versión de un canal de versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="3334c-143">Use this option to install a version from a preview channel.</span></span> <span data-ttu-id="3334c-144">Use el nombre del canal como aparece en [Instaladores y binarios](https://github.com/dotnet/core-sdk#installers-and-binaries).</span><span class="sxs-lookup"><span data-stu-id="3334c-144">Use the name of the channel as listed in [Installers and Binaries](https://github.com/dotnet/core-sdk#installers-and-binaries).</span></span>

  <span data-ttu-id="3334c-145">El valor predeterminado es `LTS`.</span><span class="sxs-lookup"><span data-stu-id="3334c-145">The default value is `LTS`.</span></span> <span data-ttu-id="3334c-146">Para más información sobre los canales de soporte técnico de .NET, vea la página [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) (Directiva de soporte técnico de .NET Core).</span><span class="sxs-lookup"><span data-stu-id="3334c-146">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-DryRun|--dry-run`**

  <span data-ttu-id="3334c-147">Si se establece, el script no realizará la instalación.</span><span class="sxs-lookup"><span data-stu-id="3334c-147">If set, the script won't perform the installation.</span></span> <span data-ttu-id="3334c-148">En su lugar, mostrará qué línea de comandos se va a usar para instalar de manera coherente la versión solicitada actualmente de la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3334c-148">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="3334c-149">Por ejemplo, si especifica la versión `latest`, se muestra un vínculo con la versión específica, de manera que este comando puede usarse de manera determinista en un script de compilación.</span><span class="sxs-lookup"><span data-stu-id="3334c-149">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="3334c-150">También se muestra la ubicación de los archivos binarios si prefiere instalarla o descargarla por su cuenta.</span><span class="sxs-lookup"><span data-stu-id="3334c-150">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-FeedCredential|--feed-credential`**

  <span data-ttu-id="3334c-151">Se utiliza como una cadena de consulta para anexar a la fuente de Azure.</span><span class="sxs-lookup"><span data-stu-id="3334c-151">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="3334c-152">Permite cambiar la dirección URL para usar cuentas de almacenamiento de blobs no público.</span><span class="sxs-lookup"><span data-stu-id="3334c-152">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`-Help|--help`**

  <span data-ttu-id="3334c-153">Imprime la ayuda para el script.</span><span class="sxs-lookup"><span data-stu-id="3334c-153">Prints out help for the script.</span></span>

- **`-InstallDir|--install-dir <DIRECTORY>`**

  <span data-ttu-id="3334c-154">Especifica la ruta de instalación.</span><span class="sxs-lookup"><span data-stu-id="3334c-154">Specifies the installation path.</span></span> <span data-ttu-id="3334c-155">Si no existe el directorio, se crea.</span><span class="sxs-lookup"><span data-stu-id="3334c-155">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="3334c-156">El valor predeterminado es *%LocalAppData%\Microsoft\dotnet* en Windows y */usr/share/dotnet* en Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="3334c-156">The default value is *%LocalAppData%\Microsoft\dotnet* on Windows and */usr/share/dotnet* on Linux/macOS.</span></span> <span data-ttu-id="3334c-157">Los archivos binarios se colocan directamente en el directorio.</span><span class="sxs-lookup"><span data-stu-id="3334c-157">Binaries are placed directly in this directory.</span></span>

- **`-JSonFile|--jsonfile <JSONFILE>`**

  <span data-ttu-id="3334c-158">Especifica una ruta de acceso a un archivo [global.json](global-json.md) que se va a usar para determinar la versión del SDK.</span><span class="sxs-lookup"><span data-stu-id="3334c-158">Specifies a path to a [global.json](global-json.md) file that will be used to determine the SDK version.</span></span> <span data-ttu-id="3334c-159">El archivo *global.json* debe tener un valor para `sdk:version`.</span><span class="sxs-lookup"><span data-stu-id="3334c-159">The *global.json* file must have a value for `sdk:version`.</span></span>

- **`-NoCdn|--no-cdn`**

  <span data-ttu-id="3334c-160">Deshabilita la descarga desde [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) y usa la fuente no almacenada en caché directamente.</span><span class="sxs-lookup"><span data-stu-id="3334c-160">Disables downloading from the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-NoPath|--no-path`**

  <span data-ttu-id="3334c-161">Si se establece, la carpeta de instalación no se exporta a la ruta de acceso para la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="3334c-161">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="3334c-162">De manera predeterminada, el script modifica la variable de entorno PATH, que hace que la CLI esté disponible inmediatamente después de la instalación.</span><span class="sxs-lookup"><span data-stu-id="3334c-162">By default, the script modifies the PATH, which makes the .NET Core CLI available immediately after install.</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="3334c-163">Si se establece, el instalador usa el proxy al realizar solicitudes web.</span><span class="sxs-lookup"><span data-stu-id="3334c-163">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="3334c-164">(Solo es válido para Windows).</span><span class="sxs-lookup"><span data-stu-id="3334c-164">(Only valid for Windows.)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="3334c-165">Si se establece, el instalador usa las credenciales del usuario actual cuando se usa la dirección del proxy.</span><span class="sxs-lookup"><span data-stu-id="3334c-165">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="3334c-166">(Solo es válido para Windows).</span><span class="sxs-lookup"><span data-stu-id="3334c-166">(Only valid for Windows.)</span></span>

- **`-Runtime|--runtime <RUNTIME>`**

  <span data-ttu-id="3334c-167">Se instala simplemente el entorno de tiempo de ejecución compartido, no el SDK completo.</span><span class="sxs-lookup"><span data-stu-id="3334c-167">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="3334c-168">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="3334c-168">The possible values are:</span></span>

  - <span data-ttu-id="3334c-169">`dotnet`: el entorno de tiempo de ejecución compartido `Microsoft.NETCore.App`.</span><span class="sxs-lookup"><span data-stu-id="3334c-169">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="3334c-170">`aspnetcore`: el entorno de tiempo de ejecución compartido `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="3334c-170">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>
  - <span data-ttu-id="3334c-171">`windowsdesktop`: el entorno de tiempo de ejecución compartido `Microsoft.WindowsDesktop.App`.</span><span class="sxs-lookup"><span data-stu-id="3334c-171">`windowsdesktop` - the `Microsoft.WindowsDesktop.App` shared runtime.</span></span>

- **`--runtime-id <RID>`**

  <span data-ttu-id="3334c-172">Especifica el [identificador de entorno de ejecución](../rid-catalog.md) para el que se van a instalar las herramientas.</span><span class="sxs-lookup"><span data-stu-id="3334c-172">Specifies the [runtime identifier](../rid-catalog.md) for which the tools are being installed.</span></span> <span data-ttu-id="3334c-173">Use `linux-x64` para Linux portátil.</span><span class="sxs-lookup"><span data-stu-id="3334c-173">Use `linux-x64` for portable Linux.</span></span> <span data-ttu-id="3334c-174">(Solo es válido para Linux/macOS).</span><span class="sxs-lookup"><span data-stu-id="3334c-174">(Only valid for Linux/macOS.)</span></span>

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > <span data-ttu-id="3334c-175">Este parámetro está obsoleto y puede quitarse en una versión futura del script.</span><span class="sxs-lookup"><span data-stu-id="3334c-175">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="3334c-176">La alternativa recomendada es la opción `-Runtime|--runtime`.</span><span class="sxs-lookup"><span data-stu-id="3334c-176">The recommended alternative is the `-Runtime|--runtime` option.</span></span>

  <span data-ttu-id="3334c-177">Se instalan simplemente los bits del entorno de tiempo de ejecución compartido, no el SDK completo.</span><span class="sxs-lookup"><span data-stu-id="3334c-177">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="3334c-178">Esta opción equivale a especificar `-Runtime|--runtime dotnet`.</span><span class="sxs-lookup"><span data-stu-id="3334c-178">This option is equivalent to specifying `-Runtime|--runtime dotnet`.</span></span>

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  <span data-ttu-id="3334c-179">Omite la instalación de archivos sin control de versiones, como *dotnet.exe*, si ya existen.</span><span class="sxs-lookup"><span data-stu-id="3334c-179">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-UncachedFeed|--uncached-feed`**

  <span data-ttu-id="3334c-180">Permite cambiar la dirección URL de la fuente no almacenada en caché que este instalador utiliza.</span><span class="sxs-lookup"><span data-stu-id="3334c-180">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="3334c-181">Le recomendamos que no cambie este valor.</span><span class="sxs-lookup"><span data-stu-id="3334c-181">We recommended that you don't change this value.</span></span>

- **`-Verbose|--verbose`**

  <span data-ttu-id="3334c-182">Muestra la información de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="3334c-182">Displays diagnostics information.</span></span>

- **`-Version|--version <VERSION>`**

  <span data-ttu-id="3334c-183">Representa una versión de compilación concreta.</span><span class="sxs-lookup"><span data-stu-id="3334c-183">Represents a specific build version.</span></span> <span data-ttu-id="3334c-184">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="3334c-184">The possible values are:</span></span>

  - <span data-ttu-id="3334c-185">`latest`: compilación más reciente en el canal (utilizado con la opción `-Channel`).</span><span class="sxs-lookup"><span data-stu-id="3334c-185">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="3334c-186">`coherent`: compilación coherente más reciente en el canal; usa la última combinación de paquetes estables (usados con las opciones `-Channel` del nombre de la rama).</span><span class="sxs-lookup"><span data-stu-id="3334c-186">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="3334c-187">Versión de tres partes en formato X.Y.Z que representa una determinada versión de compilación; reemplaza a la opción `-Channel`.</span><span class="sxs-lookup"><span data-stu-id="3334c-187">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="3334c-188">Por ejemplo: `2.0.0-preview2-006120`.</span><span class="sxs-lookup"><span data-stu-id="3334c-188">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="3334c-189">Si no se especifica, el valor predeterminado de `-Version` es `latest`.</span><span class="sxs-lookup"><span data-stu-id="3334c-189">If not specified, `-Version` defaults to `latest`.</span></span>

## <a name="examples"></a><span data-ttu-id="3334c-190">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3334c-190">Examples</span></span>

- <span data-ttu-id="3334c-191">Instale la versión compatible a largo plazo más reciente en la ubicación predeterminada:</span><span class="sxs-lookup"><span data-stu-id="3334c-191">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="3334c-192">Windows:</span><span class="sxs-lookup"><span data-stu-id="3334c-192">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="3334c-193">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="3334c-193">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="3334c-194">Instale la versión más reciente del canal 3.1 en la ubicación especificada:</span><span class="sxs-lookup"><span data-stu-id="3334c-194">Install the latest version from 3.1 channel to the specified location:</span></span>

  <span data-ttu-id="3334c-195">Windows:</span><span class="sxs-lookup"><span data-stu-id="3334c-195">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  <span data-ttu-id="3334c-196">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="3334c-196">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- <span data-ttu-id="3334c-197">Instale la versión 3.0.0 del entorno de ejecución compartido:</span><span class="sxs-lookup"><span data-stu-id="3334c-197">Install the 3.0.0 version of the shared runtime:</span></span>

  <span data-ttu-id="3334c-198">Windows:</span><span class="sxs-lookup"><span data-stu-id="3334c-198">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  <span data-ttu-id="3334c-199">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="3334c-199">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
  ```

- <span data-ttu-id="3334c-200">Obtenga el script e instale la versión 2.1.2 detrás de un proxy corporativo (solo Windows):</span><span class="sxs-lookup"><span data-stu-id="3334c-200">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="3334c-201">Obtenga el script e instale ejemplos de una línea para la CLI de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="3334c-201">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="3334c-202">Windows:</span><span class="sxs-lookup"><span data-stu-id="3334c-202">Windows:</span></span>

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="3334c-203">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="3334c-203">macOS/Linux:</span></span>

  ```bash
  curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="3334c-204">Vea también</span><span class="sxs-lookup"><span data-stu-id="3334c-204">See also</span></span>

- [<span data-ttu-id="3334c-205">Versiones de .NET Core</span><span class="sxs-lookup"><span data-stu-id="3334c-205">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
- [<span data-ttu-id="3334c-206">Archivo de descarga del SDK y .NET Core Runtime</span><span class="sxs-lookup"><span data-stu-id="3334c-206">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
