---
title: "C&#243;mo: Ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms | Microsoft Docs"
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
  - "CheckedListBox (control) [Windows Forms], ordenar"
  - "cuadros combinados, ordenar contenido"
  - "ComboBox (control) [Windows Forms], ordenar contenido"
  - "cuadros de lista, ordenar contenido"
  - "ListBox (control) [Windows Forms], ordenar contenido"
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms
Los controles de los formularios Windows Forms no ordenan cuando están enlazados a datos.  Para mostrar datos ordenados, utilice un origen de datos que permita ordenar y, a continuación, haga que el origen de datos ordene los datos.  Los orígenes de datos que permiten ordenar son las vistas de datos, los administradores de vistas de datos y las matrices ordenadas.  
  
 Si el control no está enlazado a datos, puede ordenarlo.  
  
### Para ordenar la lista  
  
1.  Establezca la propiedad  `Sorted`  en `true`.  
  
     Esta configuración cambia de posición todos los elementos de lista existentes de forma ordenada.  
  
## Vea también  
 <xref:System.Windows.Forms.ComboBox>   
 <xref:System.Windows.Forms.ListBox>   
 <xref:System.Windows.Forms.CheckedListBox>   
 [Enlace de datos en Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Cómo: Agregar y quitar elementos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)   
 [Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)   
 [Controles de formularios Windows Forms usados para mostrar opciones](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)