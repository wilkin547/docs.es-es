---
title: Implementación del proveedor de UI Automation en el servidor
ms.date: 03/30/2017
helpviewer_keywords:
- server-side UI Automation provider implementation
- UI Automation, server-side provider implementation
- provider implementation, UI Automation
ms.assetid: 6acc6d08-bd67-4e2e-915c-9c1d34eb86fe
ms.openlocfilehash: 8a52d84f7152b9cb431ad0aa97c88b143463be2d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789622"
---
# <a name="server-side-ui-automation-provider-implementation"></a>Implementación del proveedor de UI Automation en el servidor

> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).

En esta sección se describe cómo implementar un proveedor de UI Automation del lado servidor para un control personalizado.

La implementación de elementos Windows Presentation Foundation (WPF) y elementos que no son de WPF (como los diseñados para Windows Forms) es fundamentalmente diferente. Los elementos de WPF proporcionan compatibilidad con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] a través de una clase derivada de <xref:System.Windows.Automation.Peers.AutomationPeer>. Los elementos que no son de WPF proporcionan compatibilidad a través de implementaciones de interfaces de proveedor.

<a name="Security_Considerations"></a>

## <a name="security-considerations"></a>Consideraciones de seguridad

Los proveedores deben escribirse para funcionar en un entorno de confianza parcial. Dado que UIAutomationClient.dll no está configurado para ejecutarse con confianza parcial, el código del proveedor no debe hacer referencia a ese ensamblado. En caso contrario, el código podría ejecutarse en un entorno de plena confianza, pero se producirá un error en un entorno de confianza parcial.

De forma específica, no use los campos de las clases de UIAutomationClient.dll, como los de <xref:System.Windows.Automation.AutomationElement>. En su lugar, use los campos equivalentes de las clases de UIAutomationTypes.dll, como <xref:System.Windows.Automation.AutomationElementIdentifiers>.

<a name="Provider_Implementation_by_WPF_Elements"></a>

## <a name="provider-implementation-by-windows-presentation-foundation-elements"></a>Implementación del proveedor con los elementos de Windows Presentation Foundation

Para obtener más información sobre este tema, consulte [Automatización de la interfaz de usuario de un control personalizado de WPF](../wpf/controls/ui-automation-of-a-wpf-custom-control.md).

<a name="Provider_Implementation_by_non_WPF_Elements"></a>

## <a name="provider-implementation-by-non-wpf-elements"></a>Implementación del proveedor con elementos que no son de WPF

Los controles personalizados que no forman parte del marco de WPF, pero que se escriben en código administrado (lo que suele ser Windows Forms controles), proporcionan compatibilidad con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] mediante la implementación de interfaces. Cada elemento debe implementar al menos una de las interfaces enumeradas en la primera tabla de la sección siguiente. Además, si el elemento es compatible con uno o varios patrones de control, debe implementar la interfaz adecuada para cada uno de ellos.

El proveedor de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] debe hacer referencia a los ensamblados siguientes:

- UIAutomationProviders.dll

- UIAutomationTypes.dll

- WindowsBase.dll

<a name="Provider_Interfaces"></a>

### <a name="provider-interfaces"></a>Interfaces de proveedor

Cada proveedor de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] debe implementar una de las interfaces siguientes:

|Interfaz|Descripción|
|---------------|-----------------|
|<xref:System.Windows.Automation.Provider.IRawElementProviderSimple>|Proporciona funcionalidad para un control simple hospedado en una ventana. Es compatible con las propiedades y los patrones de control.|
|<xref:System.Windows.Automation.Provider.IRawElementProviderFragment>|Se hereda de <xref:System.Windows.Automation.Provider.IRawElementProviderSimple>. Agrega una funcionalidad para un elemento de un control complejo, incluida la navegación por el fragmento, el establecimiento del foco y la devolución del rectángulo delimitador del elemento.|
|<xref:System.Windows.Automation.Provider.IRawElementProviderFragmentRoot>|Se hereda de <xref:System.Windows.Automation.Provider.IRawElementProviderFragment>. Agrega funcionalidad para el elemento raíz de un control complejo, incluida la ubicación de un elemento secundario en las coordenadas especificadas y el establecimiento del estado del foco global del control.|

Las interfaces siguientes incrementan la funcionalidad, pero no se requiere su implementación.

