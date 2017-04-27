---
title: "Dibujar texto con formato | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "dibujar, texto con formato"
  - "texto con formato [WPF]"
  - "texto [WPF]"
  - "tipografía, dibujar texto con formato"
ms.assetid: b1d851c1-331c-4814-9964-6fe769db6f1f
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Dibujar texto con formato
En este tema se proporciona información general sobre las características del objeto <xref:System.Windows.Media.FormattedText>.  Este objeto proporciona control de bajo nivel para dibujar texto en aplicaciones de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
   
  
<a name="technology_overview"></a>   
## Información general sobre la tecnología  
 El objeto <xref:System.Windows.Media.FormattedText> permite dibujar texto con varias líneas, en el que se puede dar formato a cada carácter individualmente.  En el ejemplo siguiente se muestra texto con varios formatos.  
  
 ![Texto mostrado mediante un objeto FormattedText](../../../../docs/framework/wpf/advanced/media/formattedtext01.png "FormattedText01")  
Texto mostrado mediante el método FormattedText  
  
> [!NOTE]
>  Para los programadores que migran desde API de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], la tabla de la sección [Migración de Win32](#win32_migration) enumera los marcadores DrawText de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] y el equivalente aproximado en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
### Razones para utilizar el texto con formato  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye varios controles para dibujar texto en la pantalla.  Cada control se destina a un escenario diferente y tiene su propia lista de características y limitaciones.  En general, el elemento <xref:System.Windows.Controls.TextBlock> se debe usar cuando se necesita una compatibilidad de texto limitada, como una frase breve en una [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  <xref:System.Windows.Controls.Label> se puede usar cuando se necesita una compatibilidad de texto mínima.  Para obtener más información, vea [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
 El objeto <xref:System.Windows.Media.FormattedText> proporciona características de formato de texto más importantes que los controles de texto de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], y puede ser útil en caso de que se desee utilizar texto como elemento decorativo. Para obtener más información, vea la siguiente sección [Convertir el texto con formato en una geometría](#converting_formatted_text).  
  
 Además, el objeto <xref:System.Windows.Media.FormattedText> es útil para crear objetos orientados a texto derivados de <xref:System.Windows.Media.DrawingVisual>.  <xref:System.Windows.Media.DrawingVisual> es una clase de dibujo ligera que se utiliza para representar formas, imágenes o texto.  Para obtener más información, vea [Hit Test Using DrawingVisuals Sample](http://go.microsoft.com/fwlink/?LinkID=159994).  
  
<a name="using_the_formattedtext_object"></a>   
## Utilizar el objeto FormattedText  
 Para crear texto con formato, llame al constructor <xref:System.Windows.Media.FormattedText.%23ctor%2A> para crear un objeto <xref:System.Windows.Media.FormattedText>.  Una vez creada la cadena de texto con formato inicial, puede aplicarle varios estilos de formato.  
  
 Utilice la propiedad <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> para restringir el texto a un ancho específico.  El texto se ajustará automáticamente para evitar superar el ancho especificado.  Utilice la propiedad <xref:System.Windows.Media.FormattedText.MaxTextHeight%2A> para restringir el texto a un alto específico.  El texto mostrará puntos suspensivos, "…". para el texto que supera el alto especificado.  
  
 ![Texto mostrado mediante un objeto FormattedText](../../../../docs/framework/wpf/advanced/media/formattedtext02.png "FormattedText02")  
Texto mostrado al que se ha aplicado el ajuste de línea y los puntos suspensivos  
  
 Puede aplicar varios estilos de formato a uno o más caracteres.  Por ejemplo, podría llamar a los métodos <xref:System.Windows.Media.FormattedText.SetFontSize%2A> y <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> para cambiar el formato de los cinco primeros caracteres del texto.  
  
 En el ejemplo de código siguiente se crea un objeto <xref:System.Windows.Media.FormattedText> y, a continuación, se aplican varios estilos de formato al texto.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
### Unidad de medida del tamaño de fuente  
 Como sucede con otros objetos de texto en las aplicaciones de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], el objeto <xref:System.Windows.Media.FormattedText> utiliza los píxeles independientes del dispositivo como unidad de medida.  Sin embargo, la mayoría de las aplicaciones de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] utilizan los puntos como unidad de medida.  Si desea utilizar el texto visualizado en unidades de puntos en las aplicaciones [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], es preciso convertir los [!INCLUDE[TLA#tla_dipixel#plural](../../../../includes/tlasharptla-dipixelsharpplural-md.md)] en puntos.  En el ejemplo de código siguiente se muestra cómo realizar esta conversión.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets2)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets2)]  
  
<a name="converting_formatted_text"></a>   
### Convertir el texto con formato en una geometría  
 Puede convertir el texto con formato en objetos <xref:System.Windows.Media.Geometry>, lo que permite crear otros tipos de texto visualmente interesante.  Por ejemplo, podría crear un objeto <xref:System.Windows.Media.Geometry> basado en el contorno de una cadena de texto.  
  
 ![Esquema de texto que usa un pincel de degradado lineal](../../../../docs/framework/wpf/advanced/media/outlinedtext02.png "OutlinedText02")  
Aplicación de un contorno al texto mediante un pincel de degradado lineal  
  
 En los ejemplos siguientes se muestran varias maneras de crear efectos visuales interesantes modificando el trazo, el relleno y el resaltado del texto convertido.  
  
 ![Texto con colores diferentes para relleno y trazo](../../../../docs/framework/wpf/advanced/media/outlinedtext03.png "OutlinedText03")  
Ejemplo de cómo establecer el trazo y el relleno en diferentes colores  
  
 ![Texto con pincel de imagen aplicado a trazo](../../../../docs/framework/wpf/advanced/media/outlinedtext04.png "OutlinedText04")  
Ejemplo de un pincel de imagen aplicado al trazo  
  
 ![Texto con pincel de imagen aplicado a trazo](../../../../docs/framework/wpf/advanced/media/outlinedtext05.png "OutlinedText05")  
Ejemplo de un pincel de imagen aplicado al trazo y al resaltado  
  
 Cuando se convierte el texto en un objeto <xref:System.Windows.Media.Geometry>, deja de ser una colección de caracteres; no se pueden modificar los caracteres de la cadena de texto.  Sin embargo, se puede cambiar la apariencia del texto convertido modificando sus propiedades de trazo y relleno.  El trazo se refiere al contorno del texto convertido; el relleno se refiere al área situada dentro del contorno del texto convertido.  Para obtener más información, vea [Crear texto con contorno](../../../../docs/framework/wpf/advanced/how-to-create-outlined-text.md).  
  
 También puede convertir el texto con formato en un objeto <xref:System.Windows.Media.PathGeometry> y utiliza el objeto para resaltar el texto.  Por ejemplo, puede aplicar una animación al objeto <xref:System.Windows.Media.PathGeometry> para que la animación siga el contorno del texto con formato.  
  
 En el ejemplo siguiente se muestra texto con formato convertido en un objeto <xref:System.Windows.Media.PathGeometry>.  Una elipse animada sigue el trazado de los trazos del texto representado.  
  
 ![Esfera que sigue la geometría de trayecto de texto](../../../../docs/framework/wpf/advanced/media/textpathgeometry01.png "TextPathGeometry01")  
Esfera que sigue la geometría de trazado del texto  
  
 Para obtener más información, vea [How to: Create a PathGeometry Animation for Text](http://msdn.microsoft.com/es-es/29f8051e-798a-463f-a926-a099a99e9c67).  
  
 Puede crear otros usos interesantes para el texto con formato una vez convertido en un objeto <xref:System.Windows.Media.PathGeometry>.  Por ejemplo, puede mostrar en él un clip de vídeo.  
  
 ![Vídeo mostrándose en la geometría de trayecto de texto](../../../../docs/framework/wpf/advanced/media/videotextdemo01.png "VideoTextDemo01")  
Vídeo mostrado en la geometría de trazado del texto  
  
<a name="win32_migration"></a>   
## Migración de Win32  
 Las características de <xref:System.Windows.Media.FormattedText> para dibujar texto son similares a las de la función DrawText de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)].  Para los programadores que migran desde la API de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], se enumeran en la tabla siguiente los marcadores de DrawText de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] y su equivalente aproximado en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
