---
title: Tipografía en WPF
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], about typography
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
ms.openlocfilehash: eba59f81fa19ee3fe4fbb82682ca986d082e449f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64621586"
---
# <a name="typography-in-wpf"></a>Tipografía en WPF
En este tema se presentan las características tipográficas principales de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Estas características incluyen la mejora de la calidad y el rendimiento de la representación de texto, la compatibilidad con tipografía [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)], el texto internacional mejorado, la compatibilidad mejorada con fuentes y nuevas interfaces de programación de aplicaciones (API) de texto.  
  
<a name="Improved_Quality_and_Performance_of_Text"></a>   
## <a name="improved-quality-and-performance-of-text"></a>Mejora de la calidad y el rendimiento del texto  
 El texto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se representa mediante [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)], que mejora la claridad y la legibilidad del texto. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] es una tecnología de software desarrollada por [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] que mejora la legibilidad del texto en pantallas de cristal líquido (LCD) existentes, como las de portátiles, Pocket PC y monitores de pantalla plana. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] usa la representación de subpíxeles, lo que permite mostrar el texto de una manera más fiel a su forma real, ya que alinea los caracteres en una parte fraccionaria de un píxel. Esta resolución adicional aumenta la nitidez de los detalles diminutos en la presentación del texto, lo que facilita la lectura durante largos períodos de tiempo. Otra mejora de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es el suavizado de contorno en la dirección del eje Y, que suaviza la parte superior e inferior de las curvas de los caracteres de texto. Para obtener más detalles sobre las características de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)], vea [Información general sobre ClearType](cleartype-overview.md).  
  
 ![Texto con función de suavizado de contorno de ClearType en la dirección del eje y](./media/typography-in-wpf/text-y-direction-antialiasing.gif)  
Texto con función de suavizado de contorno de ClearType en la dirección del eje Y  
  
 La canalización de representación de texto completo se puede acelerar mediante hardware en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], siempre y cuando la máquina cumpla los requisitos mínimos de hardware. Si una representación no se puede realizar mediante hardware, se recurre a la representación mediante software. La aceleración de hardware afecta a todas las fases de la canalización de representación de texto: almacenamiento de glifos individuales, composición de glifos en secuencias de glifos, aplicación de efectos y aplicación del algoritmo de combinación [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] a la salida final mostrada. Para obtener más información sobre la aceleración de hardware, vea [Niveles de representación de gráficos](graphics-rendering-tiers.md).  
  
 ![Diagrama de la canalización de representación de texto](./media/typography-in-wpf/text-rendering-pipeline.png)  
  
 Además, el texto animado, ya sea mediante caracteres o glifos, aprovecha al máximo la capacidad de hardware gráfico habilitada por [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Como resultado, la animación de texto se suaviza.  
  
<a name="Rich_Typography"></a>   
## <a name="rich-typography"></a>Tipografía enriquecida  
 El formato de fuente [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] es una extensión del formato de fuente [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)]. [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] y Adobe desarrollaron conjuntamente el formato de fuente [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)], que proporciona una gran variedad de características tipográficas avanzadas. El <xref:System.Windows.Documents.Typography> objeto expone muchas de las características avanzadas de [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] fuentes, como formato de alternativas estilística y caracteres floreados. [!INCLUDE[TLA2#tla_lhsdk](../../../../includes/tla2sharptla-lhsdk-md.md)] proporciona un conjunto de fuentes [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] de ejemplo que están diseñadas con características enriquecidas, como las fuentes Pericles y Pescadero. Para obtener más información, vea [Paquete de fuentes OpenType de ejemplo](sample-opentype-font-pack.md).  
  
 La fuente [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] Pericles contiene glifos adicionales que proporcionan alternativas estilísticas al conjunto estándar de glifos. En el texto siguiente se muestran glifos alternativos de estilo.  
  
 ![Texto que usa glifos alternativos de estilo OpenType](./media/typography-in-wpf/opentype-stylistic-alternate-glyphs.gif "texto mediante glifos alternativos de estilo OpenType")  
  
 Los caracteres floreados son glifos decorativos que usan adornos elaborados que suelen asociarse a la caligrafía. El texto siguiente muestran glifos estándar y floreados para la fuente Pescadero.  
  
 ![Texto que usa glifos OpenType estándar y floreados](./media/typography-in-wpf/opentype-standard-swash-glyphs.gif "texto mediante glifos OpenType estándar y floreados")  
  
 Para obtener más detalles sobre las características de [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)], vea [Características de las fuentes OpenType](opentype-font-features.md).  
  
<a name="Enhanced_International_Text_Support"></a>   
## <a name="enhanced-international-text-support"></a>Compatibilidad mejorada con texto internacional  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona compatibilidad mejorada con texto internacional mediante las características siguientes:  
  
- Interlineado automático en todos los sistemas de escritura mediante la medición adaptable.  
  
- Amplia compatibilidad con texto internacional. Para obtener más información, vea [Globalización de WPF](globalization-for-wpf.md).  
  
- Saltos de línea, guiones y justificación basados en el idioma.  
  
<a name="Enhanced_Font_Support"></a>   
## <a name="enhanced-font-support"></a>Compatibilidad mejorada con fuentes  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona compatibilidad con fuentes mejorada mediante las características siguientes:  
  
- Se usa Unicode para todo el texto. El comportamiento y la selección de la fuente ya no requieren un conjunto de caracteres o página de códigos.  
  
- El comportamiento de la fuente es independiente de la configuración global, como la configuración regional del sistema.  
  
- Independiente <xref:System.Windows.FontWeight>, <xref:System.Windows.FontStretch>, y <xref:System.Windows.FontStyle> tipos para definir un <xref:System.Windows.Media.FontFamily>. Esto proporciona mayor flexibilidad que en la programación de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], en la que se usan combinaciones booleanas de negrita y cursiva para definir una familia de fuentes.  
  
