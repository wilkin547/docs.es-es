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
ms.openlocfilehash: 80056771744c9b97828a024adf32638e545a839e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211587"
---
# <a name="combobox-control-overview-windows-forms"></a>Información general sobre el control ComboBox (formularios Windows Forms)
Los formularios de Windows <xref:System.Windows.Forms.ComboBox> control se usa para mostrar datos en un cuadro combinado desplegable. De forma predeterminada, el <xref:System.Windows.Forms.ComboBox> control aparece en dos partes: la parte superior es un cuadro de texto que permite al usuario escribir un elemento de lista. La segunda parte es un cuadro de lista que muestra una lista de elementos desde el que el usuario puede seleccionar uno. Para obtener más información sobre otros estilos de cuadro combinado, vea [cuándo se debe usar un cuadro combinado de Windows Forms en lugar de un cuadro de lista](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md).  
  
 El <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> propiedad devuelve un valor entero que corresponde al elemento de lista seleccionado. Puede cambiar mediante programación el elemento seleccionado, cambie el <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> valor en el código; el elemento correspondiente en la lista aparecerán en la parte de cuadro de texto del cuadro combinado. Si se selecciona ningún elemento, el <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> valor es -1. Si se selecciona el primer elemento en la lista, el <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> valor es 0. El <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> es similar a la propiedad <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> , pero devuelve el elemento, normalmente un valor de cadena. El <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> propiedad refleja el número de elementos de la lista y el valor de la <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> propiedad siempre es uno más que lo más grande posible <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> valor porque <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> está basado en cero.  
  
 Para agregar o eliminar elementos en un <xref:System.Windows.Forms.ComboBox> controlar, use el <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A> o <xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A> método. Como alternativa, puede agregar elementos a la lista mediante el <xref:System.Windows.Forms.ComboBox.Items%2A> propiedad en el diseñador.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ComboBox>
- [Información general sobre el control ListBox](listbox-control-overview-windows-forms.md)
- [Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [Filtrar para agregar y quitar elementos de un control ComboBox, ListBox o CheckedListBox de formularios Windows Forms](add-and-remove-items-from-a-wf-combobox.md)
- [Filtrar para ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Filtrar para obtener acceso a elementos específicos de un control ComboBox, ListBox o CheckedListBox de formularios Windows Forms](access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)
- [Filtrar para enlazar un control ComboBox o ListBox de formularios Windows Forms a datos](how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)
- [Controles de formularios Windows Forms usados para mostrar opciones](windows-forms-controls-used-to-list-options.md)
- [Filtrar para crear una tabla de búsqueda para un control ComboBox, ListBox o CheckedListBox de formularios Windows Forms](create-a-lookup-table-for-a-wf-combobox-listbox.md)
