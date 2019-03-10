---
title: Información general sobre ListBox (Control, formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ListBox
helpviewer_keywords:
- list boxes [Windows Forms], about list boxes
- ListBox control [Windows Forms], about ListBox control
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
ms.openlocfilehash: 2bba90f704458e1c724328feccaaf6f04b98ecb4
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723990"
---
# <a name="listbox-control-overview-windows-forms"></a>Información general sobre ListBox (Control, formularios Windows Forms)
Un formulario Windows Forms <xref:System.Windows.Forms.ListBox> control muestra una lista desde el que el usuario puede seleccionar uno o varios elementos. Si el número total de elementos supera el número que se puede mostrar, una barra de desplazamiento se agrega automáticamente a la <xref:System.Windows.Forms.ListBox> control. Cuando el <xref:System.Windows.Forms.ListBox.MultiColumn%2A> propiedad está establecida en `true`, el cuadro de lista muestra elementos en varias columnas y aparece una barra de desplazamiento horizontal. Cuando el <xref:System.Windows.Forms.ListBox.MultiColumn%2A> propiedad está establecida en `false`, el cuadro de lista muestra los elementos en una sola columna y aparece una barra de desplazamiento vertical. Cuando <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A> está establecido en `true`, aparece la barra de desplazamiento, independientemente del número de elementos. El <xref:System.Windows.Forms.ListBox.SelectionMode%2A> propiedad determina cuántos elementos de lista se pueden seleccionar a la vez.  
  
## <a name="ways-to-change-the-listbox-control"></a>Formas de cambiar el Control ListBox  
 El <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> propiedad devuelve un valor entero que corresponde al primer elemento seleccionado en el cuadro de lista. Puede cambiar mediante programación el elemento seleccionado, cambie el <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> valor en el código; el elemento correspondiente en la lista aparecerán resaltado en el formulario de Windows. Si se selecciona ningún elemento, el <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> valor es -1. Si se selecciona el primer elemento en la lista, el <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> valor es 0. Cuando se seleccionan varios elementos, el <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> valor refleja el elemento seleccionado que aparece en primer lugar en la lista. El <xref:System.Windows.Forms.ListBox.SelectedItem%2A> es similar a la propiedad <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>, pero devuelve el elemento, normalmente un valor de cadena. El <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> propiedad refleja el número de elementos de la lista y el valor de la <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> propiedad siempre es uno más que lo más grande posible <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> valor porque <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> está basado en cero.  
  
 Para agregar o eliminar elementos en un <xref:System.Windows.Forms.ListBox> controlar, use el <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> o <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A> método. Como alternativa, puede agregar elementos a la lista mediante el <xref:System.Windows.Forms.ListBox.Items%2A> propiedad en tiempo de diseño.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ListBox>
- [Cómo: Agregar y quitar elementos de un Windows Forms control ComboBox, ListBox o CheckedListBox (Control)](add-and-remove-items-from-a-wf-combobox.md)
- [Cómo: Ordenar el contenido de un Windows Forms control ComboBox, ListBox o CheckedListBox (Control)](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Cómo: Enlazar un Control de ListBox o ComboBox de formularios Windows Forms a datos](how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)
- [Información general sobre el control ComboBox](combobox-control-overview-windows-forms.md)
- [CheckedListBox Control Overview](checkedlistbox-control-overview-windows-forms.md)
- [Controles de formularios Windows Forms usados para mostrar opciones](windows-forms-controls-used-to-list-options.md)
- [Cómo: Crear una tabla de búsqueda para un Windows Forms control ComboBox, ListBox o CheckedListBox (Control)](create-a-lookup-table-for-a-wf-combobox-listbox.md)
