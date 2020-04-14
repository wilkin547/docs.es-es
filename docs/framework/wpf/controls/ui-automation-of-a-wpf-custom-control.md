---
title: Automatización de la interfaz de usuario de un control personalizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], applying UI automation
- accessibility [WPF], applying to custom controls
- custom controls [WPF], improving accessibility
- UI Automation [WPF], using with custom controls
ms.assetid: 47b310fc-fbd5-4ce2-a606-22d04c6d4911
ms.openlocfilehash: 97db94215220ac2a68e0395bd63b7a874a745a48
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243250"
---
# <a name="ui-automation-of-a-wpf-custom-control"></a>Automatización de la interfaz de usuario de un control personalizado de WPF
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)] proporciona una única interfaz generalizada que los clientes de automatización pueden utilizar para examinar o utilizar las interfaces de usuario de una variedad de plataformas y entornos. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] permite al código de control de calidad (prueba) y a las aplicaciones de accesibilidad, tales como lectores de pantalla, examinar los elementos de la interfaz de usuario y simular la interacción del usuario con ellos desde otro código. Para más información acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] en todas las plataformas, consulte Accesibilidad.  
  
 En este tema se describe cómo implementar un proveedor de automatización de la interfaz de usuario del lado servidor para un control personalizado que se ejecuta en una aplicación de WPF. WPF admite [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] mediante un árbol de objetos de automatización del mismo nivel que se corresponde con el árbol de elementos de la interfaz de usuario. El código de prueba y las aplicaciones que proporcionan características de accesibilidad pueden usar objetos de automatización del mismo nivel directamente (para código en proceso) o mediante la interfaz generalizada proporcionada por [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)].  

<a name="AutomationPeerClasses"></a>
## <a name="automation-peer-classes"></a>Clases de automatización del mismo nivel  
 WPFWPF [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] WPFWPF admite a través <xref:System.Windows.Automation.Peers.AutomationPeer>de un árbol de clases del mismo nivel que derivan de . Por convención, los nombres de clase del mismo nivel empiezan por el nombre de clase del control y terminan por "AutomationPeer". Por ejemplo, <xref:System.Windows.Automation.Peers.ButtonAutomationPeer> es la <xref:System.Windows.Controls.Button> clase del mismo nivel para la clase de control. Las clases del mismo [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] nivel son aproximadamente equivalentes a los tipos de control, pero son específicas de WPFWPF elementos. El código de automatización que tiene acceso a las aplicaciones de WPF mediante la interfaz [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] no utiliza directamente elementos de automatización del mismo nivel; sin embargo, el código de automatización en el mismo espacio de proceso puede utilizar directamente elementos de automatización del mismo nivel.  
  
<a name="BuiltInAutomationPeerClasses"></a>
## <a name="built-in-automation-peer-classes"></a>Clases de automatización del mismo nivel integradas  
 Los elementos implementan una clase de automatización del mismo nivel si aceptan la actividad de la interfaz de usuario o si contienen la información necesaria para los usuarios de aplicaciones de lector de pantalla. No todos los elementos visuales de WPF tienen elementos de automatización del mismo nivel. Ejemplos de clases que <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.TextBox>implementan <xref:System.Windows.Controls.Label>pares de automatización son , , y . Ejemplos de clases que no implementan pares <xref:System.Windows.Controls.Decorator>de <xref:System.Windows.Controls.Border>automatización son <xref:System.Windows.Controls.Panel>clases <xref:System.Windows.Controls.Grid> que <xref:System.Windows.Controls.Canvas>derivan de , como , y clases basadas en , como y .  
  
 La <xref:System.Windows.Controls.Control> clase base no tiene una clase del mismo nivel correspondiente. Si necesita que una clase del mismo nivel <xref:System.Windows.Controls.Control>corresponda a un control personalizado <xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>que deriva de , debe derivar la clase del mismo nivel personalizada de .  
  
<a name="SecurityConsiderations"></a>
## <a name="security-considerations-for-derived-peers"></a>Consideraciones de seguridad para elementos del mismo nivel derivados  
 Los elementos de automatización del mismo nivel deben ejecutarse en un entorno de confianza parcial. El código del ensamblado UIAutomationClient no está configurado para ejecutarse en un entorno de confianza parcial y el código de automatización del mismo nivel no debe hacer referencia a dicho ensamblado. En su lugar, debe usar las clases del ensamblado UIAutomationTypes. Por ejemplo, debe <xref:System.Windows.Automation.AutomationElementIdentifiers> usar la clase del ensamblado UIAutomationTypes, que corresponde a la <xref:System.Windows.Automation.AutomationElement> clase del ensamblado UIAutomationClient. Es seguro hacer referencia al ensamblado UIAutomationTypes en el código de automatización del mismo nivel.  
  
