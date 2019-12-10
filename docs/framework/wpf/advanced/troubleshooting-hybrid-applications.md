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
ms.openlocfilehash: 46d8f00f9328e9c0a4df596b709195ae42d651bf
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960130"
---
# <a name="troubleshooting-hybrid-applications"></a>Solución de problemas de aplicaciones híbridas
<a name="introduction"></a> En este tema se enumeran algunos problemas comunes que se pueden producir al crear aplicaciones híbridas, que usan las dos tecnologías, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  

<a name="overlapping_controls"></a>   
## <a name="overlapping-controls"></a>Controles superpuestos  
 Los controles no se pueden superponer como cabría esperar. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] usa un HWND independiente para cada control. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa un HWND para todo el contenido de una página. Esta diferencia de implementación da lugar a comportamientos de superposición inesperados.  
  
 Un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] siempre aparece encima del contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido hospedado en un control de <xref:System.Windows.Forms.Integration.ElementHost> aparece en el orden z del control <xref:System.Windows.Forms.Integration.ElementHost>. Es posible superponer <xref:System.Windows.Forms.Integration.ElementHost> controles, pero el contenido de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedada no se combina ni interactúa.  
  
<a name="child_property"></a>   
## <a name="child-property"></a>Child Property  
 Las clases <xref:System.Windows.Forms.Integration.WindowsFormsHost> y <xref:System.Windows.Forms.Integration.ElementHost> solo pueden hospedar un único elemento o control secundario. Para hospedar más de un control o elemento, se debe usar un contenedor como contenido secundario. Por ejemplo, puede Agregar [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] botón y controles de casilla a un control <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> y, a continuación, asignar el panel a la propiedad <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> del control <xref:System.Windows.Forms.Integration.WindowsFormsHost>. Sin embargo, no puede Agregar los controles de botón y casilla por separado al mismo <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.  
  
<a name="scaling"></a>   
## <a name="scaling"></a>Cambiar escala  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tienen modelos diferentes de escala. Algunas transformaciones de escala de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] resultan lógicas para los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], pero otras no. Por ejemplo, ajustar la escala de un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] a 0 funcionará, pero si se intenta ajustar la escala del mismo control a un valor distinto de cero, el tamaño del control sigue siendo 0. Para más información, vea [Consideraciones sobre el diseño del elemento WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="adapter"></a>   
## <a name="adapter"></a>Adaptador de  
 Puede haber confusión al trabajar con las clases <xref:System.Windows.Forms.Integration.WindowsFormsHost> y <xref:System.Windows.Forms.Integration.ElementHost>, porque incluyen un contenedor oculto. Las clases <xref:System.Windows.Forms.Integration.WindowsFormsHost> y <xref:System.Windows.Forms.Integration.ElementHost> tienen un contenedor oculto, denominado *adaptador*, que utilizan para hospedar el contenido. En el caso del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, el adaptador se deriva de la clase <xref:System.Windows.Forms.ContainerControl?displayProperty=nameWithType>. En el caso del control <xref:System.Windows.Forms.Integration.ElementHost>, el adaptador se deriva del elemento <xref:System.Windows.Controls.DockPanel>. Cuando se encuentren referencias al adaptador en otros temas sobre interoperación, se refieren a este contenedor.  
  
<a name="nesting"></a>   
## <a name="nesting"></a>Anidación  
 No se admite el anidamiento de un elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> dentro de un control <xref:System.Windows.Forms.Integration.ElementHost>. Tampoco se admite el anidamiento de un control <xref:System.Windows.Forms.Integration.ElementHost> dentro de un elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
<a name="focus"></a>   
## <a name="focus"></a>Foco  
 El foco funciona de manera diferente en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], lo que significa que pueden producirse problemas de foco en una aplicación híbrida. Por ejemplo, si tiene el foco dentro de un elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, y minimiza y restaura la página o muestra un cuadro de diálogo modal, se puede perder el foco dentro del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>. El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> todavía tiene el foco, pero es posible que el control que contiene no sea así.  
  
 El foco también afecta a la validación de datos. La validación funciona en un elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, pero no funciona al salir del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> o entre dos elementos <xref:System.Windows.Forms.Integration.WindowsFormsHost> diferentes.  
  
<a name="property_mapping"></a>   
## <a name="property-mapping"></a>Asignación de propiedades  
 Algunas asignaciones de propiedades requieren una ardua labor de interpretación a fin de salvar las diferencias de implementación entre ambas tecnologías, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Las asignaciones de propiedad permiten que el código reaccione ante los cambios de fuentes, colores y otras propiedades. En general, las asignaciones de propiedad funcionan realizando escuchas para detectar eventos *Propiedad*Changed o llamadas a On*Propiedad*Changed, y estableciendo las propiedades adecuadas en el control secundario o en su adaptador. Para más información, vea [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md).  
  
