---
title: Procedimiento para especificar el modo de edición del control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: a999582aeb629646fa1843f973b10a039c29e1a3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630536"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="cdfc9-102">Procedimiento para especificar el modo de edición del control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cdfc9-102">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="cdfc9-103">De forma predeterminada, los usuarios pueden editar el contenido del elemento actual <xref:System.Windows.Forms.DataGridView> celda de cuadro de texto al escribir en él o presione F2.</span><span class="sxs-lookup"><span data-stu-id="cdfc9-103">By default, users can edit the contents of the current <xref:System.Windows.Forms.DataGridView> text box cell by typing in it or pressing F2.</span></span> <span data-ttu-id="cdfc9-104">Esto coloca la celda en modo de edición si se cumplen todas las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="cdfc9-104">This puts the cell in edit mode if all of the following conditions are met:</span></span>  
  
- <span data-ttu-id="cdfc9-105">El origen de datos subyacente admite la edición.</span><span class="sxs-lookup"><span data-stu-id="cdfc9-105">The underlying data source supports editing.</span></span>  
  
- <span data-ttu-id="cdfc9-106">El <xref:System.Windows.Forms.DataGridView> control está habilitado.</span><span class="sxs-lookup"><span data-stu-id="cdfc9-106">The <xref:System.Windows.Forms.DataGridView> control is enabled.</span></span>  
  
- <span data-ttu-id="cdfc9-107">El <xref:System.Windows.Forms.DataGridView.EditMode%2A> no es el valor de propiedad <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span><span class="sxs-lookup"><span data-stu-id="cdfc9-107">The <xref:System.Windows.Forms.DataGridView.EditMode%2A> property value is not <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span></span>  
  
- <span data-ttu-id="cdfc9-108">El `ReadOnly` propiedades de la celda, fila, columna y control están establecidos en `false`.</span><span class="sxs-lookup"><span data-stu-id="cdfc9-108">The `ReadOnly` properties of the cell, row, column, and control are all set to `false`.</span></span>  
  
 <span data-ttu-id="cdfc9-109">En modo de edición, el usuario puede cambiar el valor de celda y presione ENTRAR para confirmar el cambio o la tecla ESC para revertir la celda a su valor original.</span><span class="sxs-lookup"><span data-stu-id="cdfc9-109">In edit mode, the user can change the cell value and press ENTER to commit the change or ESC to revert the cell to its original value.</span></span>  
  
 <span data-ttu-id="cdfc9-110">Puede configurar un <xref:System.Windows.Forms.DataGridView> controlar de manera que una celda entra en modo de edición, en cuanto se convierte en la celda actual.</span><span class="sxs-lookup"><span data-stu-id="cdfc9-110">You can configure a <xref:System.Windows.Forms.DataGridView> control so that a cell enters edit mode as soon as it becomes the current cell.</span></span> <span data-ttu-id="cdfc9-111">El comportamiento de las teclas ENTRAR y ESC se modifica en este caso, pero sigue siendo la celda en modo de edición después de confirmar o revertir el valor.</span><span class="sxs-lookup"><span data-stu-id="cdfc9-111">The behavior of the ENTER and ESC keys is unchanged in this case, but the cell remains in edit mode after the value is committed or reverted.</span></span> <span data-ttu-id="cdfc9-112">También puede configurar el control para que las celdas entrar en modo de edición solo cuando los usuarios escriben en la celda o solo cuando los usuarios presionar F2.</span><span class="sxs-lookup"><span data-stu-id="cdfc9-112">You can also configure the control so that cells enter edit mode only when users type in the cell or only when users press F2.</span></span> <span data-ttu-id="cdfc9-113">Por último, puede impedir que las celdas entrando en modo de edición, excepto cuando se llama a la <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> método.</span><span class="sxs-lookup"><span data-stu-id="cdfc9-113">Finally, you can prevent cells from entering edit mode except when you call the <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> method.</span></span>  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a><span data-ttu-id="cdfc9-114">Para cambiar el modo de edición de un control DataGridView</span><span class="sxs-lookup"><span data-stu-id="cdfc9-114">To change the edit mode of a DataGridView control</span></span>  
  
- <span data-ttu-id="cdfc9-115">Establecer el <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> propiedad correspondientes <xref:System.Windows.Forms.DataGridViewEditMode> enumeración.</span><span class="sxs-lookup"><span data-stu-id="cdfc9-115">Set the <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> property to the appropriate <xref:System.Windows.Forms.DataGridViewEditMode> enumeration.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cdfc9-116">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="cdfc9-116">Compiling the Code</span></span>  
 <span data-ttu-id="cdfc9-117">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="cdfc9-117">This example requires:</span></span>  
  
- <span data-ttu-id="cdfc9-118">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="cdfc9-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="cdfc9-119">Referencias a los ensamblados <xref:System> y <xref:System.Windows.Forms>.</span><span class="sxs-lookup"><span data-stu-id="cdfc9-119">References to the <xref:System> and <xref:System.Windows.Forms> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdfc9-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="cdfc9-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="cdfc9-121">Entrada de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cdfc9-121">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