<a name="PeerNavigation"></a>
## <a name="peer-navigation"></a>Navegación entre elementos del mismo nivel  
 Después de localizar un elemento del mismo nivel de automatización, el código en proceso puede navegar por el árbol del mismo nivel llamando a los métodos <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A> y <xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A> al objeto. La implementación del mismo nivel del método admite <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A> la navegación entre elementos WPF dentro de un control. El sistema de automatización de la interfaz de usuario llama a este método para crear un árbol de subelementos incluidos dentro de un control; por ejemplo, los elementos de lista de un cuadro de lista. El <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=nameWithType> método predeterminado recorre el árbol visual de los elementos para crear el árbol de pares de automatización. Los controles personalizados invalidan este método para exponer los elementos secundarios a los clientes de automatización, y devuelven aquellos elementos de automatización del mismo nivel que transmiten información o permiten la interacción del usuario.  
  
<a name="Customizations"></a>
## <a name="customizations-in-a-derived-peer"></a>Personalizaciones en un elemento del mismo nivel derivado  
 Todas las clases <xref:System.Windows.ContentElement> que derivan <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> <xref:System.Windows.UIElement> y contienen el método virtual protegido. WPFWPF <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> llama para obtener el objeto del mismo nivel de automatización para cada control. El código de automatización puede utilizar el elemento del mismo nivel para obtener información sobre las características y funciones de un control, y simular el uso interactivo. Un control personalizado que <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> admite la automatización debe invalidar <xref:System.Windows.Automation.Peers.AutomationPeer>y devolver una instancia de una clase que deriva de . Por ejemplo, si un control <xref:System.Windows.Controls.Primitives.ButtonBase> personalizado deriva de la <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> clase, <xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>el objeto devuelto por debe derivar de .  
  
 Al implementar un control personalizado, se deben invalidar los métodos "Core" de la clase base de automatización del mismo nivel, que describen el comportamiento único y específico del control personalizado.  
  
### <a name="override-oncreateautomationpeer"></a>Invalidar OnCreateAutomationPeer  
 Invalide <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> el método para el control personalizado para que devuelva el <xref:System.Windows.Automation.Peers.AutomationPeer>objeto de proveedor, que debe derivar directa o indirectamente de .  
  
### <a name="override-getpattern"></a>Invalidar GetPattern  
 Los elementos de automatización del mismo nivel simplifican algunos aspectos de la implementación de proveedores de [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] del lado servidor; sin embargo, los elementos de automatización del mismo nivel de un control personalizado deben controlar las interfaces de patrón. Al igual que los proveedores que no son WPFWPF, <xref:System.Windows.Automation.Provider?displayProperty=nameWithType> los pares <xref:System.Windows.Automation.Provider.IInvokeProvider>admiten patrones de control proporcionando implementaciones de interfaces en el espacio de nombres, como . Las interfaces de patrón de control pueden implementarlas el propio elemento del mismo nivel u otro objeto. La implementación del <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> mismo nivel devuelve el objeto que admite el patrón especificado. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]código llama <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> al método <xref:System.Windows.Automation.Peers.PatternInterface> y especifica un valor de enumeración. La invalidación de <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> debe devolver el objeto que implementa el patrón especificado. Si el control no tiene una implementación personalizada de un patrón, puede llamar a la implementación del tipo base para <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> recuperar su implementación o null si el patrón no se admite para este tipo de control. Por ejemplo, un control NumericUpDown personalizado se puede establecer [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] en un <xref:System.Windows.Automation.Provider.IRangeValueProvider> valor dentro de un intervalo, por lo que su elemento del mismo nivel implementaría la interfaz. En el ejemplo siguiente se <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> muestra cómo se invalida el método del mismo nivel para responder a un <xref:System.Windows.Automation.Peers.PatternInterface.RangeValue?displayProperty=nameWithType> valor.  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 Un <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> método también puede especificar un subelemento como proveedor de patrones. El código siguiente <xref:System.Windows.Controls.ItemsControl> muestra cómo transfiere el control <xref:System.Windows.Controls.ScrollViewer> del patrón de desplazamiento al mismo nivel de su control interno.  
  
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
  
 Para especificar un subelemento para el control de patrones, este código <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A> obtiene el <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> objeto de subelemento, crea un elemento del mismo nivel mediante el método, establece la propiedad del nuevo elemento del mismo nivel en el mismo nivel actual y devuelve el nuevo elemento del mismo nivel. Establecer <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> en un subelemento impide que el subelemento aparezca en el árbol del mismo nivel de automatización <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>y designa todos los eventos generados por el subelemento como originarios del control especificado en . El <xref:System.Windows.Controls.ScrollViewer> control no aparece en el árbol de automatización y los <xref:System.Windows.Controls.ItemsControl> eventos de desplazamiento que genera parecen originarse en el objeto.  
  
