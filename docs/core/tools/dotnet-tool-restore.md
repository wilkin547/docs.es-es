---
title: Comando dotnet tool restore
description: El comando dotnet tool restore instala en el equipo las herramientas locales de .NET Core que se encuentran en el ámbito del directorio actual.
ms.date: 02/14/2020
ms.openlocfilehash: 2900d431987661a9232ceed10d9a424093f8be45
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543855"
---
# <a name="dotnet-tool-restore"></a><span data-ttu-id="11ba3-103">dotnet tool restore</span><span class="sxs-lookup"><span data-stu-id="11ba3-103">dotnet tool restore</span></span>

<span data-ttu-id="11ba3-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="11ba3-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="11ba3-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="11ba3-105">Name</span></span>

<span data-ttu-id="11ba3-106">`dotnet tool restore`: instala en el equipo las herramientas locales de .NET Core que se encuentran en el ámbito del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="11ba3-106">`dotnet tool restore` - Installs on your machine the .NET Core local tools that are in scope for the current directory.</span></span>

## <a name="synopsis"></a><span data-ttu-id="11ba3-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="11ba3-107">Synopsis</span></span>

```dotnetcli
dotnet tool restore <PACKAGE_NAME> [--configfile] [--add-source] [tool-manifest] [--disable-parallel] [--ignore-failed-sources] [--no-cache] [-interactive] [-v|--verbosity]
dotnet tool restore <-h|--help>
```

## <a name="description"></a><span data-ttu-id="11ba3-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="11ba3-108">Description</span></span>

<span data-ttu-id="11ba3-109">El comando `dotnet tool restore` busca el archivo de manifiesto de las herramientas que está en el ámbito del directorio actual e instala las herramientas que se indican en él.</span><span class="sxs-lookup"><span data-stu-id="11ba3-109">The `dotnet tool restore` command finds the tool manifest file that is in scope for the current directory and installs the tools that are listed in it.</span></span> <span data-ttu-id="11ba3-110">Para obtener información sobre los archivos de manifiesto, vea [Instalación de una herramienta local](global-tools.md#install-a-local-tool) e [Invocación de una herramienta local](global-tools.md#invoke-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="11ba3-110">For information about manifest files, see [Install a local tool](global-tools.md#install-a-local-tool) and [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="11ba3-111">Argumentos</span><span class="sxs-lookup"><span data-stu-id="11ba3-111">Arguments</span></span>

- **`PACKAGE_NAME`**

<span data-ttu-id="11ba3-112">Nombre o identificador del paquete NuGet que contiene la herramienta de .NET Core que se quiere instalar.</span><span class="sxs-lookup"><span data-stu-id="11ba3-112">Name/ID of the NuGet package that contains the .NET Core tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="11ba3-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="11ba3-113">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="11ba3-114">El archivo de configuración de NuGet (*nuget.config*) que se usará.</span><span class="sxs-lookup"><span data-stu-id="11ba3-114">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="11ba3-115">Agrega un origen de paquete NuGet adicional que se usará durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="11ba3-115">Adds an additional NuGet package source to use during installation.</span></span>

- **`--tool-manifest <PATH>`**

  <span data-ttu-id="11ba3-116">Ruta de acceso al archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="11ba3-116">Path to the manifest file.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="11ba3-117">Impide que se restauren varios proyectos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="11ba3-117">Prevent restoring multiple projects in parallel.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="11ba3-118">Indica que los errores de origen de paquete se traten como advertencias.</span><span class="sxs-lookup"><span data-stu-id="11ba3-118">Treat package source failures as warnings.</span></span>

- **`--no-cache`**

  <span data-ttu-id="11ba3-119">Indica que no se almacenen en caché los paquetes ni las solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="11ba3-119">Do not cache packages and http requests.</span></span>

- **`--interactive`**

  <span data-ttu-id="11ba3-120">Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación).</span><span class="sxs-lookup"><span data-stu-id="11ba3-120">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span>

- **`-h|--help`**

  <span data-ttu-id="11ba3-121">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="11ba3-121">Prints out a short help for the command.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="11ba3-122">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="11ba3-122">Sets the verbosity level of the command.</span></span> <span data-ttu-id="11ba3-123">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="11ba3-123">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="example"></a><span data-ttu-id="11ba3-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="11ba3-124">Example</span></span>

- **`dotnet tool restore`**

  <span data-ttu-id="11ba3-125">Restaura las herramientas locales del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="11ba3-125">Restores local tools for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="11ba3-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="11ba3-126">See also</span></span>

- [<span data-ttu-id="11ba3-127">Herramientas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="11ba3-127">.NET Core tools</span></span>](global-tools.md)
