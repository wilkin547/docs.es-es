---
title: "Asignaci&#243;n de propiedades en formularios Windows Forms y WPF | Microsoft Docs"
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
  - "interoperabilidad [WPF], Windows Forms"
  - "asignación de propiedades [interoperabilidad con WPF]"
  - "formularios Windows Forms [WPF], interoperabilidad con"
  - "Windows Forms, interoperabilidad con WPF"
  - "asignación de propiedades del elemento WindowsFormsHost"
ms.assetid: 999d8298-9c04-467d-a453-86e41002057d
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Asignaci&#243;n de propiedades en formularios Windows Forms y WPF
Las tecnologías de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tienen dos modelos de propiedades similares pero diferentes.  La *asignación de propiedades* admite la interoperabilidad entre las dos arquitecturas y proporciona las funciones siguientes:  
  
-   Facilita la asignación de los cambios de las propiedades pertinentes en el entorno del host al control o elemento hospedado.  
  
-   Proporciona el control predeterminado para asignar las propiedades más utilizadas.  
  
-   Facilita la eliminación, invalidación o extensión de las propiedades predeterminadas.  
  
-   Permite asegurarse de que los cambios de los valores de propiedad en el host se detecten y traduzcan automáticamente al control o elemento hospedado.  
  
> [!NOTE]
>  Los eventos de cambio de propiedad no se propagan en sentido ascendente por la jerarquía del control o elemento de hospedaje.  La conversión de propiedades no se efectúa si el valor local de una propiedad no cambia por la existencia de mecanismos que modifican el valor de la propiedad, tales como establecimiento directo, estilos, herencia, enlaces de datos u otros.  
  
 Utilice la propiedad <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> y la propiedad <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> del control <xref:System.Windows.Forms.Integration.ElementHost> para tener acceso a la asignación de propiedades.  
  
## Asignación de propiedades con el elemento WindowsFormsHost  
 El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> convierte las propiedades predeterminadas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en sus equivalentes en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] utilizando la tabla de conversión siguiente.  
  