- La dirección de escritura (horizontal o vertical) se controla con independencia del nombre de la fuente.  
  
- La vinculación de fuentes y la reserva de fuentes se incluye en un archivo [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] portátil mediante la tecnología de fuentes compuestas. Las fuentes compuestas permiten la construcción de fuentes multilingües completas. Las fuentes compuestas también proporcionan un mecanismo que impide la presentación de los glifos que faltan. Para obtener más información, vea los comentarios de la <xref:System.Windows.Media.FontFamily> clase.  
  
- Las fuentes internacionales se generan a partir de fuentes compuestas mediante un grupo de fuentes de un solo idioma. De este modo se ahorran recursos a la hora de desarrollar fuentes para varios idiomas.  
  
- Las fuentes compuestas se insertan en un documento, lo que permite la portabilidad de los documentos. Para obtener más información, vea los comentarios de la <xref:System.Windows.Media.FontFamily> clase.  
  
<a name="New_Text_APIs"></a>   
## <a name="new-text-application-programming-interfaces-apis"></a>Nuevas interfaces de programación de aplicaciones (API) de texto  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona varias [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] de texto para que las usen los desarrolladores al incluir texto en sus aplicaciones. Estas [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] se agrupan en tres categorías:  
  
- **Diseño e interfaz de usuario**. Controles de texto comunes para la [!INCLUDE[TLA#tla_gui](../../../../includes/tlasharptla-gui-md.md)].  
  
- **Dibujo de texto ligero**. Permite dibujar texto directamente en objetos.  
  
- **Formato de texto avanzado**. Permite implementar un motor de texto personalizado.  
  
### <a name="layout-and-user-interface"></a>Diseño e interfaz de usuario  
 En el nivel más alto de funcionalidad, el texto [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] proporcionar comunes [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] controles como <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBlock>, y <xref:System.Windows.Controls.TextBox>. Estos controles proporcionan elementos de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] básicos dentro de una aplicación y ofrecen una manera fácil de presentar el texto e interactuar con él. Los controles como <xref:System.Windows.Controls.RichTextBox> y <xref:System.Windows.Controls.PasswordBox> habilitar más avanzado o especializado de control de texto. Y las clases como <xref:System.Windows.Documents.TextRange>, <xref:System.Windows.Documents.TextSelection>, y <xref:System.Windows.Documents.TextPointer> habilitar la manipulación de texto muy útil. Estos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] controles proporcionan propiedades como <xref:System.Windows.Controls.Control.FontFamily%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, y <xref:System.Windows.Controls.Control.FontStyle%2A>, que le permiten controlar la fuente que se usa para representar el texto.  
  
