---
title: "C&#243;mo: Agregar elementos a controles DomainUpDown de formularios Windows Forms mediante programaci&#243;n | Microsoft Docs"
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
  - "DomainUpDown (control) [Windows Forms], agregar elementos"
  - "control de botón de número, agregar elementos"
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Agregar elementos a controles DomainUpDown de formularios Windows Forms mediante programaci&#243;n
Puede agregar elementos al control <xref:System.Windows.Forms.DomainUpDown> de formularios Windows Forms en el código.  Llame al método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> o <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> de la clase <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> para agregar elementos a la propiedad <xref:System.Windows.Forms.DomainUpDown.Items%2A> del control.  El método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> agrega un elemento al final de una colección, mientras que el método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> agrega un elemento en una posición especificada.  
  
### Para agregar un nuevo elemento  
  
1.  Utilice el método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> para agregar un elemento al final de la lista de elementos.  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     O bien  
  
2.  Utilice el método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> para insertar un elemento en la lista en una posición especificada.  
  
    ```vb  
    ' Inserts an item at the third position in the list  
    DomainUpDown1.Items.Insert(2, "rice")  
  
    ```  
  
    ```csharp  
    // Inserts an item at the third position in the list  
    domainUpDown1.Items.Insert(2, "rice");  
  
    ```  
  
    ```cpp  
    // Inserts an item at the third position in the list  
    domainUpDown1->Items->Insert(2, "rice");  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.DomainUpDown>   
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=fullName>   
 <xref:System.Collections.ArrayList.Insert%2A?displayProperty=fullName>   
 [DomainUpDown \(Control\)](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)   
 [Información general sobre el control DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)