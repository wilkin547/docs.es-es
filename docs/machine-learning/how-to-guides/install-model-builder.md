---
title: Cómo instalar el Generador de modelos
description: Obtenga información sobre cómo instalar la herramienta Generador de modelos de ML.NET.
author: luisquintanilla
ms.author: luquinta
ms.date: 11/21/2019
ms.custom: mvc, how-to
ms.openlocfilehash: b87f712ad7a8b2229c1d42db4bad1fe511475ac7
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552941"
---
# <a name="how-to-install-mlnet-model-builder"></a><span data-ttu-id="d717d-103">Cómo instalar el Generador de modelos de ML.NET</span><span class="sxs-lookup"><span data-stu-id="d717d-103">How to install ML.NET Model Builder</span></span>

<span data-ttu-id="d717d-104">Obtenga información sobre cómo instalar el Generador de modelos de ML.NET para agregar aprendizaje automático a las aplicaciones. NET.</span><span class="sxs-lookup"><span data-stu-id="d717d-104">Learn how to install ML.NET Model Builder to add machine learning to your .NET applications.</span></span>

> [!NOTE]
> <span data-ttu-id="d717d-105">De momento, el Generador de modelos se encuentra en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="d717d-105">Model Builder is currently in Preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d717d-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d717d-106">Prerequisites</span></span>

- <span data-ttu-id="d717d-107">Visual Studio 2017, versión 15.9.12 o una posterior/Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="d717d-107">Visual Studio 2017 version 15.9.12 or later / Visual Studio 2019</span></span>
- <span data-ttu-id="d717d-108">SDK de .NET Core 2.1 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="d717d-108">.NET Core 2.1 SDK or later.</span></span>

> [!NOTE]
> <span data-ttu-id="d717d-109">El SDK de .NET Core 3.0 no se admite actualmente.</span><span class="sxs-lookup"><span data-stu-id="d717d-109">.NET Core 3.0 SDK is not currently supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="d717d-110">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="d717d-110">Limitations</span></span>

- <span data-ttu-id="d717d-111">La extensión Generador de modelos de ML.NET solo funciona actualmente en Visual Studio para Windows.</span><span class="sxs-lookup"><span data-stu-id="d717d-111">ML.NET Model Builder Extension currently only works on Visual Studio on Windows.</span></span>
- <span data-ttu-id="d717d-112">El límite del conjunto de datos de entrenamiento es de 1 GB</span><span class="sxs-lookup"><span data-stu-id="d717d-112">Training dataset limit of 1GB</span></span>
- <span data-ttu-id="d717d-113">SQL Server tiene un límite de 100 000 filas para el entrenamiento</span><span class="sxs-lookup"><span data-stu-id="d717d-113">SQL Server has a limit of 100 thousand rows for training</span></span>
- <span data-ttu-id="d717d-114">No admite Microsoft SQL Server Data Tools para Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="d717d-114">Microsoft SQL Server Data Tools for Visual Studio 2017 is not supported</span></span>

## <a name="install"></a><span data-ttu-id="d717d-115">Instalar</span><span class="sxs-lookup"><span data-stu-id="d717d-115">Install</span></span>

<span data-ttu-id="d717d-116">El Generador de modelos de ML.NET se puede instalar desde Visual Studio Marketplace o desde el propio Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d717d-116">ML.NET Model builder can be installed either through the Visual Studio Marketplace or from within Visual Studio.</span></span>

### <a name="visual-studio-marketplace"></a><span data-ttu-id="d717d-117">Visual Studio Marketplace</span><span class="sxs-lookup"><span data-stu-id="d717d-117">Visual Studio Marketplace</span></span>

