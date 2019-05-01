---
title: Ordenar datos en el control DataGridView de formularios Windows Forms
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 606ffc7bd6136b775adaaaa79cf5042cf1e2dd70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012157"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="0f30d-102">Ordenar datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0f30d-102">Sorting data in the Windows Forms DataGridView control</span></span>

<span data-ttu-id="0f30d-103">De forma predeterminada, los usuarios pueden ordenar los datos en un <xref:System.Windows.Forms.DataGridView> control haciendo clic en el encabezado de una columna del cuadro de texto (o presionar F3 cuando una celda de cuadro de texto se centra en .NET Framework 4.7.2 y versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="0f30d-103">By default, users can sort the data in a <xref:System.Windows.Forms.DataGridView> control by clicking the header of a text box column (or by pressing F3 when a text box cell is focused on .NET Framework 4.7.2 and later versions).</span></span> <span data-ttu-id="0f30d-104">Puede modificar el <xref:System.Windows.Forms.DataGridViewColumn.SortMode> propiedad de columnas específicas para permitir que los usuarios ordenen por otros tipos de columna cuando sea conveniente hacerlo.</span><span class="sxs-lookup"><span data-stu-id="0f30d-104">You can modify the <xref:System.Windows.Forms.DataGridViewColumn.SortMode> property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="0f30d-105">También puede ordenar los datos mediante programación por cualquier columna o por varias columnas.</span><span class="sxs-lookup"><span data-stu-id="0f30d-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0f30d-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0f30d-106">In this section</span></span>

[<span data-ttu-id="0f30d-107">Modos de ordenación de columnas del control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0f30d-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="0f30d-108">Describe las opciones para ordenar los datos en el control.</span><span class="sxs-lookup"><span data-stu-id="0f30d-108">Describes the options for sorting data in the control.</span></span>

[<span data-ttu-id="0f30d-109">Cómo: Establecer modos de ordenación de columnas en el Control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0f30d-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
<span data-ttu-id="0f30d-110">Describe cómo habilitar usuarios ordenar por columnas que no se puede ordenar de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0f30d-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>

[<span data-ttu-id="0f30d-111">Cómo: Personalizar la ordenación en el Control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0f30d-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="0f30d-112">Describe cómo ordenar los datos mediante programación y cómo personalizar la ordenación mediante el uso de la <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> eventos o implementando la <xref:System.Collections.IComparer> interfaz.</span><span class="sxs-lookup"><span data-stu-id="0f30d-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>

## <a name="reference"></a><span data-ttu-id="0f30d-113">Referencia</span><span class="sxs-lookup"><span data-stu-id="0f30d-113">Reference</span></span>

<xref:System.Windows.Forms.DataGridView>  
<span data-ttu-id="0f30d-114">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="0f30d-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
<span data-ttu-id="0f30d-115">Proporciona documentación de referencia para el <xref:System.Windows.Forms.DataGridView.Sort%2A> método.</span><span class="sxs-lookup"><span data-stu-id="0f30d-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
<span data-ttu-id="0f30d-116">Proporciona documentación de referencia para el <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="0f30d-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
<span data-ttu-id="0f30d-117">Proporciona documentación de referencia para el <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeración.</span><span class="sxs-lookup"><span data-stu-id="0f30d-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f30d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f30d-118">See also</span></span>

- [<span data-ttu-id="0f30d-119">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="0f30d-119">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="0f30d-120">Tipos de columnas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0f30d-120">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
