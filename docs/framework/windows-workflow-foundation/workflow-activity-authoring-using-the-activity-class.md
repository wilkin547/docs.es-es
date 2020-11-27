---
title: Crear actividades de flujo de trabajo mediante la clase Activity
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: 21f1c8b1249d41029fa7a19360e96ad866c823a7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293850"
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a><span data-ttu-id="3b752-102">Crear actividades de flujo de trabajo mediante la clase Activity</span><span class="sxs-lookup"><span data-stu-id="3b752-102">Workflow Activity Authoring Using the Activity Class</span></span>

<span data-ttu-id="3b752-103">La manera más básica de crear una actividad mediante Windows Workflow Foundation (WF) en [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] es crear una clase que herede de <xref:System.Activities.Activity> que crea la funcionalidad ensamblando actividades o actividades personalizadas desde la [biblioteca de actividades integrada](net-framework-4-5-built-in-activity-library.md).</span><span class="sxs-lookup"><span data-stu-id="3b752-103">The most basic way to create an activity using Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] is to create a class that inherits from <xref:System.Activities.Activity> that creates functionality by assembling custom activities or activities from the [Built-In Activity Library](net-framework-4-5-built-in-activity-library.md).</span></span> <span data-ttu-id="3b752-104">En este tema se muestra cómo crear una actividad que escribe dos mensajes en la consola.</span><span class="sxs-lookup"><span data-stu-id="3b752-104">This topic demonstrates how to create an activity that writes two messages to the console.</span></span>

### <a name="to-create-a-custom-activity-using-the-activity-designer"></a><span data-ttu-id="3b752-105">Para crear una actividad personalizada mediante el diseñador de actividad</span><span class="sxs-lookup"><span data-stu-id="3b752-105">To create a custom Activity using the activity designer</span></span>

1. <span data-ttu-id="3b752-106">Abra Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="3b752-106">Open Visual Studio 2012.</span></span>

2. <span data-ttu-id="3b752-107">Seleccione Archivo, Nuevo, Proyecto.</span><span class="sxs-lookup"><span data-stu-id="3b752-107">Select File, New, Project.</span></span> <span data-ttu-id="3b752-108">Seleccione **flujo de trabajo 4,0** en **Visual C#** en la ventana **tipos de proyecto** y seleccione el nodo **V2010** .</span><span class="sxs-lookup"><span data-stu-id="3b752-108">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="3b752-109">Seleccione **biblioteca de actividades** en la ventana **plantillas** .</span><span class="sxs-lookup"><span data-stu-id="3b752-109">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="3b752-110">Dé al nuevo proyecto el nombre "HelloActivity".</span><span class="sxs-lookup"><span data-stu-id="3b752-110">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="3b752-111">Abra la nueva actividad.</span><span class="sxs-lookup"><span data-stu-id="3b752-111">Open the new activity.</span></span>  <span data-ttu-id="3b752-112">Arrastre una actividad <xref:System.Activities.Statements.Sequence> desde el cuadro de herramientas a la superficie del diseñador.</span><span class="sxs-lookup"><span data-stu-id="3b752-112">Drag a <xref:System.Activities.Statements.Sequence> activity from the toolbox onto the designer surface.</span></span>

4. <span data-ttu-id="3b752-113">Arrastre una actividad <xref:System.Activities.Statements.WriteLine> a la actividad <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="3b752-113">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="3b752-114">Escriba `"Hello World"` (con comillas) en el campo de **texto** .</span><span class="sxs-lookup"><span data-stu-id="3b752-114">Enter `"Hello World"` (with quotes) into the **Text** field.</span></span>

5. <span data-ttu-id="3b752-115">Arrastre una segunda actividad <xref:System.Activities.Statements.WriteLine> a la actividad <xref:System.Activities.Statements.Sequence>, debajo de la primera.</span><span class="sxs-lookup"><span data-stu-id="3b752-115">Drag a second <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity, below the first one.</span></span> <span data-ttu-id="3b752-116">Escriba `"Goodbye"` (con comillas) en el campo de **texto** .</span><span class="sxs-lookup"><span data-stu-id="3b752-116">Enter `"Goodbye"` (with quotes) into the **Text** field.</span></span>