1. <span data-ttu-id="d717d-118">Descargar desde [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span><span class="sxs-lookup"><span data-stu-id="d717d-118">Download from [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span></span>
1. <span data-ttu-id="d717d-119">Siga las indicaciones para instalar en la versión correspondiente de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d717d-119">Follow prompts to install onto respective Visual Studio version</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="d717d-120">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="d717d-120">Visual Studio 2017</span></span>

1. <span data-ttu-id="d717d-121">En la barra de menús, elija **Herramientas** > **Extensiones y actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="d717d-121">In the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![Cuadro de diálogo Abrir administrador de extensiones de VS2017](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="d717d-123">Dentro del símbolo del sistema de *Extensiones y actualizaciones*, seleccione el nodo *En línea*.</span><span class="sxs-lookup"><span data-stu-id="d717d-123">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="d717d-124">En la barra de búsqueda, busque *Generador de modelos de ML.NET* y en los resultados, seleccione Generador de modelos de ML.NET (versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="d717d-124">In the search bar, search for *ML.NET Model Builder* and from the results, select ML.NET Model Builder (Preview)</span></span>

    ![Cuadro de diálogo de búsqueda e instalación de la extensión del Generador de modelos en el Administrador de extensiones de VS2017](./media/install-model-builder/vs2017-install-model-builder.png)

1. <span data-ttu-id="d717d-126">Siga las indicaciones para completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="d717d-126">Follow the prompts to complete the installation</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="d717d-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="d717d-127">Visual Studio 2019</span></span>

1. <span data-ttu-id="d717d-128">En la barra de menús, elija **Extensiones** > **Administrar extensiones**.</span><span class="sxs-lookup"><span data-stu-id="d717d-128">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![Cuadro de diálogo Abrir administrador de extensiones de VS2019](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="d717d-130">Dentro del símbolo del sistema de *Extensiones y actualizaciones*, seleccione el nodo *En línea*.</span><span class="sxs-lookup"><span data-stu-id="d717d-130">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="d717d-131">Busque *Generador de modelos de ML.NET* en la barra de búsqueda y seleccione Generador de modelos de ML.NET (versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="d717d-131">Type *ML.NET Model Builder* into the search bar select ML.NET Model Builder (Preview)</span></span>

    ![Cuadro de diálogo de búsqueda e instalación de la extensión del Generador de modelos en el Administrador de extensiones de VS2019](./media/install-model-builder/vs2019-install-model-builder.png)

1. <span data-ttu-id="d717d-133">Siga las indicaciones para completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="d717d-133">Follow the prompts to complete the installation</span></span>

## <a name="uninstall"></a><span data-ttu-id="d717d-134">Desinstalar</span><span class="sxs-lookup"><span data-stu-id="d717d-134">Uninstall</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="d717d-135">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="d717d-135">Visual Studio 2017</span></span>

1. <span data-ttu-id="d717d-136">En la barra de menús, elija **Herramientas** > **Extensiones y actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="d717d-136">On the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![Abrir cuadro de diálogo de administración de extensiones de VS2017](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="d717d-138">Dentro del símbolo del sistema de *Extensiones y actualizaciones*, expanda el nodo *Instaladas* y seleccione *Herramientas*.</span><span class="sxs-lookup"><span data-stu-id="d717d-138">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="d717d-139">Seleccione Generador de modelos de ML.NET (versión preliminar) en la lista de herramientas y, a continuación, seleccione *Desinstalar*.</span><span class="sxs-lookup"><span data-stu-id="d717d-139">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![Cuadro de diálogo de búsqueda e instalación de la extensión del Generador de modelos en el Administrador de extensiones de VS2017](./media/install-model-builder/vs2017-uninstall-model-builder.png)

1. <span data-ttu-id="d717d-141">Siga las indicaciones para completar la desinstalación.</span><span class="sxs-lookup"><span data-stu-id="d717d-141">Follow the prompts to complete the uninstallation.</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="d717d-142">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="d717d-142">Visual Studio 2019</span></span>

1. <span data-ttu-id="d717d-143">En la barra de menús, elija **Extensiones** > **Administrar extensiones**.</span><span class="sxs-lookup"><span data-stu-id="d717d-143">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![Abrir cuadro de diálogo de administración de extensiones de VS2019](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="d717d-145">Dentro del símbolo del sistema de *Extensiones y actualizaciones*, expanda el nodo *Instaladas* y seleccione *Herramientas*.</span><span class="sxs-lookup"><span data-stu-id="d717d-145">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="d717d-146">Seleccione Generador de modelos de ML.NET (versión preliminar) en la lista de herramientas y, a continuación, seleccione *Desinstalar*.</span><span class="sxs-lookup"><span data-stu-id="d717d-146">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![Cuadro de diálogo de búsqueda e instalación de la extensión del Generador de modelos en el Administrador de extensiones de VS2019](./media/install-model-builder/vs2019-uninstall-model-builder.png)

1. <span data-ttu-id="d717d-148">Siga las indicaciones para completar la desinstalación.</span><span class="sxs-lookup"><span data-stu-id="d717d-148">Follow the prompts to complete the uninstallation.</span></span>

## <a name="upgrade"></a><span data-ttu-id="d717d-149">Actualización:</span><span class="sxs-lookup"><span data-stu-id="d717d-149">Upgrade</span></span>

<span data-ttu-id="d717d-150">El proceso de actualización es similar al proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="d717d-150">The upgrade process is similar to the installation process.</span></span> <span data-ttu-id="d717d-151">Descargue la versión más reciente desde Visual Studio Marketplace o use el Administrador de extensiones de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d717d-151">Either download the latest version from Visual Studio Marketplace or use the Extensions Manager in Visual Studio.</span></span>
