---
title: "Información general sobre ListBox (Control, formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ListBox
helpviewer_keywords:
- list boxes [Windows Forms], about list boxes
- ListBox control [Windows Forms], about ListBox control
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f0eadf9db9a952fdabe77100cb31501be1970e74
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="listbox-control-overview-windows-forms"></a>Información general sobre ListBox (Control, formularios Windows Forms)
Un formulario Windows Forms <xref:System.Windows.Forms.ListBox> control muestra una lista desde el que el usuario puede seleccionar uno o varios elementos. Si el número total de elementos supera el número que se pueden mostrar, automáticamente se agrega una barra de desplazamiento a la <xref:System.Windows.Forms.ListBox> control. Cuando el <xref:System.Windows.Forms.ListBox.MultiColumn%2A> propiedad está establecida en `true`, el cuadro de lista muestra elementos en varias columnas y aparece una barra de desplazamiento horizontal. Cuando el <xref:System.Windows.Forms.ListBox.MultiColumn%2A> propiedad está establecida en `false`, el cuadro de lista muestra elementos en una sola columna y aparece una barra de desplazamiento vertical. Cuando <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A> se establece en `true`, aparece la barra de desplazamiento, independientemente del número de elementos. El <xref:System.Windows.Forms.ListBox.SelectionMode%2A> propiedad determina cuántos elementos de la lista pueden seleccionarse a la vez.  
  
## <a name="ways-to-change-the-listbox-control"></a>Formas de cambiar el Control de cuadro de lista  
 El <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> propiedad devuelve un valor entero que corresponde al primer elemento seleccionado en el cuadro de lista. Puede cambiar mediante programación el elemento seleccionado cambiando el <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> del valor en el código; el elemento correspondiente en la lista aparecerán resaltado en el Windows Form. Si se selecciona ningún elemento, el <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> valor es -1. Si se selecciona el primer elemento de la lista, el <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> valor es 0. Cuando se seleccionan varios elementos, la <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> valor refleja el elemento seleccionado que aparece en primer lugar en la lista. El <xref:System.Windows.Forms.ListBox.SelectedItem%2A> propiedad es similar a <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>, pero devuelve el elemento en Sí, normalmente un valor de cadena. El <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> propiedad refleja el número de elementos de la lista y el valor de la <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> propiedad siempre es uno más que el mayor tamaño posible <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> valor porque <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> está basado en cero.  
  
 Para agregar o eliminar elementos en una <xref:System.Windows.Forms.ListBox> de control, use la <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> o <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A> método. Como alternativa, puede agregar elementos a la lista mediante el <xref:System.Windows.Forms.ListBox.Items%2A> propiedad en tiempo de diseño.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ListBox>  
 [Agregar y quitar elementos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [Ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [Enlazar un control ComboBox o ListBox de formularios Windows Forms a datos](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)  
 [Información general sobre el control ComboBox](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)  
 [CheckedListBox Control Overview](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)  
 [Controles de formularios Windows Forms usados para mostrar opciones](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)  
 [Crear una tabla de búsqueda para un control ComboBox, ListBox o CheckedListBox de Windows Forms](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)
