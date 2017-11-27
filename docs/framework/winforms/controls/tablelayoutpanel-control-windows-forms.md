---
title: TableLayoutPanel (Control, formularios Windows Forms)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms]
- controls [Windows Forms], sizing
- sizing [Windows Forms], automatic
- layout [Windows Forms], TableLayoutPanel control
- automatic sizing
ms.assetid: f55175c6-424e-4782-a86e-3f79c1550235
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6f8f949edcf637f4b56ab0bcfdd121c5cb29e543
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="tablelayoutpanel-control-windows-forms"></a><span data-ttu-id="d6a8f-102">TableLayoutPanel (Control, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="d6a8f-102">TableLayoutPanel Control (Windows Forms)</span></span>
<span data-ttu-id="d6a8f-103">El control <xref:System.Windows.Forms.TableLayoutPanel> organiza su contenido en una cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="d6a8f-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="d6a8f-104">Como el diseño se realiza en tiempo de diseño y en tiempo de ejecución, puede cambiar dinámicamente cuando cambie el entorno de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d6a8f-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="d6a8f-105">Esto proporciona a los controles del panel la capacidad de ajustar el tamaño proporcionalmente para poder responder a cambios como el ajuste de tamaño del control primario o el cambio de longitud del texto debido a la localización.</span><span class="sxs-lookup"><span data-stu-id="d6a8f-105">This gives the controls in the panel the ability to proportionally resize, so it can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d6a8f-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d6a8f-106">In This Section</span></span>  
 [<span data-ttu-id="d6a8f-107">Información general sobre el control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d6a8f-107">TableLayoutPanel Control Overview</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-overview.md)  
 <span data-ttu-id="d6a8f-108">Presenta los conceptos generales del control <xref:System.Windows.Forms.TableLayoutPanel>, que permite crear un diseño de filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="d6a8f-108">Introduces the general concepts of the <xref:System.Windows.Forms.TableLayoutPanel> control, which allows you to create a layout with rows and columns.</span></span>  
  
 [<span data-ttu-id="d6a8f-109">Procedimientos recomendados para el control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d6a8f-109">Best Practices for the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="d6a8f-110">Describe recomendaciones para ayudarle a sacar el máximo partido de las características de diseño del control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="d6a8f-110">Outlines recommendations to help you get the most out of the layout features of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="d6a8f-111">Comportamiento de AutoSize en el control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d6a8f-111">AutoSize Behavior in the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/autosize-behavior-in-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="d6a8f-112">Explica las formas en que el control <xref:System.Windows.Forms.TableLayoutPanel> admite el comportamiento de ajuste automático de tamaño.</span><span class="sxs-lookup"><span data-stu-id="d6a8f-112">Explains the ways in which the <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior.</span></span>  
  
 [<span data-ttu-id="d6a8f-113">Delimitar y acoplar controles secundarios en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d6a8f-113">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 <span data-ttu-id="d6a8f-114">Muestra cómo delimitar y acoplar controles secundarios en un control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="d6a8f-114">Shows how to anchor and dock child controls in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="d6a8f-115">Crear un diseño de formularios Windows Forms que sea apropiado para la localización</span><span class="sxs-lookup"><span data-stu-id="d6a8f-115">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 <span data-ttu-id="d6a8f-116">Muestra cómo utilizar un control <xref:System.Windows.Forms.TableLayoutPanel> para crear un formulario que sea apropiado para la localización.</span><span class="sxs-lookup"><span data-stu-id="d6a8f-116">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to localization.</span></span>  
  
 [<span data-ttu-id="d6a8f-117">Crear Windows Forms de entrada de datos de tamaño variable</span><span class="sxs-lookup"><span data-stu-id="d6a8f-117">How to: Create a Resizable Windows Form for Data Entry</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-resizable-windows-form-for-data-entry.md)  
 <span data-ttu-id="d6a8f-118">Muestra cómo utilizar un control <xref:System.Windows.Forms.TableLayoutPanel> para crear un formulario que sea apropiado para el cambio de tamaño.</span><span class="sxs-lookup"><span data-stu-id="d6a8f-118">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to resizing.</span></span>  
  
1.  <span data-ttu-id="d6a8f-119">[Cómo: Alinear y expandir un control en un control TableLayoutPanel](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="d6a8f-119">[How to: Align and Stretch a Control in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span></span>  
  
2.  <span data-ttu-id="d6a8f-120">[Cómo: Abarcar filas y columnas en un control TableLayoutPanel](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="d6a8f-120">[How to: Span Rows and Columns in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span></span>  
  
3.  <span data-ttu-id="d6a8f-121">[Cómo: Editar columnas y filas en un control TableLayoutPanel](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="d6a8f-121">[How to: Edit Columns and Rows in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span></span>  
  
4.  <span data-ttu-id="d6a8f-122">[Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="d6a8f-122">[Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d6a8f-123">Referencia</span><span class="sxs-lookup"><span data-stu-id="d6a8f-123">Reference</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <span data-ttu-id="d6a8f-124">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="d6a8f-124">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 <xref:System.Windows.Forms.TableLayoutSettings>  
 <span data-ttu-id="d6a8f-125">Proporciona documentación de referencia para el tipo <xref:System.Windows.Forms.TableLayoutSettings>.</span><span class="sxs-lookup"><span data-stu-id="d6a8f-125">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutSettings> type.</span></span>  
  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <span data-ttu-id="d6a8f-126">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="d6a8f-126">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d6a8f-127">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="d6a8f-127">Related Sections</span></span>  
 [<span data-ttu-id="d6a8f-128">Localización</span><span class="sxs-lookup"><span data-stu-id="d6a8f-128">Localization</span></span>](../../../../docs/standard/globalization-localization/localization.md)  
 <span data-ttu-id="d6a8f-129">Proporciona información general sobre temas relacionados con la localización.</span><span class="sxs-lookup"><span data-stu-id="d6a8f-129">Provides an overview of topics relating to localization.</span></span>  
  
 <span data-ttu-id="d6a8f-130">Consulte también [localizar aplicaciones](http://msdn.microsoft.com/library/z68135h5\(v=vs.110\)) o [localizar aplicaciones](http://msdn.microsoft.com/library/z68135h5\(v=vs.120\))</span><span class="sxs-lookup"><span data-stu-id="d6a8f-130">Also see [Localizing Applications](http://msdn.microsoft.com/library/z68135h5\(v=vs.110\)) or [Localizing Applications](http://msdn.microsoft.com/library/z68135h5\(v=vs.120\))</span></span>
