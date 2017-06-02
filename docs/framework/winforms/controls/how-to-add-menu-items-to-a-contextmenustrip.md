---
title: "C&#243;mo: Agregar elementos de men&#250; a ContextMenuStrip | Microsoft Docs"
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
  - "menús contextuales, agregar elementos de menú"
  - "ContextMenuStrips, agregar elementos de menú"
  - "menús contextuales, agregar elementos"
ms.assetid: 1ec14776-3ea2-4752-bd22-4fae0fd19e1a
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Agregar elementos de men&#250; a ContextMenuStrip
Puede agregar un único elemento de menú o varios elementos a la vez a <xref:System.Windows.Forms.ContextMenuStrip>.  
  
### Para agregar un elemento de menú único a un ContextMenuStrip  
  
-   Utilice el método <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> para agregar un elemento de menú a <xref:System.Windows.Forms.ContextMenuStrip>.  
  
     \[Visual Basic\]  
  
    ```  
    Me.contextMenuStrip1.Items.Add(Me.toolStripMenuItem1)  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.Add(toolStripMenuItem1);  
    ```  
  
### Para agregar varios elementos de menú a un ContextMenuStrip  
  
-   Utilice el método <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> para agregar varios elementos de menú a <xref:System.Windows.Forms.ContextMenuStrip>.  
  
     \[Visual Basic\]  
  
    ```  
    Me.contextMenuStrip1.Items.AddRange(New _  
       System.Windows.Forms.ToolStripItem() {Me.toolStripMenuItem1, _  
          Me.toolStripMenuItem2})  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.AddRange(new   
       System.Windows.Forms.ToolStripItem[] {  
          this.toolStripMenuItem1, this.toolStripMenuItem2});  
    ```  
  
## Vea también  
 [ContextMenuStrip \(Control\)](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)