|Interfaz|Descripción|
|---------------|-----------------|
|<xref:System.Windows.Automation.Provider.IRawElementProviderAdviseEvents>|Habilita al proveedor para realizar un seguimiento de las solicitudes de eventos.|
|<xref:System.Windows.Automation.Provider.IRawElementProviderHwndOverride>|Habilita la reordenación de los elementos basados en ventanas en el árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] de un fragmento.|

Todas las demás interfaces del espacio de nombres de <xref:System.Windows.Automation.Provider> son compatibles con el patrón de control.

<a name="Requirements_for_Non_WPF_Providers"></a>

### <a name="requirements-for-non-wpf-providers"></a>Requisitos para los proveedores que no son de WPF

Para comunicarse con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], el control debe implementar las áreas principales de funcionalidad siguientes:

|Funcionalidad|Implementación|
|-------------------|--------------------|
|Exponer el proveedor a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|En respuesta a un mensaje WM_GETOBJECT enviado a la ventana de control, devuelva el objeto que implementa <xref:System.Windows.Automation.Provider.IRawElementProviderSimple> (o una interfaz derivada). En el caso de los fragmentos, debe ser el proveedor de las raíces correspondientes.|
|Proporcionar valores de propiedad|Implemente <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPropertyValue%2A> para proporcionar o reemplazar valores.|
|Habilitar al cliente para interactuar con el control|Implemente interfaces compatibles con los patrones de control, como <xref:System.Windows.Automation.Provider.IInvokeProvider>. Devuelva estos proveedores de patrones en la implementación de <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A>.|
|Generar eventos|Llame a uno de los métodos estáticos de <xref:System.Windows.Automation.Provider.AutomationInteropProvider> para generar un evento que pueda escuchar un cliente.|
|Habilitar la navegación y el establecimiento del foco en un fragmento|Implemente <xref:System.Windows.Automation.Provider.IRawElementProviderFragment> para cada elemento del fragmento (no es necesario para los elementos que no forman parte de un fragmento).|
|Habilitar el establecimiento del foco y la ubicación del elemento secundario de un fragmento|Implemente <xref:System.Windows.Automation.Provider.IRawElementProviderFragmentRoot>. (no es necesario para los elementos que no son raíces de fragmento).|

<a name="Property_Values_in_Non_WPF_Providers"></a>

### <a name="property-values-in-non-wpf-providers"></a>Valores de propiedad de los proveedores que no son de WPF

En lo que respecta a los controles personalizados, los proveedores de[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] deben ofrecer compatibilidad con ciertas propiedades que pueden usar tanto el sistema de automatización como las aplicaciones cliente. Para los elementos que se hospedan en ventanas (HWND), [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] puede recuperar algunas propiedades del proveedor de ventana predeterminado, pero debe obtener otras del proveedor personalizado.

Por lo general, en lo que respecta a los controles basados en HWND, los proveedores no necesitan proporcionar las propiedades siguientes (identificadas por los valores de campo):

- <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.ProcessIdProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.ClassNameProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.HasKeyboardFocusProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.IsPasswordProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.RuntimeIdProperty>

> [!NOTE]
> El objeto <xref:System.Windows.Automation.AutomationElementIdentifiers.RuntimeIdProperty> de un elemento simple o una raíz de fragmento hospedada en una ventana se obtiene de la ventana. No obstante, los elementos del fragmento situados debajo de la raíz (por ejemplo, los elementos de lista de un cuadro de lista) deben proporcionar sus propios identificadores. Para obtener más información, vea <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.GetRuntimeId%2A>.
>
> Se debe devolver el <xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty> para los proveedores hospedados en un control de Windows Forms. En este caso, es posible que el proveedor de ventana predeterminado no consiga recuperar el valor correcto.
>
> Por lo general, el elemento <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> lo proporciona el proveedor de host. Por ejemplo, si se deriva un control personalizado de <xref:System.Windows.Forms.Control>, el nombre derivará de la propiedad `Text` del control.

Para obtener código de ejemplo, vea [Return Properties from a UI Automation Provider](return-properties-from-a-ui-automation-provider.md).

<a name="Events_in_Non_WPF_Providers"></a>

### <a name="events-in-non-wpf-providers"></a>Eventos de proveedores que no son de WPF

Los proveedores de[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] deben generar eventos para notificar a las aplicaciones cliente los cambios en el estado de la interfaz de usuario. Para generar eventos, se usan los métodos siguientes:

