---
title: "C&#243;mo: Mejorar el rendimiento del desplazamiento de un control ListBox | Microsoft Docs"
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
  - "ListBox (control) [WPF], mejorar el rendimiento de desplazamiento"
  - "ListBox (control) [WPF], reutilizar contenedores de elementos"
ms.assetid: 1e2bf8f3-c8ce-47f7-a400-a7fe11d1a848
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Mejorar el rendimiento del desplazamiento de un control ListBox
Si <xref:System.Windows.Controls.ListBox> contiene muchos elementos, la respuesta de la interfaz de usuario puede ser lenta cuando un usuario desplaza el control <xref:System.Windows.Controls.ListBox> utilizando la rueda del mouse o arrastrando el cuadro de una barra de desplazamiento.  Puede mejorar el rendimiento de <xref:System.Windows.Controls.ListBox> cuando el usuario se desplaza estableciendo la propiedad adjunta <xref:System.Windows.Controls.VirtualizingStackPanel.VirtualizationMode%2A?displayProperty=fullName> en <xref:System.Windows.Controls.VirtualizationMode>.  
  
## Ejemplo  
  
## Descripción  
 En el ejemplo siguiente se crea un control <xref:System.Windows.Controls.ListBox> y se establece la propiedad <xref:System.Windows.Controls.VirtualizingStackPanel.VirtualizationMode%2A?displayProperty=fullName> en <xref:System.Windows.Controls.VirtualizationMode> para mejorar el rendimiento durante los desplazamientos.  
  
## Código  
 [!code-xml[RecycleItemContainerShippets#VirtualizationMode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 En el ejemplo siguiente se muestran los datos que se utilizan en el ejemplo anterior.  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]