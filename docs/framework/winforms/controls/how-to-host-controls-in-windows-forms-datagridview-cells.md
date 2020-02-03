---
title: Controles host en celdas DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], hosting in cells
- DataGridView control [Windows Forms], hosting controls in cells
- cells [Windows Forms], hosting controls
ms.assetid: e79a9d4e-64ec-41f5-93ec-f5492633cbb2
ms.openlocfilehash: a64521a15a272ca8140302f39d15e7f17e0c423b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736542"
---
# <a name="how-to-host-controls-in-windows-forms-datagridview-cells"></a><span data-ttu-id="66f59-102">Cómo: Alojar controles en celdas DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="66f59-102">How to: Host Controls in Windows Forms DataGridView Cells</span></span>
<span data-ttu-id="66f59-103">El control <xref:System.Windows.Forms.DataGridView> proporciona varios tipos de columna, permitiendo a sus usuarios escribir y editar valores de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="66f59-103">The <xref:System.Windows.Forms.DataGridView> control provides several column types, enabling your users to enter and edit values in a variety of ways.</span></span> <span data-ttu-id="66f59-104">No obstante, si estos tipos de columna no satisfacen sus necesidades de entrada de datos, puede crear sus propios tipos de columna con celdas que alojen los controles que elija.</span><span class="sxs-lookup"><span data-stu-id="66f59-104">If these column types do not meet your data-entry needs, however, you can create your own column types with cells that host controls of your choosing.</span></span> <span data-ttu-id="66f59-105">Para ello, debe definir clases que deriven de <xref:System.Windows.Forms.DataGridViewColumn> y <xref:System.Windows.Forms.DataGridViewCell>.</span><span class="sxs-lookup"><span data-stu-id="66f59-105">To do this, you must define classes that derive from <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewCell>.</span></span> <span data-ttu-id="66f59-106">También debe definir una clase que derive de <xref:System.Windows.Forms.Control> e implemente la interfaz <xref:System.Windows.Forms.IDataGridViewEditingControl>.</span><span class="sxs-lookup"><span data-stu-id="66f59-106">You must also define a class that derives from <xref:System.Windows.Forms.Control> and implements the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
 <span data-ttu-id="66f59-107">El ejemplo de código siguiente muestra cómo crear una columna de calendario.</span><span class="sxs-lookup"><span data-stu-id="66f59-107">The following code example shows how to create a calendar column.</span></span> <span data-ttu-id="66f59-108">Las celdas de esta columna muestran fechas en celdas de cuadro de texto normales, pero cuando el usuario edita una celda, aparece un control <xref:System.Windows.Forms.DateTimePicker>.</span><span class="sxs-lookup"><span data-stu-id="66f59-108">The cells of this column display dates in ordinary text box cells, but when the user edits a cell, a <xref:System.Windows.Forms.DateTimePicker> control appears.</span></span> <span data-ttu-id="66f59-109">Para evitar tener que implementar nuevamente la funcionalidad de visualización de cuadro de texto, la clase `CalendarCell` deriva de la clase <xref:System.Windows.Forms.DataGridViewTextBoxCell>, en lugar de heredar directamente la clase <xref:System.Windows.Forms.DataGridViewCell>.</span><span class="sxs-lookup"><span data-stu-id="66f59-109">In order to avoid having to implement text box display functionality again, the `CalendarCell` class derives from the <xref:System.Windows.Forms.DataGridViewTextBoxCell> class rather than inheriting the <xref:System.Windows.Forms.DataGridViewCell> class directly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66f59-110">Al derivar de <xref:System.Windows.Forms.DataGridViewCell> o <xref:System.Windows.Forms.DataGridViewColumn> y agregar nuevas propiedades a la clase derivada, asegúrese de invalidar el método `Clone` para copiar las nuevas propiedades durante las operaciones de clonación.</span><span class="sxs-lookup"><span data-stu-id="66f59-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="66f59-111">También debe llamar al método `Clone` de la clase base para copiar las propiedades de la clase base a la nueva celda o columna.</span><span class="sxs-lookup"><span data-stu-id="66f59-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66f59-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="66f59-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/CS/datagridviewcalendarcolumn.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/VB/datagridviewcalendarcolumn.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="66f59-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="66f59-113">Compiling the Code</span></span>  
 <span data-ttu-id="66f59-114">El ejemplo siguiente requiere:</span><span class="sxs-lookup"><span data-stu-id="66f59-114">The following example requires:</span></span>  
  
- <span data-ttu-id="66f59-115">Referencias a los ensamblados System y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="66f59-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66f59-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66f59-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>
- <xref:System.Windows.Forms.IDataGridViewEditingControl>
- <xref:System.Windows.Forms.DateTimePicker>
- [<span data-ttu-id="66f59-117">Personalizar el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="66f59-117">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="66f59-118">Arquitectura del control DataGridView</span><span class="sxs-lookup"><span data-stu-id="66f59-118">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="66f59-119">Tipos de columnas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="66f59-119">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
