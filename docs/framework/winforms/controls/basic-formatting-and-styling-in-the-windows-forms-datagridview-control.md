---
title: "Estilo y formato básicos del control DataGridView en formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1c6ae9c4159f8f9eafd73608e4fc3f4a646c1eaa
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="3e614-102">Estilo y formato básicos del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3e614-102">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="3e614-103">El `DataGridView` control facilita el proceso definir la apariencia básica de celdas y el formato de presentación de valores de celda.</span><span class="sxs-lookup"><span data-stu-id="3e614-103">The `DataGridView` control makes it easy to define the basic appearance of cells and the display formatting of cell values.</span></span> <span data-ttu-id="3e614-104">Puede definir la apariencia y el formato estilos para celdas individuales, para las celdas de columnas y filas concretas o para todas las celdas del control estableciendo las propiedades de la `DataGridViewCellStyle` objetos obtiene acceso a través de diversos `DataGridView` propiedades del control.</span><span class="sxs-lookup"><span data-stu-id="3e614-104">You can define appearance and formatting styles for individual cells, for cells in specific columns and rows, or for all cells in the control by setting the properties of the `DataGridViewCellStyle` objects accessed through various `DataGridView` control properties.</span></span> <span data-ttu-id="3e614-105">Además, puede modificar estos estilos dinámicamente en función de factores como el valor de celda controlando el `CellFormatting` eventos.</span><span class="sxs-lookup"><span data-stu-id="3e614-105">Additionally, you can modify these styles dynamically based on factors such as the cell value by handling the `CellFormatting` event.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3e614-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3e614-106">In This Section</span></span>  
 [<span data-ttu-id="3e614-107">Cambiar los estilos de borde y línea de la cuadrícula en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3e614-107">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)  
 <span data-ttu-id="3e614-108">Describe cómo establecer `DataGridView` propiedades que definen la apariencia del borde del control y las líneas de límite entre las celdas.</span><span class="sxs-lookup"><span data-stu-id="3e614-108">Describes how to set `DataGridView` properties that define the appearance of the control border and the boundary lines between cells.</span></span>  
  
 [<span data-ttu-id="3e614-109">Estilos de celda en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3e614-109">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3e614-110">Describe la `DataGridViewCellStyle` clase y cómo interactúan las propiedades de ese tipo para definir cómo se muestran las celdas del control.</span><span class="sxs-lookup"><span data-stu-id="3e614-110">Describes the `DataGridViewCellStyle` class and how properties of that type interact to define how cells are displayed in the control.</span></span>  
  
 [<span data-ttu-id="3e614-111">Establecer estilos de celda predeterminados para el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3e614-111">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3e614-112">Describe cómo usar `DataGridViewCellStyle` propiedades para definir la apariencia predeterminada de celdas en filas y columnas específicas y en todo el control.</span><span class="sxs-lookup"><span data-stu-id="3e614-112">Describes how to use `DataGridViewCellStyle` properties to define the default appearance of cells in specific rows and columns and in the entire control.</span></span>  
  
 [<span data-ttu-id="3e614-113">Dar formato a datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3e614-113">How to: Format Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3e614-114">Describe cómo dar formato a valores de presentación de celda con `DataGridViewCellStyle` propiedades.</span><span class="sxs-lookup"><span data-stu-id="3e614-114">Describes how to format cell display values using `DataGridViewCellStyle` properties.</span></span>  
  
 [<span data-ttu-id="3e614-115">Establecer estilos de colores y fuentes en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3e614-115">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3e614-116">Describe cómo utilizar el `DefaultCellStyle` propiedad para establecer básica mostrar características para todas las celdas del control.</span><span class="sxs-lookup"><span data-stu-id="3e614-116">Describes how to use the `DefaultCellStyle` property to set basic display characteristics for all cells in the control.</span></span>  
  
 [<span data-ttu-id="3e614-117">Establecer estilos de fila alternos para el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3e614-117">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3e614-118">Describe cómo crear un efecto de carta en el control con filas alternativas que se muestran de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="3e614-118">Describes how to create a ledger-like effect in the control using alternating rows that are displayed differently.</span></span>  
  
 [<span data-ttu-id="3e614-119">Utilizar la plantilla de filas para personalizar filas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3e614-119">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 <span data-ttu-id="3e614-120">Describe cómo utilizar el `RowTemplate` propiedad para establecer las propiedades de la fila que se usará para todas las filas en el control.</span><span class="sxs-lookup"><span data-stu-id="3e614-120">Describes how to use the `RowTemplate` property to set row properties that will be used for all rows in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3e614-121">Referencia</span><span class="sxs-lookup"><span data-stu-id="3e614-121">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="3e614-122">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="3e614-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <span data-ttu-id="3e614-123">Proporciona documentación de referencia para la <xref:System.Windows.Forms.DataGridViewCellStyle> clase.</span><span class="sxs-lookup"><span data-stu-id="3e614-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 <span data-ttu-id="3e614-124">Proporciona documentación de referencia para el <xref:System.Windows.Forms.DataGridView.CellFormatting> eventos.</span><span class="sxs-lookup"><span data-stu-id="3e614-124">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 <span data-ttu-id="3e614-125">Proporciona documentación de referencia para el <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="3e614-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3e614-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="3e614-126">Related Sections</span></span>  
 [<span data-ttu-id="3e614-127">Personalizar el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3e614-127">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3e614-128">Proporciona temas que describen el dibujo personalizado de celdas y filas de <xref:System.Windows.Forms.DataGridView>, y la creación de tipos derivados de celda, columna y fila.</span><span class="sxs-lookup"><span data-stu-id="3e614-128">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="3e614-129">Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3e614-129">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="3e614-130">Proporciona temas que describen normalmente usan las propiedades de celda, fila y columna.</span><span class="sxs-lookup"><span data-stu-id="3e614-130">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e614-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e614-131">See Also</span></span>  
 [<span data-ttu-id="3e614-132">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="3e614-132">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
