---
description: 'Más información sobre: creación de actividades de flujo de trabajo mediante la clase Activity'
title: Crear actividades de flujo de trabajo mediante la clase Activity
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: 0d3ffc88bacfd941dfa0c853991bf72045468323
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754945"
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a><span data-ttu-id="ed4be-103">Crear actividades de flujo de trabajo mediante la clase Activity</span><span class="sxs-lookup"><span data-stu-id="ed4be-103">Workflow Activity Authoring Using the Activity Class</span></span>

<span data-ttu-id="ed4be-104">La manera más básica de crear una actividad mediante Windows Workflow Foundation (WF) en [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] es crear una clase que herede de <xref:System.Activities.Activity> que crea la funcionalidad ensamblando actividades o actividades personalizadas desde la [biblioteca de actividades integrada](net-framework-4-5-built-in-activity-library.md).</span><span class="sxs-lookup"><span data-stu-id="ed4be-104">The most basic way to create an activity using Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] is to create a class that inherits from <xref:System.Activities.Activity> that creates functionality by assembling custom activities or activities from the [Built-In Activity Library](net-framework-4-5-built-in-activity-library.md).</span></span> <span data-ttu-id="ed4be-105">En este tema se muestra cómo crear una actividad que escribe dos mensajes en la consola.</span><span class="sxs-lookup"><span data-stu-id="ed4be-105">This topic demonstrates how to create an activity that writes two messages to the console.</span></span>

### <a name="to-create-a-custom-activity-using-the-activity-designer"></a><span data-ttu-id="ed4be-106">Para crear una actividad personalizada mediante el diseñador de actividad</span><span class="sxs-lookup"><span data-stu-id="ed4be-106">To create a custom Activity using the activity designer</span></span>

1. <span data-ttu-id="ed4be-107">Abra Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="ed4be-107">Open Visual Studio 2012.</span></span>

2. <span data-ttu-id="ed4be-108">Seleccione Archivo, Nuevo, Proyecto.</span><span class="sxs-lookup"><span data-stu-id="ed4be-108">Select File, New, Project.</span></span> <span data-ttu-id="ed4be-109">Seleccione **flujo de trabajo 4,0** en **Visual C#** en la ventana **tipos de proyecto** y seleccione el nodo **V2010** .</span><span class="sxs-lookup"><span data-stu-id="ed4be-109">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="ed4be-110">Seleccione **biblioteca de actividades** en la ventana **plantillas** .</span><span class="sxs-lookup"><span data-stu-id="ed4be-110">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="ed4be-111">Dé al nuevo proyecto el nombre "HelloActivity".</span><span class="sxs-lookup"><span data-stu-id="ed4be-111">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="ed4be-112">Abra la nueva actividad.</span><span class="sxs-lookup"><span data-stu-id="ed4be-112">Open the new activity.</span></span>  <span data-ttu-id="ed4be-113">Arrastre una actividad <xref:System.Activities.Statements.Sequence> desde el cuadro de herramientas a la superficie del diseñador.</span><span class="sxs-lookup"><span data-stu-id="ed4be-113">Drag a <xref:System.Activities.Statements.Sequence> activity from the toolbox onto the designer surface.</span></span>

4. <span data-ttu-id="ed4be-114">Arrastre una actividad <xref:System.Activities.Statements.WriteLine> a la actividad <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="ed4be-114">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="ed4be-115">Escriba `"Hello World"` (con comillas) en el campo de **texto** .</span><span class="sxs-lookup"><span data-stu-id="ed4be-115">Enter `"Hello World"` (with quotes) into the **Text** field.</span></span>

5. <span data-ttu-id="ed4be-116">Arrastre una segunda actividad <xref:System.Activities.Statements.WriteLine> a la actividad <xref:System.Activities.Statements.Sequence>, debajo de la primera.</span><span class="sxs-lookup"><span data-stu-id="ed4be-116">Drag a second <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity, below the first one.</span></span> <span data-ttu-id="ed4be-117">Escriba `"Goodbye"` (con comillas) en el campo de **texto** .</span><span class="sxs-lookup"><span data-stu-id="ed4be-117">Enter `"Goodbye"` (with quotes) into the **Text** field.</span></span>
