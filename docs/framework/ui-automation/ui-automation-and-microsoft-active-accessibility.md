---
title: UI Automation y Microsoft Active Accessibility
ms.date: 03/30/2017
helpviewer_keywords:
- Active Accessibility
- UI Automation, Active Accessibility compared to
- UI Automation, Microsoft Active Accessibility
- Active Accessibility, UI Automation compared to
ms.assetid: 87bee662-0a3e-4232-a421-20e7a5968321
ms.openlocfilehash: 29a6b897115c5f2f3ae8d7e4ec708be59dc0d85b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115341"
---
# <a name="ui-automation-and-microsoft-active-accessibility"></a>UI Automation y Microsoft Active Accessibility
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)] fue la solución anterior para hacer que las aplicaciones sean accesibles. [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] es el nuevo modelo de accesibilidad para [!INCLUDE[TLA#tla_win](../../../includes/tlasharptla-win-md.md)] y está pensado para abordar las necesidades de los productos de tecnología y herramientas de pruebas automatizadas. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ofrece muchas mejoras sobre [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)].  
  
 En este tema se incluyen las principales características de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] y se explica cómo estas características se diferencian de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)].  
  
<a name="Programming_Languages_compare"></a>   
## <a name="programming-languages"></a>Lenguajes de programación  
<[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] se basa en el [!INCLUDE[TLA#tla_com](../../../includes/tlasharptla-com-md.md)] con compatibilidad para interfaces duales y, por tanto, es programable en C/C ++, [!INCLUDE[TLA#tla_vb6](../../../includes/tlasharptla-vb6-md.md)]y lenguajes de scripting. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] (incluida la biblioteca de proveedor de cliente para los controles estándar) se escribe en código administrado y las aplicaciones cliente de automatización de interfaz de usuario se programan con mayor facilidad mediante C# o Visual Basic. NET. Los proveedores de automatización de la interfaz de usuario, que son implementaciones de interfaz, se pueden escribir en código administrado o en C/C++.  
  
<a name="Support_in_Windows_Presentation_Foundation_"></a>   
## <a name="support-in-windows-presentation-foundation"></a>Compatibilidad en Windows Presentation Foundation  
 Windows Presentation Foundation (WPF) es el nuevo modelo para crear interfaces de usuario. [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] los elementos no contienen compatibilidad nativa para [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]; sin embargo, que admiten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], que incluye compatibilidad para de puente [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] los clientes. Solo los clientes creados de manera específica para [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] pueden aprovechar al máximo las características de accesibilidad de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)], como la amplia compatibilidad con texto.  
  
<a name="Servers_and_Clients_compare"></a>   
## <a name="servers-and-clients"></a>Servidores y clientes  
 En [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)], los servidores y clientes se comunican directamente, en gran medida a través de la implementación del servidor de `IAccessible`.  
  
 En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], un servicio principal se encuentra entre el servidor (denominado proveedor) y el cliente. El servicio principal realiza llamadas a las interfaces implementadas por los proveedores y ofrece servicios adicionales como la generación de identificadores únicos en tiempo de ejecución para los elementos. Las aplicaciones cliente usan funciones de la biblioteca para llamar al servicio [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 Los proveedores de la automatización de la interfaz de usuario pueden ofrecer información a los clientes de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] y los servidores de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] pueden ofrecer información a las aplicaciones cliente de la automatización de la interfaz de usuario. Sin embargo, dado que [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] no expone tanta información como [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], los dos modelos no son totalmente compatibles.  
  
<a name="UI_Elements_compare"></a>   
## <a name="ui-elements"></a>Elementos de interfaz de usuario  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] presenta [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elementos como un `IAccessible` interfaz o como un identificador secundario. Es difícil comparar dos punteros `IAccessible` para determinar si hacen referencia al mismo elemento.  
  
 En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], cada elemento se representa como un objeto <xref:System.Windows.Automation.AutomationElement> . La comparación se realiza mediante el operador de igualdad o el método <xref:System.Windows.Automation.AutomationElement.Equals%2A> , que comparan los identificadores únicos en tiempo de ejecución de los elementos.  
  
