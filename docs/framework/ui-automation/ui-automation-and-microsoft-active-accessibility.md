---
title: UI Automation y Microsoft Active Accessibility
description: Comprenda las diferencias entre la automatización de la interfaz de usuario y Microsoft Active Accessibility, la solución anterior para que las aplicaciones sean accesibles.
ms.date: 03/30/2017
helpviewer_keywords:
- Active Accessibility
- UI Automation, Active Accessibility compared to
- UI Automation, Microsoft Active Accessibility
- Active Accessibility, UI Automation compared to
ms.assetid: 87bee662-0a3e-4232-a421-20e7a5968321
ms.openlocfilehash: 0685a3f89a6578433641aaf78717f4ff377ff2f9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164073"
---
# <a name="ui-automation-and-microsoft-active-accessibility"></a>UI Automation y Microsoft Active Accessibility
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 Microsoft Active Accessibility era la solución anterior para permitir el acceso a las aplicaciones. [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]es el nuevo modelo de accesibilidad de Microsoft Windows y está diseñado para satisfacer las necesidades de productos de tecnología de asistencia y herramientas de pruebas automatizadas. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]ofrece muchas mejoras respecto a Active Accessibility.  
  
 En este tema se incluyen las características principales de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] y se explica cómo estas características se diferencian de Active Accessibility.  
  
<a name="Programming_Languages_compare"></a>
## <a name="programming-languages"></a>Lenguajes de programación  
Active Accessibility se basa en el modelo de objetos componentes (COM) compatible con interfaces duales y, por lo tanto, es programable en C/C++, Microsoft Visual Basic 6,0 y lenguajes de scripting. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)](incluida la biblioteca del proveedor del lado cliente para los controles estándar) se escribe en código administrado y las aplicaciones cliente de automatización de la interfaz de usuario se programan con mayor facilidad mediante C# o Visual Basic .NET. Los proveedores de automatización de la interfaz de usuario, que son implementaciones de interfaz, se pueden escribir en código administrado o en C/C++.  
  
<a name="Support_in_Windows_Presentation_Foundation_"></a>
## <a name="support-in-windows-presentation-foundation"></a>Compatibilidad en Windows Presentation Foundation  
 Windows Presentation Foundation (WPF) es el nuevo modelo para crear interfaces de usuario. Los elementos de WPF no contienen compatibilidad nativa con Active Accessibility; sin embargo, admiten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , que incluye compatibilidad de puente para los clientes de Active Accessibility. Solo los clientes creados específicamente para [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] pueden aprovechar al máximo las características de accesibilidad de WPF, como la amplia compatibilidad con texto.  
  
