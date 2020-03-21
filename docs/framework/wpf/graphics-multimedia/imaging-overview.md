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
ms.openlocfilehash: 3365c35e3e7b7fe5c0be48a65d7a14da0882c90e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186698"
---
# <a name="imaging-overview"></a>Información general sobre imágenes
En este tema se proporciona una introducción al componente de imágenes de Microsoft Windows Presentation Foundation. WPF Imaging permite a los desarrolladores mostrar, transformar y dar formato a imágenes.  

## <a name="wpf-imaging-component"></a>Componente de creación de imágenes de WPF  
 WPF Imaging proporciona mejoras significativas en las capacidades de creación de imágenes dentro de Microsoft Windows. Las capacidades de creación de imágenes, como mostrar un mapa de bits o usar una imagen en un control común, dependían anteriormente de las bibliotecas de Microsoft Windows Graphics Device Interface (GDI) o Microsoft Windows GDI+. Estas API proporcionan funcionalidad de creación de imágenes de línea base, pero carecen de características como la compatibilidad con la extensibilidad de códecs y la compatibilidad con imágenes de alta fidelidad. WPF Imaging está diseñado para superar las deficiencias de GDI y GDI+GDI+ y proporcionar un nuevo conjunto de API para mostrar y usar imágenes dentro de sus aplicaciones.  
  
 Hay dos maneras de tener acceso a la API de imágenes de WPFWPF, un componente administrado y un componente no administrado. El componente no administrado proporciona las siguientes características.  
  
- Modelo de extensibilidad para formatos de imagen nuevos o de propiedad.  
  
- Rendimiento y seguridad mejorados en formatos de imagen nativos, como mapa de bits (BMP), Joint Photographics Experts Group (JPEG), Portable Network Graphics (PNG), Tagged Image File Format (TIFF), Microsoft Windows Media Photo, Graphics Interchange Format (GIF), e icono (.ico).  
  
- Conservación de datos de imagen de alta profundidad de bits de hasta 8 bits por canal (32 bits por píxel).  
  
- Escalado, recorte y giros de imágenes no destructivos.  
  
- Administración del color simplificada.  
  
- Compatibilidad con metadatos de propiedad integrados.  
  
- El componente administrado utiliza la infraestructura no administrada para proporcionar una [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]integración perfecta de imágenes con otras características de WPFWPF, como, animación y gráficos. El componente administrado también se beneficia del modelo de extensibilidad del códec de imágenes de Windows Presentation Foundation (WPF), que permite el reconocimiento automático de nuevos formatos de imagen en aplicaciones WPF.  
  
 La mayoría de la API de <xref:System.Windows.Media.Imaging?displayProperty=nameWithType> imágenes de WPF <xref:System.Windows.Media.ImageBrush> administrada <xref:System.Windows.Media.ImageDrawing> reside <xref:System.Windows.Media?displayProperty=nameWithType> en <xref:System.Windows.Controls.Image> el espacio de nombres, aunque varios tipos importantes, como y residen en el espacio de nombres y residen en el <xref:System.Windows.Controls?displayProperty=nameWithType> espacio de nombres.  
  
 En este tema se proporciona información adicional sobre el componente administrado. Para obtener más información sobre la API no administrada, consulte la documentación componente de [imágenes de WPF no administrado.](/windows/desktop/wic/-wic-lh)  
  
