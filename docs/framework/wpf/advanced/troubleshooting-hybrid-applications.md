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
ms.openlocfilehash: 707e77ac69878c1c7fb8e975c1f90ad657228d1a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079680"
---
# <a name="troubleshooting-hybrid-applications"></a>Solución de problemas de aplicaciones híbridas
<a name="introduction"></a> En este tema se enumeran algunos problemas comunes que se pueden producir al crear aplicaciones híbridas, que usan las dos tecnologías, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  

<a name="overlapping_controls"></a>   
## <a name="overlapping-controls"></a>Controles superpuestos  
 Los controles no se pueden superponer como cabría esperar. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] usa un HWND independiente para cada control. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa un HWND para todo el contenido de una página. Esta diferencia de implementación da lugar a comportamientos de superposición inesperados.  
  
 Un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] siempre aparece encima del contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido hospedado en un <xref:System.Windows.Forms.Integration.ElementHost> control aparece en el orden z de la <xref:System.Windows.Forms.Integration.ElementHost> control. Es posible superponer <xref:System.Windows.Forms.Integration.ElementHost> controles, pero hospedado [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido no se combina ni interactúa.  
  
<a name="child_property"></a>   
## <a name="child-property"></a>Child Property  
 El <xref:System.Windows.Forms.Integration.WindowsFormsHost> y <xref:System.Windows.Forms.Integration.ElementHost> clases pueden hospedar únicamente un solo control o elemento secundario. Para hospedar más de un control o elemento, se debe usar un contenedor como contenido secundario. Por ejemplo, podría agregar [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles de botón y casilla de verificación para un <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> controlar y, a continuación, asignar el panel a un <xref:System.Windows.Forms.Integration.WindowsFormsHost> del control <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> propiedad. Sin embargo, no se puede agregar los controles de botón y casilla por separado al mismo <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.  
  
<a name="scaling"></a>   
## <a name="scaling"></a>Cambiar escala  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tienen modelos diferentes de escala. Algunas transformaciones de escala de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] resultan lógicas para los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], pero otras no. Por ejemplo, ajustar la escala de un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] a 0 funcionará, pero si se intenta ajustar la escala del mismo control a un valor distinto de cero, el tamaño del control sigue siendo 0. Para más información, vea [Consideraciones sobre el diseño del elemento WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="adapter"></a>   
## <a name="adapter"></a>Adaptador  
 Puede producirse confusión al trabajar el <xref:System.Windows.Forms.Integration.WindowsFormsHost> y <xref:System.Windows.Forms.Integration.ElementHost> clases, porque incluyen un contenedor oculto. Tanto el <xref:System.Windows.Forms.Integration.WindowsFormsHost> y <xref:System.Windows.Forms.Integration.ElementHost> clases tienen un contenedor oculto, denominado un *adaptador*, que utiliza para hospedar contenido. Para el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento, el adaptador se deriva de la <xref:System.Windows.Forms.ContainerControl?displayProperty=nameWithType> clase. Para el <xref:System.Windows.Forms.Integration.ElementHost> control, el adaptador se deriva de la <xref:System.Windows.Controls.DockPanel> elemento. Cuando se encuentren referencias al adaptador en otros temas sobre interoperación, se refieren a este contenedor.  
  
<a name="nesting"></a>   
## <a name="nesting"></a>Anidamiento  
 Anidar un <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento dentro de un <xref:System.Windows.Forms.Integration.ElementHost> no se admite el control. Anidar un <xref:System.Windows.Forms.Integration.ElementHost> control dentro de un <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento tampoco se admite.  
  
<a name="focus"></a>   
## <a name="focus"></a>Foco  
 El foco funciona de manera diferente en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], lo que significa que pueden producirse problemas de foco en una aplicación híbrida. Por ejemplo, si tiene el foco dentro un <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento y bien minimizar y restaurar la página o mostrar un cuadro de diálogo modal, centrarse en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento podrían perderse. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento todavía tiene el foco, pero el control dentro de él, es posible que no.  
  
 El foco también afecta a la validación de datos. Validación funciona en un <xref:System.Windows.Forms.Integration.WindowsFormsHost> , pero no funciona pestaña fuera de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento, o entre dos diferentes <xref:System.Windows.Forms.Integration.WindowsFormsHost> elementos.  
  
<a name="property_mapping"></a>   
## <a name="property-mapping"></a>Asignación de propiedades  
 Algunas asignaciones de propiedades requieren una ardua labor de interpretación a fin de salvar las diferencias de implementación entre ambas tecnologías, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Las asignaciones de propiedad permiten que el código reaccione ante los cambios de fuentes, colores y otras propiedades. En general, las asignaciones de propiedad funcionan realizando escuchas para detectar eventos *Propiedad*Changed o llamadas a On*Propiedad*Changed, y estableciendo las propiedades adecuadas en el control secundario o en su adaptador. Para más información, vea [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md).  
  
<a name="layoutrelated_properties_on_hosted_content"></a>   
## <a name="layout-related-properties-on-hosted-content"></a>Propiedades relacionadas con el diseño en el contenido hospedado  
 Cuando el <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.Integration.ElementHost.Child%2A?displayProperty=nameWithType> se asigna la propiedad, se establecen automáticamente varias propiedades relacionadas con el diseño en el contenido hospedado. Cambiar estas propiedades de contenido puede producir comportamientos de diseño inesperados.  
  
 El contenido hospedado se acopla para rellenar el <xref:System.Windows.Forms.Integration.WindowsFormsHost> y <xref:System.Windows.Forms.Integration.ElementHost> primario. Para habilitar este comportamiento de relleno, se establecen varias propiedades al establecer la propiedad secundaria. La siguiente tabla muestra que se establecen las propiedades de contenido mediante el <xref:System.Windows.Forms.Integration.ElementHost> y <xref:System.Windows.Forms.Integration.WindowsFormsHost> clases.  
  
|Clase de host|Propiedades de contenido|  
|----------------|------------------------|  
|<xref:System.Windows.Forms.Integration.ElementHost>|<xref:System.Windows.FrameworkElement.Height%2A><br /><br /> <xref:System.Windows.FrameworkElement.Width%2A><br /><br /> <xref:System.Windows.FrameworkElement.Margin%2A><br /><br /> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A><br /><br /> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>|  
|<xref:System.Windows.Forms.Integration.WindowsFormsHost>|<xref:System.Windows.Forms.Control.Margin%2A><br /><br /> <xref:System.Windows.Forms.Control.Dock%2A><br /><br /> <xref:System.Windows.Forms.Control.AutoSize%2A><br /><br /> <xref:System.Windows.Forms.Control.Location%2A><br /><br /> <xref:System.Windows.Forms.Control.MaximumSize%2A>|  
  
 No establezca estas propiedades directamente en el contenido hospedado. Para más información, vea [Consideraciones sobre el diseño del elemento WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="navigation_applications"></a>   
## <a name="navigation-applications"></a>Aplicaciones de navegación  
 Es posible que las aplicaciones de navegación no mantengan el estado del usuario. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento vuelve a crear sus controles cuando se usa en una aplicación de navegación. Volver a crear los controles secundarios se produce cuando el usuario navega fuera de la página que hospeda el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento y, a continuación, devuelve a él. Todo el contenido que el usuario haya escrito se perderá.  
  
<a name="message_loop_interoperation"></a>   
## <a name="message-loop-interoperation"></a>Interoperación de bucles de mensajes  
 Cuando se trabaja con bucles de mensajes de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], es posible que los mensajes no se procesen de la forma esperada. El <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> llama al método el <xref:System.Windows.Forms.Integration.WindowsFormsHost> constructor. Este método agrega un filtro de mensajes al bucle de mensajes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Este filtro llama a la <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> método si un <xref:System.Windows.Forms.Control?displayProperty=nameWithType> era el destino del mensaje y convierte o envía el mensaje.  
  
 Si se muestra un <xref:System.Windows.Window> en un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] bucle de mensajes con <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>, no se puede escribir nada a menos que llame a la <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> método. El <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> método toma un <xref:System.Windows.Window> y agrega un <xref:System.Windows.Forms.IMessageFilter?displayProperty=nameWithType>, que vuelve a enrutar los mensajes relacionados con la clave para el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bucle de mensajes. Para más información, vea [Arquitectura de entrada de interoperabilidad entre formularios Windows Forms y WPF](windows-forms-and-wpf-interoperability-input-architecture.md).  
  