<a name="Servers_and_Clients_compare"></a>
## <a name="servers-and-clients"></a>Servidores y clientes  
 En Active Accessibility, los servidores y los clientes se comunican directamente, en gran medida a través de la implementación del servidor de `IAccessible` .  
  
 En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], un servicio principal se encuentra entre el servidor (denominado proveedor) y el cliente. El servicio principal realiza llamadas a las interfaces implementadas por los proveedores y ofrece servicios adicionales como la generación de identificadores únicos en tiempo de ejecución para los elementos. Las aplicaciones cliente usan funciones de la biblioteca para llamar al servicio [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 Los proveedores de automatización de la interfaz de usuario pueden proporcionar información a los clientes de Active Accessibility y Active Accessibility servidores pueden proporcionar información a las aplicaciones cliente de automatización de la interfaz de usuario. Sin embargo, dado que Active Accessibility no expone tanta información como [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , los dos modelos no son totalmente compatibles.  
  
<a name="UI_Elements_compare"></a>
## <a name="ui-elements"></a>Elementos de interfaz de usuario  
 Active Accessibility presenta [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] los elementos como una `IAccessible` interfaz o como un identificador secundario. Es difícil comparar dos punteros `IAccessible` para determinar si hacen referencia al mismo elemento.  
  
 En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], cada elemento se representa como un objeto <xref:System.Windows.Automation.AutomationElement> . La comparación se realiza mediante el operador de igualdad o el método <xref:System.Windows.Automation.AutomationElement.Equals%2A> , que comparan los identificadores únicos en tiempo de ejecución de los elementos.  
  
<a name="Tree_Views_and_Navigation_compare"></a>
## <a name="tree-views-and-navigation"></a>Vistas de árbol y navegación  
 Los elementos [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] de la pantalla pueden verse como una estructura de árbol con el escritorio como la raíz, las ventanas de la aplicación como elementos secundarios inmediatos y los elementos que se encuentran dentro de las aplicaciones como descendientes más lejanos.  
  
 En Active Accessibility, muchos elementos de automatización que son irrelevantes para los usuarios finales se exponen en el árbol. Las aplicaciones cliente tienen que mirar todos los elementos para determinar cuáles son significativos.  
  
 Las aplicaciones cliente de la automatización de la interfaz de usuario ven la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] mediante una vista filtrada. La vista solo contiene elementos de interés: aquellos que ofrecen información al usuario o habilitan la interacción. Hay vistas predefinidas que incluyen solo elementos de control y solo elementos de contenido; además, las aplicaciones pueden definir vistas personalizadas. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] simplifica la tarea de describir la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] al usuario y de ayudar al usuario para que interactúe con la aplicación.  
  
 La navegación entre los elementos, en Active Accessibility, es espacial (por ejemplo, al mover al elemento que se encuentra a la izquierda en la pantalla), lógica (por ejemplo, al desplazarse al siguiente elemento de menú o al siguiente elemento en el orden de tabulación dentro de un cuadro de diálogo), o a la jerarquía (por ejemplo, al mover el primer elemento secundario de un contenedor o La navegación jerárquica resulta complicada por el hecho de que los elementos secundarios no siempre son objetos que implementan `IAccessible`.  
  
 En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], todos los elementos [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] son objetos <xref:System.Windows.Automation.AutomationElement> que admiten la misma funcionalidad básica. (Desde el punto de vista del proveedor, son objetos que implementan una interfaz heredada de <xref:System.Windows.Automation.Provider.IRawElementProviderSimple> ). La navegación es principalmente jerárquica: de los elementos primarios a secundarios y de un elemento relacionado con el siguiente. (La navegación entre elementos del mismo nivel tiene un elemento lógico, ya que puede seguir el orden de tabulación). Puede navegar desde cualquier punto de partida, utilizando cualquier vista filtrada del árbol, mediante la <xref:System.Windows.Automation.TreeWalker> clase. También puede navegar a determinados elementos secundarios o descendientes mediante el uso de <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> y <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; por ejemplo, es muy sencillo recuperar todos los elementos de un cuadro de diálogo que admitan un patrón de control especificado.  
  
 La navegación en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] es más coherente que en Active Accessibility. Algunos elementos como las listas desplegables y las ventanas emergentes aparecen dos veces en el árbol de Active Accessibility y la navegación desde ellos puede tener resultados inesperados. En realidad, es imposible implementar correctamente Active Accessibility para un control rebar. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] habilita la reorganización dinámica de relación jerárquica y el cambio de posición, para que un elemento se pueda colocar en cualquier lugar del árbol a pesar de la jerarquía impuesta por la propiedad de las ventanas.  
  