<a name="Tree_Views_and_Navigation_compare"></a>   
## <a name="tree-views-and-navigation"></a>Vistas de árbol y navegación  
 Los elementos [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] de la pantalla pueden verse como una estructura de árbol con el escritorio como la raíz, las ventanas de la aplicación como elementos secundarios inmediatos y los elementos que se encuentran dentro de las aplicaciones como descendientes más lejanos.  
  
 En [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)], muchos elementos de automatización que son irrelevantes para los usuarios finales se exponen en el árbol. Las aplicaciones cliente tienen que mirar todos los elementos para determinar cuáles son significativos.  
  
 Las aplicaciones cliente de la automatización de la interfaz de usuario ven la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] mediante una vista filtrada. La vista solo contiene elementos de interés: aquellos que ofrecen información al usuario o habilitan la interacción. Hay vistas predefinidas que incluyen solo elementos de control y solo elementos de contenido; además, las aplicaciones pueden definir vistas personalizadas. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] simplifica la tarea de describir el [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] al usuario y ayudar al usuario interactuar con la aplicación.  
  
 La navegación entre elementos, en [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)], es espacial (por ejemplo, desplazarse al elemento que se encuentra a la izquierda de la pantalla), lógica (por ejemplo, moverse al siguiente elemento de menú o el siguiente elemento en el orden de tabulación dentro de un cuadro de diálogo) o jerárquica (por ejemplo, mover el primer elemento secundario de un contenedor o desde el elemento secundario a su elemento principal). La navegación jerárquica resulta complicada por el hecho de que los elementos secundarios no siempre son objetos que implementan `IAccessible`.  
  
 En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], todos los elementos [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] son objetos <xref:System.Windows.Automation.AutomationElement> que admiten la misma funcionalidad básica. (Desde el punto de vista del proveedor, son objetos que implementan una interfaz heredada de <xref:System.Windows.Automation.Provider.IRawElementProviderSimple>). La navegación es principalmente jerárquica: de elementos primarios a elementos secundarios, y de un elemento del mismo nivel al siguiente. (La navegación entre elementos del mismo nivel tiene un componente lógico, ya que puede seguir el orden de tabulación). Puede navegar desde cualquier punto de partida, usando cualquier vista filtrada del árbol, mediante la clase <xref:System.Windows.Automation.TreeWalker>. También puede navegar a determinados elementos secundarios o descendientes mediante el uso de <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> y <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; por ejemplo, es muy sencillo recuperar todos los elementos de un cuadro de diálogo que admitan un patrón de control especificado.  
  
 La navegación en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] es más coherente que en [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. Algunos elementos como las listas desplegables y las ventanas emergentes aparecen dos veces en el árbol [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] y la navegación desde ellos puede tener resultados inesperados. Es realmente imposible implementar [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] correctamente para un control rebar. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] permite cambiar el elemento primario y cambiar su posición, por lo que un elemento puede colocarse en cualquier lugar en el árbol a pesar de la jerarquía impuesta por la propiedad de windows.  
  
