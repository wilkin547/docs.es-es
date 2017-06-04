---
title: "C&#243;mo: Usar el elemento de imagen | Microsoft Docs"
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
  - "BitmapImage (clase)"
  - "clases, BitmapImage"
  - "controles, Imagen"
  - "Image (control)"
  - "representar imágenes"
ms.assetid: 5b92e74b-1b56-4756-ac64-d5e9e08d9854
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# C&#243;mo: Usar el elemento de imagen
En este ejemplo se muestra cómo incluir imágenes en una aplicación utilizando el elemento <xref:System.Windows.Controls.Image>.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo representar una imagen de 200 píxeles de ancho.  En este ejemplo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], se utilizan la sintaxis de atributo y la sintaxis de etiquetas de propiedad para definir la imagen.  Para obtener más información sobre la sintaxis de atributo y la sintaxis de propiedad, consulte [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  <xref:System.Windows.Media.Imaging.BitmapImage> se utiliza para definir los datos de origen de la imagen y se define explícitamente para el ejemplo de sintaxis de etiquetas de propiedad.  Además, la propiedad <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> de <xref:System.Windows.Media.Imaging.BitmapImage> se establece en el mismo ancho que la propiedad <xref:System.Windows.FrameworkElement.Width%2A> de <xref:System.Windows.Controls.Image>.  Esto se hace para asegurarse de utilizar la mínima cantidad de memoria para representar la imagen.  
  
> [!NOTE]
>  En general, si desea especificar el tamaño de una imagen representada, especifique sólo <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A> pero no ambas.  Si sólo especifica una, se conserva la [relación de aspecto](GTMT) de la imagen.  De lo contrario, la imagen puede sufrir un ajuste o distorsión inesperados.  Para controlar el comportamiento de ajuste de la imagen, utilice las propiedades <xref:System.Windows.Controls.Image.Stretch%2A> y <xref:System.Windows.Controls.Image.StretchDirection%2A>.  
  
> [!NOTE]
>  Cuando especifique el tamaño de una imagen con <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A>, también debe establecer <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> o <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> en el mismo tamaño correspondiente.  
  
 La propiedad <xref:System.Windows.Controls.Image.Stretch%2A> determina cómo se ajusta el origen de la imagen para rellenar el elemento de imagen.  Para obtener más información, vea la enumeración <xref:System.Windows.Media.Stretch>.  
  
 [!code-xml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo representar una imagen de 200 píxeles de ancho mediante código.  
  
> [!NOTE]
>  El establecimiento de las propiedades <xref:System.Windows.Media.Imaging.BitmapImage> se debe hacer dentro de un bloque de <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> y <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A>.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## Vea también  
 [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)