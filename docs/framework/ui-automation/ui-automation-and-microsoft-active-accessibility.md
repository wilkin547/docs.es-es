---
title: UI Automation y Microsoft Active Accessibility
ms.date: 03/30/2017
helpviewer_keywords:
- Active Accessibility
- UI Automation, Active Accessibility compared to
- UI Automation, Microsoft Active Accessibility
- Active Accessibility, UI Automation compared to
ms.assetid: 87bee662-0a3e-4232-a421-20e7a5968321
ms.openlocfilehash: 9a84c344ffabdaaa9d0aed68b05b7a4449776789
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179979"
---
# <a name="ui-automation-and-microsoft-active-accessibility"></a>UI Automation y Microsoft Active Accessibility
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 Microsoft Active Accessibility fue la solución anterior para hacer que las aplicaciones sean accesibles. [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]es el nuevo modelo de accesibilidad para Microsoft Windows y está diseñado para abordar las necesidades de los productos de tecnología de asistencia y herramientas de prueba automatizadas. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]ofrece muchas mejoras sobre la accesibilidad activa.  
  
 En este tema se [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] incluyen las principales características y se explica cómo se diferencian estas características de la accesibilidad activa.  
  
<a name="Programming_Languages_compare"></a>
## <a name="programming-languages"></a>Lenguajes de programación  
<Active Accessibility se basa en el modelo de objetos componentes (COM) con compatibilidad con interfaces duales y, por lo tanto, se puede programar en C/C+, Microsoft Visual Basic 6.0 y lenguajes de scripting. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)](incluida la biblioteca de proveedores del lado cliente para controles estándar) se escribe en código administrado y las aplicaciones cliente de Automatización de la interfaz de usuarioUI Automation se programan más fácilmente mediante C o Visual Basic .NET. Los proveedores de automatización de la interfaz de usuario, que son implementaciones de interfaz, se pueden escribir en código administrado o en C/C++.  
  
<a name="Support_in_Windows_Presentation_Foundation_"></a>
## <a name="support-in-windows-presentation-foundation"></a>Compatibilidad en Windows Presentation Foundation  
 Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) es el nuevo modelo para crear interfaces de usuario. WPFWPF elementos no contienen compatibilidad nativa para Active Accessibility; sin embargo, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]admiten, lo que incluye compatibilidad con puentes para clientes de accesibilidad activa. Solo los clientes [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] escritos específicamente para pueden aprovechar al máximo las características de accesibilidad de WPFWPF, como la compatibilidad enriquecida con texto.  
  
<a name="Servers_and_Clients_compare"></a>
## <a name="servers-and-clients"></a>Servidores y clientes  
 En Active Accessibility, los servidores y clientes se comunican directamente, en gran medida a través de la implementación del servidor de `IAccessible`.  
  
 En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], un servicio principal se encuentra entre el servidor (denominado proveedor) y el cliente. El servicio principal realiza llamadas a las interfaces implementadas por los proveedores y ofrece servicios adicionales como la generación de identificadores únicos en tiempo de ejecución para los elementos. Las aplicaciones cliente usan funciones de la biblioteca para llamar al servicio [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 Los proveedores de Automatización de la interfaz de usuarioUI Automation pueden proporcionar información a los clientes de Active Accessibility y los servidores de Active Accessibility pueden proporcionar información a las aplicaciones cliente de Automatización de la interfaz de usuarioUI Automation . Sin embargo, dado que Active Accessibility no expone tanta información como [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], los dos modelos no son totalmente compatibles.  
  
<a name="UI_Elements_compare"></a>
## <a name="ui-elements"></a>Elementos de interfaz de usuario  
 Active Accessibility [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] presenta elementos como una `IAccessible` interfaz o como un identificador secundario. Es difícil comparar dos punteros `IAccessible` para determinar si hacen referencia al mismo elemento.  
  
 En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], cada elemento se representa como un objeto <xref:System.Windows.Automation.AutomationElement> . La comparación se realiza mediante el operador de igualdad o el método <xref:System.Windows.Automation.AutomationElement.Equals%2A> , que comparan los identificadores únicos en tiempo de ejecución de los elementos.  
  
