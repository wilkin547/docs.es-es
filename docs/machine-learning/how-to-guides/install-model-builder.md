---
title: Cómo instalar el Generador de modelos
description: Obtenga información sobre cómo instalar la herramienta Generador de modelos de ML.NET.
author: luisquintanilla
ms.author: luquinta
ms.date: 06/21/2019
ms.custom: mvc, how-to
ms.openlocfilehash: 54ab595c56f816517180aab48022c7df207fe84d
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410573"
---
# <a name="how-to-install-mlnet-model-builder"></a><span data-ttu-id="6f47f-103">Cómo instalar el Generador de modelos de ML.NET</span><span class="sxs-lookup"><span data-stu-id="6f47f-103">How to install ML.NET Model Builder</span></span>

<span data-ttu-id="6f47f-104">Obtenga información sobre cómo instalar el Generador de modelos de ML.NET para agregar aprendizaje automático a las aplicaciones. NET.</span><span class="sxs-lookup"><span data-stu-id="6f47f-104">Learn how to install ML.NET Model Builder to add machine learning to your .NET applications.</span></span>

> [!NOTE]
> <span data-ttu-id="6f47f-105">El Generador de modelos se encuentra en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="6f47f-105">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="6f47f-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6f47f-106">Pre-requisites</span></span>

- <span data-ttu-id="6f47f-107">Visual Studio 2017 15.9.12 o posterior / Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="6f47f-107">Visual Studio 2017 15.9.12 or later / Visual Studio 2019</span></span>
- <span data-ttu-id="6f47f-108">.NET Core 2.1 o SDK posterior</span><span class="sxs-lookup"><span data-stu-id="6f47f-108">.NET Core 2.1 or later SDK</span></span>

## <a name="limitations"></a><span data-ttu-id="6f47f-109">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="6f47f-109">Limitations</span></span>

- <span data-ttu-id="6f47f-110">La extensión Generador de modelos de ML.NET solo funciona actualmente en Visual Studio para Windows.</span><span class="sxs-lookup"><span data-stu-id="6f47f-110">ML.NET Model Builder Extension currently only works on Visual Studio on Windows.</span></span>
- <span data-ttu-id="6f47f-111">El límite del conjunto de datos de entrenamiento es de 1 GB</span><span class="sxs-lookup"><span data-stu-id="6f47f-111">Training dataset limit of 1GB</span></span>
- <span data-ttu-id="6f47f-112">SQL Server tiene un límite de 100 000 filas para el entrenamiento</span><span class="sxs-lookup"><span data-stu-id="6f47f-112">SQL Server has a limit of 100 thousand rows for training</span></span>
- <span data-ttu-id="6f47f-113">No admite Microsoft SQL Server Data Tools para Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="6f47f-113">Microsoft SQL Server Data Tools for Visual Studio 2017 is not supported</span></span>

## <a name="install"></a><span data-ttu-id="6f47f-114">Instalar</span><span class="sxs-lookup"><span data-stu-id="6f47f-114">Install</span></span>

<span data-ttu-id="6f47f-115">El Generador de modelos de ML.NET se puede instalar desde Visual Studio Marketplace o desde el propio Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6f47f-115">ML.NET Model builder can be installed either through the Visual Studio Marketplace or from within Visual Studio.</span></span> 

### <a name="visual-studio-marketplace"></a><span data-ttu-id="6f47f-116">Visual Studio Marketplace</span><span class="sxs-lookup"><span data-stu-id="6f47f-116">Visual Studio Marketplace</span></span>

