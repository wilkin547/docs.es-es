---
title: Solución de problemas de aplicaciones híbridas
ms.date: 03/30/2017
helpviewer_keywords:
- overlapping controls [WPF]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid applications [WPF interoperability]
- message loops [WPF]
ms.assetid: f440c23f-fa5d-4d5a-852f-ba61150e6405
ms.openlocfilehash: b85a607d2e44d6253359a81118f90e6ee05d2d3f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187326"
---
# <a name="troubleshooting-hybrid-applications"></a>Solución de problemas de aplicaciones híbridas
<a name="introduction"></a>En este tema se enumeran algunos problemas comunes que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pueden producirse al crear aplicaciones híbridas, que usan tecnologías de Windows Forms y Windows Forms.  

<a name="overlapping_controls"></a>
## <a name="overlapping-controls"></a>Controles superpuestos  
 Los controles no se pueden superponer como cabría esperar. Windows Forms usa un HWND independiente para cada control. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa un HWND para todo el contenido de una página. Esta diferencia de implementación da lugar a comportamientos de superposición inesperados.  
  
 Un control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] formularios Windows Forms [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedado en siempre aparece encima del contenido.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]contenido hospedado <xref:System.Windows.Forms.Integration.ElementHost> en un control aparece en <xref:System.Windows.Forms.Integration.ElementHost> el orden z del control. Es posible superponer <xref:System.Windows.Forms.Integration.ElementHost> controles, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pero el contenido hospedado no combina ni interactúa.  
  
<a name="child_property"></a>
## <a name="child-property"></a>Child Property  
 Las <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Forms.Integration.ElementHost> clases y pueden hospedar solo un único control secundario o elemento. Para hospedar más de un control o elemento, se debe usar un contenedor como contenido secundario. Por ejemplo, puede agregar controles de botón <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> y casilla de verificación <xref:System.Windows.Forms.Integration.WindowsFormsHost> de <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> formularios Windows Forms a un control y, a continuación, asignar el panel a la propiedad de un control. Sin embargo, no puede agregar los controles <xref:System.Windows.Forms.Integration.WindowsFormsHost> de botón y casilla de verificación por separado al mismo control.  
  
<a name="scaling"></a>
## <a name="scaling"></a>Ampliación  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]y Windows Forms tienen diferentes modelos de escalado. Algunas [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] transformaciones de escalado son significativas para los controles de formularios Windows Forms, pero otras no. Por ejemplo, escalar un control de formularios Windows Forms a 0 funcionará, pero si intenta escalar el mismo control a un valor distinto de cero, el tamaño del control sigue siendo 0. Para más información, vea [Consideraciones sobre el diseño del elemento WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="adapter"></a>
## <a name="adapter"></a>Adapter (Adaptador)  
 Puede haber confusión <xref:System.Windows.Forms.Integration.WindowsFormsHost> al <xref:System.Windows.Forms.Integration.ElementHost> trabajar las clases, porque incluyen un contenedor oculto. Las <xref:System.Windows.Forms.Integration.WindowsFormsHost> clases y <xref:System.Windows.Forms.Integration.ElementHost> tienen un contenedor oculto, denominado *adaptador,* que usan para hospedar contenido. Para <xref:System.Windows.Forms.Integration.WindowsFormsHost> el elemento, el adaptador <xref:System.Windows.Forms.ContainerControl?displayProperty=nameWithType> deriva de la clase. Para <xref:System.Windows.Forms.Integration.ElementHost> el control, el adaptador <xref:System.Windows.Controls.DockPanel> deriva del elemento. Cuando se encuentren referencias al adaptador en otros temas sobre interoperación, se refieren a este contenedor.  
  
<a name="nesting"></a>
## <a name="nesting"></a>Anidamiento  
 No se <xref:System.Windows.Forms.Integration.WindowsFormsHost> admite <xref:System.Windows.Forms.Integration.ElementHost> el anidamiento de un elemento dentro de un control. Tampoco <xref:System.Windows.Forms.Integration.ElementHost> se admite <xref:System.Windows.Forms.Integration.WindowsFormsHost> el anidamiento de un control dentro de un elemento.  
  
<a name="focus"></a>
## <a name="focus"></a>Focus  
 El foco [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funciona de forma diferente en Windows Forms, lo que significa que pueden producirse problemas de foco en una aplicación híbrida. Por ejemplo, si tiene <xref:System.Windows.Forms.Integration.WindowsFormsHost> el foco dentro de un elemento y minimiza y restaura <xref:System.Windows.Forms.Integration.WindowsFormsHost> la página o muestra un cuadro de diálogo modal, el foco dentro del elemento puede perderse. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento todavía tiene el foco, pero el control dentro de él puede no.  
  
 El foco también afecta a la validación de datos. La validación <xref:System.Windows.Forms.Integration.WindowsFormsHost> funciona en un elemento, pero no <xref:System.Windows.Forms.Integration.WindowsFormsHost> funciona como ficha <xref:System.Windows.Forms.Integration.WindowsFormsHost> fuera del elemento, o entre dos elementos diferentes.  
  
<a name="property_mapping"></a>
## <a name="property-mapping"></a>Asignación de propiedades  
 Algunas asignaciones de propiedades requieren una interpretación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] exhaustiva para establecer un puente entre las tecnologías y Windows Forms. Las asignaciones de propiedad permiten que el código reaccione ante los cambios de fuentes, colores y otras propiedades. En general, las asignaciones de propiedad funcionan realizando escuchas para detectar eventos *Propiedad*Changed o llamadas a On*Propiedad*Changed, y estableciendo las propiedades adecuadas en el control secundario o en su adaptador. Para más información, vea [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md).  
  