<a name="Roles_and_Control_Types"></a>
## <a name="roles-and-control-types"></a>Roles y tipos de control  
 Active Accessibility usa la `accRole` propiedad ( `IAccessible::get_actRole` ) para recuperar una descripción del rol del elemento en, como [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] ROLE_SYSTEM_SLIDER o ROLE_SYSTEM_MENUITEM. El rol de un elemento es la pista principal para su funcionalidad disponible. La interacción con un control se logra mediante métodos fijos como `IAccessible::accSelect` y `IAccessible::accDoDefaultAction`. La interacción entre la aplicación cliente y el [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] se limita a lo que se puede hacer mediante `IAccessible`.  
  
 En cambio, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] desacopla en gran medida el tipo de control del elemento (descrito por la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> ) de su funcionalidad esperada. La funcionalidad se determina por los patrones de control admitidos por el proveedor a través de su implementación de interfaces especializadas. Los patrones de control se pueden combinar para describir el conjunto completo de la funcionalidad admitida por un determinado elemento [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] . Algunos proveedores deben admitir un patrón de control concreto; por ejemplo, el proveedor de una casilla debe admitir el patrón de control Toggle. Otros proveedores deben admitir uno o más patrones de un conjunto de patrones de control; por ejemplo, un botón debe admitir Toggle o Invoke. Sin embargo, otros no admiten ningún patrón de control; por ejemplo, un panel que no se pueda mover, cambiar de tamaño o acoplar no tiene ningún patrón de control.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] admite controles personalizados, que se identifican mediante la propiedad <xref:System.Windows.Automation.ControlType.Custom> y se pueden describir por la propiedad <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty> .  
  
 En la tabla siguiente se muestra la asignación de roles de Active Accessibility a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tipos de control.  
  
|Rol de Active Accessibility|Tipo de control[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------|  
|ROLE_SYSTEM_PUSHBUTTON|Botón|  
|ROLE_SYSTEM_CLIENT|Calendario|  
|ROLE_SYSTEM_CHECKBUTTON|Casilla|  
|ROLE_SYSTEM_COMBOBOX|Cuadro combinado|  
|ROLE_SYSTEM_CLIENT|Personalizada|  
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
|ROLE_SYSTEM_RADIOBUTTON|Botón de selección|  
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
 En Active Accessibility, los elementos admiten un conjunto común de propiedades y algunas propiedades (como `accState` ) deben describir aspectos muy diferentes, en función del rol del elemento. Los servidores deben implementar todos los métodos de `IAccessible` que devuelvan una propiedad, incluso aquellos que no son pertinentes para el elemento.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]define muchas más propiedades, algunas de las cuales se corresponden con Estados en Active Accessibility. Algunas son comunes para todos los elementos, pero otras son específicas de tipos de control y patrones de control. Las propiedades se distinguen mediante identificadores únicos y la mayoría de las propiedades se pueden recuperar mediante el uso de un único método, <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> o <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>. Muchas propiedades también se pueden recuperar con facilidad a partir de los descriptores de acceso de propiedad <xref:System.Windows.Automation.AutomationElement.Current%2A> y <xref:System.Windows.Automation.AutomationElement.Cached%2A> .  
  
 Un proveedor de la automatización de la interfaz de usuario no tiene que implementar propiedades irrelevantes, pero puede devolver simplemente un valor `null` para cualquier propiedad que no admita. Además, el servicio principal [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] puede obtener algunas propiedades del proveedor de ventana predeterminado y estas se combinan con propiedades implementadas de manera explícita por el proveedor.  
  
 Además de admitir muchas más propiedades, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ofrece un rendimiento mejorado al permitir que se recuperen varias propiedades con una llamada única entre procesos.  
  
 En la tabla siguiente se muestra la correspondencia entre las propiedades de los dos modelos.  
  
|Active Accessibility descriptor de acceso de propiedad|Id. de propiedad[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Observaciones|  
|-----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|-------------|  
|`get_accKeyboardShortcut`|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty> o <xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|`AccessKeyProperty` tiene prioridad si ambos están presentes.|  
|`get_accName`|<xref:System.Windows.Automation.AutomationElement.NameProperty>||  
|`get_accRole`|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|Vea la tabla anterior para la asignación de roles a tipos de control.|  
|`get_accValue`|<xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=nameWithType>|Válido únicamente para tipos de control que admiten ValuePattern o RangeValuePattern. Los valores de RangeValue se normalizan entre 0 y 100, para que sean coherentes con el comportamiento de MSAA. Los elementos de valor usan una cadena.|  
|`get_accHelp`|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>||  
|`accLocation`|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>||  
|`get_accDescription`|No se admiten en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].|`accDescription` no tenía una especificación clara en MSAA, lo que hizo que los proveedores colocaran diferente información en esta propiedad.|  
|`get_accHelpTopic`|No se admiten en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].||  
  
 En la tabla siguiente se muestran las [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] propiedades que corresponden a las constantes de estado de Active Accessibility.  
  
