---
title: ComboBox frente a ListBox
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], vs. ComboBox
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- ComboBox control [Windows Forms], compared to ListBox
- combo boxes [Windows Forms], compared to list boxes
- ListBox control [Windows Forms], accessing items
- ListCount property
ms.assetid: 7bcaea58-1cfa-46db-9baf-b75a69d8f9ec
ms.openlocfilehash: 7087760a393bb58d83d899c1741c745fb28585bb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739930"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="67500-102">Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox</span><span class="sxs-lookup"><span data-stu-id="67500-102">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="67500-103">Los controles <xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.ListBox> tienen comportamientos similares y, en algunos casos, pueden ser intercambiables.</span><span class="sxs-lookup"><span data-stu-id="67500-103">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="67500-104">No obstante, hay ocasiones en las que una u otra es más adecuada para una tarea.</span><span class="sxs-lookup"><span data-stu-id="67500-104">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="67500-105">Por lo general, un cuadro combinado es adecuado cuando hay una lista de opciones sugeridas y un cuadro de lista es adecuado cuando se desea limitar la entrada a lo que está en la lista.</span><span class="sxs-lookup"><span data-stu-id="67500-105">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="67500-106">Un cuadro combinado contiene un campo de cuadro de texto, por lo que se puede escribir en las opciones que no están en la lista.</span><span class="sxs-lookup"><span data-stu-id="67500-106">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="67500-107">La excepción es cuando la propiedad <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> está establecida en <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span><span class="sxs-lookup"><span data-stu-id="67500-107">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="67500-108">En ese caso, el control seleccionará un elemento si escribe su primera letra.</span><span class="sxs-lookup"><span data-stu-id="67500-108">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="67500-109">Además, los cuadros combinados ahorran espacio en un formulario.</span><span class="sxs-lookup"><span data-stu-id="67500-109">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="67500-110">Dado que la lista completa no se muestra hasta que el usuario hace clic en la flecha hacia abajo, un cuadro combinado puede caber fácilmente en un espacio pequeño en el que no quepa un cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="67500-110">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="67500-111">Una excepción es cuando la propiedad <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> está establecida en <xref:System.Windows.Forms.ComboBoxStyle.Simple>: se muestra la lista completa y el cuadro combinado ocupa más espacio que el cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="67500-111">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67500-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="67500-112">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="67500-113">Agregar y quitar elementos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="67500-113">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="67500-114">Ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="67500-114">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="67500-115">Controles de formularios Windows Forms usados para mostrar opciones</span><span class="sxs-lookup"><span data-stu-id="67500-115">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
