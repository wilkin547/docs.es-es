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
ms.openlocfilehash: 13d5ea2735a799332edd8e552198de0f2b970dad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914100"
---
# <a name="imaging-overview"></a>Información general sobre imágenes
En este tema se proporciona una introducción a [!INCLUDE[TLA#tla_wic](../../../../includes/tlasharptla-wic-md.md)]. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] permite a los desarrolladores mostrar, transformar y dar formato a imágenes.  

## <a name="wpf-imaging-component"></a>Componente de creación de imágenes de WPF  
 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] proporciona mejoras significativas en funciones de creación de imágenes de [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)]. Las funciones de creación de imágenes, como mostrar un mapa de bits o usar una imagen en un control común, se basaban previamente en las bibliotecas GDI+ de Microsoft Windows Interfaz de dispositivo gráfico (GDI) o Microsoft Windows. Estas API proporcionan funcionalidad de creación de imágenes de línea base, pero carecen de características como la compatibilidad con la extensibilidad de códecs y la compatibilidad con imágenes de alta fidelidad. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]está diseñado para superar las deficiencias de GDI y GDI+ y proporcionar un nuevo conjunto de API para mostrar y usar imágenes en las aplicaciones.  
  
 Hay dos maneras de tener acceso a [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] la API, un componente administrado y un componente no administrado. El componente no administrado proporciona las siguientes características.  
  
- Modelo de extensibilidad para formatos de imagen nuevos o de propiedad.  
  
- Mejora en el rendimiento y la seguridad de los formatos de imágenes nativas, incluido el mapa de bits (BMP), el grupo de expertos de fotográficos [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)]Unidos (JPEG), los gráficos de red portátiles (PNG), [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)],, el formato de intercambio de gráficos (GIF) y el icono (. ico).  
  
- Conservación de datos de imagen de alta profundidad de bits de hasta 8 bits por canal (32 bits por píxel).  
  
- Escalado, recorte y giros de imágenes no destructivos.  
  
- Administración del color simplificada.  
  
- Compatibilidad con metadatos de propiedad integrados.  
  
- El componente administrado usa la infraestructura no administrada para proporcionar una integración de imágenes perfecta con otras características de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], tales como [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], animación y gráficos. El componente administrado también se beneficia del modelo de extensibilidad de códec de imágenes de Windows Presentation Foundation (WPF), que permite el reconocimiento [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] automático de nuevos formatos de imagen en las aplicaciones.  
  
 La mayoría de la API [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] administrada reside en el <xref:System.Windows.Media.Imaging?displayProperty=nameWithType> espacio de nombres, aunque varios tipos <xref:System.Windows.Media.ImageBrush> importantes, como <xref:System.Windows.Media.ImageDrawing> y residen en <xref:System.Windows.Media?displayProperty=nameWithType> el espacio <xref:System.Windows.Controls.Image> de nombres y residen <xref:System.Windows.Controls?displayProperty=nameWithType> en el System.IO.  
  
 En este tema se proporciona información adicional sobre el componente administrado. Para obtener más información sobre la API no administrada, vea la documentación de [componentes de imagen de WPF no administrados](/windows/desktop/wic/-wic-lh) .  
  
