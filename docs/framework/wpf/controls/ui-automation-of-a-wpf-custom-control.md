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
ms.openlocfilehash: a370ed2c6b1f3273eca93b4865a032e8299f1cfb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738200"
---
# <a name="ui-automation-of-a-wpf-custom-control"></a>Automatización de la interfaz de usuario de un control personalizado de WPF
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)] proporciona una única interfaz generalizada que los clientes de automatización pueden utilizar para examinar o utilizar las interfaces de usuario de una variedad de plataformas y entornos. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] permite al código de control de calidad (prueba) y a las aplicaciones de accesibilidad, tales como lectores de pantalla, examinar los elementos de la interfaz de usuario y simular la interacción del usuario con ellos desde otro código. Para más información acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] en todas las plataformas, consulte Accesibilidad.  
  
 En este tema se describe cómo implementar un proveedor de automatización de la interfaz de usuario del lado servidor para un control personalizado que se ejecuta en una aplicación de WPF. WPF admite [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] mediante un árbol de objetos de automatización del mismo nivel que se corresponde con el árbol de elementos de la interfaz de usuario. El código de prueba y las aplicaciones que proporcionan características de accesibilidad pueden usar objetos de automatización del mismo nivel directamente (para código en proceso) o mediante la interfaz generalizada proporcionada por [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)].  

<a name="AutomationPeerClasses"></a>   
## <a name="automation-peer-classes"></a>Clases de automatización del mismo nivel  
 Los controles de WPF admiten [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] a través de un árbol de clases del mismo nivel que derivan de <xref:System.Windows.Automation.Peers.AutomationPeer>. Por convención, los nombres de clase del mismo nivel empiezan por el nombre de clase del control y terminan por "AutomationPeer". Por ejemplo, <xref:System.Windows.Automation.Peers.ButtonAutomationPeer> es la clase del mismo nivel para la clase de control <xref:System.Windows.Controls.Button>. Las clases del mismo nivel son aproximadamente equivalentes a los tipos de control [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)], pero son específicos de los elementos de WPF. El código de automatización que tiene acceso a las aplicaciones de WPF mediante la interfaz [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] no utiliza directamente elementos de automatización del mismo nivel; sin embargo, el código de automatización en el mismo espacio de proceso puede utilizar directamente elementos de automatización del mismo nivel.  
  
<a name="BuiltInAutomationPeerClasses"></a>   
## <a name="built-in-automation-peer-classes"></a>Clases de automatización del mismo nivel integradas  
 Los elementos implementan una clase de automatización del mismo nivel si aceptan la actividad de la interfaz de usuario o si contienen la información necesaria para los usuarios de aplicaciones de lector de pantalla. No todos los elementos visuales de WPF tienen elementos de automatización del mismo nivel. Ejemplos de clases que implementan elementos de automatización del mismo nivel son <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.TextBox>y <xref:System.Windows.Controls.Label>. Ejemplos de clases que no implementan elementos de automatización del mismo nivel son clases que derivan de <xref:System.Windows.Controls.Decorator>, como <xref:System.Windows.Controls.Border>, y clases basadas en <xref:System.Windows.Controls.Panel>, como <xref:System.Windows.Controls.Grid> y <xref:System.Windows.Controls.Canvas>.  
  
 La clase de <xref:System.Windows.Controls.Control> base no tiene una clase del mismo nivel correspondiente. Si necesita que una clase del mismo nivel se corresponda con un control personalizado que se deriva de <xref:System.Windows.Controls.Control>, debe derivar la clase personalizada del mismo nivel de <xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>.  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations-for-derived-peers"></a>Consideraciones de seguridad para elementos del mismo nivel derivados  
 Los elementos de automatización del mismo nivel deben ejecutarse en un entorno de confianza parcial. El código del ensamblado UIAutomationClient no está configurado para ejecutarse en un entorno de confianza parcial y el código de automatización del mismo nivel no debe hacer referencia a dicho ensamblado. En su lugar, debe usar las clases del ensamblado UIAutomationTypes. Por ejemplo, debe usar la clase <xref:System.Windows.Automation.AutomationElementIdentifiers> del ensamblado UIAutomationTypes, que corresponde a la clase <xref:System.Windows.Automation.AutomationElement> en el ensamblado UIAutomationClient. Es seguro hacer referencia al ensamblado UIAutomationTypes en el código de automatización del mismo nivel.  
  
