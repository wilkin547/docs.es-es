---
title: Control DataGridView
description: Aprenda a usar el `DataGridView` control para mostrar vistas de solo lectura de una pequeña cantidad de datos, o bien escale para mostrar vistas editables de conjuntos de datos muy grandes.
ms.date: 03/30/2017
helpviewer_keywords:
- tables [Windows Forms]
- data grids [Windows Forms
- data [Windows Forms], displaying in tabular format
- grid controls [Windows Forms]
- datasets [Windows Forms], user interface
- Windows Forms, displaying data
- data presentation
- tabular data [Windows Forms], displaying on Windows Forms
- datasets [Windows Forms], displaying in DataGridView control
- DataGridView control [Windows Forms]
ms.assetid: dbee73f2-bba6-4874-9389-cd21d44309be
ms.openlocfilehash: f9a45e8be7975697ca5c0d019c6bc4119f562aea
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325899"
---
# <a name="datagridview-control-windows-forms"></a><span data-ttu-id="b369a-103">DataGridView (Control, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b369a-103">DataGridView Control (Windows Forms)</span></span>
<span data-ttu-id="b369a-104">El control `DataGridView` proporciona una forma eficaz y flexible de mostrar datos en formato de tabla.</span><span class="sxs-lookup"><span data-stu-id="b369a-104">The `DataGridView` control provides a powerful and flexible way to display data in a tabular format.</span></span> <span data-ttu-id="b369a-105">Puede usar el control `DataGridView` para mostrar vistas de solo lectura de una pequeña cantidad de datos, o puede ampliarlo para mostrar vistas editables de conjuntos de datos muy grandes.</span><span class="sxs-lookup"><span data-stu-id="b369a-105">You can use the `DataGridView` control to show read-only views of a small amount of data, or you can scale it to show editable views of very large sets of data.</span></span>  
  
 <span data-ttu-id="b369a-106">Puede ampliar el control `DataGridView` de varias maneras para construir comportamientos personalizados en sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b369a-106">You can extend the `DataGridView` control in a number of ways to build custom behaviors into your applications.</span></span> <span data-ttu-id="b369a-107">Por ejemplo, puede especificar mediante programación sus propios algoritmos de ordenación y puede crear sus propios tipos de celdas.</span><span class="sxs-lookup"><span data-stu-id="b369a-107">For example, you can programmatically specify your own sorting algorithms, and you can create your own types of cells.</span></span> <span data-ttu-id="b369a-108">Puede personalizar fácilmente la apariencia del control `DataGridView` eligiendo entre varias propiedades.</span><span class="sxs-lookup"><span data-stu-id="b369a-108">You can easily customize the appearance of the `DataGridView` control by choosing among several properties.</span></span> <span data-ttu-id="b369a-109">Se pueden usar muchos tipos de almacenes de datos como origen de datos, o el control `DataGridView` puede funcionar sin ningún origen de datos enlazado a él.</span><span class="sxs-lookup"><span data-stu-id="b369a-109">Many types of data stores can be used as a data source, or the `DataGridView` control can operate with no data source bound to it.</span></span>  
  
 <span data-ttu-id="b369a-110">Los temas de esta sección describen los conceptos y técnicas que puede usar para crear características `DataGridView` en sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b369a-110">The topics in this section describe the concepts and techniques that you can use to build `DataGridView` features into your applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b369a-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b369a-111">In This Section</span></span>  
 [<span data-ttu-id="b369a-112">Información general del control DataGridView</span><span class="sxs-lookup"><span data-stu-id="b369a-112">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)  
 <span data-ttu-id="b369a-113">Proporciona temas que describen los arquitectura y los conceptos fundamentales del control `DataGridView` de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b369a-113">Provides topics that describe the architecture and core concepts of the Windows Forms `DataGridView` control.</span></span>  
  
 [<span data-ttu-id="b369a-114">Funcionalidad predeterminada en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b369a-114">Default Functionality in the Windows Forms DataGridView Control</span></span>](default-functionality-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="b369a-115">Describe la apariencia y el comportamiento predeterminados del control `DataGridView` de Windows Forms cuándo está enlazado a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b369a-115">Describes the default appearance and behavior of the Windows Forms `DataGridView` control when it is bound to a data source.</span></span>  
  
 [<span data-ttu-id="b369a-116">Tipos de columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b369a-116">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="b369a-117">Describe los tipos de columna en el control `DataGridView` de Windows Forms que se usan para mostrar datos y permitir a los usuarios modificar o agregar datos.</span><span class="sxs-lookup"><span data-stu-id="b369a-117">Describes the column types in the Windows Forms `DataGridView` control used to display data and allow users to modify or add data.</span></span>  
  
 [<span data-ttu-id="b369a-118">Características básicas de columnas, filas y celdas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b369a-118">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="b369a-119">Proporciona temas que describen las propiedades de celda, fila y columna que se usan habitualmente.</span><span class="sxs-lookup"><span data-stu-id="b369a-119">Provides topics that describe commonly-used cell, row, and column properties.</span></span>  
  
 [<span data-ttu-id="b369a-120">Estilo y formato básicos del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b369a-120">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="b369a-121">Proporciona temas que describen cómo modificar la apariencia básica del control y el formato de presentación de los datos de celda.</span><span class="sxs-lookup"><span data-stu-id="b369a-121">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
 [<span data-ttu-id="b369a-122">Mostrar datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b369a-122">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="b369a-123">Proporciona temas que describen cómo rellenar el control con datos manualmente o desde un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="b369a-123">Provides topics that describe how to populate the control with data either manually, or from an external data source.</span></span>  
  
 [<span data-ttu-id="b369a-124">Cambiar el tamaño de columnas y filas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b369a-124">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="b369a-125">Proporciona temas que describen cómo ajustar automáticamente el tamaño de las filas y columnas al contenido de la celda o al ancho disponible del control.</span><span class="sxs-lookup"><span data-stu-id="b369a-125">Provides topics that describe how the size of rows and columns can be adjusted automatically to fit cell content or to fit the available width of the control.</span></span>  
  
 [<span data-ttu-id="b369a-126">Ordenar datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b369a-126">Sorting Data in the Windows Forms DataGridView Control</span></span>](sorting-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="b369a-127">Proporciona temas que describen las características de ordenación en el control.</span><span class="sxs-lookup"><span data-stu-id="b369a-127">Provides topics that describe the sorting features in the control.</span></span>  
  
 [<span data-ttu-id="b369a-128">Entrada de datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b369a-128">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="b369a-129">Proporciona temas que describen cómo cambiar la forma en que los usuarios agregan y modifican datos en el control.</span><span class="sxs-lookup"><span data-stu-id="b369a-129">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
 [<span data-ttu-id="b369a-130">Selección y uso del Portapapeles con el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b369a-130">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="b369a-131">Proporciona temas que describen las características de selección de celdas, filas y columnas en el control.</span><span class="sxs-lookup"><span data-stu-id="b369a-131">Provides topics that describe the cell, row, and column selection features in the control.</span></span>  
  
 [<span data-ttu-id="b369a-132">Programar con celdas, filas y columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b369a-132">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 <span data-ttu-id="b369a-133">Proporciona temas que describen cómo programar con objetos de columna, fila y celda.</span><span class="sxs-lookup"><span data-stu-id="b369a-133">Provides topics that describe how to program with cell, row, and column objects.</span></span>  
  
 [<span data-ttu-id="b369a-134">Personalizar el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b369a-134">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="b369a-135">Proporciona temas que describen el dibujo personalizado de celdas y filas de `DataGridView`, y la creación de tipos derivados de celda, columna y fila.</span><span class="sxs-lookup"><span data-stu-id="b369a-135">Provides topics that describe custom painting `DataGridView` cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="b369a-136">Ajuste del rendimiento del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b369a-136">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="b369a-137">Proporciona temas que describen cómo usar eficazmente el control para evitar problemas de rendimiento cuando se trabaja con grandes cantidades de datos.</span><span class="sxs-lookup"><span data-stu-id="b369a-137">Provides topics that describe how to use the control efficiently to avoid performance problems when working with large amounts of data.</span></span>  
  
 [<span data-ttu-id="b369a-138">Control predeterminado de teclado y mouse en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b369a-138">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="b369a-139">Describe cómo los usuarios pueden interactuar con el control `DataGridView` mediante un teclado y un mouse.</span><span class="sxs-lookup"><span data-stu-id="b369a-139">Describes how users can interact with the `DataGridView` control through a keyboard and a mouse.</span></span>  
  
 [<span data-ttu-id="b369a-140">Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b369a-140">Differences Between the Windows Forms DataGridView and DataGrid Controls</span></span>](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)  
 <span data-ttu-id="b369a-141">Describe cómo el control `DataGridView` mejora y reemplaza el control <xref:System.Windows.Forms.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="b369a-141">Describes how the `DataGridView` control improves upon and replaces the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
 <span data-ttu-id="b369a-142">Vea también [usar el diseñador con el control DataGridView Windows Forms](using-the-designer-with-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="b369a-142">Also see [Using the Designer with the Windows Forms DataGridView Control](using-the-designer-with-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b369a-143">Referencia</span><span class="sxs-lookup"><span data-stu-id="b369a-143">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="b369a-144">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="b369a-144">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="b369a-145">Proporciona documentación de referencia para el componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="b369a-145">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="b369a-146">El control <xref:System.Windows.Forms.DataGridView> y el componente <xref:System.Windows.Forms.BindingSource> están diseñados para funcionar en estrecha colaboración.</span><span class="sxs-lookup"><span data-stu-id="b369a-146">The <xref:System.Windows.Forms.DataGridView> control and the <xref:System.Windows.Forms.BindingSource> component are designed to work closely together.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b369a-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="b369a-147">See also</span></span>

- [<span data-ttu-id="b369a-148">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b369a-148">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
