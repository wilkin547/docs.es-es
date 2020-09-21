---
title: Comando dotnet nuget add source
description: El comando dotnet nuget add source agrega un nuevo origen de paquete a los archivos de configuración de NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: b847d987de2d88cb3452d32d1bc84232a1e20b6e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537978"
---
# <a name="dotnet-nuget-add-source"></a><span data-ttu-id="e7891-103">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="e7891-103">dotnet nuget add source</span></span>

<span data-ttu-id="e7891-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.1.200 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="e7891-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="e7891-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="e7891-105">Name</span></span>

<span data-ttu-id="e7891-106">`dotnet nuget add source`: agrega un origen de NuGet.</span><span class="sxs-lookup"><span data-stu-id="e7891-106">`dotnet nuget add source` - Add a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e7891-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="e7891-107">Synopsis</span></span>

```dotnetcli
dotnet nuget add source <PACKAGE_SOURCE_PATH> [--name <SOURCE_NAME>] [--username <USER>]
    [--password <PASSWORD>] [--store-password-in-clear-text]
    [--valid-authentication-types <TYPES>] [--configfile <FILE>]

dotnet nuget add source -h|--help
```

## <a name="description"></a><span data-ttu-id="e7891-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7891-108">Description</span></span>

<span data-ttu-id="e7891-109">El comando `dotnet nuget add source` agrega un nuevo origen de paquete a los archivos de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="e7891-109">The `dotnet nuget add source` command adds a new package source to your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="e7891-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e7891-110">Arguments</span></span>

- **`PACKAGE_SOURCE_PATH`**

  <span data-ttu-id="e7891-111">Ruta de acceso al origen del paquete.</span><span class="sxs-lookup"><span data-stu-id="e7891-111">Path to the package source.</span></span>

## <a name="options"></a><span data-ttu-id="e7891-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="e7891-112">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="e7891-113">Archivo de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="e7891-113">The NuGet configuration file.</span></span> <span data-ttu-id="e7891-114">Si se especifica, solo se usará la configuración de este archivo.</span><span class="sxs-lookup"><span data-stu-id="e7891-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="e7891-115">Si no se especifica, se utilizará la jerarquía de archivos de configuración del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="e7891-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="e7891-116">Para más información, consulte [Configuraciones comunes de NuGet](/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="e7891-116">For more information, see [Common NuGet Configurations](/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`-n|--name <SOURCE_NAME>`**

  <span data-ttu-id="e7891-117">Nombre del origen.</span><span class="sxs-lookup"><span data-stu-id="e7891-117">Name of the source.</span></span>

- **`-p|--password <PASSWORD>`**

  <span data-ttu-id="e7891-118">Contraseña que se debe usar al conectarse a un origen autenticado.</span><span class="sxs-lookup"><span data-stu-id="e7891-118">Password to be used when connecting to an authenticated source.</span></span>

- **`--store-password-in-clear-text`**

  <span data-ttu-id="e7891-119">Deshabilita el cifrado de la contraseña para permitir el almacenamiento de las credenciales de origen del paquete portátil.</span><span class="sxs-lookup"><span data-stu-id="e7891-119">Enables storing portable package source credentials by disabling password encryption.</span></span>

- **`-u|--username <USER>`**

  <span data-ttu-id="e7891-120">Nombre de usuario que se usará al conectarse a un origen autenticado.</span><span class="sxs-lookup"><span data-stu-id="e7891-120">Username to be used when connecting to an authenticated source.</span></span>

- **`--valid-authentication-types <TYPES>`**

  <span data-ttu-id="e7891-121">Lista separada por comas de tipos de autenticación válidos para este origen.</span><span class="sxs-lookup"><span data-stu-id="e7891-121">Comma-separated list of valid authentication types for this source.</span></span> <span data-ttu-id="e7891-122">Establézcalo en `basic` si el servidor anuncia NTLM o Negotiate y las credenciales deben enviarse mediante el mecanismo básico, por ejemplo, cuando se usa una instancia de PAT con Azure DevOps Server local.</span><span class="sxs-lookup"><span data-stu-id="e7891-122">Set this to `basic` if the server advertises NTLM or Negotiate and your credentials must be sent using the Basic mechanism, for instance when using a PAT with on-premises Azure DevOps Server.</span></span> <span data-ttu-id="e7891-123">Otros valores válidos son `negotiate`, `kerberos`, `ntlm` y `digest`, pero es poco probable que estos valores sean útiles.</span><span class="sxs-lookup"><span data-stu-id="e7891-123">Other valid values include `negotiate`, `kerberos`, `ntlm`, and `digest`, but these values are unlikely to be useful.</span></span>

## <a name="examples"></a><span data-ttu-id="e7891-124">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e7891-124">Examples</span></span>

- <span data-ttu-id="e7891-125">Agregue `nuget.org` como origen:</span><span class="sxs-lookup"><span data-stu-id="e7891-125">Add `nuget.org` as a source:</span></span>

  ```dotnetcli
  dotnet nuget add source https://api.nuget.org/v3/index.json -n nuget.org
  ```

- <span data-ttu-id="e7891-126">Agregue `c:\packages` como origen local:</span><span class="sxs-lookup"><span data-stu-id="e7891-126">Add `c:\packages` as a local source:</span></span>

  ```dotnetcli
  dotnet nuget add source c:\packages
  ```

- <span data-ttu-id="e7891-127">Agregue un origen que necesite autenticación:</span><span class="sxs-lookup"><span data-stu-id="e7891-127">Add a source that needs authentication:</span></span>

  ```dotnetcli
  dotnet nuget add source https://someServer/myTeam -n myTeam -u myUsername -p myPassword --store-password-in-clear-text
  ```

- <span data-ttu-id="e7891-128">Agregue un origen que necesite autenticación (luego, pase a la instalación del proveedor de credenciales):</span><span class="sxs-lookup"><span data-stu-id="e7891-128">Add a source that needs authentication (then go install credential provider):</span></span>

  ```dotnetcli
  dotnet nuget add source https://azureartifacts.microsoft.com/myTeam -n myTeam
  ```

## <a name="see-also"></a><span data-ttu-id="e7891-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7891-129">See also</span></span>

- [<span data-ttu-id="e7891-130">Secciones de origen del paquete en archivos NuGet.config</span><span class="sxs-lookup"><span data-stu-id="e7891-130">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="e7891-131">Comando sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="e7891-131">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
