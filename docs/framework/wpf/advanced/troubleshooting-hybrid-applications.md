---
title: "Soluci&#243;n de problemas de aplicaciones h&#237;bridas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "aplicaciones híbridas [interoperabilidad con WPF]"
  - "interoperabilidad [WPF], Windows Forms"
  - "bucles de mensajes [WPF]"
  - "controles superpuestos"
  - "formularios Windows Forms [WPF], interoperabilidad con"
  - "Windows Forms, interoperabilidad con WPF"
ms.assetid: f440c23f-fa5d-4d5a-852f-ba61150e6405
caps.latest.revision: 26
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Soluci&#243;n de problemas de aplicaciones h&#237;bridas
<a name="introduction"></a> En este tema se muestra una lista de algunos problemas comunes que se pueden producir al crear aplicaciones híbridas, que utilizan las dos tecnologías, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
   
  
<a name="overlapping_controls"></a>   
## Controles superpuestos  
 Los controles no se pueden superponer como cabría esperar.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] utiliza un HWND independiente para cada control.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza un HWND para todo el contenido de una página.  Esta diferencia de implementación da lugar a comportamientos de superposición inesperados.  
  
 Un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] siempre aparece encima del contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 El contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedado en un control de <xref:System.Windows.Forms.Integration.ElementHost> aparece en el orden z del control <xref:System.Windows.Forms.Integration.ElementHost>.  Es posible superponer controles <xref:System.Windows.Forms.Integration.ElementHost>, pero el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedado no se combina ni interactúa.  
  
<a name="child_property"></a>   
## Propiedad secundaria  
 Las clases <xref:System.Windows.Forms.Integration.WindowsFormsHost> y <xref:System.Windows.Forms.Integration.ElementHost> pueden hospedar un solo control o elemento secundario.  Para hospedar más de un control o elemento, debe utilizar un contenedor como contenido secundario.  Por ejemplo, puede agregar controles de botón y casilla de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] a un control <xref:System.Windows.Forms.Panel?displayProperty=fullName> y, a continuación, asignar el panel a la propiedad <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> del control <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  Sin embargo, no puede agregar los controles de botón y casilla por separado al mismo control <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
<a name="scaling"></a>   
## Ajustar la escala  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tienen modelos diferentes de ajuste de escala.  Algunas transformaciones de ajuste de escala de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] resultan lógicas para los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], pero otras, no.  Por ejemplo, ajustar la escala de un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] a 0 funcionará, pero si intenta ajustar la escala del mismo control a un valor distinto de cero, el tamaño del control sigue siendo 0.  Para obtener más información, consulte [Consideraciones sobre el diseño del elemento WindowsFormsHost](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="adapter"></a>   
## Adaptador  
 Puede producirse confusión al trabajar con las clases <xref:System.Windows.Forms.Integration.WindowsFormsHost> y <xref:System.Windows.Forms.Integration.ElementHost>, porque incluyen un contenedor oculto.  Las clases <xref:System.Windows.Forms.Integration.WindowsFormsHost> y <xref:System.Windows.Forms.Integration.ElementHost> tienen un contenedor oculto, denominado *adaptador*, que utilizan para hospedar el contenido.  Para el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, el adaptador se deriva de la clase <xref:System.Windows.Forms.ContainerControl?displayProperty=fullName>.  Para el control <xref:System.Windows.Forms.Integration.ElementHost>, el adaptador se deriva del elemento <xref:System.Windows.Controls.DockPanel>.  Cuando encuentre referencias al adaptador en otros temas sobre interoperación, se refieren a este contenedor.  
  
<a name="nesting"></a>   
## Anidamiento  
 No se admite anidar un elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> dentro de un control <xref:System.Windows.Forms.Integration.ElementHost>.  Tampoco se admite anidar un control <xref:System.Windows.Forms.Integration.ElementHost> dentro de un elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
<a name="focus"></a>   
## Focus  
 El foco funciona de manera diferente en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], lo que significa que pueden producirse problemas de foco en las aplicaciones híbridas.  Por ejemplo, si tiene el foco dentro de un elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, y minimiza y restaura la página o muestra un cuadro de diálogo modal, puede perderse el foco del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> sigue teniendo el foco, pero puede que el control contenido en él no lo tenga.  
  
 El foco afecta también a la validación de datos.  La validación funciona en un elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, pero no funciona cuando se presiona la tecla TAB para salir del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, o para cambiar entre dos elementos <xref:System.Windows.Forms.Integration.WindowsFormsHost> diferentes.  
  
