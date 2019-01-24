---
title: Modelos de evento débil
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: ad0b30c9f628148f77761ff3af810b484c5ae583
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632925"
---
# <a name="weak-event-patterns"></a>Modelos de evento débil
En las aplicaciones, es posible que los controladores que están conectados a orígenes de eventos no se destruirán en coordinación con el objeto de agente de escucha que adjuntó el controlador para el origen. Esta situación puede provocar pérdidas de memoria. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] presenta un patrón de diseño que se puede usar para resolver este problema, que proporciona una clase de administrador dedicada para eventos concretos e implementando una interfaz en los agentes de escucha para ese evento. Este patrón de diseño se conoce como el *modelo de evento débil*.  
  
## <a name="why-implement-the-weak-event-pattern"></a>¿Por qué implementar el modelo de evento débil?  
 Escucha de eventos puede dar lugar a pérdidas de memoria. La técnica típica para realizar escuchas de eventos es usar la sintaxis específica del lenguaje que se adjunta un controlador a un evento en un origen. Por ejemplo, en C#, que la sintaxis es: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.  
  
 Esta técnica crea una referencia segura desde el origen del evento a la escucha de eventos. Normalmente, adjuntar un controlador de eventos para un agente de escucha, hace que el agente de escucha tienen una duración de objeto que se ve afectada por la duración del objeto de origen (a menos que explícitamente se quita el controlador de eventos). Pero en determinadas circunstancias, puede que desee la duración del objeto del agente de escucha que estén controladas por otros factores, como si lo actualmente pertenece al árbol visual de la aplicación y no por la duración de la fuente. Cada vez que la duración del objeto de origen se extiende más allá de la duración del objeto del agente de escucha, el patrón de eventos normales conduce a una pérdida de memoria: el agente de escucha se mantiene activo más tiempo del previsto.  
  
 El modelo de evento débil está diseñado para resolver este problema de pérdida de memoria. El modelo de evento débil puede usarse siempre que un agente de escucha necesita registrarse para un evento, pero el agente de escucha no conoce explícitamente cuándo se debe anular el registro. También se puede usar el modelo de evento débil cada vez que la duración del objeto de origen supera la duración del objeto útiles del agente de escucha. (En este caso, *útil* viene determinada por el usuario.) El modelo de evento débil permite que el agente de escucha para registrarse y recibir el evento sin que afecte a las características de la duración de objeto del agente de escucha de ninguna manera. De hecho, la referencia implícita desde el origen no determina si el agente de escucha es apto para la recolección de elementos. La referencia es una referencia débil, por lo tanto la denominación de modelo de evento débil y relacionado [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]. El agente de escucha puede ser elementos no utilizados o se destruye en caso contrario, y el origen puede continuar sin conservar las referencias de controlador no recopilables a un objeto que se ha destruido.  
  
## <a name="who-should-implement-the-weak-event-pattern"></a>¿Quién debe implementar el modelo de evento débil?  
 Implementar el patrón de evento débil es interesante, principalmente para los autores de controles. Como autor del control, es responsable en gran medida el comportamiento y la contención de su control y el impacto que tiene en las aplicaciones en la que se inserta. Esto incluye el comportamiento de duración de objetos de control, en particular la administración del problema de pérdida de memoria descrito.  
  
 Ciertos escenarios intrínsecamente se prestan a la aplicación del modelo de evento débil. Uno de estos escenarios es el enlace de datos. En el enlace de datos, es común para el objeto de origen que sean completamente independientes del objeto de agente de escucha, que es un destino de un enlace. Muchos aspectos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enlace de datos ya tiene el modelo de evento débil aplicado en cómo se implementan los eventos.  
  
## <a name="how-to-implement-the-weak-event-pattern"></a>Cómo implementar el modelo de evento débil  
 Hay tres maneras de implementar el modelo de evento débil. En la tabla siguiente se enumera los tres enfoques y ofrece algunas indicaciones sobre cuándo deben usar cada uno.  
  
