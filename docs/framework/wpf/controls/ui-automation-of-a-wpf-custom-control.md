---
title: "Automatizaci&#243;n de la interfaz de usuario de un control personalizado de WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "controles personalizados [WPF], aplicación de UI automation"
  - "aplicar a controles personalizados de accesibilidad [WPF]"
  - "controles personalizados [WPF], mejorar la accesibilidad"
  - "Automatización de interfaz de usuario [WPF] con controles personalizados"
ms.assetid: 47b310fc-fbd5-4ce2-a606-22d04c6d4911
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 34
---
# Automatizaci&#243;n de la interfaz de usuario de un control personalizado de WPF
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)]Proporciona una única interfaz generalizada que los clientes pueden utilizar para examinar o utilizar las interfaces de usuario de una variedad de plataformas y marcos de automatización. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]permite que el código de control de calidad (prueba) y aplicaciones de accesibilidad como lectores de pantalla para examinar los elementos de la interfaz de usuario y simular la interacción del usuario con ellos desde otro código. Para obtener información acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] en todas las plataformas, vea accesibilidad.  
  
 En este tema se describe cómo implementar un proveedor de UI Automation en el servidor para un control personalizado que se ejecuta en una aplicación WPF. WPF admite [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] a través de un árbol de objetos de automatización del mismo nivel correspondiente al árbol de elementos de la interfaz de usuario. Probar el código y las aplicaciones que proporcionan características de accesibilidad pueden usar objetos de automatización del mismo nivel directamente (para código en proceso) o a través de la interfaz generalizada proporcionada por [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)].  
  
 
  
<a name="AutomationPeerClasses"></a>   
## <a name="automation-peer-classes"></a>Clases de automatización del mismo nivel  
 Compatibilidad con los controles de WPF [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] a través de un árbol de clases del mismo nivel que se derivan de <xref:System.Windows.Automation.Peers.AutomationPeer>. Por convención, los nombres de clase del mismo nivel empiezan por el nombre de clase del control y terminan por "AutomationPeer". Por ejemplo, <xref:System.Windows.Automation.Peers.ButtonAutomationPeer> es la clase del mismo nivel para la <xref:System.Windows.Controls.Button> clase del control. Las clases del mismo nivel equivalen a [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] tipos de control, pero son específicas de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] elementos. Código de automatización que tiene acceso a las aplicaciones de WPF a través de la [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] interfaz no utiliza directamente los pares de automatización, pero el código de automatización en el mismo espacio de proceso puede automatización.  
  
<a name="BuiltInAutomationPeerClasses"></a>   
## <a name="built-in-automation-peer-classes"></a>Clases del mismo nivel de automatización integrada  
 Los elementos implementan una clase de automatización del mismo nivel si aceptan actividad de la interfaz de usuario o si contienen información necesaria para los usuarios de aplicaciones de lector de pantalla. No todos los elementos visuales de WPF tienen equivalentes de automatización. Ejemplos de clases que implementan el mismo nivel de automatización son <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.TextBox>, y <xref:System.Windows.Controls.Label>. Ejemplos de clases que implementan el mismo nivel de automatización son clases que derivan de <xref:System.Windows.Controls.Decorator>, como <xref:System.Windows.Controls.Border>y las clases basadas en <xref:System.Windows.Controls.Panel>, como <xref:System.Windows.Controls.Grid> y <xref:System.Windows.Controls.Canvas>.  
  
 La base de <xref:System.Windows.Controls.Control> clase no tiene una clase correspondiente del mismo nivel. Si necesita una clase del mismo nivel que corresponda a un control personalizado que se deriva de <xref:System.Windows.Controls.Control>, debe derivar la clase personalizada del mismo nivel de <xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>.  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations-for-derived-peers"></a>Consideraciones de seguridad para los equipos del mismo nivel derivadas  
 Debe ejecutar el mismo nivel de automatización en un entorno de confianza parcial. Código del ensamblado UIAutomationClient no está configurado para ejecutarse en un entorno de confianza parcial y código de automatización del mismo nivel no debe hacer referencia a ese ensamblado. En su lugar, debe usar las clases del ensamblado UIAutomationTypes. Por ejemplo, debe usar el <xref:System.Windows.Automation.AutomationElementIdentifiers> clase del ensamblado UIAutomationTypes, que corresponde a la <xref:System.Windows.Automation.AutomationElement> clase del ensamblado UIAutomationClient. Es seguro hacer referencia al ensamblado UIAutomationTypes en el código de automatización del mismo nivel.  
  
