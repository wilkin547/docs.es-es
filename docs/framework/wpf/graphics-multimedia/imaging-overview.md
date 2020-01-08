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
ms.openlocfilehash: a4151ff610c67ac762f0096c6a136f4475317782
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636645"
---
# <a name="imaging-overview"></a>Información general sobre imágenes
En este tema se proporciona una introducción al componente de creación de imágenes de Microsoft Windows Presentation Foundation. La creación de imágenes de WPF permite a los desarrolladores Mostrar, transformar y dar formato a las imágenes.  

## <a name="wpf-imaging-component"></a>Componente de creación de imágenes de WPF  
 La creación de imágenes de WPF proporciona mejoras significativas en las funciones de creación de imágenes de Microsoft Windows. Las funciones de creación de imágenes, como mostrar un mapa de bits o usar una imagen en un control común, se basaban previamente en las bibliotecas GDI+ de Microsoft Windows Interfaz de dispositivo gráfico (GDI) o Microsoft Windows. Estas API proporcionan funcionalidad de creación de imágenes de línea base, pero carecen de características como la compatibilidad con la extensibilidad de códecs y la compatibilidad con imágenes de alta fidelidad. La creación de imágenes de WPF está diseñada para superar las deficiencias de GDI e GDI+ y proporcionar un nuevo conjunto de API para mostrar y usar imágenes en las aplicaciones.  
  
 Hay dos maneras de tener acceso a la API de creación de imágenes de WPF, un componente administrado y un componente no administrado. El componente no administrado proporciona las siguientes características.  
  
- Modelo de extensibilidad para formatos de imagen nuevos o de propiedad.  
  
- Mejora en el rendimiento y la seguridad de los formatos de imagen nativas, incluido el mapa de bits (BMP), grupo de expertos de fotográficos (JPEG), gráficos de red portátiles (PNG), Tagged Image File Format (TIFF), Microsoft Windows Media Photo, formato de intercambio de gráficos (GIF), y el icono (. ico).  
  
- Conservación de datos de imagen de alta profundidad de bits de hasta 8 bits por canal (32 bits por píxel).  
  
- Escalado, recorte y giros de imágenes no destructivos.  
  
- Administración del color simplificada.  
  
- Compatibilidad con metadatos de propiedad integrados.  
  
- El componente administrado emplea la infraestructura no administrada para proporcionar una integración sin problemas de las imágenes con otras características de WPF como [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], animación y gráficos. El componente administrado también se beneficia del modelo de extensibilidad de códec de imágenes de Windows Presentation Foundation (WPF), que permite el reconocimiento automático de nuevos formatos de imagen en aplicaciones WPF.  
  
 La mayoría de la API de creación de imágenes de WPF administrada reside en el espacio de nombres <xref:System.Windows.Media.Imaging?displayProperty=nameWithType>, aunque varios tipos importantes, como <xref:System.Windows.Media.ImageBrush> y <xref:System.Windows.Media.ImageDrawing> residen en el espacio de nombres <xref:System.Windows.Media?displayProperty=nameWithType> y <xref:System.Windows.Controls.Image> residen en el espacio de nombres <xref:System.Windows.Controls?displayProperty=nameWithType>.  
  
 En este tema se proporciona información adicional sobre el componente administrado. Para obtener más información sobre la API no administrada, vea la documentación de [componentes de imagen de WPF no administrados](/windows/desktop/wic/-wic-lh) .  
  
