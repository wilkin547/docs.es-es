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
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a>Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox
Los controles <xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.ListBox> tienen comportamientos similares y, en algunos casos, pueden ser intercambiables. No obstante, hay ocasiones en las que una u otra es más adecuada para una tarea.  
  
 Por lo general, un cuadro combinado es adecuado cuando hay una lista de opciones sugeridas y un cuadro de lista es adecuado cuando se desea limitar la entrada a lo que está en la lista. Un cuadro combinado contiene un campo de cuadro de texto, por lo que se puede escribir en las opciones que no están en la lista. La excepción es cuando la propiedad <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> está establecida en <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>. En ese caso, el control seleccionará un elemento si escribe su primera letra.  
  
 Además, los cuadros combinados ahorran espacio en un formulario. Dado que la lista completa no se muestra hasta que el usuario hace clic en la flecha hacia abajo, un cuadro combinado puede caber fácilmente en un espacio pequeño en el que no quepa un cuadro de lista. Una excepción es cuando la propiedad <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> está establecida en <xref:System.Windows.Forms.ComboBoxStyle.Simple>: se muestra la lista completa y el cuadro combinado ocupa más espacio que el cuadro de lista.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Agregar y quitar elementos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](add-and-remove-items-from-a-wf-combobox.md)
- [Ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Controles de formularios Windows Forms usados para mostrar opciones](windows-forms-controls-used-to-list-options.md)
