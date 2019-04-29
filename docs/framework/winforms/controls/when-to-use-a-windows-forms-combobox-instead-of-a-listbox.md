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
ms.openlocfilehash: 8a2429049acf1a22edde8d132ece17da4e91f1db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61759835"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="776b0-102">Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox</span><span class="sxs-lookup"><span data-stu-id="776b0-102">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="776b0-103">El <xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.ListBox> controles tienen comportamientos similares y en algunos casos pueden ser intercambiables.</span><span class="sxs-lookup"><span data-stu-id="776b0-103">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="776b0-104">Veces, sin embargo, cuando uno de ellos es más adecuado para una tarea.</span><span class="sxs-lookup"><span data-stu-id="776b0-104">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="776b0-105">Por lo general, un cuadro combinado es adecuado cuando hay una lista de opciones sugeridas, y un cuadro de lista es adecuado cuando desee limitar la entrada a lo que aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="776b0-105">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="776b0-106">Un cuadro combinado contiene un campo de cuadro de texto, por lo que las opciones no están en la lista se pueden escribir en.</span><span class="sxs-lookup"><span data-stu-id="776b0-106">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="776b0-107">La excepción es cuando la <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> propiedad está establecida en <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span><span class="sxs-lookup"><span data-stu-id="776b0-107">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="776b0-108">En ese caso, el control seleccionará un elemento si escribe su primera letra.</span><span class="sxs-lookup"><span data-stu-id="776b0-108">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="776b0-109">Además, los cuadros combinados de ahorrar espacio en un formulario.</span><span class="sxs-lookup"><span data-stu-id="776b0-109">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="776b0-110">Dado que no se muestra la lista completa hasta que el usuario hace clic en la flecha hacia abajo, un cuadro combinado cabe fácilmente en un espacio muy reducido en un cuadro de lista no podría encajar.</span><span class="sxs-lookup"><span data-stu-id="776b0-110">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="776b0-111">Una excepción es cuando la <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> propiedad está establecida en <xref:System.Windows.Forms.ComboBoxStyle.Simple>: se muestra la lista completa y el cuadro combinado ocupa más espacio que sería un cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="776b0-111">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="776b0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="776b0-112">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="776b0-113">Cómo: Agregar y quitar elementos de un Windows Forms control ComboBox, ListBox o CheckedListBox (Control)</span><span class="sxs-lookup"><span data-stu-id="776b0-113">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="776b0-114">Cómo: Ordenar el contenido de un Windows Forms control ComboBox, ListBox o CheckedListBox (Control)</span><span class="sxs-lookup"><span data-stu-id="776b0-114">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="776b0-115">Controles de formularios Windows Forms usados para mostrar opciones</span><span class="sxs-lookup"><span data-stu-id="776b0-115">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
