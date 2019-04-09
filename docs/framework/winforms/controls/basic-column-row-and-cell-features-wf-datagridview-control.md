---
title: Características básicas de columnas, filas y celdas en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], basic features
- columns [Windows Forms], DataGridView control
- data grids [Windows Forms], examples
- DataGridView control [Windows Forms], examples
ms.assetid: 78085f26-d5d2-4b75-813e-e932b72fd06f
ms.openlocfilehash: 4c755d5f0c2e134b83beb27ebbd06080bad620b6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115237"
---
# <a name="basic-column-row-and-cell-features-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="070d3-102">Características básicas de columnas, filas y celdas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="070d3-102">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="070d3-103">Muchos comportamientos básicos de `DataGridView` celdas, filas y columnas se pueden modificar estableciendo propiedades únicas.</span><span class="sxs-lookup"><span data-stu-id="070d3-103">Many basic behaviors of `DataGridView` cells, rows, and columns can be modified by setting single properties.</span></span> <span data-ttu-id="070d3-104">Los temas de esta sección describen varias de estas características más usado.</span><span class="sxs-lookup"><span data-stu-id="070d3-104">The topics in this section describe several of the most commonly used of these features.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="070d3-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="070d3-105">In This Section</span></span>  
 [<span data-ttu-id="070d3-106">Filtrar para ocultar columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="070d3-106">How to: Hide Columns in the Windows Forms DataGridView Control</span></span>](how-to-hide-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="070d3-107">Describe cómo impedir que aparezcan en el control de las columnas específicas.</span><span class="sxs-lookup"><span data-stu-id="070d3-107">Describes how to prevent specific columns from appearing in the control.</span></span>  
  
 [<span data-ttu-id="070d3-108">Filtrar para ocultar encabezados de columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="070d3-108">How to: Hide Column Headers in the Windows Forms DataGridView Control</span></span>](how-to-hide-column-headers-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="070d3-109">Describe cómo evitar que los encabezados de columna en el control de botón de encendido.</span><span class="sxs-lookup"><span data-stu-id="070d3-109">Describes how to prevent the column headers from appearing in the control.</span></span>  
  
 [<span data-ttu-id="070d3-110">Filtrar para habilitar la reordenación de columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="070d3-110">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="070d3-111">Describe cómo habilitar usuarios reorganizar las columnas del control.</span><span class="sxs-lookup"><span data-stu-id="070d3-111">Describes how to enable users to rearrange columns in the control.</span></span>  
  
 [<span data-ttu-id="070d3-112">Filtrar para inmovilizar columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="070d3-112">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>](how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="070d3-113">Describe cómo evitar que una o varias columnas adyacentes se desplacen.</span><span class="sxs-lookup"><span data-stu-id="070d3-113">Describes how prevent one or more adjacent columns from scrolling.</span></span>  
  
 [<span data-ttu-id="070d3-114">Filtrar para crear columnas de solo lectura en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="070d3-114">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="070d3-115">Describe cómo evitar que los usuarios editen columnas específicas en el control.</span><span class="sxs-lookup"><span data-stu-id="070d3-115">Describes how to prevent users from editing specific columns in the control.</span></span>  
  
 [<span data-ttu-id="070d3-116">Filtrar para impedir la adición y eliminación de filas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="070d3-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](prevent-row-addition-and-deletion-datagridview.md)  
 <span data-ttu-id="070d3-117">Describe cómo quitar la fila de nuevos registros en la parte inferior del control para impedir que los usuarios agreguen filas.</span><span class="sxs-lookup"><span data-stu-id="070d3-117">Describes how to remove the row for new records at the bottom of the control to prevent users from adding rows.</span></span> <span data-ttu-id="070d3-118">También se describe cómo impedir que los usuarios eliminen filas.</span><span class="sxs-lookup"><span data-stu-id="070d3-118">Also describes how to prevent users from deleting rows.</span></span>  
  
 [<span data-ttu-id="070d3-119">Filtrar para obtener y establecer la celda actual en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="070d3-119">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>](get-and-set-the-current-cell-wf-datagridview-control.md)  
 <span data-ttu-id="070d3-120">Describe cómo tener acceso a la celda que tiene actualmente el foco en el control.</span><span class="sxs-lookup"><span data-stu-id="070d3-120">Describes how to access the cell that currently has focus in the control.</span></span>  
  
 [<span data-ttu-id="070d3-121">Filtrar para mostrar imágenes en celdas del control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="070d3-121">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>](how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="070d3-122">Describe cómo crear una columna de imagen que muestra un icono de cada celda.</span><span class="sxs-lookup"><span data-stu-id="070d3-122">Describes how to create an image column that displays an icon in every cell.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="070d3-123">Referencia</span><span class="sxs-lookup"><span data-stu-id="070d3-123">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="070d3-124">Proporciona documentación de referencia para el control.</span><span class="sxs-lookup"><span data-stu-id="070d3-124">Provides reference documentation for the control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="070d3-125">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="070d3-125">Related Sections</span></span>  
 [<span data-ttu-id="070d3-126">Estilo y formato básicos del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="070d3-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="070d3-127">Proporciona temas que describen cómo modificar la apariencia básica del control y el formato de presentación de los datos de celda.</span><span class="sxs-lookup"><span data-stu-id="070d3-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
 [<span data-ttu-id="070d3-128">Programar con celdas, filas y columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="070d3-128">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 <span data-ttu-id="070d3-129">Proporciona temas que describen cómo programar con objetos de columna, fila y celda.</span><span class="sxs-lookup"><span data-stu-id="070d3-129">Provides topics that describe how to program with cell, row, and column objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="070d3-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="070d3-130">See also</span></span>

- [<span data-ttu-id="070d3-131">Control DataGridView</span><span class="sxs-lookup"><span data-stu-id="070d3-131">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="070d3-132">Tipos de columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="070d3-132">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
