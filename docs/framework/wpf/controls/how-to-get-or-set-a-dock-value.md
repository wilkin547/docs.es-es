---
title: "C&#243;mo: Obtener o establecer un valor de acoplamiento | Microsoft Docs"
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
  - "Dock (valores), obtener"
  - "Dock (valores), establecer"
ms.assetid: fcf4ab8a-c7cd-4835-8d04-de1c999ab4a8
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Obtener o establecer un valor de acoplamiento
En el ejemplo siguiente se muestra cómo asignar un valor <xref:System.Windows.Controls.Dock> para un objeto.  El ejemplo usa los métodos <xref:System.Windows.Controls.DockPanel.GetDock%2A> y <xref:System.Windows.Controls.DockPanel.SetDock%2A> de <xref:System.Windows.Controls.DockPanel>.  
  
## Ejemplo  
 En el ejemplo se crea una instancia del elemento <xref:System.Windows.Controls.TextBlock>, `txt1`, y se asigna un valor `Top` para <xref:System.Windows.Controls.Dock> mediante el método <xref:System.Windows.Controls.DockPanel.SetDock%2A> de <xref:System.Windows.Controls.DockPanel>.  Después, se anexa el valor de <xref:System.Windows.Controls.Dock> a la propiedad <xref:System.Windows.Controls.TextBlock.Text%2A> del elemento <xref:System.Windows.Controls.TextBlock> a través del método <xref:System.Windows.Controls.DockPanel.GetDock%2A>.  Por último, se agrega el elemento <xref:System.Windows.Controls.TextBlock> al objeto <xref:System.Windows.Controls.DockPanel>primario, `dp1`.  
  
 [!code-csharp[DockPanelSetDock#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## Vea también  
 <xref:System.Windows.Controls.DockPanel>   
 <xref:System.Windows.Controls.DockPanel.GetDock%2A>   
 <xref:System.Windows.Controls.DockPanel.SetDock%2A>   
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)