<a name="property_mapping"></a>   
## Asignación de propiedad  
 Algunas asignaciones de propiedad exigen una ardua labor de interpretación a fin de salvar las diferencias de implementación entre ambas tecnologías, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Las asignaciones de propiedad permiten que el código reaccione ante los cambios de fuentes, colores y otras propiedades.  En general, las asignaciones de propiedad funcionan realizando escuchas para detectar eventos de cambio de propiedad \(*Property*Changed\) o llamadas a On*Property*Changed, y estableciendo las propiedades adecuadas en el control secundario o en su adaptador.  Para obtener más información, vea [Asignación de propiedades en formularios Windows Forms y WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md).  
  
<a name="layoutrelated_properties_on_hosted_content"></a>   
## Propiedades relacionadas con el diseño en el contenido hospedado  
 Cuando se asigna la propiedad <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A?displayProperty=fullName> o <xref:System.Windows.Forms.Integration.ElementHost.Child%2A?displayProperty=fullName>, automáticamente se establecen varias propiedades relacionadas con el diseño en el contenido hospedado.  Cambiar estas propiedades de contenido puede producir comportamientos de diseño inesperados.  
  
 El contenido hospedado se acopla para rellenar el elemento primario <xref:System.Windows.Forms.Integration.WindowsFormsHost> y <xref:System.Windows.Forms.Integration.ElementHost>.  Para habilitar este comportamiento de relleno, se establecen varias propiedades al establecer la propiedad secundaria.  En la tabla siguiente se muestra qué propiedades de contenido establecen las clases <xref:System.Windows.Forms.Integration.ElementHost> y <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
|Clase host|Propiedades de contenido|  
|----------------|------------------------------|  
|<xref:System.Windows.Forms.Integration.ElementHost>|<xref:System.Windows.FrameworkElement.Height%2A><br /><br /> <xref:System.Windows.FrameworkElement.Width%2A><br /><br /> <xref:System.Windows.FrameworkElement.Margin%2A><br /><br /> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A><br /><br /> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>|  
|<xref:System.Windows.Forms.Integration.WindowsFormsHost>|<xref:System.Windows.Forms.Control.Margin%2A><br /><br /> <xref:System.Windows.Forms.Control.Dock%2A><br /><br /> <xref:System.Windows.Forms.Control.AutoSize%2A><br /><br /> <xref:System.Windows.Forms.Control.Location%2A><br /><br /> <xref:System.Windows.Forms.Control.MaximumSize%2A>|  
  
 No se establezca directamente estas propiedades en el contenido hospedado.  Para obtener más información, consulte [Consideraciones sobre el diseño del elemento WindowsFormsHost](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="navigation_applications"></a>   
## Aplicaciones de navegación  
 Las aplicaciones de navegación pueden no mantener el estado del usuario.  El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> vuelve a crear los controles cuando se utiliza en una aplicación de navegación.  La nueva creación de los controles secundarios se produce cuando el usuario sale de la página que hospeda el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> y, a continuación, vuelve a ella.  Todo el contenido que el usuario haya escrito se perderá.  
  
<a name="message_loop_interoperation"></a>   
## Interoperación de bucles de mensajes  
 Cuando se trabaja con bucles de mensajes de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], puede que los mensajes no se procesen como cabría esperar.  El constructor <xref:System.Windows.Forms.Integration.WindowsFormsHost> llama al método <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>.  Este método agrega un filtro de mensajes al bucle de mensajes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Este filtro llama al método <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=fullName> si el destino del mensaje es <xref:System.Windows.Forms.Control?displayProperty=fullName> y convierte o envía el mensaje.  
  
 Si muestra <xref:System.Windows.Window> en un bucle de mensajes de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] con el método <xref:System.Windows.Forms.Application.Run%2A?displayProperty=fullName>, no podrá escribir nada a menos que llame al método <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>.  El método <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> toma <xref:System.Windows.Window> y agrega un objeto <xref:System.Windows.Forms.IMessageFilter?displayProperty=fullName>, que reenruta los mensajes relacionados con claves al bucle de mensajes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Para obtener más información, vea [Arquitectura de entrada de interoperabilidad entre formularios Windows Forms y WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-interoperability-input-architecture.md).  
  
<a name="opacity_and_layering"></a>   
## Opacidad y disposición en capas  
 La clase <xref:System.Windows.Interop.HwndHost> no admite las capas.  Esto significa que establecer la propiedad <xref:System.Windows.UIElement.Opacity%2A> en el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> no surte ningún efecto, y que no se producirá ninguna mezcla con las demás ventanas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cuya propiedad <xref:System.Windows.Window.AllowsTransparency%2A> esté establecida en `true`.  
  
