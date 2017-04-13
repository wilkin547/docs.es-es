---
title: "C&#243;mo: Dividir una ventana horizontalmente | Microsoft Docs"
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
  - "SplitContainer (control) [Windows Forms], divisor horizontal"
  - "ventanas divisoras, cambiar la orientación del divisor"
  - "ventanas divisoras, horizontal"
  - "ventanas, dividir horizontalmente"
ms.assetid: a1f74f29-048c-4723-85fa-b9d375ab8f4b
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Dividir una ventana horizontalmente
El ejemplo de código siguiente coloca en posición horizontal el divisor que divide el control <xref:System.Windows.Forms.SplitContainer>.  
  
> [!NOTE]
>  La propiedad <xref:System.Windows.Forms.SplitContainer.Orientation%2A> del control <xref:System.Windows.Forms.SplitContainer> determina la dirección del divisor, no del control propiamente dicho.  
  
### Para dividir una ventana horizontalmente  
  
1.  Dentro de un procedimiento, establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Orientation%2A> del control <xref:System.Windows.Forms.SplitContainer> en <xref:System.Windows.Forms.Orientation>.  
  
    ```vb  
    Sub ShowSplitContainer()  
        Dim splitContainer1 as new SplitContainer()  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D  
        splitContainer1.Location = New System.Drawing.Point(74, 20)  
        splitContainer1.Name = "DemoSplitContainer"  
        splitContainer1.Size = New System.Drawing.Size(212, 435)  
        splitContainer1.TabIndex = 0  
        splitContainer1.Orientation = Orientation.Horizontal  
        Controls.Add(splitContainer1)  
    End Sub  
  
    ```  
  
    ```csharp  
    public void showSplitContainer()  
    {  
        SplitContainer splitContainer1 = new SplitContainer ();  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D;  
        splitContainer1.Location = new System.Drawing.Point (74, 20);  
        splitContainer1.Name = "DemoSplitContainer";  
        splitContainer1.Size = new System.Drawing.Size (212, 435);  
        splitContainer1.TabIndex = 0;  
        splitContainer1.Orientation = Orientation.Horizontal;  
        this.Controls.Add (splitContainer1);  
  
    }  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.SplitContainer>   
 [SplitContainer \(Control\)](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)