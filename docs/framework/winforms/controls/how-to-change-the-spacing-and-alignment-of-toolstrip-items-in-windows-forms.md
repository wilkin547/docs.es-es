---
title: "C&#243;mo: Cambiar el espaciado y la alineaci&#243;n de los elementos ToolStrip en formularios Windows Forms | Microsoft Docs"
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
  - "ejemplos [Windows Forms], barras de herramientas"
  - "barras de herramientas [Windows Forms], alinear elementos"
  - "ToolStrip (control) [Windows Forms], alinear elementos"
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Cambiar el espaciado y la alineaci&#243;n de los elementos ToolStrip en formularios Windows Forms
El control <xref:System.Windows.Forms.ToolStrip> admite todas las características de diseño como ajuste de tamaño, el espaciado de los controles <xref:System.Windows.Forms.ToolStripItem> entre sí, la disposición de los controles en <xref:System.Windows.Forms.ToolStrip> y el espaciado de los controles en relación con el <xref:System.Windows.Forms.ToolStrip>.  
  
 Puesto que el valor predeterminado de la propiedad <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> es `true`, automáticamente se ajusta el tamaño de los controles a menos que la propiedad <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> se establezca en `false`.  
  
### Para ajustar el tamaño de un ToolStripItem manualmente  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> en `false` para el control asociado.  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
  
    ```  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Size%2A> como desee para el control <xref:System.Windows.Forms.ToolStripItem> asociado.  
  
### Para establecer el espaciado de un ToolStripItem  
  
1.  Inserte los valores deseados, en píxeles, en la propiedad <xref:System.Windows.Forms.ToolStripItem.Margin%2A> del control asociado.  
  
     Los valores de la propiedad <xref:System.Windows.Forms.ToolStripItem.Margin%2A> especifican el espaciado entre el elemento y los elementos adyacentes, en este orden: Izquierdo, Superior, Derecho e Inferior.  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
  
    ```  
  
### Para alinear un ToolStripItem a la derecha de ToolStrip  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> en <xref:System.Windows.Forms.ToolStripItemAlignment> para el control asociado.  De forma predeterminada, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> se establece en <xref:System.Windows.Forms.ToolStripItemAlignment> que alinea los controles al lado izquierdo de <xref:System.Windows.Forms.ToolStrip>.  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
  
    ```  
  
### Para organizar los elementos ToolStrip en ToolStrip  
  
-   Establezca la propiedad <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> en el valor de <xref:System.Windows.Forms.ToolStripLayoutStyle> que desea.  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.Control.Layout>   
 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>   
 <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>   
 <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>   
 <xref:System.Windows.Forms.ToolStripItem.Placement%2A>   
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>   
 [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Arquitectura del control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Resumen de la tecnología ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)