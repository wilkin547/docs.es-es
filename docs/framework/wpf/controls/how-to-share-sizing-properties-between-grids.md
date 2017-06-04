---
title: "C&#243;mo: Compartir propiedades de ajuste de tama&#241;o entre elementos Grid | Microsoft Docs"
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
  - "Grid (control), compartir datos de ajuste de tamaño de las columnas"
  - "Grid (control), compartir datos de ajuste de tamaño de las filas"
  - "datos de ajuste de tamaño de controles Grid"
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Compartir propiedades de ajuste de tama&#241;o entre elementos Grid
En este ejemplo se muestra cómo compartir los datos de tamaño de columnas y filas entre elementos <xref:System.Windows.Controls.Grid> para mantener un tamaño coherente.  
  
## Ejemplo  
 En el ejemplo siguiente se incluyen dos elementos <xref:System.Windows.Controls.Grid> como elementos secundarios de un <xref:System.Windows.Controls.DockPanel> primario.  La [propiedad adjunta](GTMT) <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> de <xref:System.Windows.Controls.Grid> se define en el objeto <xref:System.Windows.Controls.DockPanel> primario.  
  
 En el ejemplo se manipula el valor de propiedad mediante dos elementos <xref:System.Windows.Controls.Button>, cada uno de los cuales representa uno de los valores booleanos de propiedad.  Cuando el valor de propiedad <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> se establece en `true`, cada miembro de columna o fila de <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> comparte la información de tamaño, sin tener en cuenta el contenido de la fila o columna.  
  
 [!code-xml[gridIssharedsizescopeProp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 ...  
  
 [!code-xml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 En el siguiente ejemplo de código subyacente se controlan los métodos que provocan el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> de botón.  En el ejemplo, los resultados de estas llamadas a método se escriben en elementos <xref:System.Windows.Controls.TextBlock> que usan métodos Get relacionados para generar los nuevos valores de propiedad como cadenas.  
  
 [!code-csharp[gridIssharedsizescopeProp#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## Vea también  
 <xref:System.Windows.Controls.Grid>   
 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>   
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)