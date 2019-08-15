---
title: Cómo crear un valor de configuración en tiempo de diseño
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: 35a7cd8cc1daaf76a25977751ddc9ec0709e5947
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69037907"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="2f0cf-102">Cómo Crear un nuevo valor de configuración en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="2f0cf-102">How To: Create a new setting at design time</span></span>

<span data-ttu-id="2f0cf-103">Puede crear un nuevo valor de configuración en tiempo de diseño mediante el diseñador de configuración de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2f0cf-103">You can create a new setting at design time by using the Settings designer in Visual Studio.</span></span> <span data-ttu-id="2f0cf-104">El diseñador de configuración es una interfaz de estilo de cuadrícula que le permite crear nuevas opciones de configuración y especificar propiedades para esas opciones.</span><span class="sxs-lookup"><span data-stu-id="2f0cf-104">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="2f0cf-105">Debe especificar el nombre, el valor, el tipo y el ámbito de la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="2f0cf-105">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="2f0cf-106">Una vez creada la configuración, se puede acceder a ella en el código.</span><span class="sxs-lookup"><span data-stu-id="2f0cf-106">Once a setting is created, it is accessible in code.</span></span>

## <a name="create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="2f0cf-107">Crear un nuevo valor de configuración en tiempo de diseño en C\#</span><span class="sxs-lookup"><span data-stu-id="2f0cf-107">Create a new setting at design time in C\#</span></span>

1. <span data-ttu-id="2f0cf-108">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2f0cf-108">Open Visual Studio.</span></span>

2. <span data-ttu-id="2f0cf-109">En **Explorador de soluciones**, expanda el nodo **propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="2f0cf-109">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>

3. <span data-ttu-id="2f0cf-110">Haga doble clic en el archivo. Settings en el que desea agregar un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="2f0cf-110">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="2f0cf-111">El nombre predeterminado de este archivo es Settings. Settings.</span><span class="sxs-lookup"><span data-stu-id="2f0cf-111">The default name for this file is Settings.settings.</span></span>

4. <span data-ttu-id="2f0cf-112">En el diseñador de configuración, establezca el **nombre**, el **valor**, el **tipo**y el **ámbito** de la configuración.</span><span class="sxs-lookup"><span data-stu-id="2f0cf-112">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="2f0cf-113">Cada fila representa una única configuración.</span><span class="sxs-lookup"><span data-stu-id="2f0cf-113">Each row represents a single setting.</span></span>

## <a name="create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="2f0cf-114">Crear un nuevo valor de configuración en tiempo de diseño en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2f0cf-114">Create a new setting at design time in Visual Basic</span></span>

1. <span data-ttu-id="2f0cf-115">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2f0cf-115">Open Visual Studio.</span></span>

2. <span data-ttu-id="2f0cf-116">En **Explorador de soluciones**, haga clic con el botón secundario en el nodo del proyecto y elija **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2f0cf-116">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>

3. <span data-ttu-id="2f0cf-117">En la página **propiedades** , seleccione la pestaña **configuración** .</span><span class="sxs-lookup"><span data-stu-id="2f0cf-117">In the **Properties** page, select the **Settings** tab.</span></span>

4. <span data-ttu-id="2f0cf-118">En el diseñador de configuración, establezca el **nombre**, el **valor**, el **tipo**y el **ámbito** de la configuración.</span><span class="sxs-lookup"><span data-stu-id="2f0cf-118">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="2f0cf-119">Cada fila representa una única configuración.</span><span class="sxs-lookup"><span data-stu-id="2f0cf-119">Each row represents a single setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f0cf-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f0cf-120">See also</span></span>

- [<span data-ttu-id="2f0cf-121">Utilizar valores de configuración de aplicación y de usuario</span><span class="sxs-lookup"><span data-stu-id="2f0cf-121">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="2f0cf-122">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="2f0cf-122">Application Settings Overview</span></span>](application-settings-overview.md)
- [<span data-ttu-id="2f0cf-123">Cómo: Cambiar el valor de una configuración existente en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="2f0cf-123">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)