<a name="layoutrelated_properties_on_hosted_content"></a>   
## <a name="layout-related-properties-on-hosted-content"></a>Propiedades relacionadas con el diseño en el contenido hospedado  
 Cuando se asigna la propiedad <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.Integration.ElementHost.Child%2A?displayProperty=nameWithType>, se establecen automáticamente varias propiedades relacionadas con el diseño en el contenido hospedado. Cambiar estas propiedades de contenido puede producir comportamientos de diseño inesperados.  
  
 El contenido hospedado está acoplado para rellenar el <xref:System.Windows.Forms.Integration.WindowsFormsHost> y <xref:System.Windows.Forms.Integration.ElementHost> primario. Para habilitar este comportamiento de relleno, se establecen varias propiedades al establecer la propiedad secundaria. En la tabla siguiente se enumeran las propiedades de contenido establecidas por las clases <xref:System.Windows.Forms.Integration.ElementHost> y <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
|Clase de host|Propiedades de contenido|  
|----------------|------------------------|  
|<xref:System.Windows.Forms.Integration.ElementHost>|<xref:System.Windows.FrameworkElement.Height%2A><br /><br /> <xref:System.Windows.FrameworkElement.Width%2A><br /><br /> <xref:System.Windows.FrameworkElement.Margin%2A><br /><br /> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A><br /><br /> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>|  
|<xref:System.Windows.Forms.Integration.WindowsFormsHost>|<xref:System.Windows.Forms.Control.Margin%2A><br /><br /> <xref:System.Windows.Forms.Control.Dock%2A><br /><br /> <xref:System.Windows.Forms.Control.AutoSize%2A><br /><br /> <xref:System.Windows.Forms.Control.Location%2A><br /><br /> <xref:System.Windows.Forms.Control.MaximumSize%2A>|  
  
 No establezca estas propiedades directamente en el contenido hospedado. Para más información, vea [Consideraciones sobre el diseño del elemento WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="navigation_applications"></a>   
## <a name="navigation-applications"></a>Aplicaciones de navegación  
 Es posible que las aplicaciones de navegación no mantengan el estado del usuario. El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> vuelve a crear sus controles cuando se utiliza en una aplicación de navegación. Volver a crear los controles secundarios se produce cuando el usuario se desplaza fuera de la página que hospeda el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> y, a continuación, vuelve a él. Todo el contenido que el usuario haya escrito se perderá.  
  
<a name="message_loop_interoperation"></a>   
## <a name="message-loop-interoperation"></a>Interoperación de bucles de mensajes  
 Cuando se trabaja con bucles de mensajes de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], es posible que los mensajes no se procesen de la forma esperada. El constructor de <xref:System.Windows.Forms.Integration.WindowsFormsHost> llama al método <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>. Este método agrega un filtro de mensajes al bucle de mensajes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Este filtro llama al método <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> si un <xref:System.Windows.Forms.Control?displayProperty=nameWithType> era el destino del mensaje y traduce o envía el mensaje.  
  
 Si muestra una <xref:System.Windows.Window> en un bucle de mensajes [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] con <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>, no podrá escribir nada a menos que llame al método <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>. El método <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> toma un <xref:System.Windows.Window> y agrega un <xref:System.Windows.Forms.IMessageFilter?displayProperty=nameWithType>, que vuelve a enrutar los mensajes relacionados con la clave al bucle de mensajes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Para más información, vea [Arquitectura de entrada de interoperabilidad entre formularios Windows Forms y WPF](windows-forms-and-wpf-interoperability-input-architecture.md).  
  