|Estado de Active Accessibility|Propiedad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|¿Desencadena el cambio de estado?|  
|-----------------------------------------------------------------------|------------------------------------------------------------------------------------|----------------------------|  
|STATE_SYSTEM_CHECKED|Para casilla, <xref:System.Windows.Automation.TogglePattern.ToggleStateProperty><br /><br /> Para botón de radio, <xref:System.Windows.Automation.SelectionItemPattern.IsSelectedProperty>|esté|  
|STATE_SYSTEM_COLLAPSED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> = <xref:System.Windows.Automation.ExpandCollapseState.Collapsed>|esté|  
|STATE_SYSTEM_EXPANDED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> = <xref:System.Windows.Automation.ExpandCollapseState.Expanded> o <xref:System.Windows.Automation.ExpandCollapseState.PartiallyExpanded>|esté|  
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
|STATE_SYSTEM_UNAVAILABLE|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|esté|  
  
 Los siguientes Estados no se implementaron por la mayoría de los servidores de control de Active Accessibility o no tienen equivalente en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
|Estado de Active Accessibility|Observaciones|  
|-----------------------------------------------------------------------|-------------|  
|STATE_SYSTEM_BUSY|No disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_DEFAULT|No disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_ANIMATED|No disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_EXTSELECTABLE|No está ampliamente implementado por servidores Active Accessibility|  
|STATE_SYSTEM_MARQUEED|No está ampliamente implementado por servidores Active Accessibility|  
|STATE_SYSTEM_SELFVOICING|No está ampliamente implementado por servidores Active Accessibility|  
|STATE_SYSTEM_TRAVERSED|No disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_ALERT_HIGH|No está ampliamente implementado por servidores Active Accessibility|  
|STATE_SYSTEM_ALERT_MEDIUM|No está ampliamente implementado por servidores Active Accessibility|  
|STATE_SYSTEM_ALERT_LOW|No está ampliamente implementado por servidores Active Accessibility|  
|STATE_SYSTEM_FLOATING|No está ampliamente implementado por servidores Active Accessibility|  
|STATE_SYSTEM_HOTTRACKED|No disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_PRESSED|No disponible en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
  
 Para obtener una lista completa de los identificadores de propiedad [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Properties Overview](ui-automation-properties-overview.md).  
  
