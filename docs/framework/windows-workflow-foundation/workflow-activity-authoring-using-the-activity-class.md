---
title: Crear actividades de flujo de trabajo mediante la clase Activity
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 517e646c8a84ed4374c01da974d952d4f50a4e22
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a><span data-ttu-id="91688-102">Crear actividades de flujo de trabajo mediante la clase Activity</span><span class="sxs-lookup"><span data-stu-id="91688-102">Workflow Activity Authoring Using the Activity Class</span></span>
<span data-ttu-id="91688-103">La manera más sencilla de crear una actividad utilizando Windows Workflow Foundation (WF) en [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] consiste en crear una clase que hereda de <xref:System.Activities.Activity> que crea la funcionalidad ensamblando personalizado actividades o actividades de la [integrada Biblioteca de actividades](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md).</span><span class="sxs-lookup"><span data-stu-id="91688-103">The most basic way to create an activity using Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] is to create a class that inherits from <xref:System.Activities.Activity> that creates functionality by assembling custom activities or activities from the [Built-In Activity Library](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md).</span></span> <span data-ttu-id="91688-104">En este tema se muestra cómo crear una actividad que escribe dos mensajes en la consola.</span><span class="sxs-lookup"><span data-stu-id="91688-104">This topic demonstrates how to create an activity that writes two messages to the console.</span></span>  
  
### <a name="to-create-a-custom-activity-using-the-activity-designer"></a><span data-ttu-id="91688-105">Para crear una actividad personalizada mediante el diseñador de actividad</span><span class="sxs-lookup"><span data-stu-id="91688-105">To create a custom Activity using the activity designer</span></span>  
  
1.  <span data-ttu-id="91688-106">Abra [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91688-106">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="91688-107">Seleccione Archivo, Nuevo, Proyecto.</span><span class="sxs-lookup"><span data-stu-id="91688-107">Select File, New, Project.</span></span> <span data-ttu-id="91688-108">Seleccione **Workflow 4.0** en **Visual C#** en el **tipos de proyecto** ventana y seleccione el **v2010** nodo.</span><span class="sxs-lookup"><span data-stu-id="91688-108">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="91688-109">Seleccione **biblioteca de actividades** en el **plantillas** ventana.</span><span class="sxs-lookup"><span data-stu-id="91688-109">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="91688-110">Dé al nuevo proyecto el nombre "HelloActivity".</span><span class="sxs-lookup"><span data-stu-id="91688-110">Name the new project HelloActivity.</span></span>  
  
3.  <span data-ttu-id="91688-111">Abra la nueva actividad.</span><span class="sxs-lookup"><span data-stu-id="91688-111">Open the new activity.</span></span>  <span data-ttu-id="91688-112">Arrastre una actividad <xref:System.Activities.Statements.Sequence> desde el cuadro de herramientas a la superficie del diseñador.</span><span class="sxs-lookup"><span data-stu-id="91688-112">Drag a <xref:System.Activities.Statements.Sequence> activity from the toolbox onto the designer surface.</span></span>  
  
4.  <span data-ttu-id="91688-113">Arrastre una actividad <xref:System.Activities.Statements.WriteLine> a la actividad <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="91688-113">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="91688-114">Escriba `"Hello World"` (con comillas) en el **texto** campo.</span><span class="sxs-lookup"><span data-stu-id="91688-114">Enter `"Hello World"` (with quotes) into the **Text** field.</span></span>  
  
5.  <span data-ttu-id="91688-115">Arrastre una segunda actividad <xref:System.Activities.Statements.WriteLine> a la actividad <xref:System.Activities.Statements.Sequence>, debajo de la primera.</span><span class="sxs-lookup"><span data-stu-id="91688-115">Drag a second <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity, below the first one.</span></span> <span data-ttu-id="91688-116">Escriba `"Goodbye"` (con comillas) en el **texto** campo.</span><span class="sxs-lookup"><span data-stu-id="91688-116">Enter `"Goodbye"` (with quotes) into the **Text** field.</span></span>
