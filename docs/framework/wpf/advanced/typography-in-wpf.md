---
title: Tipografía
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], about typography
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
ms.openlocfilehash: 501a4221c99d405484a2fb908641d27d1f38f266
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187351"
---
# <a name="typography-in-wpf"></a>Tipografía en WPF
En este tema se presentan las características tipográficas principales de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Estas características incluyen una mejor calidad y rendimiento de la representación de texto, compatibilidad con tipografía SOpenType, texto internacional mejorado, compatibilidad mejorada con fuentes y nuevas interfaces de programación de aplicaciones de texto (API).  
  
<a name="Improved_Quality_and_Performance_of_Text"></a>
## <a name="improved-quality-and-performance-of-text"></a>Mejora de la calidad y el rendimiento del texto  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] texto en se representa mediante Microsoft ClearType, que mejora la claridad y la legibilidad del texto. ClearType es una tecnología de software desarrollada por Microsoft que mejora la legibilidad del texto en pantallas LCD existentes (pantallas de cristal líquido), como pantallas de portátiles, pantallas de Pocket PC y monitores de pantalla plana. ClearType utiliza la representación de subpíxeles que permite que el texto se muestre con una mayor fidelidad a su forma verdadera alineando caracteres en una parte fraccionaria de un píxel. Esta resolución adicional aumenta la nitidez de los detalles diminutos en la presentación del texto, lo que facilita la lectura durante largos períodos de tiempo. Otra mejora de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ClearType en es el suavizado de dirección Y, que suaviza las partes superior e inferior de las curvas poco profundas en caracteres de texto. Para obtener más información sobre las características de ClearType, vea Información general sobre [ClearType](cleartype-overview.md).  
  
 ![Texto con función de suavizado de contorno de ClearType en la dirección del eje y](./media/typography-in-wpf/text-y-direction-antialiasing.gif)  
