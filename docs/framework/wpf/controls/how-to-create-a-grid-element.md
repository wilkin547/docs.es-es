---
title: "C&#243;mo: Crear un elemento Grid | Microsoft Docs"
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
  - "Grid (control), crear, instancia de cuadrícula"
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Crear un elemento Grid
## Ejemplo  
 En el ejemplo siguiente se muestra cómo crear y usar una instancia de <xref:System.Windows.Controls.Grid> mediante el uso de código o [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  En este ejemplo se utilizan tres objetos <xref:System.Windows.Controls.ColumnDefinition> y tres objetos <xref:System.Windows.Controls.RowDefinition> para crear una cuadrícula que tiene nueve celdas, como en una hoja de cálculo.  Cada celda contiene un elemento <xref:System.Windows.Controls.TextBlock> que representa los datos y la fila superior contiene un objeto <xref:System.Windows.Controls.TextBlock> con la propiedad <xref:System.Windows.Controls.Grid.ColumnSpan%2A> aplicada.  Para mostrar los límites de cada celda, se habilita la propiedad <xref:System.Windows.Controls.Grid.ShowGridLines%2A>.  
  
 [!code-csharp[Grid#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xml[Grid#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
## Vea también  
 <xref:System.Windows.Controls.Grid>   
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)