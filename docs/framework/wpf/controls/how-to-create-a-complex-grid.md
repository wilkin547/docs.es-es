---
title: "C&#243;mo: Crear un contol Grid complejo | Microsoft Docs"
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
  - "calendario, crear"
  - "Grid (control), crear, cuadrículas complejas"
  - "calendario mensual, crear"
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Crear un contol Grid complejo
En este ejemplo se muestra cómo utilizar un control <xref:System.Windows.Controls.Grid> para crear un diseño que parezca un calendario mensual.  
  
## Ejemplo  
 En el ejemplo siguiente se definen ocho filas y ocho columnas mediante las clases <xref:System.Windows.Controls.RowDefinition> y <xref:System.Windows.Controls.ColumnDefinition>.  Se utilizan las propiedades adjuntas <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=fullName> y <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=fullName>, junto con elementos <xref:System.Windows.Shapes.Rectangle>, que rellenan el fondo de varias columnas y filas.  Este diseño es posible porque el control <xref:System.Windows.Controls.Grid> permite la existencia de más de un elemento en cada celda, un principio que no es igual en <xref:System.Windows.Controls.Grid> y <xref:System.Windows.Documents.Table>.  
  
 En el ejemplo se utilizan degradados verticales para rellenar con <xref:System.Windows.Shapes.Shape.Fill%2A> las columnas y las filas a fin de mejorar la presentación visual y la legibilidad del calendario.  Las fechas y los días de la semana se representan mediante elementos <xref:System.Windows.Controls.TextBlock> a los que se ha aplicado un estilo.  Los elementos <xref:System.Windows.Controls.TextBlock> se colocan en posiciones absolutas dentro de sus celdas, mediante la propiedad <xref:System.Windows.FrameworkElement.Margin%2A> y mediante propiedades de alineación definidas en el estilo correspondiente a la aplicación.  
  
 [!code-xml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]  
  
## Vea también  
 <xref:System.Windows.Controls.Grid>   
 <xref:System.Windows.Documents.TableCell>   
 [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Información general sobre tablas](../../../../docs/framework/wpf/advanced/table-overview.md)