1. <span data-ttu-id="6f47f-117">Descargar desde [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span><span class="sxs-lookup"><span data-stu-id="6f47f-117">Download from [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span></span>
1. <span data-ttu-id="6f47f-118">Siga las indicaciones para instalar en la versión correspondiente de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6f47f-118">Follow prompts to install onto respective Visual Studio version</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="6f47f-119">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="6f47f-119">Visual Studio 2017</span></span>

1. <span data-ttu-id="6f47f-120">En la barra de menús, elija **Herramientas** > **Extensiones y actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="6f47f-120">In the menu bar, select **Tools** > **Extensions and Updates**</span></span>
1. <span data-ttu-id="6f47f-121">Dentro del símbolo del sistema de *Extensiones y actualizaciones*, seleccione el nodo *En línea*.</span><span class="sxs-lookup"><span data-stu-id="6f47f-121">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="6f47f-122">En la barra de búsqueda, busque *Generador de modelos de ML.NET* y en los resultados, seleccione Generador de modelos de ML.NET (versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="6f47f-122">In the search bar, search for *ML.NET Model Builder* and from the results, select ML.NET Model Builder (Preview)</span></span>
1. <span data-ttu-id="6f47f-123">Siga las indicaciones para completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="6f47f-123">Follow the prompts to complete the installation</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="6f47f-124">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="6f47f-124">Visual Studio 2019</span></span>

1. <span data-ttu-id="6f47f-125">En la barra de menús, elija **Extensiones** > **Administrar extensiones**.</span><span class="sxs-lookup"><span data-stu-id="6f47f-125">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>
1. <span data-ttu-id="6f47f-126">Dentro del símbolo del sistema de *Extensiones y actualizaciones*, seleccione el nodo *En línea*.</span><span class="sxs-lookup"><span data-stu-id="6f47f-126">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="6f47f-127">Busque *Generador de modelos de ML.NET* en la barra de búsqueda y seleccione Generador de modelos de ML.NET (versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="6f47f-127">Type *ML.NET Model Builder* into the search bar select ML.NET Model Builder (Preview)</span></span>
1. <span data-ttu-id="6f47f-128">Siga las indicaciones para completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="6f47f-128">Follow the prompts to complete the installation</span></span>

## <a name="uninstall"></a><span data-ttu-id="6f47f-129">Desinstalar</span><span class="sxs-lookup"><span data-stu-id="6f47f-129">Uninstall</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="6f47f-130">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="6f47f-130">Visual Studio 2017</span></span>

1. <span data-ttu-id="6f47f-131">En la barra de menús, elija **Herramientas** > **Extensiones y actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="6f47f-131">On the menu bar, select **Tools** > **Extensions and Updates**</span></span>
1. <span data-ttu-id="6f47f-132">Dentro del símbolo del sistema de *Extensiones y actualizaciones*, expanda el nodo *Instaladas* y seleccione *Herramientas*.</span><span class="sxs-lookup"><span data-stu-id="6f47f-132">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="6f47f-133">Seleccione Generador de modelos de ML.NET (versión preliminar) en la lista de herramientas y, a continuación, seleccione *Desinstalar*.</span><span class="sxs-lookup"><span data-stu-id="6f47f-133">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>
1. <span data-ttu-id="6f47f-134">Siga las indicaciones para completar la desinstalación.</span><span class="sxs-lookup"><span data-stu-id="6f47f-134">Follow the prompts to complete the uninstallation.</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="6f47f-135">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="6f47f-135">Visual Studio 2019</span></span>

1. <span data-ttu-id="6f47f-136">En la barra de menús, elija **Extensiones** > **Administrar extensiones**.</span><span class="sxs-lookup"><span data-stu-id="6f47f-136">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>
1. <span data-ttu-id="6f47f-137">Dentro del símbolo del sistema de *Extensiones y actualizaciones*, expanda el nodo *Instaladas* y seleccione *Herramientas*.</span><span class="sxs-lookup"><span data-stu-id="6f47f-137">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="6f47f-138">Seleccione Generador de modelos de ML.NET (versión preliminar) en la lista de herramientas y, a continuación, seleccione *Desinstalar*.</span><span class="sxs-lookup"><span data-stu-id="6f47f-138">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>
1. <span data-ttu-id="6f47f-139">Siga las indicaciones para completar la desinstalación.</span><span class="sxs-lookup"><span data-stu-id="6f47f-139">Follow the prompts to complete the uninstallation.</span></span>

## <a name="upgrade"></a><span data-ttu-id="6f47f-140">Actualizar</span><span class="sxs-lookup"><span data-stu-id="6f47f-140">Upgrade</span></span>

<span data-ttu-id="6f47f-141">El proceso de actualización es similar al proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="6f47f-141">The upgrade process is similar to the installation process.</span></span> <span data-ttu-id="6f47f-142">Descargue la versión más reciente desde Visual Studio Marketplace o use el Administrador de extensiones de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6f47f-142">Either download the latest version from Visual Studio Marketplace or use the Extensions Manager in Visual Studio.</span></span>
