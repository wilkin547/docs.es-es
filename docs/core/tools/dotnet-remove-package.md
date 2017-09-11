---
title: 'Comando dotnet remove package: CLI de .NET Core'
description: "El comando dotnet remove package constituye una opción práctica para quitar la referencia de paquete NuGet de un proyecto."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 4167f5465571259975572669e27f20c586b910da
ms.contentlocale: es-es
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-remove-package"></a><span data-ttu-id="01cba-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="01cba-103">dotnet remove package</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="01cba-104">Nombre</span><span class="sxs-lookup"><span data-stu-id="01cba-104">Name</span></span>

<span data-ttu-id="01cba-105">`dotnet remove package`: quita la referencia de paquete de un archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="01cba-105">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="01cba-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="01cba-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="01cba-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="01cba-107">Description</span></span>

<span data-ttu-id="01cba-108">El comando `dotnet remove package` constituye una opción práctica para quitar una referencia de paquete de NuGet de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="01cba-108">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="01cba-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="01cba-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="01cba-110">Especifica el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="01cba-110">Specifies the project file.</span></span> <span data-ttu-id="01cba-111">Si no se especifica, el comando buscará uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="01cba-111">If not specified, the command will search the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="01cba-112">La referencia de paquete que hay que quitar.</span><span class="sxs-lookup"><span data-stu-id="01cba-112">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="01cba-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="01cba-113">Options</span></span>

`-h|--help`

<span data-ttu-id="01cba-114">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="01cba-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="01cba-115">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="01cba-115">Examples</span></span>

<span data-ttu-id="01cba-116">Quita el paquete de NuGet `Newtonsoft.Json` de un proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="01cba-116">Removes `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

`dotnet remove package Newtonsoft.Json`