<a name="Roles_and_Control_Types"></a>   
## <a name="roles-and-control-types"></a>Roles y tipos de control  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] usa el `accRole` propiedad (`IAccessible::get_actRole`) para recuperar una descripción del rol del elemento en el [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], como ROLE_SYSTEM_SLIDER o ROLE_SYSTEM_MENUITEM. El rol de un elemento es la pista principal para su funcionalidad disponible. La interacción con un control se logra mediante métodos fijos como `IAccessible::accSelect` y `IAccessible::accDoDefaultAction`. La interacción entre la aplicación cliente y el [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] se limita a lo que se puede hacer mediante `IAccessible`.  
  
 En cambio, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] desacopla en gran medida el tipo de control del elemento (descrito por la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> ) de su funcionalidad esperada. La funcionalidad se determina por los patrones de control admitidos por el proveedor a través de su implementación de interfaces especializadas. Los patrones de control se pueden combinar para describir el conjunto completo de la funcionalidad admitida por un determinado elemento [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] . Algunos proveedores deben admitir un patrón de control concreto; por ejemplo, el proveedor de una casilla debe admitir el patrón de control Toggle. Otros proveedores deben admitir uno o más patrones de un conjunto de patrones de control; por ejemplo, un botón debe admitir Toggle o Invoke. Sin embargo, otros no admiten ningún patrón de control; por ejemplo, un panel que no se pueda mover, cambiar de tamaño o acoplar no tiene ningún patrón de control.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] admite controles personalizados, que se identifican por la <xref:System.Windows.Automation.ControlType.Custom> propiedad y se puede describir mediante el <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty> propiedad.  
  
 En la tabla siguiente se muestra la asignación de los roles [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] a tipos de control [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] rol|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Tipo de control|  
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------|  
|ROLE_SYSTEM_PUSHBUTTON|Botón|  
|ROLE_SYSTEM_CLIENT|Calendario|  
|ROLE_SYSTEM_CHECKBUTTON|Casilla de verificación|  
|ROLE_SYSTEM_COMBOBOX|Cuadro combinado|  
|ROLE_SYSTEM_CLIENT|Personalizados|  
|ROLE_SYSTEM_LIST|Cuadrícula de datos|  
|ROLE_SYSTEM_LISTITEM|Elemento de datos|  
|ROLE_SYSTEM_DOCUMENT|Documento|  
|ROLE_SYSTEM_TEXT|Editar|  
|ROLE_SYSTEM_GROUPING|Agrupar|  
|ROLE_SYSTEM_LIST|Header|  
|ROLE_SYSTEM_COLUMNHEADER|Elemento de encabezado|  
|ROLE_SYSTEM_LINK|Hipervínculo|  
|ROLE_SYSTEM_GRAPHIC|Imagen|  
|ROLE_SYSTEM_LIST|Lista|  
|ROLE_SYSTEM_LISTITEM|Elemento de lista|  
|ROLE_SYSTEM_MENUPOPUP|Menú|  
|ROLE_SYSTEM_MENUBAR|Barra de menús|  
|ROLE_SYSTEM_MENUITEM|Elemento de menú|  
|ROLE_SYSTEM_PANE|Panel|  
|ROLE_SYSTEM_PROGRESSBAR|Barra de progreso|  
|ROLE_SYSTEM_RADIOBUTTON|Botón de radio|  
|ROLE_SYSTEM_SCROLLBAR|Barra de desplazamiento|  
|ROLE_SYSTEM_SEPARATOR|Separador|  
|ROLE_SYSTEM_SLIDER|Slider|  
|ROLE_SYSTEM_SPINBUTTON|Spinner|  
|ROLE_SYSTEM_SPLITBUTTON|Botón de expansión|  
|ROLE_SYSTEM_STATUSBAR|Barra de estado|  
|ROLE_SYSTEM_PAGETABLIST|Tab|  
|ROLE_SYSTEM_PAGETAB|Elemento de pestaña|  
|ROLE_SYSTEM_TABLE|Tabla|  
|ROLE_SYSTEM_STATICTEXT|Texto|  
|ROLE_SYSTEM_INDICATOR|Thumb|  
|ROLE_SYSTEM_TITLEBAR|Barra de título|  
|ROLE_SYSTEM_TOOLBAR|Barra de herramientas|  
|ROLE_SYSTEM_TOOLTIP|Información sobre herramientas|  
|ROLE_SYSTEM_OUTLINE|Árbol|  
|ROLE_SYSTEM_OUTLINEITEM|Elemento de árbol|  
|ROLE_SYSTEM_WINDOW|Ventana|  
  
 Para más información sobre los diferentes tipos de control, vea [UI Automation Control Types](../../../docs/framework/ui-automation/ui-automation-control-types.md).  
  