<a name="_imageformats"></a>
## <a name="wpf-image-formats"></a>Formatos de imagen de WPF  

 Un códec se usa para descodificar o codificar un formato de medios específico. WPF Imaging incluye un códec para los formatos de imagen BMP, JPEG, PNG, TIFF, Windows Media Photo, GIF e ICON. Cada uno de estos códecs permiten a las aplicaciones descodificar y, con la excepción de ICON, codificar sus formatos de imagen respectivos.  
  
 <xref:System.Windows.Media.Imaging.BitmapSource>es una clase importante utilizada en la decodificación y codificación de imágenes. Es el bloque de creación básico de la canalización de imágenes de WPFWPF y representa un único conjunto constante de píxeles con un tamaño y una resolución determinados. A <xref:System.Windows.Media.Imaging.BitmapSource> puede ser un fotograma individual de una imagen de varios fotogramas, o puede ser el resultado de una transformación realizada en un <xref:System.Windows.Media.Imaging.BitmapSource>archivo . Es el elemento primario de muchas de las <xref:System.Windows.Media.Imaging.BitmapFrame>clases principales utilizadas en wpfWPF wpfWPF como .  
  
 A <xref:System.Windows.Media.Imaging.BitmapFrame> se utiliza para almacenar los datos de mapa de bits reales de un formato de imagen. Muchos formatos de <xref:System.Windows.Media.Imaging.BitmapFrame>imagen solo admiten un solo, aunque formatos como GIF y TIFF admiten varios fotogramas por imagen. Los descodificadores usan los marcos como datos de entrada y se pasan a los codificadores para crear archivos de imagen.  
  
 En el ejemplo siguiente <xref:System.Windows.Media.Imaging.BitmapFrame> se muestra <xref:System.Windows.Media.Imaging.BitmapSource> cómo se crea a partir de a y, a continuación, se agrega a una imagen TIFF.  
  
 [!code-csharp[BitmapFrameExample#10](~/samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### <a name="image-format-decoding"></a>Descodificación de formatos de imagen  
 La descodificación de imágenes es la traslación de un formato de imagen a datos de imagen que el sistema puede usar. Los datos de imagen pueden usarse entonces para mostrar, procesar o codificar en otro formato. La selección del descodificador se basa en el formato de imagen. La selección del códec es automática a menos que se indique un descodificador específico. En los ejemplos de la sección [Mostrar imágenes en WPF](#_displayingimages) se muestra la descodificación automática. Los decodificadores de formato personalizado desarrollados mediante las interfaces de imágenes de WPF no administradas y registrados en el sistema participan automáticamente en la selección del decodificador. Esto permite que los formatos personalizados se muestren automáticamente en las aplicaciones WPFWPF.  
  
 En el ejemplo siguiente se muestra el uso de un descodificador de mapa de bits para descodificar una imagen de formato BMP.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
### <a name="image-format-encoding"></a>Codificación de formatos de imagen  
 La codificación de imágenes es la traslación de datos de imagen a un formato de imagen específico. Los datos de imagen codificados pueden usarse entonces para crear nuevos archivos de imagen. WPF Imaging proporciona codificadores para cada uno de los formatos de imagen descritos anteriormente.  
  
 En el siguiente ejemplo se muestra el uso de un codificador para guardar una imagen de mapa de bits recién creada.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#3](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#3)]
 [!code-csharp[BmpBitmapDecoderEncoder#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#3)]
 [!code-vb[BmpBitmapDecoderEncoder#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#3)]  
  
<a name="_displayingimages"></a>
## <a name="displaying-images-in-wpf"></a>Mostrar imágenes en WPF  
 Hay varias maneras de mostrar una imagen en una aplicación de Windows Presentation Foundation (WPF). Las imágenes se <xref:System.Windows.Controls.Image> pueden mostrar mediante un <xref:System.Windows.Media.ImageBrush>control, pintarse en un objeto visual mediante un archivo , o dibujarse con un <xref:System.Windows.Media.ImageDrawing>archivo .  
  
### <a name="using-the-image-control"></a>Usar el control de imagen  
 <xref:System.Windows.Controls.Image>es un elemento de marco de trabajo y la forma principal de mostrar imágenes en las aplicaciones. En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <xref:System.Windows.Controls.Image> , se puede utilizar de dos maneras; sintaxis de atributo o sintaxis de propiedad. En el siguiente ejemplo se muestra cómo representar una imagen de 200 píxeles de ancho mediante la sintaxis de atributo y la sintaxis de etiquetas de propiedad. Para más información sobre la sintaxis de atributo y la sintaxis de propiedad, consulte [Información general sobre las propiedades de dependencia](../advanced/dependency-properties-overview.md).  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 Muchos de los ejemplos utilizan un <xref:System.Windows.Media.Imaging.BitmapImage> objeto para hacer referencia a un archivo de imagen. <xref:System.Windows.Media.Imaging.BitmapImage>es un <xref:System.Windows.Media.Imaging.BitmapSource> especialista que [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] está optimizado para la carga y <xref:System.Windows.Controls.Image.Source%2A> es <xref:System.Windows.Controls.Image> una manera fácil de mostrar imágenes como el de un control.  
  
 En el siguiente ejemplo se muestra cómo representar una imagen de 200 píxeles de ancho mediante código.  
  
> [!NOTE]
> <xref:System.Windows.Media.Imaging.BitmapImage>implementa la <xref:System.ComponentModel.ISupportInitialize> interfaz para optimizar la inicialización en varias propiedades. Los cambios en la propiedad solo se pueden producir durante la inicialización del objeto. Llame <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> para indicar que <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> la inicialización ha comenzado y para señalar que la inicialización se ha completado. Una vez inicializado, se omiten los cambios en la propiedad.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### <a name="rotating-converting-and-cropping-images"></a>Girar, convertir y recortar imágenes  
 WPFWPF permite a los usuarios transformar <xref:System.Windows.Media.Imaging.BitmapSource> imágenes <xref:System.Windows.Media.Imaging.CroppedBitmap> <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>mediante el uso de propiedades de <xref:System.Windows.Media.Imaging.BitmapImage> o mediante objetos adicionales como o . Dichas transformaciones de imágenes pueden escalar o girar una imagen, cambiar el formato de píxel de una imagen o recortar una imagen.  
  
 Las rotaciones de <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A> imagen <xref:System.Windows.Media.Imaging.BitmapImage>se realizan utilizando la propiedad de . Estos solo pueden llevarse a cabo en incrementos de 90 grados. En el siguiente ejemplo, una imagen se gira 90 grados.  
  
 [!code-xaml[ImageElementExample#TransformedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 La conversión de una imagen a un formato <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>de píxel diferente, como la escala de grises, se realiza mediante . En los ejemplos siguientes, una <xref:System.Windows.Media.PixelFormats.Gray4%2A>imagen se convierte en .  
  
 [!code-xaml[ImageElementExample_snip#ConvertedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 Para recortar una imagen, <xref:System.Windows.Controls.Image> se <xref:System.Windows.Media.Imaging.CroppedBitmap> puede utilizar la <xref:System.Windows.UIElement.Clip%2A> propiedad de o se puede utilizar. Normalmente, si solo desea mostrar una parte <xref:System.Windows.UIElement.Clip%2A> de una imagen, debe utilizarse. Si necesita codificar y guardar una imagen <xref:System.Windows.Media.Imaging.CroppedBitmap> recortada, se debe utilizar. En el ejemplo siguiente, una imagen se recorta mediante la propiedad Clip mediante un <xref:System.Windows.Media.EllipseGeometry>archivo .  
  
 [!code-xaml[ImageElementExample_snip#CroppedXAMLUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### <a name="stretching-images"></a>Ajustar imágenes  
 La <xref:System.Windows.Controls.Image.Stretch%2A> propiedad controla cómo se estira una imagen para rellenar su contenedor. La <xref:System.Windows.Controls.Image.Stretch%2A> propiedad acepta los siguientes valores, definidos por la <xref:System.Windows.Media.Stretch> enumeración:  
  
- <xref:System.Windows.Media.Stretch.None>: La imagen no se estira para rellenar el área de salida. Si la imagen es más grande que el área de salida, esta se dibujará en dicha área, recortando lo que no se ajuste.  
  
- <xref:System.Windows.Media.Stretch.Fill>: La imagen se escala para ajustarse al área de salida. Como el alto y el ancho de las imágenes se escalan de forma independiente, podría no conservarse la relación de aspecto original de la imagen. En otras palabras, la imagen podría distorsionarse para rellenar por completo el contenedor de salida.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: La imagen se escala para que quepa completamente dentro del área de salida. Se conserva la relación de aspecto de la imagen.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: La imagen se escala para que llene completamente el área de salida conservando la relación de aspecto original de la imagen.  
  
 En el ejemplo siguiente <xref:System.Windows.Media.Stretch> se aplica <xref:System.Windows.Controls.Image>cada una de las enumeraciones disponibles a un archivo .  
  
 La siguiente imagen muestra la salida del ejemplo <xref:System.Windows.Controls.Image.Stretch%2A> y muestra el efecto que tienen los diferentes ajustes cuando se aplican a una imagen.  
  
 ![Diferentes valores de Stretch para TileBrush](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
Diferentes valores de Stretch  
  
 [!code-xaml[ImageElementExample_snip#ImageStretchExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### <a name="painting-with-images"></a>Pintar con imágenes  
 Las imágenes también se pueden mostrar <xref:System.Windows.Media.Brush>en una aplicación pintando con un archivo . Los pinceles permiten pintar objetos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con cualquier cosa, desde colores simples y sólidos hasta conjuntos complejos de patrones e imágenes. Para pintar con imágenes, utilice un <xref:System.Windows.Media.ImageBrush>archivo . Un <xref:System.Windows.Media.ImageBrush> es un <xref:System.Windows.Media.TileBrush> tipo de que define su contenido como una imagen de mapa de bits. Un <xref:System.Windows.Media.ImageBrush> muestra una sola imagen, que <xref:System.Windows.Media.ImageBrush.ImageSource%2A> se especifica por su propiedad. Puede controlar cómo se ajusta, alinea y coloca en mosaico la imagen, evitándose de este modo la distorsión y produciéndose patrones y otros efectos. La siguiente ilustración muestra algunos efectos <xref:System.Windows.Media.ImageBrush>que se pueden lograr con un archivo .  
  
 ![Ejemplos de resultados de ImageBrush](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Los pinceles de imagen pueden rellenar formas, controles, texto, etc.  
  
 En el ejemplo siguiente se muestra cómo pintar el <xref:System.Windows.Media.ImageBrush>fondo de un botón con una imagen mediante un archivo .  
  
 [!code-xaml[UsingImageBrush#4](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 Para obtener <xref:System.Windows.Media.ImageBrush> información adicional sobre y pintar imágenes, consulte [Pintura con imágenes, dibujos y objetos visuales](painting-with-images-drawings-and-visuals.md).  
  
<a name="_metadata"></a>
## <a name="image-metadata"></a>Metadatos de imagen  
 Algunos archivos de imagen contienen metadatos que describen el contenido o las características del archivo. Por ejemplo, la mayoría de las cámaras digitales crean imágenes que contienen metadatos sobre la marca y modelo de la cámara empleada para capturar la imagen. Cada formato de imagen controla los metadatos de forma diferente, pero WPF Imaging proporciona una forma uniforme de almacenar y recuperar metadatos para cada formato de imagen admitido.  
  
 El acceso a los <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> metadatos <xref:System.Windows.Media.Imaging.BitmapSource> se proporciona a través de la propiedad de un objeto. <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A>devuelve <xref:System.Windows.Media.Imaging.BitmapMetadata> un objeto que incluye todos los metadatos contenidos en la imagen. Estos datos pueden estar en un esquema de metadatos o una combinación de diferentes esquemas. WPF Imaging admite los siguientes esquemas de metadatos de imagen: archivo de imagen intercambiable (Exif), tEXt (PNG Textual Data), directorio de archivos de imagen (IFD), International Press Telecommunications Council (IPTC) y Extensible Metadata Platform (XMP).  
  
 Para simplificar el proceso de <xref:System.Windows.Media.Imaging.BitmapMetadata> lectura de metadatos, proporciona varias <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>propiedades <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A>con <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>nombre a las que se puede acceder fácilmente, como , , y . Muchas de estas propiedades con nombre también se pueden usar para escribir metadatos. El lector de consultas de metadatos proporciona soporte técnico adicional para leer metadatos. El <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> método se utiliza para recuperar un lector de consultas de metadatos proporcionando una consulta de cadena como *"/app1/exif/"*. En el ejemplo <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> siguiente, se utiliza para obtener el texto almacenado en la ubicación *"/Text/Description".*  
  
 [!code-cpp[BitmapMetadata#GetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 Para escribir metadatos, se usa un escritor de consultas de metadatos. <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A>obtiene el escritor de consultas y establece el valor deseado. En el ejemplo <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> siguiente, se utiliza para escribir el texto almacenado en la ubicación *"/Text/Description".*  
  
 [!code-cpp[BitmapMetadata#SetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>
## <a name="codec-extensibility"></a>Extensibilidad de códec  
 Una característica principal de WPFWPF Imaging es el modelo de extensibilidad para los nuevos códecs de imagen. Estas interfaces no administradas permiten a los desarrolladores de códecs integrar códecs con WPFWPF para que las aplicaciones WPF puedan usar automáticamente nuevos formatos de imagen.  
  
 Para obtener un ejemplo de la API de extensibilidad, consulte el códec de ejemplo [de Win32](https://go.microsoft.com/fwlink/?LinkID=160052). En este ejemplo se muestra cómo crear un descodificador y un codificador para un formato de imagen personalizado.  
  
> [!NOTE]
> El códec se debe firmar digitalmente para que el sistema lo reconozca.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Imaging.BitmapSource>
- <xref:System.Windows.Media.Imaging.BitmapImage>
- <xref:System.Windows.Controls.Image>
- <xref:System.Windows.Media.Imaging.BitmapMetadata>
- [Imágenes y gráficos 2D](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Código de ejemplo Win32](https://go.microsoft.com/fwlink/?LinkID=160052)
