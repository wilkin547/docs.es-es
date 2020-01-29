---
title: Asignación de propiedades en formularios Windows Forms y WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- property mapping [WPF interoperability]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 999d8298-9c04-467d-a453-86e41002057d
ms.openlocfilehash: 07e58f87d886212426e25be83f988037549ab642
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735236"
---
# <a name="windows-forms-and-wpf-property-mapping"></a>Asignación de propiedades en formularios Windows Forms y WPF
Las tecnologías [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tienen dos modelos de propiedades similares pero diferentes. La *asignación de propiedades* admite la interoperación entre las dos arquitecturas y proporciona las siguientes capacidades:  
  
- Facilita la asignación de los cambios de propiedad relevantes en el entorno de host al control o elemento hospedado.  
  
- Proporciona el control predeterminado para asignar las propiedades que se usan con más frecuencia.  
  
- Permite la eliminación, invalidación o extensión de propiedades predeterminadas.  
  
- Garantiza que los cambios de valor de propiedad en el host se detectan y se convierten automáticamente en el control o elemento hospedado.  
  
> [!NOTE]
> Los eventos de cambio de propiedad no se propagan hacia arriba en la jerarquía de controles o elementos de hospedaje. La conversión de propiedad no se realiza si el valor local de una propiedad no cambia debido a la configuración directa, los estilos, la herencia, el enlace de datos u otros mecanismos que cambian el valor de la propiedad.  
  
 Use la propiedad <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> en el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> y la propiedad <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> en el control <xref:System.Windows.Forms.Integration.ElementHost> para tener acceso a la asignación de propiedades.  
  
## <a name="property-mapping-with-the-windowsformshost-element"></a>Asignación de propiedades con el elemento WindowsFormsHost  
 El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> convierte las propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] predeterminadas en sus [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] equivalentes mediante la siguiente tabla de traducción.  
  
