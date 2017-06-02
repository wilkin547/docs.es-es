---
title: "UI Automation and Microsoft Active Accessibility | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Active Accessibility"
  - "UI Automation, Active Accessibility compared to"
  - "UI Automation, Microsoft Active Accessibility"
  - "Active Accessibility, UI Automation compared to"
ms.assetid: 87bee662-0a3e-4232-a421-20e7a5968321
caps.latest.revision: 24
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 23
---
# UI Automation and Microsoft Active Accessibility
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)] fue la solución anterior para hacer que las aplicaciones fueran accesibles.[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] es el nuevo modelo de accesibilidad para [!INCLUDE[TLA#tla_win](../../../includes/tlasharptla-win-md.md)] y está pensado para abordar las necesidades de los productos de tecnología de asistencia y herramientas de prueba automatizadas.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ofrece muchas mejoras respecto a [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)].  
  
 En este tema se incluyen las principales características de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] y se explica cómo estas características se diferencian de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)].  
  
<a name="Programming_Languages_compare"></a>   
## Lenguajes de programación  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] se basa en el [!INCLUDE[TLA#tla_com](../../../includes/tlasharptla-com-md.md)] con compatibilidad para interfaces duales y, por tanto, se puede programar en C o C\+\+, [!INCLUDE[TLA#tla_vb6](../../../includes/tlasharptla-vb6-md.md)] y lenguajes de scripting.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] \(incluida la biblioteca del proveedor del lado cliente para los controles estándar\) se escribe en código administrado y las aplicaciones cliente de automatización de la interfaz de usuario se programan con mayor facilidad mediante [!INCLUDE[TLA#tla_vcshrp](../../../includes/tlasharptla-vcshrp-md.md)] o [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]. Los proveedores de automatización de la interfaz de usuario, que son implementaciones de interfaz, se pueden escribir en código administrado o en C\/C\+\+.  
  
<a name="Support_in_Windows_Presentation_Foundation_"></a>   
## Compatibilidad en Windows Presentation Foundation  
 [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] es el nuevo modelo para crear interfaces de usuario. Los elementos [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] no contienen compatibilidad nativa para [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]; sin embargo, admiten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], que incluye compatibilidad de puente para los clientes de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. Solo los clientes creados de manera específica para [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] pueden aprovechar al máximo las características de accesibilidad de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)], como la amplia compatibilidad con texto.  
  
<a name="Servers_and_Clients_compare"></a>   
## Servidores y clientes  
 En [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)], los servidores y clientes se comunican directamente, en gran medida a través de la implementación del servidor de `IAccessible`.  
  
 En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], un servicio principal se encuentra entre el servidor \(denominado proveedor\) y el cliente. El servicio principal realiza llamadas a las interfaces implementadas por los proveedores y ofrece servicios adicionales como la generación de identificadores únicos en tiempo de ejecución para los elementos. Las aplicaciones cliente usan funciones de la biblioteca para llamar al servicio [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
 Los proveedores de la automatización de la interfaz de usuario pueden ofrecer información a los clientes de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] y los servidores de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] pueden ofrecer información a las aplicaciones cliente de la automatización de la interfaz de usuario. Sin embargo, dado que [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] no expone tanta información como [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], los dos modelos no son totalmente compatibles.  
  
<a name="UI_Elements_compare"></a>   
## Elementos de interfaz de usuario  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] presenta los elementos [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] como una interfaz `IAccessible` o como un identificador secundario. Es difícil comparar dos punteros `IAccessible` para determinar si hacen referencia al mismo elemento.  
  
 En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], cada elemento se representa como un objeto <xref:System.Windows.Automation.AutomationElement>. La comparación se realiza mediante el operador de igualdad o el método <xref:System.Windows.Automation.AutomationElement.Equals%2A>, que comparan los identificadores únicos en tiempo de ejecución de los elementos.  
  
