---
title: Consideraciones sobre el diseño del elemento WindowsFormsHost
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element layout considerations [WPF]
- dynamic layout [WPF interoperability]
- device-independent pixels
ms.assetid: 3c574597-bbde-440f-95cc-01371f1a5d9d
ms.openlocfilehash: 786e3adae6c5b8167fbba00aa140d4d728308dc5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="layout-considerations-for-the-windowsformshost-element"></a>Consideraciones sobre el diseño del elemento WindowsFormsHost
Este tema se describe cómo el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento interactúa con el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de diseño.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] admiten la lógica de diferentes, pero de forma similar, para calcular el tamaño y colocar elementos en un formulario o página. Cuando se crea una interfaz de usuario (UI) de híbrida que hospeda [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controla en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento integra los dos esquemas del diseño.  
  
## <a name="differences-in-layout-between-wpf-and-windows-forms"></a>Diferencias de diseño entre formularios Windows Forms y WPF  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa un diseño independiente de la resolución. Todos los [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dimensiones de diseño se especifican utilizando *píxeles independientes del dispositivo*. Un píxel independiente del dispositivo es un sexto noventa de una pulgada en tamaño y resolución independientes, por lo que se obtienen resultados similares independientemente de si está representando en un monitor de 72 ppp o una impresora de 19.200 PPP.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] También se basa en *diseño dinámico*. Esto significa que un elemento de interfaz de usuario se organiza en un formulario o página de acuerdo con su contenido, el contenedor de diseño principal y el tamaño de pantalla disponibles. Diseño dinámico facilita la localización ajustando automáticamente el tamaño y la posición de elementos de interfaz de usuario cuando las cadenas que contienen cambiar longitud.  
  
 Diseño de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] es dependiente del dispositivo y más probable que sean estáticos. Por lo general, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles se colocan estrictamente en un formulario de uso de dimensiones especificados en píxeles de hardware. Sin embargo, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] es compatible con algunas características de diseño dinámico, como se resume en la tabla siguiente.  
  
|Característica de diseño|Descripción|  
|--------------------|-----------------|  
|Cambiar automáticamente el tamaño|Algunos [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles de tamaño para mostrar su contenido correctamente. Para obtener más información, consulte [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).|  
|Delimitar y acoplar|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] los controles admiten la colocación y el dimensionamiento basados en el contenedor primario. Para obtener más información, consulte <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType> y <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>.|  
|Escala automática|Controles de contenedor de tamaño por sí mismos y sus elementos secundarios en función de la resolución del dispositivo de salida o el tamaño, en píxeles, de la fuente predeterminada del contenedor. Para obtener más información, consulte [el escalado automático en formularios Windows Forms](../../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md).|  
|Contenedores de diseño|El <xref:System.Windows.Forms.FlowLayoutPanel> y <xref:System.Windows.Forms.TableLayoutPanel> controles organiza sus controles secundarios y ajustan su tamaño según su contenido.|  
  
## <a name="layout-limitations"></a>Limitaciones de diseño  
 En general, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles no se puede escalar y transformar a la medida de lo posible en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. La siguiente lista describe las limitaciones conocidas cuando el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento intenta integrar su hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlar en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de diseño.  
  
-   En algunos casos no se puede cambiar el tamaño de los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] (o solo se pueden fijar unas dimensiones específicas). Por ejemplo, un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.ComboBox> control admite solo un alto, que se define según el tamaño de fuente del control. En un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diseño dinámico donde los elementos pueden ajustarse verticalmente, hospedados <xref:System.Windows.Forms.ComboBox> control no se ajustará según lo esperado.  
  
-   Los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no se pueden girar ni sesgar. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento provoca la <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> eventos si aplica una transformación de sesgo o la rotación. Si no controla la <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> eventos, un <xref:System.InvalidOperationException> se genera.  
  
-   En la mayoría de los casos, los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no admiten el escalado proporcional. Aunque las dimensiones generales del control se escalarán, los controles secundarios y los elementos de los componentes del control podrían no cambiar de tamaño según lo previsto. Esta limitación depende del grado de compatibilidad del escalado de cada control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Además, no es posible escalar [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles hasta un tamaño de 0 píxeles.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] los controles admiten escalado automático, en el que el formulario cambia de tamaño automáticamente y sus controles en función del tamaño de fuente. En una interfaz de usuario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], al cambiar el tamaño de fuente no se cambia el tamaño de todo el diseño, aunque es posible que algunos elementos cambien de tamaño dinámicamente.  
  
### <a name="z-order"></a>Orden Z  
 En una interfaz de usuario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], puede cambiar el orden z de los elementos para controlar el comportamiento de superposición. Los controles hospedados de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] se dibujan en un HWND independiente, por lo que siempre se dibujan en la parte superior de los elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Hospedados [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] también se dibujará el control sobre cualquier <xref:System.Windows.Documents.Adorner> elementos.  
  
