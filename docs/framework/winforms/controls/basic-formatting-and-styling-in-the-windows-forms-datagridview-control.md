---
title: Formato y estilo básicos en el control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
ms.openlocfilehash: d295718b7bd4f3bc4c5f63b6e6cb911f733525fe
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732000"
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="51f65-102">Estilo y formato básicos del control DataGridView en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="51f65-102">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="51f65-103">El control `DataGridView` permite definir fácilmente la apariencia básica de las celdas y el formato de presentación de los valores de las celdas.</span><span class="sxs-lookup"><span data-stu-id="51f65-103">The `DataGridView` control makes it easy to define the basic appearance of cells and the display formatting of cell values.</span></span> <span data-ttu-id="51f65-104">Puede definir el aspecto y los estilos de formato para celdas individuales, para las celdas de columnas y filas concretas, o para todas las celdas del control estableciendo las propiedades del `DataGridViewCellStyle` objetos a los que se tiene acceso a través de diversas propiedades de control `DataGridView`.</span><span class="sxs-lookup"><span data-stu-id="51f65-104">You can define appearance and formatting styles for individual cells, for cells in specific columns and rows, or for all cells in the control by setting the properties of the `DataGridViewCellStyle` objects accessed through various `DataGridView` control properties.</span></span> <span data-ttu-id="51f65-105">Además, puede modificar estos estilos dinámicamente basándose en factores como el valor de la celda mediante el control del evento `CellFormatting`.</span><span class="sxs-lookup"><span data-stu-id="51f65-105">Additionally, you can modify these styles dynamically based on factors such as the cell value by handling the `CellFormatting` event.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="51f65-106">Esta sección</span><span class="sxs-lookup"><span data-stu-id="51f65-106">In This Section</span></span>  
 [<span data-ttu-id="51f65-107">Cambiar los estilos de borde y línea de la cuadrícula en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="51f65-107">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>](change-the-border-and-gridline-styles-in-the-datagrid.md)  
 <span data-ttu-id="51f65-108">Describe cómo establecer `DataGridView` propiedades que definen la apariencia del borde del control y las líneas de límite entre las celdas.</span><span class="sxs-lookup"><span data-stu-id="51f65-108">Describes how to set `DataGridView` properties that define the appearance of the control border and the boundary lines between cells.</span></span>  
  
 [<span data-ttu-id="51f65-109">Estilos de celda en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="51f65-109">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="51f65-110">Describe la clase `DataGridViewCellStyle` y cómo interactúan las propiedades de ese tipo para definir cómo se muestran las celdas en el control.</span><span class="sxs-lookup"><span data-stu-id="51f65-110">Describes the `DataGridViewCellStyle` class and how properties of that type interact to define how cells are displayed in the control.</span></span>  
  
 [<span data-ttu-id="51f65-111">Establecer estilos de celda predeterminados para el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="51f65-111">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="51f65-112">Describe cómo utilizar las propiedades de `DataGridViewCellStyle` para definir el aspecto predeterminado de las celdas en filas y columnas específicas y en todo el control.</span><span class="sxs-lookup"><span data-stu-id="51f65-112">Describes how to use `DataGridViewCellStyle` properties to define the default appearance of cells in specific rows and columns and in the entire control.</span></span>  
  
 [<span data-ttu-id="51f65-113">Dar formato a datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="51f65-113">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="51f65-114">Describe cómo dar formato a los valores de presentación de la celda mediante propiedades de `DataGridViewCellStyle`.</span><span class="sxs-lookup"><span data-stu-id="51f65-114">Describes how to format cell display values using `DataGridViewCellStyle` properties.</span></span>  
  
 [<span data-ttu-id="51f65-115">Establecer estilos de colores y fuentes en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="51f65-115">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="51f65-116">Describe cómo utilizar la propiedad `DefaultCellStyle` para establecer las características básicas de presentación de todas las celdas del control.</span><span class="sxs-lookup"><span data-stu-id="51f65-116">Describes how to use the `DefaultCellStyle` property to set basic display characteristics for all cells in the control.</span></span>  
  
 [<span data-ttu-id="51f65-117">Establecer estilos de fila alternos para el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="51f65-117">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="51f65-118">Describe cómo crear un efecto de libro de contabilidad en el control utilizando filas alternas que se muestran de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="51f65-118">Describes how to create a ledger-like effect in the control using alternating rows that are displayed differently.</span></span>  
  
 [<span data-ttu-id="51f65-119">Utilizar la plantilla de filas para personalizar filas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="51f65-119">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>](use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 <span data-ttu-id="51f65-120">Describe cómo utilizar la propiedad `RowTemplate` para establecer las propiedades de fila que se usarán para todas las filas del control.</span><span class="sxs-lookup"><span data-stu-id="51f65-120">Describes how to use the `RowTemplate` property to set row properties that will be used for all rows in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="51f65-121">Referencia</span><span class="sxs-lookup"><span data-stu-id="51f65-121">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="51f65-122">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="51f65-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <span data-ttu-id="51f65-123">Proporciona documentación de referencia para la clase <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="51f65-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 <span data-ttu-id="51f65-124">Proporciona documentación de referencia para el evento <xref:System.Windows.Forms.DataGridView.CellFormatting>.</span><span class="sxs-lookup"><span data-stu-id="51f65-124">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 <span data-ttu-id="51f65-125">Proporciona documentación de referencia para la propiedad <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="51f65-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="51f65-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="51f65-126">Related Sections</span></span>  
 [<span data-ttu-id="51f65-127">Personalizar el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="51f65-127">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="51f65-128">Proporciona temas que describen el dibujo personalizado de celdas y filas de <xref:System.Windows.Forms.DataGridView>, y la creación de tipos derivados de celda, columna y fila.</span><span class="sxs-lookup"><span data-stu-id="51f65-128">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="51f65-129">Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="51f65-129">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="51f65-130">Proporciona temas que describen las propiedades de celda, fila y columna que se usan habitualmente.</span><span class="sxs-lookup"><span data-stu-id="51f65-130">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51f65-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="51f65-131">See also</span></span>

- [<span data-ttu-id="51f65-132">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="51f65-132">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