|Hospedaje de Windows Presentation Foundation|Windows Forms|Comportamiento de interoperación|  
|--------------------------------------------------|-------------------|--------------------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> \(<xref:System.Windows.Media.Brush?displayProperty=fullName>\)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> \(<xref:System.Drawing.Color?displayProperty=fullName>\)|El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> establece las propiedades <xref:System.Windows.Forms.Control.BackColor%2A> y <xref:System.Windows.Forms.Control.BackgroundImage%2A> del control hospedado.  La asignación se efectúa mediante las reglas siguientes:<br /><br /> -   Si <xref:System.Windows.Controls.Control.Background%2A> es un color sólido, se convierte y utiliza para establecer la propiedad <xref:System.Windows.Forms.Control.BackColor%2A> del control hospedado.  La propiedad <xref:System.Windows.Forms.Control.BackColor%2A> no se establece en el control hospedado, porque el control hospedado puede heredar el valor de la propiedad <xref:System.Windows.Forms.Control.BackColor%2A>. **Note:**  El control hospedado no admite la transparencia.  Todos los colores que se asignen a <xref:System.Windows.Forms.Control.BackColor%2A> deberán ser totalmente opacos, con un valor de alfa de 0xFF. <br /><br /> -   Si <xref:System.Windows.Controls.Control.Background%2A> no es un color sólido, el control <xref:System.Windows.Forms.Integration.WindowsFormsHost> crea un mapa de bits a partir de la propiedad <xref:System.Windows.Controls.Control.Background%2A>.  El control <xref:System.Windows.Forms.Integration.WindowsFormsHost> asigna este mapa de bits a la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A> del control hospedado.  Esto proporciona un efecto que es similar a la transparencia. **Note:**  Puede invalidar este comportamiento o quitar la asignación de la propiedad <xref:System.Windows.Controls.Control.Background%2A>.|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|Si no se ha reasignado la asignación predeterminada, el control <xref:System.Windows.Forms.Integration.WindowsFormsHost> recorre su jerarquía de antecesores hasta que encuentra uno cuya propiedad <xref:System.Windows.FrameworkElement.Cursor%2A> está establecida.  Este valor se convierte en el cursor de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] correspondiente más cercano.<br /><br /> Si no se ha reasignado la asignación predeterminada para la propiedad <xref:System.Windows.FrameworkElement.ForceCursor%2A>, el recorrido se detiene en el primer antecesor cuya propiedad <xref:System.Windows.FrameworkElement.ForceCursor%2A> está establecida en `true`.|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> \(<xref:System.Windows.FlowDirection?displayProperty=fullName>\)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> \(<xref:System.Windows.Forms.RightToLeft?displayProperty=fullName>\)|<xref:System.Windows.FlowDirection> se asigna a <xref:System.Windows.Forms.RightToLeft>.<br /><br /> <xref:System.Windows.FlowDirection> se asigna a <xref:System.Windows.Forms.RightToLeft>.<br /><br /> <xref:System.Windows.Forms.RightToLeft> no se asigna.<br /><br /> <xref:System.Windows.FlowDirection?displayProperty=fullName> se asigna a <xref:System.Windows.Forms.RightToLeft?displayProperty=fullName>.|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|Propiedad <xref:System.Drawing.Font.Style%2A> del objeto <xref:System.Drawing.Font?displayProperty=fullName> del control hospedado.|El conjunto de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se convierte a la <xref:System.Drawing.Font> correspondiente.  Cuando alguna de estas propiedades cambia, se crea una nueva <xref:System.Drawing.Font>.  Para <xref:System.Windows.FontStyles.Normal%2A>: <xref:System.Drawing.FontStyle> está deshabilitado.  Para <xref:System.Windows.FontStyles.Italic%2A> o <xref:System.Windows.FontStyles.Oblique%2A>: <xref:System.Drawing.FontStyle> está habilitado.|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|Propiedad <xref:System.Drawing.Font.Style%2A> del objeto <xref:System.Drawing.Font?displayProperty=fullName> del control hospedado.|El conjunto de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se convierte a la <xref:System.Drawing.Font> correspondiente.  Cuando alguna de estas propiedades cambia, se crea una nueva <xref:System.Drawing.Font>.  Para <xref:System.Windows.FontWeights.Black%2A>, <xref:System.Windows.FontWeights.Bold%2A>, <xref:System.Windows.FontWeights.DemiBold%2A>, <xref:System.Windows.FontWeights.ExtraBold%2A>, <xref:System.Windows.FontWeights.Heavy%2A>, <xref:System.Windows.FontWeights.Medium%2A>, <xref:System.Windows.FontWeights.SemiBold%2A> o <xref:System.Windows.FontWeights.UltraBold%2A>: <xref:System.Drawing.FontStyle> está habilitado.  Para <xref:System.Windows.FontWeights.ExtraLight%2A>, <xref:System.Windows.FontWeights.Light%2A>, <xref:System.Windows.FontWeights.Normal%2A>, <xref:System.Windows.FontWeights.Regular%2A>, <xref:System.Windows.FontWeights.Thin%2A> o <xref:System.Windows.FontWeights.UltraLight%2A>: <xref:System.Drawing.FontStyle> está deshabilitado.|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> \(<xref:System.Drawing.Font?displayProperty=fullName>\)|El conjunto de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se convierte a la <xref:System.Drawing.Font> correspondiente.  Cuando alguna de estas propiedades cambia, se crea una nueva <xref:System.Drawing.Font>.  El tamaño del control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado cambia dependiendo del tamaño de fuente.<br /><br /> En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], el tamaño de fuente se expresa en noventa y seisavos de pulgada; mientras que en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] se expresa en setenta y dosavos de pulgada.  La conversión correspondiente es:<br /><br /> Tamaño de fuente en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] \= tamaño de fuente en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] \* 72,0 \/ 96,0.|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> \(<xref:System.Windows.Media.Brush?displayProperty=fullName>\)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> \(<xref:System.Drawing.Color?displayProperty=fullName>\)|La asignación de la propiedad <xref:System.Windows.Controls.Control.Foreground%2A> se realiza utilizando las reglas siguientes:<br /><br /> -   Si <xref:System.Windows.Controls.Control.Foreground%2A> es un <xref:System.Windows.Media.SolidColorBrush>, se utiliza <xref:System.Windows.Media.SolidColorBrush.Color%2A> para <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />-   Si <xref:System.Windows.Controls.Control.Foreground%2A> es un <xref:System.Windows.Media.GradientBrush>, se utiliza el color de <xref:System.Windows.Media.GradientStop> con el valor de desplazamiento más bajo para <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />-   Para todos los demás tipos de <xref:System.Windows.Media.Brush>, se deja <xref:System.Windows.Forms.Control.ForeColor%2A> sin cambios.  Esto significa que se utiliza el valor predeterminado.|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|Cuando se establece <xref:System.Windows.UIElement.IsEnabled%2A>, el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> establece la propiedad <xref:System.Windows.Forms.Control.Enabled%2A> del control hospedado.|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|Los cuatro valores de la propiedad <xref:System.Windows.Forms.Control.Padding%2A> en el control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado se establecen en el mismo valor de <xref:System.Windows.Thickness>.<br /><br /> -   Los valores mayores que <xref:System.Int32.MaxValue> se establecen en <xref:System.Int32.MaxValue>.<br />-   Los valores menores que <xref:System.Int32.MinValue> se establecen en <xref:System.Int32.MinValue>.|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility> se asigna a <xref:System.Windows.Forms.Control.Visible%2A> \= `true`.  El control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado está visible.  No se recomienda establecer explícitamente la propiedad <xref:System.Windows.Forms.Control.Visible%2A> del control hospedado en `false`.<br />-   <xref:System.Windows.Visibility> se asigna a <xref:System.Windows.Forms.Control.Visible%2A> \= `true` o `false`.  No se dibuja el control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado y se contrae su área.<br />-   <xref:System.Windows.Visibility>: el control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado ocupa espacio en el diseño, pero no está visible.  En este caso, la propiedad <xref:System.Windows.Forms.Control.Visible%2A> se establece en `true`.  No se recomienda establecer explícitamente la propiedad <xref:System.Windows.Forms.Control.Visible%2A> del control hospedado en `false`.|  
  
 El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> admite plenamente las propiedades asociadas a los elementos contenedor.  
  
 Para obtener más información, consulte [Tutorial: Asignar propiedades mediante el uso del elemento WindowsFormsHost](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-windowsformshost-element.md).  
  