<a name="opacity_and_layering"></a>   
## <a name="opacity-and-layering"></a>Opacidad y disposición en capas  
 La <xref:System.Windows.Interop.HwndHost> clase no admite la disposición en capas. Esto significa que esa configuración la <xref:System.Windows.UIElement.Opacity%2A> propiedad en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento no tiene ningún efecto y se producirá ninguna mezcla con otros [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] windows que tienen <xref:System.Windows.Window.AllowsTransparency%2A> establecido en `true`.  
  
<a name="dispose"></a>   
## <a name="dispose"></a>Desechar  
 No desechar correctamente las clases puede hacer que se pierdan recursos. En las aplicaciones híbridas, asegúrese de que el <xref:System.Windows.Forms.Integration.WindowsFormsHost> y <xref:System.Windows.Forms.Integration.ElementHost> clases se eliminan o se podrían producir pérdida de recursos. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] desecha <xref:System.Windows.Forms.Integration.ElementHost> controla cuándo su no modal <xref:System.Windows.Forms.Form> primario se cierra. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] desecha <xref:System.Windows.Forms.Integration.WindowsFormsHost> elementos cuando se cierra la aplicación. Es posible mostrar un <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento en un <xref:System.Windows.Window> en un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] bucle de mensajes. En este caso, es posible que el código no reciba la notificación de que la aplicación se está cerrando.  
  