<a name="Tree_Views_and_Navigation_compare"></a>
## <a name="tree-views-and-navigation"></a>Vistas de árbol y navegación  
 Los elementos [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] de la pantalla pueden verse como una estructura de árbol con el escritorio como la raíz, las ventanas de la aplicación como elementos secundarios inmediatos y los elementos que se encuentran dentro de las aplicaciones como descendientes más lejanos.  
  
 En Active Accessibility, muchos elementos de automatización que son irrelevantes para los usuarios finales se exponen en el árbol. Las aplicaciones cliente tienen que mirar todos los elementos para determinar cuáles son significativos.  
  
 Las aplicaciones cliente de la automatización de la interfaz de usuario ven la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] mediante una vista filtrada. La vista solo contiene elementos de interés: aquellos que ofrecen información al usuario o habilitan la interacción. Hay vistas predefinidas que incluyen solo elementos de control y solo elementos de contenido; además, las aplicaciones pueden definir vistas personalizadas. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] simplifica la tarea de describir la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] al usuario y de ayudar al usuario para que interactúe con la aplicación.  
  
 La navegación entre elementos, en Active Accessibility, es espacial (por ejemplo, desplazarse al elemento que se encuentra a la izquierda en la pantalla), lógico (por ejemplo, pasar al siguiente elemento de menú o al siguiente elemento en el orden de tabulación dentro de un cuadro de diálogo) o jerárquico ( por ejemplo, mover el primer elemento secundario en un contenedor o del elemento secundario a su elemento primario). La navegación jerárquica resulta complicada por el hecho de que los elementos secundarios no siempre son objetos que implementan `IAccessible`.  
  
 En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], todos los elementos [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] son objetos <xref:System.Windows.Automation.AutomationElement> que admiten la misma funcionalidad básica. (Desde el punto de vista del proveedor, son <xref:System.Windows.Automation.Provider.IRawElementProviderSimple>objetos que implementan una interfaz heredada de .) La navegación es principalmente jerárquica: de padres a hijos, y de un hermano a otro. (La navegación entre hermanos tiene un elemento lógico, ya que puede seguir el orden de tabulación.) Puede navegar desde cualquier punto de partida, utilizando cualquier <xref:System.Windows.Automation.TreeWalker> vista filtrada del árbol, utilizando la clase. También puede navegar a determinados elementos secundarios o descendientes mediante el uso de <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> y <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; por ejemplo, es muy sencillo recuperar todos los elementos de un cuadro de diálogo que admitan un patrón de control especificado.  
  
 La [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] navegación es más coherente que en Active Accessibility. Algunos elementos, como las listas desplegables y las ventanas emergentes, aparecen dos veces en el árbol de accesibilidad activa, y la navegación desde ellos puede tener resultados inesperados. En realidad, es imposible implementar correctamente Active Accessibility para un control de armadura. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] habilita la reorganización dinámica de relación jerárquica y el cambio de posición, para que un elemento se pueda colocar en cualquier lugar del árbol a pesar de la jerarquía impuesta por la propiedad de las ventanas.  
  
<a name="Roles_and_Control_Types"></a>
## <a name="roles-and-control-types"></a>Roles y tipos de control  
 Active Accessibility `accRole` utiliza`IAccessible::get_actRole`la propiedad ( ) para recuperar una [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]descripción del rol del elemento en el ROLE_SYSTEM_SLIDER o ROLE_SYSTEM_MENUITEM. El rol de un elemento es la pista principal para su funcionalidad disponible. La interacción con un control se logra mediante métodos fijos como `IAccessible::accSelect` y `IAccessible::accDoDefaultAction`. La interacción entre la aplicación cliente y el [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] se limita a lo que se puede hacer mediante `IAccessible`.  
  
 En cambio, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] desacopla en gran medida el tipo de control del elemento (descrito por la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> ) de su funcionalidad esperada. La funcionalidad se determina por los patrones de control admitidos por el proveedor a través de su implementación de interfaces especializadas. Los patrones de control se pueden combinar para describir el conjunto completo de la funcionalidad admitida por un determinado elemento [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] . Algunos proveedores deben admitir un patrón de control concreto; por ejemplo, el proveedor de una casilla debe admitir el patrón de control Toggle. Otros proveedores deben admitir uno o más patrones de un conjunto de patrones de control; por ejemplo, un botón debe admitir Toggle o Invoke. Sin embargo, otros no admiten ningún patrón de control; por ejemplo, un panel que no se pueda mover, cambiar de tamaño o acoplar no tiene ningún patrón de control.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] admite controles personalizados, que se identifican mediante la propiedad <xref:System.Windows.Automation.ControlType.Custom> y se pueden describir por la propiedad <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty> .  
  
 En la tabla siguiente se muestra [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] la asignación de roles de accesibilidad activa a tipos de control.  
  
