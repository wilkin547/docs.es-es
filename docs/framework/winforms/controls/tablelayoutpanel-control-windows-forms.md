---
title: TableLayoutPanel (Control)
ms.date: 03/30/2017
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms]
- controls [Windows Forms], sizing
- sizing [Windows Forms], automatic
- layout [Windows Forms], TableLayoutPanel control
- automatic sizing
ms.assetid: f55175c6-424e-4782-a86e-3f79c1550235
ms.openlocfilehash: 12b40d4ce47770b3ffe9bfdebca74eca4afd3dd1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735506"
---
# <a name="tablelayoutpanel-control-windows-forms"></a><span data-ttu-id="d1009-102">TableLayoutPanel (Control, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="d1009-102">TableLayoutPanel Control (Windows Forms)</span></span>
<span data-ttu-id="d1009-103">El control <xref:System.Windows.Forms.TableLayoutPanel> organiza su contenido en una cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="d1009-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="d1009-104">Como el diseño se realiza en tiempo de diseño y en tiempo de ejecución, puede cambiar dinámicamente cuando cambie el entorno de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d1009-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="d1009-105">Esto proporciona a los controles del panel la capacidad de ajustar el tamaño proporcionalmente para poder responder a cambios como el ajuste de tamaño del control primario o el cambio de longitud del texto debido a la localización.</span><span class="sxs-lookup"><span data-stu-id="d1009-105">This gives the controls in the panel the ability to proportionally resize, so it can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1009-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d1009-106">In This Section</span></span>  
 [<span data-ttu-id="d1009-107">Información general sobre el control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d1009-107">TableLayoutPanel Control Overview</span></span>](tablelayoutpanel-control-overview.md)  
 <span data-ttu-id="d1009-108">Presenta los conceptos generales del control <xref:System.Windows.Forms.TableLayoutPanel>, que permite crear un diseño de filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="d1009-108">Introduces the general concepts of the <xref:System.Windows.Forms.TableLayoutPanel> control, which allows you to create a layout with rows and columns.</span></span>  
  
 [<span data-ttu-id="d1009-109">Procedimientos recomendados para el control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d1009-109">Best Practices for the TableLayoutPanel Control</span></span>](best-practices-for-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="d1009-110">Describe recomendaciones para ayudarle a sacar el máximo partido de las características de diseño del control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="d1009-110">Outlines recommendations to help you get the most out of the layout features of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="d1009-111">Comportamiento de AutoSize en el control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d1009-111">AutoSize Behavior in the TableLayoutPanel Control</span></span>](autosize-behavior-in-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="d1009-112">Explica las formas en que el control <xref:System.Windows.Forms.TableLayoutPanel> admite el comportamiento de ajuste automático de tamaño.</span><span class="sxs-lookup"><span data-stu-id="d1009-112">Explains the ways in which the <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior.</span></span>  
  
 [<span data-ttu-id="d1009-113">Delimitar y acoplar controles secundarios en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d1009-113">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 <span data-ttu-id="d1009-114">Muestra cómo delimitar y acoplar controles secundarios en un control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="d1009-114">Shows how to anchor and dock child controls in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="d1009-115">Crear un diseño de formularios Windows Forms que sea apropiado para la localización</span><span class="sxs-lookup"><span data-stu-id="d1009-115">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 <span data-ttu-id="d1009-116">Muestra cómo utilizar un control <xref:System.Windows.Forms.TableLayoutPanel> para crear un formulario que sea apropiado para la localización.</span><span class="sxs-lookup"><span data-stu-id="d1009-116">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to localization.</span></span>  
  
 [<span data-ttu-id="d1009-117">Crear Windows Forms de entrada de datos de tamaño variable</span><span class="sxs-lookup"><span data-stu-id="d1009-117">How to: Create a Resizable Windows Form for Data Entry</span></span>](how-to-create-a-resizable-windows-form-for-data-entry.md)  
 <span data-ttu-id="d1009-118">Muestra cómo utilizar un control <xref:System.Windows.Forms.TableLayoutPanel> para crear un formulario que sea apropiado para el cambio de tamaño.</span><span class="sxs-lookup"><span data-stu-id="d1009-118">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to resizing.</span></span>  
  
1. [<span data-ttu-id="d1009-119">Cómo: Alinear y expandir un control en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d1009-119">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2. [<span data-ttu-id="d1009-120">Cómo: Abarcar filas y columnas en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d1009-120">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
3. [<span data-ttu-id="d1009-121">Cómo: Editar columnas y filas en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d1009-121">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
4. [<span data-ttu-id="d1009-122">Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d1009-122">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
  
## <a name="reference"></a><span data-ttu-id="d1009-123">Referencia</span><span class="sxs-lookup"><span data-stu-id="d1009-123">Reference</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <span data-ttu-id="d1009-124">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="d1009-124">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 <xref:System.Windows.Forms.TableLayoutSettings>  
 <span data-ttu-id="d1009-125">Proporciona documentación de referencia para el tipo <xref:System.Windows.Forms.TableLayoutSettings>.</span><span class="sxs-lookup"><span data-stu-id="d1009-125">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutSettings> type.</span></span>  
  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <span data-ttu-id="d1009-126">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="d1009-126">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d1009-127">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="d1009-127">Related Sections</span></span>  
 [<span data-ttu-id="d1009-128">Localización</span><span class="sxs-lookup"><span data-stu-id="d1009-128">Localization</span></span>](../../../standard/globalization-localization/localization.md)  
 <span data-ttu-id="d1009-129">Proporciona información general sobre temas relacionados con la localización.</span><span class="sxs-lookup"><span data-stu-id="d1009-129">Provides an overview of topics relating to localization.</span></span>  
  
 <span data-ttu-id="d1009-130">Consulte también [localizar aplicaciones](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/z68135h5(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="d1009-130">Also see [Localizing Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/z68135h5(v=vs.120)).</span></span>