<a name="Tree_Views_and_Navigation_compare"></a>   
## Vistas de árbol y navegación  
 Los elementos [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] de la pantalla pueden verse como una estructura de árbol con el escritorio como la raíz, las ventanas de la aplicación como elementos secundarios inmediatos y los elementos que se encuentran dentro de las aplicaciones como descendientes más lejanos.  
  
 En [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)], muchos elementos de automatización que son irrelevantes para los usuarios finales se exponen en el árbol. Las aplicaciones cliente tienen que mirar todos los elementos para determinar cuáles son significativos.  
  
 Las aplicaciones cliente de la automatización de la interfaz de usuario ven la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] mediante una vista filtrada. La vista solo contiene elementos de interés: aquellos que ofrecen información al usuario o habilitan la interacción. Hay vistas predefinidas que incluyen solo elementos de control y solo elementos de contenido; además, las aplicaciones pueden definir vistas personalizadas.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] simplifica la tarea de describir la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] al usuario y de ayudar al usuario para que interactúe con la aplicación.  
  
 La navegación entre elementos, en [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)], es espacial \(por ejemplo, desplazarse al elemento que se encuentra a la izquierda de la pantalla\), lógica \(por ejemplo, moverse al siguiente elemento de menú o el siguiente elemento en el orden de tabulación dentro de un cuadro de diálogo\) o jerárquica \(por ejemplo, mover el primer elemento secundario de un contenedor o desde el elemento secundario a su elemento principal\). La navegación jerárquica resulta complicada por el hecho de que los elementos secundarios no siempre son objetos que implementan `IAccessible`.  
  
 En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], todos los elementos [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] son objetos <xref:System.Windows.Automation.AutomationElement> que admiten la misma funcionalidad básica. \(Desde el punto de vista del proveedor, son objetos que implementan una interfaz heredada de <xref:System.Windows.Automation.Provider.IRawElementProviderSimple>\). La navegación es principalmente jerárquica: de elementos primarios a elementos secundarios, y de un elemento del mismo nivel al siguiente. \(La navegación entre elementos del mismo nivel tiene un componente lógico, ya que puede seguir el orden de tabulación\). Puede navegar desde cualquier punto de partida, usando cualquier vista filtrada del árbol, mediante la clase <xref:System.Windows.Automation.TreeWalker>. También puede navegar a determinados elementos secundarios o descendientes mediante el uso de <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> y <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; por ejemplo, es muy sencillo recuperar todos los elementos de un cuadro de diálogo que admitan un patrón de control especificado.  
  
 La navegación en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] es más coherente que en [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. Algunos elementos como las listas desplegables y las ventanas emergentes aparecen dos veces en el árbol [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] y la navegación desde ellos puede tener resultados inesperados. Es realmente imposible implementar [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] correctamente para un control rebar.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] habilita la reorganización dinámica de relación jerárquica y el cambio de posición, para que un elemento se pueda colocar en cualquier lugar del árbol a pesar de la jerarquía impuesta por la propiedad de las ventanas.  
  
