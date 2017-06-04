---
title: "C&#243;mo: Aplicar estilo a controles en un elemento ToolBar | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "personalizar controles en barras de herramientas"
  - "aplicar estilos a controles en barras de herramientas"
  - "barras de herramientas"
ms.assetid: ba6ae056-d6a9-4c24-90f8-467ab0bc0b1a
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# C&#243;mo: Aplicar estilo a controles en un elemento ToolBar
<xref:System.Windows.Controls.ToolBar> define objetos <xref:System.Windows.ResourceKey> para especificar el estilo de los controles dentro de un control <xref:System.Windows.Controls.ToolBar>.  Para aplicar un estilo a un control de una barra de herramientas \(<xref:System.Windows.Controls.ToolBar>\), se establece el atributo `x:key` del estilo en una clave de recurso \(<xref:System.Windows.ResourceKey>\) definida en <xref:System.Windows.Controls.ToolBar>.  
  
 <xref:System.Windows.Controls.ToolBar> define los objetos <xref:System.Windows.ResourceKey> siguientes:  
  
-   <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.CheckBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.MenuStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.RadioButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.SeparatorStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.TextBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ToggleButtonStyleKey%2A>  
  
## Ejemplo  
 En el ejemplo siguiente se definen estilos para los controles de un elemento <xref:System.Windows.Controls.ToolBar>.  
  
 [!code-xml[ToolBar_snip#ToolBarAllStyles](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbarallstyles)]  
[!code-xml[ToolBar_snip#ToolBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbar)]  
  
## Vea también  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)