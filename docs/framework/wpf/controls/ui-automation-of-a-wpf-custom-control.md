---
title: "Automatización de la interfaz de usuario de un control personalizado de WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], applying UI automation
- accessibility [WPF], applying to custom controls
- custom controls [WPF], improving accessibility
- UI Automation [WPF], using with custom controls
ms.assetid: 47b310fc-fbd5-4ce2-a606-22d04c6d4911
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d10c11cfcacb435438695b0e76ee8982ba9ef24a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ui-automation-of-a-wpf-custom-control"></a>Automatización de la interfaz de usuario de un control personalizado de WPF
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)] proporciona una única interfaz generalizada que los clientes de automatización pueden utilizar para examinar o utilizar las interfaces de usuario de una variedad de plataformas y entornos. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] permite al código de control de calidad (prueba) y a las aplicaciones de accesibilidad, tales como lectores de pantalla, examinar los elementos de la interfaz de usuario y simular la interacción del usuario con ellos desde otro código. Para más información acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] en todas las plataformas, consulte Accesibilidad.  
  
 En este tema se describe cómo implementar un proveedor de automatización de la interfaz de usuario del lado servidor para un control personalizado que se ejecuta en una aplicación de WPF. WPF admite [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] mediante un árbol de objetos de automatización del mismo nivel que se corresponde con el árbol de elementos de la interfaz de usuario. El código de prueba y las aplicaciones que proporcionan características de accesibilidad pueden usar objetos de automatización del mismo nivel directamente (para código en proceso) o mediante la interfaz generalizada proporcionada por [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)].  
  
 
  
<a name="AutomationPeerClasses"></a>   
## <a name="automation-peer-classes"></a>Clases de automatización del mismo nivel  
 Compatibilidad con los controles de WPF [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] a través de un árbol de clases del mismo nivel que derivan de <xref:System.Windows.Automation.Peers.AutomationPeer>. Por convención, los nombres de clase del mismo nivel empiezan por el nombre de clase del control y terminan por "AutomationPeer". Por ejemplo, <xref:System.Windows.Automation.Peers.ButtonAutomationPeer> es la clase del mismo nivel para el <xref:System.Windows.Controls.Button> clase del control. Las clases del mismo nivel equivalen a los tipos de control de [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)], pero son específicas de los elementos de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. El código de automatización que tiene acceso a las aplicaciones de WPF mediante la interfaz [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] no utiliza directamente elementos de automatización del mismo nivel; sin embargo, el código de automatización en el mismo espacio de proceso puede utilizar directamente elementos de automatización del mismo nivel.  
  
<a name="BuiltInAutomationPeerClasses"></a>   
## <a name="built-in-automation-peer-classes"></a>Clases de automatización del mismo nivel integradas  
 Los elementos implementan una clase de automatización del mismo nivel si aceptan la actividad de la interfaz de usuario o si contienen la información necesaria para los usuarios de aplicaciones de lector de pantalla. No todos los elementos visuales de WPF tienen elementos de automatización del mismo nivel. Algunos ejemplos de clases que implementan el mismo nivel de automatización son <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.TextBox>, y <xref:System.Windows.Controls.Label>. Ejemplos de clases que implementan el mismo nivel de automatización son clases que derivan de <xref:System.Windows.Controls.Decorator>, como <xref:System.Windows.Controls.Border>y las clases basadas en <xref:System.Windows.Controls.Panel>, como <xref:System.Windows.Controls.Grid> y <xref:System.Windows.Controls.Canvas>.  
  
 La base de <xref:System.Windows.Controls.Control> clase no tiene una clase del mismo nivel correspondiente. Si necesita una clase del mismo nivel que corresponda a un control personalizado que deriva de <xref:System.Windows.Controls.Control>, debe derivar la clase del mismo nivel personalizado de <xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>.  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations-for-derived-peers"></a>Consideraciones de seguridad para elementos del mismo nivel derivados  
 Los elementos de automatización del mismo nivel deben ejecutarse en un entorno de confianza parcial. El código del ensamblado UIAutomationClient no está configurado para ejecutarse en un entorno de confianza parcial y el código de automatización del mismo nivel no debe hacer referencia a dicho ensamblado. En su lugar, debe usar las clases del ensamblado UIAutomationTypes. Por ejemplo, debe utilizar el <xref:System.Windows.Automation.AutomationElementIdentifiers> clase a partir del ensamblado UIAutomationTypes, que corresponde a la <xref:System.Windows.Automation.AutomationElement> clase del ensamblado UIAutomationClient. Es seguro hacer referencia al ensamblado UIAutomationTypes en el código de automatización del mismo nivel.  
  
