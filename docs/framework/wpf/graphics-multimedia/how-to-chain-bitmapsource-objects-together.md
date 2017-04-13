---
title: "C&#243;mo: Encadenar objetos BitmapSource | Microsoft Docs"
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
  - "BitmapSource (objetos), encadenar"
  - "encadenar objetos BitmapSource"
  - "gráficos, encadenar objetos BitmapSource"
ms.assetid: 32d88853-395b-4855-9685-51a482a3b421
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Encadenar objetos BitmapSource
En este ejemplo se muestra cómo aplicar diversos efectos a un origen de imagen encadenando varios objetos <xref:System.Windows.Media.Imaging.BitmapSource> derivados entre sí.  
  
 En el ejemplo siguiente se utiliza el encadenamiento para voltear y cambiar el formato de píxel del origen de una imagen.  
  
## Ejemplo  
 [!code-xml[ImagingSnippetGallery_snip#ChainedBitmapSourcesXamlExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_snip/CS/ChainedBitmapSourcesExample.xaml#chainedbitmapsourcesxamlexamplewholepage)]  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#ChainedBitmapSourcesCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/ChainedBitmapSourcesExample.cs#chainedbitmapsourcescodeexamplewholepage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#ChainedBitmapSourcesCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/ChainedBitmapSourcesExample.vb#chainedbitmapsourcescodeexamplewholepage)]