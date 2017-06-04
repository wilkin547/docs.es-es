---
title: "C&#243;mo: Definir una tabla con XAML | Microsoft Docs"
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
  - "documentos, definir tablas con XAML"
  - "tablas, definir con XAML"
  - "XAML, definir tablas"
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# C&#243;mo: Definir una tabla con XAML
En el ejemplo siguiente se muestra cómo definir un objeto <xref:System.Windows.Documents.Table> mediante [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  La tabla del ejemplo tiene cuatro columnas \(representas por elementos <xref:System.Windows.Documents.TableColumn>\) y varias filas \(representadas por elementos <xref:System.Windows.Documents.TableRow>\) que contienen datos y, además, la información de título, encabezado y pie de página.  Las filas deben estar contenidas en un elemento <xref:System.Windows.Documents.TableRowGroup>.  Cada fila de la tabla consta de una o más celdas \(representadas por elementos <xref:System.Windows.Documents.TableCell>\).  El contenido de la celda de una tabla debe estar incluido en un elemento <xref:System.Windows.Documents.Block>; en este caso se utilizan elementos <xref:System.Windows.Documents.Paragraph>.  La tabla también hospeda un hipervínculo \(representado por el elemento <xref:System.Windows.Documents.Hyperlink>\) en la fila del pie de página.  
  
## Ejemplo  
 [!code-xml[TableSnippetsXAML#_TableXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 En la ilustración siguiente se muestra cómo se representa la tabla definida en este ejemplo.  
  
 ![Tabla representada.](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")