Texto con función de suavizado de contorno de ClearType en la dirección del eje Y  
  
 La canalización de representación de texto completo se puede acelerar mediante hardware en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], siempre y cuando la máquina cumpla los requisitos mínimos de hardware. Si una representación no se puede realizar mediante hardware, se recurre a la representación mediante software. La aceleración de hardware afecta a todas las fases de la canalización de representación de texto, desde almacenar glifos individuales, componer glifos en corridas de glifos, aplicar efectos hasta aplicar el algoritmo de fusión ClearType a la salida final mostrada. Para obtener más información sobre la aceleración de hardware, vea [Niveles de representación de gráficos](graphics-rendering-tiers.md).  
  
 ![Diagrama de la canalización de representación de texto](./media/typography-in-wpf/text-rendering-pipeline.png)  
  
 Además, el texto animado, ya sea mediante caracteres o glifos, aprovecha al máximo la capacidad de hardware gráfico habilitada por [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Como resultado, la animación de texto se suaviza.  
  
<a name="Rich_Typography"></a>
## <a name="rich-typography"></a>Tipografía enriquecida  
 El formato de fuente OpenType es una extensión del formato de fuente TrueType®. El formato de fuente OpenType fue desarrollado conjuntamente por Microsoft y Adobe, y proporciona una amplia variedad de características tipográficas avanzadas. El <xref:System.Windows.Documents.Typography> objeto expone muchas de las características avanzadas de las fuentes OpenType, como alternativas estilísticas y swashes. Windows SDK proporciona un conjunto de fuentes OpenType de ejemplo diseñadas con características enriquecidas, como las fuentes Pericles y Pescadero. Para obtener más información, vea [Sample OpenType Font Pack](sample-opentype-font-pack.md).  
  
 La fuente Pericles OpenType contiene glifos adicionales que proporcionan alternativas estilísticas al conjunto estándar de pictogramas. En el texto siguiente se muestran glifos alternativos de estilo.  
  
 ![Texto que usa glifos alternativos de estilo OpenType](./media/typography-in-wpf/opentype-stylistic-alternate-glyphs.gif "Texto que usa glifos alternativos de estilo OpenType")  
  
 Los caracteres floreados son glifos decorativos que usan adornos elaborados que suelen asociarse a la caligrafía. El texto siguiente muestra glifos estándar y swash para la fuente Pescadero.  
  
 ![Texto que usa glifos OpenType estándar y floreados](./media/typography-in-wpf/opentype-standard-swash-glyphs.gif "Texto que usa glifos OpenType estándar y floreados")  
  
 Para obtener más información sobre las características de OpenType, vea Características de [fuente OpenType](opentype-font-features.md).  
  
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
  
- Separar <xref:System.Windows.FontWeight> <xref:System.Windows.FontStretch>, <xref:System.Windows.FontStyle> , y tipos <xref:System.Windows.Media.FontFamily>para definir un archivo . Esto proporciona una mayor flexibilidad que en la programación Win32, en la que se utilizan combinaciones booleanas de cursiva y negrita para definir una familia de fuentes.  
  
- La dirección de escritura (horizontal o vertical) se controla con independencia del nombre de la fuente.  
  
- Vinculación de fuentes y reserva de fuentes en un archivo XML portátil, utilizando tecnología de fuentes compuestas. Las fuentes compuestas permiten la construcción de fuentes multilingües completas. Las fuentes compuestas también proporcionan un mecanismo que impide la presentación de los glifos que faltan. Para obtener más información, consulte <xref:System.Windows.Media.FontFamily> las observaciones de la clase.  
  
- Las fuentes internacionales se generan a partir de fuentes compuestas mediante un grupo de fuentes de un solo idioma. De este modo se ahorran recursos a la hora de desarrollar fuentes para varios idiomas.  
  
- Las fuentes compuestas se insertan en un documento, lo que permite la portabilidad de los documentos. Para obtener más información, consulte <xref:System.Windows.Media.FontFamily> las observaciones de la clase.  
  
<a name="New_Text_APIs"></a>
## <a name="new-text-application-programming-interfaces-apis"></a>Nuevas interfaces de programación de aplicaciones (API) de texto  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]proporciona varias API de texto para que los desarrolladores las usen al incluir texto en sus aplicaciones. Estas API se agrupan en tres categorías:  
  
- **Diseño e interfaz de usuario**. Los controles de texto comunes para la interfaz gráfica de usuario (GUI).  
  
- **Dibujo de texto ligero**. Permite dibujar texto directamente en objetos.  
  
- **Formato de texto avanzado**. Permite implementar un motor de texto personalizado.  
  
### <a name="layout-and-user-interface"></a>Diseño e interfaz de usuario  
 En el nivel más alto de funcionalidad, [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] las <xref:System.Windows.Controls.Label>API <xref:System.Windows.Controls.TextBlock>de <xref:System.Windows.Controls.TextBox>texto proporcionan controles comunes como , , y . Estos controles proporcionan elementos de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] básicos dentro de una aplicación y ofrecen una manera fácil de presentar el texto e interactuar con él. Controles como <xref:System.Windows.Controls.RichTextBox> <xref:System.Windows.Controls.PasswordBox> y permiten un control de texto más avanzado o especializado. Y clases <xref:System.Windows.Documents.TextRange> <xref:System.Windows.Documents.TextSelection>como <xref:System.Windows.Documents.TextPointer> , , y permiten la manipulación de texto útil. Estos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] controles proporcionan <xref:System.Windows.Controls.Control.FontFamily%2A>propiedades <xref:System.Windows.Controls.Control.FontSize%2A>como <xref:System.Windows.Controls.Control.FontStyle%2A>, , y , que permiten controlar la fuente que se utiliza para representar el texto.  
  