|Enfoque|Cuándo implementar|  
|--------------|-----------------------|  
|Usar una clase de administrador existente de evento débil|Si el evento que desea suscribirse a le corresponde una <xref:System.Windows.WeakEventManager>, utilice el Administrador de evento débil existente. Para obtener una lista de administradores de evento débil que se incluyen con WPF, vea la jerarquía de herencia en el <xref:System.Windows.WeakEventManager> clase. Dado que los administradores de evento débil incluye son limitados, probablemente tendrá que elegir uno de los otros enfoques.|  
|Usar una clase de evento débil genérico manager|Usar un tipo genérico <xref:System.Windows.WeakEventManager%602> cuando existente <xref:System.Windows.WeakEventManager> es en cuestión no está disponible, desea una manera fácil de implementar, y no sobre la eficacia. La interfaz genérica <xref:System.Windows.WeakEventManager%602> es menos eficaz que un administrador de evento débil existentes o personalizadas. Por ejemplo, la clase genérica hace más de reflexión para detectar el evento que tiene el nombre del evento. Además, el código para registrar el evento mediante el modelo genérico <xref:System.Windows.WeakEventManager%602> es más detallado que el uso de una existente o personalizado <xref:System.Windows.WeakEventManager>.|  
|Crear una clase de administrador personalizado de evento débil|Crear un personalizado <xref:System.Windows.WeakEventManager> cuando existente <xref:System.Windows.WeakEventManager> no está disponible y desea que la mejor eficacia. Utiliza una <xref:System.Windows.WeakEventManager> para suscribirse a un evento será más eficaz, pero se incurre en el costo de escribir más código al principio.|  
|Usar un administrador de evento débil de terceros|NuGet tiene [varios administradores de evento débil](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) y muchos marcos WPF también admiten el patrón (por ejemplo, ver [documentación de Prism en la suscripción de eventos de correspondencia imprecisa](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/Communication.md#subscribing-to-events)).|

 Las secciones siguientes describen cómo implementar el modelo de evento débil.  Para propósitos de este tutorial, el evento para la suscripción tiene las siguientes características.  
  
-   Es el nombre del evento `SomeEvent`.  
  
-   El evento es desencadenado por la `EventSource` clase.  
  
-   El controlador de eventos tiene el tipo: `SomeEventEventHandler` (o `EventHandler<SomeEventEventArgs>`).  
  
-   El evento pasa un parámetro de tipo `SomeEventEventArgs` a los controladores de eventos.  
  
### <a name="using-an-existing-weak-event-manager-class"></a>Uso de una clase de administrador de eventos débiles existente  
  
1.  Encuentre un evento existente débil manager.  
  
     Para obtener una lista de administradores de evento débil que se incluyen con WPF, vea la jerarquía de herencia en el <xref:System.Windows.WeakEventManager> clase.  
  
2.  Use el nuevo administrador de evento débil en lugar de los enlaces de eventos normales.  
  
     Por ejemplo, si el código usa el patrón siguiente para suscribirse a un evento:  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Puede cambiarlo en el siguiente patrón:  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     De forma similar, si el código usa el patrón siguiente para cancelar la suscripción a un evento:  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     Puede cambiarlo en el siguiente patrón:  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a>Uso de la clase de administrador de eventos genéricos débil  
  
1.  Utilice el tipo genérico <xref:System.Windows.WeakEventManager%602> clase en lugar de los enlaces de eventos normales.  
  
     Cuando usas <xref:System.Windows.WeakEventManager%602> para registrar los agentes de escucha de eventos, proporciona el origen del evento y <xref:System.EventArgs> tipo como parámetros de tipo para la clase y llamar a <xref:System.Windows.WeakEventManager%602.AddHandler%2A> tal como se muestra en el código siguiente:  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a>Creación de una clase personalizada de administrador de evento débil  
  
1.  Copie la siguiente plantilla de clase al proyecto.  
  
     Esta clase hereda de la <xref:System.Windows.WeakEventManager> clase.  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2.  Reemplace el `SomeEventWeakEventManager` nombre con su propio nombre.  
  
3.  Reemplace los tres nombres que se ha descrito anteriormente con los nombres correspondientes para el evento. (`SomeEvent`, `EventSource`, y `SomeEventEventArgs`)  
  
4.  Establecer la visibilidad (pública o interna o privada) de la clase de evento débil manager en la misma visibilidad que administra el evento.  
  
5.  Use el nuevo administrador de evento débil en lugar de los enlaces de eventos normales.  
  
     Por ejemplo, si el código usa el patrón siguiente para suscribirse a un evento:  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Puede cambiarlo en el siguiente patrón:  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     De forma similar, si el código usa el patrón siguiente para cancelar la suscripción a un evento:  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     Puede cambiarlo en el siguiente patrón:  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
- [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)