<a name="PeerNavigation"></a>   
## <a name="peer-navigation"></a>Navegación entre elementos del mismo nivel  
 Después de encontrar un elemento de automatización del mismo nivel, el código en proceso puede navegar por el árbol del mismo nivel llamando a los métodos <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A> y <xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A> del objeto. La navegación entre los elementos de WPF dentro de un control es compatible con la implementación del mismo nivel del método <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A>. El sistema de automatización de la interfaz de usuario llama a este método para crear un árbol de subelementos incluidos dentro de un control; por ejemplo, los elementos de lista de un cuadro de lista. El método <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=nameWithType> predeterminado atraviesa el árbol visual de elementos para compilar el árbol de elementos de automatización del mismo nivel. Los controles personalizados invalidan este método para exponer los elementos secundarios a los clientes de automatización, y devuelven aquellos elementos de automatización del mismo nivel que transmiten información o permiten la interacción del usuario.  
  
<a name="Customizations"></a>   
## <a name="customizations-in-a-derived-peer"></a>Personalizaciones en un elemento del mismo nivel derivado  
 Todas las clases que derivan de <xref:System.Windows.UIElement> y <xref:System.Windows.ContentElement> contienen el método virtual protegido <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>. WPF llama a <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> para obtener el objeto de automatización del mismo nivel para cada control. El código de automatización puede utilizar el elemento del mismo nivel para obtener información sobre las características y funciones de un control, y simular el uso interactivo. Un control personalizado que admite Automation debe reemplazar <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> y devolver una instancia de una clase que deriva de <xref:System.Windows.Automation.Peers.AutomationPeer>. Por ejemplo, si un control personalizado se deriva de la clase <xref:System.Windows.Controls.Primitives.ButtonBase>, el objeto devuelto por <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> debe derivar de <xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>.  
  
 Al implementar un control personalizado, se deben invalidar los métodos "Core" de la clase base de automatización del mismo nivel, que describen el comportamiento único y específico del control personalizado.  
  
### <a name="override-oncreateautomationpeer"></a>Invalidar OnCreateAutomationPeer  
 Invalide el método <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> para el control personalizado de modo que devuelva el objeto de proveedor, que debe derivarse directa o indirectamente de <xref:System.Windows.Automation.Peers.AutomationPeer>.  
  
### <a name="override-getpattern"></a>Invalidar GetPattern  
 Los elementos de automatización del mismo nivel simplifican algunos aspectos de la implementación de proveedores de [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] del lado servidor; sin embargo, los elementos de automatización del mismo nivel de un control personalizado deben controlar las interfaces de patrón. Al igual que los proveedores que no son de WPF, los elementos del mismo nivel admiten patrones de control al proporcionar implementaciones de interfaces en el espacio de nombres <xref:System.Windows.Automation.Provider?displayProperty=nameWithType>, como <xref:System.Windows.Automation.Provider.IInvokeProvider>. Las interfaces de patrón de control pueden implementarlas el propio elemento del mismo nivel u otro objeto. La implementación del mismo nivel de <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> devuelve el objeto que admite el patrón especificado. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] código llama al método <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> y especifica un valor de enumeración <xref:System.Windows.Automation.Peers.PatternInterface>. La invalidación de <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> debe devolver el objeto que implementa el patrón especificado. Si el control no tiene una implementación personalizada de un patrón, puede llamar a la implementación del tipo base de <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> para recuperar su implementación o null si el patrón no se admite para este tipo de control. Por ejemplo, un control NumericUpDown personalizado se puede establecer en un valor dentro de un intervalo, por lo que su [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] del mismo nivel implementaría la interfaz <xref:System.Windows.Automation.Provider.IRangeValueProvider>. En el ejemplo siguiente se muestra cómo se invalida el método de <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> del mismo nivel para responder a un valor de <xref:System.Windows.Automation.Peers.PatternInterface.RangeValue?displayProperty=nameWithType>.  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 Un método <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> también puede especificar un subelemento como proveedor de patrones. En el código siguiente se muestra cómo <xref:System.Windows.Controls.ItemsControl> transfiere el control del patrón de desplazamiento al elemento del mismo nivel de su control de <xref:System.Windows.Controls.ScrollViewer> interno.  
  
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
  
 Para especificar un subelemento para el control de patrones, este código obtiene el objeto de subelemento, crea un elemento del mismo nivel mediante el método <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A>, establece la propiedad <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> del nuevo elemento del mismo nivel en el elemento del mismo nivel actual y devuelve el nuevo elemento del mismo nivel. El establecimiento de <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> en un subelemento evita que el subelemento aparezca en el árbol de automatización del mismo nivel y designa todos los eventos generados por el subelemento como originados en el control especificado en <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>. El control <xref:System.Windows.Controls.ScrollViewer> no aparece en el árbol de automatización y los eventos de desplazamiento que genera parecen originarse en el objeto <xref:System.Windows.Controls.ItemsControl>.  
  