#### <a name="using-bitmap-effects-transforms-and-text-effects"></a>Uso de efectos de imagen, transformaciones y efectos de texto  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permite crear usar el texto de forma visualmente interesante mediante características como efectos de imagen, transformaciones y efectos de texto. En el ejemplo siguiente se muestra un efecto típico de sombra paralela aplicado al texto.  
  
 ![Sombra de texto con suavidad &#61; 0,25](./media/typography-in-wpf/drop-shadow-text-effect.jpg) 
  
 En el ejemplo siguiente se muestra un efecto de sombra paralela y ruido aplicado al texto.  
  
 ![Sombra de texto con ruido](./media/typography-in-wpf/drop-shadow-noise-text.jpg) 
  
 En el ejemplo siguiente se muestra un efecto de iluminado exterior aplicado al texto.  
  
 ![Sombra de texto usando OuterGlowBitmapEffect](./media/typography-in-wpf/text-shadow-glow-effect.jpg)
  
 En el ejemplo siguiente se muestra un efecto de desenfoque aplicado al texto.  
  
 ![Sombra de texto usando BlurBitmapEffect](./media/typography-in-wpf/text-shadow-blur-effect.jpg)  

 En el ejemplo siguiente se muestra la segunda línea de texto escalada al 150 % a lo largo del eje X y la tercera línea de texto escalada al 150 % a lo largo del eje Y.  
  
 ![Texto con escala ajustada usando ScaleTransform](./media/typography-in-wpf/scaled-text-scaletransform.jpg) 
  
 En el ejemplo siguiente se muestra el texto sesgado a lo largo del eje X.  
  
 ![Texto sesgado usando SkewTransform](./media/typography-in-wpf/skewed-transformed-text.jpg)
  
 Un <xref:System.Windows.Media.TextEffect> objeto es un objeto auxiliar que permite tratar el texto como uno o varios grupos de caracteres en una cadena de texto. En el ejemplo siguiente se muestra un carácter individual girado. Cada carácter se gira de manera independiente a intervalos de 1 segundo.  
  
 ![Captura de pantalla de efecto de texto girando texto](./media/typography-in-wpf/rotating-text-effect.jpg) 
  
#### <a name="using-flow-documents"></a>Uso de documentos dinámicos  
 Además de los archivos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] controles, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ofrece un control de diseño para la presentación de texto, el <xref:System.Windows.Documents.FlowDocument> elemento. El <xref:System.Windows.Documents.FlowDocument> elemento, junto con el <xref:System.Windows.Controls.DocumentViewer> elemento, proporciona un control para grandes cantidades de texto con diferentes requisitos de diseño. Controles de diseño proporcionan acceso a tipografía avanzada a través de la <xref:System.Windows.Documents.Typography> objetos y propiedades relacionadas con la fuente de otros [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] controles.  
  
 El ejemplo siguiente muestra el contenido de texto hospedado en un <xref:System.Windows.Controls.FlowDocumentReader>, que proporciona búsqueda, navegación, paginación y escalado de soporte técnico de contenido.  
  
 ![Captura de pantalla que muestra las fuentes OpenType.](./media/typography-in-wpf/typography-text-flowdocumentreader.png)
  
 Para obtener más información, consulte [Documentos en WPF](documents-in-wpf.md).  
  
