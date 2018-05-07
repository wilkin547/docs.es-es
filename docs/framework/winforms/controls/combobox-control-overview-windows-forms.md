---
title: Información general sobre el control ComboBox (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ComboBox
helpviewer_keywords:
- drop-down lists [Windows Forms], Windows Forms
- ComboBox control [Windows Forms], about ComboBox control
- drop-down lists [Windows Forms], ComboBox control
- combo boxes [Windows Forms], about combo boxes
ms.assetid: a58b393f-a614-45d1-8961-857a024b5acd
ms.openlocfilehash: c8cd0430e9abaed0ee58e971edf6a9c871da37c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="combobox-control-overview-windows-forms"></a>Información general sobre el control ComboBox (formularios Windows Forms)
Los formularios Windows Forms <xref:System.Windows.Forms.ComboBox> control se utiliza para mostrar datos en un cuadro combinado desplegable. De forma predeterminada, el <xref:System.Windows.Forms.ComboBox> control aparece en dos partes: la parte superior es un cuadro de texto que permite al usuario escribir un elemento de lista. La segunda parte es un cuadro de lista que muestra una lista de elementos desde el que el usuario puede seleccionar uno. Para obtener más información sobre otros estilos de cuadro combinado, vea [cuándo se debe utilizar un ComboBox de formularios Windows Forms en lugar de un control ListBox](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md).  
  
 El <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> propiedad devuelve un valor entero que corresponde al elemento de lista seleccionado. Puede cambiar mediante programación el elemento seleccionado cambiando el <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> del valor en el código; el elemento correspondiente en la lista aparecerán en la parte de cuadro de texto del cuadro combinado. Si se selecciona ningún elemento, el <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> valor es -1. Si se selecciona el primer elemento de la lista, la <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> valor es 0. El <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> propiedad es similar a <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> , pero devuelve el elemento en Sí, normalmente un valor de cadena. El <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> propiedad refleja el número de elementos de la lista y el valor de la <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> propiedad siempre es uno más que el mayor tamaño posible <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> valor porque <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> está basado en cero.  
  
 Para agregar o eliminar elementos en una <xref:System.Windows.Forms.ComboBox> de control, use la <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A> o <xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A> método. Como alternativa, puede agregar elementos a la lista mediante el <xref:System.Windows.Forms.ComboBox.Items%2A> propiedad en el diseñador.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ComboBox>  
 [Información general sobre ListBox (Control)](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)  
 [Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 [Agregar y quitar elementos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [Ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [Obtener acceso a elementos específicos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)  
 [Enlazar un control ComboBox o ListBox de formularios Windows Forms a datos](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)  
 [Controles de formularios Windows Forms usados para mostrar opciones](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)  
 [Crear una tabla de búsqueda para un control ComboBox, ListBox o CheckedListBox de Windows Forms](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)