### <a name="override-core-methods"></a>Invalidar métodos "Core"  
 Para obtener información sobre el control, el código de automatización llama a métodos públicos de la clase del mismo nivel. Para proporcionar información sobre el control, invalide los métodos cuyo nombre termina con "Core" en caso de que la implementación del control sea diferente de la que proporciona la clase base de automatización del mismo nivel. Como mínimo, el control debe implementar los métodos <xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A> y <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A>, tal y como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 La implementación de <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> describe el control devolviendo un valor de <xref:System.Windows.Automation.ControlType>. Aunque puede devolver <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType>, debe devolver uno de los tipos de control más específicos si describe con precisión el control. Un valor devuelto de <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType> requiere un trabajo adicional para que el proveedor implemente [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]y [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] productos cliente no pueden prever la estructura del control, la interacción con el teclado y posibles patrones de control.  
  
 Implemente los métodos <xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A> y <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> para indicar si el control contiene contenido de datos o si cumple un rol interactivo en la interfaz de usuario (o ambos). De forma predeterminada, ambos métodos devuelven `true`. Esta configuración aumenta la facilidad de uso de herramientas de automatización, como lectores de pantalla, que pueden utilizar estos métodos para filtrar el árbol de automatización. Si el método de <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> transfiere el control del patrón a un subelemento del mismo nivel, el método de <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> del subelemento del mismo nivel puede devolver false para ocultar el subelemento del mismo nivel del árbol de automatización. Por ejemplo, el desplazamiento en un <xref:System.Windows.Controls.ListBox> se controla mediante un <xref:System.Windows.Controls.ScrollViewer>y el método <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> del <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> asociado al <xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>devuelve la automatización del mismo nivel para <xref:System.Windows.Automation.Peers.PatternInterface.Scroll?displayProperty=nameWithType>. Por lo tanto, el método <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> del <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> devuelve `false`, de modo que el <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> no aparezca en el árbol de automatización.  
  
 El elemento de automatización del mismo nivel debe proporcionar los valores predeterminados adecuados para el control. Tenga en cuenta que el código XAML que hace referencia al control puede invalidar las implementaciones del mismo nivel de los métodos principales mediante la inclusión de atributos de <xref:System.Windows.Automation.AutomationProperties>. Por ejemplo, el código XAML siguiente crea un botón que tiene dos propiedades personalizadas [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)].  
  
```xaml  
<Button AutomationProperties.Name="Special"   
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>Implementar proveedores de patrón  
 Las interfaces implementadas por un proveedor personalizado se declaran explícitamente si el elemento propietario deriva directamente de <xref:System.Windows.Controls.Control>. Por ejemplo, el código siguiente declara un elemento del mismo nivel para un <xref:System.Windows.Controls.Control> que implementa un valor de intervalo.  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 Si el control propietario se deriva de un tipo específico de control como <xref:System.Windows.Controls.Primitives.RangeBase>, el elemento del mismo nivel se puede derivar de una clase derivada equivalente equivalente. En este caso, el elemento del mismo nivel derivaría de <xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer>, que proporciona una implementación base de <xref:System.Windows.Automation.Provider.IRangeValueProvider>. El código siguiente muestra la declaración de un elemento del mismo nivel como este.  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
Para ver una implementación de ejemplo, [C#](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp) vea el código fuente o [Visual Basic](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic) que implementa y usa un control personalizado NumericUpDown.  
  
### <a name="raise-events"></a>Generar eventos  
 Los clientes de automatización pueden suscribirse a eventos de automatización. Los controles personalizados deben notificar los cambios en el estado del control llamando al método <xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A>. Del mismo modo, cuando cambia el valor de una propiedad, llame al método <xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A>. El código siguiente muestra cómo obtener el objeto del mismo nivel desde el código del control, y cómo llamar a un método para generar un evento. Como optimización, el código determina si hay agentes de escucha para este tipo de evento. Generar el evento únicamente cuando hay agentes de escucha evita una sobrecarga innecesaria y ayuda a que el control siga respondiendo.  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre la Automatización de la interfaz de usuario](../../ui-automation/ui-automation-overview.md)
- [Implementación del proveedor de automatización de la interfaz de usuario en el servidor](../../ui-automation/server-side-ui-automation-provider-implementation.md)
- [Control personalizado NumericUpDown (C#) en github](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp)  
- [Control personalizado NumericUpDown (Visual Basic) en GitHub](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic)