<a name="PeerNavigation"></a>   
## <a name="peer-navigation"></a>Navegación entre elementos del mismo nivel  
 Después de encontrar una automatización del mismo nivel, código en proceso puede navegar por el árbol del mismo nivel mediante una llamada del objeto <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A> y <xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A> métodos. Navegación entre [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] elementos dentro de un control es compatible con la implementación del mismo nivel de la <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A> método. El sistema de automatización de la interfaz de usuario llama a este método para crear un árbol de subelementos incluidos dentro de un control; por ejemplo, los elementos de lista de un cuadro de lista. El valor predeterminado <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=nameWithType> método recorre el árbol visual de elementos para generar el árbol de elementos de automatización del mismo nivel. Los controles personalizados invalidan este método para exponer los elementos secundarios a los clientes de automatización, y devuelven aquellos elementos de automatización del mismo nivel que transmiten información o permiten la interacción del usuario.  
  
<a name="Customizations"></a>   
## <a name="customizations-in-a-derived-peer"></a>Personalizaciones en un elemento del mismo nivel derivado  
 Todas las clases que derivan de <xref:System.Windows.UIElement> y <xref:System.Windows.ContentElement> contienen el método virtual protegido <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>. Llamadas WPF <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> para obtener el objeto de automatización del mismo nivel para cada control. El código de automatización puede utilizar el elemento del mismo nivel para obtener información sobre las características y funciones de un control, y simular el uso interactivo. Un control personalizado que admite la automatización debe invalidar <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> y devolver una instancia de una clase que deriva de <xref:System.Windows.Automation.Peers.AutomationPeer>. Por ejemplo, si un control personalizado se deriva de la <xref:System.Windows.Controls.Primitives.ButtonBase> clase y, a continuación, el objeto devuelto por <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> debe derivarse de <xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>.  
  
 Al implementar un control personalizado, se deben invalidar los métodos "Core" de la clase base de automatización del mismo nivel, que describen el comportamiento único y específico del control personalizado.  
  
### <a name="override-oncreateautomationpeer"></a>Invalidar OnCreateAutomationPeer  
 Invalidar el <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> método para el control personalizado para que devuelva el objeto de proveedor, debe derivar directa o indirectamente de <xref:System.Windows.Automation.Peers.AutomationPeer>.  
  