### <a name="override-core-methods"></a>Invalidar métodos "Core"  
 Para obtener información sobre el control, el código de automatización llama a métodos públicos de la clase del mismo nivel. Para proporcionar información sobre el control, invalide los métodos cuyo nombre termina con "Core" en caso de que la implementación del control sea diferente de la que proporciona la clase base de automatización del mismo nivel. Como mínimo, el control <xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A> debe <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> implementar los métodos y, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 La implementación de <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> describe el <xref:System.Windows.Automation.ControlType> control devolviendo un valor. Aunque puede <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType>devolver , debe devolver uno de los tipos de control más específicos si describe con precisión el control. Un valor <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType> devuelto requiere trabajo adicional para [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]que [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] el proveedor implemente y los productos cliente no pueden anticipar la estructura de control, la interacción del teclado y los posibles patrones de control.  
  
 Implemente <xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A> los <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> métodos y para indicar si el control contiene contenido de datos o cumple un rol interactivo en la interfaz de usuario (o ambos). De forma predeterminada, ambos métodos devuelven `true`. Esta configuración aumenta la facilidad de uso de herramientas de automatización, como lectores de pantalla, que pueden utilizar estos métodos para filtrar el árbol de automatización. Si <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> el método transfiere el control de patrones a <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> un subelemento del mismo nivel, el método del mismo nivel del subelemento puede devolver false para ocultar el par de subelementos del árbol de automatización. Por ejemplo, el <xref:System.Windows.Controls.ListBox> desplazamiento en un <xref:System.Windows.Controls.ScrollViewer>se controla <xref:System.Windows.Automation.Peers.PatternInterface.Scroll?displayProperty=nameWithType> mediante un <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> , y <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> el elemento <xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>del mismo nivel de automatización para se devuelve mediante el método del que está asociado con el archivo . Por lo <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> tanto, <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> `false`el método <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> de los retornos , para que no aparezca en el árbol de automatización.  
  
 El elemento de automatización del mismo nivel debe proporcionar los valores predeterminados adecuados para el control. Tenga en cuenta que XAML que hace referencia al <xref:System.Windows.Automation.AutomationProperties> control puede invalidar las implementaciones del mismo nivel de los métodos principales mediante la inclusión de atributos. Por ejemplo, el código XAML siguiente crea un botón que tiene dos propiedades personalizadas [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)].  
  
```xaml  
<Button AutomationProperties.Name="Special"
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>Implementar proveedores de patrón  
 Las interfaces implementadas por un proveedor personalizado se declaran explícitamente si el elemento propietario deriva directamente de <xref:System.Windows.Controls.Control>. Por ejemplo, el código siguiente declara <xref:System.Windows.Controls.Control> un par para un que implementa un valor de intervalo.  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 Si el control propietario deriva de un tipo <xref:System.Windows.Controls.Primitives.RangeBase>específico de control como , el elemento del mismo nivel se puede derivar de una clase del mismo nivel derivada equivalente. En este caso, el <xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer>par derivaría de , <xref:System.Windows.Automation.Provider.IRangeValueProvider>que proporciona una implementación base de . El código siguiente muestra la declaración de un elemento del mismo nivel como este.  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
Para obtener una implementación de ejemplo, vea el código fuente de [C](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp) o [Visual Basic](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic) que implementa y consume un NumericUpDown control personalizado.  
  
### <a name="raise-events"></a>Generar eventos  
 Los clientes de automatización pueden suscribirse a eventos de automatización. Los controles personalizados deben notificar <xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A> los cambios en el estado de control mediante una llamada al método. De forma similar, cuando cambia <xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A> un valor de propiedad, llame al método. El código siguiente muestra cómo obtener el objeto del mismo nivel desde el código del control, y cómo llamar a un método para generar un evento. Como optimización, el código determina si hay agentes de escucha para este tipo de evento. Generar el evento únicamente cuando hay agentes de escucha evita una sobrecarga innecesaria y ayuda a que el control siga respondiendo.  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre UI Automation](../../ui-automation/ui-automation-overview.md)
- [Implementación del proveedor de UI Automation en el servidor](../../ui-automation/server-side-ui-automation-provider-implementation.md)
- [Control personalizado NumericUpDown (C- ) en GitHub](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp)  
- [Control personalizado NumericUpDown (Visual Basic) en GitHub](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic)
