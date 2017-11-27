---
title: Ordenar datos en el control DataGridView de formularios Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b4027f3ae604f2a3ff4996855fa6dd34d4de8ea2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="e7bde-102">Ordenar datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e7bde-102">Sorting Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e7bde-103">De forma predeterminada, los usuarios pueden ordenar los datos en un `DataGridView` control haciendo clic en el encabezado de una columna del cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="e7bde-103">By default, users can sort the data in a `DataGridView` control by clicking the header of a text box column.</span></span> <span data-ttu-id="e7bde-104">Puede modificar el `SortMode` propiedad de columnas concretas para permitir que los usuarios ordenen por otros tipos de columna cuando tiene sentido hacerlo.</span><span class="sxs-lookup"><span data-stu-id="e7bde-104">You can modify the `SortMode` property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="e7bde-105">También puede ordenar los datos mediante programación por cualquier columna o por varias columnas.</span><span class="sxs-lookup"><span data-stu-id="e7bde-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e7bde-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e7bde-106">In This Section</span></span>  
 [<span data-ttu-id="e7bde-107">Modos de ordenación de columnas del control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e7bde-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e7bde-108">Describe las opciones para ordenar los datos en el control.</span><span class="sxs-lookup"><span data-stu-id="e7bde-108">Describes the options for sorting data in the control.</span></span>  
  
 [<span data-ttu-id="e7bde-109">Cómo: Establecer modos de ordenación de columnas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e7bde-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)  
 <span data-ttu-id="e7bde-110">Describe cómo permitir a los usuarios ordenar por columnas que no se puede ordenables de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e7bde-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>  
  
 [<span data-ttu-id="e7bde-111">Personalizar la ordenación en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e7bde-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e7bde-112">Describe cómo ordenar los datos mediante programación y cómo personalizar la ordenación mediante el uso de la <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> eventos o implementando la <xref:System.Collections.IComparer> interfaz.</span><span class="sxs-lookup"><span data-stu-id="e7bde-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e7bde-113">Referencia</span><span class="sxs-lookup"><span data-stu-id="e7bde-113">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="e7bde-114">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="e7bde-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
 <span data-ttu-id="e7bde-115">Proporciona documentación de referencia para el <xref:System.Windows.Forms.DataGridView.Sort%2A> método.</span><span class="sxs-lookup"><span data-stu-id="e7bde-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="e7bde-116">Proporciona documentación de referencia para el <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="e7bde-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumnSortMode>  
 <span data-ttu-id="e7bde-117">Proporciona documentación de referencia para el <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeración.</span><span class="sxs-lookup"><span data-stu-id="e7bde-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7bde-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7bde-118">See Also</span></span>  
 [<span data-ttu-id="e7bde-119">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="e7bde-119">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="e7bde-120">Tipos de columnas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e7bde-120">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