### <a name="override-getpattern"></a>Invalidar GetPattern  
 Los elementos de automatización del mismo nivel simplifican algunos aspectos de la implementación de proveedores de [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] del lado servidor; sin embargo, los elementos de automatización del mismo nivel de un control personalizado deben controlar las interfaces de patrón. Al igual que los proveedores que no son de WPF, elementos del mismo nivel admiten patrones de control proporcionando las implementaciones de interfaces de la <xref:System.Windows.Automation.Provider?displayProperty=nameWithType> espacio de nombres, como <xref:System.Windows.Automation.Provider.IInvokeProvider>. Las interfaces de patrón de control pueden implementarlas el propio elemento del mismo nivel u otro objeto. Implementación del mismo nivel de <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> devuelve el objeto que admite el patrón especificado. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]el código llama a la <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> método y especifica un <xref:System.Windows.Automation.Peers.PatternInterface> valor de enumeración. El reemplazo del <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> debe devolver el objeto que implementa el patrón especificado. Si el control no tiene una implementación personalizada de un patrón, puede llamar a implementación del tipo base <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> para recuperar su implementación o null si no se admite el patrón para este tipo de control. Por ejemplo, un control NumericUpDown personalizado puede establecerse en un valor dentro de un intervalo, por lo que su [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] punto implementaría el <xref:System.Windows.Automation.Provider.IRangeValueProvider> interfaz. El siguiente ejemplo se muestra cómo el par <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> método se invalida para responder a un <xref:System.Windows.Automation.Peers.PatternInterface.RangeValue?displayProperty=nameWithType> valor.  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 Un <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> método también puede especificar un subelemento como proveedor del patrón. El siguiente código muestra cómo <xref:System.Windows.Controls.ItemsControl> transfiere el control del patrón para el mismo nivel de su interno de desplazamiento <xref:System.Windows.Controls.ScrollViewer> control.  
  
```csharp  
public override object GetPattern(PatternInterface patternInterface)  
{  
    if (patternInterface == PatternInterface.Scroll)  
    {  
        ItemsControl owner = (ItemsControl) base.Owner;  
  
        // ScrollHost is internal to the ItemsControl class  
        if (owner.ScrollHost != null)  
        {  
            AutomationPeer peer = UIElementAutomationPeer.CreatePeerForElement(owner.ScrollHost);  
            if ((peer != null) && (peer is IScrollProvider))  
            {  
                peer.EventsSource = this;  
                return (IScrollProvider) peer;  
            }  
        }  
    }  
    return base.GetPattern(patternInterface);  
}  
```  
  
```vb  
Public Class Class1  
    Public Overrides Function GetPattern(ByVal patternInterface__1 As PatternInterface) As Object  
        If patternInterface1 = PatternInterface.Scroll Then  
            Dim owner As ItemsControl = DirectCast(MyBase.Owner, ItemsControl)  
  
            ' ScrollHost is internal to the ItemsControl class  
            If owner.ScrollHost IsNot Nothing Then  
                Dim peer As AutomationPeer = UIElementAutomationPeer.CreatePeerForElement(owner.ScrollHost)  
                If (peer IsNot Nothing) AndAlso (TypeOf peer Is IScrollProvider) Then  
                    peer.EventsSource = Me  
                    Return DirectCast(peer, IScrollProvider)  
                End If  
            End If  
        End If  
        Return MyBase.GetPattern(patternInterface1)  
    End Function  
End Class  
```  
  
 Para especificar un subelemento para el control del patrón, este código obtiene el objeto del subelemento, crea un elemento del mismo nivel mediante el <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A> método, Establece el <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> propiedad del mismo nivel nuevo para el par actual y devuelve la nueva del mismo nivel. Establecer <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> en un subelemento impide que el subelemento que aparecen en el árbol de automatización del mismo nivel y todos los eventos provocados por el subelemento de designa como que se origina en el control especificado en <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>. El <xref:System.Windows.Controls.ScrollViewer> control no aparece en el árbol de automatización y los eventos de desplazamiento que genera parezcan proceder de la <xref:System.Windows.Controls.ItemsControl> objeto.  
  