<a name="layoutrelated_properties_on_hosted_content"></a>
## <a name="layout-related-properties-on-hosted-content"></a>Propiedades relacionadas con el diseño en el contenido hospedado  
 Cuando <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A?displayProperty=nameWithType> se <xref:System.Windows.Forms.Integration.ElementHost.Child%2A?displayProperty=nameWithType> asigna la propiedad o, se establecen automáticamente varias propiedades relacionadas con el diseño en el contenido hospedado. Cambiar estas propiedades de contenido puede producir comportamientos de diseño inesperados.  
  
 El contenido hospedado se acopla para rellenar el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento primario. <xref:System.Windows.Forms.Integration.ElementHost> Para habilitar este comportamiento de relleno, se establecen varias propiedades al establecer la propiedad secundaria. En la tabla siguiente se enumeran <xref:System.Windows.Forms.Integration.ElementHost> <xref:System.Windows.Forms.Integration.WindowsFormsHost> las propiedades de contenido establecidas por las clases y.  
  
|Clase de host|Propiedades de contenido|  
|----------------|------------------------|  
|<xref:System.Windows.Forms.Integration.ElementHost>|<xref:System.Windows.FrameworkElement.Height%2A><br /><br /> <xref:System.Windows.FrameworkElement.Width%2A><br /><br /> <xref:System.Windows.FrameworkElement.Margin%2A><br /><br /> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A><br /><br /> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>|  
|<xref:System.Windows.Forms.Integration.WindowsFormsHost>|<xref:System.Windows.Forms.Control.Margin%2A><br /><br /> <xref:System.Windows.Forms.Control.Dock%2A><br /><br /> <xref:System.Windows.Forms.Control.AutoSize%2A><br /><br /> <xref:System.Windows.Forms.Control.Location%2A><br /><br /> <xref:System.Windows.Forms.Control.MaximumSize%2A>|  
  
 No establezca estas propiedades directamente en el contenido hospedado. Para más información, vea [Consideraciones sobre el diseño del elemento WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="navigation_applications"></a>
## <a name="navigation-applications"></a>Aplicaciones de navegación  
 Es posible que las aplicaciones de navegación no mantengan el estado del usuario. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento vuelve a crear sus controles cuando se utiliza en una aplicación de navegación. La recreación de controles secundarios se produce cuando <xref:System.Windows.Forms.Integration.WindowsFormsHost> el usuario se aleja de la página que hospeda el elemento y, a continuación, vuelve a él. Todo el contenido que el usuario haya escrito se perderá.  
  
<a name="message_loop_interoperation"></a>
## <a name="message-loop-interoperation"></a>Interoperación de bucles de mensajes  
 Cuando se trabaja con bucles de mensajes de formularios Windows Forms, es posible que los mensajes no se procesen como se esperaba. El <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> constructor llama <xref:System.Windows.Forms.Integration.WindowsFormsHost> al método. Este método agrega un filtro de mensajes al bucle de mensajes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Este filtro <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> llama al <xref:System.Windows.Forms.Control?displayProperty=nameWithType> método si a era el destino del mensaje y traduce/distribuye el mensaje.  
  
 Si muestra <xref:System.Windows.Window> un bucle de mensajes <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>en formularios Windows Forms <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> con , no puede escribir nada a menos que llame al método. El <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> método <xref:System.Windows.Window> toma un <xref:System.Windows.Forms.IMessageFilter?displayProperty=nameWithType>y agrega un , que redirige [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] los mensajes relacionados con la clave al bucle de mensajes. Para más información, vea [Arquitectura de entrada de interoperabilidad entre formularios Windows Forms y WPF](windows-forms-and-wpf-interoperability-input-architecture.md).  
  
<a name="opacity_and_layering"></a>
## <a name="opacity-and-layering"></a>Opacidad y disposición en capas  
 La <xref:System.Windows.Interop.HwndHost> clase no admite capas. Esto significa que <xref:System.Windows.UIElement.Opacity%2A> establecer <xref:System.Windows.Forms.Integration.WindowsFormsHost> la propiedad en el elemento no [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tiene ningún <xref:System.Windows.Window.AllowsTransparency%2A> efecto `true`y no se producirá ninguna fusión con otras ventanas que se han establecido en .  
  
<a name="dispose"></a>
## <a name="dispose"></a>Dispose  
 No desechar correctamente las clases puede hacer que se pierdan recursos. En las aplicaciones híbridas, <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Forms.Integration.ElementHost> asegúrese de que las clases y se eliminan, o podría perder recursos. Windows Forms <xref:System.Windows.Forms.Integration.ElementHost> Windows Forms elimina <xref:System.Windows.Forms.Form> los controles cuando se cierra su elemento primario no modal. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]elimina <xref:System.Windows.Forms.Integration.WindowsFormsHost> los elementos cuando se cierra la aplicación. Es posible mostrar <xref:System.Windows.Forms.Integration.WindowsFormsHost> un elemento <xref:System.Windows.Window> en un bucle de mensajes de formularios Windows Forms. En este caso, es posible que el código no reciba la notificación de que la aplicación se está cerrando.  
  
<a name="enabling_visual_styles"></a>
## <a name="enabling-visual-styles"></a>Habilitar los estilos visuales  
 Es posible que los estilos visuales de Microsoft Windows XP en un control de formularios Windows Forms no estén habilitados. Se <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> llama al método en la plantilla para una aplicación de Windows Forms. Aunque no se llama a este método de forma predeterminada, si usa Visual Studio para crear un proyecto, obtendrá estilos visuales de Microsoft Windows XP para los controles, si la versión 6.0 de Comctl32.dll está disponible. Debe llamar <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> al método antes de crear identificadores en el subproceso. Para más información, vea [Cómo: Habilitar estilos visuales en una aplicación híbrida](how-to-enable-visual-styles-in-a-hybrid-application.md).  
  
<a name="licensed_controls"></a>
## <a name="licensed-controls"></a>Controles con licencia  
 Los controles de formularios Windows Forms con licencia que muestran información de licencias en un cuadro de mensaje al usuario pueden provocar un comportamiento inesperado para una aplicación híbrida. Algunos controles con licencia muestran un cuadro de diálogo como respuesta a la creación de controladores. Por ejemplo, un control con licencia podría informar al usuario de que se requiere una licencia o de que al usuario le quedan tres usos de prueba del control.  
  
 El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento deriva <xref:System.Windows.Interop.HwndHost> de la clase y el identificador del <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> control secundario se crea dentro del método. La <xref:System.Windows.Interop.HwndHost> clase no permite que los <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> mensajes se procesen en el método, pero mostrar un cuadro de diálogo hace que se envíen mensajes. Para habilitar este escenario <xref:System.Windows.Forms.Control.CreateControl%2A?displayProperty=nameWithType> de licencia, llame al <xref:System.Windows.Forms.Integration.WindowsFormsHost> método en el control antes de asignarlo como elemento secundario del elemento.  
  
<a name="wpf_designer"></a>
## <a name="wpf-designer"></a>WPF Designer  
 Puede diseñar el contenido de WPFWPF mediante el Diseñador wpfWPF para Visual Studio. En las secciones siguientes se enumeran algunos problemas comunes que pueden producirse al crear aplicaciones híbridas con WPF Designer.  
  
### <a name="backcolortransparent-is-ignored-at-design-time"></a>BackColorTransparent se omite en tiempo de diseño  
 Es <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> posible que la propiedad no funcione como se esperaba en tiempo de diseño.  
  
 Si un WPFWPF control no está en un <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> elemento primario visible, el tiempo de ejecución de WPFWPF omite el valor. La razón <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> que se <xref:System.Windows.Forms.Integration.ElementHost> puede omitir es <xref:System.AppDomain>porque el objeto se crea en un archivo . Sin embargo, cuando <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> se ejecuta la aplicación, funciona según lo esperado.  
  
### <a name="design-time-error-list-appears-when-the-obj-folder-is-deleted"></a>Aparece la lista de errores en tiempo de diseño cuando se elimina la carpeta obj  
 Si se elimina la carpeta obj, aparece la lista de errores en tiempo de diseño.  
  
 Al diseñar <xref:System.Windows.Forms.Integration.ElementHost>con , el Diseñador de Windows Forms usa archivos generados en la carpeta Depurar o Liberar dentro de la carpeta obj del proyecto. Si se eliminan estos archivos, aparece la lista de errores en tiempo de diseño. Para corregir este problema, recompile el proyecto. Para más información, vea [Errores en tiempo de diseño en el Diseñador de Windows Forms](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md).  
  
<a name="elementhost_and_ime"></a>
## <a name="elementhost-and-ime"></a>ElementHost e IME  
 WPFWPF controles <xref:System.Windows.Forms.Integration.ElementHost> hospedados en <xref:System.Windows.Forms.Control.ImeMode%2A> un actualmente no admiten la propiedad. Los <xref:System.Windows.Forms.Control.ImeMode%2A> controles hospedados omitirán los cambios en.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Interoperabilidad en WPF Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628658(v=vs.100))
- [Arquitectura de entrada de interoperabilidad entre formularios Windows Forms y WPF](windows-forms-and-wpf-interoperability-input-architecture.md)
- [Cómo: Habilitar estilos visuales en una aplicación híbrida](how-to-enable-visual-styles-in-a-hybrid-application.md)
- [Consideraciones sobre el diseño del elemento WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md)
- [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md)
- [Errores en tiempo de diseño en el Diseñador de Windows Forms](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md)
- [Migración e interoperabilidad](migration-and-interoperability.md)
