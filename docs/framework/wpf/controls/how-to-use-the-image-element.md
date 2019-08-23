---
title: Procedimiento Usar el elemento de imagen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Image
- Image control [WPF]
- rendering images [WPF]
ms.assetid: 5b92e74b-1b56-4756-ac64-d5e9e08d9854
ms.openlocfilehash: 164eee7c10d9e388c6e6ee695af479ca2d6974b3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958324"
---
# <a name="how-to-use-the-image-element"></a>Procedimiento Usar el elemento de imagen
En este ejemplo se muestra cómo incluir imágenes en una aplicación mediante el <xref:System.Windows.Controls.Image> elemento.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra cómo representar una imagen de 200 píxeles de ancho. En este ejemplo de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], tanto la sintaxis de atributo como la sintaxis de etiquetas de propiedad se usan para definir la imagen. Para más información sobre la sintaxis de atributo y la sintaxis de propiedad, consulte [Información general sobre las propiedades de dependencia](../advanced/dependency-properties-overview.md). <xref:System.Windows.Media.Imaging.BitmapImage> Se utiliza para definir los datos de origen de la imagen y se define explícitamente para el ejemplo de sintaxis de etiquetas de propiedad. Además <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> , el <xref:System.Windows.Media.Imaging.BitmapImage> de se establece en el mismo <xref:System.Windows.Controls.Image>ancho que el <xref:System.Windows.FrameworkElement.Width%2A> de. Esto se hace para garantizar que la cantidad mínima de memoria se use para representar la imagen.  
  
> [!NOTE]
> En general, si desea especificar el tamaño de una imagen representada, especifique solo <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> o, pero no ambos. Si solo especifica uno, se conserva la relación de aspecto de la imagen. De lo contrario, la imagen puede aparecer ajustada o distorsionada de forma inesperada. Para controlar el comportamiento de ajuste de la imagen, use <xref:System.Windows.Controls.Image.Stretch%2A> las <xref:System.Windows.Controls.Image.StretchDirection%2A> propiedades y.  
  
> [!NOTE]
> Al especificar el tamaño de una imagen <xref:System.Windows.FrameworkElement.Width%2A> con o <xref:System.Windows.FrameworkElement.Height%2A>, también debe establecer <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> o <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> en el mismo tamaño respectivo.  
  
 La <xref:System.Windows.Controls.Image.Stretch%2A> propiedad determina cómo se ajusta el origen de la imagen para rellenar el elemento de imagen. Para obtener más información, vea la enumeración <xref:System.Windows.Media.Stretch>.  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra cómo representar una imagen de 200 píxeles de ancho mediante código.  
  
> [!NOTE]
> La <xref:System.Windows.Media.Imaging.BitmapImage> configuración de las propiedades debe realizarse <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> dentro de un <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> bloque and.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre imágenes](../graphics-multimedia/imaging-overview.md)
