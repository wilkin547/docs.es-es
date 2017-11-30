---
title: "Cómo: Usar el elemento de imagen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Image
- Image control [WPF]
- rendering images [WPF]
ms.assetid: 5b92e74b-1b56-4756-ac64-d5e9e08d9854
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 75177c8aae8964ebdc50ae94b2f3a6372991e2c6
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-the-image-element"></a>Cómo: Usar el elemento de imagen
Este ejemplo muestra cómo incluir imágenes en una aplicación mediante el uso de la <xref:System.Windows.Controls.Image> elemento.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra cómo representar una imagen de 200 píxeles de ancho. En este ejemplo de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], tanto la sintaxis de atributo como la sintaxis de etiquetas de propiedad se usan para definir la imagen. Para más información sobre la sintaxis de atributo y la sintaxis de propiedad, consulte [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md). Un <xref:System.Windows.Media.Imaging.BitmapImage> se utiliza para definir los datos de origen de la imagen y se define explícitamente para el ejemplo de sintaxis de la etiqueta de propiedad. Además, el <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> de la <xref:System.Windows.Media.Imaging.BitmapImage> se establece en el mismo ancho que la <xref:System.Windows.FrameworkElement.Width%2A> de la <xref:System.Windows.Controls.Image>. Esto se hace para garantizar que la cantidad mínima de memoria se use para representar la imagen.  
  
> [!NOTE]
>  En general, si desea especificar el tamaño de una imagen representada, especifique sólo el <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A> , pero no ambos. Si solo especifica uno, se conserva la relación de aspecto de la imagen. De lo contrario, la imagen puede aparecer ajustada o distorsionada de forma inesperada. Para controlar la imagen del ajuste de comportamiento, use la <xref:System.Windows.Controls.Image.Stretch%2A> y <xref:System.Windows.Controls.Image.StretchDirection%2A> propiedades.  
  
> [!NOTE]
>  Cuando se especifica el tamaño de una imagen con una <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A>, también se debe establecer <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> o <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> para el mismo tamaño correspondiente.  
  
 El <xref:System.Windows.Controls.Image.Stretch%2A> propiedad determina cómo se ajusta el origen de imagen para rellenar el elemento de imagen. Para obtener más información, vea la enumeración <xref:System.Windows.Media.Stretch>.  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra cómo representar una imagen de 200 píxeles de ancho mediante código.  
  
> [!NOTE]
>  Establecer <xref:System.Windows.Media.Imaging.BitmapImage> propiedades deben realizarse dentro de un <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> y <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> bloque.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