## Actualizaciones de propiedades primarias  
 Al cambiar la mayoría de las propiedades primarias, se producen notificaciones al control secundario hospedado.  En la lista siguiente se describen las propiedades que no dan lugar a notificaciones cuando sus valores cambian.  
  
-   <xref:System.Windows.Controls.Control.Background%2A>  
  
-   <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
-   <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
-   <xref:System.Windows.UIElement.Visibility%2A>  
  
 Por ejemplo, si cambia el valor de la propiedad <xref:System.Windows.Controls.Control.Background%2A> del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, la propiedad <xref:System.Windows.Forms.Control.BackColor%2A> del control hospedado no cambia.  
  
## Asignación de propiedades con el control ElementHost  
 Las propiedades siguientes proporcionan notificación de cambios integrada.  No llame al método <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> cuando asigne estas propiedades:  
  
-   AutoSize  
  
-   BackColor  
  
-   BackgroundImage  
  
-   BackgroundImageLayout  
  
-   BindingContext  
  
-   CausesValidation  
  
-   ContextMenu  
  
-   ContextMenuStrip  
  
-   Cursor  
  
-   Dock  
  
-   Enabled  
  
-   Fuente  
  
-   ForeColor  
  
-   Ubicación  
  
-   Margin  
  
-   Relleno  
  
-   Primario  
  
-   Región  
  
-   RightToLeft  
  
-   Size  
  
-   TabIndex  
  
-   TabStop  
  
-   Text  
  
-   Visible  
  
 El control <xref:System.Windows.Forms.Integration.ElementHost> convierte las propiedades predeterminadas de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] en sus equivalentes en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizando la tabla de conversión siguiente.  
  
 Para obtener más información, consulte [Tutorial: Asignar propiedades mediante el uso del control ElementHost](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-elementhost-control.md).  
  
