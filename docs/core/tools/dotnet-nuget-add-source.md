---
title: Comando dotnet nuget add source
description: El comando dotnet nuget add source agrega un nuevo origen de paquete a los archivos de configuración de NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: df31a2eaba997d0e9fe4f4c2666052fd7c7c2f03
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102105056"
---
# <a name="dotnet-nuget-add-source"></a><span data-ttu-id="ce4ca-103">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="ce4ca-103">dotnet nuget add source</span></span>

<span data-ttu-id="ce4ca-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.1.200 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="ce4ca-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="ce4ca-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="ce4ca-105">Name</span></span>

<span data-ttu-id="ce4ca-106">`dotnet nuget add source`: agrega un origen de NuGet.</span><span class="sxs-lookup"><span data-stu-id="ce4ca-106">`dotnet nuget add source` - Add a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ce4ca-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="ce4ca-107">Synopsis</span></span>

```dotnetcli
dotnet nuget add source <PACKAGE_SOURCE_PATH> [--name <SOURCE_NAME>] [--username <USER>]
    [--password <PASSWORD>] [--store-password-in-clear-text]
    [--valid-authentication-types <TYPES>] [--configfile <FILE>]

dotnet nuget add source -h|--help
```

## <a name="description"></a><span data-ttu-id="ce4ca-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce4ca-108">Description</span></span>

<span data-ttu-id="ce4ca-109">El comando `dotnet nuget add source` agrega un nuevo origen de paquete a los archivos de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="ce4ca-109">The `dotnet nuget add source` command adds a new package source to your NuGet configuration files.</span></span>

> [!WARNING]
> <span data-ttu-id="ce4ca-110">Al agregar varios orígenes de paquete, tenga cuidado de no introducir una [vulnerabilidad de confusión de dependencias](https://aka.ms/pkg-sec-wp).</span><span class="sxs-lookup"><span data-stu-id="ce4ca-110">When adding multiple package sources, be careful not to introduce a [dependency confusion vulnerability](https://aka.ms/pkg-sec-wp).</span></span>

## <a name="arguments"></a><span data-ttu-id="ce4ca-111">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ce4ca-111">Arguments</span></span>

- **`PACKAGE_SOURCE_PATH`**

  <span data-ttu-id="ce4ca-112">Ruta de acceso al origen del paquete.</span><span class="sxs-lookup"><span data-stu-id="ce4ca-112">Path to the package source.</span></span>

## <a name="options"></a><span data-ttu-id="ce4ca-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="ce4ca-113">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="ce4ca-114">Archivo de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="ce4ca-114">The NuGet configuration file.</span></span> <span data-ttu-id="ce4ca-115">Si se especifica, solo se usará la configuración de este archivo.</span><span class="sxs-lookup"><span data-stu-id="ce4ca-115">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="ce4ca-116">Si no se especifica, se utilizará la jerarquía de archivos de configuración del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="ce4ca-116">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="ce4ca-117">Para más información, consulte [Configuraciones comunes de NuGet](/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="ce4ca-117">For more information, see [Common NuGet Configurations](/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`-n|--name <SOURCE_NAME>`**

  <span data-ttu-id="ce4ca-118">Nombre del origen.</span><span class="sxs-lookup"><span data-stu-id="ce4ca-118">Name of the source.</span></span>

- **`-p|--password <PASSWORD>`**

  <span data-ttu-id="ce4ca-119">Contraseña que se debe usar al conectarse a un origen autenticado.</span><span class="sxs-lookup"><span data-stu-id="ce4ca-119">Password to be used when connecting to an authenticated source.</span></span>

- **`--store-password-in-clear-text`**

  <span data-ttu-id="ce4ca-120">Deshabilita el cifrado de la contraseña para permitir el almacenamiento de las credenciales de origen del paquete portátil.</span><span class="sxs-lookup"><span data-stu-id="ce4ca-120">Enables storing portable package source credentials by disabling password encryption.</span></span>

- **`-u|--username <USER>`**

  <span data-ttu-id="ce4ca-121">Nombre de usuario que se usará al conectarse a un origen autenticado.</span><span class="sxs-lookup"><span data-stu-id="ce4ca-121">Username to be used when connecting to an authenticated source.</span></span>

- **`--valid-authentication-types <TYPES>`**

  <span data-ttu-id="ce4ca-122">Lista separada por comas de tipos de autenticación válidos para este origen.</span><span class="sxs-lookup"><span data-stu-id="ce4ca-122">Comma-separated list of valid authentication types for this source.</span></span> <span data-ttu-id="ce4ca-123">Establézcalo en `basic` si el servidor anuncia NTLM o Negotiate y las credenciales deben enviarse mediante el mecanismo básico, por ejemplo, cuando se usa una instancia de PAT con Azure DevOps Server local.</span><span class="sxs-lookup"><span data-stu-id="ce4ca-123">Set this to `basic` if the server advertises NTLM or Negotiate and your credentials must be sent using the Basic mechanism, for instance when using a PAT with on-premises Azure DevOps Server.</span></span> <span data-ttu-id="ce4ca-124">Otros valores válidos son `negotiate`, `kerberos`, `ntlm` y `digest`, pero es poco probable que estos valores sean útiles.</span><span class="sxs-lookup"><span data-stu-id="ce4ca-124">Other valid values include `negotiate`, `kerberos`, `ntlm`, and `digest`, but these values are unlikely to be useful.</span></span>

## <a name="examples"></a><span data-ttu-id="ce4ca-125">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ce4ca-125">Examples</span></span>

- <span data-ttu-id="ce4ca-126">Agregue `nuget.org` como origen:</span><span class="sxs-lookup"><span data-stu-id="ce4ca-126">Add `nuget.org` as a source:</span></span>

  ```dotnetcli
  dotnet nuget add source https://api.nuget.org/v3/index.json -n nuget.org
  ```

- <span data-ttu-id="ce4ca-127">Agregue `c:\packages` como origen local:</span><span class="sxs-lookup"><span data-stu-id="ce4ca-127">Add `c:\packages` as a local source:</span></span>

  ```dotnetcli
  dotnet nuget add source c:\packages
  ```

- <span data-ttu-id="ce4ca-128">Agregue un origen que necesite autenticación:</span><span class="sxs-lookup"><span data-stu-id="ce4ca-128">Add a source that needs authentication:</span></span>

  ```dotnetcli
  dotnet nuget add source https://someServer/myTeam -n myTeam -u myUsername -p myPassword --store-password-in-clear-text
  ```

- <span data-ttu-id="ce4ca-129">Agregue un origen que necesite autenticación (luego, pase a la instalación del proveedor de credenciales):</span><span class="sxs-lookup"><span data-stu-id="ce4ca-129">Add a source that needs authentication (then go install credential provider):</span></span>

  ```dotnetcli
  dotnet nuget add source https://azureartifacts.microsoft.com/myTeam -n myTeam
  ```

## <a name="see-also"></a><span data-ttu-id="ce4ca-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce4ca-130">See also</span></span>

- [<span data-ttu-id="ce4ca-131">Secciones de origen del paquete en archivos NuGet.config</span><span class="sxs-lookup"><span data-stu-id="ce4ca-131">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="ce4ca-132">Comando sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="ce4ca-132">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