<a name="_imageformats"></a>   
## <a name="wpf-image-formats"></a>Formatos de imagen de WPF  

 Un códec se usa para descodificar o codificar un formato de medios específico. La creación de imágenes de WPF incluye un códec para formatos BMP, JPEG, PNG, TIFF, Windows Media Photo, GIF y de imagen de iconos. Cada uno de estos códecs permiten a las aplicaciones descodificar y, con la excepción de ICON, codificar sus formatos de imagen respectivos.  
  
 <xref:System.Windows.Media.Imaging.BitmapSource> es una clase importante que se usa en la descodificación y codificación de imágenes. Es el bloque de creación básico de la canalización de imágenes de WPF y representa un único conjunto constante de píxeles con un tamaño y resolución determinados. Un <xref:System.Windows.Media.Imaging.BitmapSource> puede ser un fotograma individual de una imagen de varios marcos o puede ser el resultado de una transformación realizada en un <xref:System.Windows.Media.Imaging.BitmapSource>. Es el elemento primario de muchas de las clases principales que se usan en la creación de imágenes de WPF, como <xref:System.Windows.Media.Imaging.BitmapFrame>.  
  
 Un <xref:System.Windows.Media.Imaging.BitmapFrame> se utiliza para almacenar los datos de mapa de bits reales de un formato de imagen. Muchos formatos de imagen solo admiten un único <xref:System.Windows.Media.Imaging.BitmapFrame>, aunque formatos como GIF y TIFF admiten varios fotogramas por imagen. Los descodificadores usan los marcos como datos de entrada y se pasan a los codificadores para crear archivos de imagen.  
  
 En el ejemplo siguiente se muestra cómo se crea un <xref:System.Windows.Media.Imaging.BitmapFrame> a partir de un <xref:System.Windows.Media.Imaging.BitmapSource> y, a continuación, se agrega a una imagen TIFF.  
  
 [!code-csharp[BitmapFrameExample#10](~/samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### <a name="image-format-decoding"></a>Descodificación de formatos de imagen  
 La descodificación de imágenes es la traslación de un formato de imagen a datos de imagen que el sistema puede usar. Los datos de imagen pueden usarse entonces para mostrar, procesar o codificar en otro formato. La selección del descodificador se basa en el formato de imagen. La selección del códec es automática a menos que se indique un descodificador específico. En los ejemplos de la sección [Mostrar imágenes en WPF](#_displayingimages) se muestra la descodificación automática. Los descodificadores de formato personalizados desarrollados con las interfaces de imagen de WPF no administradas y registrados con el sistema participan automáticamente en la selección del descodificador. Esto permite que los formatos personalizados se muestren automáticamente en las aplicaciones WPF.  
  
 En el ejemplo siguiente se muestra el uso de un descodificador de mapa de bits para descodificar una imagen de formato BMP.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
### <a name="image-format-encoding"></a>Codificación de formatos de imagen  
 La codificación de imágenes es la traslación de datos de imagen a un formato de imagen específico. Los datos de imagen codificados pueden usarse entonces para crear nuevos archivos de imagen. La creación de imágenes de WPF proporciona codificadores para cada uno de los formatos de imagen descritos anteriormente.  
  
 En el siguiente ejemplo se muestra el uso de un codificador para guardar una imagen de mapa de bits recién creada.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#3](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#3)]
 [!code-csharp[BmpBitmapDecoderEncoder#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#3)]
 [!code-vb[BmpBitmapDecoderEncoder#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#3)]  
  
<a name="_displayingimages"></a>   
## <a name="displaying-images-in-wpf"></a>Mostrar imágenes en WPF  
 Hay varias maneras de mostrar una imagen en una aplicación Windows Presentation Foundation (WPF). Las imágenes se pueden mostrar mediante un control de <xref:System.Windows.Controls.Image>, pintados en un visual con un <xref:System.Windows.Media.ImageBrush>o dibujadas con un <xref:System.Windows.Media.ImageDrawing>.  
  
### <a name="using-the-image-control"></a>Usar el control de imagen  
 <xref:System.Windows.Controls.Image> es un elemento de marco y la forma principal de mostrar imágenes en las aplicaciones. En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], <xref:System.Windows.Controls.Image> se pueden usar de dos maneras: Sintaxis de atributo o sintaxis de propiedad. En el siguiente ejemplo se muestra cómo representar una imagen de 200 píxeles de ancho mediante la sintaxis de atributo y la sintaxis de etiquetas de propiedad. Para más información sobre la sintaxis de atributo y la sintaxis de propiedad, consulte [Información general sobre las propiedades de dependencia](../advanced/dependency-properties-overview.md).  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 Muchos de los ejemplos usan un objeto <xref:System.Windows.Media.Imaging.BitmapImage> para hacer referencia a un archivo de imagen. <xref:System.Windows.Media.Imaging.BitmapImage> es un <xref:System.Windows.Media.Imaging.BitmapSource> especializado que está optimizado para la carga de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y es una manera fácil de mostrar imágenes como <xref:System.Windows.Controls.Image.Source%2A> de un control de <xref:System.Windows.Controls.Image>.  
  
 En el siguiente ejemplo se muestra cómo representar una imagen de 200 píxeles de ancho mediante código.  
  
> [!NOTE]
> <xref:System.Windows.Media.Imaging.BitmapImage> implementa la interfaz <xref:System.ComponentModel.ISupportInitialize> para optimizar la inicialización en varias propiedades. Los cambios en la propiedad solo se pueden producir durante la inicialización del objeto. Llame a <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> para indicar que la inicialización ha comenzado y <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> para indicar que la inicialización se ha completado. Una vez inicializado, se omiten los cambios en la propiedad.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### <a name="rotating-converting-and-cropping-images"></a>Girar, convertir y recortar imágenes  
 WPF permite a los usuarios transformar imágenes mediante las propiedades de <xref:System.Windows.Media.Imaging.BitmapImage> o mediante el uso de objetos de <xref:System.Windows.Media.Imaging.BitmapSource> adicionales como <xref:System.Windows.Media.Imaging.CroppedBitmap> o <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>. Dichas transformaciones de imágenes pueden escalar o girar una imagen, cambiar el formato de píxel de una imagen o recortar una imagen.  
  
 Las rotaciones de imagen se realizan utilizando la propiedad <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A> de <xref:System.Windows.Media.Imaging.BitmapImage>. Estos solo pueden llevarse a cabo en incrementos de 90 grados. En el siguiente ejemplo, una imagen se gira 90 grados.  
  
 [!code-xaml[ImageElementExample#TransformedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 La conversión de una imagen a un formato de píxel diferente, como la escala de grises, se realiza mediante <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>. En los ejemplos siguientes, una imagen se convierte en <xref:System.Windows.Media.PixelFormats.Gray4%2A>.  
  
 [!code-xaml[ImageElementExample_snip#ConvertedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 Para recortar una imagen, se puede usar la propiedad <xref:System.Windows.UIElement.Clip%2A> de <xref:System.Windows.Controls.Image> o <xref:System.Windows.Media.Imaging.CroppedBitmap>. Normalmente, si solo desea mostrar una parte de una imagen, se debe usar <xref:System.Windows.UIElement.Clip%2A>. Si necesita codificar y guardar una imagen recortada, se debe usar el <xref:System.Windows.Media.Imaging.CroppedBitmap>. En el ejemplo siguiente, se recorta una imagen utilizando la propiedad clip mediante una <xref:System.Windows.Media.EllipseGeometry>.  
  
 [!code-xaml[ImageElementExample_snip#CroppedXAMLUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### <a name="stretching-images"></a>Ajustar imágenes  
 La propiedad <xref:System.Windows.Controls.Image.Stretch%2A> controla cómo se ajusta una imagen para rellenar su contenedor. La propiedad <xref:System.Windows.Controls.Image.Stretch%2A> acepta los siguientes valores, definidos por la enumeración <xref:System.Windows.Media.Stretch>:  
  
- <xref:System.Windows.Media.Stretch.None>: la imagen no se ajusta para rellenar el área de salida. Si la imagen es más grande que el área de salida, esta se dibujará en dicha área, recortando lo que no se ajuste.  
  
- <xref:System.Windows.Media.Stretch.Fill>: la imagen se escala para ajustarse al área de salida. Como el alto y el ancho de las imágenes se escalan de forma independiente, podría no conservarse la relación de aspecto original de la imagen. En otras palabras, la imagen podría distorsionarse para rellenar por completo el contenedor de salida.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: la imagen se escala para que quepa completamente dentro del área de salida. Se conserva la relación de aspecto de la imagen.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: la imagen se escala para que rellene completamente el área de salida, al mismo tiempo que se conserva la relación de aspecto original de la imagen.  
  
 En el ejemplo siguiente se aplica cada una de las enumeraciones de <xref:System.Windows.Media.Stretch> disponibles a una <xref:System.Windows.Controls.Image>.  
  
 En la imagen siguiente se muestra el resultado del ejemplo y se muestra el efecto que tienen las distintas configuraciones de <xref:System.Windows.Controls.Image.Stretch%2A> cuando se aplican a una imagen.  
  
 ![Diferentes valores de Stretch para TileBrush](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
Diferentes valores de Stretch  
  
 [!code-xaml[ImageElementExample_snip#ImageStretchExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### <a name="painting-with-images"></a>Pintar con imágenes  
 Las imágenes también se pueden mostrar en una aplicación pintando con un <xref:System.Windows.Media.Brush>. Los pinceles permiten pintar objetos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con cualquier cosa, desde colores simples y sólidos hasta conjuntos complejos de patrones e imágenes. Para pintar con imágenes, use una <xref:System.Windows.Media.ImageBrush>. Un <xref:System.Windows.Media.ImageBrush> es un tipo de <xref:System.Windows.Media.TileBrush> que define su contenido como una imagen de mapa de bits. Un <xref:System.Windows.Media.ImageBrush> muestra una sola imagen, que se especifica mediante su propiedad <xref:System.Windows.Media.ImageBrush.ImageSource%2A>. Puede controlar cómo se ajusta, alinea y coloca en mosaico la imagen, evitándose de este modo la distorsión y produciéndose patrones y otros efectos. En la ilustración siguiente se muestran algunos efectos que se pueden lograr con un <xref:System.Windows.Media.ImageBrush>.  
  
 ![Ejemplos de resultados de ImageBrush](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Los pinceles de imagen pueden rellenar formas, controles, texto, etc.  
  
 En el ejemplo siguiente se muestra cómo pintar el fondo de un botón con una imagen mediante un <xref:System.Windows.Media.ImageBrush>.  
  
 [!code-xaml[UsingImageBrush#4](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 Para obtener más información sobre cómo <xref:System.Windows.Media.ImageBrush> y pintar imágenes [, vea pintar con imágenes, dibujos y objetos visuales](painting-with-images-drawings-and-visuals.md).  
  
<a name="_metadata"></a>   
## <a name="image-metadata"></a>Metadatos de imagen  
 Algunos archivos de imagen contienen metadatos que describen el contenido o las características del archivo. Por ejemplo, la mayoría de las cámaras digitales crean imágenes que contienen metadatos sobre la marca y modelo de la cámara empleada para capturar la imagen. Cada formato de imagen controla los metadatos de manera diferente, pero la creación de imágenes de WPF proporciona una manera uniforme de almacenar y recuperar los metadatos de cada formato de imagen compatible.  
  
 El acceso a los metadatos se proporciona a través de la propiedad <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> de un objeto <xref:System.Windows.Media.Imaging.BitmapSource>. <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> devuelve un objeto <xref:System.Windows.Media.Imaging.BitmapMetadata> que incluye todos los metadatos que contiene la imagen. Estos datos pueden estar en un esquema de metadatos o una combinación de diferentes esquemas. La creación de imágenes de WPF admite los siguientes esquemas de metadatos de imagen: el archivo de imagen intercambiable (EXIF), el texto (datos de texto PNG), el directorio de archivos de imagen (IFD), el Consejo Internacional de telecomunicaciones (IPTC) y la plataforma de metadatos extensible (XMP).  
  
 Con el fin de simplificar el proceso de lectura de metadatos, <xref:System.Windows.Media.Imaging.BitmapMetadata> proporciona varias propiedades con nombre a las que se puede tener acceso fácilmente, como <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>, <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A>y <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>. Muchas de estas propiedades con nombre también se pueden usar para escribir metadatos. El lector de consultas de metadatos proporciona soporte técnico adicional para leer metadatos. El método <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> se utiliza para recuperar un lector de consultas de metadatos proporcionando una consulta de cadena como *"/APP1/Exif/"* . En el ejemplo siguiente, se usa <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> para obtener el texto almacenado en la ubicación *"/Text/Description"* .  
  
 [!code-cpp[BitmapMetadata#GetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 Para escribir metadatos, se usa un escritor de consultas de metadatos. <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> obtiene el escritor de consultas y establece el valor deseado. En el ejemplo siguiente, se usa <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> para escribir el texto almacenado en la ubicación *"/Text/Description"* .  
  
 [!code-cpp[BitmapMetadata#SetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>   
## <a name="codec-extensibility"></a>Extensibilidad de códec  
 Una característica fundamental de la creación de imágenes de WPF es el modelo de extensibilidad para los nuevos códecs de imagen. Estas interfaces no administradas permiten a los desarrolladores de códec integrar códecs con WPF para que las aplicaciones de WPF puedan usar automáticamente nuevos formatos de imagen.  
  
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
