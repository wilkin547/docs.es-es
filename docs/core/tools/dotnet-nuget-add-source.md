---
title: Comando dotnet nuget add source
description: El comando dotnet nuget add source agrega un nuevo origen de paquete a los archivos de configuración de NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: c1e398699c7482a69b750cde718e6f9178b5c4bd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148493"
---
# <a name="dotnet-nuget-add-source"></a><span data-ttu-id="030bb-103">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="030bb-103">dotnet nuget add source</span></span>

<span data-ttu-id="030bb-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.1.200 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="030bb-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="030bb-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="030bb-105">Name</span></span>

<span data-ttu-id="030bb-106">`dotnet nuget add source`: agrega un origen de NuGet.</span><span class="sxs-lookup"><span data-stu-id="030bb-106">`dotnet nuget add source` - Add a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="030bb-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="030bb-107">Synopsis</span></span>

```dotnetcli
dotnet nuget add source <PACKAGE_SOURCE_PATH> [--name] [--username]
    [--password] [--store-password-in-clear-text] [--valid-authentication-types]
    [--configfile]
dotnet nuget add source [-h|--help]
```

## <a name="description"></a><span data-ttu-id="030bb-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="030bb-108">Description</span></span>

<span data-ttu-id="030bb-109">El comando `dotnet nuget add source` agrega un nuevo origen de paquete a los archivos de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="030bb-109">The `dotnet nuget add source` command adds a new package source to your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="030bb-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="030bb-110">Arguments</span></span>

- **`PACKAGE_SOURCE_PATH`**

  <span data-ttu-id="030bb-111">Ruta de acceso al origen del paquete.</span><span class="sxs-lookup"><span data-stu-id="030bb-111">Path to the package source.</span></span>

## <a name="options"></a><span data-ttu-id="030bb-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="030bb-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="030bb-113">Archivo de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="030bb-113">The NuGet configuration file.</span></span> <span data-ttu-id="030bb-114">Si se especifica, solo se usará la configuración de este archivo.</span><span class="sxs-lookup"><span data-stu-id="030bb-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="030bb-115">Si no se especifica, se utilizará la jerarquía de archivos de configuración del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="030bb-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="030bb-116">Para más información, consulte [Configuraciones comunes de NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="030bb-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`-n|--name`**

  <span data-ttu-id="030bb-117">Nombre del origen.</span><span class="sxs-lookup"><span data-stu-id="030bb-117">Name of the source.</span></span>

- **`-p|--password`**

  <span data-ttu-id="030bb-118">Contraseña que se debe usar al conectarse a un origen autenticado.</span><span class="sxs-lookup"><span data-stu-id="030bb-118">Password to be used when connecting to an authenticated source.</span></span>

- **`--store-password-in-clear-text`**

  <span data-ttu-id="030bb-119">Deshabilita el cifrado de la contraseña para permitir el almacenamiento de las credenciales de origen del paquete portátil.</span><span class="sxs-lookup"><span data-stu-id="030bb-119">Enables storing portable package source credentials by disabling password encryption.</span></span>

- **`-u|--username`**

  <span data-ttu-id="030bb-120">Nombre de usuario que se usará al conectarse a un origen autenticado.</span><span class="sxs-lookup"><span data-stu-id="030bb-120">Username to be used when connecting to an authenticated source.</span></span>

- **`--valid-authentication-types`**

  <span data-ttu-id="030bb-121">Lista separada por comas de tipos de autenticación válidos para este origen.</span><span class="sxs-lookup"><span data-stu-id="030bb-121">Comma-separated list of valid authentication types for this source.</span></span> <span data-ttu-id="030bb-122">Establézcalo en `basic` si el servidor anuncia NTLM o Negotiate y las credenciales deben enviarse mediante el mecanismo básico, por ejemplo, cuando se usa una instancia de PAT con Azure DevOps Server local.</span><span class="sxs-lookup"><span data-stu-id="030bb-122">Set this to `basic` if the server advertises NTLM or Negotiate and your credentials must be sent using the Basic mechanism, for instance when using a PAT with on-premises Azure DevOps Server.</span></span> <span data-ttu-id="030bb-123">Otros valores válidos son `negotiate`, `kerberos`, `ntlm` y `digest`, pero es poco probable que estos valores sean útiles.</span><span class="sxs-lookup"><span data-stu-id="030bb-123">Other valid values include `negotiate`, `kerberos`, `ntlm`, and `digest`, but these values are unlikely to be useful.</span></span>

## <a name="examples"></a><span data-ttu-id="030bb-124">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="030bb-124">Examples</span></span>

- <span data-ttu-id="030bb-125">Agregue `nuget.org` como origen:</span><span class="sxs-lookup"><span data-stu-id="030bb-125">Add `nuget.org` as a source:</span></span>

  ```dotnetcli
  dotnet nuget add source https://api.nuget.org/v3/index.json -n nuget.org
  ```

- <span data-ttu-id="030bb-126">Agregue `c:\packages` como origen local:</span><span class="sxs-lookup"><span data-stu-id="030bb-126">Add `c:\packages` as a local source:</span></span>

  ```dotnetcli
  dotnet nuget add source c:\packages
  ```

- <span data-ttu-id="030bb-127">Agregue un origen que necesite autenticación:</span><span class="sxs-lookup"><span data-stu-id="030bb-127">Add a source that needs authentication:</span></span>

  ```dotnetcli
  dotnet nuget add source https://someServer/myTeam -n myTeam -u myUsername -p myPassword --store-password-in-clear-text
  ```

- <span data-ttu-id="030bb-128">Agregue un origen que necesite autenticación (luego, pase a la instalación del proveedor de credenciales):</span><span class="sxs-lookup"><span data-stu-id="030bb-128">Add a source that needs authentication (then go install credential provider):</span></span>

  ```dotnetcli
  dotnet nuget add source https://azureartifacts.microsoft.com/myTeam -n myTeam
  ```

## <a name="see-also"></a><span data-ttu-id="030bb-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="030bb-129">See also</span></span>

- [<span data-ttu-id="030bb-130">Secciones de origen del paquete en archivos NuGet.config</span><span class="sxs-lookup"><span data-stu-id="030bb-130">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="030bb-131">Comando sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="030bb-131">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
