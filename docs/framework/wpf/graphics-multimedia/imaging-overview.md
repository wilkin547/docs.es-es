---
title: Información general sobre imágenes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- metadata [WPF], images
- displaying images [WPF]
- Imaging API [WPF]
- image metadata [WPF]
- converting images [WPF]
- encoding image formats [WPF]
- format decoding for images [WPF]
- painting with images [WPF]
- stretching images [WPF]
- images [WPF], about imaging
- format encoding for images [WPF]
- cropping images [WPF]
- decoding image formats [WPF]
- rotating images [WPF]
ms.assetid: 72aad87a-e6f3-4937-94cd-a18b7766e990
ms.openlocfilehash: 45214b5f0e6827c36f87a4d45592ff0989c9a877
ms.sourcegitcommit: 5c2176883dc3107445702724a7caa7ac2f6cb0d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2019
ms.locfileid: "58890815"
---
# <a name="imaging-overview"></a>Información general sobre imágenes
En este tema se proporciona una introducción a [!INCLUDE[TLA#tla_wic](../../../../includes/tlasharptla-wic-md.md)]. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] permite a los desarrolladores mostrar, transformar y dar formato a imágenes.  
  
  
<a name="_wpfImaging"></a>   
## <a name="wpf-imaging-component"></a>Componente de creación de imágenes de WPF  
 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] ofrece mejoras significativas en capacidades dentro de imágenes [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)]. Anteriormente, las funciones de creación de imágenes, tales como mostrar un mapa de bits o usar una imagen en un control común, dependían de las bibliotecas de [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)] o [!INCLUDE[TLA#tla_gdiplus](../../../../includes/tlasharptla-gdiplus-md.md)]. Estas [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] proporcionan funciones de creación de imágenes, pero carecen de algunas características, como la compatibilidad con la extensibilidad de códec y con imágenes de alta fidelidad. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] está diseñado para superar las limitaciones de [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] y [!INCLUDE[TLA2#tla_gdiplus](../../../../includes/tla2sharptla-gdiplus-md.md)] y proporcionar un nuevo conjunto de [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] para mostrar y usar imágenes en sus aplicaciones.  
  
 Existen dos formas de obtener acceso a [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)], un componente administrado y un componente no administrado. El componente no administrado proporciona las siguientes características.  
  
-   Modelo de extensibilidad para formatos de imagen nuevos o de propiedad.  
  
-   Rendimiento y seguridad mejorados en formatos de imagen nativos, entre los que se incluyen [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)], [!INCLUDE[TLA#tla_jpegorg](../../../../includes/tlasharptla-jpegorg-md.md)], [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)], [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)], [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)], [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] y formato de icono (.ico).  
  
-   Conservación de datos de imagen de alta profundidad de bits de hasta 8 bits por canal (32 bits por píxel).  
  
-   Escalado, recorte y giros de imágenes no destructivos.  
  
-   Administración del color simplificada.  
  
-   Compatibilidad con metadatos de propiedad integrados.  
  
-   El componente administrado usa la infraestructura no administrada para proporcionar una integración de imágenes perfecta con otras características de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], tales como [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], animación y gráficos. El componente administrado también se beneficia de la Windows Presentation Foundation (WPF) creación de imágenes códec modelo de extensibilidad que habilita el reconocimiento automático de nuevos formatos de imagen en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicaciones.  
  
 La mayoría de los recursos administrados [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] residen en el <xref:System.Windows.Media.Imaging?displayProperty=nameWithType> espacio de nombres, aunque importante varios tipos, como <xref:System.Windows.Media.ImageBrush> y <xref:System.Windows.Media.ImageDrawing> residen en el <xref:System.Windows.Media?displayProperty=nameWithType> espacio de nombres y <xref:System.Windows.Controls.Image> reside en el <xref:System.Windows.Controls?displayProperty=nameWithType> espacio de nombres.  
  
 En este tema se proporciona información adicional sobre el componente administrado. Para más información sobre la [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] no administrada, consulte la documentación relativa al [componente de creación de imágenes de WPF no administrado](/windows/desktop/wic/-wic-lh).  
  
<a name="_imageformats"></a>   
## <a name="wpf-image-formats"></a>Formatos de imagen de WPF  
 Un códec se usa para descodificar o codificar un formato de medios específico. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] incluye un códec para [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)], [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)], [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)], [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)], [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)], [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)]y formatos de imagen de icono. Cada uno de estos códecs permiten a las aplicaciones descodificar y, con la excepción de ICON, codificar sus formatos de imagen respectivos.  
  
 <xref:System.Windows.Media.Imaging.BitmapSource> ¿se usa una clase importante en la descodificación y codificación de imágenes. Es el bloque de creación básico de la canalización de [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] y representa un solo conjunto constante de píxeles con un tamaño y resolución determinados. Un <xref:System.Windows.Media.Imaging.BitmapSource> puede ser un fotograma individual de una imagen de varios marcos, o puede ser el resultado de una transformación realizada en un <xref:System.Windows.Media.Imaging.BitmapSource>. Es el elemento primario de muchas de las clases primarias utilizadas en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] imaging como <xref:System.Windows.Media.Imaging.BitmapFrame>.  
  
 Un <xref:System.Windows.Media.Imaging.BitmapFrame> se usa para almacenar los datos de mapa de bits real de un formato de imagen. Muchos formatos de imagen solo admiten un <xref:System.Windows.Media.Imaging.BitmapFrame>, aunque formatos tales como [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] y [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] admiten varios marcos por imagen. Los descodificadores usan los marcos como datos de entrada y se pasan a los codificadores para crear archivos de imagen.  
  
 En el ejemplo siguiente se muestra cómo un <xref:System.Windows.Media.Imaging.BitmapFrame> creada a partir de un <xref:System.Windows.Media.Imaging.BitmapSource> y, a continuación, se agrega a un [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] imagen.  
  
 [!code-csharp[BitmapFrameExample#10](~/samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### <a name="image-format-decoding"></a>Descodificación de formatos de imagen  
 La descodificación de imágenes es la traslación de un formato de imagen a datos de imagen que el sistema puede usar. Los datos de imagen pueden usarse entonces para mostrar, procesar o codificar en otro formato. La selección del descodificador se basa en el formato de imagen. La selección del códec es automática a menos que se indique un descodificador específico. En los ejemplos de la sección [Mostrar imágenes en WPF](#_displayingimages) se muestra la descodificación automática. Los descodificadores de formato personalizado desarrollados con las interfaces de [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] no administradas y registrados con el sistema, participan automáticamente en la selección del descodificador. Esto permite que los formatos personalizados se muestren automáticamente en aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 En el siguiente ejemplo se muestra el uso de un descodificador de mapa de bits para descodificar una imagen en formato [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)].  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
### <a name="image-format-encoding"></a>Codificación de formatos de imagen  
 La codificación de imágenes es la traslación de datos de imagen a un formato de imagen específico. Los datos de imagen codificados pueden usarse entonces para crear nuevos archivos de imagen. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] proporciona codificadores para cada uno de los formatos de imagen que se ha descrito anteriormente.  
  
 En el siguiente ejemplo se muestra el uso de un codificador para guardar una imagen de mapa de bits recién creada.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#3](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#3)]
 [!code-csharp[BmpBitmapDecoderEncoder#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#3)]
 [!code-vb[BmpBitmapDecoderEncoder#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#3)]  
  
<a name="_displayingimages"></a>   
## <a name="displaying-images-in-wpf"></a>Mostrar imágenes en WPF  
 Hay varias maneras de mostrar una imagen en una aplicación de Windows Presentation Foundation (WPF). Las imágenes se pueden mostrar mediante un <xref:System.Windows.Controls.Image> control, pintado en un objeto visual mediante un <xref:System.Windows.Media.ImageBrush>, o dibujar mediante un <xref:System.Windows.Media.ImageDrawing>.  
  
### <a name="using-the-image-control"></a>Usar el control de imagen  
 <xref:System.Windows.Controls.Image> es un elemento de marco y la forma principal para mostrar imágenes en las aplicaciones. En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], <xref:System.Windows.Controls.Image> se puede usar de dos maneras; la sintaxis de atributo o propiedad. En el siguiente ejemplo se muestra cómo representar una imagen de 200 píxeles de ancho mediante la sintaxis de atributo y la sintaxis de etiquetas de propiedad. Para más información sobre la sintaxis de atributo y la sintaxis de propiedad, consulte [Información general sobre las propiedades de dependencia](../advanced/dependency-properties-overview.md).  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 Muchos de los ejemplos utilizan un <xref:System.Windows.Media.Imaging.BitmapImage> objeto para hacer referencia a un archivo de imagen. <xref:System.Windows.Media.Imaging.BitmapImage> está especializado <xref:System.Windows.Media.Imaging.BitmapSource> que está optimizado para [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] cargando y es una manera fácil de mostrar imágenes como la <xref:System.Windows.Controls.Image.Source%2A> de un <xref:System.Windows.Controls.Image> control.  
  
 En el siguiente ejemplo se muestra cómo representar una imagen de 200 píxeles de ancho mediante código.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Imaging.BitmapImage> implementa el <xref:System.ComponentModel.ISupportInitialize> interfaz para optimizar la inicialización en varias propiedades. Los cambios en la propiedad solo se pueden producir durante la inicialización del objeto. Llame a <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> para indicar que la inicialización ha comenzado y <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> para indicar que la inicialización se ha completado. Una vez inicializado, se omiten los cambios en la propiedad.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### <a name="rotating-converting-and-cropping-images"></a>Girar, convertir y recortar imágenes  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] permite a los usuarios transformar imágenes mediante las propiedades de <xref:System.Windows.Media.Imaging.BitmapImage> o mediante el uso adicional <xref:System.Windows.Media.Imaging.BitmapSource> objetos como <xref:System.Windows.Media.Imaging.CroppedBitmap> o <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>. Dichas transformaciones de imágenes pueden escalar o girar una imagen, cambiar el formato de píxel de una imagen o recortar una imagen.  
  
 Los giros de imágenes se realizan mediante el <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A> propiedad de <xref:System.Windows.Media.Imaging.BitmapImage>. Estos solo pueden llevarse a cabo en incrementos de 90 grados. En el siguiente ejemplo, una imagen se gira 90 grados.  
  
 [!code-xaml[ImageElementExample#TransformedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 Convertir una imagen a un formato de píxel diferente, como la escala de grises se realiza mediante <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>. En los ejemplos siguientes, se convierte una imagen en <xref:System.Windows.Media.PixelFormats.Gray4%2A>.  
  
 [!code-xaml[ImageElementExample_snip#ConvertedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 Para recortar una imagen, ya sea el <xref:System.Windows.UIElement.Clip%2A> propiedad de <xref:System.Windows.Controls.Image> o <xref:System.Windows.Media.Imaging.CroppedBitmap> se puede usar. Normalmente, si solo desea mostrar una parte de una imagen, <xref:System.Windows.UIElement.Clip%2A> debe usarse. Si tiene que codificar y guardar una imagen recortada, el <xref:System.Windows.Media.Imaging.CroppedBitmap> se debe usar. En el ejemplo siguiente, se recorta una imagen mediante la propiedad Clip usando un <xref:System.Windows.Media.EllipseGeometry>.  
  
 [!code-xaml[ImageElementExample_snip#CroppedXAMLUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### <a name="stretching-images"></a>Ajustar imágenes  
 El <xref:System.Windows.Controls.Image.Stretch%2A> propiedad controla cómo se ajusta una imagen para rellenar su contenedor. El <xref:System.Windows.Controls.Image.Stretch%2A> propiedad acepta los valores siguientes, definidos por el <xref:System.Windows.Media.Stretch> enumeración:  
  
-   <xref:System.Windows.Media.Stretch.None>: La imagen no se ajusta para rellenar el área de salida. Si la imagen es más grande que el área de salida, esta se dibujará en dicha área, recortando lo que no se ajuste.  
  
-   <xref:System.Windows.Media.Stretch.Fill>: La imagen se escala para ajustarse al área de salida. Como el alto y el ancho de las imágenes se escalan de forma independiente, podría no conservarse la relación de aspecto original de la imagen. En otras palabras, la imagen podría distorsionarse para rellenar por completo el contenedor de salida.  
  
-   <xref:System.Windows.Media.Stretch.Uniform>: La imagen se escala para que quepa completamente dentro del área de salida. Se conserva la relación de aspecto de la imagen.  
  
-   <xref:System.Windows.Media.Stretch.UniformToFill>: La imagen se escala para que rellene completamente el área de salida conservando la relación de aspecto original de la imagen.  
  
 El ejemplo siguiente aplica a cada uno de los disponibles <xref:System.Windows.Media.Stretch> enumeraciones que permiten una <xref:System.Windows.Controls.Image>.  
  
 La siguiente imagen muestra la salida del ejemplo y muestra el efecto de los diferentes <xref:System.Windows.Controls.Image.Stretch%2A> configuración cuando se aplica a una imagen.  
  
 ![Diferentes valores de Stretch para TileBrush](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
Diferentes valores de Stretch  
  
 [!code-xaml[ImageElementExample_snip#ImageStretchExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### <a name="painting-with-images"></a>Pintar con imágenes  
 Las imágenes también se pueden mostrar en una aplicación pintando con un <xref:System.Windows.Media.Brush>. Los pinceles permiten pintar objetos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con cualquier cosa, desde colores simples y sólidos hasta conjuntos complejos de patrones e imágenes. Para pintar con imágenes, use un <xref:System.Windows.Media.ImageBrush>. Un <xref:System.Windows.Media.ImageBrush> es un tipo de <xref:System.Windows.Media.TileBrush> que define su contenido como una imagen de mapa de bits. Un <xref:System.Windows.Media.ImageBrush> muestra una sola imagen, que se especifica mediante su <xref:System.Windows.Media.ImageBrush.ImageSource%2A> propiedad. Puede controlar cómo se ajusta, alinea y coloca en mosaico la imagen, evitándose de este modo la distorsión y produciéndose patrones y otros efectos. La siguiente ilustración muestra algunos efectos que se pueden lograr con un <xref:System.Windows.Media.ImageBrush>.  
  
 ![Ejemplos del resultado de ImageBrush](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Los pinceles de imagen pueden rellenar formas, controles, texto, etc.  
  
 En el ejemplo siguiente se muestra cómo pintar el fondo de un botón con una imagen mediante un <xref:System.Windows.Media.ImageBrush>.  
  
 [!code-xaml[UsingImageBrush#4](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 Para obtener más información acerca de <xref:System.Windows.Media.ImageBrush> y vea cómo pintar imágenes [pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md).  
  
<a name="_metadata"></a>   
## <a name="image-metadata"></a>Metadatos de imagen  
 Algunos archivos de imagen contienen metadatos que describen el contenido o las características del archivo. Por ejemplo, la mayoría de las cámaras digitales crean imágenes que contienen metadatos sobre la marca y modelo de la cámara empleada para capturar la imagen. Cada formato de imagen controla los metadatos de forma diferente, pero [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] proporciona una manera uniforme de almacenar y recuperar metadatos para cada formato de imagen compatible.  
  
 Se proporciona acceso a los metadatos a través de la <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> propiedad de un <xref:System.Windows.Media.Imaging.BitmapSource> objeto. <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> Devuelve un <xref:System.Windows.Media.Imaging.BitmapMetadata> objeto que incluye todos los metadatos incluidos en la imagen. Estos datos pueden estar en un esquema de metadatos o una combinación de diferentes esquemas. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] admite los siguientes esquemas de metadatos de imagen: [!INCLUDE[TLA#tla_exif](../../../../includes/tlasharptla-exif-md.md)], texto (datos textuales PNG), [!INCLUDE[TLA#tla_ifd](../../../../includes/tlasharptla-ifd-md.md)], [!INCLUDE[TLA#tla_iptc](../../../../includes/tlasharptla-iptc-md.md)], y [!INCLUDE[TLA#tla_xmp](../../../../includes/tlasharptla-xmp-md.md)].  
  
 Para simplificar el proceso de lectura de metadatos, <xref:System.Windows.Media.Imaging.BitmapMetadata> proporciona varias propiedades con nombre que se pueden acceder fácilmente como <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>, <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A>, y <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>. Muchas de estas propiedades con nombre también se pueden usar para escribir metadatos. El lector de consultas de metadatos proporciona soporte técnico adicional para leer metadatos. El <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> método se usa para recuperar un lector de consultas de metadatos proporcionando una consulta de cadena como *"/ app1/exif /"*. En el ejemplo siguiente, <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> se utiliza para obtener el texto almacenado en el *"/ Text/Description"* ubicación.  
  
 [!code-cpp[BitmapMetadata#GetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 Para escribir metadatos, se usa un escritor de consultas de metadatos. <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> Obtiene el escritor de consultas y establece el valor deseado. En el ejemplo siguiente, <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> se utiliza para escribir el texto almacenado en el *"/ Text/Description"* ubicación.  
  
 [!code-cpp[BitmapMetadata#SetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>   
## <a name="codec-extensibility"></a>Extensibilidad de códec  
 Una característica básica de [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] es el modelo de extensibilidad para los nuevos códecs de imagen. Estas interfaces no administradas permiten a los desarrolladores de códec integrar códecs con [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], por lo que las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] pueden usar automáticamente nuevos formatos de imagen.  
  
 Para obtener un ejemplo de la [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] de extensibilidad, consulte [Código de ejemplo Win32](https://go.microsoft.com/fwlink/?LinkID=160052). En este ejemplo se muestra cómo crear un descodificador y un codificador para un formato de imagen personalizado.  
  
> [!NOTE]
>  El códec se debe firmar digitalmente para que el sistema lo reconozca.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Media.Imaging.BitmapSource>
- <xref:System.Windows.Media.Imaging.BitmapImage>
- <xref:System.Windows.Controls.Image>
- <xref:System.Windows.Media.Imaging.BitmapMetadata>
- [Imágenes y gráficos 2D](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Código de ejemplo Win32](https://go.microsoft.com/fwlink/?LinkID=160052)
