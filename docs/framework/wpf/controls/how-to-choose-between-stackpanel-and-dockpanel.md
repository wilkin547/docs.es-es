---
title: "C&#243;mo: Elegir entre StackPanel y DockPanel | Microsoft Docs"
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
  - "controles [WPF], StackPanel"
  - "DockPanel (control), StackPanel (control) frente a"
  - "StackPanel (control), DockPanel (control) frente a"
ms.assetid: f9239086-451f-42e6-81f7-ef89ef349742
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Elegir entre StackPanel y DockPanel
En este ejemplo se muestra cómo elegir entre el uso de <xref:System.Windows.Controls.StackPanel> o <xref:System.Windows.Controls.DockPanel> al apilar el contenido en un elemento <xref:System.Windows.Controls.Panel>.  
  
## Ejemplo  
 Aunque puede usar <xref:System.Windows.Controls.DockPanel> o <xref:System.Windows.Controls.StackPanel> para apilar los elementos secundarios, los dos controles no siempre generan los mismos resultados.  Por ejemplo, el orden en el que se colocan los elementos secundarios puede afectar al tamaño de los elementos secundarios en <xref:System.Windows.Controls.DockPanel> pero no en <xref:System.Windows.Controls.StackPanel>.  Este comportamiento diferente se debe a que <xref:System.Windows.Controls.StackPanel> mide en la dirección de apilado en <xref:System.Double>.<xref:System.Double.PositiveInfinity>, pero <xref:System.Windows.Controls.DockPanel> mide solo el tamaño disponible.  
  
 En el ejemplo siguiente se muestra esta diferencia clave entre <xref:System.Windows.Controls.DockPanel> y <xref:System.Windows.Controls.StackPanel>.  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
## Vea también  
 <xref:System.Windows.Controls.StackPanel>   
 <xref:System.Windows.Controls.DockPanel>   
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)