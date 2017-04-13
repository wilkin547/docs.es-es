---
title: "Informaci&#243;n general sobre ListBox (Control, formularios Windows Forms) | Microsoft Docs"
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
  - "ListBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "cuadros de lista, acerca de los cuadros de texto"
  - "ListBox (control) [Windows Forms], acerca del control ListBox"
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Informaci&#243;n general sobre ListBox (Control, formularios Windows Forms)
Un control <xref:System.Windows.Forms.ListBox> de formularios Windows Forms muestra una lista de elementos entre los que el usuario puede seleccionar uno o más.  Si el número total de elementos supera el número que se puede mostrar, se agrega automáticamente una barra de desplazamiento al control <xref:System.Windows.Forms.ListBox>.  Cuando la propiedad <xref:System.Windows.Forms.ListBox.MultiColumn%2A> se establece en `true`, el cuadro de lista muestra elementos en varias columnas y aparece una barra de desplazamiento horizontal.  Cuando la propiedad <xref:System.Windows.Forms.ListBox.MultiColumn%2A> se establece en `false`, el cuadro de lista muestra los elementos en una sola columna y aparece una barra de desplazamiento vertical.  Cuando <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A> se establece en `true`, la barra de desplazamiento aparece, independientemente del número de elementos.  La propiedad <xref:System.Windows.Forms.ListBox.SelectionMode%2A> determina cuántos elementos de la lista pueden seleccionarse a la vez.  
  
## Maneras de modificar el control ListBox  
 La propiedad <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> devuelve un valor entero que corresponde al primer elemento seleccionado en el cuadro de lista.  Para cambiar mediante programación el elemento seleccionado, cambie el valor de la propiedad <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> en el código; el elemento correspondiente de la lista aparecerá resaltado en el Windows Form.  Si no se selecciona ningún elemento, el valor de <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> es \-1.   Si el primer elemento de la lista está seleccionado, el valor de <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> es 0.  Cuando varios elementos están seleccionados, el valor <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> refleja el elemento seleccionado que aparece primero en la lista.  La propiedad <xref:System.Windows.Forms.ListBox.SelectedItem%2A> es similar a <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>, pero devuelve el elemento en sí, habitualmente un valor de cadena.  La propiedad <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> refleja el número de elementos de la lista. El valor de la propiedad <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> es siempre una unidad más que el máximo valor posible para <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>, ya que <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> está basada en cero.  
  
 Para agregar o eliminar los elementos en un control <xref:System.Windows.Forms.ListBox>, utilice el método <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> o <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A>.  También puede agregar elementos a la lista mediante la propiedad <xref:System.Windows.Forms.ListBox.Items%2A> en tiempo de diseño.  
  
## Vea también  
 <xref:System.Windows.Forms.ListBox>   
 [Cómo: Agregar y quitar elementos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)   
 [Cómo: Ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)   
 [Cómo: Enlazar un control ComboBox o ListBox de formularios Windows Forms a datos](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)   
 [Información general sobre el control ComboBox](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)   
 [Información general sobre el control CheckedListBox](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)   
 [Controles de formularios Windows Forms usados para mostrar opciones](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)   
 [Cómo: Crear una tabla de búsqueda para un control ComboBox, ListBox o CheckedListBox de Windows Forms](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)