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
ms.openlocfilehash: 1e82795afbdd5b1b0a05f95600ebdb92fc134b7d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186561"
---
# <a name="drawing-formatted-text"></a>Dibujar texto con formato
En este tema se proporciona <xref:System.Windows.Media.FormattedText> información general sobre las características del objeto. Este objeto proporciona control de nivel bajo para dibujar texto en aplicaciones [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  

## <a name="technology-overview"></a>Información general sobre la tecnología  
 El <xref:System.Windows.Media.FormattedText> objeto permite dibujar texto de varias líneas, en el que cada carácter del texto se puede formatear individualmente. En el ejemplo siguiente se muestra texto al que se le aplicaron varios formatos.  
  
 ![Texto mostrado mediante un objeto FormattedText](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)  
  
> [!NOTE]
> Para los desarrolladores que migran desde la API de Win32, la tabla de la sección [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]Migración de [Win32](#win32_migration) enumera los indicadores DrawText de Win32 y el equivalente aproximado en .  
  
### <a name="reasons-for-using-formatted-text"></a>Razones para utilizar el texto con formato  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye varios controles para dibujar texto en la pantalla. Cada control se destina a un escenario diferente y tiene su propia lista de características y limitaciones. En general, <xref:System.Windows.Controls.TextBlock> el elemento debe utilizarse cuando se requiere compatibilidad [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]limitada con texto, como una breve frase en un archivo . <xref:System.Windows.Controls.Label>se puede utilizar cuando se requiere un soporte de texto mínimo. Para obtener más información, vea [Documentos en WPF](documents-in-wpf.md).  
  
 El <xref:System.Windows.Media.FormattedText> objeto proporciona mayores [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] características de formato de texto que los controles de texto y puede ser útil en los casos en los que desea utilizar texto como elemento decorativo. Para obtener más información, consulte la sección siguiente [Convertir texto con formato en una geometría](#converting_formatted_text).  
  
 Además, <xref:System.Windows.Media.FormattedText> el objeto es útil <xref:System.Windows.Media.DrawingVisual>para crear objetos derivados orientados al texto. <xref:System.Windows.Media.DrawingVisual>es una clase de dibujo ligera que se utiliza para representar formas, imágenes o texto. Para obtener más información, consulte [Hit Test Using DrawingVisuals Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual).  
  
## <a name="using-the-formattedtext-object"></a>Utilizar el objeto FormattedText  
 Para crear texto con <xref:System.Windows.Media.FormattedText.%23ctor%2A> formato, llame <xref:System.Windows.Media.FormattedText> al constructor para crear un objeto. Una vez que haya creado la cadena inicial de texto con formato, podrá aplicar una gama de estilos de formato.  
  
 Utilice <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> la propiedad para restringir el texto a un ancho específico. El texto se ajustará automáticamente para evitar superar el ancho especificado. Utilice <xref:System.Windows.Media.FormattedText.MaxTextHeight%2A> la propiedad para restringir el texto a una altura específica. El texto mostrará puntos suspensivos ("...") para el texto que supere el alto especificado.  
  
 ![Texto mostrado con textwrap y puntos suspensivos.](./media/drawing-formatted-text/formatted-text-wordwrap-ellipsis.png)
  
 Puede aplicar varios estilos de formato a uno o más caracteres. Por ejemplo, podría llamar <xref:System.Windows.Media.FormattedText.SetFontSize%2A> <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> a los métodos y y para cambiar el formato de los primeros cinco caracteres del texto.  
  
 En el ejemplo <xref:System.Windows.Media.FormattedText> de código siguiente se crea un objeto y, a continuación, se aplican varios estilos de formato al texto.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
### <a name="font-size-unit-of-measure"></a>Unidad de medida del tamaño de fuente  
 Al igual que [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] con otros <xref:System.Windows.Media.FormattedText> objetos de texto en aplicaciones, el objeto utiliza píxeles independientes del dispositivo como unidad de medida. Sin embargo, la mayoría de las aplicaciones Win32 utilizan puntos como unidad de medida. Si desea utilizar el texto de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] visualización en unidades de puntos en las aplicaciones, debe convertir las unidades independientes del dispositivo (1/96 de pulgada por unidad) en puntos. En el ejemplo de código siguiente se muestra cómo realizar esta conversión.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets2)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets2)]  
  
