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
ms.openlocfilehash: 89ed57a787b93a1326b4accd3bb1bc5ff9a825fd
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095156"
---
# <a name="layout-considerations-for-the-windowsformshost-element"></a>Consideraciones sobre el diseño del elemento WindowsFormsHost
En este tema se describe cómo interactúa el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> con el sistema de diseño de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y Windows Forms admiten una lógica diferente, pero similar, para el ajuste de tamaño y la posición de los elementos en un formulario o una página. Al crear una interfaz de usuario (IU) híbrida que hospede controles Windows Forms en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> integra los dos esquemas de diseño.  
  
## <a name="differences-in-layout-between-wpf-and-windows-forms"></a>Diferencias de diseño entre WPF y Windows Forms  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa el diseño independiente de la resolución. Todas las dimensiones de diseño [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se especifican mediante *píxeles independientes del dispositivo*. Un píxel independiente del dispositivo es de 90 a sexto cm de tamaño e independiente de la resolución, por lo que obtendrá resultados similares independientemente de si está representando en un monitor de 72 ppp o una impresora de 19.200 ppp.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también se basa en el *diseño dinámico*. Esto significa que un elemento de la interfaz de usuario se organiza en un formulario o una página según su contenido, su contenedor de diseño primario y el tamaño de pantalla disponible. El diseño dinámico facilita la localización ajustando automáticamente el tamaño y la posición de los elementos de la interfaz de usuario cuando las cadenas contienen la longitud del cambio.  
  
 El diseño en Windows Forms depende del dispositivo y es más probable que sea estático. Normalmente, los controles de Windows Forms se colocan de forma absoluta en un formulario mediante dimensiones especificadas en píxeles de hardware. Sin embargo, Windows Forms admite algunas características de diseño dinámico, como se resume en la tabla siguiente.  
  
|Característica de diseño|Descripción|  
|--------------------|-----------------|  
|Cambiar automáticamente|Algunos controles de Windows Forms cambian de tamaño para mostrar su contenido correctamente. Para obtener más información, vea [información general sobre la propiedad AutoSize](../../winforms/controls/autosize-property-overview.md).|  
|Delimitar y acoplar|Windows Forms controles admiten la colocación y el ajuste de tamaño según el contenedor primario. Para más información, vea <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType> y <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>.|  
|Escalado automático|Los controles de contenedor cambian de tamaño y sus elementos secundarios en función de la resolución del dispositivo de salida o el tamaño, en píxeles, de la fuente del contenedor predeterminado. Para obtener más información, vea [escalado automático en Windows Forms](../../winforms/automatic-scaling-in-windows-forms.md).|  
|Contenedores de diseño|Los controles <xref:System.Windows.Forms.FlowLayoutPanel> y <xref:System.Windows.Forms.TableLayoutPanel> organizan sus controles secundarios y su propio tamaño según su contenido.|  
  
## <a name="layout-limitations"></a>Limitaciones de diseño  
 En general, los controles de Windows Forms no se pueden escalar y transformar en la medida que sea posible en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. En la lista siguiente se describen las limitaciones conocidas cuando el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> intenta integrar su control de Windows Forms hospedado en el sistema de diseño de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- En algunos casos, no se puede cambiar el tamaño de los controles de Windows Forms o solo se puede ajustar a dimensiones específicas. Por ejemplo, un control de <xref:System.Windows.Forms.ComboBox> de Windows Forms admite un solo alto, que se define mediante el tamaño de fuente del control. En un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diseño dinámico en el que los elementos pueden ajustarse verticalmente, un control de <xref:System.Windows.Forms.ComboBox> hospedado no se ajustará según lo esperado.  
  
- Windows Forms controles no se pueden girar ni sesgar. El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> provoca el evento <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> si se aplica una transformación sesgado o giro. Si no controla el evento <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>, se genera un <xref:System.InvalidOperationException>.  
  
- En la mayoría de los casos, los controles de Windows Forms no admiten el escalado proporcional. Aunque las dimensiones generales del control se escalarán, los controles secundarios y los elementos de los componentes del control podrían no cambiar de tamaño según lo previsto. Esta limitación depende de cómo cada control Windows Forms admita el escalado. Además, no puede escalar Windows Forms controles hasta un tamaño de 0 píxeles.  
  
- Windows Forms controles admiten el escalado automático, en el que el formulario cambia automáticamente de tamaño y sus controles según el tamaño de fuente. En una interfaz de usuario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], al cambiar el tamaño de fuente no se cambia el tamaño de todo el diseño, aunque es posible que algunos elementos cambien de tamaño dinámicamente.  
  
### <a name="z-order"></a>Orden Z  
 En una interfaz de usuario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], puede cambiar el orden z de los elementos para controlar el comportamiento de superposición. Un control de Windows Forms hospedado se dibuja en un HWND independiente, por lo que siempre se dibuja encima de los elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Un control de Windows Forms hospedado también se dibuja encima de los elementos <xref:System.Windows.Documents.Adorner>.  
  
