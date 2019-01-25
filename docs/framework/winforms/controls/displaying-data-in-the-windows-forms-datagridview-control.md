---
title: Mostrar datos en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], displaying data
- displaying data [Windows Forms], data grids
- DataGridView control [Windows Forms], displaying data
ms.assetid: b170b52a-2ebd-4948-ac2f-e52d494cebb2
ms.openlocfilehash: 39c5482c48f3728469e8952220eabc4daef1cbf6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54665258"
---
# <a name="displaying-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="705c7-102">Mostrar datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="705c7-102">Displaying Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="705c7-103">El `DataGridView` control se usa para mostrar los datos desde una variedad de orígenes de datos externos.</span><span class="sxs-lookup"><span data-stu-id="705c7-103">The `DataGridView` control is used to display data from a variety of external data sources.</span></span> <span data-ttu-id="705c7-104">Como alternativa, puede agregar filas y columnas al control y rellenarlo con datos manualmente.</span><span class="sxs-lookup"><span data-stu-id="705c7-104">Alternatively, you can add rows and columns to the control and manually populate it with data.</span></span>  
  
 <span data-ttu-id="705c7-105">Al enlazar el control a un origen de datos, puede generar columnas automáticamente según el esquema del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="705c7-105">When you bind the control to a data source, you can generate columns automatically based on the schema of the data source.</span></span> <span data-ttu-id="705c7-106">Si estas columnas no aparecen tal como desea a, puede ocultar, quitar o reorganizarlos.</span><span class="sxs-lookup"><span data-stu-id="705c7-106">If these columns do not appear just as you want them to, you can hide, remove, or rearrange them.</span></span> <span data-ttu-id="705c7-107">También puede agregar columnas sin enlazar para mostrar datos complementarios que no proceden del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="705c7-107">You can also add unbound columns to display supplemental data that does not come from the data source.</span></span>  
  
 <span data-ttu-id="705c7-108">Además, puede mostrar los datos con formatos estándares (por ejemplo, el formato de moneda), o puede personalizar el formato de presentación para presentar los datos, sin embargo, debe (por ejemplo, cambiar el color de fondo para los números negativos o reemplazar los valores de cadena con las imágenes correspondientes).</span><span class="sxs-lookup"><span data-stu-id="705c7-108">Additionally, you can display your data using standard formats (such as currency format), or you can customize the display formatting to present your data however you need to (such as changing the background color for negative numbers, or replacing string values with corresponding images).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="705c7-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="705c7-109">In This Section</span></span>  
 [<span data-ttu-id="705c7-110">Modos de presentación de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="705c7-110">Data Display Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="705c7-111">Describe las opciones para rellenar el control con datos.</span><span class="sxs-lookup"><span data-stu-id="705c7-111">Describes the options for populating the control with data.</span></span>  
  
 [<span data-ttu-id="705c7-112">Formato de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="705c7-112">Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="705c7-113">Describe las opciones para dar formato a valores de celda para mostrar.</span><span class="sxs-lookup"><span data-stu-id="705c7-113">Describes the options for formatting cell display values.</span></span>  
  
 [<span data-ttu-id="705c7-114">Tutorial: Crear una independiente de Windows Forms DataGridView Control</span><span class="sxs-lookup"><span data-stu-id="705c7-114">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 <span data-ttu-id="705c7-115">Describe cómo rellenar manualmente el control con datos.</span><span class="sxs-lookup"><span data-stu-id="705c7-115">Describes how to manually populate the control with data.</span></span>  
  
 [<span data-ttu-id="705c7-116">Cómo: Enlazar datos al Control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="705c7-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="705c7-117">Describe cómo rellenar el control con datos mediante su enlace a un `BindingSource` que contiene información extraída de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="705c7-117">Describes how to populate the control with data by binding it to a `BindingSource` that contains information pulled from a database.</span></span>  
  
 [<span data-ttu-id="705c7-118">Cómo: Generar columnas automáticamente en un Control DataGridView de formularios de Windows enlazados a datos</span><span class="sxs-lookup"><span data-stu-id="705c7-118">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/autogenerate-columns-in-a-data-bound-wf-datagridview-control.md)  
 <span data-ttu-id="705c7-119">Describe cómo generar automáticamente columnas basándose en un origen de datos enlazado.</span><span class="sxs-lookup"><span data-stu-id="705c7-119">Describes how to automatically generate columns based on a bound data source.</span></span>  
  
 [<span data-ttu-id="705c7-120">Cómo: Quitar columnas generadas automáticamente desde un Control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="705c7-120">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/remove-autogenerated-columns-from-a-wf-datagridview-control.md)  
 <span data-ttu-id="705c7-121">Describe cómo ocultar o eliminar columnas generadas automáticamente desde un origen de datos enlazado.</span><span class="sxs-lookup"><span data-stu-id="705c7-121">Describes how to hide or delete columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="705c7-122">Cómo: Cambiar el orden de columnas en el Control DataGridView de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="705c7-122">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="705c7-123">Describe cómo reorganizar columnas generadas automáticamente desde un origen de datos enlazado.</span><span class="sxs-lookup"><span data-stu-id="705c7-123">Describes how to rearrange columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="705c7-124">Cómo: Agregar una columna independiente a un Control DataGridView de formularios de Windows enlazados a datos</span><span class="sxs-lookup"><span data-stu-id="705c7-124">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/unbound-column-to-a-data-bound-datagridview.md)  
 <span data-ttu-id="705c7-125">Describe cómo complementar los datos de un origen de datos enlazado al mostrar columnas adicionales e independientes.</span><span class="sxs-lookup"><span data-stu-id="705c7-125">Describes how to supplement data from a bound data source by displaying additional, unbound columns.</span></span>  
  
 [<span data-ttu-id="705c7-126">Cómo: Enlazar objetos a controles DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="705c7-126">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-objects-to-windows-forms-datagridview-controls.md)  
 <span data-ttu-id="705c7-127">Describe cómo enlazar el control a una colección de objetos arbitrarios para que cada objeto se muestran en su propia fila.</span><span class="sxs-lookup"><span data-stu-id="705c7-127">Describes how to bind the control to a collection of arbitrary objects so that each object is displayed in its own row.</span></span>  
  
 [<span data-ttu-id="705c7-128">Cómo: Obtener acceso a objetos enlazados a Windows Forms filas DataGridView</span><span class="sxs-lookup"><span data-stu-id="705c7-128">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](../../../../docs/framework/winforms/controls/how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)  
 <span data-ttu-id="705c7-129">Describe cómo recuperar un objeto enlazado a una fila determinada del control.</span><span class="sxs-lookup"><span data-stu-id="705c7-129">Describes how to retrieve an object bound to a particular row of the control.</span></span>  
  
 [<span data-ttu-id="705c7-130">Tutorial: Creación de un formulario principal-detalle mediante dos controles DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="705c7-130">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagridviews.md)  
 <span data-ttu-id="705c7-131">Describe cómo mostrar datos de dos tablas relacionadas de la base de datos para que los valores mostrados en uno `DataGridView` control dependen de la fila seleccionada actualmente en otro control.</span><span class="sxs-lookup"><span data-stu-id="705c7-131">Describes how to display data from two related database tables so that the values shown in one `DataGridView` control depend on the currently selected row in another control.</span></span>  
  
 [<span data-ttu-id="705c7-132">Cómo: Personalizar el formato de datos en el Control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="705c7-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="705c7-133">Describe cómo controlar la <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> eventos para cambiar la apariencia de las celdas según sus valores.</span><span class="sxs-lookup"><span data-stu-id="705c7-133">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event to change the appearance of cells depending on their values.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="705c7-134">Referencia</span><span class="sxs-lookup"><span data-stu-id="705c7-134">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="705c7-135">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="705c7-135">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <span data-ttu-id="705c7-136">Proporciona documentación de referencia para el <xref:System.Windows.Forms.DataGridView.DataSource%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="705c7-136">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="705c7-137">Proporciona documentación de referencia para el componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="705c7-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="705c7-138">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="705c7-138">Related Sections</span></span>  
 [<span data-ttu-id="705c7-139">Entrada de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="705c7-139">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="705c7-140">Proporciona temas que describen cómo cambiar la forma en que los usuarios agregan y modifican datos en el control.</span><span class="sxs-lookup"><span data-stu-id="705c7-140">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="705c7-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="705c7-141">See also</span></span>
- [<span data-ttu-id="705c7-142">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="705c7-142">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
- [<span data-ttu-id="705c7-143">Tipos de columnas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="705c7-143">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