<a name="converting_formatted_text"></a>
### <a name="converting-formatted-text-to-a-geometry"></a>Convertir texto con formato a una geometría  
 Puede convertir texto con <xref:System.Windows.Media.Geometry> formato en objetos, lo que le permite crear otros tipos de texto visualmente interesante. Por ejemplo, podría <xref:System.Windows.Media.Geometry> crear un objeto basado en el contorno de una cadena de texto.  
  
 ![Esquema de texto que usa un pincel de degradado lineal](./media/typography-in-wpf/text-outline-linear-gradient.jpg)
  
 En los ejemplos siguientes se muestran varias maneras de crear efectos visuales interesantes modificando el trazo, el relleno y el resaltado del texto convertido.  
  
 ![Texto con colores diferentes para relleno y trazo](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Texto con pincel de imagen aplicado a trazo](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Texto con pincel de imagen aplicado al trazo y resaltado](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Cuando el texto <xref:System.Windows.Media.Geometry> se convierte en un objeto, ya no es una colección de caracteres: no se pueden modificar los caracteres de la cadena de texto. Sin embargo, puede afectar a la apariencia del texto convertido modificando sus propiedades de trazo y relleno. El trazo se refiere al contorno del texto convertido; el relleno es el área dentro del contorno del texto convertido. Para obtener más información, consulte [Crear texto con contorno](how-to-create-outlined-text.md).  
  
 También puede convertir texto con <xref:System.Windows.Media.PathGeometry> formato en un objeto y utilizar el objeto para resaltar el texto. Por ejemplo, podría aplicar una <xref:System.Windows.Media.PathGeometry> animación al objeto para que la animación siga el contorno del texto con formato.  
  
 En el ejemplo siguiente se muestra el <xref:System.Windows.Media.PathGeometry> texto con formato que se ha convertido en un objeto. Una elipse animada sigue la ruta de los trazos del texto representado.  
  
 ![Esfera que sigue la geometría de trayecto de texto](./media/drawing-formatted-text/sphere-following-geometry-path.gif)  
Esfera que sigue la geometría de trayecto de texto  
  
 Para obtener más información, consulte [How to: Create a PathGeometry Animation for Text](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100)) (Cómo: Crear una animación PathGeometry para texto).  
  
 Puede crear otros usos interesantes para el texto <xref:System.Windows.Media.PathGeometry> con formato una vez que se ha convertido en un objeto. Por ejemplo, puede recortar vídeo para que se muestre dentro de él.  
  
 ![Vídeo mostrándose en la geometría de trayecto de texto](./media/drawing-formatted-text/video-displaying-text-path-geometry.png)
  
<a name="win32_migration"></a>
## <a name="win32-migration"></a>Migración de Win32  
 Las características <xref:System.Windows.Media.FormattedText> del texto de dibujo son similares a las características de la función DrawText de Win32. Para los desarrolladores que migran desde la API de Win32, en la [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]tabla siguiente se enumeran los indicadores DrawText de Win32 y el equivalente aproximado en .  
  