## <a name="layout-behavior"></a>Comportamiento de diseño  
 En las secciones siguientes se describen aspectos específicos del comportamiento de diseño al hospedar Windows Forms controles en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="scaling-unit-conversion-and-device-independence"></a>Escalado, conversión de unidades y independencia del dispositivo  
 Cada vez que el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> realiza operaciones que implican [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y Windows Forms dimensiones, se implican dos sistemas de coordenadas: píxeles independientes del dispositivo para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y píxeles de hardware para Windows Forms. Por lo tanto, debe aplicar las conversiones de escala y unidad adecuadas para lograr un diseño coherente.  
  
 La conversión entre los sistemas de coordenadas depende de la resolución actual del dispositivo y de las transformaciones de diseño o representación aplicadas al elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> o a sus antecesores.  
  
 Si el dispositivo de salida tiene 96 PPP y no se ha aplicado ningún ajuste de escala al elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, un píxel independiente del dispositivo es igual a un píxel de hardware.  
  
 Todos los demás casos requieren el escalado del sistema de coordenadas. No se cambia el tamaño del control hospedado. En su lugar, el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> intenta escalar el control hospedado y todos sus controles secundarios. Dado que Windows Forms no es totalmente compatible con el escalado, el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se escala hasta el grado admitido por controles concretos.  
  
 Invalide el método <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A> para proporcionar el comportamiento de escalado personalizado para el control de Windows Forms hospedado.  
  
 Además de escalar, el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> controla los casos de redondeo y de desbordamiento, tal y como se describe en la tabla siguiente.  
  
|Problema de conversión|Descripción|  
|----------------------|-----------------|  
|Redondeo|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dimensiones de píxeles independientes del dispositivo se especifican como `double`y Windows Forms dimensiones de píxeles de hardware se especifican como `int`. En los casos en los que las dimensiones basadas en `double`se convierten en dimensiones basadas en `int`, el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> utiliza el redondeo estándar, de modo que los valores fraccionarios inferiores a 0,5 se redondean a 0.|  
|Desbordamiento|Cuando el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> convierte de `double` valores a `int` valores, es posible que se produzca un desbordamiento. Los valores mayores que <xref:System.Int32.MaxValue> se establecen en <xref:System.Int32.MaxValue>.|  
  
### <a name="layout-related-properties"></a>Propiedades relacionadas con el diseño  
 Las propiedades que controlan el comportamiento del diseño en Windows Forms controles y elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se asignan correctamente mediante el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>. Para más información, vea [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="layout-changes-in-the-hosted-control"></a>Cambios de diseño en el control hospedado  
 Los cambios de diseño en el control de Windows Forms hospedado se propagan a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para desencadenar actualizaciones de diseño. El método <xref:System.Windows.UIElement.InvalidateMeasure%2A> en <xref:System.Windows.Forms.Integration.WindowsFormsHost> garantiza que los cambios de diseño en el control hospedado provoquen la ejecución del motor de diseño [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="continuously-sized-windows-forms-controls"></a>Controles de Windows Forms de tamaño continuo  
 Windows Forms controles que admiten el escalado continuo interactúan totalmente con el sistema de diseño de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> usa los métodos <xref:System.Windows.FrameworkElement.MeasureOverride%2A> y <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> como de costumbre para ajustar el tamaño y organizar el control de Windows Forms hospedado.  
  
### <a name="sizing-algorithm"></a>Algoritmo de ajuste de tamaño  
 El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> usa el procedimiento siguiente para cambiar el tamaño del control hospedado:  
  
1. El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> invalida los métodos <xref:System.Windows.FrameworkElement.MeasureOverride%2A> y <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>.  
  
2. Para determinar el tamaño del control hospedado, el método <xref:System.Windows.FrameworkElement.MeasureOverride%2A> llama al método de <xref:System.Windows.Forms.Control.GetPreferredSize%2A> del control hospedado con una restricción traducida a partir de la restricción pasada al método <xref:System.Windows.FrameworkElement.MeasureOverride%2A>.  
  
3. El método <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> intenta establecer el control hospedado en la restricción de tamaño especificada.  
  
4. Si la propiedad <xref:System.Windows.Forms.Control.Size%2A> del control hospedado coincide con la restricción especificada, se ajusta el tamaño del control hospedado a la restricción.  
  
 Si la propiedad <xref:System.Windows.Forms.Control.Size%2A> no coincide con la restricción especificada, el control hospedado no admite el ajuste de tamaño continuo. Por ejemplo, el control <xref:System.Windows.Forms.MonthCalendar> solo permite tamaños discretos. Los tamaños permitidos para este control constan de enteros (que representan el número de meses) para el alto y el ancho. En casos como este, el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se comporta de la siguiente manera:  
  
- Si la propiedad <xref:System.Windows.Forms.Control.Size%2A> devuelve un tamaño mayor que la restricción especificada, el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> recorta el control hospedado. El alto y el ancho se administran por separado, por lo que el control hospedado se puede recortar en cualquier dirección.  
  
- Si la propiedad <xref:System.Windows.Forms.Control.Size%2A> devuelve un tamaño menor que la restricción especificada, <xref:System.Windows.Forms.Integration.WindowsFormsHost> acepta este valor de tamaño y devuelve el valor al sistema de diseño de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Tutorial: Organizar controles de formularios Windows Forms en WPF](walkthrough-arranging-windows-forms-controls-in-wpf.md)
- [Ejemplo de cómo organizar controles Windows Forms en WPF](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WpfLayoutHostingWfWithXaml)
- [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md)
- [Migración e interoperabilidad](migration-and-interoperability.md)
