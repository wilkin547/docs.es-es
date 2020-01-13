---
title: Dibujar texto con formato
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF]
- typography [WPF], drawing formatted text
- formatted text [WPF]
- drawing [WPF], formatted text
ms.assetid: b1d851c1-331c-4814-9964-6fe769db6f1f
ms.openlocfilehash: c786137a471e0199a8ac60f8d82b4ce440e33b7e
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740400"
---
# <a name="drawing-formatted-text"></a>Dibujar texto con formato
En este tema se proporciona información general sobre las características del objeto <xref:System.Windows.Media.FormattedText>. Este objeto proporciona control de nivel bajo para dibujar texto en aplicaciones [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  

## <a name="technology-overview"></a>Información general sobre la tecnología  
 El objeto <xref:System.Windows.Media.FormattedText> permite dibujar texto de varias líneas, en el que se puede dar formato a cada carácter del texto de forma individual. En el ejemplo siguiente se muestra texto al que se le aplicaron varios formatos.  
  
 ![Texto mostrado mediante un objeto FormattedText](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)  
  
> [!NOTE]
> Para aquellos desarrolladores que migran desde la API de Win32, en la tabla de la sección [migración de Win32](#win32_migration) se enumeran las marcas DrawText de Win32 y el equivalente aproximado en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
### <a name="reasons-for-using-formatted-text"></a>Razones para utilizar el texto con formato  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye varios controles para dibujar texto en la pantalla. Cada control se destina a un escenario diferente y tiene su propia lista de características y limitaciones. En general, el elemento <xref:System.Windows.Controls.TextBlock> debe usarse cuando se requiere compatibilidad de texto limitada, como una frase breve en un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> se puede usar cuando se requiere compatibilidad de texto mínima. Para obtener más información, vea [Documentos en WPF](documents-in-wpf.md).  
  
 El objeto <xref:System.Windows.Media.FormattedText> proporciona características de formato de texto más que [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] controles de texto, y puede ser útil en los casos en los que desea utilizar texto como elemento decorativo. Para obtener más información, consulte la sección siguiente [Convertir texto con formato en una geometría](#converting_formatted_text).  
  
 Además, el objeto <xref:System.Windows.Media.FormattedText> es útil para crear objetos derivados de <xref:System.Windows.Media.DrawingVisual>orientados a texto. <xref:System.Windows.Media.DrawingVisual> es una clase de dibujo ligera que se utiliza para representar formas, imágenes o texto. Para obtener más información, consulte [Hit Test Using DrawingVisuals Sample](https://go.microsoft.com/fwlink/?LinkID=159994).  
  
## <a name="using-the-formattedtext-object"></a>Utilizar el objeto FormattedText  
 Para crear texto con formato, llame al constructor <xref:System.Windows.Media.FormattedText.%23ctor%2A> para crear un objeto <xref:System.Windows.Media.FormattedText>. Una vez que haya creado la cadena inicial de texto con formato, podrá aplicar una gama de estilos de formato.  
  
 Use la propiedad <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> para restringir el texto a un ancho específico. El texto se ajustará automáticamente para evitar superar el ancho especificado. Use la propiedad <xref:System.Windows.Media.FormattedText.MaxTextHeight%2A> para restringir el texto a un alto específico. El texto mostrará puntos suspensivos ("...") para el texto que supere el alto especificado.  
  
 ![Texto que se muestra con WordWrap y puntos suspensivos.](./media/drawing-formatted-text/formatted-text-wordwrap-ellipsis.png)    
  
 Puede aplicar varios estilos de formato a uno o más caracteres. Por ejemplo, puede llamar a los métodos <xref:System.Windows.Media.FormattedText.SetFontSize%2A> y <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> para cambiar el formato de los cinco primeros caracteres del texto.  
  
 En el ejemplo de código siguiente se crea un objeto <xref:System.Windows.Media.FormattedText> y, a continuación, se aplican varios estilos de formato al texto.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
### <a name="font-size-unit-of-measure"></a>Unidad de medida del tamaño de fuente  
 Como con otros objetos de texto en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplicaciones, el objeto de <xref:System.Windows.Media.FormattedText> utiliza píxeles independientes del dispositivo como unidad de medida. Sin embargo, la mayoría de las aplicaciones de Win32 usan puntos como unidad de medida. Si desea utilizar texto para mostrar en unidades de puntos en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplicaciones, debe convertir las unidades independientes del dispositivo (1/1/96 de pulgada por unidad) en puntos. En el ejemplo de código siguiente se muestra cómo realizar esta conversión.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets2)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets2)]  
  
<a name="converting_formatted_text"></a>   
### <a name="converting-formatted-text-to-a-geometry"></a>Convertir texto con formato a una geometría  
 Puede convertir texto con formato en objetos de <xref:System.Windows.Media.Geometry>, lo que le permite crear otros tipos de texto visualmente interesante. Por ejemplo, puede crear un objeto de <xref:System.Windows.Media.Geometry> basado en el contorno de una cadena de texto.  
  
 ![Esquema de texto que usa un pincel de degradado lineal](./media/typography-in-wpf/text-outline-linear-gradient.jpg)    
  
 En los ejemplos siguientes se muestran varias maneras de crear efectos visuales interesantes modificando el trazo, el relleno y el resaltado del texto convertido.  
  
 ![Texto con colores diferentes para relleno y trazo](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Texto con pincel de imagen aplicado a trazo](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Texto con pincel de imagen aplicado al trazo y al resaltado](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Cuando el texto se convierte en un objeto <xref:System.Windows.Media.Geometry>, ya no es una colección de caracteres; no se pueden modificar los caracteres de la cadena de texto. Sin embargo, puede afectar a la apariencia del texto convertido modificando sus propiedades de trazo y relleno. El trazo se refiere al contorno del texto convertido; el relleno es el área dentro del contorno del texto convertido. Para obtener más información, consulte [Crear texto con contorno](how-to-create-outlined-text.md).  
  
 También puede convertir texto con formato en un objeto <xref:System.Windows.Media.PathGeometry> y usar el objeto para resaltar el texto. Por ejemplo, puede aplicar una animación al objeto <xref:System.Windows.Media.PathGeometry> para que la animación siga el contorno del texto con formato.  
  
 En el ejemplo siguiente se muestra texto con formato que se ha convertido en un objeto <xref:System.Windows.Media.PathGeometry>. Una elipse animada sigue la ruta de los trazos del texto representado.  
  
 ![Esfera que sigue la geometría de trayecto de texto](./media/drawing-formatted-text/sphere-following-geometry-path.gif)  
Esfera que sigue la geometría de trayecto de texto  
  
 Para obtener más información, consulte [How to: Create a PathGeometry Animation for Text](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100)) (Cómo: Crear una animación PathGeometry para texto).  
  
 Puede crear otros usos interesantes para el texto con formato una vez que se haya convertido en un objeto de <xref:System.Windows.Media.PathGeometry>. Por ejemplo, puede recortar vídeo para que se muestre dentro de él.  
  
 ![Vídeo mostrándose en la geometría de trayecto de texto](./media/drawing-formatted-text/video-displaying-text-path-geometry.png)
  
<a name="win32_migration"></a>   
## <a name="win32-migration"></a>Migración de Win32  
 Las características de <xref:System.Windows.Media.FormattedText> para dibujar texto son similares a las características de la función DrawText de Win32. Para aquellos desarrolladores que migran desde la API de Win32, en la tabla siguiente se enumeran las marcas DrawText de Win32 y el equivalente aproximado en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
|Marca DrawText|Equivalente de WPF|Notas|  
|-------------------|--------------------|-----------|  
|DT_BOTTOM|<xref:System.Windows.Media.FormattedText.Height%2A>|Utilice la propiedad <xref:System.Windows.Media.FormattedText.Height%2A> para calcular una posición adecuada de Win32 DrawText ' y '.|  
|DT_CALCRECT|<xref:System.Windows.Media.FormattedText.Height%2A>, <xref:System.Windows.Media.FormattedText.Width%2A>|Use las propiedades <xref:System.Windows.Media.FormattedText.Height%2A> y <xref:System.Windows.Media.FormattedText.Width%2A> para calcular el rectángulo de salida.|  
|DT_CENTER|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Use la propiedad <xref:System.Windows.Media.FormattedText.TextAlignment%2A> con el valor establecido en <xref:System.Windows.TextAlignment.Center>.|  
|DT_EDITCONTROL|Ninguno|No requerido. El ancho del espacio y la representación de la última línea son los mismos que en el control de edición de marcos.|  
|DT_END_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Use la propiedad <xref:System.Windows.Media.FormattedText.Trimming%2A> con el valor <xref:System.Windows.TextTrimming.CharacterEllipsis>.<br /><br /> Use <xref:System.Windows.TextTrimming.WordEllipsis> para obtener DT_END_ELLIPSIS de Win32 con DT_WORD_ELIPSIS puntos suspensivos finales; en este caso, los puntos suspensivos de carácter solo se producen en palabras que no caben en una sola línea.|  
|DT_EXPAND_TABS|Ninguno|No requerido. Las tabulaciones se expanden automáticamente a cada 4 ems, que es, aproximadamente, el ancho de 8 caracteres independientes del lenguaje.|  
|DT_EXTERNALLEADING|Ninguno|No requerido. El espacio externo siempre se incluye en el interlineado. Use la propiedad <xref:System.Windows.Media.FormattedText.LineHeight%2A> para crear el espaciado de línea definido por el usuario.|  
|DT_HIDEPREFIX|Ninguno|No se admite. Quite ' & ' de la cadena antes de construir el objeto <xref:System.Windows.Media.FormattedText>.|  
|DT_LEFT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Esta es la alineación del texto predeterminada. Use la propiedad <xref:System.Windows.Media.FormattedText.TextAlignment%2A> con el valor establecido en <xref:System.Windows.TextAlignment.Left>. (sólo WPF)|  
|DT_MODIFYSTRING|Ninguno|No se admite.|  
|DT_NOCLIP|<xref:System.Windows.Media.Visual.VisualClip%2A>|El recorte no se realiza automáticamente. Si desea recortar el texto, use la propiedad <xref:System.Windows.Media.Visual.VisualClip%2A>.|  
|DT_NOFULLWIDTHCHARBREAK|Ninguno|No se admite.|  
|DT_NOPREFIX|Ninguno|No requerido. El carácter '&' en las cadenas siempre se trata como un carácter normal.|  
|DT_PATHELLIPSIS|Ninguno|Use la propiedad <xref:System.Windows.Media.FormattedText.Trimming%2A> con el valor <xref:System.Windows.TextTrimming.WordEllipsis>.|  
|DT_PREFIX|Ninguno|No se admite. Si desea utilizar el carácter de subrayado para el texto, como una tecla de aceleración o un vínculo, use el método <xref:System.Windows.Media.FormattedText.SetTextDecorations%2A>.|  
|DT_PREFIXONLY|Ninguno|No se admite.|  
|DT_RIGHT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Use la propiedad <xref:System.Windows.Media.FormattedText.TextAlignment%2A> con el valor establecido en <xref:System.Windows.TextAlignment.Right>. (sólo WPF)|  
|DT_RTLREADING|<xref:System.Windows.Media.FormattedText.FlowDirection%2A>|Establezca la propiedad <xref:System.Windows.Media.FormattedText.FlowDirection%2A> en <xref:System.Windows.FlowDirection.RightToLeft>.|  
|DT_SINGLELINE|Ninguno|No requerido. <xref:System.Windows.Media.FormattedText> objetos se comportan como un control de línea única, a menos que se establezca la propiedad <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> o que el texto contenga un retorno de carro/avance de línea (CR/LF).|  
|DT_TABSTOP|Ninguno|No se admite para las posiciones de tabulación definidas por el usuario.|  
|DT_TOP|<xref:System.Windows.Media.FormattedText.Height%2A>|No requerido. La justificación superior es el valor predeterminado. Otros valores de posición vertical se pueden definir utilizando la propiedad <xref:System.Windows.Media.FormattedText.Height%2A> para calcular una posición adecuada de Win32 DrawText ' y '.|  
|DT_VCENTER|<xref:System.Windows.Media.FormattedText.Height%2A>|Utilice la propiedad <xref:System.Windows.Media.FormattedText.Height%2A> para calcular una posición adecuada de Win32 DrawText ' y '.|  
|DT_WORDBREAK|Ninguno|No requerido. La separación de palabras se produce automáticamente con objetos <xref:System.Windows.Media.FormattedText>. No se puede deshabilitar.|  
|DT_WORD_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Use la propiedad <xref:System.Windows.Media.FormattedText.Trimming%2A> con el valor <xref:System.Windows.TextTrimming.WordEllipsis>.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.FormattedText>
- [Documentos en WPF](documents-in-wpf.md)
- [Tipografía en WPF](typography-in-wpf.md)
- [Crear texto con contorno](how-to-create-outlined-text.md)
- [How to: Create a PathGeometry Animation for Text](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100)) (Cómo: Crear una animación PathGeometry para texto).