<a name="Roles_and_Control_Types"></a>   
## Roles y tipos de control  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] usa la propiedad `accRole` \(`IAccessible::get_actRole`\) para recuperar una descripción del rol del elemento en la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], como ROLE\_SYSTEM\_SLIDER o ROLE\_SYSTEM\_MENUITEM. El rol de un elemento es la pista principal para su funcionalidad disponible. La interacción con un control se logra mediante métodos fijos como `IAccessible::accSelect` y `IAccessible::accDoDefaultAction`. La interacción entre la aplicación cliente y el [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] se limita a lo que se puede hacer mediante `IAccessible`.  
  
 En cambio, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] desacopla en gran medida el tipo de control del elemento \(descrito por la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A>\) de su funcionalidad esperada. La funcionalidad se determina por los patrones de control admitidos por el proveedor a través de su implementación de interfaces especializadas. Los patrones de control se pueden combinar para describir el conjunto completo de la funcionalidad admitida por un determinado elemento [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Algunos proveedores deben admitir un patrón de control concreto; por ejemplo, el proveedor de una casilla debe admitir el patrón de control Toggle. Otros proveedores deben admitir uno o más patrones de un conjunto de patrones de control; por ejemplo, un botón debe admitir Toggle o Invoke. Sin embargo, otros no admiten ningún patrón de control; por ejemplo, un panel que no se pueda mover, cambiar de tamaño o acoplar no tiene ningún patrón de control.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] admite controles personalizados, que se identifican mediante la propiedad <xref:System.Windows.Automation.ControlType.Custom> y se pueden describir por la propiedad <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>.  
  
 En la tabla siguiente se muestra la asignación de los roles [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] a tipos de control [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
|Rol [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|Tipo de control [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|---------------------------------------------------------------------|-------------------------------------------------------------------------------------------|  
|ROLE\_SYSTEM\_PUSHBUTTON|Botón|  
|ROLE\_SYSTEM\_CLIENT|Calendario|  
|ROLE\_SYSTEM\_CHECKBUTTON|Casilla de verificación|  
|ROLE\_SYSTEM\_COMBOBOX|Cuadro combinado|  
|ROLE\_SYSTEM\_CLIENT|Personalizados|  
|ROLE\_SYSTEM\_LIST|Cuadrícula de datos|  
|ROLE\_SYSTEM\_LISTITEM|Elemento de datos|  
|ROLE\_SYSTEM\_DOCUMENT|Documento|  
|ROLE\_SYSTEM\_TEXT|Editar|  
|ROLE\_SYSTEM\_GROUPING|Agrupar|  
|ROLE\_SYSTEM\_LIST|Encabezado|  
|ROLE\_SYSTEM\_COLUMNHEADER|Elemento de encabezado|  
|ROLE\_SYSTEM\_LINK|Hipervínculo|  
|ROLE\_SYSTEM\_GRAPHIC|Imagen|  
|ROLE\_SYSTEM\_LIST|Lista|  
|ROLE\_SYSTEM\_LISTITEM|Elemento de lista|  
|ROLE\_SYSTEM\_MENUPOPUP|Menú|  
|ROLE\_SYSTEM\_MENUBAR|Barra de menús|  
|ROLE\_SYSTEM\_MENUITEM|Elemento de menú|  
|ROLE\_SYSTEM\_PANE|Panel|  
|ROLE\_SYSTEM\_PROGRESSBAR|Barra de progreso|  
|ROLE\_SYSTEM\_RADIOBUTTON|Botón de radio|  
|ROLE\_SYSTEM\_SCROLLBAR|Barra de desplazamiento|  
|ROLE\_SYSTEM\_SEPARATOR|Separador|  
|ROLE\_SYSTEM\_SLIDER|Slider|  
|ROLE\_SYSTEM\_SPINBUTTON|Spinner|  
|ROLE\_SYSTEM\_SPLITBUTTON|Botón de expansión|  
|ROLE\_SYSTEM\_STATUSBAR|Barra de estado|  
|ROLE\_SYSTEM\_PAGETABLIST|Tab|  
|ROLE\_SYSTEM\_PAGETAB|Elemento de pestaña|  
|ROLE\_SYSTEM\_TABLE|Tabla|  
|ROLE\_SYSTEM\_STATICTEXT|Texto|  
|ROLE\_SYSTEM\_INDICATOR|Thumb|  
|ROLE\_SYSTEM\_TITLEBAR|Barra de título|  
|ROLE\_SYSTEM\_TOOLBAR|Barra de herramientas|  
|ROLE\_SYSTEM\_TOOLTIP|Información sobre herramientas|  
|ROLE\_SYSTEM\_OUTLINE|Árbol|  
|ROLE\_SYSTEM\_OUTLINEITEM|Elemento de árbol|  
|ROLE\_SYSTEM\_WINDOW|Ventana|  
  
 Para más información sobre los diferentes tipos de control, vea [UI Automation Control Types](../../../docs/framework/ui-automation/ui-automation-control-types.md).  
  
<a name="States_and_Properties"></a>   
## Estados y propiedades  
 En [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)], los elementos admiten un conjunto común de propiedades y algunas propiedades \(como `accState`\) deben describir aspectos muy diferentes, en función del rol del elemento. Los servidores deben implementar todos los métodos de `IAccessible` que devuelvan una propiedad, incluso aquellos que no son pertinentes para el elemento.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] define muchas más propiedades, algunas de las cuales se corresponden con estados en [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. Algunas son comunes para todos los elementos, pero otras son específicas de tipos de control y patrones de control. Las propiedades se distinguen mediante identificadores únicos y la mayoría de las propiedades se pueden recuperar mediante el uso de un único método, <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> o <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>. Muchas propiedades también se pueden recuperar con facilidad a partir de los descriptores de acceso de propiedad <xref:System.Windows.Automation.AutomationElement.Current%2A> y <xref:System.Windows.Automation.AutomationElement.Cached%2A>.  
  
 Un proveedor de la automatización de la interfaz de usuario no tiene que implementar propiedades irrelevantes, pero puede devolver simplemente un valor `null` para cualquier propiedad que no admita. Además, el servicio principal [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] puede obtener algunas propiedades del proveedor de ventana predeterminado y estas se combinan con propiedades implementadas de manera explícita por el proveedor.  
  
 Además de admitir muchas más propiedades, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ofrece un rendimiento mejorado al permitir que se recuperen varias propiedades con una llamada única entre procesos.  
  
 En la tabla siguiente se muestra la correspondencia entre las propiedades de los dos modelos.  
  
|Descriptor de acceso de propiedades [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|Id. de propiedad [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Comentarios|  
|-----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|-----------------|  
|`get_accKeyboardShortcut`|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty> o <xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|`AccessKeyProperty` tiene prioridad si ambos están presentes.|  
|`get_accName`|<xref:System.Windows.Automation.AutomationElement.NameProperty>|``|  
|`get_accRole`|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|Vea la tabla anterior para la asignación de roles a tipos de control.|  
|`get_accValue`|<xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=fullName>|Válido únicamente para tipos de control que admiten ValuePattern o RangeValuePattern. Los valores de RangeValue se normalizan entre 0 y 100, para que sean coherentes con el comportamiento de MSAA. Los elementos de valor usan una cadena.|  
|`get_accHelp`|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>||  
|`accLocation`|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>||  
|`get_accDescription`|No se admiten en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].|`accDescription` no tenía una especificación clara en MSAA, lo que hizo que los proveedores colocaran diferente información en esta propiedad.|  
|`get_accHelpTopic`|No se admite en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].||  
  
 En la tabla siguiente se muestra qué propiedades [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] corresponden a constantes de estado [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)].  
  
|Estado [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|Propiedad [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|¿Desencadena el cambio de estado?|  
|------------------------------------------------------------------------|-------------------------------------------------------------------------------------|---------------------------------------|  
|STATE\_SYSTEM\_CHECKED|Para casilla, <xref:System.Windows.Automation.TogglePattern.ToggleStateProperty><br /><br /> Para botón de radio, <xref:System.Windows.Automation.SelectionItemPattern.IsSelectedProperty>|Y|  
|STATE\_SYSTEM\_COLLAPSED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> \= <xref:System.Windows.Automation.ExpandCollapseState>|Y|  
|STATE\_SYSTEM\_EXPANDED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> \= <xref:System.Windows.Automation.ExpandCollapseState> o <xref:System.Windows.Automation.ExpandCollapseState>|Y|  
|STATE\_SYSTEM\_FOCUSABLE|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|N|  
|STATE\_SYSTEM\_FOCUSED|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|N|  
|STATE\_SYSTEM\_HASPOPUP|<xref:System.Windows.Automation.ExpandCollapsePattern> para elementos de menú|N|  
|STATE\_SYSTEM\_INVISIBLE|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty> \= True y <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A> produce <xref:System.Windows.Automation.NoClickablePointException>|N|  
|STATE\_SYSTEM\_LINKED|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> \=<br /><br /> <xref:System.Windows.Automation.ControlType.Hyperlink>|N|  
|STATE\_SYSTEM\_MIXED|<xref:System.Windows.Automation.TogglePattern.TogglePatternInformation.ToggleState%2A> \= <xref:System.Windows.Automation.ToggleState>|N|  
|STATE\_SYSTEM\_MOVEABLE|<xref:System.Windows.Automation.TransformPattern.CanMoveProperty>|N|  
|STATE\_SYSTEM\_MUTLISELECTABLE|<xref:System.Windows.Automation.SelectionPattern.CanSelectMultipleProperty>|N|  
|STATE\_SYSTEM\_OFFSCREEN|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty> \= True|N|  
|STATE\_SYSTEM\_PROTECTED|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|N|  
|STATE\_SYSTEM\_READONLY|<xref:System.Windows.Automation.RangeValuePattern.IsReadOnlyProperty?displayProperty=fullName> y <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty?displayProperty=fullName>|N|  
|STATE\_SYSTEM\_SELECTABLE|Se admite <xref:System.Windows.Automation.SelectionItemPattern>|N|  
|STATE\_SYSTEM\_SELECTED|<xref:System.Windows.Automation.SelectionItemPattern.IsSelectedProperty>|N|  
|STATE\_SYSTEM\_SIZEABLE|<xref:System.Windows.Automation.TransformPattern.TransformPatternInformation.CanResize%2A>|N|  
|STATE\_SYSTEM\_UNAVAILABLE|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|Y|  
  
 Los siguientes estados no se implementaron por la mayoría de los servidores de control [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] o no tienen equivalente en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
|Estado [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|Comentarios|  
|------------------------------------------------------------------------|-----------------|  
|STATE\_SYSTEM\_BUSY|No disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE\_SYSTEM\_DEFAULT|No disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE\_SYSTEM\_ANIMATED|No disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE\_SYSTEM\_EXTSELECTABLE|No se ha implementado ampliamente por los servidores de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE\_SYSTEM\_MARQUEED|No se ha implementado ampliamente por los servidores de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE\_SYSTEM\_SELFVOICING|No se ha implementado ampliamente por los servidores de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE\_SYSTEM\_TRAVERSED|No disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE\_SYSTEM\_ALERT\_HIGH|No se ha implementado ampliamente por los servidores de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE\_SYSTEM\_ALERT\_MEDIUM|No se ha implementado ampliamente por los servidores de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE\_SYSTEM\_ALERT\_LOW|No se ha implementado ampliamente por los servidores de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE\_SYSTEM\_FLOATING|No se ha implementado ampliamente por los servidores de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE\_SYSTEM\_HOTTRACKED|No disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE\_SYSTEM\_PRESSED|No disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
  
 Para obtener una lista completa de los identificadores de propiedad [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vea [UI Automation Properties Overview](../../../docs/framework/ui-automation/ui-automation-properties-overview.md).  
  
<a name="uiautomation_events_compare"></a>   
## Eventos  
 El mecanismo de eventos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], a diferencia del de [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)], no se basa en el enrutamiento de eventos de Windows \(que está estrechamente relacionado con los identificadores de ventana\) y no requiere la aplicación cliente para configurar enlaces. Las suscripciones a eventos se pueden ajustar no solo para eventos concretos, sino también para partes específicas del árbol. Los proveedores también pueden ajustar su generación de eventos mediante el mantenimiento del seguimiento de qué eventos se están escuchando.  
  
 También resulta más sencillo para los clientes recuperar los elementos que generan eventos, ya que estos se pasan directamente a la devolución de llamada de evento. Las propiedades del elemento se recuperan previamente de manera automática si había una solicitud de caché activa cuando el cliente se suscribió al evento.  
  
 En la tabla siguiente se muestra la correspondencia de WinEvents [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] y eventos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
|WinEvent|Identificador de evento [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|--------------|---------------------------------------------------------------------------------------------------|  
|EVENT\_OBJECT\_ACCELERATORCHANGE|Cambio de propiedad <xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|  
|EVENT\_OBJECT\_CONTENTSCROLLED|Cambio de propiedad <xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> o <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty> en las barras de desplazamiento asociadas|  
|EVENT\_OBJECT\_CREATE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT\_OBJECT\_DEFACTIONCHANGE|No equivalente|  
|EVENT\_OBJECT\_DESCRIPTIONCHANGE|Ningún equivalente exacto; quizás cambio de propiedad <xref:System.Windows.Automation.AutomationElement.HelpTextProperty> o <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>|  
|EVENT\_OBJECT\_DESTROY|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT\_OBJECT\_FOCUS|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT\_OBJECT\_HELPCHANGE|Cambio de <xref:System.Windows.Automation.AutomationElement.HelpTextProperty>|  
|EVENT\_OBJECT\_HIDE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT\_OBJECT\_LOCATIONCHANGE|Cambio de propiedad <xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|  
|EVENT\_OBJECT\_NAMECHANGE|Cambio de propiedad <xref:System.Windows.Automation.AutomationElement.NameProperty>|  
|EVENT\_OBJECT\_PARENTCHANGE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT\_OBJECT\_REORDER|No se usa de manera coherente en [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. No se define ningún evento correspondiente directamente en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].|  
|EVENT\_OBJECT\_SELECTION|<xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>|  
|EVENT\_OBJECT\_SELECTIONADD|<xref:System.Windows.Automation.SelectionItemPattern.ElementAddedToSelectionEvent>|  
|EVENT\_OBJECT\_SELECTIONREMOVE|<xref:System.Windows.Automation.SelectionItemPattern.ElementRemovedFromSelectionEvent>|  
|EVENT\_OBJECT\_SELECTIONWITHIN|No equivalente|  
|EVENT\_OBJECT\_SHOW|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT\_OBJECT\_STATECHANGE|Diversos eventos de cambio de propiedades|  
|EVENT\_OBJECT\_VALUECHANGE|Se han cambiado <xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=fullName> y <xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=fullName>|  
|EVENT\_SYSTEM\_ALERT|No equivalente|  
|EVENT\_SYSTEM\_CAPTUREEND|No equivalente|  
|EVENT\_SYSTEM\_CAPTURESTART|No equivalente|  
|EVENT\_SYSTEM\_CONTEXTHELPEND|No equivalente|  
|EVENT\_SYSTEM\_CONTEXTHELPSTART|No equivalente|  
|EVENT\_SYSTEM\_DIALOGEND|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|  
|EVENT\_SYSTEM\_DIALOGSTART|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|  
|EVENT\_SYSTEM\_DRAGDROPEND|No equivalente|  
|EVENT\_SYSTEM\_DRAGDROPSTART|No equivalente|  
|EVENT\_SYSTEM\_FOREGROUND|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT\_SYSTEM\_MENUEND|<xref:System.Windows.Automation.AutomationElement.MenuClosedEvent>|  
|EVENT\_SYSTEM\_MENUPOPUPEND|<xref:System.Windows.Automation.AutomationElement.MenuClosedEvent>|  
|EVENT\_SYSTEM\_MENUPOPUPSTART|<xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent>|  
|EVENT\_SYSTEM\_MENUSTART|<xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent>|  
|EVENT\_SYSTEM\_MINIMIZEEND|Cambio de propiedad <xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty>|  
|EVENT\_SYSTEM\_MINIMIZESTART|Cambio de propiedad <xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty>|  
|EVENT\_SYSTEM\_MOVESIZEEND|Cambio de propiedad <xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|  
|EVENT\_SYSTEM\_MOVESIZESTART|Cambio de propiedad <xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|  
|EVENT\_SYSTEM\_SCROLLINGEND|Cambio de propiedad <xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> o <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty>|  
|EVENT\_SYSTEM\_SCROLLINGSTART|Cambio de propiedad <xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> o <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty>|  
|EVENT\_SYSTEM\_SOUND|No equivalente|  
|EVENT\_SYSTEM\_SWITCHEND|Ningún equivalente, pero un evento <xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent> señala que una nueva aplicación ha recibido el enfoque|  
|EVENT\_SYSTEM\_SWITCHSTART|No equivalente|  
|No equivalente|Cambio de propiedad <xref:System.Windows.Automation.MultipleViewPattern.CurrentViewProperty>|  
|No equivalente|Cambio de propiedad <xref:System.Windows.Automation.ScrollPattern.HorizontallyScrollableProperty>|  
|No equivalente|Cambio de propiedad <xref:System.Windows.Automation.ScrollPattern.VerticallyScrollableProperty>|  
|No equivalente|Cambio de propiedad <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty>|  
|No equivalente|Cambio de propiedad <xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty>|  
|No equivalente|Cambio de propiedad <xref:System.Windows.Automation.ScrollPattern.HorizontalViewSizeProperty>|  
|No equivalente|Cambio de propiedad <xref:System.Windows.Automation.ScrollPattern.VerticalViewSizeProperty>|  
|No equivalente|Cambio de propiedad <xref:System.Windows.Automation.TogglePattern.ToggleStateProperty>|  
|No equivalente|Cambio de propiedad <xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty>|  
|No equivalente|Evento <xref:System.Windows.Automation.AutomationElement.AsyncContentLoadedEvent>|  
|No equivalente|<xref:System.Windows.Automation.AutomationElement.ToolTipOpenedEvent>|  
  
<a name="Security_compare"></a>   
## Seguridad  
 Algunos escenarios de personalización de `IAccessible` requieren el ajuste de `IAccessible` de base y la llamada a través de él. Esto tiene implicaciones de seguridad, puesto que un componente de confianza parcial no debería ser un intermediario en una ruta de acceso a código.  
  
 El modelo [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elimina la necesidad de que los proveedores realicen llamadas a otro código de proveedor. El servicio principal de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] realiza toda la agregación necesaria.  
  
## Vea también  
 [UI Automation Fundamentals](../../../docs/framework/ui-automation/index.md)