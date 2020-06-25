---
title: Cómo crear un valor de configuración en tiempo de diseño
description: Obtenga información sobre cómo crear un nuevo Windows Forms valor en tiempo de diseño mediante el diseñador de configuración de Visual Studio.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: ce37b42191999e29de2f2f7f7e7abfa0ec3f4d47
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325848"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="2753f-103">Cómo: crear un nuevo valor de configuración en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="2753f-103">How To: Create a new setting at design time</span></span>

<span data-ttu-id="2753f-104">Puede crear un nuevo valor de configuración en tiempo de diseño mediante el diseñador de configuración de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2753f-104">You can create a new setting at design time by using the Settings designer in Visual Studio.</span></span> <span data-ttu-id="2753f-105">El diseñador de configuración es una interfaz de estilo de cuadrícula que le permite crear nuevas opciones de configuración y especificar propiedades para esas opciones.</span><span class="sxs-lookup"><span data-stu-id="2753f-105">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="2753f-106">Debe especificar el nombre, el valor, el tipo y el ámbito de la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="2753f-106">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="2753f-107">Una vez creada la configuración, se puede acceder a ella en el código.</span><span class="sxs-lookup"><span data-stu-id="2753f-107">Once a setting is created, it is accessible in code.</span></span>

## <a name="create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="2753f-108">Crear un nuevo valor de configuración en tiempo de diseño en C\#</span><span class="sxs-lookup"><span data-stu-id="2753f-108">Create a new setting at design time in C\#</span></span>

1. <span data-ttu-id="2753f-109">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2753f-109">Open Visual Studio.</span></span>

2. <span data-ttu-id="2753f-110">En **Explorador de soluciones**, expanda el nodo **propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="2753f-110">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>

3. <span data-ttu-id="2753f-111">Haga doble clic en el archivo. Settings en el que desea agregar un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="2753f-111">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="2753f-112">El nombre predeterminado de este archivo es Settings. Settings.</span><span class="sxs-lookup"><span data-stu-id="2753f-112">The default name for this file is Settings.settings.</span></span>

4. <span data-ttu-id="2753f-113">En el diseñador de configuración, establezca el **nombre**, el **valor**, el **tipo**y el **ámbito** de la configuración.</span><span class="sxs-lookup"><span data-stu-id="2753f-113">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="2753f-114">Cada fila representa una única configuración.</span><span class="sxs-lookup"><span data-stu-id="2753f-114">Each row represents a single setting.</span></span>

## <a name="create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="2753f-115">Crear un nuevo valor de configuración en tiempo de diseño en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2753f-115">Create a new setting at design time in Visual Basic</span></span>

1. <span data-ttu-id="2753f-116">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2753f-116">Open Visual Studio.</span></span>

2. <span data-ttu-id="2753f-117">En **Explorador de soluciones**, haga clic con el botón secundario en el nodo del proyecto y elija **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2753f-117">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>

3. <span data-ttu-id="2753f-118">En la página **propiedades** , seleccione la pestaña **configuración** .</span><span class="sxs-lookup"><span data-stu-id="2753f-118">In the **Properties** page, select the **Settings** tab.</span></span>

4. <span data-ttu-id="2753f-119">En el diseñador de configuración, establezca el **nombre**, el **valor**, el **tipo**y el **ámbito** de la configuración.</span><span class="sxs-lookup"><span data-stu-id="2753f-119">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="2753f-120">Cada fila representa una única configuración.</span><span class="sxs-lookup"><span data-stu-id="2753f-120">Each row represents a single setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="2753f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="2753f-121">See also</span></span>

- [<span data-ttu-id="2753f-122">Utilizar valores de configuración de aplicación y de usuario</span><span class="sxs-lookup"><span data-stu-id="2753f-122">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="2753f-123">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="2753f-123">Application Settings Overview</span></span>](application-settings-overview.md)
- [<span data-ttu-id="2753f-124">Cómo cambiar el valor de una opción de configuración existente en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="2753f-124">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)
