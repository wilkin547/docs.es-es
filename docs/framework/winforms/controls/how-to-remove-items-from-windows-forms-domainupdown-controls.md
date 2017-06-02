---
title: "C&#243;mo: Quitar elementos de los controles DomainUpDown de formularios Windows Forms | Microsoft Docs"
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
  - "DomainUpDown (control) [Windows Forms], quitar elementos"
  - "control de botón de número, quitar elementos"
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Quitar elementos de los controles DomainUpDown de formularios Windows Forms
Se pueden quitar los elementos del control <xref:System.Windows.Forms.DomainUpDown> de formularios Windows Forms llamando al método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> o <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> de la clase <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>.  El método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> quita un elemento específico, mientras que el método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> quita un elemento según su posición.  
  
### Para quitar un elemento  
  
-   Utilice el método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> de la clase <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> para quitar un elemento por nombre.  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     O bien  
  
-   Utilice el método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> para quitar un elemento por su posición.  
  
    ```vb  
    ' Removes the first item in the list.  
    DomainUpDown1.Items.RemoveAt(0)  
  
    ```  
  
    ```csharp  
    // Removes the first item in the list.  
    domainUpDown1.Items.RemoveAt(0);  
  
    ```  
  
    ```cpp  
    // Removes the first item in the list.  
    domainUpDown1->Items->RemoveAt(0);  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.DomainUpDown>   
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=fullName>   
 [DomainUpDown \(Control\)](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)   
 [Información general sobre el control DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)