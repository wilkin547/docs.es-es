---
title: Información general sobre ListBox (Control)
ms.date: 03/30/2017
f1_keywords:
- ListBox
helpviewer_keywords:
- list boxes [Windows Forms], about list boxes
- ListBox control [Windows Forms], about ListBox control
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
ms.openlocfilehash: 1abf8bea5c786f2ce326631370fa294ada09a92c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745182"
---
# <a name="listbox-control-overview-windows-forms"></a>Información general sobre ListBox (Control, formularios Windows Forms)
Un control Windows Forms <xref:System.Windows.Forms.ListBox> muestra una lista en la que el usuario puede seleccionar uno o varios elementos. Si el número total de elementos supera el número que se puede mostrar, se agrega automáticamente una barra de desplazamiento al control <xref:System.Windows.Forms.ListBox>. Cuando la propiedad <xref:System.Windows.Forms.ListBox.MultiColumn%2A> está establecida en `true`, el cuadro de lista muestra los elementos en varias columnas y aparece una barra de desplazamiento horizontal. Cuando la propiedad <xref:System.Windows.Forms.ListBox.MultiColumn%2A> está establecida en `false`, el cuadro de lista muestra los elementos en una sola columna y aparece una barra de desplazamiento vertical. Cuando <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A> se establece en `true`, la barra de desplazamiento aparece independientemente del número de elementos. La propiedad <xref:System.Windows.Forms.ListBox.SelectionMode%2A> determina el número de elementos de lista que se pueden seleccionar a la vez.  
  
## <a name="ways-to-change-the-listbox-control"></a>Formas de cambiar el control ListBox  
 La propiedad <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> devuelve un valor entero que corresponde al primer elemento seleccionado en el cuadro de lista. Puede cambiar el elemento seleccionado mediante programación cambiando el valor de <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> en el código; el elemento correspondiente de la lista aparecerá resaltado en Windows Forms. Si no hay ningún elemento seleccionado, el valor de <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> es-1. Si se selecciona el primer elemento de la lista, el valor de <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> es 0. Cuando se seleccionan varios elementos, el valor de <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> refleja el elemento seleccionado que aparece en primer lugar en la lista. La propiedad <xref:System.Windows.Forms.ListBox.SelectedItem%2A> es similar a <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>, pero devuelve el elemento en sí, normalmente un valor de cadena. La propiedad <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> refleja el número de elementos de la lista y el valor de la propiedad <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> siempre es superior al valor de <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> más grande posible porque <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> está basado en cero.  
  
 Para agregar o eliminar elementos en un control de <xref:System.Windows.Forms.ListBox>, utilice el método <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> o <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A>. Como alternativa, puede agregar elementos a la lista utilizando la propiedad <xref:System.Windows.Forms.ListBox.Items%2A> en tiempo de diseño.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ListBox>
- [Agregar y quitar elementos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](add-and-remove-items-from-a-wf-combobox.md)
- [Ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Enlazar un control ComboBox o ListBox de formularios Windows Forms a datos](how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)
- [Información general sobre el control ComboBox](combobox-control-overview-windows-forms.md)
- [CheckedListBox Control Overview](checkedlistbox-control-overview-windows-forms.md)
- [Controles de formularios Windows Forms usados para mostrar opciones](windows-forms-controls-used-to-list-options.md)
- [Crear una tabla de búsqueda para un control ComboBox, ListBox o CheckedListBox de Windows Forms](create-a-lookup-table-for-a-wf-combobox-listbox.md)