## <a name="layout-behavior"></a>Comportamiento de diseño  
 Las siguientes secciones describen determinados aspectos del comportamiento de diseño al hospedar [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controla en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="scaling-unit-conversion-and-device-independence"></a>Ajuste de escala, la conversión de unidad y la independencia del dispositivo  
 Cada vez que la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento realiza operaciones que implican [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] relacionados con las dimensiones, dos sistemas de coordenadas: píxeles independientes del dispositivo para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y píxeles de hardware para [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Por lo tanto, debe aplicar la unidad adecuada y ajuste de escala en las conversiones para lograr un diseño coherente.  
  
 Conversión entre los sistemas de coordenadas depende de la resolución del dispositivo actual y de cualquier diseño o representación de las transformaciones aplicadas a la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento o sus antecesores.  
  
 Si el dispositivo de salida es de 96 PPP y no se ha aplicado ningún ajuste de escala a la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento, un píxel independiente del dispositivo es igual a un píxel de hardware.  
  
 Todos los demás casos requieren el ajuste de escala en sistema de coordenadas. No se cambia el tamaño del control hospedado. En su lugar, el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento intenta ajustar la escala del control hospedado y todos sus controles secundarios. Dado que [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no son totalmente compatibles con ajuste de escala, el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento escala al grado compatible con controles específicos.  
  
 Invalidar el <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A> método para proporcionar un comportamiento de ajuste de escala personalizado para el control de formularios Windows Forms hospedado.  
  
 Además del escalado, el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento controla los casos de redondeo y desbordamiento tal como se describe en la tabla siguiente.  
  
|Problema de conversión|Descripción|  
|----------------------|-----------------|  
|Redondeo|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dimensiones en píxeles independientes del dispositivo se especifican como `double`, y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] dimensiones de píxel de hardware se especifican como `int`. En casos donde `double`-dimensiones según se convierten en `int`-según las dimensiones, la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento utiliza el redondeo estándar, por lo que los valores fraccionarios menor que 0,5 se redondea a 0.|  
|Desbordamiento|Cuando el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento se convierte de `double` valores `int` desbordamiento de valores, es posible. Los valores mayores que <xref:System.Int32.MaxValue> se establecen en <xref:System.Int32.MaxValue>.|  
  
### <a name="layout-related-properties"></a>Propiedades relacionadas con el diseño  
 Propiedades que controlan el comportamiento de diseño en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementos se asignan correctamente por el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento. Para más información, vea [Asignación de propiedades en formularios Windows Forms y WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md).  
  
### <a name="layout-changes-in-the-hosted-control"></a>Cambios de diseño en el Control hospedado  
 Cambios de diseño en hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control se propagan a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para desencadenar actualizaciones del diseño. El <xref:System.Windows.UIElement.InvalidateMeasure%2A> método en <xref:System.Windows.Forms.Integration.WindowsFormsHost> garantiza que los cambios de diseño en el control hospedado invalidarán el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] motor de diseño para que se ejecute.  
  
### <a name="continuously-sized-windows-forms-controls"></a>Ajuste de tamaño continuo controles de Windows Forms  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles que admiten el ajuste de escala continuo totalmente interactúan con el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de diseño. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento utiliza el <xref:System.Windows.FrameworkElement.MeasureOverride%2A> y <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> métodos como de costumbre para cambiar el tamaño y organizar hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.  
  
### <a name="sizing-algorithm"></a>Algoritmo de ajuste de tamaño  
 El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento usa el siguiente procedimiento para cambiar el tamaño del control hospedado:  
  
1.  El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento invalida la <xref:System.Windows.FrameworkElement.MeasureOverride%2A> y <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> métodos.  
  
2.  Para determinar el tamaño del control hospedado, el <xref:System.Windows.FrameworkElement.MeasureOverride%2A> método llama el control hospedado <xref:System.Windows.Forms.Control.GetPreferredSize%2A> método con una restricción se convierte desde la restricción pasada a la <xref:System.Windows.FrameworkElement.MeasureOverride%2A> método.  
  
3.  El <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> método intenta establecer el control hospedado en la restricción del tamaño especificado.  
  
4.  Si el control hospedado <xref:System.Windows.Forms.Control.Size%2A> propiedad coincide con la restricción especificada, el control hospedado tiene un tamaño para la restricción.  
  
 Si el <xref:System.Windows.Forms.Control.Size%2A> propiedad no coincide con la restricción especificada, el control hospedado no admite el ajuste de tamaño continuo. Por ejemplo, el <xref:System.Windows.Forms.MonthCalendar> control sólo permite tamaños discretos. Los tamaños permitidos para este control consisten en números enteros (que representa el número de meses) para el alto y ancho. En casos como éste, el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento se comporta como sigue:  
  
-   Si el <xref:System.Windows.Forms.Control.Size%2A> propiedad devuelve un tamaño mayor que la restricción especificada, el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento recorta el control hospedado. Alto y ancho se tratan por separado, por lo que el control hospedado se puede recortar en cualquier dirección.  
  
-   Si el <xref:System.Windows.Forms.Control.Size%2A> propiedad devuelve un tamaño menor que la restricción especificada, <xref:System.Windows.Forms.Integration.WindowsFormsHost> acepta este valor de tamaño y devuelve el valor para el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de diseño.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Tutorial: Organizar controles de formularios Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-arranging-windows-forms-controls-in-wpf.md)  
 [Organizar Windows Forms en el ejemplo WPF](http://go.microsoft.com/fwlink/?LinkID=159971)  
 [Asignación de propiedades en formularios Windows Forms y WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [Migración e interoperabilidad](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