<a name="enabling_visual_styles"></a>   
## <a name="enabling-visual-styles"></a>Habilitar los estilos visuales  
 Es posible que los elementos visuales de [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] no estén habilitados en un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. El <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> se llama al método en la plantilla para un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] aplicación. Aunque este método no se llama de forma predeterminada, si usa [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] para crear un proyecto, obtendrá los elementos visuales de [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] para los controles, si está disponible la versión 6.0 de Comctl32.dll. Debe llamar a la <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> método antes de que se creen los controladores en el subproceso. Para obtener más información, vea [Cómo: Habilitar estilos visuales en una aplicación híbrida](how-to-enable-visual-styles-in-a-hybrid-application.md).  
  
<a name="licensed_controls"></a>   
## <a name="licensed-controls"></a>Controles con licencia  
 Los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] con licencia que muestran información de licencia en un cuadro de mensaje al usuario pueden provocar un comportamiento inesperado en una aplicación híbrida. Algunos controles con licencia muestran un cuadro de diálogo como respuesta a la creación de controladores. Por ejemplo, un control con licencia podría informar al usuario de que se requiere una licencia o de que al usuario le quedan tres usos de prueba del control.  
  
 El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento se deriva de la <xref:System.Windows.Interop.HwndHost> clase y el identificador del control secundario se crea dentro de la <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> método. El <xref:System.Windows.Interop.HwndHost> clase no permite los mensajes se procesen en el <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> método, pero muestra un cuadro de diálogo hace que los mensajes se envíen. Para habilitar este escenario de licencias, llame a la <xref:System.Windows.Forms.Control.CreateControl%2A?displayProperty=nameWithType> método en el control antes de asignarlo como el <xref:System.Windows.Forms.Integration.WindowsFormsHost> secundario del elemento.  
  
<a name="wpf_designer"></a>   
## <a name="wpf-designer"></a>WPF Designer  
 Puede diseñar el contenido de WPF mediante [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]. En las secciones siguientes se indican algunos problemas comunes que se pueden producir al crear aplicaciones híbridas con [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
### <a name="backcolortransparent-is-ignored-at-design-time"></a>BackColorTransparent se omite en tiempo de diseño  
 El <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> propiedad podría no funcionar según lo previsto en tiempo de diseño.  
  
 Si un control WPF no está en un elemento primario visible, el tiempo de ejecución WPF omite el <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> valor. La razón por la que <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> puede omitirse porque <xref:System.Windows.Forms.Integration.ElementHost> se crea el objeto en otro <xref:System.AppDomain>. Sin embargo, al ejecutar la aplicación, <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> funcionan según lo previsto.  
  
### <a name="design-time-error-list-appears-when-the-obj-folder-is-deleted"></a>Aparece la lista de errores en tiempo de diseño cuando se elimina la carpeta obj  
 Si se elimina la carpeta obj, aparece la lista de errores en tiempo de diseño.  
  
 Al diseñar mediante <xref:System.Windows.Forms.Integration.ElementHost>, el Diseñador de Windows Forms usa los archivos generados en la carpeta Debug o Release en la carpeta del proyecto obj. Si se eliminan estos archivos, aparece la lista de errores en tiempo de diseño. Para corregir este problema, recompile el proyecto. Para más información, vea [Errores en tiempo de diseño en el Diseñador de Windows Forms](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md).  
  
<a name="elementhost_and_ime"></a>   
## <a name="elementhost-and-ime"></a>ElementHost e IME  
 Controles de WPF hospedan en un <xref:System.Windows.Forms.Integration.ElementHost> actualmente no se admite el <xref:System.Windows.Forms.Control.ImeMode%2A> propiedad. Cambia a <xref:System.Windows.Forms.Control.ImeMode%2A> los controles hospedados omitirán.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Interoperabilidad en WPF Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628658(v=vs.100))
- [Arquitectura de entrada de interoperabilidad entre formularios Windows Forms y WPF](windows-forms-and-wpf-interoperability-input-architecture.md)
- [Cómo: Habilitar estilos visuales en una aplicación híbrida](how-to-enable-visual-styles-in-a-hybrid-application.md)
- [Consideraciones sobre el diseño del elemento WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md)
- [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md)
- [Errores en tiempo de diseño en el Diseñador de Windows Forms](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md)
- [Migración e interoperabilidad](migration-and-interoperability.md)
