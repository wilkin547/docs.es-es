---
title: Especificar el modo de edición para el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: c0318202a80f9a43f1b656201732ef032f430b5b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743767"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="3bd8f-102">Cómo: Especificar el modo de edición del control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3bd8f-102">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="3bd8f-103">De forma predeterminada, los usuarios pueden modificar el contenido de la celda <xref:System.Windows.Forms.DataGridView> cuadro de texto actual escribiendo o presionando F2.</span><span class="sxs-lookup"><span data-stu-id="3bd8f-103">By default, users can edit the contents of the current <xref:System.Windows.Forms.DataGridView> text box cell by typing in it or pressing F2.</span></span> <span data-ttu-id="3bd8f-104">Esto coloca la celda en modo de edición si se cumplen todas las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3bd8f-104">This puts the cell in edit mode if all of the following conditions are met:</span></span>  
  
- <span data-ttu-id="3bd8f-105">El origen de datos subyacente admite la edición.</span><span class="sxs-lookup"><span data-stu-id="3bd8f-105">The underlying data source supports editing.</span></span>  
  
- <span data-ttu-id="3bd8f-106">El control de <xref:System.Windows.Forms.DataGridView> está habilitado.</span><span class="sxs-lookup"><span data-stu-id="3bd8f-106">The <xref:System.Windows.Forms.DataGridView> control is enabled.</span></span>  
  
- <span data-ttu-id="3bd8f-107">El valor de propiedad <xref:System.Windows.Forms.DataGridView.EditMode%2A> no es <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span><span class="sxs-lookup"><span data-stu-id="3bd8f-107">The <xref:System.Windows.Forms.DataGridView.EditMode%2A> property value is not <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span></span>  
  
- <span data-ttu-id="3bd8f-108">El `ReadOnly` las propiedades de la celda, la fila, la columna y el control se establecen en `false`.</span><span class="sxs-lookup"><span data-stu-id="3bd8f-108">The `ReadOnly` properties of the cell, row, column, and control are all set to `false`.</span></span>  
  
 <span data-ttu-id="3bd8f-109">En el modo de edición, el usuario puede cambiar el valor de la celda y presionar entrar para confirmar el cambio o ESC para revertir la celda a su valor original.</span><span class="sxs-lookup"><span data-stu-id="3bd8f-109">In edit mode, the user can change the cell value and press ENTER to commit the change or ESC to revert the cell to its original value.</span></span>  
  
 <span data-ttu-id="3bd8f-110">Puede configurar un control de <xref:System.Windows.Forms.DataGridView> para que una celda entre en el modo de edición en cuanto se convierta en la celda actual.</span><span class="sxs-lookup"><span data-stu-id="3bd8f-110">You can configure a <xref:System.Windows.Forms.DataGridView> control so that a cell enters edit mode as soon as it becomes the current cell.</span></span> <span data-ttu-id="3bd8f-111">En este caso, el comportamiento de las teclas entrar y ESC no cambia, pero la celda permanece en modo de edición después de confirmar o revertir el valor.</span><span class="sxs-lookup"><span data-stu-id="3bd8f-111">The behavior of the ENTER and ESC keys is unchanged in this case, but the cell remains in edit mode after the value is committed or reverted.</span></span> <span data-ttu-id="3bd8f-112">También puede configurar el control para que las celdas entren en modo de edición solo cuando los usuarios escriban la celda o solo cuando los usuarios presionen F2.</span><span class="sxs-lookup"><span data-stu-id="3bd8f-112">You can also configure the control so that cells enter edit mode only when users type in the cell or only when users press F2.</span></span> <span data-ttu-id="3bd8f-113">Por último, puede evitar que las celdas entren en el modo de edición excepto cuando llame al método <xref:System.Windows.Forms.DataGridView.BeginEdit%2A>.</span><span class="sxs-lookup"><span data-stu-id="3bd8f-113">Finally, you can prevent cells from entering edit mode except when you call the <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> method.</span></span>  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a><span data-ttu-id="3bd8f-114">Para cambiar el modo de edición de un control DataGridView</span><span class="sxs-lookup"><span data-stu-id="3bd8f-114">To change the edit mode of a DataGridView control</span></span>  
  
- <span data-ttu-id="3bd8f-115">Establezca la propiedad <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> en la enumeración <xref:System.Windows.Forms.DataGridViewEditMode> adecuada.</span><span class="sxs-lookup"><span data-stu-id="3bd8f-115">Set the <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> property to the appropriate <xref:System.Windows.Forms.DataGridViewEditMode> enumeration.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3bd8f-116">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="3bd8f-116">Compiling the Code</span></span>  
 <span data-ttu-id="3bd8f-117">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="3bd8f-117">This example requires:</span></span>  
  
- <span data-ttu-id="3bd8f-118">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="3bd8f-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="3bd8f-119">Referencias a los ensamblados <xref:System> y <xref:System.Windows.Forms>.</span><span class="sxs-lookup"><span data-stu-id="3bd8f-119">References to the <xref:System> and <xref:System.Windows.Forms> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bd8f-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3bd8f-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3bd8f-121">Entrada de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3bd8f-121">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
