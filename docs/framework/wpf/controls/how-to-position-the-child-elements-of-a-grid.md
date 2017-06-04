---
title: "C&#243;mo: Situar los elementos secundarios de un control Grid | Microsoft Docs"
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
  - "Grid (control), colocar elementos secundarios"
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Situar los elementos secundarios de un control Grid
En este ejemplo se muestra cómo utilizar los métodos get y set que se definen en <xref:System.Windows.Controls.Grid> para colocar elementos secundarios.  
  
## Ejemplo  
 En el ejemplo siguiente se define un elemento <xref:System.Windows.Controls.Grid> primario \(`grid1`\) que tiene tres columnas y tres filas.  Se agrega un elemento <xref:System.Windows.Shapes.Rectangle> secundario \(`rect1`\) a <xref:System.Windows.Controls.Grid> en la posición de columna cero y la posición de fila cero.  Los elementos <xref:System.Windows.Controls.Button> representan métodos a los que se puede llamar para cambiar la posición del elemento <xref:System.Windows.Shapes.Rectangle> en el control <xref:System.Windows.Controls.Grid>.  Cuando un usuario hace clic en un botón, se activa el método relacionado.  
  
 [!code-xml[gridGetSetMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml#1)]  
  
 En el ejemplo siguiente de código subyacente se administran los métodos provocados por los eventos <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del botón.  En el ejemplo se escriben estas llamadas a los métodos en elementos <xref:System.Windows.Controls.TextBlock> que utilizan métodos get relacionados para generar los nuevos valores de propiedad de tipo String.  
  
 [!code-csharp[gridGetSetMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## Vea también  
 <xref:System.Windows.Controls.Grid>   
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)