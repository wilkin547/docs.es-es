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
ms.openlocfilehash: ae4a97bc96a4f9e93942b4995f488c427fda3134
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917500"
---
# <a name="windows-forms-and-wpf-property-mapping"></a>Asignación de propiedades en formularios Windows Forms y WPF
Las [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tecnologías [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y tienen dos modelos de propiedades similares pero diferentes. La *asignación de propiedades* admite la interoperación entre las dos arquitecturas y proporciona las siguientes capacidades:  
  
- Facilita la asignación de los cambios de propiedad relevantes en el entorno de host al control o elemento hospedado.  
  
- Proporciona el control predeterminado para asignar las propiedades que se usan con más frecuencia.  
  
- Permite la eliminación, invalidación o extensión de propiedades predeterminadas.  
  
- Garantiza que los cambios de valor de propiedad en el host se detectan y se convierten automáticamente en el control o elemento hospedado.  
  
> [!NOTE]
> Los eventos de cambio de propiedad no se propagan hacia arriba en la jerarquía de controles o elementos de hospedaje. La conversión de propiedad no se realiza si el valor local de una propiedad no cambia debido a la configuración directa, los estilos, la herencia, el enlace de datos u otros mecanismos que cambian el valor de la propiedad.  
  
 Use la <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> propiedad en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento y la <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> propiedad en <xref:System.Windows.Forms.Integration.ElementHost> el control para tener acceso a la asignación de propiedades.  
  
## <a name="property-mapping-with-the-windowsformshost-element"></a>Asignación de propiedades con el elemento WindowsFormsHost  
 El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento convierte las propiedades predeterminadas [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] sus equivalentes mediante la siguiente tabla de traducción.  
  
|Hospedaje de Windows Presentation Foundation|Windows Forms|Comportamiento de interoperación|  
|---------------------------------------------|-------------------|-----------------------------|  
|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento establece la <xref:System.Windows.Forms.Control.BackColor%2A> propiedad del control hospedado y la <xref:System.Windows.Forms.Control.BackgroundImage%2A> propiedad del control hospedado. La asignación se realiza mediante las siguientes reglas:<br /><br /> -Si <xref:System.Windows.Controls.Control.Background%2A> es un color sólido, se convierte y se usa para establecer la <xref:System.Windows.Forms.Control.BackColor%2A> propiedad del control hospedado. La <xref:System.Windows.Forms.Control.BackColor%2A> propiedad no se establece en el control hospedado, porque el control hospedado puede heredar el <xref:System.Windows.Forms.Control.BackColor%2A> valor de la propiedad. **Nota:**  El control hospedado no admite la transparencia. Cualquier color asignado a <xref:System.Windows.Forms.Control.BackColor%2A> debe ser totalmente opaco, con un valor alfa de 0xFF. <br /><br /> -Si <xref:System.Windows.Controls.Control.Background%2A> no es un color sólido, el <xref:System.Windows.Forms.Integration.WindowsFormsHost> control crea un mapa de bits <xref:System.Windows.Controls.Control.Background%2A> a partir de la propiedad. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> control asigna este mapa de bits a la <xref:System.Windows.Forms.Control.BackgroundImage%2A> propiedad del control hospedado. Esto proporciona un efecto que es similar a la transparencia. **Nota:**  Puede invalidar este comportamiento o puede quitar la asignación <xref:System.Windows.Controls.Control.Background%2A> de propiedades.|  
|<xref:System.Windows.FrameworkElement.Cursor%2A>|<xref:System.Windows.Forms.Control.Cursor%2A>|Si no se ha reasignado la asignación predeterminada, <xref:System.Windows.Forms.Integration.WindowsFormsHost> el control atraviesa su jerarquía antecesor hasta que encuentra un antecesor con su <xref:System.Windows.FrameworkElement.Cursor%2A> propiedad establecida. Este valor se traduce al cursor correspondiente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] más cercano.<br /><br /> Si no se ha reasignado <xref:System.Windows.FrameworkElement.ForceCursor%2A> la asignación predeterminada para la propiedad, el recorrido se detiene en el primer antecesor con <xref:System.Windows.FrameworkElement.ForceCursor%2A> establecido en `true`.|  
|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FlowDirection.LeftToRight>se asigna <xref:System.Windows.Forms.RightToLeft.No>a.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft>se asigna <xref:System.Windows.Forms.RightToLeft.Yes>a.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Inherit>no está asignado.<br /><br /> <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType>se asigna <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType>a.|  
|<xref:System.Windows.Controls.Control.FontStyle%2A>|<xref:System.Drawing.Font.Style%2A>en el del control hospedado<xref:System.Drawing.Font?displayProperty=nameWithType>|El conjunto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades se convierte en un correspondiente <xref:System.Drawing.Font>. Cuando una de estas propiedades cambia, se crea <xref:System.Drawing.Font> un nuevo. Para <xref:System.Windows.FontStyles.Normal%2A> :<xref:System.Drawing.FontStyle.Italic> está deshabilitado. Para <xref:System.Windows.FontStyles.Italic%2A> o <xref:System.Windows.FontStyles.Oblique%2A> :<xref:System.Drawing.FontStyle.Italic> está habilitado.|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Drawing.Font.Style%2A>en el del control hospedado<xref:System.Drawing.Font?displayProperty=nameWithType>|El conjunto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades se convierte en un correspondiente <xref:System.Drawing.Font>. Cuando una de estas propiedades cambia, se crea <xref:System.Drawing.Font> un nuevo. Para <xref:System.Windows.FontWeights.Black%2A>, <xref:System.Windows.FontWeights.Bold%2A>, ,<xref:System.Windows.FontWeights.DemiBold%2A> ,<xref:System.Windows.FontWeights.Heavy%2A>, ,<xref:System.Windows.FontWeights.SemiBold%2A>o: está habilitado<xref:System.Drawing.FontStyle.Bold> . <xref:System.Windows.FontWeights.ExtraBold%2A> <xref:System.Windows.FontWeights.Medium%2A> <xref:System.Windows.FontWeights.UltraBold%2A> Para <xref:System.Windows.FontWeights.ExtraLight%2A>, <xref:System.Windows.FontWeights.Light%2A>, ,,<xref:System.Windows.FontWeights.Regular%2A>o :<xref:System.Windows.FontWeights.UltraLight%2A>está deshabilitado.<xref:System.Drawing.FontStyle.Bold> <xref:System.Windows.FontWeights.Normal%2A> <xref:System.Windows.FontWeights.Thin%2A>|  
|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|El conjunto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades se convierte en un correspondiente <xref:System.Drawing.Font>. Cuando una de estas propiedades cambia, se crea <xref:System.Drawing.Font> un nuevo. El control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado cambia de tamaño en función del tamaño de fuente.<br /><br /> El tamaño de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fuente en se expresa como un noventa-sexto de pulgada y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] en como un setenta de una pulgada. La conversión correspondiente es:<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]tamaño de fuente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] = tamaño de fuente * 72,0/96,0.|  
|<xref:System.Windows.Controls.Control.Foreground%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>)|<xref:System.Windows.Forms.Control.ForeColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|La <xref:System.Windows.Controls.Control.Foreground%2A> asignación de propiedades se realiza mediante las siguientes reglas:<br /><br /> -Si <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Media.SolidColorBrush.Color%2A> es, use para<xref:System.Windows.Forms.Control.ForeColor%2A>. <xref:System.Windows.Media.SolidColorBrush><br />-Si <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Forms.Control.ForeColor%2A>es, use el color de conelvalordedesplazamientomásbajopara.<xref:System.Windows.Media.GradientStop> <xref:System.Windows.Media.GradientBrush><br />-Para cualquier otro <xref:System.Windows.Media.Brush> tipo, deje <xref:System.Windows.Forms.Control.ForeColor%2A> sin cambios. Esto significa que se usa el valor predeterminado.|  
|<xref:System.Windows.UIElement.IsEnabled%2A>|<xref:System.Windows.Forms.Control.Enabled%2A>|Cuando <xref:System.Windows.UIElement.IsEnabled%2A> se establece, <xref:System.Windows.Forms.Integration.WindowsFormsHost> el elemento establece <xref:System.Windows.Forms.Control.Enabled%2A> la propiedad en el control hospedado.|  
|<xref:System.Windows.Controls.Control.Padding%2A>|<xref:System.Windows.Forms.Control.Padding%2A>|Los cuatro valores de la <xref:System.Windows.Forms.Control.Padding%2A> propiedad en el control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado se establecen en el <xref:System.Windows.Thickness> mismo valor.<br /><br /> : Los valores mayores <xref:System.Int32.MaxValue> que se establecen <xref:System.Int32.MaxValue>en.<br />: Los valores menores <xref:System.Int32.MinValue> que se establecen <xref:System.Int32.MinValue>en.|  
|<xref:System.Windows.UIElement.Visibility%2A>|<xref:System.Windows.Forms.Control.Visible%2A>|-   <xref:System.Windows.Visibility.Visible>se asigna <xref:System.Windows.Forms.Control.Visible%2A>a  =  .`true` El control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado está visible. No se recomienda <xref:System.Windows.Forms.Control.Visible%2A> establecer explícitamente la propiedad en `false` el control hospedado en.<br />-   <xref:System.Windows.Visibility.Collapsed>asigna a <xref:System.Windows.Forms.Control.Visible%2A>  =  o.`true` `false` El control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado no se dibuja y su área está contraída.<br />-   <xref:System.Windows.Visibility.Hidden>: El control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado ocupa espacio en el diseño, pero no es visible. En este caso, la <xref:System.Windows.Forms.Control.Visible%2A> propiedad se establece en `true`. No se recomienda <xref:System.Windows.Forms.Control.Visible%2A> establecer explícitamente la propiedad en `false` el control hospedado en.|  
  
 Las propiedades adjuntas de los elementos de contenedor <xref:System.Windows.Forms.Integration.WindowsFormsHost> son totalmente compatibles con el elemento.  
  
 Para obtener más información, vea [Tutorial: Asignar propiedades mediante el elemento](walkthrough-mapping-properties-using-the-windowsformshost-element.md)WindowsFormsHost.  
  