|Hospedaje de Windows Presentation Foundation|Windows Forms|Comportamiento de interoperación|  
|---------------------------------------------|-------------------|-----------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> establece la propiedad <xref:System.Windows.Forms.Control.BackColor%2A> del control hospedado y la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A> del control hospedado. La asignación se realiza mediante las siguientes reglas:<br /><br /> -Si <xref:System.Windows.Controls.Control.Background%2A> es un color sólido, se convierte y se usa para establecer la propiedad <xref:System.Windows.Forms.Control.BackColor%2A> del control hospedado. La propiedad <xref:System.Windows.Forms.Control.BackColor%2A> no se establece en el control hospedado, porque el control hospedado puede heredar el valor de la propiedad <xref:System.Windows.Forms.Control.BackColor%2A>. **Nota:**  El control hospedado no admite la transparencia. Cualquier color asignado a <xref:System.Windows.Forms.Control.BackColor%2A> debe ser totalmente opaco, con un valor alfa de 0xFF. <br /><br /> -Si <xref:System.Windows.Controls.Control.Background%2A> no es un color sólido, el control <xref:System.Windows.Forms.Integration.WindowsFormsHost> crea un mapa de bits a partir de la propiedad <xref:System.Windows.Controls.Control.Background%2A>. El control <xref:System.Windows.Forms.Integration.WindowsFormsHost> asigna este mapa de bits a la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A> del control hospedado. Esto proporciona un efecto que es similar a la transparencia. **Nota:**  Puede invalidar este comportamiento o puede quitar la asignación de propiedades de <xref:System.Windows.Controls.Control.Background%2A>.|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|Si no se ha reasignado la asignación predeterminada, <xref:System.Windows.Forms.Integration.WindowsFormsHost> control atraviesa su jerarquía antecesor hasta que encuentra un antecesor con su conjunto de propiedades <xref:System.Windows.FrameworkElement.Cursor%2A>. Este valor se traduce al cursor de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] correspondiente más próximo.<br /><br /> Si no se ha reasignado la asignación predeterminada para la propiedad <xref:System.Windows.FrameworkElement.ForceCursor%2A>, el recorrido se detiene en el primer antecesor con <xref:System.Windows.FrameworkElement.ForceCursor%2A> establecido en `true`.|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FlowDirection.LeftToRight> se asigna a <xref:System.Windows.Forms.RightToLeft.No>.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft> se asigna a <xref:System.Windows.Forms.RightToLeft.Yes>.<br /><br /> no se ha asignado <xref:System.Windows.Forms.RightToLeft.Inherit>.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> se asigna a <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Style%2A> en el <xref:System.Drawing.Font?displayProperty=nameWithType> del control hospedado|El conjunto de propiedades [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se convierte en una <xref:System.Drawing.Font>correspondiente. Cuando cambia una de estas propiedades, se crea un nuevo <xref:System.Drawing.Font>. Por <xref:System.Windows.FontStyles.Normal%2A>: <xref:System.Drawing.FontStyle.Italic> está deshabilitado. Para <xref:System.Windows.FontStyles.Italic%2A> o <xref:System.Windows.FontStyles.Oblique%2A>: <xref:System.Drawing.FontStyle.Italic> está habilitado.|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Style%2A> en el <xref:System.Drawing.Font?displayProperty=nameWithType> del control hospedado|El conjunto de propiedades [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se convierte en una <xref:System.Drawing.Font>correspondiente. Cuando cambia una de estas propiedades, se crea un nuevo <xref:System.Drawing.Font>. Por <xref:System.Windows.FontWeights.Black%2A>, <xref:System.Windows.FontWeights.Bold%2A>, <xref:System.Windows.FontWeights.DemiBold%2A>, <xref:System.Windows.FontWeights.ExtraBold%2A>, <xref:System.Windows.FontWeights.Heavy%2A>, <xref:System.Windows.FontWeights.Medium%2A>, <xref:System.Windows.FontWeights.SemiBold%2A>o <xref:System.Windows.FontWeights.UltraBold%2A>: <xref:System.Drawing.FontStyle.Bold> está habilitado. Por <xref:System.Windows.FontWeights.ExtraLight%2A>, <xref:System.Windows.FontWeights.Light%2A>, <xref:System.Windows.FontWeights.Normal%2A>, <xref:System.Windows.FontWeights.Regular%2A>, <xref:System.Windows.FontWeights.Thin%2A>o <xref:System.Windows.FontWeights.UltraLight%2A>: <xref:System.Drawing.FontStyle.Bold> está deshabilitado.|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|El conjunto de propiedades [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se convierte en una <xref:System.Drawing.Font>correspondiente. Cuando cambia una de estas propiedades, se crea un nuevo <xref:System.Drawing.Font>. El control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado cambia de tamaño en función del tamaño de fuente.<br /><br /> El tamaño de fuente en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se expresa como un noventa-sexto de pulgada y en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] como un setenta por segundo de una pulgada. La conversión correspondiente es:<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tamaño de fuente = [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tamaño de fuente * 72,0/96,0.|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|La asignación de la propiedad <xref:System.Windows.Controls.Control.Foreground%2A> se realiza mediante las siguientes reglas:<br /><br /> -Si <xref:System.Windows.Controls.Control.Foreground%2A> es una <xref:System.Windows.Media.SolidColorBrush>, use <xref:System.Windows.Media.SolidColorBrush.Color%2A> para <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />-Si <xref:System.Windows.Controls.Control.Foreground%2A> es una <xref:System.Windows.Media.GradientBrush>, use el color de la <xref:System.Windows.Media.GradientStop> con el valor de desplazamiento más bajo para <xref:System.Windows.Forms.Control.ForeColor%2A>.<br />-Para cualquier otro tipo de <xref:System.Windows.Media.Brush>, deje <xref:System.Windows.Forms.Control.ForeColor%2A> sin cambios. Esto significa que se usa el valor predeterminado.|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|Cuando se establece <xref:System.Windows.UIElement.IsEnabled%2A>, <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento establece la propiedad <xref:System.Windows.Forms.Control.Enabled%2A> en el control hospedado.|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|Los cuatro valores de la propiedad <xref:System.Windows.Forms.Control.Padding%2A> en el control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado se establecen en el mismo valor de <xref:System.Windows.Thickness>.<br /><br /> : Los valores mayores que <xref:System.Int32.MaxValue> se establecen en <xref:System.Int32.MaxValue>.<br />: Los valores menores que <xref:System.Int32.MinValue> se establecen en <xref:System.Int32.MinValue>.|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility.Visible> se asigna a <xref:System.Windows.Forms.Control.Visible%2A> = `true`. El control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado está visible. No se recomienda establecer explícitamente la propiedad <xref:System.Windows.Forms.Control.Visible%2A> en el control hospedado en `false`.<br />-   <xref:System.Windows.Visibility.Collapsed> se asigna a <xref:System.Windows.Forms.Control.Visible%2A> = `true` o `false`. No se dibuja el control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado y su área está contraída.<br />-   <xref:System.Windows.Visibility.Hidden>: el control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado ocupa espacio en el diseño, pero no es visible. En este caso, la propiedad <xref:System.Windows.Forms.Control.Visible%2A> se establece en `true`. No se recomienda establecer explícitamente la propiedad <xref:System.Windows.Forms.Control.Visible%2A> en el control hospedado en `false`.|  
  
 Las propiedades adjuntas de los elementos de contenedor son totalmente compatibles con el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
 Para obtener más información, vea [Tutorial: asignar propiedades mediante el elemento WindowsFormsHost](walkthrough-mapping-properties-using-the-windowsformshost-element.md).  
  
## <a name="updates-to-parent-properties"></a>Actualizaciones de las propiedades principales  
 Los cambios en la mayoría de las propiedades primarias producen notificaciones al control secundario hospedado. En la siguiente lista se describen las propiedades que no producen notificaciones cuando cambian sus valores.  
  
- <xref:System.Windows.Controls.Control.Background%2A>  
  
- <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
- <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
- <xref:System.Windows.UIElement.Visibility%2A>  
  
 Por ejemplo, si cambia el valor de la propiedad <xref:System.Windows.Controls.Control.Background%2A> del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, la propiedad <xref:System.Windows.Forms.Control.BackColor%2A> del control hospedado no cambia.  
  
## <a name="property-mapping-with-the-elementhost-control"></a>Asignación de propiedades con el control ElementHost  
 Las siguientes propiedades proporcionan una notificación de cambio integrada. No llame al método <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> cuando esté asignando estas propiedades:  
  
- AutoSize  
  
- BackColor  
  
- BackgroundImage  
  
- BackgroundImageLayout  
  
- BindingContext  
  
- Nastavení CausesValidation Pro  
  
- ContextMenu  
  
- ContextMenuStrip  
  
- Cursor  
  
- Acoplar  
  
- Enabled  
  
- Fuente  
  
- ForeColor  
  
- Ubicación  
  
- Margen  
  
- Relleno  
  
- Primario  
  
- Región  
  
- RightToLeft  
  
- Tamaño de la  
  
- TabIndex  
  
- TabStop  
  
- Text  
  
- Visible  
  
 El control <xref:System.Windows.Forms.Integration.ElementHost> convierte las propiedades [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] predeterminadas en sus [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] equivalentes mediante la siguiente tabla de traducción.  
  
 Para obtener más información, vea [Tutorial: asignar propiedades mediante el control ElementHost](walkthrough-mapping-properties-using-the-elementhost-control.md).  
  
|Hospedaje de Windows Forms|Windows Presentation Foundation|Comportamiento de interoperación|  
|---------------------------|-------------------------------------|-----------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) en el elemento hospedado|El establecimiento de esta propiedad obliga a que se vuelva a dibujar con un <xref:System.Windows.Media.ImageBrush>. Si la propiedad <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> está establecida en `false` (el valor predeterminado), este <xref:System.Windows.Media.ImageBrush> se basa en la apariencia del control de <xref:System.Windows.Forms.Integration.ElementHost>, incluidas las propiedades <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> y los controladores de pintura asociados.<br /><br /> Si la propiedad <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> está establecida en `true`, el <xref:System.Windows.Media.ImageBrush> se basa en la apariencia del elemento primario del control de <xref:System.Windows.Forms.Integration.ElementHost>, incluidos los <xref:System.Windows.Forms.Control.BackColor%2A>de los elementos primarios, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> y los controladores de dibujo asociados.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> (<xref:System.Drawing.Image?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) en el elemento hospedado|Al establecer esta propiedad, se produce el mismo comportamiento descrito para la asignación de <xref:System.Windows.Forms.Control.BackColor%2A>.|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) en el elemento hospedado|Al establecer esta propiedad, se produce el mismo comportamiento descrito para la asignación de <xref:System.Windows.Forms.Control.BackColor%2A>.|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> (<xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> (<xref:System.Windows.Input.Cursor?displayProperty=nameWithType>)|El cursor estándar de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] se convierte en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cursor estándar correspondiente. Si el [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no es un cursor estándar, se asigna el valor predeterminado.|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|Cuando se establece <xref:System.Windows.Forms.Control.Enabled%2A>, el control <xref:System.Windows.Forms.Integration.ElementHost> establece la propiedad <xref:System.Windows.UIElement.IsEnabled%2A> en el elemento hospedado.|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|El valor <xref:System.Windows.Forms.Control.Font%2A> se traduce en un conjunto correspondiente de propiedades de fuente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|  
|<xref:System.Drawing.Font.Bold%2A>|<xref:System.Windows.Controls.Control.FontWeight%2A> en el elemento hospedado|Si el valor de <xref:System.Drawing.Font.Bold%2A> es `true`, el valor de <xref:System.Windows.Controls.Control.FontWeight%2A> se establece en <xref:System.Windows.FontWeights.Bold%2A>.<br /><br /> Si el valor de <xref:System.Drawing.Font.Bold%2A> es `false`, el valor de <xref:System.Windows.Controls.Control.FontWeight%2A> se establece en <xref:System.Windows.FontWeights.Normal%2A>.|  
|<xref:System.Drawing.Font.Italic%2A>|<xref:System.Windows.Controls.Control.FontStyle%2A> en el elemento hospedado|Si el valor de <xref:System.Drawing.Font.Italic%2A> es `true`, el valor de <xref:System.Windows.Controls.Control.FontStyle%2A> se establece en <xref:System.Windows.FontStyles.Italic%2A>.<br /><br /> Si el valor de <xref:System.Drawing.Font.Italic%2A> es `false`, el valor de <xref:System.Windows.Controls.Control.FontStyle%2A> se establece en <xref:System.Windows.FontStyles.Normal%2A>.|  
|<xref:System.Drawing.Font.Strikeout%2A>|<xref:System.Windows.TextDecorations> en el elemento hospedado|Solo se aplica cuando se hospeda un control <xref:System.Windows.Controls.TextBlock>.|  
|<xref:System.Drawing.Font.Underline%2A>|<xref:System.Windows.TextDecorations> en el elemento hospedado|Solo se aplica cuando se hospeda un control <xref:System.Windows.Controls.TextBlock>.|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection>)|<xref:System.Windows.Forms.RightToLeft.No> se asigna a <xref:System.Windows.FlowDirection.LeftToRight>.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Yes> se asigna a <xref:System.Windows.FlowDirection.RightToLeft>.|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|El control <xref:System.Windows.Forms.Integration.ElementHost> establece la propiedad <xref:System.Windows.UIElement.Visibility%2A> en el elemento hospedado mediante las siguientes reglas:<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> = `true` se asigna a <xref:System.Windows.Visibility.Visible>.<br />-   <xref:System.Windows.Forms.Control.Visible%2A> = `false` se asigna a <xref:System.Windows.Visibility.Hidden>.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md)
- [Interoperabilidad entre Windows Forms y WPF](wpf-and-windows-forms-interoperation.md)
- [Tutorial: Asignar propiedades mediante el uso del elemento WindowsFormsHost](walkthrough-mapping-properties-using-the-windowsformshost-element.md)
- [Tutorial: Asignar propiedades mediante el uso del control ElementHost](walkthrough-mapping-properties-using-the-elementhost-control.md)
