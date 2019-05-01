---
title: Asignación de propiedades en formularios Windows Forms y WPF
ms.date: 03/30/2017
helpviewer_keywords:
- property mapping [WPF interoperability]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 999d8298-9c04-467d-a453-86e41002057d
ms.openlocfilehash: a7d78837a141ed322da42629501cee6dcc9143e1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053137"
---
# <a name="windows-forms-and-wpf-property-mapping"></a>Asignación de propiedades en formularios Windows Forms y WPF
El [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tecnologías, hay dos modelos de propiedades similares pero diferentes. *Asignación de propiedad* admite la interoperabilidad entre las dos arquitecturas y proporciona las siguientes capacidades:  
  
- Facilita asignar los cambios de propiedad correspondiente en el entorno de host para el control o elemento hospedado.  
  
- Proporciona propiedades de control predeterminado para asignar más comúnmente utilizadas.  
  
- Permite que facilita la eliminación, reemplazar o extensión de las propiedades predeterminadas.  
  
- Garantiza que los cambios de valor de propiedad en el host se ha detectado y traducidos al control hospedado o elemento automáticamente.  
  
> [!NOTE]
>  Eventos de cambio de propiedad no se propaga hacia arriba en el control de hospedaje o de la jerarquía de elementos. No se realiza la traducción de la propiedad si el valor local de una propiedad no cambia debido a la configuración directa, estilos, herencia, enlace de datos u otros mecanismos que cambie el valor de la propiedad.  
  
 Use la <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> propiedad en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento y el <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> propiedad <xref:System.Windows.Forms.Integration.ElementHost> control para tener acceso a la asignación de propiedades.  
  
## <a name="property-mapping-with-the-windowsformshost-element"></a>Asignación de propiedades con el elemento WindowsFormsHost  
 El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento traduce predeterminada [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades a sus [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] equivalentes con la siguiente tabla de traducción.  
  
|Hospedaje de Windows Presentation Foundation|Windows Forms|Comportamiento de interoperación|  
|---------------------------------------------|-------------------|-----------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|El <xref:System.Windows.Forms.Integration.WindowsFormsHost> conjuntos de elementos del <xref:System.Windows.Forms.Control.BackColor%2A> propiedad del control hospedado y <xref:System.Windows.Forms.Control.BackgroundImage%2A> propiedad del control hospedado. Asignación se realiza mediante el uso de las siguientes reglas:<br /><br /> -If <xref:System.Windows.Controls.Control.Background%2A> es un color sólido, se convierte y se usa para establecer el <xref:System.Windows.Forms.Control.BackColor%2A> propiedad del control hospedado. El <xref:System.Windows.Forms.Control.BackColor%2A> propiedad no se establece en el control hospedado, porque el control hospedado puede heredar el valor de la <xref:System.Windows.Forms.Control.BackColor%2A> propiedad. **Nota:**  El control hospedado no es compatible con la transparencia. Cualquier color asignado a <xref:System.Windows.Forms.Control.BackColor%2A> debe ser completamente opaco, con un valor alfa de 0xFF. <br /><br /> -If <xref:System.Windows.Controls.Control.Background%2A> no es un color sólido, el <xref:System.Windows.Forms.Integration.WindowsFormsHost> control crea un mapa de bits desde el <xref:System.Windows.Controls.Control.Background%2A> propiedad. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> control asigna este mapa de bits para el <xref:System.Windows.Forms.Control.BackgroundImage%2A> propiedad del control hospedado. Esto proporciona un efecto que es similar a la transparencia. **Nota:**  Puede invalidar este comportamiento, o bien puede quitar el <xref:System.Windows.Controls.Control.Background%2A> asignación de propiedades.|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|Si no se ha reasignado la asignación predeterminada, <xref:System.Windows.Forms.Integration.WindowsFormsHost> control atraviesa su jerarquía de antecesores hasta que encuentra un antecesor con su <xref:System.Windows.FrameworkElement.Cursor%2A> conjunto de propiedades. Este valor se convierte en la correspondiente más cercano [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] cursor.<br /><br /> Si la asignación predeterminada para el <xref:System.Windows.FrameworkElement.ForceCursor%2A> propiedad no se ha reasignado, el recorrido se detiene en el primer antecesor con <xref:System.Windows.FrameworkElement.ForceCursor%2A> establecido en `true`.|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FlowDirection.LeftToRight> se asigna a <xref:System.Windows.Forms.RightToLeft.No>.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft> se asigna a <xref:System.Windows.Forms.RightToLeft.Yes>.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Inherit> no está asignada.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> se asigna a <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Style%2A> en el control hospedado <xref:System.Drawing.Font?displayProperty=nameWithType>|El conjunto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades se traduce en correspondiente <xref:System.Drawing.Font>. Cuando se cambia una de estas propiedades, un nuevo <xref:System.Drawing.Font> se crea. Para <xref:System.Windows.FontStyles.Normal%2A>: <xref:System.Drawing.FontStyle.Italic> está deshabilitado. Para <xref:System.Windows.FontStyles.Italic%2A> o <xref:System.Windows.FontStyles.Oblique%2A>: <xref:System.Drawing.FontStyle.Italic> está habilitado.|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Style%2A> en el control hospedado <xref:System.Drawing.Font?displayProperty=nameWithType>|El conjunto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades se traduce en correspondiente <xref:System.Drawing.Font>. Cuando se cambia una de estas propiedades, un nuevo <xref:System.Drawing.Font> se crea. Para <xref:System.Windows.FontWeights.Black%2A>, <xref:System.Windows.FontWeights.Bold%2A>, <xref:System.Windows.FontWeights.DemiBold%2A>, <xref:System.Windows.FontWeights.ExtraBold%2A>, <xref:System.Windows.FontWeights.Heavy%2A>, <xref:System.Windows.FontWeights.Medium%2A>, <xref:System.Windows.FontWeights.SemiBold%2A>, o <xref:System.Windows.FontWeights.UltraBold%2A>: <xref:System.Drawing.FontStyle.Bold> está habilitado. Para <xref:System.Windows.FontWeights.ExtraLight%2A>, <xref:System.Windows.FontWeights.Light%2A>, <xref:System.Windows.FontWeights.Normal%2A>, <xref:System.Windows.FontWeights.Regular%2A>, <xref:System.Windows.FontWeights.Thin%2A>, o <xref:System.Windows.FontWeights.UltraLight%2A>: <xref:System.Drawing.FontStyle.Bold> está deshabilitado.|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|El conjunto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades se traduce en correspondiente <xref:System.Drawing.Font>. Cuando se cambia una de estas propiedades, un nuevo <xref:System.Drawing.Font> se crea. Hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control cambia automáticamente de tamaño según el tamaño de fuente.<br /><br /> Tamaño de fuente en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se expresa como un noventa sexto de una pulgada y en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] como un segundo setenta de pulgada. La conversión correspondiente es:<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tamaño de fuente = [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tamaño de fuente * 72,0 / 96,0.|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|El <xref:System.Windows.Controls.Control.Foreground%2A> se realiza la asignación de propiedades mediante el uso de las siguientes reglas:<br /><br /> -If <xref:System.Windows.Controls.Control.Foreground%2A> es un <xref:System.Windows.Media.SolidColorBrush>, utilice <xref:System.Windows.Media.SolidColorBrush.Color%2A> para <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />-If <xref:System.Windows.Controls.Control.Foreground%2A> es un <xref:System.Windows.Media.GradientBrush>, use el color de la <xref:System.Windows.Media.GradientStop> con el menor valor de desplazamiento para <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />-Para cualquier otro <xref:System.Windows.Media.Brush> escriba, deje <xref:System.Windows.Forms.Control.ForeColor%2A> sin cambios. Esto significa que se usa el valor predeterminado.|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|Cuando <xref:System.Windows.UIElement.IsEnabled%2A> está establecida, <xref:System.Windows.Forms.Integration.WindowsFormsHost> conjuntos de elementos del <xref:System.Windows.Forms.Control.Enabled%2A> propiedad en el control hospedado.|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|Los cuatro valores de la <xref:System.Windows.Forms.Control.Padding%2A> propiedad hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control se establecen en el mismo <xref:System.Windows.Thickness> valor.<br /><br /> -Los valores mayores que <xref:System.Int32.MaxValue> se establecen en <xref:System.Int32.MaxValue>.<br />-Los valores de menor <xref:System.Int32.MinValue> se establecen en <xref:System.Int32.MinValue>.|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility.Visible> se asigna a <xref:System.Windows.Forms.Control.Visible%2A>  =  `true`. Hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control está visible. De forma explícita el <xref:System.Windows.Forms.Control.Visible%2A> propiedad en el control hospedado a `false` no se recomienda.<br />-   <xref:System.Windows.Visibility.Collapsed> se asigna a <xref:System.Windows.Forms.Control.Visible%2A>  =  `true` o `false`. Hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no se dibuja el control y se contrae su área.<br />-   <xref:System.Windows.Visibility.Hidden> : Hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ocupa espacio en el diseño del control, pero no está visible. En este caso, el <xref:System.Windows.Forms.Control.Visible%2A> propiedad está establecida en `true`. De forma explícita el <xref:System.Windows.Forms.Control.Visible%2A> propiedad en el control hospedado a `false` no se recomienda.|  
  
 Las propiedades adjuntas en elementos de contenedor son totalmente compatibles con el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.  
  
 Para obtener más información, vea [Tutorial: Asignar propiedades mediante el uso del elemento WindowsFormsHost](walkthrough-mapping-properties-using-the-windowsformshost-element.md).  
  
## <a name="updates-to-parent-properties"></a>Actualizaciones de propiedades del miembro primario  
 Los cambios realizados en la mayoría de las propiedades de elemento primario, generarán notificaciones al control secundario hospedado. La lista siguiente describe las propiedades que no generan notificaciones cuando cambian sus valores.  
  
- <xref:System.Windows.Controls.Control.Background%2A>  
  
- <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
- <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
- <xref:System.Windows.UIElement.Visibility%2A>  
  
 Por ejemplo, si cambia el valor de la <xref:System.Windows.Controls.Control.Background%2A> propiedad de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento, el <xref:System.Windows.Forms.Control.BackColor%2A> no cambia la propiedad del control hospedado.  
  
## <a name="property-mapping-with-the-elementhost-control"></a>Asignación de propiedades con el Control ElementHost  
 Las propiedades siguientes proporcionan notificación de cambios integrado. No llame a la <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> método cuando se asignan estas propiedades:  
  
- AutoSize  
  
- BackColor  
  
- BackgroundImage  
  
- BackgroundImageLayout  
  
- BindingContext  
  
- CausesValidation  
  
- ContextMenu  
  
- ContextMenuStrip  
  
- Cursor  
  
- Acoplar  
  
- Habilitado  
  
- Fuente  
  
- ForeColor  
  
- Ubicación  
  
- Margen  
  
- Relleno  
  
- Primario  
  
- Región  
  
- RightToLeft  
  
- Tamaño  
  
- TabIndex  
  
- TabStop  
  
- Texto  
  
- Visible  
  
 El <xref:System.Windows.Forms.Integration.ElementHost> control traduce predeterminada [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] propiedades a sus [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] equivalentes mediante el uso de la siguiente tabla de traducción.  
  
 Para obtener más información, vea [Tutorial: Asignar propiedades mediante el uso del Control ElementHost](walkthrough-mapping-properties-using-the-elementhost-control.md).  
  
|Hospedaje de formularios de Windows|Windows Presentation Foundation|Comportamiento de interoperación|  
|---------------------------|-------------------------------------|-----------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) en el elemento hospedado|Al establecer esta propiedad hace vuelva a dibujarse con un <xref:System.Windows.Media.ImageBrush>. Si el <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> propiedad está establecida en `false` (el valor predeterminado), esto <xref:System.Windows.Media.ImageBrush> se basa en la apariencia de la <xref:System.Windows.Forms.Integration.ElementHost> controlar, incluida su <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> propiedades y cualquier paint adjunto controladores.<br /><br /> Si el <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> propiedad está establecida en `true`, el <xref:System.Windows.Media.ImageBrush> se basa en la apariencia de la <xref:System.Windows.Forms.Integration.ElementHost> primario del control, incluidos los padres <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> propiedades y cualquier paint adjunto controladores.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> (<xref:System.Drawing.Image?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) en el elemento hospedado|Al establecer esta propiedad hace que el mismo comportamiento descrito para el <xref:System.Windows.Forms.Control.BackColor%2A> asignación.|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) en el elemento hospedado|Al establecer esta propiedad hace que el mismo comportamiento descrito para el <xref:System.Windows.Forms.Control.BackColor%2A> asignación.|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> (<xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> (<xref:System.Windows.Input.Cursor?displayProperty=nameWithType>)|El [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] cursor estándar se traduce a la correspondiente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cursor estándar. Si el [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no es un cursor estándar, se asigna el valor predeterminado.|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|Cuando <xref:System.Windows.Forms.Control.Enabled%2A> se establece, el <xref:System.Windows.Forms.Integration.ElementHost> conjuntos de controles el <xref:System.Windows.UIElement.IsEnabled%2A> propiedad en el elemento hospedado.|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|El <xref:System.Windows.Forms.Control.Font%2A> valor se convierte en un conjunto correspondiente de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades de fuente.|  
|<xref:System.Drawing.Font.Bold%2A>|<xref:System.Windows.Controls.Control.FontWeight%2A> en el elemento hospedado|Si el valor de <xref:System.Drawing.Font.Bold%2A> es `true`, el valor de <xref:System.Windows.Controls.Control.FontWeight%2A> se establece en <xref:System.Windows.FontWeights.Bold%2A>.<br /><br /> Si el valor de <xref:System.Drawing.Font.Bold%2A> es `false`, el valor de <xref:System.Windows.Controls.Control.FontWeight%2A> se establece en <xref:System.Windows.FontWeights.Normal%2A>.|  
|<xref:System.Drawing.Font.Italic%2A>|<xref:System.Windows.Controls.Control.FontStyle%2A> en el elemento hospedado|Si el valor de <xref:System.Drawing.Font.Italic%2A> es `true`, el valor de <xref:System.Windows.Controls.Control.FontStyle%2A> se establece en <xref:System.Windows.FontStyles.Italic%2A>.<br /><br /> Si el valor de <xref:System.Drawing.Font.Italic%2A> es `false`, el valor de <xref:System.Windows.Controls.Control.FontStyle%2A> se establece en <xref:System.Windows.FontStyles.Normal%2A>.|  
|<xref:System.Drawing.Font.Strikeout%2A>|<xref:System.Windows.TextDecorations> en el elemento hospedado|Se aplica solo al hospedar un <xref:System.Windows.Controls.TextBlock> control.|  
|<xref:System.Drawing.Font.Underline%2A>|<xref:System.Windows.TextDecorations> en el elemento hospedado|Se aplica solo al hospedar un <xref:System.Windows.Controls.TextBlock> control.|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection>)|<xref:System.Windows.Forms.RightToLeft.No> se asigna a <xref:System.Windows.FlowDirection.LeftToRight>.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Yes> se asigna a <xref:System.Windows.FlowDirection.RightToLeft>.|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|El <xref:System.Windows.Forms.Integration.ElementHost> conjuntos de controles el <xref:System.Windows.UIElement.Visibility%2A> propiedad en el elemento hospedado mediante el uso de las siguientes reglas:<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> = `true` se asigna a <xref:System.Windows.Visibility.Visible>.<br />-   <xref:System.Windows.Forms.Control.Visible%2A> = `false` se asigna a <xref:System.Windows.Visibility.Hidden>.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md)
- [Interoperabilidad entre Windows Forms y WPF](wpf-and-windows-forms-interoperation.md)
- [Tutorial: Asignar propiedades mediante el uso del elemento WindowsFormsHost](walkthrough-mapping-properties-using-the-windowsformshost-element.md)
- [Tutorial: Asignar propiedades mediante el uso del Control ElementHost](walkthrough-mapping-properties-using-the-elementhost-control.md)