## <a name="updates-to-parent-properties"></a>Actualizaciones de las propiedades principales  
 Los cambios en la mayoría de las propiedades primarias producen notificaciones al control secundario hospedado. En la siguiente lista se describen las propiedades que no producen notificaciones cuando cambian sus valores.  
  
- <xref:System.Windows.Controls.Control.Background%2A>  
  
- <xref:System.Windows.FrameworkElement.Cursor%2A>  
  
- <xref:System.Windows.FrameworkElement.ForceCursor%2A>  
  
- <xref:System.Windows.UIElement.Visibility%2A>  
  
 Por ejemplo, si cambia el valor de la <xref:System.Windows.Controls.Control.Background%2A> propiedad <xref:System.Windows.Forms.Integration.WindowsFormsHost> del elemento, la <xref:System.Windows.Forms.Control.BackColor%2A> propiedad del control hospedado no cambia.  
  
## <a name="property-mapping-with-the-elementhost-control"></a>Asignación de propiedades con el control ElementHost  
 Las siguientes propiedades proporcionan una notificación de cambio integrada. No llame <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> al método cuando esté asignando estas propiedades:  
  
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
  
- Área  
  
- RightToLeft  
  
- Tamaño  
  
- TabIndex  
  
- TabStop  
  
- Text  
  