<a name="PeerNavigation"></a>   
## <a name="peer-navigation"></a>Exploración del mismo nivel  
 Después de encontrar un nivel de automatización, código en proceso puede navegar por el árbol del mismo nivel mediante una llamada del objeto <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A> y <xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A> métodos. Navegación entre [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] elementos dentro de un control es compatible con la implementación del mismo nivel de la <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A> método. El sistema de automatización de la interfaz de usuario llama a este método para crear un árbol de elementos secundarios incluidos dentro de un control; Por ejemplo, elementos de lista en un cuadro de lista. El valor predeterminado <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=fullName> método recorre el árbol visual de elementos para generar el árbol de elementos de automatización del mismo nivel. Controles personalizados invalidación este método para exponer los elementos secundarios a los clientes de automatización, devolviendo a los interlocutores de automatización de los elementos que transmiten información o permiten la interacción del usuario.  
  
<a name="Customizations"></a>   
## <a name="customizations-in-a-derived-peer"></a>Personalizaciones en derivada del mismo nivel  
 Todas las clases que derivan de <xref:System.Windows.UIElement> y <xref:System.Windows.ContentElement> contienen el método virtual protegido <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>. Llamadas WPF <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> para obtener el objeto de automatización del mismo nivel para cada control. Código de automatización puede utilizar al mismo nivel para obtener información sobre las características y funciones de un control y simular el uso interactivo. Un control personalizado que admite la automatización debe invalidar <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> y devuelva una instancia de una clase que deriva de <xref:System.Windows.Automation.Peers.AutomationPeer>. Por ejemplo, si un control personalizado se deriva de la <xref:System.Windows.Controls.Primitives.ButtonBase> (clase) y, a continuación, el objeto devuelto por <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> debe derivar de <xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>.  
  
 Al implementar un control personalizado, debe invalidar los métodos "Principal" de la clase de base de automatización del mismo nivel que describen el comportamiento único y específico para el control personalizado.  
  
### <a name="override-oncreateautomationpeer"></a>Invalidar OnCreateAutomationPeer  
 Invalidar el <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> método para el control personalizado para que devuelva el objeto de proveedor, debe derivar directa o indirectamente de <xref:System.Windows.Automation.Peers.AutomationPeer>.  
  
### <a name="override-getpattern"></a>Invalidar GetPattern  
 Elementos de automatización del mismo nivel simplifican algunos aspectos de la implementación de servidor [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] proveedores pero pares de automatización del control personalizado todavía deben controlar las interfaces patrón. Como proveedores de WPF no elementos del mismo nivel admiten patrones de controles mediante implementaciones de interfaces de la <xref:System.Windows.Automation.Provider?displayProperty=fullName> espacio de nombres, como <xref:System.Windows.Automation.Provider.IInvokeProvider>. Las interfaces del patrón de control se pueden implementar por el nodo en sí mismo o por otro objeto. Implementación del mismo nivel de <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> devuelve el objeto que admite el patrón especificado. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]el código llama a la <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> (método) y especifica un <xref:System.Windows.Automation.Peers.PatternInterface> valor de enumeración. El reemplazo de <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> debe devolver el objeto que implementa el patrón especificado. Si el control no tiene una implementación personalizada de un patrón, puede llamar la implementación del tipo base <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> para recuperar su implementación o null si no se admite el patrón para este tipo de control. Por ejemplo, un control NumericUpDown personalizado puede establecerse en un valor dentro de un intervalo, por lo que su [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] punto implementaría la <xref:System.Windows.Automation.Provider.IRangeValueProvider> interfaz. El ejemplo siguiente se muestra cómo el interlocutor <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> método se invalida para responder a una <xref:System.Windows.Automation.Peers.PatternInterface?displayProperty=fullName> valor.  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 Un <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> método también puede especificar un subelemento como proveedor del patrón. El siguiente código muestra cómo <xref:System.Windows.Controls.ItemsControl> transfiere el control al par de interna del patrón de desplazamiento <xref:System.Windows.Controls.ScrollViewer> control.  
  
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
  
 Para especificar un subelemento para el control del patrón, este código obtiene el objeto del subelemento, crea un punto mediante el <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A> método, Establece la <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> propiedad del mismo nivel nuevo para el mismo nivel actual y devuelve la nueva del mismo nivel. Configuración de <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> en un subelemento impide que el subelemento aparezca en el árbol de automatización del mismo nivel y todos los eventos provocados por el subelemento de designa como originadas en el control especificado en <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>. El <xref:System.Windows.Controls.ScrollViewer> control no aparece en el árbol de automatización y eventos de desplazamiento que genera parecerán originarse en el <xref:System.Windows.Controls.ItemsControl> objeto.  
  