<a name="States_and_Properties"></a>   
## <a name="states-and-properties"></a>Estados y propiedades  
 En [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)], los elementos admiten un conjunto común de propiedades y algunas propiedades (como `accState`) deben describir aspectos muy diferentes, en función del rol del elemento. Los servidores deben implementar todos los métodos de `IAccessible` que devuelvan una propiedad, incluso aquellos que no son pertinentes para el elemento.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] define muchas más propiedades, algunas de las cuales se corresponden con Estados en [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. Algunas son comunes para todos los elementos, pero otras son específicas de tipos de control y patrones de control. Las propiedades se distinguen mediante identificadores únicos y la mayoría de las propiedades se pueden recuperar mediante el uso de un único método, <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> o <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>. Muchas propiedades también se pueden recuperar con facilidad a partir de los descriptores de acceso de propiedad <xref:System.Windows.Automation.AutomationElement.Current%2A> y <xref:System.Windows.Automation.AutomationElement.Cached%2A> .  
  
 Un proveedor de la automatización de la interfaz de usuario no tiene que implementar propiedades irrelevantes, pero puede devolver simplemente un valor `null` para cualquier propiedad que no admita. Además, el servicio principal [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] puede obtener algunas propiedades del proveedor de ventana predeterminado y estas se combinan con propiedades implementadas de manera explícita por el proveedor.  
  
 Además de admitir muchas más propiedades, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ofrece un rendimiento mejorado al permitir que se recuperen varias propiedades con una llamada única entre procesos.  
  
 En la tabla siguiente se muestra la correspondencia entre las propiedades de los dos modelos.  
  
|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] descriptor de acceso de propiedad|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Identificador de propiedad|Comentarios|  
|-----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|-------------|  
|`get_accKeyboardShortcut`|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty> o <xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|`AccessKeyProperty` tiene prioridad si ambos están presentes.|  
|`get_accName`|<xref:System.Windows.Automation.AutomationElement.NameProperty>||  
|`get_accRole`|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|Vea la tabla anterior para la asignación de roles a tipos de control.|  
|`get_accValue`|<xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=nameWithType>|Válido únicamente para tipos de control que admiten ValuePattern o RangeValuePattern. Los valores de RangeValue se normalizan entre 0 y 100, para que sean coherentes con el comportamiento de MSAA. Los elementos de valor usan una cadena.|  
|`get_accHelp`|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>||  
|`accLocation`|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>||  
|`get_accDescription`|No se admite en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|`accDescription` no tenía una especificación clara en MSAA, lo que hizo que los proveedores colocaran diferente información en esta propiedad.|  
|`get_accHelpTopic`|No se admite en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]||  
  
 En la tabla siguiente se muestra qué propiedades [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] corresponden a constantes de estado [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] .  
  
|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] state|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] propiedad|¿Desencadena el cambio de estado?|  
|-----------------------------------------------------------------------|------------------------------------------------------------------------------------|----------------------------|  
|STATE_SYSTEM_CHECKED|Casilla de verificación <xref:System.Windows.Automation.TogglePattern.ToggleStateProperty><br /><br /> Para el botón de radio, <xref:System.Windows.Automation.SelectionItemPattern.IsSelectedProperty>|Y|  
|STATE_SYSTEM_COLLAPSED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> = <xref:System.Windows.Automation.ExpandCollapseState.Collapsed>|Y|  
|STATE_SYSTEM_EXPANDED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> = <xref:System.Windows.Automation.ExpandCollapseState.Expanded> O <xref:System.Windows.Automation.ExpandCollapseState.PartiallyExpanded>|Y|  
|STATE_SYSTEM_FOCUSABLE|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|N|  
|STATE_SYSTEM_FOCUSED|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|N|  
|STATE_SYSTEM_HASPOPUP|<xref:System.Windows.Automation.ExpandCollapsePattern> los elementos de menú|N|  
|STATE_SYSTEM_INVISIBLE|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty> = True y <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A> hace <xref:System.Windows.Automation.NoClickablePointException>|N|  
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
  
 Los siguientes estados no se implementaron por la mayoría de los servidores de control [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] o no tienen equivalente en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] state|Comentarios|  