|Rol de accesibilidad activa|Tipo de control[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------|  
|ROLE_SYSTEM_PUSHBUTTON|Botón|  
|ROLE_SYSTEM_CLIENT|Calendario|  
|ROLE_SYSTEM_CHECKBUTTON|casilla|  
|ROLE_SYSTEM_COMBOBOX|Cuadro combinado|  
|ROLE_SYSTEM_CLIENT|Personalizado|  
|ROLE_SYSTEM_LIST|Cuadrícula de datos|  
|ROLE_SYSTEM_LISTITEM|Elemento de datos|  
|ROLE_SYSTEM_DOCUMENT|Documento|  
|ROLE_SYSTEM_TEXT|Editar|  
|ROLE_SYSTEM_GROUPING|Grupo|  
|ROLE_SYSTEM_LIST|Encabezado|  
|ROLE_SYSTEM_COLUMNHEADER|Elemento de encabezado|  
|ROLE_SYSTEM_LINK|Hyperlink|  
|ROLE_SYSTEM_GRAPHIC|Imagen|  
|ROLE_SYSTEM_LIST|List|  
|ROLE_SYSTEM_LISTITEM|Elemento de lista|  
|ROLE_SYSTEM_MENUPOPUP|Menú|  
|ROLE_SYSTEM_MENUBAR|Barra de menús|  
|ROLE_SYSTEM_MENUITEM|Elemento de menú|  
|ROLE_SYSTEM_PANE|Panel|  
|ROLE_SYSTEM_PROGRESSBAR|Barra de progreso|  
|ROLE_SYSTEM_RADIOBUTTON|Botón de radio|  
|ROLE_SYSTEM_SCROLLBAR|Barra de desplazamiento|  
|ROLE_SYSTEM_SEPARATOR|Separador|  
|ROLE_SYSTEM_SLIDER|Control deslizante|  
|ROLE_SYSTEM_SPINBUTTON|Spinner|  
|ROLE_SYSTEM_SPLITBUTTON|Botón de expansión|  
|ROLE_SYSTEM_STATUSBAR|Barra de estado|  
|ROLE_SYSTEM_PAGETABLIST|Pestaña|  
|ROLE_SYSTEM_PAGETAB|Elemento de pestaña|  
|ROLE_SYSTEM_TABLE|Tabla|  
|ROLE_SYSTEM_STATICTEXT|Texto|  
|ROLE_SYSTEM_INDICATOR|Thumb|  
|ROLE_SYSTEM_TITLEBAR|Barra de título|  
|ROLE_SYSTEM_TOOLBAR|Barra de herramientas|  
|ROLE_SYSTEM_TOOLTIP|Información sobre herramientas|  
|ROLE_SYSTEM_OUTLINE|Árbol|  
|ROLE_SYSTEM_OUTLINEITEM|Elemento de árbol|  
|ROLE_SYSTEM_WINDOW|Periodo|  
  
 Para más información sobre los diferentes tipos de control, vea [UI Automation Control Types](ui-automation-control-types.md).  
  
<a name="States_and_Properties"></a>
## <a name="states-and-properties"></a>Estados y propiedades  
 En Active Accessibility, los elementos admiten un conjunto `accState`común de propiedades y algunas propiedades (como ) deben describir cosas muy diferentes, dependiendo del rol del elemento. Los servidores deben implementar todos los métodos de `IAccessible` que devuelvan una propiedad, incluso aquellos que no son pertinentes para el elemento.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]define muchas más propiedades, algunas de las cuales corresponden a estados de Active Accessibility. Algunas son comunes para todos los elementos, pero otras son específicas de tipos de control y patrones de control. Las propiedades se distinguen mediante identificadores únicos y la mayoría de las propiedades se pueden recuperar mediante el uso de un único método, <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> o <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>. Muchas propiedades también se pueden recuperar con facilidad a partir de los descriptores de acceso de propiedad <xref:System.Windows.Automation.AutomationElement.Current%2A> y <xref:System.Windows.Automation.AutomationElement.Cached%2A> .  
  
 Un proveedor de la automatización de la interfaz de usuario no tiene que implementar propiedades irrelevantes, pero puede devolver simplemente un valor `null` para cualquier propiedad que no admita. Además, el servicio principal [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] puede obtener algunas propiedades del proveedor de ventana predeterminado y estas se combinan con propiedades implementadas de manera explícita por el proveedor.  
  
 Además de admitir muchas más propiedades, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ofrece un rendimiento mejorado al permitir que se recuperen varias propiedades con una llamada única entre procesos.  
  
 En la tabla siguiente se muestra la correspondencia entre las propiedades de los dos modelos.  
  
