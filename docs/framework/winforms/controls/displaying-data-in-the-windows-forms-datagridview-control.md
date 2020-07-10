---
title: Mostrar datos en el control DataGridView
description: Aprenda a usar el control DataGridView Windows Forms para Mostrar datos de diversos orígenes de datos externos.
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], displaying data
- displaying data [Windows Forms], data grids
- DataGridView control [Windows Forms], displaying data
ms.assetid: b170b52a-2ebd-4948-ac2f-e52d494cebb2
ms.openlocfilehash: a0f3e6627290521b8c10477c31459f1486e79162
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174580"
---
# <a name="displaying-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="26179-103">Mostrar datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="26179-103">Displaying Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="26179-104">El `DataGridView` control se usa para mostrar los datos de diversos orígenes de datos externos.</span><span class="sxs-lookup"><span data-stu-id="26179-104">The `DataGridView` control is used to display data from a variety of external data sources.</span></span> <span data-ttu-id="26179-105">Como alternativa, puede Agregar filas y columnas al control y rellenarlas manualmente con los datos.</span><span class="sxs-lookup"><span data-stu-id="26179-105">Alternatively, you can add rows and columns to the control and manually populate it with data.</span></span>  
  
 <span data-ttu-id="26179-106">Al enlazar el control a un origen de datos, puede generar columnas automáticamente según el esquema del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="26179-106">When you bind the control to a data source, you can generate columns automatically based on the schema of the data source.</span></span> <span data-ttu-id="26179-107">Si estas columnas no aparecen exactamente como desea, puede ocultarlas, quitarlas o reorganizarlas.</span><span class="sxs-lookup"><span data-stu-id="26179-107">If these columns do not appear just as you want them to, you can hide, remove, or rearrange them.</span></span> <span data-ttu-id="26179-108">También puede Agregar columnas sin enlazar para Mostrar datos complementarios que no proceden del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="26179-108">You can also add unbound columns to display supplemental data that does not come from the data source.</span></span>  
  
 <span data-ttu-id="26179-109">Además, puede mostrar los datos mediante formatos estándar (como el formato de moneda), o puede personalizar el formato de presentación para presentar los datos, sin embargo, es necesario (por ejemplo, cambiar el color de fondo de los números negativos o reemplazar los valores de cadena con las imágenes correspondientes).</span><span class="sxs-lookup"><span data-stu-id="26179-109">Additionally, you can display your data using standard formats (such as currency format), or you can customize the display formatting to present your data however you need to (such as changing the background color for negative numbers, or replacing string values with corresponding images).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="26179-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="26179-110">In This Section</span></span>  
 [<span data-ttu-id="26179-111">Modos de presentación de datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="26179-111">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="26179-112">Describe las opciones para rellenar el control con datos.</span><span class="sxs-lookup"><span data-stu-id="26179-112">Describes the options for populating the control with data.</span></span>  
  
 [<span data-ttu-id="26179-113">Formato de datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="26179-113">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="26179-114">Describe las opciones para dar formato a los valores de presentación de la celda.</span><span class="sxs-lookup"><span data-stu-id="26179-114">Describes the options for formatting cell display values.</span></span>  
  
 [<span data-ttu-id="26179-115">Tutorial: Crear un control DataGridView sin enlazar en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="26179-115">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 <span data-ttu-id="26179-116">Describe cómo rellenar manualmente el control con datos.</span><span class="sxs-lookup"><span data-stu-id="26179-116">Describes how to manually populate the control with data.</span></span>  
  
 [<span data-ttu-id="26179-117">Procedimiento para enlazar datos al control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="26179-117">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="26179-118">Describe cómo rellenar el control con datos enlazándolo a un `BindingSource` que contiene información extraída de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="26179-118">Describes how to populate the control with data by binding it to a `BindingSource` that contains information pulled from a database.</span></span>  
  
 [<span data-ttu-id="26179-119">Procedimiento para generar columnas automáticamente en un control DataGridView de formularios Windows Forms enlazado a datos</span><span class="sxs-lookup"><span data-stu-id="26179-119">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>](autogenerate-columns-in-a-data-bound-wf-datagridview-control.md)  
 <span data-ttu-id="26179-120">Describe cómo generar automáticamente columnas basadas en un origen de datos enlazado.</span><span class="sxs-lookup"><span data-stu-id="26179-120">Describes how to automatically generate columns based on a bound data source.</span></span>  
  
 [<span data-ttu-id="26179-121">Procedimiento para quitar columnas generadas automáticamente de un control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="26179-121">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)  
 <span data-ttu-id="26179-122">Describe cómo ocultar o eliminar columnas generadas automáticamente desde un origen de datos enlazado.</span><span class="sxs-lookup"><span data-stu-id="26179-122">Describes how to hide or delete columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="26179-123">Procedimiento para cambiar el orden de las columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="26179-123">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="26179-124">Describe cómo reorganizar las columnas generadas automáticamente a partir de un origen de datos enlazado.</span><span class="sxs-lookup"><span data-stu-id="26179-124">Describes how to rearrange columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="26179-125">Procedimiento para agregar una columna sin enlazar a un control DataGridView de formularios Windows Forms enlazado a datos</span><span class="sxs-lookup"><span data-stu-id="26179-125">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>](unbound-column-to-a-data-bound-datagridview.md)  
 <span data-ttu-id="26179-126">Describe cómo complementar los datos de un origen de datos enlazado mostrando columnas adicionales y sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="26179-126">Describes how to supplement data from a bound data source by displaying additional, unbound columns.</span></span>  
  
 [<span data-ttu-id="26179-127">Cómo: Enlazar objetos a controles DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="26179-127">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](how-to-bind-objects-to-windows-forms-datagridview-controls.md)  
 <span data-ttu-id="26179-128">Describe cómo enlazar el control a una colección de objetos arbitrarios para que cada objeto se muestre en su propia fila.</span><span class="sxs-lookup"><span data-stu-id="26179-128">Describes how to bind the control to a collection of arbitrary objects so that each object is displayed in its own row.</span></span>  
  
 [<span data-ttu-id="26179-129">Cómo: Obtener acceso a objetos enlazados a filas DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="26179-129">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)  
 <span data-ttu-id="26179-130">Describe cómo recuperar un objeto enlazado a una fila determinada del control.</span><span class="sxs-lookup"><span data-stu-id="26179-130">Describes how to retrieve an object bound to a particular row of the control.</span></span>  
  
 [<span data-ttu-id="26179-131">Tutorial: Crear un formulario maestro y detalle mediante dos controles DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="26179-131">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](creating-a-master-detail-form-using-two-datagridviews.md)  
 <span data-ttu-id="26179-132">Describe cómo mostrar los datos de dos tablas de base de datos relacionadas para que los valores mostrados en un `DataGridView` control dependan de la fila seleccionada actualmente en otro control.</span><span class="sxs-lookup"><span data-stu-id="26179-132">Describes how to display data from two related database tables so that the values shown in one `DataGridView` control depend on the currently selected row in another control.</span></span>  
  
 [<span data-ttu-id="26179-133">Procedimiento para personalizar el formato de los datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="26179-133">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="26179-134">Describe cómo controlar el <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> evento para cambiar la apariencia de las celdas en función de sus valores.</span><span class="sxs-lookup"><span data-stu-id="26179-134">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event to change the appearance of cells depending on their values.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="26179-135">Referencia</span><span class="sxs-lookup"><span data-stu-id="26179-135">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="26179-136">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="26179-136">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <span data-ttu-id="26179-137">Proporciona documentación de referencia para la <xref:System.Windows.Forms.DataGridView.DataSource%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="26179-137">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="26179-138">Proporciona documentación de referencia para el componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="26179-138">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="26179-139">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="26179-139">Related Sections</span></span>  
 [<span data-ttu-id="26179-140">Entrada de datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="26179-140">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="26179-141">Proporciona temas que describen cómo cambiar la forma en que los usuarios agregan y modifican datos en el control.</span><span class="sxs-lookup"><span data-stu-id="26179-141">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26179-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="26179-142">See also</span></span>

- [<span data-ttu-id="26179-143">Control DataGridView</span><span class="sxs-lookup"><span data-stu-id="26179-143">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="26179-144">Tipos de columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="26179-144">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