### <a name="lightweight-text-drawing"></a>Dibujo de texto ligero  
 Puede dibujar texto directamente en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objetos mediante el uso de la <xref:System.Windows.Media.DrawingContext.DrawText%2A> método de la <xref:System.Windows.Media.DrawingContext> objeto. Para usar este método, se crea un <xref:System.Windows.Media.FormattedText> objeto. Este objeto permite dibujar texto de varias líneas, en el que se puede dar formato individual a cada carácter del texto. La funcionalidad de la <xref:System.Windows.Media.FormattedText> objeto contiene gran parte de la funcionalidad de las marcas DrawText de la API de Windows. Además, el <xref:System.Windows.Media.FormattedText> objeto contiene la funcionalidad como la compatibilidad con puntos suspensivos, en el que se muestra un botón de puntos suspensivos al texto supera los límites establecidos. En el ejemplo siguiente se muestra texto al que se han aplicado varios formatos diferentes, incluido un degradado lineal en la segunda y tercera palabra.  
  
 ![Texto mostrado mediante un objeto FormattedText](./media/typography-in-wpf/text-formatted-linear-gradient.jpg) 
  
 Puede convertir texto con formato en <xref:System.Windows.Media.Geometry> objetos, lo que permite crear otros tipos de texto visualmente interesante. Por ejemplo, podría crear un <xref:System.Windows.Media.Geometry> objeto basado en el esquema de una cadena de texto.  
  
 ![Esquema de texto que usa un pincel de degradado lineal](./media/typography-in-wpf/text-outline-linear-gradient.jpg)  
  
 En los ejemplos siguientes se muestran varias maneras de crear efectos visuales interesantes modificando el trazo, el relleno y el resaltado del texto convertido.  
  
 ![Texto con colores diferentes para relleno y trazo](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Texto con pincel de imagen aplicado a trazo](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Texto con pincel de imagen aplicado para trazar y resaltar](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Para obtener más información sobre la <xref:System.Windows.Media.FormattedText> de objetos, consulte [dibujar texto con formato](drawing-formatted-text.md).  
  
### <a name="advanced-text-formatting"></a>Formato de texto avanzado  
 En el nivel más avanzado del texto [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ofrece la posibilidad de crear el diseño de texto personalizado mediante la <xref:System.Windows.Media.TextFormatting.TextFormatter> objeto y otros tipos en el <xref:System.Windows.Media.TextFormatting> espacio de nombres. El <xref:System.Windows.Media.TextFormatting.TextFormatter> y las clases asociadas permiten implementar el diseño de texto personalizado que admita su propia definición de formatos de caracteres, estilos de párrafo, reglas de salto de línea y otras características de diseño de texto internacional. Se darán muy pocos casos en los que le interese reemplazar la implementación predeterminada de la compatibilidad con el diseño de texto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], pero si está creando un aplicación o un control de edición de texto, es posible que necesite una implementación diferente de la implementación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] predeterminada.  
  
 A diferencia de un texto tradicional [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)], el <xref:System.Windows.Media.TextFormatting.TextFormatter> interactúa con un cliente de diseño de texto a través de un conjunto de métodos de devolución de llamada. Requiere que el cliente proporcione estos métodos en una implementación de la <xref:System.Windows.Media.TextFormatting.TextSource> clase. El siguiente diagrama ilustra la interacción del diseño de texto entre la aplicación cliente y <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
 ![Diagrama de TextFormatter y cliente de diseño de texto](./media/typography-in-wpf/text-layout-text-formatter-interaction.png)  
  
 Para obtener más información sobre la creación de un diseño de texto personalizado, vea [Formato de texto avanzado](advanced-text-formatting.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.FormattedText>
- <xref:System.Windows.Media.TextFormatting.TextFormatter>
- [Información general sobre ClearType](cleartype-overview.md)
- [Características de las fuentes OpenType](opentype-font-features.md)
- [Dibujar texto con formato](drawing-formatted-text.md)
- [Formato de texto avanzado](advanced-text-formatting.md)
- [Texto](optimizing-performance-text.md)
- [Tipografía de Microsoft](https://docs.microsoft.com/typography/)
