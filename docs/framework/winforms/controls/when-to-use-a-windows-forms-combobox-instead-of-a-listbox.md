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
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a>Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox
El <xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.ListBox> controles se comportan de forma similar y en algunos casos pueden ser intercambiables. Hay ocasiones, sin embargo, cuando uno de los dos son más adecuado para una tarea.  
  
 Por lo general, un cuadro combinado es adecuado cuando hay una lista de opciones sugeridas y un cuadro de lista es adecuado cuando desea limitar la entrada a lo que aparece en la lista. Un cuadro combinado contiene un campo de cuadro de texto, por lo que las opciones no están en la lista se pueden escribir en. La excepción es cuando el <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> propiedad está establecida en <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>. En ese caso, el control seleccionará un elemento si escribe su primera letra.  
  
 Además, los cuadros combinados ahorrar espacio en un formulario. Porque no se muestra la lista completa hasta que el usuario hace clic en la flecha hacia abajo, un cuadro combinado cabe fácilmente en un espacio pequeño donde no se adaptaría un cuadro de lista. Una excepción es cuando el <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> propiedad está establecida en <xref:System.Windows.Forms.ComboBoxStyle.Simple>: se muestra la lista completa y el cuadro combinado ocupa más espacio que haría un cuadro de lista.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 [Agregar y quitar elementos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [Ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [Controles de formularios Windows Forms usados para mostrar opciones](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
