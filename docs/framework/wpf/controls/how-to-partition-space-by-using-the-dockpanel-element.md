---
title: "C&#243;mo: Crear una partici&#243;n del espacio mediante el elemento DockPanel | Microsoft Docs"
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
  - "controles [WPF], DockPanel"
  - "DockPanel (control), realizar particiones del espacio"
  - "realizar particiones del espacio"
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Crear una partici&#243;n del espacio mediante el elemento DockPanel
En el ejemplo siguiente se crea un marco de [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] simple mediante un elemento <xref:System.Windows.Controls.DockPanel>.  El objeto <xref:System.Windows.Controls.DockPanel> crea particiones del espacio disponible para los elementos secundarios.  
  
## Ejemplo  
 En este ejemplo se usa la propiedad <xref:System.Windows.Controls.DockPanel.Dock%2A>, que es una [propiedad asociada](GTMT), para acoplar dos elementos <xref:System.Windows.Controls.Border> idénticos en la parte superior \(<xref:System.Windows.Controls.Dock>\) del espacio subdividido.  Un tercer elemento <xref:System.Windows.Controls.Border> se acopla a la izquierda \(<xref:System.Windows.Controls.Dock>\), con un ancho establecido en 200 píxeles.  Un cuarto elemento <xref:System.Windows.Controls.Border> se acopla en la parte inferior \(<xref:System.Windows.Controls.Dock>\) de la pantalla.  El último elemento <xref:System.Windows.Controls.Border> rellena automáticamente el espacio restante.  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  De forma predeterminada, el último elemento secundario de un elemento <xref:System.Windows.Controls.DockPanel> rellena el espacio restante sin asignar.  Si no desea este comportamiento, establezca `LastChildFill="False"`.  
  
 La aplicación compilada produce una nueva interfaz de usuario con esta apariencia.  
  
 ![Escenario DockPanel típico.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.png "panel\_intro\_dockpanel")  
  
## Vea también  
 <xref:System.Windows.Controls.DockPanel>   
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)