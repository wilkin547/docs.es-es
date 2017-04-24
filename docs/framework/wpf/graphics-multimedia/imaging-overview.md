---
title: "Informaci&#243;n general sobre im&#225;genes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "convertir imágenes"
  - "recortar imágenes"
  - "descodificar formatos de imagen"
  - "mostrar imágenes"
  - "codificar formatos de imagen"
  - "descodificación de formatos para imágenes"
  - "codificación de formatos para imágenes"
  - "metadatos de imagen"
  - "imágenes, acerca de la creación de imágenes"
  - "API de creación de imágenes"
  - "metadatos, imágenes"
  - "pintar con imágenes"
  - "girar imágenes"
  - "expandir imágenes"
ms.assetid: 72aad87a-e6f3-4937-94cd-a18b7766e990
caps.latest.revision: 32
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# Informaci&#243;n general sobre im&#225;genes
En este tema se proporciona una introducción a [!INCLUDE[TLA#tla_wic](../../../../includes/tlasharptla-wic-md.md)].  [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] permite a los desarrolladores mostrar y transformar imágenes, así como darles formato.  
  
   
  
<a name="_wpfImaging"></a>   
## Componente de creación de imágenes de WPF  
 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] proporciona mejoras significativas a las funciones de creación de imágenes de [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)].  Anteriormente, las funciones de creación de imágenes, tales como mostrar un mapa de bits o utilizar una imagen en un control común, dependían de las bibliotecas de [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)] o [!INCLUDE[TLA#tla_gdiplus](../../../../includes/tlasharptla-gdiplus-md.md)].  Estas [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] proporcionan la funcionalidad de línea base para la creación de imágenes, pero carecen de características tales como compatibilidad con la extensibilidad de códec y con imágenes de alta fidelidad.  La [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] de creación de imágenes se ha rediseñado para superar las limitaciones de [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] y [!INCLUDE[TLA2#tla_gdiplus](../../../../includes/tla2sharptla-gdiplus-md.md)], y proporcionar un nuevo conjunto de [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] para mostrar y utilizar imágenes en las aplicaciones.  
  
 Existen dos maneras de tener acceso a la [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] de [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)]: un componente administrado y un componente no administrado.  El componente no administrado proporciona las características siguientes.  
  
-   Modelo de extensibilidad para los formatos de imágenes nuevos o de propietario.  
  
-   Rendimiento mejorado y seguridad en los formatos de imagen nativos, incluidos [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)], [!INCLUDE[TLA#tla_jpegorg](../../../../includes/tlasharptla-jpegorg-md.md)], [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)], [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)], [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)], [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] y los iconos \(.ico\).  
  
-   Conservación de datos de imágenes de gran profundidad de hasta 8 bits por canal \(32 bits por píxel\).  
  
-   Ajuste de escala, recorte y giro no destructivos de la imagen.  
  
-   Administración del color simplificada.  
  
-   Compatibilidad con metadatos de propietario integrados en archivos.  
  
-   El componente administrado utiliza la infraestructura no administrada para proporcionar la integración sin problemas de las imágenes con otras características de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], tales como [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], animación y gráficos.  El componente administrado se beneficia asimismo del modelo de extensibilidad de códec de creación de imágenes de [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] que permite el reconocimiento automático de nuevos formatos de imágenes en aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 La mayoría de las [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] administradas de [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] residen en el espacio de nombres <xref:System.Windows.Media.Imaging?displayProperty=fullName>, aunque hay varios tipos importantes, como <xref:System.Windows.Media.ImageBrush> y <xref:System.Windows.Media.ImageDrawing>, que residen en el espacio de nombres <xref:System.Windows.Media?displayProperty=fullName>, así como <xref:System.Windows.Controls.Image>, que reside en el espacio de nombres <xref:System.Windows.Controls?displayProperty=fullName>.  
  
 En este tema se proporciona información adicional sobre el componente administrado.  Para obtener más información sobre la [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] no administrada, consulte la documentación de [Componente no administrado de creación de imágenes de WPF](_wic_lh).  
  
<a name="_imageformats"></a>   
## Formatos de imagen de WPF  
 Se utiliza un códec para descodificar o codificar cada formato multimedia concreto.  [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] incluye un códec para los formatos de imagen [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)], [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)], [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)], [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)], [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)], [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] y de icono.  Cada uno de estos códecs permite a las aplicaciones descodificar y, con la excepción de los iconos, codificar sus formatos de imagen respectivos.  
  
 <xref:System.Windows.Media.Imaging.BitmapSource> es una clase importante utilizada en la descodificación y codificación de imágenes.  Es la unidad de creación básica de la canalización de [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] y representa un conjunto de píxeles único y constante a un tamaño y resolución determinados.  Un <xref:System.Windows.Media.Imaging.BitmapSource> puede ser un fotograma individual de una imagen con varios fotogramas, o puede ser el resultado de una transformación realizada en <xref:System.Windows.Media.Imaging.BitmapSource>.  Se trata del elemento primario de muchas de las clases primarias utilizadas en la creación de imágenes de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], como <xref:System.Windows.Media.Imaging.BitmapFrame>.  
  
 <xref:System.Windows.Media.Imaging.BitmapFrame> se utiliza para almacenar los datos reales del mapa de bits de un formato de imagen.  Numerosos formatos de imagen únicamente admiten un <xref:System.Windows.Media.Imaging.BitmapFrame>, aunque existen formatos, como [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] y [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)], que admiten varios fotogramas por imagen.  Los descodificadores utilizan los fotogramas como datos de entrada y se pasan a los codificadores para crear archivos de imagen.  
  
 En el ejemplo siguiente se demuestra cómo se crea un <xref:System.Windows.Media.Imaging.BitmapFrame> a partir de un <xref:System.Windows.Media.Imaging.BitmapSource> y, a continuación, se agrega a una imagen [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)].  
  
 [!code-csharp[BitmapFrameExample#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### Descodificación de formatos de imagen  
 La descodificación de imágenes consiste en convertir un formato de imagen en datos de imagen que pueden ser utilizados por el sistema.  A continuación, los datos de imagen se pueden utilizar para mostrarlos, procesarlos o codificarlos a un formato diferente.  La selección del descodificador se basa en el formato de la imagen.  La selección del códec es automática a menos que se especifique un descodificador concreto.  En los ejemplos de la sección [Mostrar imágenes en WPF](#_displayingimages) se muestra la descodificación automática.  Los descodificadores de formato personalizados programados mediante interfaces de [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] no administradas y registradas con el sistema participan automáticamente en la selección del descodificador.  Esto permite mostrar los formatos personalizados automáticamente en las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 En el ejemplo siguiente se muestra el uso de un descodificador de mapa de bits para descodificar una imagen en formato [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)].  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
### Codificación de formatos de imagen  
 La codificación de imágenes consiste en convertir los datos de una imagen en un formato de imagen concreto.  A continuación, los datos de imagen codificados se pueden utilizar para crear nuevos archivos de imagen.  [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] proporciona codificadores para cada uno de los formatos de imagen descritos anteriormente.  
  
 En el ejemplo siguiente se muestra el uso de un codificador para guardar una imagen de mapa de bits recién creada.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#3](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#3)]
 [!code-csharp[BmpBitmapDecoderEncoder#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#3)]
 [!code-vb[BmpBitmapDecoderEncoder#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#3)]  
  
<a name="_displayingimages"></a>   
## Mostrar imágenes en WPF  
 Hay varias maneras de mostrar una imagen en una aplicación de [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  Las imágenes se pueden mostrar mediante un control <xref:System.Windows.Controls.Image>, pintado en un objeto visual con un objeto <xref:System.Windows.Media.ImageBrush>, o dibujado con un objeto <xref:System.Windows.Media.ImageDrawing>.  
  
### Utilizar el control de imagen  
 <xref:System.Windows.Controls.Image> es un elemento de marco de trabajo y la manera principal de mostrar imágenes en aplicaciones.  En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], <xref:System.Windows.Controls.Image> se puede utilizar de dos maneras; sintaxis de atributo o sintaxis de propiedad.  En el ejemplo siguiente se muestra cómo representar una imagen de 200 píxeles de ancho mediante la sintaxis de atributo y la sintaxis de etiqueta de propiedad.  Para obtener más información sobre la sintaxis de atributo y la sintaxis de propiedad, consulte [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
 [!code-xml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 En muchos de los ejemplos se utiliza un objeto <xref:System.Windows.Media.Imaging.BitmapImage> para hacer referencia a un archivo de imagen.  <xref:System.Windows.Media.Imaging.BitmapImage> es un <xref:System.Windows.Media.Imaging.BitmapSource> especializado que se optimiza para la carga en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y constituye una manera fácil de mostrar imágenes como la propiedad <xref:System.Windows.Controls.Image.Source%2A> de un control <xref:System.Windows.Controls.Image>.  
  
 En el ejemplo siguiente se muestra cómo representar una imagen de 200 píxeles de ancho mediante código.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Imaging.BitmapImage> implementa la interfaz <xref:System.ComponentModel.ISupportInitialize> para optimizar la inicialización basándose en varias propiedades.  Los cambios de propiedad sólo pueden producirse durante la inicialización del objeto.  Llame a <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> para indicar que la inicialización ha empezado, y a <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> para señalar que la inicialización se ha completado.  Una vez inicializada, los cambios de propiedad se omiten.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### Girar, convertir y recortar imágenes  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] permite a los usuarios transformar imágenes utilizando las propiedades de <xref:System.Windows.Media.Imaging.BitmapImage> o mediante objetos <xref:System.Windows.Media.Imaging.BitmapSource> adicionales, tales como <xref:System.Windows.Media.Imaging.CroppedBitmap> o <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>.  Estas transformaciones de imagen pueden girar una imagen, ajustar su escala, cambiar su formato de píxel o recortarla.  
  
 Los giros de imagen se realizan mediante la propiedad <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A> de <xref:System.Windows.Media.Imaging.BitmapImage>.  Los giros sólo se pueden hacer en incrementos de 90 grados.  En el ejemplo siguiente, una imagen se gira 90 grados.  
  
 [!code-xml[ImageElementExample#TransformedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 Convertir una imagen en un formato de píxel diferente, como la escala de grises, se hace mediante <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>.  En los ejemplos siguientes, se convierte una imagen a <xref:System.Windows.Media.PixelFormats.Gray4%2A>.  
  
 [!code-xml[ImageElementExample_snip#ConvertedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 Para recortar una imagen, se puede utilizar la propiedad <xref:System.Windows.UIElement.Clip%2A> de <xref:System.Windows.Controls.Image> o <xref:System.Windows.Media.Imaging.CroppedBitmap>.  Normalmente, si únicamente desea mostrar una parte de una imagen, debe utilizar <xref:System.Windows.UIElement.Clip%2A>.  Si necesita codificar y guardar una imagen recortada, debe utilizar <xref:System.Windows.Media.Imaging.CroppedBitmap>.  En el ejemplo siguiente, se recorta una imagen mediante la propiedad Clip y un objeto <xref:System.Windows.Media.EllipseGeometry>.  
  
 [!code-xml[ImageElementExample_snip#CroppedXAMLUsingClip1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### Ajustar imágenes  
 La propiedad <xref:System.Windows.Controls.Image.Stretch%2A> controla cómo se ajusta una imagen para rellenar su contenedor.  La propiedad <xref:System.Windows.Controls.Image.Stretch%2A> acepta los valores siguientes, definidos por la enumeración <xref:System.Windows.Media.Stretch>:  
  
-   <xref:System.Windows.Media.Stretch>: la imagen no se ajusta para rellenar el área de salida.  Si la imagen es mayor que el área de salida, la imagen se dibuja en el área de salida, y se recorta lo que sobra.  
  
-   <xref:System.Windows.Media.Stretch>: se ajusta la escala de la imagen al área de salida.  Dado que la escala se aplica de manera independiente al alto y al ancho de la imagen, puede que no se conserve su relación de aspecto original.  Es decir, es posible que la imagen se distorsione para rellenar totalmente el contenedor de salida.  
  
-   <xref:System.Windows.Media.Stretch>: se cambia la escala de la imagen de modo que se ajuste completamente al área de salida.  Se conserva la relación de aspecto de la imagen.  
  
-   <xref:System.Windows.Media.Stretch>: la escala de la imagen se ajusta hasta rellenar completamente el área de salida y se conserva la relación de aspecto original de la imagen.  
  
 En el ejemplo siguiente se aplican todas las enumeraciones <xref:System.Windows.Media.Stretch> disponibles a <xref:System.Windows.Controls.Image>.  
  
 La imagen siguiente muestra el resultado del ejemplo y el efecto que ejercen los distintos valores de <xref:System.Windows.Controls.Image.Stretch%2A> al aplicarlos a una imagen.  
  
 ![Diferentes valores de Stretch para TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/img-mmgraphics-stretchenum.png "img\_mmgraphics\_stretchenum")  
Diferentes valores de ajuste  
  
 [!code-xml[ImageElementExample_snip#ImageStretchExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### Pintar con imágenes  
 Las imágenes también se pueden mostrar en una aplicación pintándolas con un objeto <xref:System.Windows.Media.Brush>.  Los pinceles permiten pintar los objetos de una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con cualquier cosa desde simples colores sólidos hasta conjuntos complejos de tramas e imágenes.  Para pintar con imágenes, utilice un <xref:System.Windows.Media.ImageBrush>.  Un <xref:System.Windows.Media.ImageBrush> es un tipo de <xref:System.Windows.Media.TileBrush> que define su contenido como una imagen de mapa de bits.  Un <xref:System.Windows.Media.ImageBrush> muestra una imagen única, que se especifica mediante su propiedad <xref:System.Windows.Media.ImageBrush.ImageSource%2A>.  Puede controlar cómo se ajusta, alinea o coloca en mosaico la imagen, a fin de evitar la distorsión y crear tramas y otros efectos.  En la ilustración siguiente se muestran algunos efectos que se pueden lograr con <xref:System.Windows.Media.ImageBrush>.  
  
 ![Ejemplos de resultados de ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-imagebrushexamples.png "wcpsdk\_mmgraphics\_imagebrushexamples")  
Los pinceles de imagen pueden rellenar formas, controles, texto, etc.  
  
 En el ejemplo siguiente se muestra cómo pintar el fondo de un botón con una imagen mediante <xref:System.Windows.Media.ImageBrush>.  
  
 [!code-xml[UsingImageBrush#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 Para obtener información adicional acerca de <xref:System.Windows.Media.ImageBrush> y de cómo pintar imágenes, consulte [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="_metadata"></a>   
## Metadatos de imagen  
 Algunos archivos de imagen contienen metadatos que describen el contenido o las características del archivo.  Por ejemplo, la mayoría de las cámaras digitales crean imágenes que contienen metadatos relativos a la marca y el modelo de la cámara empleada para capturar la imagen.  Cada formato de imagen administra de manera diferente los metadatos, pero [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] proporciona una manera uniforme de almacenar y recuperar los metadatos de cada formato de imagen compatible.  
  
 El acceso a los metadatos se proporciona a través de la propiedad <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> de un objeto <xref:System.Windows.Media.Imaging.BitmapSource>.  <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> devuelve un objeto <xref:System.Windows.Media.Imaging.BitmapMetadata> que incluye todos los metadatos contenidos en la imagen.  Estos datos pueden pertenecer a un esquema de metadatos o a una combinación de esquemas diferentes.  [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] admite los esquemas de metadatos de imagen siguientes: [!INCLUDE[TLA#tla_exif](../../../../includes/tlasharptla-exif-md.md)], tEXt \(datos de texto PNG\), [!INCLUDE[TLA#tla_ifd](../../../../includes/tlasharptla-ifd-md.md)], [!INCLUDE[TLA#tla_iptc](../../../../includes/tlasharptla-iptc-md.md)] y [!INCLUDE[TLA#tla_xmp](../../../../includes/tlasharptla-xmp-md.md)].  
  
 Para simplificar el proceso de leer los metadatos, <xref:System.Windows.Media.Imaging.BitmapMetadata> proporciona varias propiedades con nombre a las que resulta fácil tener acceso, como <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>, <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A> y <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>.  Muchas de estas propiedades con nombre también se pueden utilizar para escribir metadatos.  El lector de consulta de metadatos proporciona compatibilidad adicional con la lectura de metadatos.  El método <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> se utiliza para recuperar un lector de consulta de metadatos proporcionando una consulta de cadena, como *"\/app1\/exif\/"*.  En el ejemplo siguiente, se utiliza el método <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> para obtener el texto almacenado en la ubicación *"\/Text\/Description"*."  
  
 [!code-cpp[BitmapMetadata#GetQuery](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 Para escribir metadatos, se utiliza un sistema de escritura de consulta de metadatos.  <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> obtiene el sistema de escritura de consulta y establece el valor deseado.  En el ejemplo siguiente, se utiliza el método <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> para escribir el texto almacenado en la ubicación *"\/Text\/Description"*."  
  
 [!code-cpp[BitmapMetadata#SetQuery](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>   
## Extensibilidad de códec  
 Una característica principal de [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] es el modelo de extensibilidad para los nuevos códecs de imagen.  Estas interfaces no administradas permiten a los desarrolladores de códec integrar los códecs con [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], para que las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] puedan utilizar automáticamente los nuevos formatos de imagen.  
  
 Para obtener un ejemplo de [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] de extensibilidad, vea [Win32 Sample Codec](http://go.microsoft.com/fwlink/?LinkID=160052).  En este ejemplo se muestra cómo crear un descodificador y codificador para un formato de imagen personalizado.  
  
> [!NOTE]
>  El códec debe estar firmado digitalmente para que el sistema lo reconozca.  
  
## Vea también  
 <xref:System.Windows.Media.Imaging.BitmapSource>   
 <xref:System.Windows.Media.Imaging.BitmapImage>   
 <xref:System.Windows.Controls.Image>   
 <xref:System.Windows.Media.Imaging.BitmapMetadata>   
 [Imágenes y gráficos GDI\+](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Ejemplo Win32 Codec](http://go.microsoft.com/fwlink/?LinkID=160052)