- Visible  
  
 El <xref:System.Windows.Forms.Integration.ElementHost> control convierte las propiedades predeterminadas [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sus equivalentes mediante la siguiente tabla de traducción.  
  
 Para obtener más información, vea [Tutorial: Asignar propiedades mediante el control](walkthrough-mapping-properties-using-the-elementhost-control.md)ElementHost.  
  
|Hospedaje de Windows Forms|Windows Presentation Foundation|Comportamiento de interoperación|  
|---------------------------|-------------------------------------|-----------------------------|  
|<xref:System.Windows.Forms.Control.BackColor%2A><br /><br /> (<xref:System.Drawing.Color?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) en el elemento hospedado|El establecimiento de esta propiedad obliga a que se vuelva <xref:System.Windows.Media.ImageBrush>a dibujar con. Si la <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> propiedad se establece en `false` (el valor <xref:System.Windows.Media.ImageBrush> predeterminado), se basa en la apariencia del <xref:System.Windows.Forms.Integration.ElementHost> control, incluidas sus <xref:System.Windows.Forms.Control.BackColor%2A>propiedades, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> y cualquier pintura adjunta Controladores.<br /><br /> Si la <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> propiedad está establecida en `true`, el <xref:System.Windows.Media.ImageBrush> objeto se basa en la apariencia del <xref:System.Windows.Forms.Integration.ElementHost> elemento primario del control, incluidas las <xref:System.Windows.Forms.Control.BackColor%2A> <xref:System.Windows.Forms.Control.BackgroundImage%2A> <xref:System.Windows.Forms.Control.BackgroundImageLayout%2A> propiedades,,, y cualquier dibujo adjunta Controladores.|  
|<xref:System.Windows.Forms.Control.BackgroundImage%2A><br /><br /> (<xref:System.Drawing.Image?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) en el elemento hospedado|Al establecer esta propiedad, se produce el mismo comportamiento <xref:System.Windows.Forms.Control.BackColor%2A> descrito para la asignación.|  
|<xref:System.Windows.Forms.Control.BackgroundImageLayout%2A>|<xref:System.Windows.Controls.Control.Background%2A><br /><br /> (<xref:System.Windows.Media.Brush?displayProperty=nameWithType>) en el elemento hospedado|Al establecer esta propiedad, se produce el mismo comportamiento <xref:System.Windows.Forms.Control.BackColor%2A> descrito para la asignación.|  
|<xref:System.Windows.Forms.Control.Cursor%2A><br /><br /> (<xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.Cursor%2A><br /><br /> (<xref:System.Windows.Input.Cursor?displayProperty=nameWithType>)|El [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] cursor estándar se convierte en el cursor [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] estándar correspondiente. Si no [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] es un cursor estándar, se asigna el valor predeterminado.|  
|<xref:System.Windows.Forms.Control.Enabled%2A>|<xref:System.Windows.UIElement.IsEnabled%2A>|Cuando <xref:System.Windows.Forms.Control.Enabled%2A> se establece, el <xref:System.Windows.Forms.Integration.ElementHost> control establece la <xref:System.Windows.UIElement.IsEnabled%2A> propiedad en el elemento hospedado.|  
|<xref:System.Windows.Forms.Control.Font%2A><br /><br /> (<xref:System.Drawing.Font?displayProperty=nameWithType>)|<xref:System.Windows.Controls.Control.FontFamily%2A><br /><br /> <xref:System.Windows.Controls.Control.FontSize%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStretch%2A><br /><br /> <xref:System.Windows.Controls.Control.FontStyle%2A><br /><br /> <xref:System.Windows.Controls.Control.FontWeight%2A>|El <xref:System.Windows.Forms.Control.Font%2A> valor se convierte en un conjunto de propiedades [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de fuente correspondiente.|  
|<xref:System.Drawing.Font.Bold%2A>|<xref:System.Windows.Controls.Control.FontWeight%2A>en elemento hospedado|Si el valor de <xref:System.Drawing.Font.Bold%2A> es `true`, el valor de <xref:System.Windows.Controls.Control.FontWeight%2A> se establece en <xref:System.Windows.FontWeights.Bold%2A>.<br /><br /> Si el valor de <xref:System.Drawing.Font.Bold%2A> es `false`, el valor de <xref:System.Windows.Controls.Control.FontWeight%2A> se establece en <xref:System.Windows.FontWeights.Normal%2A>.|  
|<xref:System.Drawing.Font.Italic%2A>|<xref:System.Windows.Controls.Control.FontStyle%2A>en elemento hospedado|Si el valor de <xref:System.Drawing.Font.Italic%2A> es `true`, el valor de <xref:System.Windows.Controls.Control.FontStyle%2A> se establece en <xref:System.Windows.FontStyles.Italic%2A>.<br /><br /> Si el valor de <xref:System.Drawing.Font.Italic%2A> es `false`, el valor de <xref:System.Windows.Controls.Control.FontStyle%2A> se establece en <xref:System.Windows.FontStyles.Normal%2A>.|  
|<xref:System.Drawing.Font.Strikeout%2A>|<xref:System.Windows.TextDecorations>en elemento hospedado|Solo se aplica cuando se <xref:System.Windows.Controls.TextBlock> hospeda un control.|  
|<xref:System.Drawing.Font.Underline%2A>|<xref:System.Windows.TextDecorations>en elemento hospedado|Solo se aplica cuando se <xref:System.Windows.Controls.TextBlock> hospeda un control.|  
|<xref:System.Windows.Forms.Control.RightToLeft%2A><br /><br /> (<xref:System.Windows.Forms.RightToLeft?displayProperty=nameWithType>)|<xref:System.Windows.FrameworkElement.FlowDirection%2A><br /><br /> (<xref:System.Windows.FlowDirection>)|<xref:System.Windows.Forms.RightToLeft.No>se asigna <xref:System.Windows.FlowDirection.LeftToRight>a.<br /><br /> <xref:System.Windows.Forms.RightToLeft.Yes>se asigna <xref:System.Windows.FlowDirection.RightToLeft>a.|  
|<xref:System.Windows.Forms.Control.Visible%2A>|<xref:System.Windows.UIElement.Visibility%2A>|El <xref:System.Windows.Forms.Integration.ElementHost> control establece la <xref:System.Windows.UIElement.Visibility%2A> propiedad en el elemento hospedado mediante las siguientes reglas:<br /><br /> -   <xref:System.Windows.Forms.Control.Visible%2A> = `true`se asigna <xref:System.Windows.Visibility.Visible>a.<br />-   <xref:System.Windows.Forms.Control.Visible%2A> = `false`se asigna <xref:System.Windows.Visibility.Hidden>a.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md)
- [Interoperabilidad entre Windows Forms y WPF](wpf-and-windows-forms-interoperation.md)
- [Tutorial: Asignar propiedades mediante el elemento WindowsFormsHost](walkthrough-mapping-properties-using-the-windowsformshost-element.md)
- [Tutorial: Asignar propiedades mediante el control ElementHost](walkthrough-mapping-properties-using-the-elementhost-control.md)
