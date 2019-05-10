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
ms.openlocfilehash: 67698a0a45bdf84d36603cd1309a8dd5bce2f895
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598845"
---
# <a name="layout-considerations-for-the-windowsformshost-element"></a>Consideraciones sobre el diseño del elemento WindowsFormsHost
Este tema se describe cómo el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento interactúa con el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de diseño.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] admitir una lógica diferente, pero de forma similar, para ajustar el tamaño de los elementos y colocarlos en un formulario o página. Cuando se crea una interfaz de usuario (UI) de híbrido que hospeda [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controla en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento integra los dos esquemas del diseño.  
  
## <a name="differences-in-layout-between-wpf-and-windows-forms"></a>Diferencias de diseño entre WPF y Windows Forms  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa diseño independiente de la resolución. Todos los [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se especifican las dimensiones de diseño utilizando *píxeles independientes del dispositivo*. Un píxel independiente del dispositivo es un sexto noventa de una pulgada de tamaño y resolución independiente, por lo que obtendrá resultados similares independientemente de si está representando en un monitor de 72 ppp o una impresora 19.200 PPP.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] También se basa en *diseño dinámico*. Esto significa que un elemento de interfaz de usuario se organiza en un formulario o página de acuerdo con su contenido, el contenedor de diseño principal y el tamaño de pantalla disponibles. Diseño dinámico facilita la localización ajustando automáticamente el tamaño y posición de elementos de interfaz de usuario cuando las cadenas que contienen cambiar longitud.  
  
 Diseño en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] es dependiente del dispositivo y más probable que sea estática. Normalmente, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] los controles se colocan completamente en un formulario con dimensiones especificadas en píxeles de hardware. Sin embargo, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] es compatible con algunas características de diseño dinámico, como se resume en la tabla siguiente.  
  
|Característica de diseño|Descripción|  
|--------------------|-----------------|  
|Cambiar el tamaño automáticamente|Algunos [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles cambian de tamaño para mostrar su contenido correctamente. Para obtener más información, consulte [AutoSize Property Overview](../../winforms/controls/autosize-property-overview.md).|  
|Delimitar y acoplar|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] los controles permiten la colocación y tamaño basada en el contenedor primario. Para obtener más información, vea <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType> y <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>.|  
|Escalado automático|Cambiar el tamaño de controles del contenedor a sí mismos y sus elementos secundarios en función de la resolución del dispositivo de salida o el tamaño, en píxeles, de la fuente predeterminada del contenedor. Para obtener más información, consulte [el escalado automático en Windows Forms](../../winforms/automatic-scaling-in-windows-forms.md).|  
|Contenedores de diseño|El <xref:System.Windows.Forms.FlowLayoutPanel> y <xref:System.Windows.Forms.TableLayoutPanel> controles organiza sus controles secundarios y ajustan su tamaño según su contenido.|  
  
## <a name="layout-limitations"></a>Limitaciones de diseño  
 En general, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles no se pueden escalar y se transforma en la medida de lo posible [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. La siguiente lista describe las limitaciones conocidas cuando el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento intenta integrar su hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de diseño.  
  
- En algunos casos no se puede cambiar el tamaño de los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] (o solo se pueden fijar unas dimensiones específicas). Por ejemplo, un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.ComboBox> control admite sólo un alto, que se define según el tamaño de fuente del control. En un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diseño dinámico donde los elementos pueden ajustar verticalmente, hospedados <xref:System.Windows.Forms.ComboBox> control no se ajustará según lo previsto.  
  
- Los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no se pueden girar ni sesgar. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento provoca el <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> eventos si aplica una transformación de sesgo o una rotación. Si no controla el <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> evento, un <xref:System.InvalidOperationException> se genera.  
  
- En la mayoría de los casos, los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no admiten el escalado proporcional. Aunque las dimensiones generales del control se escalarán, los controles secundarios y los elementos de los componentes del control podrían no cambiar de tamaño según lo previsto. Esta limitación depende del grado de compatibilidad del escalado de cada control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Además, no es posible escalar [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles hasta un tamaño de 0 píxeles.  
  
- [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] los controles admiten el escalado automático, en el que el formulario cambia de tamaño automáticamente y sus controles en función del tamaño de fuente. En una interfaz de usuario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], al cambiar el tamaño de fuente no se cambia el tamaño de todo el diseño, aunque es posible que algunos elementos cambien de tamaño dinámicamente.  
  