|Marcador de DrawText|Equivalente de WPF|Notas|  
|--------------------------|------------------------|-----------|  
|DT\_BOTTOM|<xref:System.Windows.Media.FormattedText.Height%2A>|Utilice la propiedad <xref:System.Windows.Media.FormattedText.Height%2A> para calcular la posición de 'y' correcta de DrawText de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)].|  
|DT\_CALCRECT|<xref:System.Windows.Media.FormattedText.Height%2A>, <xref:System.Windows.Media.FormattedText.Width%2A>|Utilice las propiedades <xref:System.Windows.Media.FormattedText.Height%2A> y <xref:System.Windows.Media.FormattedText.Width%2A> para calcular el rectángulo de salida.|  
|DT\_CENTER|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Utilice la propiedad <xref:System.Windows.Media.FormattedText.TextAlignment%2A> con el valor establecido en <xref:System.Windows.TextAlignment>.|  
|DT\_EDITCONTROL|None|No se necesita.  El ancho del espacio y la representación de la última línea son iguales que en el control de edición del marco de trabajo.|  
|DT\_END\_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Utilice la propiedad <xref:System.Windows.Media.FormattedText.Trimming%2A> con el valor <xref:System.Windows.TextTrimming>.<br /><br /> Utilice <xref:System.Windows.TextTrimming> para obtener DT\_END\_ELLIPSIS de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] con los puntos suspensivos finales de DT\_WORD\_ELIPSIS; en este caso, los puntos suspensivos sólo se muestran en las palabras que no caben en una sola línea.|  
|DT\_EXPAND\_TABS|None|No se necesita.  Las tabulaciones se expanden automáticamente a cada 4 ems, que es aproximadamente el ancho de 8 caracteres independientes del lenguaje.|  
|DT\_EXTERNALLEADING|None|No se necesita.  El espacio externo siempre se incluye en el interlineado.  Utilice la propiedad <xref:System.Windows.Media.FormattedText.LineHeight%2A> para crear el interlineado definido por el usuario.|  
|DT\_HIDEPREFIX|None|No se admite.  Quite el signo '&' de la cadena antes de construir el objeto <xref:System.Windows.Media.FormattedText>.|  
|DT\_LEFT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Ésta es la alineación predeterminada del texto.  Utilice la propiedad <xref:System.Windows.Media.FormattedText.TextAlignment%2A> con el valor establecido en <xref:System.Windows.TextAlignment>.  \(Sólo WPF\)|  
|DT\_MODIFYSTRING|None|No se admite.|  
|DT\_NOCLIP|<xref:System.Windows.Media.Visual.VisualClip%2A>|El recorte no se realiza automáticamente.  Si desea recortar texto, utilice la propiedad <xref:System.Windows.Media.Visual.VisualClip%2A>.|  
|DT\_NOFULLWIDTHCHARBREAK|None|No se admite.|  
|DT\_NOPREFIX|None|No se necesita.  El carácter '&' en las cadenas se trata siempre como un carácter normal.|  
|DT\_PATHELLIPSIS|None|Utilice la propiedad <xref:System.Windows.Media.FormattedText.Trimming%2A> con el valor <xref:System.Windows.TextTrimming>.|  
|DT\_PREFIX|None|No se admite.  Si desea utilizar el subrayado para el texto, como en una tecla de aceleración o vínculo, utilice el método <xref:System.Windows.Media.FormattedText.SetTextDecorations%2A>.|  
|DT\_PREFIXONLY|None|No se admite.|  
|DT\_RIGHT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Utilice la propiedad <xref:System.Windows.Media.FormattedText.TextAlignment%2A> con el valor establecido en <xref:System.Windows.TextAlignment>.  \(Sólo WPF\)|  
|DT\_RTLREADING|<xref:System.Windows.Media.FormattedText.FlowDirection%2A>|Establezca la propiedad <xref:System.Windows.Media.FormattedText.FlowDirection%2A> en <xref:System.Windows.FlowDirection>.|  
|DT\_SINGLELINE|None|No se necesita.  Los objetos <xref:System.Windows.Media.FormattedText> se comportan como un control de una sola línea, a menos que se establezca la propiedad <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> o que el texto contenga un retorno de carro o salto de línea.|  
|DT\_TABSTOP|None|No se admiten las posiciones de tabulación definidas por el usuario.|  
|DT\_TOP|<xref:System.Windows.Media.FormattedText.Height%2A>|No se necesita.  La justificación superior es la predeterminada.  Se pueden definir otros valores de posición vertical utilizando la propiedad <xref:System.Windows.Media.FormattedText.Height%2A> para calcular la posición apropiada de 'y' en un DrawText de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)].|  
|DT\_VCENTER|<xref:System.Windows.Media.FormattedText.Height%2A>|Utilice la propiedad <xref:System.Windows.Media.FormattedText.Height%2A> para calcular la posición de 'y' correcta de DrawText de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)].|  
|DT\_WORDBREAK|None|No se necesita.  La ruptura de palabras se efectúa automáticamente en los objetos <xref:System.Windows.Media.FormattedText>.  No se puede deshabilitar.|  
|DT\_WORD\_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Utilice la propiedad <xref:System.Windows.Media.FormattedText.Trimming%2A> con el valor <xref:System.Windows.TextTrimming>.|  
  
## Vea también  
 <xref:System.Windows.Media.FormattedText>   
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Tipografía en WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)   
 [Crear texto con contorno](../../../../docs/framework/wpf/advanced/how-to-create-outlined-text.md)   
 [How to: Create a PathGeometry Animation for Text](http://msdn.microsoft.com/es-es/29f8051e-798a-463f-a926-a099a99e9c67)