<a name="dispose"></a>   
## Desechar  
 No desechar correctamente las clases puede malgastar recursos.  En sus aplicaciones híbridas, asegurarse de desechar las clases <xref:System.Windows.Forms.Integration.ElementHost> y <xref:System.Windows.Forms.Integration.WindowsFormsHost>, pues de lo contrario puede malgastar recursos.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] desecha los controles <xref:System.Windows.Forms.Integration.ElementHost> cuando se cierra su elemento primario <xref:System.Windows.Forms.Form>no modal. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] desecha los elementos <xref:System.Windows.Forms.Integration.WindowsFormsHost> cuando se cierra la aplicación.  Es posible mostrar un elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> en un objeto <xref:System.Windows.Window> en un bucle de mensajes de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  En este caso, puede que el código no reciba la notificación de que la aplicación se está cerrando.  
  
<a name="enabling_visual_styles"></a>   
## Habilitar estilos visuales  
 Puede que los estilos visuales de [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] no estén habilitados en un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  Se llama al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName> en la plantilla para una aplicación de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  Aunque este método no se llama de forma predeterminada, si utiliza [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] para crear un proyecto, obtendrá los estilos visuales de [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] para los controles, si la versión 6,0 de Comctl32.dll está disponible. Se debe llamar al método de <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> antes de que los identificadores se crean en el subproceso.  Para obtener más información, consulte [Cómo: Habilitar estilos visuales en una aplicación híbrida](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).  
  
<a name="licensed_controls"></a>   
## Controles con licencia  
 Los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] con licencia que muestran información de licencias en un cuadro de mensaje al usuario pueden provocar un comportamiento inesperado en una aplicación híbrida.  Algunos controles con licencia muestran un cuadro de diálogo en respuesta, a fin de administrar la creación.  Por ejemplo, un control con licencia podría informar al usuario de que se requiere una licencia o de que al usuario le quedan tres usos de prueba del control.  
  
 El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se deriva de la clase <xref:System.Windows.Interop.HwndHost> y el controlador del control secundario se crea dentro del método <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A>.  La clase <xref:System.Windows.Interop.HwndHost> no permite procesar los mensajes en el método <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A>, pero al mostrar un cuadro de diálogo se provoca el envío de mensajes.  Para habilitar este escenario de licencias, llame al método <xref:System.Windows.Forms.Control.CreateControl%2A?displayProperty=fullName> del control antes de asignarlo como elemento secundario del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
<a name="wpf_designer"></a>   
## Diseñador de WPF  
 Puede diseñar el contenido de WPF mediante [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].  En las secciones siguientes se indican algunos problemas comunes que se pueden producir al crear aplicaciones híbridas con [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
### BackColorTransparent se omite en tiempo de diseño  
 La propiedad <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> puede no funcionar según lo previsto en tiempo de diseño.  
  
 Si un control de WPF no está en un elemento primario visible, el motor de tiempo de ejecución de WPF omite el valor <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>.  La razón por la que se puede omitir <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> es porque el objeto <xref:System.Windows.Forms.Integration.ElementHost> se crea en un <xref:System.AppDomain>independiente.  Sin embargo, al ejecutar la aplicación, <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> funciona según lo previsto.  
  
### Aparece la lista de errores en tiempo de diseño cuando se elimina la carpeta obj  
 Si se elimina la carpeta obj, aparece la lista de errores en tiempo de diseño.  
  
 Al diseñar mediante <xref:System.Windows.Forms.Integration.ElementHost>, el Diseñador de Windows Forms utiliza los archivos generados en la carpeta Debug o Release situada en la carpeta obj del proyecto.  Si elimina estos archivos, aparece la lista de errores en tiempo de diseño.  Para corregir este problema, recompile el proyecto.  Para obtener más información, vea [Errores en tiempo de diseño en el Diseñador de Windows Forms](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md).  
  
<a name="elementhost_and_ime"></a>   
## ElementHost e IME  
 Los controles de WPF hospedados en <xref:System.Windows.Forms.Integration.ElementHost> no admiten actualmente la propiedad <xref:System.Windows.Forms.Control.ImeMode%2A>.  Los controles hospedados omitirán los cambios realizados en <xref:System.Windows.Forms.Control.ImeMode%2A>.  
  
## Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Interoperabilidad en WPF Designer](http://msdn.microsoft.com/es-es/2cb7c1ca-2a75-463b-8801-fba81e2b7042)   
 [Arquitectura de entrada de interoperabilidad entre formularios Windows Forms y WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-interoperability-input-architecture.md)   
 [Cómo: Habilitar estilos visuales en una aplicación híbrida](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)   
 [Consideraciones sobre el diseño del elemento WindowsFormsHost](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)   
 [Asignación de propiedades en formularios Windows Forms y WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)   
 [Errores en tiempo de diseño en el Diseñador de Windows Forms](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md)   
 [Migración e interoperabilidad](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)