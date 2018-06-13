---
title: Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox
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
ms.openlocfilehash: 88b6a6023fbfdd8fa315fcd434357626ea69a9ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537773"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="dc108-102">Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox</span><span class="sxs-lookup"><span data-stu-id="dc108-102">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="dc108-103">El <xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.ListBox> controles se comportan de forma similar y en algunos casos pueden ser intercambiables.</span><span class="sxs-lookup"><span data-stu-id="dc108-103">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="dc108-104">Hay ocasiones, sin embargo, cuando uno de los dos son más adecuado para una tarea.</span><span class="sxs-lookup"><span data-stu-id="dc108-104">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="dc108-105">Por lo general, un cuadro combinado es adecuado cuando hay una lista de opciones sugeridas y un cuadro de lista es adecuado cuando desea limitar la entrada a lo que aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="dc108-105">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="dc108-106">Un cuadro combinado contiene un campo de cuadro de texto, por lo que las opciones no están en la lista se pueden escribir en.</span><span class="sxs-lookup"><span data-stu-id="dc108-106">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="dc108-107">La excepción es cuando el <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> propiedad está establecida en <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span><span class="sxs-lookup"><span data-stu-id="dc108-107">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="dc108-108">En ese caso, el control seleccionará un elemento si escribe su primera letra.</span><span class="sxs-lookup"><span data-stu-id="dc108-108">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="dc108-109">Además, los cuadros combinados ahorrar espacio en un formulario.</span><span class="sxs-lookup"><span data-stu-id="dc108-109">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="dc108-110">Porque no se muestra la lista completa hasta que el usuario hace clic en la flecha hacia abajo, un cuadro combinado cabe fácilmente en un espacio pequeño donde no se adaptaría un cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="dc108-110">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="dc108-111">Una excepción es cuando el <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> propiedad está establecida en <xref:System.Windows.Forms.ComboBoxStyle.Simple>: se muestra la lista completa y el cuadro combinado ocupa más espacio que haría un cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="dc108-111">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc108-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc108-112">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 [<span data-ttu-id="dc108-113">Agregar y quitar elementos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dc108-113">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [<span data-ttu-id="dc108-114">Ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dc108-114">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [<span data-ttu-id="dc108-115">Controles de formularios Windows Forms usados para mostrar opciones</span><span class="sxs-lookup"><span data-stu-id="dc108-115">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