### <a name="override-core-methods"></a>Invalidar métodos "Principal"  
 Código de automatización obtiene información sobre el control al llamar a métodos públicos de la clase del mismo nivel. Para proporcionar información sobre el control, invalide los métodos cuyo nombre termina con "Core" cuando la implementación del control es diferente del que proporciona la clase de base de automatización del mismo nivel. Como mínimo, el control debe implementar la <xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A> y <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> métodos, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 La implementación de <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> describe el control devolviendo un <xref:System.Windows.Automation.ControlType> valor. Aunque puede devolver <xref:System.Windows.Automation.ControlType.Custom?displayProperty=fullName>, debe devolver uno de los tipos de control más específicos si describe el control con precisión. Un valor devuelto de <xref:System.Windows.Automation.ControlType.Custom?displayProperty=fullName> requiere trabajo adicional para el proveedor implemente [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)], y [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] productos de cliente son no pueden prever la estructura de control, interacción con el teclado y los patrones de control posibles.  
  
 Implemente el <xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A> y <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> métodos para indicar si el control contiene datos o desempeña una función de interacción en la interfaz de usuario (o ambas). De forma predeterminada, ambos métodos devuelven `true`. Esta configuración aumenta la facilidad de uso de herramientas de automatización como lectores de pantalla, que pueden utilizar estos métodos para filtrar el árbol de automatización. Si su <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> control a un subelemento del mismo nivel, el subelemento del mismo nivel del método transferencias patrón <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> método puede devolver false para ocultar el subelemento del mismo nivel del árbol de automatización. Por ejemplo, el desplazamiento en un <xref:System.Windows.Controls.ListBox> se controla mediante un <xref:System.Windows.Controls.ScrollViewer>y la automatización del mismo nivel para <xref:System.Windows.Automation.Peers.PatternInterface?displayProperty=fullName> devuelto por la <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> método de la <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> que está asociado el <xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>. Por lo tanto, la <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> método de la <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> devuelve `false`, de modo que la <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> no aparece en el árbol de automatización.  
  
 La automatización del mismo nivel debe proporcionar los valores predeterminados adecuados para el control. Tenga en cuenta que el XAML que hace referencia al control puede invalidar sus implementaciones del mismo nivel de métodos básicos mediante la inclusión de <xref:System.Windows.Automation.AutomationProperties> atributos. Por ejemplo, el código XAML siguiente crea un botón que tiene dos personalizado [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] propiedades.  
  
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
  
 Si el control propietario se deriva de un tipo específico de control como <xref:System.Windows.Controls.Primitives.RangeBase>, el mismo nivel se puede derivar de una clase del mismo nivel derivada equivalente. En este caso, el mismo nivel se derivaría de <xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer>, que proporciona una implementación base de <xref:System.Windows.Automation.Provider.IRangeValueProvider>. El código siguiente muestra la declaración de este tipo del mismo nivel.  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
 Para una implementación de ejemplo, vea [NumericUpDown Custom Control with tema y UI Automation Support Sample](http://go.microsoft.com/fwlink/?LinkID=160025).  
  
### <a name="raise-events"></a>Provocar eventos  
 Los clientes de automatización pueden suscribirse a eventos de automatización. Controles personalizados deben notificar cambios de estado del control mediante una llamada a la <xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A> método. De igual forma, se llama cuando cambia un valor de propiedad, el <xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A> método. El código siguiente muestra cómo obtener el objeto del mismo nivel desde el código de control y llamar a un método para generar un evento. Como optimización, el código determina si hay agentes de escucha para este tipo de evento. Cuando se genera el evento únicamente cuando hay agentes de escucha evita una sobrecarga innecesaria y ayuda a que el control siga respondiendo.  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre la automatización de interfaz de usuario](../../../../docs/framework/ui-automation/ui-automation-overview.md)   
 [Control personalizado NumericUpDown con compatibilidad con ejemplo de automatización de interfaz de usuario y el tema](http://go.microsoft.com/fwlink/?LinkID=160025)   
 [Implementación del proveedor de automatización de la interfaz de usuario de servidor](../../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)