|Descriptor de acceso activo a la propiedad Accessibility|Id. de propiedad[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Observaciones|  
|-----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|-------------|  
|`get_accKeyboardShortcut`|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty> o <xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|`AccessKeyProperty` tiene prioridad si ambos están presentes.|  
|`get_accName`|<xref:System.Windows.Automation.AutomationElement.NameProperty>||  
|`get_accRole`|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|Vea la tabla anterior para la asignación de roles a tipos de control.|  
|`get_accValue`|<xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=nameWithType>|Válido únicamente para tipos de control que admiten ValuePattern o RangeValuePattern. Los valores de RangeValue se normalizan entre 0 y 100, para que sean coherentes con el comportamiento de MSAA. Los elementos de valor usan una cadena.|  
|`get_accHelp`|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>||  
|`accLocation`|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>||  
|`get_accDescription`|No se admiten en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].|`accDescription` no tenía una especificación clara en MSAA, lo que hizo que los proveedores colocaran diferente información en esta propiedad.|  
|`get_accHelpTopic`|No se admiten en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].||  
  
 En la tabla [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] siguiente se muestran las propiedades que corresponden a las constantes de estado de accesibilidad activa.  
  
|Estado de accesibilidad activa|Propiedad [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|¿Desencadena el cambio de estado?|  
|-----------------------------------------------------------------------|------------------------------------------------------------------------------------|----------------------------|  
|STATE_SYSTEM_CHECKED|Para casilla, <xref:System.Windows.Automation.TogglePattern.ToggleStateProperty><br /><br /> Para botón de radio, <xref:System.Windows.Automation.SelectionItemPattern.IsSelectedProperty>|Y|  
|STATE_SYSTEM_COLLAPSED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> = <xref:System.Windows.Automation.ExpandCollapseState.Collapsed>|Y|  
|STATE_SYSTEM_EXPANDED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> = <xref:System.Windows.Automation.ExpandCollapseState.Expanded> o <xref:System.Windows.Automation.ExpandCollapseState.PartiallyExpanded>|Y|  
|STATE_SYSTEM_FOCUSABLE|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|N|  
|STATE_SYSTEM_FOCUSED|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|N|  
|STATE_SYSTEM_HASPOPUP|<xref:System.Windows.Automation.ExpandCollapsePattern> para elementos de menú|N|  
|STATE_SYSTEM_INVISIBLE|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty> = True y <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A> produce <xref:System.Windows.Automation.NoClickablePointException>|N|  
|STATE_SYSTEM_LINKED|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> =<br /><br /> <xref:System.Windows.Automation.ControlType.Hyperlink>|N|  
|STATE_SYSTEM_MIXED|<xref:System.Windows.Automation.TogglePattern.TogglePatternInformation.ToggleState%2A> = <xref:System.Windows.Automation.ToggleState.Indeterminate>|N|  
|STATE_SYSTEM_MOVEABLE|<xref:System.Windows.Automation.TransformPattern.CanMoveProperty>|N|  
|STATE_SYSTEM_MUTLISELECTABLE|<xref:System.Windows.Automation.SelectionPattern.CanSelectMultipleProperty>|N|  
|STATE_SYSTEM_OFFSCREEN|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty> = True|N|  
|STATE_SYSTEM_PROTECTED|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|N|  
|STATE_SYSTEM_READONLY|<xref:System.Windows.Automation.RangeValuePattern.IsReadOnlyProperty?displayProperty=nameWithType> y <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty?displayProperty=nameWithType>|N|  
|STATE_SYSTEM_SELECTABLE|<xref:System.Windows.Automation.SelectionItemPattern> se admite|N|  
|STATE_SYSTEM_SELECTED|<xref:System.Windows.Automation.SelectionItemPattern.IsSelectedProperty>|N|  
|STATE_SYSTEM_SIZEABLE|<xref:System.Windows.Automation.TransformPattern.TransformPatternInformation.CanResize%2A>|N|  
|STATE_SYSTEM_UNAVAILABLE|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|Y|  
  
 Los siguientes estados no se implementaron en la mayoría de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]los servidores de control de accesibilidad activa o no tienen equivalente en .  
  