|Método|Descripción|
|------------|-----------------|
|<xref:System.Windows.Automation.Provider.AutomationInteropProvider.RaiseAutomationEvent%2A>|Genera varios eventos, incluidos los que desencadenan los patrones de control.|
|<xref:System.Windows.Automation.Provider.AutomationInteropProvider.RaiseAutomationPropertyChangedEvent%2A>|Genera un evento cuando ha cambiado una propiedad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].|
|<xref:System.Windows.Automation.Provider.AutomationInteropProvider.RaiseStructureChangedEvent%2A>|Genera un evento cuando la estructura del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ha cambiado. Por ejemplo, cuando se agrega o elimina un elemento.|

El propósito de un evento es notificar al cliente algo que ha sucedido en la [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], independientemente de si el propio sistema de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] desencadena o no la actividad. Por ejemplo, el evento que identifica <xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent> debe generarse siempre que se invoca el control a través de la entrada directa del usuario o cuando la aplicación cliente llama a <xref:System.Windows.Automation.InvokePattern.Invoke%2A>.

Para optimizar el rendimiento, un proveedor puede generar eventos de forma selectiva o no generarlos en absoluto si no se registra ninguna aplicación cliente para recibirlos. Para conseguir esta optimización, se usan los métodos siguientes:

|Método|Descripción|
|------------|-----------------|
|<xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A>|Esta propiedad estática especifica si alguna aplicación cliente se ha suscrito a eventos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|
|<xref:System.Windows.Automation.Provider.IRawElementProviderAdviseEvents>|La implementación del proveedor de esta interfaz en una raíz de fragmento permite recibir información cuando los clientes registran controladores de eventos o anulan su registro en los eventos del fragmento.|

<a name="Non_WPF_Provider_Navigation"></a>

### <a name="non-wpf-provider-navigation"></a>Navegación de proveedores que no son de WPF

Los proveedores de los controles simples, como los botones personalizados hospedados en ventanas (HWND), no deben resultar compatibles necesariamente con la navegación dentro del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . La navegación hacia y desde el elemento se controla con el proveedor predeterminado de la ventana host, que se especifica en la implementación de <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.HostRawElementProvider%2A>. Sin embargo, cuando se implementa un proveedor para un control personalizado complejo, sí se debe admitir la navegación entre el nodo raíz del fragmento y sus descendientes, y entre los nodos del mismo nivel.

> [!NOTE]
> Los elementos de un fragmento que no sea la raíz deben devolver una referencia `null` desde <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.HostRawElementProvider%2A>, ya que no se hospedan directamente en una ventana y ningún proveedor predeterminado admite la navegación hacia y desde ellos.

La estructura del fragmento queda determinada por la implementación de <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A>. Este método devuelve el objeto de proveedor para el elemento en cada dirección posible, desde cada fragmento. Si no hay ningún elemento en una dirección determinada, el método devuelve una referencia `null` .

La raíz de fragmento solo permite navegar hacia los elementos secundarios. Por ejemplo, un cuadro de lista devuelve el primer elemento de la lista cuando la dirección es <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild>, y el último elemento cuando la dirección es <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>. La raíz de fragmento no admite la navegación a un elemento primario o del mismo nivel. Esto se controla desde el proveedor de ventana host.

Los elementos de un fragmento que no son la raíz deben admitir la navegación hacia el elemento primario, sus elementos secundarios y los elementos del mismo nivel que estos contengan.

<a name="Non_WPF_Provider_Reparenting"></a>

### <a name="non-wpf-provider-reparenting"></a>Reorganización dinámica de relación jerárquica de proveedores que no son de WPF

Las ventanas emergentes son en realidad ventanas de nivel superior. Por ello, aparecen de forma predeterminada en el árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] como elementos secundarios del escritorio. No obstante, en muchos casos, las ventanas emergentes son, lógicamente, elementos secundarios de otros controles. Por ejemplo, la lista desplegable de un cuadro combinado es, lógicamente, un elemento secundario de dicho cuadro. De forma similar, una ventana emergente de menú es, lógicamente, un elemento secundario de un menú. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] permite reorganizar de forma dinámica la relación jerárquica de las ventanas emergentes para que parezcan elementos secundarios del control asociado.

Para reorganizar de forma dinámica la relación jerárquica de una ventana emergente:

1. Cree un proveedor para la ventana emergente. Para ello, se debe conocer por adelantado la clase de la ventana emergente.