<a name="_imageformats"></a>   
## <a name="wpf-image-formats"></a>Formatos de imagen de WPF  
 Un códec se usa para descodificar o codificar un formato de medios específico. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]incluye un códec para los formatos de imagen BMP, [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)]JPEG [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)], PNG,,, GIF y Icon. Cada uno de estos códecs permiten a las aplicaciones descodificar y, con la excepción de ICON, codificar sus formatos de imagen respectivos.  
  
 <xref:System.Windows.Media.Imaging.BitmapSource>es una clase importante que se usa en la descodificación y codificación de imágenes. Es el bloque de creación básico de la canalización de [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] y representa un solo conjunto constante de píxeles con un tamaño y resolución determinados. Puede ser un marco individual de una imagen de varios marcos o puede ser el resultado de una transformación realizada <xref:System.Windows.Media.Imaging.BitmapSource>en. <xref:System.Windows.Media.Imaging.BitmapSource> Es el elemento primario de muchas de las clases principales que [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <xref:System.Windows.Media.Imaging.BitmapFrame>se usan en la creación de imágenes como.  
  
 <xref:System.Windows.Media.Imaging.BitmapFrame> Se utiliza para almacenar los datos de mapa de bits reales de un formato de imagen. Muchos formatos de imagen solo admiten <xref:System.Windows.Media.Imaging.BitmapFrame>un único, aunque formatos como GIF [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] y admiten varios fotogramas por imagen. Los descodificadores usan los marcos como datos de entrada y se pasan a los codificadores para crear archivos de imagen.  
  
 En el ejemplo siguiente se muestra <xref:System.Windows.Media.Imaging.BitmapFrame> cómo se crea un <xref:System.Windows.Media.Imaging.BitmapSource> a partir de y, [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] a continuación, se agrega a una imagen.  
  
 [!code-csharp[BitmapFrameExample#10](~/samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### <a name="image-format-decoding"></a>Descodificación de formatos de imagen  
 La descodificación de imágenes es la traslación de un formato de imagen a datos de imagen que el sistema puede usar. Los datos de imagen pueden usarse entonces para mostrar, procesar o codificar en otro formato. La selección del descodificador se basa en el formato de imagen. La selección del códec es automática a menos que se indique un descodificador específico. En los ejemplos de la sección [Mostrar imágenes en WPF](#_displayingimages) se muestra la descodificación automática. Los descodificadores de formato personalizado desarrollados con las interfaces de [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] no administradas y registrados con el sistema, participan automáticamente en la selección del descodificador. Esto permite que los formatos personalizados se muestren automáticamente en aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 En el ejemplo siguiente se muestra el uso de un descodificador de mapa de bits para descodificar una imagen de formato BMP.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
### <a name="image-format-encoding"></a>Codificación de formatos de imagen  
 La codificación de imágenes es la traslación de datos de imagen a un formato de imagen específico. Los datos de imagen codificados pueden usarse entonces para crear nuevos archivos de imagen. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] proporciona codificadores para cada uno de los formatos de imagen descritos anteriormente.  
  
 En el siguiente ejemplo se muestra el uso de un codificador para guardar una imagen de mapa de bits recién creada.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#3](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#3)]
 [!code-csharp[BmpBitmapDecoderEncoder#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#3)]
 [!code-vb[BmpBitmapDecoderEncoder#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#3)]  
  
<a name="_displayingimages"></a>   
## <a name="displaying-images-in-wpf"></a>Mostrar imágenes en WPF  
 Hay varias maneras de mostrar una imagen en una aplicación Windows Presentation Foundation (WPF). Las imágenes se pueden mostrar mediante <xref:System.Windows.Controls.Image> un control, pintados en un visual <xref:System.Windows.Media.ImageBrush>con o dibujadas mediante <xref:System.Windows.Media.ImageDrawing>.  
  
### <a name="using-the-image-control"></a>Usar el control de imagen  
 <xref:System.Windows.Controls.Image>es un elemento de marco y la forma principal de mostrar imágenes en las aplicaciones. En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ,<xref:System.Windows.Controls.Image> se puede usar de dos maneras: sintaxis de atributo o sintaxis de propiedad. En el siguiente ejemplo se muestra cómo representar una imagen de 200 píxeles de ancho mediante la sintaxis de atributo y la sintaxis de etiquetas de propiedad. Para más información sobre la sintaxis de atributo y la sintaxis de propiedad, consulte [Información general sobre las propiedades de dependencia](../advanced/dependency-properties-overview.md).  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 Muchos de los ejemplos usan un <xref:System.Windows.Media.Imaging.BitmapImage> objeto para hacer referencia a un archivo de imagen. <xref:System.Windows.Media.Imaging.BitmapImage>es un especializado <xref:System.Windows.Media.Imaging.BitmapSource> que está optimizado [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para la carga y es una forma sencilla de mostrar imágenes <xref:System.Windows.Controls.Image.Source%2A> como el <xref:System.Windows.Controls.Image> de un control.  
  
 En el siguiente ejemplo se muestra cómo representar una imagen de 200 píxeles de ancho mediante código.  
  
> [!NOTE]
> <xref:System.Windows.Media.Imaging.BitmapImage>implementa la interfaz <xref:System.ComponentModel.ISupportInitialize> para optimizar la inicialización en varias propiedades. Los cambios en la propiedad solo se pueden producir durante la inicialización del objeto. Llame <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> a para indicar que la inicialización <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> ha comenzado y para indicar que la inicialización se ha completado. Una vez inicializado, se omiten los cambios en la propiedad.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### <a name="rotating-converting-and-cropping-images"></a>Girar, convertir y recortar imágenes  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]permite a los usuarios transformar imágenes mediante las propiedades <xref:System.Windows.Media.Imaging.BitmapImage> de o mediante el <xref:System.Windows.Media.Imaging.BitmapSource> uso de objetos <xref:System.Windows.Media.Imaging.CroppedBitmap> adicionales <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>, como o. Dichas transformaciones de imágenes pueden escalar o girar una imagen, cambiar el formato de píxel de una imagen o recortar una imagen.  
  
 Las rotaciones de imagen se realizan <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A> mediante la <xref:System.Windows.Media.Imaging.BitmapImage>propiedad de. Estos solo pueden llevarse a cabo en incrementos de 90 grados. En el siguiente ejemplo, una imagen se gira 90 grados.  
  
 [!code-xaml[ImageElementExample#TransformedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 La conversión de una imagen a un formato de píxel diferente, como la <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>escala de grises, se realiza mediante. En los ejemplos siguientes, una imagen se convierte en <xref:System.Windows.Media.PixelFormats.Gray4%2A>.  
  
 [!code-xaml[ImageElementExample_snip#ConvertedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 Para recortar una imagen, <xref:System.Windows.UIElement.Clip%2A> se puede <xref:System.Windows.Controls.Image> usar <xref:System.Windows.Media.Imaging.CroppedBitmap> la propiedad de o. Normalmente, si solo desea mostrar una parte de una imagen, <xref:System.Windows.UIElement.Clip%2A> se debe usar. Si necesita codificar y guardar una imagen recortada, <xref:System.Windows.Media.Imaging.CroppedBitmap> se debe usar. En el ejemplo siguiente, se recorta una imagen utilizando la propiedad clip mediante <xref:System.Windows.Media.EllipseGeometry>.  
  
 [!code-xaml[ImageElementExample_snip#CroppedXAMLUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### <a name="stretching-images"></a>Ajustar imágenes  
 La <xref:System.Windows.Controls.Image.Stretch%2A> propiedad controla cómo se ajusta una imagen para rellenar su contenedor. La <xref:System.Windows.Controls.Image.Stretch%2A> propiedad acepta los siguientes valores, definidos por la <xref:System.Windows.Media.Stretch> enumeración:  
  
- <xref:System.Windows.Media.Stretch.None>: La imagen no se ajusta para rellenar el área de salida. Si la imagen es más grande que el área de salida, esta se dibujará en dicha área, recortando lo que no se ajuste.  
  
- <xref:System.Windows.Media.Stretch.Fill>: La imagen se escala para ajustarse al área de salida. Como el alto y el ancho de las imágenes se escalan de forma independiente, podría no conservarse la relación de aspecto original de la imagen. En otras palabras, la imagen podría distorsionarse para rellenar por completo el contenedor de salida.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: La imagen se escala para que quepa completamente dentro del área de salida. Se conserva la relación de aspecto de la imagen.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: La imagen se escala para que rellene completamente el área de salida, al mismo tiempo que se conserva la relación de aspecto original de la imagen.  
  
 En el ejemplo siguiente se aplica cada una <xref:System.Windows.Media.Stretch> de las enumeraciones <xref:System.Windows.Controls.Image>disponibles a un.  
  
 En la imagen siguiente se muestra el resultado del ejemplo y se muestra el efecto <xref:System.Windows.Controls.Image.Stretch%2A> que tienen las distintas configuraciones cuando se aplican a una imagen.  
  
 ![Diferentes valores de Stretch para TileBrush](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
Diferentes valores de Stretch  
  
 [!code-xaml[ImageElementExample_snip#ImageStretchExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### <a name="painting-with-images"></a>Pintar con imágenes  
 Las imágenes también se pueden mostrar en una aplicación pintando con <xref:System.Windows.Media.Brush>un. Los pinceles permiten pintar objetos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con cualquier cosa, desde colores simples y sólidos hasta conjuntos complejos de patrones e imágenes. Para pintar con imágenes, use <xref:System.Windows.Media.ImageBrush>. Es un tipo de que <xref:System.Windows.Media.TileBrush> define su contenido como una imagen de mapa de bits. <xref:System.Windows.Media.ImageBrush> Un <xref:System.Windows.Media.ImageBrush> muestra una sola imagen, que se especifica mediante su <xref:System.Windows.Media.ImageBrush.ImageSource%2A> propiedad. Puede controlar cómo se ajusta, alinea y coloca en mosaico la imagen, evitándose de este modo la distorsión y produciéndose patrones y otros efectos. En la ilustración siguiente se muestran algunos efectos que se pueden lograr <xref:System.Windows.Media.ImageBrush>con un.  
  
 ![Ejemplos de salida de ImageBrush](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Los pinceles de imagen pueden rellenar formas, controles, texto, etc.  
  
 En el ejemplo siguiente se muestra cómo pintar el fondo de un botón con una imagen mediante <xref:System.Windows.Media.ImageBrush>.  
  
 [!code-xaml[UsingImageBrush#4](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 Para obtener información adicional <xref:System.Windows.Media.ImageBrush> acerca de las imágenes y su dibujo, vea [pintar con imágenes, dibujos y objetos visuales](painting-with-images-drawings-and-visuals.md).  
  
<a name="_metadata"></a>   
## <a name="image-metadata"></a>Metadatos de imagen  
 Algunos archivos de imagen contienen metadatos que describen el contenido o las características del archivo. Por ejemplo, la mayoría de las cámaras digitales crean imágenes que contienen metadatos sobre la marca y modelo de la cámara empleada para capturar la imagen. Cada formato de imagen controla los metadatos de forma diferente, pero [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] proporciona una manera uniforme de almacenar y recuperar metadatos para cada formato de imagen compatible.  
  
 El acceso a los metadatos se <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> proporciona a través <xref:System.Windows.Media.Imaging.BitmapSource> de la propiedad de un objeto. <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A>Devuelve un <xref:System.Windows.Media.Imaging.BitmapMetadata> objeto que incluye todos los metadatos que contiene la imagen. Estos datos pueden estar en un esquema de metadatos o una combinación de diferentes esquemas. [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]admite los siguientes esquemas de metadatos de imagen: Archivo de imagen intercambiable (EXIF), texto (datos de texto PNG), directorio de archivos de imagen (IFD), International Press Telecommunications Council [!INCLUDE[TLA#tla_xmp](../../../../includes/tlasharptla-xmp-md.md)](IPTC) y.  
  
 Con el fin de simplificar el proceso de lectura <xref:System.Windows.Media.Imaging.BitmapMetadata> de metadatos, proporciona varias propiedades con nombre a las que <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>se puede tener <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>acceso fácilmente, como, <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A>y. Muchas de estas propiedades con nombre también se pueden usar para escribir metadatos. El lector de consultas de metadatos proporciona soporte técnico adicional para leer metadatos. El <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> método se usa para recuperar un lector de consultas de metadatos proporcionando una consulta de cadena como *"/APP1/Exif/"* . En el ejemplo siguiente, <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> se usa para obtener el texto almacenado en la ubicación *"/Text/Description"* .  
  
 [!code-cpp[BitmapMetadata#GetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 Para escribir metadatos, se usa un escritor de consultas de metadatos. <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A>Obtiene el escritor de consultas y establece el valor deseado. En el ejemplo siguiente, <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> se usa para escribir el texto almacenado en la ubicación *"/Text/Description"* .  
  
 [!code-cpp[BitmapMetadata#SetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>   
## <a name="codec-extensibility"></a>Extensibilidad de códec  
 Una característica básica de [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] es el modelo de extensibilidad para los nuevos códecs de imagen. Estas interfaces no administradas permiten a los desarrolladores de códec integrar códecs con [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], por lo que las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] pueden usar automáticamente nuevos formatos de imagen.  
  
 Para obtener un ejemplo de la API de extensibilidad, vea el [ejemplo de códec de Win32](https://go.microsoft.com/fwlink/?LinkID=160052). En este ejemplo se muestra cómo crear un descodificador y un codificador para un formato de imagen personalizado.  
  
> [!NOTE]
> El códec se debe firmar digitalmente para que el sistema lo reconozca.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Imaging.BitmapSource>
- <xref:System.Windows.Media.Imaging.BitmapImage>
- <xref:System.Windows.Controls.Image>
- <xref:System.Windows.Media.Imaging.BitmapMetadata>
- [Imágenes y gráficos 2D](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Código de ejemplo Win32](https://go.microsoft.com/fwlink/?LinkID=160052)