|Estado de accesibilidad activa|Observaciones|  
|-----------------------------------------------------------------------|-------------|  
|STATE_SYSTEM_BUSY|No disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_DEFAULT|No disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_ANIMATED|No disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_EXTSELECTABLE|No ampliamente implementado por los servidores de Accesibilidad Activa|  
|STATE_SYSTEM_MARQUEED|No ampliamente implementado por los servidores de Accesibilidad Activa|  
|STATE_SYSTEM_SELFVOICING|No ampliamente implementado por los servidores de Accesibilidad Activa|  
|STATE_SYSTEM_TRAVERSED|No disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_ALERT_HIGH|No ampliamente implementado por los servidores de Accesibilidad Activa|  
|STATE_SYSTEM_ALERT_MEDIUM|No ampliamente implementado por los servidores de Accesibilidad Activa|  
|STATE_SYSTEM_ALERT_LOW|No ampliamente implementado por los servidores de Accesibilidad Activa|  
|STATE_SYSTEM_FLOATING|No ampliamente implementado por los servidores de Accesibilidad Activa|  
|STATE_SYSTEM_HOTTRACKED|No disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_PRESSED|No disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
  
 Para obtener una lista completa de los identificadores de propiedad [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Properties Overview](ui-automation-properties-overview.md).  
  
<a name="uiautomation_events_compare"></a>
## <a name="events"></a>Eventos  
 El mecanismo [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]de eventos en , a diferencia de que en Active Accessibility, no se basa en el enrutamiento de eventos de Windows (que está estrechamente vinculado con identificadores de ventana) y no requiere que la aplicación cliente configure los enlaces. Las suscripciones a eventos se pueden ajustar no solo para eventos concretos, sino también para partes específicas del árbol. Los proveedores también pueden ajustar su generación de eventos mediante el mantenimiento del seguimiento de qué eventos se están escuchando.  
  
 También resulta más sencillo para los clientes recuperar los elementos que generan eventos, ya que estos se pasan directamente a la devolución de llamada de evento. Las propiedades del elemento se recuperan previamente de manera automática si había una solicitud de caché activa cuando el cliente se suscribió al evento.  
  
 En la tabla siguiente se muestra la [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] correspondencia de Active Accessibility WinEvents y eventos.  
  
