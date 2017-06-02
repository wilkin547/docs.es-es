---
title: "Cu&#225;ndo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles enlazados, cuadros combinados"
  - "cuadros combinados, comparados con cuadros de lista"
  - "ComboBox (control) [Windows Forms], comparado con ListBox"
  - "ListBox (control) [Windows Forms], obtener acceso a elementos"
  - "ListBox (control) [Windows Forms], agregar y quitar elementos"
  - "ListBox (control) [Windows Forms], ComboBox"
  - "ListCount (propiedad)"
  - "ListIndex (propiedad)"
  - "controles de Windows Forms, enlace de datos"
ms.assetid: 7bcaea58-1cfa-46db-9baf-b75a69d8f9ec
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Cu&#225;ndo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox
Los controles <xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.ListBox> se comportan de forma similar y en algunos casos pueden ser intercambiables.  No obstante, hay veces en las que uno de ellos resulta más adecuado que el otro para una tarea determinada.  
  
 Generalmente, los cuadros combinados resultan adecuados cuando hay una lista de opciones sugeridas; los cuadros de lista son más adecuados cuando se desea limitar las entradas posibles a los elementos de la lista.  Un cuadro combinado contiene un campo de cuadro de texto, por lo que las opciones que no estén en la lista se pueden escribir.  La excepción es cuando la propiedad <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> se establece en <xref:System.Windows.Forms.ComboBoxStyle>.  En ese caso, el control seleccionará un elemento si escribe su primera letra.  
  
 Además, los cuadros combinados ahorran espacio en un formulario.  Dado que la lista completa no se muestra hasta que el usuario hace clic en la flecha abajo, un cuadro combinado cabe fácilmente en un espacio pequeño en el que no cabría un cuadro de lista.  La excepción se produce cuando la propiedad <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> se establece en <xref:System.Windows.Forms.ComboBoxStyle>: se muestra la lista completa y el cuadro combinado ocupa más espacio que el que ocuparía un cuadro de lista.  
  
## Vea también  
 <xref:System.Windows.Forms.ComboBox>   
 <xref:System.Windows.Forms.ListBox>   
 [Cómo: Agregar y quitar elementos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)   
 [Cómo: Ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)   
 [Controles de formularios Windows Forms usados para mostrar opciones](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)