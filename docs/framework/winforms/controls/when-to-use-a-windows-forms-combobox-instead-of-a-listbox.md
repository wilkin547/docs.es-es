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
ms.openlocfilehash: 5dc7778f43c01fd28a14489a7b4179dd851568b2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703002"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a>Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox
El <xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.ListBox> controles tienen comportamientos similares y en algunos casos pueden ser intercambiables. Veces, sin embargo, cuando uno de ellos es más adecuado para una tarea.  
  
 Por lo general, un cuadro combinado es adecuado cuando hay una lista de opciones sugeridas, y un cuadro de lista es adecuado cuando desee limitar la entrada a lo que aparece en la lista. Un cuadro combinado contiene un campo de cuadro de texto, por lo que las opciones no están en la lista se pueden escribir en. La excepción es cuando la <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> propiedad está establecida en <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>. En ese caso, el control seleccionará un elemento si escribe su primera letra.  
  
 Además, los cuadros combinados de ahorrar espacio en un formulario. Dado que no se muestra la lista completa hasta que el usuario hace clic en la flecha hacia abajo, un cuadro combinado cabe fácilmente en un espacio muy reducido en un cuadro de lista no podría encajar. Una excepción es cuando la <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> propiedad está establecida en <xref:System.Windows.Forms.ComboBoxStyle.Simple>: se muestra la lista completa y el cuadro combinado ocupa más espacio que sería un cuadro de lista.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Cómo: Agregar y quitar elementos de un Windows Forms control ComboBox, ListBox o CheckedListBox (Control)](add-and-remove-items-from-a-wf-combobox.md)
- [Cómo: Ordenar el contenido de un Windows Forms control ComboBox, ListBox o CheckedListBox (Control)](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Controles de formularios Windows Forms usados para mostrar opciones](windows-forms-controls-used-to-list-options.md)