### <a name="override-core-methods"></a>Invalidar métodos "Core"  
 Para obtener información sobre el control, el código de automatización llama a métodos públicos de la clase del mismo nivel. Para proporcionar información sobre el control, invalide los métodos cuyo nombre termina con "Core" en caso de que la implementación del control sea diferente de la que proporciona la clase base de automatización del mismo nivel. Como mínimo, el control debe implementar la <xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A> y <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> métodos, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 La implementación de <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> describe el control devolviendo un <xref:System.Windows.Automation.ControlType> valor. Aunque puede devolver <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType>, debe devolver uno de los tipos de control más específicos si describe con precisión el control. Un valor devuelto de <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType> requiere trabajo adicional para el proveedor implemente [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)], y [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] productos de cliente son no se puede prever la estructura de control, interacción con el teclado y patrones de control posibles.  
  
 Implemente el <xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A> y <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> métodos para indicar si el control contiene datos o desempeña una función interactiva en la interfaz de usuario (o ambos). De forma predeterminada, ambos métodos devuelven `true`. Esta configuración aumenta la facilidad de uso de herramientas de automatización, como lectores de pantalla, que pueden utilizar estos métodos para filtrar el árbol de automatización. Si su <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> control a un subelemento del mismo nivel, el subelemento del mismo nivel del método transferencias patrón <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> método puede devolver false para ocultar el subelemento del mismo nivel del árbol de automatización. Desplazarse por ejemplo, en un <xref:System.Windows.Controls.ListBox> se controla mediante un <xref:System.Windows.Controls.ScrollViewer>y la automatización del mismo nivel para <xref:System.Windows.Automation.Peers.PatternInterface.Scroll?displayProperty=nameWithType> devuelto por la <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> método de la <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> que está asociada la <xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>. Por lo tanto, la <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> método de la <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> devuelve `false`, de modo que el <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> no aparece en el árbol de automatización.  
  
 El elemento de automatización del mismo nivel debe proporcionar los valores predeterminados adecuados para el control. Tenga en cuenta que el XAML que hace referencia a su control puede invalidar sus implementaciones del mismo nivel de métodos básicos mediante la inclusión de <xref:System.Windows.Automation.AutomationProperties> atributos. Por ejemplo, el código XAML siguiente crea un botón que tiene dos propiedades personalizadas [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)].  
  
```xaml  
<Button AutomationProperties.Name="Special"   
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>Implementar proveedores de patrón  
 Las interfaces implementadas por un proveedor personalizado se declaran explícitamente si el elemento propietario se deriva directamente de <xref:System.Windows.Controls.Control>. Por ejemplo, el código siguiente declara un elemento del mismo nivel para un <xref:System.Windows.Controls.Control> que implementa un valor de intervalo.  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 Si el control propietario se deriva de un tipo específico de control como <xref:System.Windows.Controls.Primitives.RangeBase>, igual que se puede derivar de una clase del mismo nivel derivada equivalente. En este caso, el punto derivaría de <xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer>, lo que proporciona una implementación base de <xref:System.Windows.Automation.Provider.IRangeValueProvider>. El código siguiente muestra la declaración de un elemento del mismo nivel como este.  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
 Para ver una implementación de ejemplo, consulte [NumericUpDown Custom Control with Theme and UI Automation Support Sample](http://go.microsoft.com/fwlink/?LinkID=160025) (Ejemplo de un control personalizado NumericUpDown y compatibilidad para Automatización de la interfaz de usuario).  
  
### <a name="raise-events"></a>Generar eventos  
 Los clientes de automatización pueden suscribirse a eventos de automatización. Controles personalizados deben notificar los cambios para controlar el estado mediante una llamada a la <xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A> método. De forma similar, cuando cambia un valor de propiedad, llame a la <xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A> método. El código siguiente muestra cómo obtener el objeto del mismo nivel desde el código del control, y cómo llamar a un método para generar un evento. Como optimización, el código determina si hay agentes de escucha para este tipo de evento. Generar el evento únicamente cuando hay agentes de escucha evita una sobrecarga innecesaria y ayuda a que el control siga respondiendo.  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre la automatización de interfaz de usuario](../../../../docs/framework/ui-automation/ui-automation-overview.md)  
 [Control personalizado NumericUpDown con tema y un ejemplo de compatibilidad UI Automation](http://go.microsoft.com/fwlink/?LinkID=160025)  
 [Implementación del proveedor de automatización de la interfaz de usuario en el servidor](../../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
