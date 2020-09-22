---
title: Comando dotnet nuget update source
description: El comando dotnet nuget update source actualiza un origen existente en los archivos de configuración de NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: a8658c78c095ad4b9272d97200e1d6466cbe658b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537859"
---
# <a name="dotnet-nuget-update-source"></a><span data-ttu-id="7e249-103">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="7e249-103">dotnet nuget update source</span></span>

<span data-ttu-id="7e249-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.1.200 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="7e249-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="7e249-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="7e249-105">Name</span></span>

<span data-ttu-id="7e249-106">`dotnet nuget update source`: actualiza un origen de NuGet.</span><span class="sxs-lookup"><span data-stu-id="7e249-106">`dotnet nuget update source` - Update a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7e249-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="7e249-107">Synopsis</span></span>

```dotnetcli
dotnet nuget update source <NAME> [--source <SOURCE>] [--username <USER>]
    [--password <PASSWORD>] [--store-password-in-clear-text]
    [--valid-authentication-types <TYPES>] [--configfile <FILE>]

dotnet nuget update source -h|--help
```

## <a name="description"></a><span data-ttu-id="7e249-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e249-108">Description</span></span>

<span data-ttu-id="7e249-109">El comando `dotnet nuget update source` actualiza un origen existente en los archivos de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="7e249-109">The `dotnet nuget update source` command updates an existing source in your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="7e249-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7e249-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="7e249-111">Nombre del origen.</span><span class="sxs-lookup"><span data-stu-id="7e249-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="7e249-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="7e249-112">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="7e249-113">Archivo de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="7e249-113">The NuGet configuration file.</span></span> <span data-ttu-id="7e249-114">Si se especifica, solo se usará la configuración de este archivo.</span><span class="sxs-lookup"><span data-stu-id="7e249-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="7e249-115">Si no se especifica, se utilizará la jerarquía de archivos de configuración del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="7e249-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="7e249-116">Para más información, consulte [Configuraciones comunes de NuGet](/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="7e249-116">For more information, see [Common NuGet Configurations](/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`-p|--password <PASSWORD>`**

  <span data-ttu-id="7e249-117">Contraseña que se debe usar al conectarse a un origen autenticado.</span><span class="sxs-lookup"><span data-stu-id="7e249-117">Password to be used when connecting to an authenticated source.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="7e249-118">Ruta de acceso al origen del paquete.</span><span class="sxs-lookup"><span data-stu-id="7e249-118">Path to the package source.</span></span>

- **`--store-password-in-clear-text`**

  <span data-ttu-id="7e249-119">Deshabilita el cifrado de la contraseña para permitir el almacenamiento de las credenciales de origen del paquete portátil.</span><span class="sxs-lookup"><span data-stu-id="7e249-119">Enables storing portable package source credentials by disabling password encryption.</span></span>

- **`-u|--username <USER>`**

  <span data-ttu-id="7e249-120">Nombre de usuario que se usará al conectarse a un origen autenticado.</span><span class="sxs-lookup"><span data-stu-id="7e249-120">Username to be used when connecting to an authenticated source.</span></span>

- **`--valid-authentication-types <TYPES>`**

  <span data-ttu-id="7e249-121">Lista separada por comas de tipos de autenticación válidos para este origen.</span><span class="sxs-lookup"><span data-stu-id="7e249-121">Comma-separated list of valid authentication types for this source.</span></span> <span data-ttu-id="7e249-122">Establézcalo en `basic` si el servidor anuncia NTLM o Negotiate y las credenciales deben enviarse mediante el mecanismo básico, por ejemplo, cuando se usa una instancia de PAT con Azure DevOps Server local.</span><span class="sxs-lookup"><span data-stu-id="7e249-122">Set this to `basic` if the server advertises NTLM or Negotiate and your credentials must be sent using the Basic mechanism, for instance when using a PAT with on-premises Azure DevOps Server.</span></span> <span data-ttu-id="7e249-123">Otros valores válidos son `negotiate`, `kerberos`, `ntlm` y `digest`, pero es poco probable que estos valores sean útiles.</span><span class="sxs-lookup"><span data-stu-id="7e249-123">Other valid values include `negotiate`, `kerberos`, `ntlm`, and `digest`, but these values are unlikely to be useful.</span></span>

## <a name="examples"></a><span data-ttu-id="7e249-124">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7e249-124">Examples</span></span>

- <span data-ttu-id="7e249-125">Actualice un origen con el nombre de `mySource`:</span><span class="sxs-lookup"><span data-stu-id="7e249-125">Update a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget update source mySource --source c:\packages
  ```

## <a name="see-also"></a><span data-ttu-id="7e249-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e249-126">See also</span></span>

- [<span data-ttu-id="7e249-127">Secciones de origen del paquete en archivos NuGet.config</span><span class="sxs-lookup"><span data-stu-id="7e249-127">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="7e249-128">Comando sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="7e249-128">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
