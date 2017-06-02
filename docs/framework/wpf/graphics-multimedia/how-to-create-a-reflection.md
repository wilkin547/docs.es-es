---
title: "C&#243;mo: Crear una reflexi&#243;n | Microsoft Docs"
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
  - "pinceles, crear reflexiones"
  - "crear reflexiones"
  - "reflexiones, crear"
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Crear una reflexi&#243;n
En este ejemplo se muestra cómo usar un objeto <xref:System.Windows.Media.VisualBrush> para crear una reflexión.  Dado que <xref:System.Windows.Media.VisualBrush> puede mostrar un objeto visual existente, puede usar esta funcionalidad para generar efectos visuales interesantes, como reflexiones y ampliación.  
  
## Ejemplo  
 En el ejemplo siguiente se usa <xref:System.Windows.Media.VisualBrush> para crear una reflexión de un <xref:System.Windows.Controls.Border> que contiene varios elementos.  En la ilustración siguiente se muestra el resultado de aplicar este ejemplo.  
  
 ![Objeto Visual reflejado](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.png "graphicsmm\_visualbrush\_reflection\_small")  
Objeto visual reflejado  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Para obtener el ejemplo completo, que incluye ejemplos que muestran cómo aumentar partes de la pantalla y crear reflexiones, vea [VisualBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160049).  
  
## Vea también  
 <xref:System.Windows.Media.VisualBrush>   
 [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)