---
title: 'NETSDK1004: archivo de recursos no encontrado'
description: Obtenga información sobre el error NETSDK1004 del SDK de .NET, que se produce cuando no se encuentra el archivo project.assets.json.
ms.topic: error-reference
ms.date: 01/29/2021
f1_keywords:
- NETSDK1004
ms.openlocfilehash: 8416063fe318106cbcb4dbccacef3ecaaff5bba2
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "99216440"
---
# <a name="netsdk1004-assets-file-not-found"></a><span data-ttu-id="9eeac-103">NETSDK1004: archivo de recursos no encontrado</span><span class="sxs-lookup"><span data-stu-id="9eeac-103">NETSDK1004: Assets file not found</span></span>

<span data-ttu-id="9eeac-104">**Este artículo se aplica a: ✔️** SDK de .NET Core 2.1.100 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="9eeac-104">**This article applies to:** ✔️ .NET Core 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="9eeac-105">NuGet escribe un archivo llamado *project.assets.json* en la carpeta *obj* y el SDK de .NET lo usa para obtener información sobre los paquetes que se van a pasar al compilador.</span><span class="sxs-lookup"><span data-stu-id="9eeac-105">NuGet writes a file named *project.assets.json* in the *obj* folder, and the .NET SDK uses it to get information about packages to pass into the compiler.</span></span> <span data-ttu-id="9eeac-106">Este error se produce cuando no se encuentra el archivo de recursos *project.assets.json* durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="9eeac-106">This error occurs when the assets file *project.assets.json* is not found during build.</span></span> <span data-ttu-id="9eeac-107">El mensaje de error es similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9eeac-107">The full error message is similar to the following example:</span></span>

<span data-ttu-id="9eeac-108">**NETSDK1004: No se ha encontrado el archivo de recursos "C:\ruta\a\project.assets.json". Ejecute una restauración de paquetes NuGet para generar el archivo.**</span><span class="sxs-lookup"><span data-stu-id="9eeac-108">**NETSDK1004: Assets file 'C:\path\to\project.assets.json' not found. Run a NuGet package restore to generate this file.**</span></span>

<span data-ttu-id="9eeac-109">Estas son algunas posibles causas del error:</span><span class="sxs-lookup"><span data-stu-id="9eeac-109">Here are some possible causes of the error:</span></span>

* <span data-ttu-id="9eeac-110">Está ejecutando el comando `dotnet build` desde una ruta de directorio que contiene un carácter `%`.</span><span class="sxs-lookup"><span data-stu-id="9eeac-110">You are running the `dotnet build` command from a directory path that contains a `%` character.</span></span> <span data-ttu-id="9eeac-111">Para resolver el error, quite el carácter `%` del nombre de la carpeta y vuelva a ejecutar `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="9eeac-111">To resolve the error, remove the `%` from the folder name, and rerun `dotnet build`.</span></span>
* <span data-ttu-id="9eeac-112">El sistema del proyecto no detectó ni restauró automáticamente un cambio en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9eeac-112">A change to the project file wasn't automatically detected and restored by the project system.</span></span> <span data-ttu-id="9eeac-113">Para resolver el error, abra un símbolo del sistema y ejecute `dotnet restore` en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9eeac-113">To resolve the error, open a command prompt and run `dotnet restore` on the project.</span></span>
* <span data-ttu-id="9eeac-114">Una versión anterior de Nuget.exe ha restaurado un proyecto por separado.</span><span class="sxs-lookup"><span data-stu-id="9eeac-114">A project was restored separately by an older version of Nuget.exe.</span></span> <span data-ttu-id="9eeac-115">Para resolver el error, abra un símbolo del sistema y ejecute `dotnet restore` en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9eeac-115">To resolve the error, open a command prompt and run `dotnet restore` on the project.</span></span>
* <span data-ttu-id="9eeac-116">Un error anterior, como NETSDK1045 (la versión del SDK que está usando no es compatible con la plataforma de destino del proyecto), impedía que NuGet creara el archivo de recursos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9eeac-116">An earlier error, such as NETSDK1045 (the version of the SDK you're using doesn't support the project's target framework), prevented NuGet from creating the project assets file.</span></span> <span data-ttu-id="9eeac-117">Para resolver el error NETSDK1004, resuelva el error anterior y, después, ejecute `dotnet restore` en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9eeac-117">To resolve the NETSDK1004 error, resolve the earlier error, and then run `dotnet restore` on the project.</span></span>
* <span data-ttu-id="9eeac-118">La CI de App Center está compilando un proyecto con un ensamblado externo que no está en NuGet.</span><span class="sxs-lookup"><span data-stu-id="9eeac-118">App Center CI is building a project that has an external assembly that is not in NuGet.</span></span> <span data-ttu-id="9eeac-119">Para resolver el error, use un paquete NuGet para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9eeac-119">To resolve the error, use a NuGet package for the assembly.</span></span>
