---
title: Ordenar datos en el control DataGridView
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 1fcd5a5f5c6d690c573c4c2c5fa7c32aa0292441
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742948"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="30fd2-102">Ordenar datos en el control DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="30fd2-102">Sorting data in the Windows Forms DataGridView control</span></span>

<span data-ttu-id="30fd2-103">De forma predeterminada, los usuarios pueden ordenar los datos de un control de <xref:System.Windows.Forms.DataGridView> haciendo clic en el encabezado de una columna de cuadro de texto (o presionando F3 cuando una celda de cuadro de texto se centra en .NET Framework 4.7.2 y versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="30fd2-103">By default, users can sort the data in a <xref:System.Windows.Forms.DataGridView> control by clicking the header of a text box column (or by pressing F3 when a text box cell is focused on .NET Framework 4.7.2 and later versions).</span></span> <span data-ttu-id="30fd2-104">Puede modificar la propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode> de columnas específicas para permitir que los usuarios ordenen por otros tipos de columna cuando tenga sentido hacerlo.</span><span class="sxs-lookup"><span data-stu-id="30fd2-104">You can modify the <xref:System.Windows.Forms.DataGridViewColumn.SortMode> property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="30fd2-105">También puede ordenar los datos mediante programación por cualquier columna o por varias columnas.</span><span class="sxs-lookup"><span data-stu-id="30fd2-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="30fd2-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="30fd2-106">In this section</span></span>

[<span data-ttu-id="30fd2-107">Modos de ordenación de columnas del control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="30fd2-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="30fd2-108">Describe las opciones para ordenar los datos del control.</span><span class="sxs-lookup"><span data-stu-id="30fd2-108">Describes the options for sorting data in the control.</span></span>

[<span data-ttu-id="30fd2-109">Cómo: Establecer modos de ordenación de columnas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="30fd2-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
<span data-ttu-id="30fd2-110">Describe cómo permitir a los usuarios ordenar por columnas que no se pueden ordenar de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="30fd2-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>

[<span data-ttu-id="30fd2-111">Personalizar la ordenación en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="30fd2-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="30fd2-112">Describe cómo ordenar los datos mediante programación y cómo personalizar la ordenación utilizando el evento <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> o implementando la interfaz <xref:System.Collections.IComparer>.</span><span class="sxs-lookup"><span data-stu-id="30fd2-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>

## <a name="reference"></a><span data-ttu-id="30fd2-113">Referencia</span><span class="sxs-lookup"><span data-stu-id="30fd2-113">Reference</span></span>

<xref:System.Windows.Forms.DataGridView>  
<span data-ttu-id="30fd2-114">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="30fd2-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
<span data-ttu-id="30fd2-115">Proporciona documentación de referencia para el método <xref:System.Windows.Forms.DataGridView.Sort%2A>.</span><span class="sxs-lookup"><span data-stu-id="30fd2-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
<span data-ttu-id="30fd2-116">Proporciona documentación de referencia para la propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="30fd2-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
<span data-ttu-id="30fd2-117">Proporciona documentación de referencia para la enumeración <xref:System.Windows.Forms.DataGridViewColumnSortMode>.</span><span class="sxs-lookup"><span data-stu-id="30fd2-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>

## <a name="see-also"></a><span data-ttu-id="30fd2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="30fd2-118">See also</span></span>

- [<span data-ttu-id="30fd2-119">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="30fd2-119">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="30fd2-120">Tipos de columnas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="30fd2-120">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
