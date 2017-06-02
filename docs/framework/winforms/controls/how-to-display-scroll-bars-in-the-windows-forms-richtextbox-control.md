---
title: "C&#243;mo: Mostrar barras de desplazamiento en el control RichTextBox de formularios Windows Forms | Microsoft Docs"
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
  - "RichTextBox (control) [Windows Forms], mostrar barras de desplazamiento"
  - "barras de desplazamiento, mostrar en controles"
  - "cuadros de texto, mostrar barras de desplazamiento"
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Mostrar barras de desplazamiento en el control RichTextBox de formularios Windows Forms
De forma predeterminada, el control <xref:System.Windows.Forms.RichTextBox> de formularios Windows Forms muestra las barras de desplazamiento horizontal y vertical cuando es necesario.  Hay siete valores posibles para la propiedad <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> del control <xref:System.Windows.Forms.RichTextBox>, que se describen en la tabla siguiente.  
  
### Para mostrar barras de desplazamiento en un control RichTextBox  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.Multiline%2A> en `true`.  Si la propiedad <xref:System.Windows.Forms.RichTextBox.Multiline%2A> se establece en `false`, no se mostrará ningún tipo de barra de desplazamiento, incluida la horizontal.  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> en un valor apropiado de la enumeración <xref:System.Windows.Forms.RichTextBoxScrollBars>.  
  
    |Valor|Descripción|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars> \(valor predeterminado\)|Muestra las barras de desplazamiento horizontal o vertical, o ambas, sólo cuando el texto supera el ancho o el alto del control.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|Nunca muestra ningún tipo de barra de desplazamiento.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|Muestra una barra de desplazamiento horizontal sólo cuando el texto supera el ancho del control.  \(Para que esto ocurra, es necesario establecer la propiedad <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> en `false`.\)|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|Muestra una barra de desplazamiento vertical sólo cuando el texto supera el alto del control.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|Muestra una barra de desplazamiento horizontal cuando la propiedad <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> está establecida en `false`.  La barra de desplazamiento aparece atenuada cuando el texto no supera el ancho del control.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|Muestra siempre una barra de desplazamiento vertical.  La barra de desplazamiento aparece atenuada cuando el texto no supera el alto del control.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|Muestra siempre una barra de desplazamiento vertical.  Muestra una barra de desplazamiento horizontal cuando la propiedad <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> está establecida en `false`.  Las barras de desplazamiento aparecen en gris cuando el texto no supera el ancho o el alto del control.|  
  
3.  Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> en un valor apropiado.  
  
    |Valor|Descripción|  
    |-----------|-----------------|  
    |`false`|El texto del control no se ajustará automáticamente al ancho del control, así que se desplazará hacia la derecha hasta encontrar un salto de línea.  Utilice este valor si anteriormente eligió las barras de desplazamiento horizontal o vertical.|  
    |`true` \(valor predeterminado\)|El texto del control se ajustará automáticamente al ancho del control.  La barra de desplazamiento horizontal no aparecerá.  Utilice este valor si anteriormente eligió los valores Vertical o None para las barras de desplazamiento con el fin de mostrar uno o más párrafos.|  
  
## Vea también  
 <xref:System.Windows.Forms.RichTextBoxScrollBars>   
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox \(Control\)](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)