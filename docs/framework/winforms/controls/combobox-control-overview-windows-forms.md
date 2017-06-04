---
title: "Informaci&#243;n general sobre el control ComboBox (formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ComboBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "cuadros combinados, acerca de los cuadros combinados"
  - "ComboBox (control) [Windows Forms], acerca del control ComboBox"
  - "listas desplegables, ComboBox (control)"
  - "listas desplegables, Windows Forms"
ms.assetid: a58b393f-a614-45d1-8961-857a024b5acd
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Informaci&#243;n general sobre el control ComboBox (formularios Windows Forms)
El control <xref:System.Windows.Forms.ComboBox> de Windows Forms se utiliza para mostrar datos en un cuadro combinado desplegable.  De forma predeterminada, el control <xref:System.Windows.Forms.ComboBox> aparece en dos partes: la parte superior es un cuadro de texto que permite al usuario escribir un elemento de la lista.  La segunda parte es un cuadro de lista que muestra una lista de elementos, de los cuales el usuario puede seleccionar uno.  Para obtener más información sobre otros estilos de cuadro combinado, vea [Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md).  
  
 La propiedad <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> devuelve un valor entero que corresponde al elemento seleccionado en la lista.  Para cambiar mediante programación el elemento seleccionado, cambie el valor de <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> en el código; el elemento correspondiente de la lista aparecerá en la parte de cuadro de texto del cuadro combinado.  Si no se selecciona ningún elemento, el valor de <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> es \-1.   Si se selecciona el primer elemento de la lista, el valor de <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> es 0.  La propiedad <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> es similar a <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>, pero devuelve el elemento en sí, habitualmente un valor de cadena.  La propiedad <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> refleja el número de elementos de la lista. El valor de la propiedad <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> es siempre una unidad más que el máximo valor posible para <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>, ya que <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> está basada en cero.  
  
 Para agregar o eliminar los elementos en un control <xref:System.Windows.Forms.ComboBox>, utilice el método <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A> o <xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A>.  También puede agregar elementos a la lista mediante la propiedad <xref:System.Windows.Forms.ComboBox.Items%2A> en el diseñador.  
  
## Vea también  
 <xref:System.Windows.Forms.ComboBox>   
 [Información general sobre ListBox \(Control\)](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)   
 [Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)   
 [Cómo: Agregar y quitar elementos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)   
 [Cómo: Ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)   
 [Cómo: Obtener acceso a elementos específicos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)   
 [Cómo: Enlazar un control ComboBox o ListBox de formularios Windows Forms a datos](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)   
 [Controles de formularios Windows Forms usados para mostrar opciones](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)   
 [Cómo: Crear una tabla de búsqueda para un control ComboBox, ListBox o CheckedListBox de Windows Forms](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)