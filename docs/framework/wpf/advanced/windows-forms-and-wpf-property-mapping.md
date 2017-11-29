---
title: "Asignación de propiedades en formularios Windows Forms y WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- property mapping [WPF interoperability]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 999d8298-9c04-467d-a453-86e41002057d
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1a0af1015747e2f27b19c2cac2c896dd60214264
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="windows-forms-and-wpf-property-mapping"></a>Asignación de propiedades en formularios Windows Forms y WPF
El [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tecnologías tienen dos modelos de propiedades similares pero diferentes. *Asignación de propiedad* admite la interoperación entre las dos arquitecturas y proporciona las siguientes capacidades:  
  
-   Hace fácil asignar los cambios de propiedad correspondiente en el entorno de host para el control o elemento hospedado.  
  
-   Proporciona propiedades de control predeterminado para asignar más comúnmente utilizadas.  
  
-   Permite que facilita la eliminación, reemplazar o extensión de las propiedades predeterminadas.  
  
-   Se asegura de que cambia de valor de propiedad en el host automáticamente se detectan y se convierten en el control o elemento hospedado.  
  
> [!NOTE]
>  Eventos de cambio de propiedad no se propagan hacia arriba el control host o la jerarquía de elementos. No se realiza la traducción de la propiedad si el valor local de una propiedad no cambia debido a la configuración directa, estilos, herencia, enlace de datos u otros mecanismos que cambie el valor de la propiedad.  
  
 Use la <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> propiedad en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento y el <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> propiedad <xref:System.Windows.Forms.Integration.ElementHost> control para tener acceso a la asignación de propiedad.  
  
## <a name="property-mapping-with-the-windowsformshost-element"></a>Asignación de propiedad con el elemento WindowsFormsHost  
 El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento traduce predeterminado [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades a sus [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] equivalentes con la siguiente tabla de traducción.  
  
|Hospedaje de Windows Presentation Foundation|Windows Forms|Comportamiento de interoperación|  
|---------------------------------------------|-------------------|-----------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|El <xref:System.Windows.Forms.Integration.WindowsFormsHost> conjuntos de elementos del <xref:System.Windows.Forms.Control.BackColor%2A> propiedad del control hospedado y <xref:System.Windows.Forms.Control.BackgroundImage%2A> propiedad del control hospedado. Asignación se realiza mediante las reglas siguientes:<br /><br /> -If <xref:System.Windows.Controls.Control.Background%2A> es un color sólido, se convierte y se usa para establecer el <xref:System.Windows.Forms.Control.BackColor%2A> propiedad del control hospedado. El <xref:System.Windows.Forms.Control.BackColor%2A> propiedad no se establece en el control hospedado, porque el control hospedado puede heredar el valor de la <xref:System.Windows.Forms.Control.BackColor%2A> propiedad. **Nota:** el control hospedado no admiten la transparencia. Cualquier color asignado al <xref:System.Windows.Forms.Control.BackColor%2A> debe ser completamente opaco, con un valor alfa de 0xFF. <br /><br /> -If <xref:System.Windows.Controls.Control.Background%2A> no es un color sólido, el <xref:System.Windows.Forms.Integration.WindowsFormsHost> control crea un mapa de bits de la <xref:System.Windows.Controls.Control.Background%2A> propiedad. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> control asigna este mapa de bits para el <xref:System.Windows.Forms.Control.BackgroundImage%2A> propiedad del control hospedado. Esto proporciona un efecto que es similar a la transparencia. **Nota:** puede invalidar este comportamiento o quitar la <xref:System.Windows.Controls.Control.Background%2A> asignación de propiedad.|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|Si no se ha reasignado la asignación predeterminada, <xref:System.Windows.Forms.Integration.WindowsFormsHost> control recorre su jerarquía de antecesores hasta que encuentra un antecesor con su <xref:System.Windows.FrameworkElement.Cursor%2A> conjunto de propiedades. Este valor se convierte en la correspondiente más cercano [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] cursor.<br /><br /> Si la asignación predeterminada para la <xref:System.Windows.FrameworkElement.ForceCursor%2A> no se ha reasignado propiedad, el recorrido se detiene en el primer antecesor con <xref:System.Windows.FrameworkElement.ForceCursor%2A> establecido en `true`.|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FlowDirection.LeftToRight> se asigna a <xref:System.Windows.Forms.RightToLeft.No>.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft> se asigna a <xref:System.Windows.Forms.RightToLeft.Yes>.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Inherit>no está asignada.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> se asigna a <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Style%2A>en el control hospedado<xref:System.Drawing.Font?displayProperty=nameWithType>|El conjunto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades se traduce en su correspondiente <xref:System.Drawing.Font>. Cuando se cambia una de estas propiedades, un nuevo <xref:System.Drawing.Font> se crea. Para <xref:System.Windows.FontStyles.Normal%2A>: <xref:System.Drawing.FontStyle.Italic> está deshabilitado. Para <xref:System.Windows.FontStyles.Italic%2A> o <xref:System.Windows.FontStyles.Oblique%2A>: <xref:System.Drawing.FontStyle.Italic> está habilitado.|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Style%2A>en el control hospedado<xref:System.Drawing.Font?displayProperty=nameWithType>|El conjunto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades se traduce en su correspondiente <xref:System.Drawing.Font>. Cuando se cambia una de estas propiedades, un nuevo <xref:System.Drawing.Font> se crea. Para <xref:System.Windows.FontWeights.Black%2A>, <xref:System.Windows.FontWeights.Bold%2A>, <xref:System.Windows.FontWeights.DemiBold%2A>, <xref:System.Windows.FontWeights.ExtraBold%2A>, <xref:System.Windows.FontWeights.Heavy%2A>, <xref:System.Windows.FontWeights.Medium%2A>, <xref:System.Windows.FontWeights.SemiBold%2A>, o <xref:System.Windows.FontWeights.UltraBold%2A>: <xref:System.Drawing.FontStyle.Bold> está habilitado. Para <xref:System.Windows.FontWeights.ExtraLight%2A>, <xref:System.Windows.FontWeights.Light%2A>, <xref:System.Windows.FontWeights.Normal%2A>, <xref:System.Windows.FontWeights.Regular%2A>, <xref:System.Windows.FontWeights.Thin%2A>, o <xref:System.Windows.FontWeights.UltraLight%2A>: <xref:System.Drawing.FontStyle.Bold> está deshabilitado.|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|El conjunto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades se traduce en su correspondiente <xref:System.Drawing.Font>. Cuando se cambia una de estas propiedades, un nuevo <xref:System.Drawing.Font> se crea. Hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control cambia de tamaño en función del tamaño de fuente.<br /><br /> Tamaño de fuente de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se expresa como un noventa sexto de pulgada y en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] como un segundo setenta de una pulgada. La conversión correspondiente es:<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]tamaño de fuente = [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tamaño de fuente * 72,0 / 96,0.|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|El <xref:System.Windows.Controls.Control.Foreground%2A> asignación de propiedad se realiza mediante las siguientes reglas:<br /><br /> -If <xref:System.Windows.Controls.Control.Foreground%2A> es un <xref:System.Windows.Media.SolidColorBrush>, use <xref:System.Windows.Media.SolidColorBrush.Color%2A> para <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />-If <xref:System.Windows.Controls.Control.Foreground%2A> es un <xref:System.Windows.Media.GradientBrush>, use el color de la <xref:System.Windows.Media.GradientStop> con el valor de desplazamiento más bajo de <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />-Para cualquier otro <xref:System.Windows.Media.Brush> escriba, deje <xref:System.Windows.Forms.Control.ForeColor%2A> sin cambios. Esto significa que se utiliza el valor predeterminado.|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|Cuando <xref:System.Windows.UIElement.IsEnabled%2A> está establecida, <xref:System.Windows.Forms.Integration.WindowsFormsHost> conjuntos de elementos del <xref:System.Windows.Forms.Control.Enabled%2A> propiedad en el control hospedado.|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|Los cuatro valores de la <xref:System.Windows.Forms.Control.Padding%2A> propiedad hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control se establecen en el mismo <xref:System.Windows.Thickness> valor.<br /><br /> -Valores mayores que <xref:System.Int32.MaxValue> se establecen en <xref:System.Int32.MaxValue>.<br />-Valores inferior a <xref:System.Int32.MinValue> se establecen en <xref:System.Int32.MinValue>.|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility.Visible>se asigna a <xref:System.Windows.Forms.Control.Visible%2A>  =  `true`. Hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control es visible. Cuando se establece explícitamente el <xref:System.Windows.Forms.Control.Visible%2A> propiedad en el control hospedado a `false` no se recomienda.<br />-   <xref:System.Windows.Visibility.Collapsed>se asigna a <xref:System.Windows.Forms.Control.Visible%2A>  =  `true` o `false`. Hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no se dibujará el control y se contrae su área.<br />-   <xref:System.Windows.Visibility.Hidden>: Hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no ocupa espacio en el diseño del control, pero no está visible. En este caso, el <xref:System.Windows.Forms.Control.Visible%2A> propiedad está establecida en `true`. Cuando se establece explícitamente el <xref:System.Windows.Forms.Control.Visible%2A> propiedad en el control hospedado a `false` no se recomienda.|  
  
 Propiedades adjuntas en elementos contenedores son totalmente compatibles con el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.  
  
 Para obtener más información, consulte [Tutorial: propiedades de asignación utilizando el elemento WindowsFormsHost](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-windowsformshost-element.md).  
  
## <a name="updates-to-parent-properties"></a>Actualizaciones a las propiedades del elemento primario  
 Los cambios a la mayoría de las propiedades primario generarán notificaciones en el control secundario hospedado. En la lista siguiente describe las propiedades que no se generarán notificaciones cuando cambian sus valores.  
  
-   <xref:System.Windows.Controls.Control.Background%2A>  
  
-   <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
-   <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
-   <xref:System.Windows.UIElement.Visibility%2A>  
  
 Por ejemplo, si cambia el valor de la <xref:System.Windows.Controls.Control.Background%2A> propiedad de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento, el <xref:System.Windows.Forms.Control.BackColor%2A> no cambia la propiedad del control hospedado.  
  
## <a name="property-mapping-with-the-elementhost-control"></a>Asignación de propiedad con el Control ElementHost  
 Las propiedades siguientes proporcionan notificación de cambios integrada. No llame a la <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> método cuando se asignan estas propiedades:  
  
-   AutoSize  
  
-   Color de fondo  
  
-   BackgroundImage  
  
-   BackgroundImageLayout  
  
-   BindingContext  
  
-   CausesValidation  
  
-   ContextMenu  
  
-   ContextMenuStrip  
  
-   Cursor  
  
-   Acoplar  
  
-   Habilitado  
  
-   Tipo de letra  
  
-   Color de primer plano  
  
-   Ubicación  
  
-   Margin  
  
-   Relleno  
  
-   Elemento primario  
  
-   Región  
  
-   RightToLeft  
  
-   Tamaño  
  
-   TabIndex  
  
-   TabStop  
  
-   Texto  
  
-   Visible  
  
 El <xref:System.Windows.Forms.Integration.ElementHost> control traduce predeterminado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] propiedades a sus [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] equivalentes mediante el uso de la siguiente tabla de traducción.  
  
 Para obtener más información, consulte [Tutorial: propiedades de asignación mediante el ElementHost Control](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-elementhost-control.md).  
  