|Hospedaje de formularios Windows Forms|Windows Presentation Foundation|Comportamiento de interoperación|  
|--------------------------------------------|-------------------------------------|--------------------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> \(<xref:System.Drawing.Color?displayProperty=fullName>\)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> \(<xref:System.Windows.Media.Brush?displayProperty=fullName>\) en el elemento hospedado|Al establecer esta propiedad fuerza a que se vuelva a pintar con <xref:System.Windows.Media.ImageBrush>.  Si la propiedad <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> está establecida en `false` \(el valor predeterminado\), <xref:System.Windows.Media.ImageBrush> se basará en el aspecto del control <xref:System.Windows.Forms.Integration.ElementHost>, incluidas sus propiedades <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>, y en todos los controladores de pintura asociados.<br /><br /> Si la propiedad <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> está establecida en `true`, <xref:System.Windows.Media.ImageBrush> se basa en el aspecto del elemento primario del control <xref:System.Windows.Forms.Integration.ElementHost>, incluidas las propiedades <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> del elemento primario, y en todos los controladores de pintura asociados.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> \(<xref:System.Drawing.Image?displayProperty=fullName>\)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> \(<xref:System.Windows.Media.Brush?displayProperty=fullName>\) en el elemento hospedado|Establecer esta propiedad produce el mismo comportamiento descrito para la asignación de <xref:System.Windows.Forms.Control.BackColor%2A>.|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> \(<xref:System.Windows.Media.Brush?displayProperty=fullName>\) en el elemento hospedado|Establecer esta propiedad produce el mismo comportamiento descrito para la asignación de <xref:System.Windows.Forms.Control.BackColor%2A>.|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> \(<xref:System.Windows.Forms.Cursor?displayProperty=fullName>\)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> \(<xref:System.Windows.Input.Cursor?displayProperty=fullName>\)|El cursor estándar de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] se convierte al cursor estándar correspondiente de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Si el de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no es un cursor estándar, se asigna el valor predeterminado.|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|Cuando se establece <xref:System.Windows.Forms.Control.Enabled%2A>, el control <xref:System.Windows.Forms.Integration.ElementHost> establece la propiedad <xref:System.Windows.UIElement.IsEnabled%2A> del elemento hospedado.|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> \(<xref:System.Drawing.Font?displayProperty=fullName>\)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|El valor de <xref:System.Windows.Forms.Control.Font%2A> se convierte a un conjunto correspondiente de propiedades de fuente de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|  
|<xref:System.Drawing.Font.Bold%2A>|<xref:System.Windows.Controls.Control.FontWeight%2A> en el elemento hospedado|Si el valor de <xref:System.Drawing.Font.Bold%2A> es `true`, el valor de <xref:System.Windows.Controls.Control.FontWeight%2A> se establece en <xref:System.Windows.FontWeights.Bold%2A>.<br /><br /> Si la dirección <xref:System.Drawing.Font.Bold%2A> es `false`, <xref:System.Windows.Controls.Control.FontWeight%2A> se establece en <xref:System.Windows.FontWeights.Normal%2A>.|  
|<xref:System.Drawing.Font.Italic%2A>|<xref:System.Windows.Controls.Control.FontStyle%2A> en el elemento hospedado|Si el valor de <xref:System.Drawing.Font.Italic%2A> es `true`, el valor de <xref:System.Windows.Controls.Control.FontStyle%2A> se establece en <xref:System.Windows.FontStyles.Italic%2A>.<br /><br /> Si el valor de <xref:System.Drawing.Font.Italic%2A> es `false`, el valor de <xref:System.Windows.Controls.Control.FontStyle%2A> se establece en <xref:System.Windows.FontStyles.Normal%2A>.|  
|<xref:System.Drawing.Font.Strikeout%2A>|<xref:System.Windows.TextDecorations> en el elemento hospedado|Sólo se aplica al hospedar un control <xref:System.Windows.Controls.TextBlock>.|  
|<xref:System.Drawing.Font.Underline%2A>|<xref:System.Windows.TextDecorations> en el elemento hospedado|Sólo se aplica al hospedar un control <xref:System.Windows.Controls.TextBlock>.|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> \(<xref:System.Windows.Forms.RightToLeft?displayProperty=fullName>\)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> \(<xref:System.Windows.FlowDirection>\)|<xref:System.Windows.Forms.RightToLeft> se asigna a <xref:System.Windows.FlowDirection>.<br /><br /> <xref:System.Windows.Forms.RightToLeft> se asigna a <xref:System.Windows.FlowDirection>.|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|El control <xref:System.Windows.Forms.Integration.ElementHost> establece la propiedad <xref:System.Windows.UIElement.Visibility%2A> en el elemento hospedado utilizando las reglas siguientes:<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> \= `true` se asigna a <xref:System.Windows.Visibility>.<br />-   <xref:System.Windows.Forms.Control.Visible%2A> \= `false` se asigna a <xref:System.Windows.Visibility>.|  
  
## Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Interoperabilidad de WPF y Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)   
 [Interoperabilidad entre Windows Forms y WPF](../../../../docs/framework/wpf/advanced/wpf-and-windows-forms-interoperation.md)   
 [Tutorial: Asignar propiedades mediante el uso del elemento WindowsFormsHost](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-windowsformshost-element.md)   
 [Tutorial: Asignar propiedades mediante el uso del control ElementHost](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-elementhost-control.md)