#### <a name="using-bitmap-effects-transforms-and-text-effects"></a>Uso de efectos de imagen, transformaciones y efectos de texto  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permite crear usar el texto de forma visualmente interesante mediante características como efectos de imagen, transformaciones y efectos de texto. En el ejemplo siguiente se muestra un efecto típico de sombra paralela aplicado al texto.  
  
 ![Sombra de texto con suavidad &#61; 0.25](./media/typography-in-wpf/drop-shadow-text-effect.jpg)
  
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
 Además de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] los [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controles comunes, ofrece un <xref:System.Windows.Documents.FlowDocument> control de diseño para la presentación de texto: el elemento. El <xref:System.Windows.Documents.FlowDocument> elemento, junto <xref:System.Windows.Controls.DocumentViewer> con el elemento, proporciona un control para grandes cantidades de texto con diferentes requisitos de diseño. Los controles de diseño proporcionan <xref:System.Windows.Documents.Typography> acceso a la tipografía [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] avanzada a través de las propiedades relacionadas con el objeto y la fuente de otros controles.  
  
 En el ejemplo siguiente se <xref:System.Windows.Controls.FlowDocumentReader>muestra el contenido de texto hospedado en un , que proporciona compatibilidad con la búsqueda, la navegación, la paginación y el escalado de contenido.  
  
 ![Captura de pantalla que muestra las fuentes OpenType.](./media/typography-in-wpf/typography-text-flowdocumentreader.png)
  
 Para obtener más información, vea [Documentos en WPF](documents-in-wpf.md).  
  
### <a name="lightweight-text-drawing"></a>Dibujo de texto ligero  
 Puede dibujar texto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] directamente en <xref:System.Windows.Media.DrawingContext.DrawText%2A> objetos <xref:System.Windows.Media.DrawingContext> mediante el método del objeto. Para utilizar este método, <xref:System.Windows.Media.FormattedText> cree un objeto. Este objeto permite dibujar texto de varias líneas, en el que se puede dar formato individual a cada carácter del texto. La funcionalidad del <xref:System.Windows.Media.FormattedText> objeto contiene gran parte de la funcionalidad de los DrawText marcas en la API de Windows. Además, <xref:System.Windows.Media.FormattedText> el objeto contiene funcionalidad como la compatibilidad con puntos suspensivos, en la que se muestran puntos suspensivos cuando el texto supera sus límites. En el ejemplo siguiente se muestra texto al que se han aplicado varios formatos diferentes, incluido un degradado lineal en la segunda y tercera palabra.  
  
 ![Texto mostrado mediante un objeto FormattedText](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)
  
 Puede convertir texto con <xref:System.Windows.Media.Geometry> formato en objetos, lo que le permite crear otros tipos de texto visualmente interesante. Por ejemplo, podría <xref:System.Windows.Media.Geometry> crear un objeto basado en el contorno de una cadena de texto.  
  
 ![Esquema de texto que usa un pincel de degradado lineal](./media/typography-in-wpf/text-outline-linear-gradient.jpg)  
  
 En los ejemplos siguientes se muestran varias maneras de crear efectos visuales interesantes modificando el trazo, el relleno y el resaltado del texto convertido.  
  
 ![Texto con colores diferentes para relleno y trazo](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Texto con pincel de imagen aplicado a trazo](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Texto con pincel de imagen aplicado al trazo y resaltado](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Para obtener más <xref:System.Windows.Media.FormattedText> información sobre el objeto, consulte Dibujo de [texto con formato](drawing-formatted-text.md).  
  
### <a name="advanced-text-formatting"></a>Formato de texto avanzado  
 En el nivel más avanzado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las API de texto, ofrece <xref:System.Windows.Media.TextFormatting.TextFormatter> la capacidad de <xref:System.Windows.Media.TextFormatting> crear un diseño de texto personalizado mediante el objeto y otros tipos en el espacio de nombres. Las <xref:System.Windows.Media.TextFormatting.TextFormatter> clases asociadas le permiten implementar un diseño de texto personalizado que admite su propia definición de formatos de caracteres, estilos de párrafo, reglas de salto de línea y otras características de diseño para texto internacional. Se darán muy pocos casos en los que le interese reemplazar la implementación predeterminada de la compatibilidad con el diseño de texto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], pero si está creando un aplicación o un control de edición de texto, es posible que necesite una implementación diferente de la implementación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] predeterminada.  
  
 A diferencia de una <xref:System.Windows.Media.TextFormatting.TextFormatter> API de texto tradicional, interactúa con un cliente de diseño de texto a través de un conjunto de métodos de devolución de llamada. Requiere que el cliente proporcione estos métodos <xref:System.Windows.Media.TextFormatting.TextSource> en una implementación de la clase. En el diagrama siguiente se muestra la <xref:System.Windows.Media.TextFormatting.TextFormatter>interacción de diseño de texto entre la aplicación cliente y .  
  
 ![Diagrama de TextFormatter y cliente de diseño de texto](./media/typography-in-wpf/text-layout-text-formatter-interaction.png)  
  
 Para obtener más información sobre la creación de un diseño de texto personalizado, vea [Formato de texto avanzado](advanced-text-formatting.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.FormattedText>
- <xref:System.Windows.Media.TextFormatting.TextFormatter>
- [Información general sobre ClearType](cleartype-overview.md)
- [Características de las fuentes OpenType](opentype-font-features.md)
- [Dibujar texto con formato](drawing-formatted-text.md)
- [Formato de texto avanzado](advanced-text-formatting.md)
- [Texto](optimizing-performance-text.md)
- [Tipografía de Microsoft](https://docs.microsoft.com/typography/)
