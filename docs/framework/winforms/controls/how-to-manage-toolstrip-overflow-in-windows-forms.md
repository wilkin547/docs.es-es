---
title: "C&#243;mo: Administrar el desbordamiento de ToolStrip en formularios Windows Forms | Microsoft Docs"
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
  - "CanOverflow (propiedad)"
  - "ejemplos [Windows Forms], barras de herramientas"
  - "Overflow (propiedad)"
  - "barras de herramientas [Windows Forms], administrar desbordamiento"
  - "ToolStrip (control) [Windows Forms], administrar desbordamiento"
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Administrar el desbordamiento de ToolStrip en formularios Windows Forms
Cuando todos los elementos de un control <xref:System.Windows.Forms.ToolStrip> no se ajustan a un espacio asignado, puede habilitar la funcionalidad del desbordamiento en <xref:System.Windows.Forms.ToolStrip> y determinar el comportamiento de desbordamiento de los<xref:System.Windows.Forms.ToolStripItem>s específicos.  
  
 Al agregar <xref:System.Windows.Forms.ToolStripItem>s que requieren más espacio que el que está libre al <xref:System.Windows.Forms.ToolStrip> dado el tamaño actual del formulario, aparece un <xref:System.Windows.Forms.ToolStripOverflowButton> automáticamente en la <xref:System.Windows.Forms.ToolStrip>.  Aparece el <xref:System.Windows.Forms.ToolStripOverflowButton> y los elementos con desbordamiento habilitado se pasan al menú de desbordamiento desplegable.  Esto le permite personalizar y dar prioridad a cómo ajustar sus <xref:System.Windows.Forms.ToolStrip> elementos correctamente a los tamaños de formulario diferentes.  Puede modificar el aspecto de sus elementos cuando se produce el desbordamiento utilizando las propiedades <xref:System.Windows.Forms.ToolStripItem.Placement%2A> y <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=fullName> y el evento <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>.  Si aumenta el formulario ya sea en tiempo de diseño o en tiempo de ejecución, se pueden mostrar más <xref:System.Windows.Forms.ToolStripItem>s en la <xref:System.Windows.Forms.ToolStrip> principal e incluso <xref:System.Windows.Forms.ToolStripOverflowButton> podría desaparecer hasta que disminuyera el tamaño del formulario.  
  
### Para habilitar el desbordamiento en un control ToolStrip  
  
-   Asegúrese de que la propiedad <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> no se establece en `false` para <xref:System.Windows.Forms.ToolStrip>.  El valor predeterminado es `True`.  
  
     Cuando <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> es `True` \(predeterminado\), se envía un <xref:System.Windows.Forms.ToolStripItem> al menú de desbordamiento desplegable cuando el contenido del <xref:System.Windows.Forms.ToolStripItem> supera el ancho de un <xref:System.Windows.Forms.ToolStrip> horizontal o el alto de un <xref:System.Windows.Forms.ToolStrip> vertical.  
  
### Para especificar el comportamiento del desbordamiento de un ToolStripItem concreto  
  
-   Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> del<xref:System.Windows.Forms.ToolStripItem> en el valor que desee.  Las posibilidades son `Always`, `Never` y `AsNeeded`.  predeterminado es `AsNeeded`.  
  
    ```vb  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never  
  
    ```  
  
    ```csharp  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never;  
  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripOverflowButton>   
 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>   
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>   
 [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Arquitectura del control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Resumen de la tecnología ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)