2. Implemente todas las propiedades y los patrones con el proceso habitual para los elementos emergentes, como si se tratase de un control por derecho propio.

3. Implemente la propiedad <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.HostRawElementProvider%2A> para que devuelva el valor obtenido de <xref:System.Windows.Automation.Provider.AutomationInteropProvider.HostProviderFromHandle%2A>, donde el parámetro es el identificador de ventana de la ventana emergente.

4. Implemente <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> para la ventana emergente y su elemento primario, de modo que la navegación pueda controlarse correctamente desde el elemento primario lógico hacia los elementos secundarios lógicos, y entre los elementos secundarios del mismo nivel.

Cuando [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] encuentra la ventana emergente, reconoce que se está reemplazando la configuración predeterminada de la navegación y omite esta ventana cuando se encuentra como elemento secundario del escritorio. En su lugar, solo podrá accederse al nodo a través del fragmento.

La reorganización dinámica de relación jerárquica no es adecuada cuando un control puede hospedar una ventana de cualquier clase. Por ejemplo, un rebar puede hospedar cualquier tipo de HWND en sus bandas. Para controlar estos casos, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] permite reubicar HWND con un procedimiento alternativo, que se describe en la sección siguiente.

<a name="Non_WPF_Provider_Repositioning"></a>

### <a name="non-wpf-provider-repositioning"></a>Reordenación de proveedores que no son de WPF

Los fragmentos de[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] pueden contener dos o más elementos, contenidos todos ellos en ventanas (HWND). Dado que cada HWND tiene su propio proveedor predeterminado que lo considera como elemento secundario de otro HWND contenedor, el árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] mostrará, de forma predeterminada, los HWND del fragmento como elementos secundarios de la ventana primaria. En la mayoría de los casos este sería el comportamiento deseable, pero a veces puede llevar a confusión porque no coincide con la estructura lógica de la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].

Un buen ejemplo de esto lo constituye un control rebar. Un rebar contiene bandas, cada una de las cuales puede incluir a su vez un control basado en HWND, como una barra de herramientas, un cuadro de edición o un cuadro combinado. El proveedor de ventana predeterminado del HWND de rebar considera los HWND del control de banda como elementos secundarios, y el proveedor de rebar considera las bandas como elementos secundarios. Dado que los proveedores de HWND y rebar trabajan en tándem y combinan sus elementos secundarios, tanto las bandas como los controles basados en HWND aparecen como elementos secundarios del rebar. Sin embargo, lógicamente, solo deberían aparecer las bandas como elementos secundarios del rebar, y cada proveedor de banda debería acoplarse con el proveedor de HWND predeterminado para el control que contiene.

Para ello, el proveedor de raíz de fragmento del rebar expone un conjunto de elementos secundarios que representan a las bandas. Cada banda tiene un proveedor único que puede exponer propiedades y patrones. En su implementación de <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.HostRawElementProvider%2A>, el proveedor de banda devuelve el proveedor de ventana predeterminado para el HWND de control. Para obtenerlo, llama a <xref:System.Windows.Automation.Provider.AutomationInteropProvider.HostProviderFromHandle%2A>y pasa el identificador de ventana del control. Por último, el proveedor de raíz de fragmento del rebar implementa la interfaz de <xref:System.Windows.Automation.Provider.IRawElementProviderHwndOverride> y, en su implementación de <xref:System.Windows.Automation.Provider.IRawElementProviderHwndOverride.GetOverrideProviderForHwnd%2A> , devuelve el proveedor de banda adecuado para el control que contiene el HWND especificado.

## <a name="see-also"></a>Vea también

- [Información general sobre proveedores de la Automatización de la interfaz de usuario](ui-automation-providers-overview.md)
- [Exposición de un proveedor de Automatización de la interfaz de usuario en el servidor](expose-a-server-side-ui-automation-provider.md)
- [Devolución de propiedades de un proveedor de Automatización de la interfaz de usuario](return-properties-from-a-ui-automation-provider.md)
- [Provocación de eventos desde un proveedor de Automatización de la interfaz de usuario](raise-events-from-a-ui-automation-provider.md)
- [Habilitar la navegación en un proveedor de fragmentos de Automatización de la interfaz de usuario](enable-navigation-in-a-ui-automation-fragment-provider.md)
- [Patrones de control compatibles en un proveedor de Automatización de la interfaz de usuario](support-control-patterns-in-a-ui-automation-provider.md)