|-----------------------------------------------------------------------|-------------|  
|STATE_SYSTEM_BUSY|No está disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_DEFAULT|No está disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_ANIMATED|No está disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_EXTSELECTABLE|No se ha implementado ampliamente por los servidores de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_MARQUEED|No se ha implementado ampliamente por los servidores de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_SELFVOICING|No se ha implementado ampliamente por los servidores de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_TRAVERSED|No está disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_ALERT_HIGH|No se ha implementado ampliamente por los servidores de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_ALERT_MEDIUM|No se ha implementado ampliamente por los servidores de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_ALERT_LOW|No se ha implementado ampliamente por los servidores de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_FLOATING|No se ha implementado ampliamente por los servidores de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_HOTTRACKED|No está disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_PRESSED|No está disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
  
 Para obtener una lista completa de los identificadores de propiedad [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Properties Overview](../../../docs/framework/ui-automation/ui-automation-properties-overview.md).  
  
<a name="uiautomation_events_compare"></a>   
## <a name="events"></a>Eventos  
 El mecanismo de eventos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], a diferencia del de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)], no se basa en el enrutamiento de eventos de Windows (que está estrechamente relacionado con los identificadores de ventana) y no requiere la aplicación cliente para configurar enlaces. Las suscripciones a eventos se pueden ajustar no solo para eventos concretos, sino también para partes específicas del árbol. Los proveedores también pueden ajustar su generación de eventos mediante el mantenimiento del seguimiento de qué eventos se están escuchando.  
  
 También resulta más sencillo para los clientes recuperar los elementos que generan eventos, ya que estos se pasan directamente a la devolución de llamada de evento. Las propiedades del elemento se recuperan previamente de manera automática si había una solicitud de caché activa cuando el cliente se suscribió al evento.  
  
 En la tabla siguiente se muestra la correspondencia de WinEvents [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] y eventos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