<a name="uiautomation_events_compare"></a>
## <a name="events"></a>Eventos  
 El mecanismo de eventos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , a diferencia de lo que ocurre en Active Accessibility, no se basa en el enrutamiento de eventos de Windows (que está estrechamente relacionado con los identificadores de ventana) y no requiere la aplicación cliente para configurar enlaces. Las suscripciones a eventos se pueden ajustar no solo para eventos concretos, sino también para partes específicas del árbol. Los proveedores también pueden ajustar su generación de eventos mediante el mantenimiento del seguimiento de qué eventos se están escuchando.  
  
 También resulta más sencillo para los clientes recuperar los elementos que generan eventos, ya que estos se pasan directamente a la devolución de llamada de evento. Las propiedades del elemento se recuperan previamente de manera automática si había una solicitud de caché activa cuando el cliente se suscribió al evento.  
  
 En la tabla siguiente se muestra la correspondencia entre WinEvents y eventos de Active Accessibility [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
|WinEvent|Identificador de evento[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|--------------|--------------------------------------------------------------------------------------------|  
|EVENT_OBJECT_ACCELERATORCHANGE|Cambio de propiedad<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|  
|EVENT_OBJECT_CONTENTSCROLLED|Cambio de propiedad o  en las barras de desplazamiento asociadas|  
|EVENT_OBJECT_CREATE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_DEFACTIONCHANGE|No equivalente|  
|EVENT_OBJECT_DESCRIPTIONCHANGE|Ningún equivalente exacto; quizás cambio de propiedad <xref:System.Windows.Automation.AutomationElement.HelpTextProperty> o <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>|  
|EVENT_OBJECT_DESTROY|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_FOCUS|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT_OBJECT_HELPCHANGE|Cambio de<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>|  
|EVENT_OBJECT_HIDE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_LOCATIONCHANGE|Cambio de propiedad<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|  
|EVENT_OBJECT_NAMECHANGE|Cambio de propiedad<xref:System.Windows.Automation.AutomationElement.NameProperty>|  
|EVENT_OBJECT_PARENTCHANGE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_REORDER|No se utiliza de forma coherente en Active Accessibility. No se define ningún evento correspondiente directamente en [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].|  
|EVENT_OBJECT_SELECTION|<xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>|  
|EVENT_OBJECT_SELECTIONADD|<xref:System.Windows.Automation.SelectionItemPattern.ElementAddedToSelectionEvent>|  
|EVENT_OBJECT_SELECTIONREMOVE|<xref:System.Windows.Automation.SelectionItemPattern.ElementRemovedFromSelectionEvent>|  
|EVENT_OBJECT_SELECTIONWITHIN|No equivalente|  
|EVENT_OBJECT_SHOW|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_STATECHANGE|Diversos eventos de cambio de propiedades|  
|EVENT_OBJECT_VALUECHANGE|Se han cambiado<xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=nameWithType> y <xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=nameWithType>|  
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
|EVENT_SYSTEM_MINIMIZEEND|Cambio de propiedad<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty>|  
|EVENT_SYSTEM_MINIMIZESTART|Cambio de propiedad<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty>|  
|EVENT_SYSTEM_MOVESIZEEND|Cambio de propiedad<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|  
|EVENT_SYSTEM_MOVESIZESTART|Cambio de propiedad<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|  
|EVENT_SYSTEM_SCROLLINGEND|Cambio de propiedad o |  
|EVENT_SYSTEM_SCROLLINGSTART|Cambio de propiedad o |  
|EVENT_SYSTEM_SOUND|No equivalente|  
|EVENT_SYSTEM_SWITCHEND|Ningún equivalente, pero un evento <xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent> señala que una nueva aplicación ha recibido el enfoque|  
|EVENT_SYSTEM_SWITCHSTART|No equivalente|  
|No equivalente|Cambio de propiedad<xref:System.Windows.Automation.MultipleViewPattern.CurrentViewProperty>|  
|No equivalente|Cambio de propiedad<xref:System.Windows.Automation.ScrollPattern.HorizontallyScrollableProperty>|  
|No equivalente|Cambio de propiedad<xref:System.Windows.Automation.ScrollPattern.VerticallyScrollableProperty>|  
|No equivalente|Cambio de propiedad<xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty>|  
|No equivalente|Cambio de propiedad<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty>|  
|No equivalente|Cambio de propiedad<xref:System.Windows.Automation.ScrollPattern.HorizontalViewSizeProperty>|  
|No equivalente|Cambio de propiedad<xref:System.Windows.Automation.ScrollPattern.VerticalViewSizeProperty>|  
|No equivalente|Cambio de propiedad<xref:System.Windows.Automation.TogglePattern.ToggleStateProperty>|  
|No equivalente|Cambio de propiedad<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty>|  
|No equivalente|Evento<xref:System.Windows.Automation.AutomationElement.AsyncContentLoadedEvent>|  
|No equivalente|<xref:System.Windows.Automation.AutomationElement.ToolTipOpenedEvent>|  
  
<a name="Security_compare"></a>
## <a name="security"></a>Seguridad  
 Algunos escenarios de personalización de `IAccessible` requieren el ajuste de `IAccessible` de base y la llamada a través de él. Esto tiene implicaciones de seguridad, puesto que un componente de confianza parcial no debería ser un intermediario en una ruta de acceso a código.  
  
 El modelo [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elimina la necesidad de que los proveedores realicen llamadas a otro código de proveedor. El servicio principal de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] realiza toda la agregación necesaria.  
  
## <a name="see-also"></a>Consulte también

- [Fundamentos de UI Automation](index.md)
