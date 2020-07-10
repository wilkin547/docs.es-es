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
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a>Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox
Los <xref:System.Windows.Forms.ComboBox> controles y <xref:System.Windows.Forms.ListBox> tienen comportamientos similares y, en algunos casos, pueden ser intercambiables. No obstante, hay ocasiones en las que una u otra es más adecuada para una tarea.  
  
 Por lo general, un cuadro combinado es adecuado cuando hay una lista de opciones sugeridas y un cuadro de lista es adecuado cuando se desea limitar la entrada a lo que está en la lista. Un cuadro combinado contiene un campo de cuadro de texto, por lo que se puede escribir en las opciones que no están en la lista. La excepción es cuando la <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> propiedad se establece en <xref:System.Windows.Forms.ComboBoxStyle.DropDownList> . En ese caso, el control seleccionará un elemento si escribe su primera letra.  
  
 Además, los cuadros combinados ahorran espacio en un formulario. Dado que la lista completa no se muestra hasta que el usuario hace clic en la flecha hacia abajo, un cuadro combinado puede caber fácilmente en un espacio pequeño en el que no quepa un cuadro de lista. Una excepción es cuando la <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> propiedad se establece en <xref:System.Windows.Forms.ComboBoxStyle.Simple> : se muestra la lista completa y el cuadro combinado ocupa más espacio que el que tendría un cuadro de lista.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Procedimiento para agregar y quitar elementos de un control ComboBox, ListBox o CheckedListBox de formularios Windows Forms](add-and-remove-items-from-a-wf-combobox.md)
- [Procedimiento para ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Controles de formularios Windows Forms usados para mostrar opciones](windows-forms-controls-used-to-list-options.md)