|WinEvent|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] identificador de evento|  
|--------------|--------------------------------------------------------------------------------------------|  
|EVENT_OBJECT_ACCELERATORCHANGE|<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty> Cambio de propiedad|  
|EVENT_OBJECT_CONTENTSCROLLED|<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> o <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty> cambio de propiedad en las barras de desplazamiento asociadas|  
|EVENT_OBJECT_CREATE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_DEFACTIONCHANGE|No equivalente|  
|EVENT_OBJECT_DESCRIPTIONCHANGE|Ningún equivalente exacto; quizás cambio de propiedad <xref:System.Windows.Automation.AutomationElement.HelpTextProperty> o <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>|  
|EVENT_OBJECT_DESTROY|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_FOCUS|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT_OBJECT_HELPCHANGE|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty> cambiar|  
|EVENT_OBJECT_HIDE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_LOCATIONCHANGE|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> Cambio de propiedad|  
|EVENT_OBJECT_NAMECHANGE|<xref:System.Windows.Automation.AutomationElement.NameProperty> Cambio de propiedad|  
|EVENT_OBJECT_PARENTCHANGE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_REORDER|No se usa de manera coherente en [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. No se define ningún evento correspondiente directamente en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].|  
|EVENT_OBJECT_SELECTION|<xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>|  
|EVENT_OBJECT_SELECTIONADD|<xref:System.Windows.Automation.SelectionItemPattern.ElementAddedToSelectionEvent>|  
|EVENT_OBJECT_SELECTIONREMOVE|<xref:System.Windows.Automation.SelectionItemPattern.ElementRemovedFromSelectionEvent>|  
|EVENT_OBJECT_SELECTIONWITHIN|No equivalente|  
|EVENT_OBJECT_SHOW|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_STATECHANGE|Diversos eventos de cambio de propiedades|  
|EVENT_OBJECT_VALUECHANGE|<xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=nameWithType> y <xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=nameWithType> cambiado|  
|EVENT_SYSTEM_ALERT|No equivalente|  
|EVENT_SYSTEM_CAPTUREEND|No equivalente|  
|EVENT_SYSTEM_CAPTURESTART|No equivalente|  
|EVENT_SYSTEM_CONTEXTHELPEND|No equivalente|  
|EVENT_SYSTEM_CONTEXTHELPSTART|No equivalente|  
|EVENT_SYSTEM_DIALOGEND|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|  
|EVENT_SYSTEM_DIALOGSTART|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|  
|EVENT_SYSTEM_DRAGDROPEND|No equivalente|  
|EVENT_SYSTEM_DRAGDROPSTART|No equivalente|  
|EVENT_SYSTEM_FOREGROUND|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT_SYSTEM_MENUEND|<xref:System.Windows.Automation.AutomationElement.MenuClosedEvent>|  
|EVENT_SYSTEM_MENUPOPUPEND|<xref:System.Windows.Automation.AutomationElement.MenuClosedEvent>|  
|EVENT_SYSTEM_MENUPOPUPSTART|<xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent>|  
|EVENT_SYSTEM_MENUSTART|<xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent>|  
|EVENT_SYSTEM_MINIMIZEEND|<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty> Cambio de propiedad|  
|EVENT_SYSTEM_MINIMIZESTART|<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty> Cambio de propiedad|  
|EVENT_SYSTEM_MOVESIZEEND|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> Cambio de propiedad|  
|EVENT_SYSTEM_MOVESIZESTART|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> Cambio de propiedad|  
|EVENT_SYSTEM_SCROLLINGEND|<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> o <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty> cambio de propiedad|  
|EVENT_SYSTEM_SCROLLINGSTART|<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> o <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty> cambio de propiedad|  
|EVENT_SYSTEM_SOUND|No equivalente|  
|EVENT_SYSTEM_SWITCHEND|Ningún equivalente, pero un evento <xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent> señala que una nueva aplicación ha recibido el enfoque|  
|EVENT_SYSTEM_SWITCHSTART|No equivalente|  
|No equivalente|<xref:System.Windows.Automation.MultipleViewPattern.CurrentViewProperty> Cambio de propiedad|  
|No equivalente|<xref:System.Windows.Automation.ScrollPattern.HorizontallyScrollableProperty> Cambio de propiedad|  
|No equivalente|<xref:System.Windows.Automation.ScrollPattern.VerticallyScrollableProperty> Cambio de propiedad|  
|No equivalente|<xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty> Cambio de propiedad|  
|No equivalente|<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> Cambio de propiedad|  
|No equivalente|<xref:System.Windows.Automation.ScrollPattern.HorizontalViewSizeProperty> Cambio de propiedad|  
|No equivalente|<xref:System.Windows.Automation.ScrollPattern.VerticalViewSizeProperty> Cambio de propiedad|  
|No equivalente|<xref:System.Windows.Automation.TogglePattern.ToggleStateProperty> Cambio de propiedad|  
|No equivalente|<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty> Cambio de propiedad|  
|No equivalente|<xref:System.Windows.Automation.AutomationElement.AsyncContentLoadedEvent> evento|  
|No equivalente|<xref:System.Windows.Automation.AutomationElement.ToolTipOpenedEvent>|  
  
<a name="Security_compare"></a>   
## <a name="security"></a>Seguridad  
 Algunos escenarios de personalización de `IAccessible` requieren el ajuste de `IAccessible` de base y la llamada a través de él. Esto tiene implicaciones de seguridad, puesto que un componente de confianza parcial no debería ser un intermediario en una ruta de acceso a código.  
  
 El modelo [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elimina la necesidad de que los proveedores realicen llamadas a otro código de proveedor. El servicio principal de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] realiza toda la agregación necesaria.  
  
## <a name="see-also"></a>Vea también

- [Fundamentos de UI Automation](../../../docs/framework/ui-automation/index.md)
