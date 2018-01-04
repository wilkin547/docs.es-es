---
title: StatusBar (Control de formularios Windows Forms)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- StatusBar control [Windows Forms]
- status bars [Windows Forms], creating
ms.assetid: 6f543e27-cf78-4b7f-b4d0-6a8030155d48
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 945d9a658dd3d75dd0edb9f4eaca78334ee4d652
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="statusbar-control-windows-forms"></a><span data-ttu-id="6093c-102">StatusBar (Control de formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="6093c-102">StatusBar Control (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="6093c-103">El control <xref:System.Windows.Forms.ToolStripStatusLabel> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.StatusBar>; sin embargo, el control <xref:System.Windows.Forms.StatusBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="6093c-103">The <xref:System.Windows.Forms.ToolStripStatusLabel> control replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control; however, the <xref:System.Windows.Forms.StatusBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="6093c-104">El control <xref:System.Windows.Forms.StatusBar> de Windows Forms se utiliza en los formularios como un área, que habitualmente se muestra en la parte inferior de una ventana, en la que una aplicación puede mostrar información de estado de diferentes tipos.</span><span class="sxs-lookup"><span data-stu-id="6093c-104">The Windows Forms <xref:System.Windows.Forms.StatusBar> control is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="6093c-105"><xref:System.Windows.Forms.StatusBar>los controles pueden tener paneles de barra de estado en ellos que mostrar iconos para indicar el estado o una serie de iconos de una animación que indican que un proceso de trabajo; Por ejemplo, Microsoft Word que indica el documento se está guardando.</span><span class="sxs-lookup"><span data-stu-id="6093c-105"><xref:System.Windows.Forms.StatusBar> controls can have status-bar panels on them that display icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6093c-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6093c-106">In This Section</span></span>  
 [<span data-ttu-id="6093c-107">Información general sobre StatusBar (Control)</span><span class="sxs-lookup"><span data-stu-id="6093c-107">StatusBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)  
 <span data-ttu-id="6093c-108">Presenta los conceptos generales de la <xref:System.Windows.Forms.StatusBar> control, que permite a los usuarios ver la información relevante para el control que tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="6093c-108">Introduces the general concepts of the <xref:System.Windows.Forms.StatusBar> control, which enables users to see relevant information for the control that has focus.</span></span>  
  
 [<span data-ttu-id="6093c-109">Agregar paneles a un control StatusBar</span><span class="sxs-lookup"><span data-stu-id="6093c-109">How to: Add Panels to a StatusBar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)  
 <span data-ttu-id="6093c-110">Explica cómo agregar paneles programables para la <xref:System.Windows.Forms.StatusBar> control.</span><span class="sxs-lookup"><span data-stu-id="6093c-110">Explains how to add programmable panels to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="6093c-111">Determinar en qué panel del control StatusBar de Windows Forms se hizo clic</span><span class="sxs-lookup"><span data-stu-id="6093c-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 <span data-ttu-id="6093c-112">Explica cómo controlar <xref:System.Windows.Forms.Control.Click> generan eventos desde el <xref:System.Windows.Forms.StatusBar> control.</span><span class="sxs-lookup"><span data-stu-id="6093c-112">Explains how to handle <xref:System.Windows.Forms.Control.Click> events raised from the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="6093c-113">Establecer el tamaño de los paneles de la barra de estado</span><span class="sxs-lookup"><span data-stu-id="6093c-113">How to: Set the Size of Status-Bar Panels</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)  
 <span data-ttu-id="6093c-114">Proporciona detalles sobre las propiedades que controlan el ancho y cambiar el tamaño de comportamiento de los paneles de la barra de estado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6093c-114">Gives details on the properties that control the width and resize behavior of status-bar panels at run time.</span></span>  
  
 [<span data-ttu-id="6093c-115">Tutorial: Actualizar la información de la barra de estado en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="6093c-115">Walkthrough: Updating Status Bar Information at Run Time</span></span>](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)  
 <span data-ttu-id="6093c-116">Explica cómo controlar mediante programación los datos dentro de los paneles de barra de estado.</span><span class="sxs-lookup"><span data-stu-id="6093c-116">Explains how to programmatically control the data within status-bar panels.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6093c-117">Referencia</span><span class="sxs-lookup"><span data-stu-id="6093c-117">Reference</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <span data-ttu-id="6093c-118">Contiene información de referencia sobre la clase y sus miembros.</span><span class="sxs-lookup"><span data-stu-id="6093c-118">Provides reference information on the class and its members.</span></span>  
  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <span data-ttu-id="6093c-119">Reemplaza y agrega funcionalidad a la <xref:System.Windows.Forms.StatusBar> control.</span><span class="sxs-lookup"><span data-stu-id="6093c-119">Replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6093c-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="6093c-120">Related Sections</span></span>  
 [<span data-ttu-id="6093c-121">Controles que se usan en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6093c-121">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="6093c-122">Proporciona una lista completa de controles de Windows Forms, con vínculos a información sobre su uso.</span><span class="sxs-lookup"><span data-stu-id="6093c-122">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
