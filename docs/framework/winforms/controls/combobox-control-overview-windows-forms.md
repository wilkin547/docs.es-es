---
title: Información general sobre el control ComboBox
ms.date: 03/30/2017
f1_keywords:
- ComboBox
helpviewer_keywords:
- drop-down lists [Windows Forms], Windows Forms
- ComboBox control [Windows Forms], about ComboBox control
- drop-down lists [Windows Forms], ComboBox control
- combo boxes [Windows Forms], about combo boxes
ms.assetid: a58b393f-a614-45d1-8961-857a024b5acd
ms.openlocfilehash: 9fb270d7787902872a32a87c140316f756bd48aa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743840"
---
# <a name="combobox-control-overview-windows-forms"></a>Información general sobre el control ComboBox (formularios Windows Forms)
El control <xref:System.Windows.Forms.ComboBox> de Windows Forms se usa para mostrar los datos en un cuadro combinado desplegable. De forma predeterminada, el control <xref:System.Windows.Forms.ComboBox> aparece en dos partes: la parte superior es un cuadro de texto que permite al usuario escribir un elemento de lista. La segunda parte es un cuadro de lista que muestra una lista de los elementos de los que el usuario puede seleccionar uno. Para obtener más información sobre otros estilos de cuadro combinado, vea [When to use a Windows Forms ComboBox en lugar de un control ListBox](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md).  
  
 La propiedad <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> devuelve un valor entero que corresponde al elemento de lista seleccionado. Puede cambiar el elemento seleccionado mediante programación cambiando el valor de <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> en el código; el elemento correspondiente de la lista aparecerá en la parte del cuadro de texto del cuadro combinado. Si no hay ningún elemento seleccionado, el valor de <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> es-1. Si se selecciona el primer elemento de la lista, el valor de <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> es 0. La propiedad <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> es similar a <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>, pero devuelve el elemento en sí, normalmente un valor de cadena. La propiedad <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> refleja el número de elementos de la lista y el valor de la propiedad <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> siempre es superior al valor de <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> más grande posible porque <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> está basado en cero.  
  
 Para agregar o eliminar elementos en un control de <xref:System.Windows.Forms.ComboBox>, utilice el método <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A> o <xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A>. Como alternativa, puede agregar elementos a la lista utilizando la propiedad <xref:System.Windows.Forms.ComboBox.Items%2A> en el diseñador.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ComboBox>
- [Información general sobre ListBox (Control)](listbox-control-overview-windows-forms.md)
- [Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [Agregar y quitar elementos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](add-and-remove-items-from-a-wf-combobox.md)
- [Ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Obtener acceso a elementos específicos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)
- [Enlazar un control ComboBox o ListBox de formularios Windows Forms a datos](how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)
- [Controles de formularios Windows Forms usados para mostrar opciones](windows-forms-controls-used-to-list-options.md)
- [Crear una tabla de búsqueda para un control ComboBox, ListBox o CheckedListBox de Windows Forms](create-a-lookup-table-for-a-wf-combobox-listbox.md)