|WinEvent|Identificador de evento[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|--------------|--------------------------------------------------------------------------------------------|  
|EVENT_OBJECT_ACCELERATORCHANGE|Cambio de propiedad<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|  
|EVENT_OBJECT_CONTENTSCROLLED|Cambio de propiedad o  en las barras de desplazamiento asociadas|  
|EVENT_OBJECT_CREATE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_DEFACTIONCHANGE|Sin equivalencia|  
|EVENT_OBJECT_DESCRIPTIONCHANGE|Ningún equivalente exacto; quizás cambio de propiedad <xref:System.Windows.Automation.AutomationElement.HelpTextProperty> o <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>|  
|EVENT_OBJECT_DESTROY|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_FOCUS|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT_OBJECT_HELPCHANGE|Cambio de<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>|  
|EVENT_OBJECT_HIDE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_LOCATIONCHANGE|Cambio de propiedad<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|  
|EVENT_OBJECT_NAMECHANGE|Cambio de propiedad<xref:System.Windows.Automation.AutomationElement.NameProperty>|  
|EVENT_OBJECT_PARENTCHANGE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_REORDER|No se utiliza de forma coherente en La accesibilidad activa. No se define ningún evento correspondiente directamente en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].|  
|EVENT_OBJECT_SELECTION|<xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>|  
|EVENT_OBJECT_SELECTIONADD|<xref:System.Windows.Automation.SelectionItemPattern.ElementAddedToSelectionEvent>|  
|EVENT_OBJECT_SELECTIONREMOVE|<xref:System.Windows.Automation.SelectionItemPattern.ElementRemovedFromSelectionEvent>|  
|EVENT_OBJECT_SELECTIONWITHIN|Sin equivalencia|  
|EVENT_OBJECT_SHOW|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_STATECHANGE|Diversos eventos de cambio de propiedades|  
|EVENT_OBJECT_VALUECHANGE|Se han cambiado<xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=nameWithType> y <xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=nameWithType>|  
|EVENT_SYSTEM_ALERT|Sin equivalencia|  
|EVENT_SYSTEM_CAPTUREEND|Sin equivalencia|  
|EVENT_SYSTEM_CAPTURESTART|Sin equivalencia|  
|EVENT_SYSTEM_CONTEXTHELPEND|Sin equivalencia|  
|EVENT_SYSTEM_CONTEXTHELPSTART|Sin equivalencia|  
|EVENT_SYSTEM_DIALOGEND|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|  
|EVENT_SYSTEM_DIALOGSTART|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|  
|EVENT_SYSTEM_DRAGDROPEND|Sin equivalencia|  
|EVENT_SYSTEM_DRAGDROPSTART|Sin equivalencia|  
|EVENT_SYSTEM_FOREGROUND|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT_SYSTEM_MENUEND|<xref:System.Windows.Automation.AutomationElement.MenuClosedEvent>|  
|EVENT_SYSTEM_MENUPOPUPEND|<xref:System.Windows.Automation.AutomationElement.MenuClosedEvent>|  
|EVENT_SYSTEM_MENUPOPUPSTART|<xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent>|  
|EVENT_SYSTEM_MENUSTART|<xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent>|  
|EVENT_SYSTEM_MINIMIZEEND|Cambio de propiedad<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty>|  
|EVENT_SYSTEM_MINIMIZESTART|Cambio de propiedad<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty>|  
|EVENT_SYSTEM_MOVESIZEEND|Cambio de propiedad<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|  
|EVENT_SYSTEM_MOVESIZESTART|Cambio de propiedad<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|  
|EVENT_SYSTEM_SCROLLINGEND|Cambio de propiedad o |  
|EVENT_SYSTEM_SCROLLINGSTART|Cambio de propiedad o |  
|EVENT_SYSTEM_SOUND|Sin equivalencia|  
|EVENT_SYSTEM_SWITCHEND|Ningún equivalente, pero un evento <xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent> señala que una nueva aplicación ha recibido el enfoque|  
|EVENT_SYSTEM_SWITCHSTART|Sin equivalencia|  
|Sin equivalencia|Cambio de propiedad<xref:System.Windows.Automation.MultipleViewPattern.CurrentViewProperty>|  
|Sin equivalencia|Cambio de propiedad<xref:System.Windows.Automation.ScrollPattern.HorizontallyScrollableProperty>|  
|Sin equivalencia|Cambio de propiedad<xref:System.Windows.Automation.ScrollPattern.VerticallyScrollableProperty>|  
|Sin equivalencia|Cambio de propiedad<xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty>|  
|Sin equivalencia|Cambio de propiedad<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty>|  
|Sin equivalencia|Cambio de propiedad<xref:System.Windows.Automation.ScrollPattern.HorizontalViewSizeProperty>|  
|Sin equivalencia|Cambio de propiedad<xref:System.Windows.Automation.ScrollPattern.VerticalViewSizeProperty>|  
|Sin equivalencia|Cambio de propiedad<xref:System.Windows.Automation.TogglePattern.ToggleStateProperty>|  
|Sin equivalencia|Cambio de propiedad<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty>|  
|Sin equivalencia|Evento<xref:System.Windows.Automation.AutomationElement.AsyncContentLoadedEvent>|  
|Sin equivalencia|<xref:System.Windows.Automation.AutomationElement.ToolTipOpenedEvent>|  
  
<a name="Security_compare"></a>
## <a name="security"></a>Seguridad  
 Algunos escenarios de personalización de `IAccessible` requieren el ajuste de `IAccessible` de base y la llamada a través de él. Esto tiene implicaciones de seguridad, puesto que un componente de confianza parcial no debería ser un intermediario en una ruta de acceso a código.  
  
 El modelo [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elimina la necesidad de que los proveedores realicen llamadas a otro código de proveedor. El servicio principal de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] realiza toda la agregación necesaria.  
  
## <a name="see-also"></a>Consulte también

- [Fundamentos de automatización de la interfaz de usuario](index.md)
