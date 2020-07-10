---
title: ComboBox frente a ListBox
description: Obtenga información sobre cómo usar Windows Forms ComboBox y Windows Forms ListBox y aprenda a saber cuándo uno u otro es más adecuado para una tarea.
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
ms.openlocfilehash: ca6ad6bec2dbc30128ea09808af2806687b17a8c
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174424"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="08cc1-103">Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox</span><span class="sxs-lookup"><span data-stu-id="08cc1-103">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="08cc1-104">Los <xref:System.Windows.Forms.ComboBox> controles y <xref:System.Windows.Forms.ListBox> tienen comportamientos similares y, en algunos casos, pueden ser intercambiables.</span><span class="sxs-lookup"><span data-stu-id="08cc1-104">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="08cc1-105">No obstante, hay ocasiones en las que una u otra es más adecuada para una tarea.</span><span class="sxs-lookup"><span data-stu-id="08cc1-105">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="08cc1-106">Por lo general, un cuadro combinado es adecuado cuando hay una lista de opciones sugeridas y un cuadro de lista es adecuado cuando se desea limitar la entrada a lo que está en la lista.</span><span class="sxs-lookup"><span data-stu-id="08cc1-106">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="08cc1-107">Un cuadro combinado contiene un campo de cuadro de texto, por lo que se puede escribir en las opciones que no están en la lista.</span><span class="sxs-lookup"><span data-stu-id="08cc1-107">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="08cc1-108">La excepción es cuando la <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> propiedad se establece en <xref:System.Windows.Forms.ComboBoxStyle.DropDownList> .</span><span class="sxs-lookup"><span data-stu-id="08cc1-108">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="08cc1-109">En ese caso, el control seleccionará un elemento si escribe su primera letra.</span><span class="sxs-lookup"><span data-stu-id="08cc1-109">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="08cc1-110">Además, los cuadros combinados ahorran espacio en un formulario.</span><span class="sxs-lookup"><span data-stu-id="08cc1-110">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="08cc1-111">Dado que la lista completa no se muestra hasta que el usuario hace clic en la flecha hacia abajo, un cuadro combinado puede caber fácilmente en un espacio pequeño en el que no quepa un cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="08cc1-111">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="08cc1-112">Una excepción es cuando la <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> propiedad se establece en <xref:System.Windows.Forms.ComboBoxStyle.Simple> : se muestra la lista completa y el cuadro combinado ocupa más espacio que el que tendría un cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="08cc1-112">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08cc1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="08cc1-113">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="08cc1-114">Procedimiento para agregar y quitar elementos de un control ComboBox, ListBox o CheckedListBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="08cc1-114">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="08cc1-115">Procedimiento para ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="08cc1-115">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="08cc1-116">Controles de formularios Windows Forms usados para mostrar opciones</span><span class="sxs-lookup"><span data-stu-id="08cc1-116">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