|Hospedaje de Windows Forms|Windows Presentation Foundation|Comportamiento de interoperación|  
|---------------------------|-------------------------------------|-----------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) en el elemento hospedado|Al establecer esta propiedad hace vuelva a dibujarse con un <xref:System.Windows.Media.ImageBrush>. Si el <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> propiedad está establecida en `false` (el valor predeterminado), esto <xref:System.Windows.Media.ImageBrush> se basa en la apariencia de la <xref:System.Windows.Forms.Integration.ElementHost> controlar, incluida su <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> propiedades y cualquier adjunto paint controladores.<br /><br /> Si el <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> propiedad está establecida en `true`, el <xref:System.Windows.Media.ImageBrush> se basa en la apariencia de la <xref:System.Windows.Forms.Integration.ElementHost> primario del control, incluida la primaria <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> propiedades y cualquier adjunto paint controladores.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> (<xref:System.Drawing.Image?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) en el elemento hospedado|Al establecer esta propiedad hace que el mismo comportamiento descrito para la <xref:System.Windows.Forms.Control.BackColor%2A> asignación.|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) en el elemento hospedado|Al establecer esta propiedad hace que el mismo comportamiento descrito para la <xref:System.Windows.Forms.Control.BackColor%2A> asignación.|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> (<xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> (<xref:System.Windows.Input.Cursor?displayProperty=nameWithType>)|El [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] cursor estándar se traduce a la correspondiente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cursor estándar. Si el [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no es un cursor estándar, se asigna el valor predeterminado.|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|Cuando <xref:System.Windows.Forms.Control.Enabled%2A> se establece, el <xref:System.Windows.Forms.Integration.ElementHost> conjuntos de controles el <xref:System.Windows.UIElement.IsEnabled%2A> propiedad en el elemento hospedado.|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|El <xref:System.Windows.Forms.Control.Font%2A> valor se convierte en un conjunto correspondiente de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades de fuente.|  
|<xref:System.Drawing.Font.Bold%2A>|<xref:System.Windows.Controls.Control.FontWeight%2A>en el elemento hospedado|Si el valor de <xref:System.Drawing.Font.Bold%2A> es `true`, el valor de <xref:System.Windows.Controls.Control.FontWeight%2A> se establece en <xref:System.Windows.FontWeights.Bold%2A>.<br /><br /> Si el valor de <xref:System.Drawing.Font.Bold%2A> es `false`, el valor de <xref:System.Windows.Controls.Control.FontWeight%2A> se establece en <xref:System.Windows.FontWeights.Normal%2A>.|  
|<xref:System.Drawing.Font.Italic%2A>|<xref:System.Windows.Controls.Control.FontStyle%2A>en el elemento hospedado|Si el valor de <xref:System.Drawing.Font.Italic%2A> es `true`, el valor de <xref:System.Windows.Controls.Control.FontStyle%2A> se establece en <xref:System.Windows.FontStyles.Italic%2A>.<br /><br /> Si el valor de <xref:System.Drawing.Font.Italic%2A> es `false`, el valor de <xref:System.Windows.Controls.Control.FontStyle%2A> se establece en <xref:System.Windows.FontStyles.Normal%2A>.|  
|<xref:System.Drawing.Font.Strikeout%2A>|<xref:System.Windows.TextDecorations>en el elemento hospedado|Se aplica solo al hospedar un <xref:System.Windows.Controls.TextBlock> control.|  
|<xref:System.Drawing.Font.Underline%2A>|<xref:System.Windows.TextDecorations>en el elemento hospedado|Se aplica solo al hospedar un <xref:System.Windows.Controls.TextBlock> control.|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection>)|<xref:System.Windows.Forms.RightToLeft.No> se asigna a <xref:System.Windows.FlowDirection.LeftToRight>.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Yes> se asigna a <xref:System.Windows.FlowDirection.RightToLeft>.|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|El <xref:System.Windows.Forms.Integration.ElementHost> conjuntos de controles el <xref:System.Windows.UIElement.Visibility%2A> propiedad en el elemento hospedado utilizando las reglas siguientes:<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> = `true`se asigna a <xref:System.Windows.Visibility.Visible>.<br />-   <xref:System.Windows.Forms.Control.Visible%2A> = `false`se asigna a <xref:System.Windows.Visibility.Hidden>.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Interoperabilidad de WPF y Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [Interoperabilidad entre Windows Forms y WPF](../../../../docs/framework/wpf/advanced/wpf-and-windows-forms-interoperation.md)  
 [Tutorial: Asignar propiedades mediante el uso del elemento WindowsFormsHost](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-windowsformshost-element.md)  
 [Tutorial: Asignar propiedades mediante el uso del control ElementHost](../../../../docs/framework/wpf/advanced/walkthrough-mapping-properties-using-the-elementhost-control.md)