<a name="opacity_and_layering"></a>   
## <a name="opacity-and-layering"></a>Opacidad y disposición en capas  
 La clase <xref:System.Windows.Interop.HwndHost> no admite la disposición en capas. Esto significa que el establecimiento de la propiedad <xref:System.Windows.UIElement.Opacity%2A> en el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> no tiene ningún efecto y que no se producirá ninguna mezcla con otras ventanas [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que tengan <xref:System.Windows.Window.AllowsTransparency%2A> establecido en `true`.  
  
<a name="dispose"></a>   
## <a name="dispose"></a>Desechar  
 No desechar correctamente las clases puede hacer que se pierdan recursos. En las aplicaciones híbridas, asegúrese de que se eliminen las clases <xref:System.Windows.Forms.Integration.WindowsFormsHost> y <xref:System.Windows.Forms.Integration.ElementHost>, o puede que se pierdan recursos. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] desecha los controles de <xref:System.Windows.Forms.Integration.ElementHost> cuando se cierra su elemento primario de <xref:System.Windows.Forms.Form> no modal. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] desecha <xref:System.Windows.Forms.Integration.WindowsFormsHost> elementos cuando se cierra la aplicación. Es posible mostrar un <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento en un <xref:System.Windows.Window> en un bucle de mensajes [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. En este caso, es posible que el código no reciba la notificación de que la aplicación se está cerrando.  
  
<a name="enabling_visual_styles"></a>   
## <a name="enabling-visual-styles"></a>Habilitar los estilos visuales  
 Es posible que los estilos visuales de Microsoft Windows XP en un control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no estén habilitados. Se llama al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> en la plantilla para una aplicación [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Aunque este método no se llama de forma predeterminada, si usa Visual Studio para crear un proyecto, obtendrá los estilos visuales de Microsoft Windows XP para los controles, si está disponible la versión 6,0 de COMCTL32. dll. Debe llamar al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> antes de que se creen los controladores en el subproceso. Para más información, vea [Cómo: Habilitar estilos visuales en una aplicación híbrida](how-to-enable-visual-styles-in-a-hybrid-application.md).  
  
<a name="licensed_controls"></a>   
## <a name="licensed-controls"></a>Controles con licencia  
 Los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] con licencia que muestran información de licencia en un cuadro de mensaje al usuario pueden provocar un comportamiento inesperado en una aplicación híbrida. Algunos controles con licencia muestran un cuadro de diálogo como respuesta a la creación de controladores. Por ejemplo, un control con licencia podría informar al usuario de que se requiere una licencia o de que al usuario le quedan tres usos de prueba del control.  
  
 El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se deriva de la clase <xref:System.Windows.Interop.HwndHost> y el identificador del control secundario se crea dentro del método <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A>. La clase <xref:System.Windows.Interop.HwndHost> no permite que los mensajes se procesen en el método <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A>, pero la visualización de un cuadro de diálogo hace que se envíen los mensajes. Para habilitar este escenario de licencia, llame al método <xref:System.Windows.Forms.Control.CreateControl%2A?displayProperty=nameWithType> en el control antes de asignarlo como el elemento secundario del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
<a name="wpf_designer"></a>   
## <a name="wpf-designer"></a>WPF Designer  
 Puede diseñar el contenido de WPF mediante WPF Designer para Visual Studio. En las secciones siguientes se enumeran algunos problemas comunes que se pueden producir al crear aplicaciones híbridas con WPF Designer.  
  
### <a name="backcolortransparent-is-ignored-at-design-time"></a>BackColorTransparent se omite en tiempo de diseño  
 Es posible que la propiedad <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> no funcione según lo esperado en tiempo de diseño.  
  
 Si un control WPF no está en un elemento primario visible, el tiempo de ejecución de WPF omite el valor de <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>. La razón por la que se podría omitir <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> es porque <xref:System.Windows.Forms.Integration.ElementHost> objeto se crea en un <xref:System.AppDomain>independiente. Sin embargo, al ejecutar la aplicación, <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> funciona según lo previsto.  
  
### <a name="design-time-error-list-appears-when-the-obj-folder-is-deleted"></a>Aparece la lista de errores en tiempo de diseño cuando se elimina la carpeta obj  
 Si se elimina la carpeta obj, aparece la lista de errores en tiempo de diseño.  
  
 Al diseñar con <xref:System.Windows.Forms.Integration.ElementHost>, el Diseñador de Windows Forms usa archivos generados en la carpeta debug o Release dentro de la carpeta obj del proyecto. Si se eliminan estos archivos, aparece la lista de errores en tiempo de diseño. Para corregir este problema, recompile el proyecto. Para más información, vea [Errores en tiempo de diseño en el Diseñador de Windows Forms](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md).  
  
<a name="elementhost_and_ime"></a>   
## <a name="elementhost-and-ime"></a>ElementHost e IME  
 Los controles de WPF hospedados en una <xref:System.Windows.Forms.Integration.ElementHost> no admiten actualmente la propiedad <xref:System.Windows.Forms.Control.ImeMode%2A>. Los controles hospedados omitirán los cambios realizados en <xref:System.Windows.Forms.Control.ImeMode%2A>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Interoperabilidad en WPF Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628658(v=vs.100))
- [Arquitectura de entrada de interoperabilidad entre formularios Windows Forms y WPF](windows-forms-and-wpf-interoperability-input-architecture.md)
- [Habilitar estilos visuales en una aplicación híbrida](how-to-enable-visual-styles-in-a-hybrid-application.md)
- [Consideraciones sobre el diseño del elemento WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md)
- [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md)
- [Errores en tiempo de diseño en el Diseñador de Windows Forms](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md)
- [Migración e interoperabilidad](migration-and-interoperability.md)
