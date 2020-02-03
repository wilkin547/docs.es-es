---
title: Mostrar datos en el control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], displaying data
- displaying data [Windows Forms], data grids
- DataGridView control [Windows Forms], displaying data
ms.assetid: b170b52a-2ebd-4948-ac2f-e52d494cebb2
ms.openlocfilehash: d02362895d75df3735d19554bd44bb8ac443c6c2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745866"
---
# <a name="displaying-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d68e7-102">Mostrar datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d68e7-102">Displaying Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d68e7-103">El control `DataGridView` se utiliza para mostrar los datos de diversos orígenes de datos externos.</span><span class="sxs-lookup"><span data-stu-id="d68e7-103">The `DataGridView` control is used to display data from a variety of external data sources.</span></span> <span data-ttu-id="d68e7-104">Como alternativa, puede Agregar filas y columnas al control y rellenarlas manualmente con los datos.</span><span class="sxs-lookup"><span data-stu-id="d68e7-104">Alternatively, you can add rows and columns to the control and manually populate it with data.</span></span>  
  
 <span data-ttu-id="d68e7-105">Al enlazar el control a un origen de datos, puede generar columnas automáticamente según el esquema del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d68e7-105">When you bind the control to a data source, you can generate columns automatically based on the schema of the data source.</span></span> <span data-ttu-id="d68e7-106">Si estas columnas no aparecen exactamente como desea, puede ocultarlas, quitarlas o reorganizarlas.</span><span class="sxs-lookup"><span data-stu-id="d68e7-106">If these columns do not appear just as you want them to, you can hide, remove, or rearrange them.</span></span> <span data-ttu-id="d68e7-107">También puede Agregar columnas sin enlazar para Mostrar datos complementarios que no proceden del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d68e7-107">You can also add unbound columns to display supplemental data that does not come from the data source.</span></span>  
  
 <span data-ttu-id="d68e7-108">Además, puede mostrar los datos mediante formatos estándar (como el formato de moneda), o puede personalizar el formato de presentación para presentar los datos, sin embargo, es necesario (por ejemplo, cambiar el color de fondo de los números negativos o reemplazar los valores de cadena). con las imágenes correspondientes).</span><span class="sxs-lookup"><span data-stu-id="d68e7-108">Additionally, you can display your data using standard formats (such as currency format), or you can customize the display formatting to present your data however you need to (such as changing the background color for negative numbers, or replacing string values with corresponding images).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d68e7-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d68e7-109">In This Section</span></span>  
 [<span data-ttu-id="d68e7-110">Modos de presentación de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d68e7-110">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d68e7-111">Describe las opciones para rellenar el control con datos.</span><span class="sxs-lookup"><span data-stu-id="d68e7-111">Describes the options for populating the control with data.</span></span>  
  
 [<span data-ttu-id="d68e7-112">Formato de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d68e7-112">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d68e7-113">Describe las opciones para dar formato a los valores de presentación de la celda.</span><span class="sxs-lookup"><span data-stu-id="d68e7-113">Describes the options for formatting cell display values.</span></span>  
  
 [<span data-ttu-id="d68e7-114">Tutorial: Crear un control DataGridView sin enlazar en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d68e7-114">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d68e7-115">Describe cómo rellenar manualmente el control con datos.</span><span class="sxs-lookup"><span data-stu-id="d68e7-115">Describes how to manually populate the control with data.</span></span>  
  
 [<span data-ttu-id="d68e7-116">Enlazar datos al control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d68e7-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d68e7-117">Describe cómo rellenar el control con datos enlazándolo a un `BindingSource` que contiene información extraída de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="d68e7-117">Describes how to populate the control with data by binding it to a `BindingSource` that contains information pulled from a database.</span></span>  
  
 [<span data-ttu-id="d68e7-118">Generar columnas automáticamente en un control DataGridView de formularios Windows Forms enlazado a datos</span><span class="sxs-lookup"><span data-stu-id="d68e7-118">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>](autogenerate-columns-in-a-data-bound-wf-datagridview-control.md)  
 <span data-ttu-id="d68e7-119">Describe cómo generar automáticamente columnas basadas en un origen de datos enlazado.</span><span class="sxs-lookup"><span data-stu-id="d68e7-119">Describes how to automatically generate columns based on a bound data source.</span></span>  
  
 [<span data-ttu-id="d68e7-120">Quitar columnas generadas automáticamente desde un control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d68e7-120">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)  
 <span data-ttu-id="d68e7-121">Describe cómo ocultar o eliminar columnas generadas automáticamente desde un origen de datos enlazado.</span><span class="sxs-lookup"><span data-stu-id="d68e7-121">Describes how to hide or delete columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="d68e7-122">Cambiar el orden de las columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d68e7-122">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d68e7-123">Describe cómo reorganizar las columnas generadas automáticamente a partir de un origen de datos enlazado.</span><span class="sxs-lookup"><span data-stu-id="d68e7-123">Describes how to rearrange columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="d68e7-124">Agregar una columna independiente a un control DataGridView de formularios Windows Forms enlazado a datos</span><span class="sxs-lookup"><span data-stu-id="d68e7-124">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>](unbound-column-to-a-data-bound-datagridview.md)  
 <span data-ttu-id="d68e7-125">Describe cómo complementar los datos de un origen de datos enlazado mostrando columnas adicionales y sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="d68e7-125">Describes how to supplement data from a bound data source by displaying additional, unbound columns.</span></span>  
  
 [<span data-ttu-id="d68e7-126">Cómo: Enlazar objetos a controles DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d68e7-126">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](how-to-bind-objects-to-windows-forms-datagridview-controls.md)  
 <span data-ttu-id="d68e7-127">Describe cómo enlazar el control a una colección de objetos arbitrarios para que cada objeto se muestre en su propia fila.</span><span class="sxs-lookup"><span data-stu-id="d68e7-127">Describes how to bind the control to a collection of arbitrary objects so that each object is displayed in its own row.</span></span>  
  
 [<span data-ttu-id="d68e7-128">Cómo: Obtener acceso a objetos enlazados a filas DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d68e7-128">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)  
 <span data-ttu-id="d68e7-129">Describe cómo recuperar un objeto enlazado a una fila determinada del control.</span><span class="sxs-lookup"><span data-stu-id="d68e7-129">Describes how to retrieve an object bound to a particular row of the control.</span></span>  
  
 [<span data-ttu-id="d68e7-130">Tutorial: Crear un formulario principal-detalle mediante dos controles DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d68e7-130">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](creating-a-master-detail-form-using-two-datagridviews.md)  
 <span data-ttu-id="d68e7-131">Describe cómo mostrar los datos de dos tablas de base de datos relacionadas para que los valores mostrados en un control `DataGridView` dependan de la fila seleccionada actualmente en otro control.</span><span class="sxs-lookup"><span data-stu-id="d68e7-131">Describes how to display data from two related database tables so that the values shown in one `DataGridView` control depend on the currently selected row in another control.</span></span>  
  
 [<span data-ttu-id="d68e7-132">Personalizar el formato de los datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d68e7-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d68e7-133">Describe cómo controlar el evento <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> para cambiar la apariencia de las celdas en función de sus valores.</span><span class="sxs-lookup"><span data-stu-id="d68e7-133">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event to change the appearance of cells depending on their values.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d68e7-134">Referencia</span><span class="sxs-lookup"><span data-stu-id="d68e7-134">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="d68e7-135">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="d68e7-135">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <span data-ttu-id="d68e7-136">Proporciona documentación de referencia para la propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="d68e7-136">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="d68e7-137">Proporciona documentación de referencia para el componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="d68e7-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d68e7-138">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="d68e7-138">Related Sections</span></span>  
 [<span data-ttu-id="d68e7-139">Entrada de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d68e7-139">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d68e7-140">Proporciona temas que describen cómo cambiar la forma en que los usuarios agregan y modifican datos en el control.</span><span class="sxs-lookup"><span data-stu-id="d68e7-140">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d68e7-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d68e7-141">See also</span></span>

- [<span data-ttu-id="d68e7-142">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="d68e7-142">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="d68e7-143">Tipos de columnas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d68e7-143">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