|Marca DrawText|Equivalente de WPF|Notas|  
|-------------------|--------------------|-----------|  
|DT_BOTTOM|<xref:System.Windows.Media.FormattedText.Height%2A>|Utilice <xref:System.Windows.Media.FormattedText.Height%2A> la propiedad para calcular una posición 'y' de Win32 DrawText adecuada.|  
|DT_CALCRECT|<xref:System.Windows.Media.FormattedText.Height%2A>, <xref:System.Windows.Media.FormattedText.Width%2A>|Utilice <xref:System.Windows.Media.FormattedText.Height%2A> las <xref:System.Windows.Media.FormattedText.Width%2A> propiedades y para calcular el rectángulo de salida.|  
|DT_CENTER|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Utilice <xref:System.Windows.Media.FormattedText.TextAlignment%2A> la propiedad con <xref:System.Windows.TextAlignment.Center>el valor establecido en .|  
|DT_EDITCONTROL|None|No se requiere. El ancho del espacio y la representación de la última línea son los mismos que en el control de edición de marcos.|  
|DT_END_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Utilice <xref:System.Windows.Media.FormattedText.Trimming%2A> la propiedad <xref:System.Windows.TextTrimming.CharacterEllipsis>con el valor .<br /><br /> Se <xref:System.Windows.TextTrimming.WordEllipsis> usa para obtener DT_END_ELLIPSIS Win32 con puntos suspensivos finales DT_WORD_ELIPSIS: en este caso, los puntos suspensivos de caracteres solo se producen en palabras que no caben en una sola línea.|  
|DT_EXPAND_TABS|None|No se requiere. Las tabulaciones se expanden automáticamente a cada 4 ems, que es, aproximadamente, el ancho de 8 caracteres independientes del lenguaje.|  
|DT_EXTERNALLEADING|None|No se requiere. El espacio externo siempre se incluye en el interlineado. Utilice <xref:System.Windows.Media.FormattedText.LineHeight%2A> la propiedad para crear un interlineado definido por el usuario.|  
|DT_HIDEPREFIX|None|No compatible. Quite el '&' de la <xref:System.Windows.Media.FormattedText> cadena antes de construir el objeto.|  
|DT_LEFT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Esta es la alineación del texto predeterminada. Utilice <xref:System.Windows.Media.FormattedText.TextAlignment%2A> la propiedad con <xref:System.Windows.TextAlignment.Left>el valor establecido en . (Solo WPF)|  
|DT_MODIFYSTRING|None|No compatible.|  
|DT_NOCLIP|<xref:System.Windows.Media.Visual.VisualClip%2A>|El recorte no se realiza automáticamente. Si desea recortar texto, <xref:System.Windows.Media.Visual.VisualClip%2A> utilice la propiedad.|  
|DT_NOFULLWIDTHCHARBREAK|None|No compatible.|  
|DT_NOPREFIX|None|No se requiere. El carácter '&' en las cadenas siempre se trata como un carácter normal.|  
|DT_PATHELLIPSIS|None|Utilice <xref:System.Windows.Media.FormattedText.Trimming%2A> la propiedad <xref:System.Windows.TextTrimming.WordEllipsis>con el valor .|  
|DT_PREFIX|None|No compatible. Si desea utilizar guiones bajos para el texto, como <xref:System.Windows.Media.FormattedText.SetTextDecorations%2A> una clave de acelerador o un vínculo, utilice el método.|  
|DT_PREFIXONLY|None|No compatible.|  
|DT_RIGHT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Utilice <xref:System.Windows.Media.FormattedText.TextAlignment%2A> la propiedad con <xref:System.Windows.TextAlignment.Right>el valor establecido en . (Solo WPF)|  
|DT_RTLREADING|<xref:System.Windows.Media.FormattedText.FlowDirection%2A>|Establezca la propiedad <xref:System.Windows.Media.FormattedText.FlowDirection%2A> en <xref:System.Windows.FlowDirection.RightToLeft>.|  
|DT_SINGLELINE|None|No se requiere. <xref:System.Windows.Media.FormattedText>los objetos se comportan como un <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> control de línea única, a menos que se establezca la propiedad o el texto contenga un retorno de carro/alimentación de línea (CR/LF).|  
|DT_TABSTOP|None|No se admite para las posiciones de tabulación definidas por el usuario.|  
|DT_TOP|<xref:System.Windows.Media.FormattedText.Height%2A>|No se requiere. La justificación superior es el valor predeterminado. Otros valores de posicionamiento vertical <xref:System.Windows.Media.FormattedText.Height%2A> se pueden definir mediante la propiedad para calcular una posición 'y' de Win32 DrawText adecuada.|  
|DT_VCENTER|<xref:System.Windows.Media.FormattedText.Height%2A>|Utilice <xref:System.Windows.Media.FormattedText.Height%2A> la propiedad para calcular una posición 'y' de Win32 DrawText adecuada.|  
|DT_WORDBREAK|None|No se requiere. La ruptura de <xref:System.Windows.Media.FormattedText> palabras ocurre automáticamente con los objetos. No se puede deshabilitar.|  
|DT_WORD_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Utilice <xref:System.Windows.Media.FormattedText.Trimming%2A> la propiedad <xref:System.Windows.TextTrimming.WordEllipsis>con el valor .|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.FormattedText>
- [Documentos en WPF](documents-in-wpf.md)
- [Tipografía en WPF](typography-in-wpf.md)
- [Crear texto con contorno](how-to-create-outlined-text.md)
- [How to: Create a PathGeometry Animation for Text](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100)) (Cómo: Crear una animación PathGeometry para texto).