### <a name="z-order"></a>Orden Z  
 En una interfaz de usuario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], puede cambiar el orden z de los elementos para controlar el comportamiento de superposición. Los controles hospedados de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] se dibujan en un HWND independiente, por lo que siempre se dibujan en la parte superior de los elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Hospedados [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control también se dibuja encima de cualquier <xref:System.Windows.Documents.Adorner> elementos.  
  
## <a name="layout-behavior"></a>Comportamiento de diseño  
 Las secciones siguientes describen los aspectos específicos del comportamiento de diseño al hospedar [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controla en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="scaling-unit-conversion-and-device-independence"></a>Independencia del dispositivo, unidades de conversión y escalado  
 Cada vez que el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento realiza las operaciones relacionadas con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] relacionados con las dimensiones, los dos sistemas de coordenadas: píxeles independientes del dispositivo para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y píxeles de hardware para [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Por lo tanto, debe aplicar la unidad adecuada y las conversiones de escalado para lograr un diseño coherente.  
  
 Conversión entre los sistemas de coordenadas depende de la resolución del dispositivo actual y cualquier diseño o transformaciones de representación se aplica a la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento o sus antecesores.  
  
 Si el dispositivo de salida es de 96 PPP y no se ha aplicado ningún ajuste de escala a la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento, un píxel independiente del dispositivo es igual a un píxel de hardware.  
  
 Todos los demás casos necesitan el escalado de sistema de coordenadas. No se cambia el tamaño del control hospedado. En su lugar, el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento intenta escalar el control hospedado y todos sus controles secundarios. Dado que [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no son totalmente compatibles con el escalado, el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento se puede escalar hasta el grado compatible con determinados controles.  
  
 Invalidar el <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A> método para proporcionar un comportamiento personalizado de escalado para el control hospedado de Windows Forms.  
  
 Además de escalar, la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento controla los casos de redondeo y desbordamiento tal como se describe en la tabla siguiente.  
  
|Problema de conversión|Descripción|  
|----------------------|-----------------|  
|Redondeo|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dimensiones en píxeles independientes del dispositivo se especifican como `double`, y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] dimensiones de píxeles de hardware se especifican como `int`. En casos donde `double`-en función de las dimensiones se convierten en `int`-según las dimensiones, la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento usa el redondeo estándar, por lo que los valores fraccionarios menor que 0,5 se redondean a 0.|  
|Desbordamiento|Cuando el <xref:System.Windows.Forms.Integration.WindowsFormsHost> convierte el elemento de `double` valores `int` desbordamiento de valores, es posible. Los valores mayores que <xref:System.Int32.MaxValue> se establecen en <xref:System.Int32.MaxValue>.|  
  
### <a name="layout-related-properties"></a>Propiedades relacionadas con el diseño  
 Las propiedades que controlan el comportamiento de diseño en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementos se asignan correctamente por el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento. Para más información, vea [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="layout-changes-in-the-hosted-control"></a>Cambios de diseño en el Control hospedado  
 Los cambios de diseño en hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control se propagan a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para desencadenar las actualizaciones de diseño. El <xref:System.Windows.UIElement.InvalidateMeasure%2A> método <xref:System.Windows.Forms.Integration.WindowsFormsHost> garantiza que los cambios de diseño en el control hospedado invalidarán el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] motor de diseño para ejecutar.  
  
### <a name="continuously-sized-windows-forms-controls"></a>Tamaño continuamente los controles de formularios Windows Forms  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] los controles que admiten el escalado continua totalmente interactúan con el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de diseño. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento utiliza la <xref:System.Windows.FrameworkElement.MeasureOverride%2A> y <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> métodos como de costumbre para cambiar el tamaño y organizar hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.  
  
### <a name="sizing-algorithm"></a>Algoritmo de ajuste de tamaño  
 El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento usa el siguiente procedimiento para cambiar el tamaño del control hospedado:  
  
1. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento invalida la <xref:System.Windows.FrameworkElement.MeasureOverride%2A> y <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> métodos.  
  
2. Para determinar el tamaño del control hospedado, el <xref:System.Windows.FrameworkElement.MeasureOverride%2A> método llama el control hospedado <xref:System.Windows.Forms.Control.GetPreferredSize%2A> traduce método con una restricción de la restricción pasa a la <xref:System.Windows.FrameworkElement.MeasureOverride%2A> método.  
  
3. El <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> método intenta establecer el control hospedado en la restricción del tamaño especificado.  
  
4. Si el control hospedado <xref:System.Windows.Forms.Control.Size%2A> propiedad coincide con la restricción especificada, el control hospedado tiene un tamaño para la restricción.  
  
 Si el <xref:System.Windows.Forms.Control.Size%2A> propiedad no coincide con la restricción especificada, el control hospedado no admite el ajuste de tamaño continuo. Por ejemplo, el <xref:System.Windows.Forms.MonthCalendar> control sólo permite tamaños discretos. Los tamaños permitidos para este control consisten en números enteros (que representa el número de meses) para el alto y ancho. En casos como este, el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento se comporta como sigue:  
  
- Si el <xref:System.Windows.Forms.Control.Size%2A> propiedad devuelve un tamaño mayor que la restricción especificada, el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento recorta el control hospedado. Alto y ancho se tratan por separado, por lo que es posible que se recorta el control hospedado en cualquier dirección.  
  
- Si el <xref:System.Windows.Forms.Control.Size%2A> propiedad devuelve un tamaño menor que la restricción especificada, <xref:System.Windows.Forms.Integration.WindowsFormsHost> acepta este valor de tamaño y devuelve el valor para el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de diseño.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Tutorial: Organización de Windows Forms en WPF](walkthrough-arranging-windows-forms-controls-in-wpf.md)
- [Organización de Windows Forms en WPF ejemplo](https://go.microsoft.com/fwlink/?LinkID=159971)
- [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md)
- [Migración e interoperabilidad](migration-and-interoperability.md)
