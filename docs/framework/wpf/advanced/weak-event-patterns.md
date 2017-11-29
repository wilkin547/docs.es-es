---
title: "Modelos de evento débil"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a27e17e4940ff68f34d1e7e4accfb9e112bc412b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="weak-event-patterns"></a>Modelos de evento débil
En las aplicaciones, es posible que los controladores que están conectados a los orígenes de eventos no se destruirán en coordinación con el objeto de agente de escucha que se adjunta el controlador para el origen. Esta situación puede provocar pérdidas de memoria. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]Introduce un modelo de diseño que puede utilizarse para solucionar este problema, debe proporcionar una clase de administrador dedicada para eventos concretos e implementando una interfaz en los agentes de escucha para ese evento. Este patrón de diseño se conoce como el *modelo de evento débil*.  
  
## <a name="why-implement-the-weak-event-pattern"></a>¿Por qué implementar el modelo de evento débil?  
 Realizar escuchas de eventos pueden provocar pérdidas de memoria. La técnica típica para realizar escuchas de eventos es utilizar la sintaxis específica del lenguaje que asocia un controlador a un evento en un origen. Por ejemplo, en [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)], que la sintaxis es: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.  
  
 Esta técnica crea una referencia segura desde el origen de eventos para el agente de escucha de eventos. Por lo general, asociar un controlador de eventos para un agente de escucha hace que el agente de escucha tienen una duración de los objetos que se ven afectada por la duración del objeto de origen (a menos que explícitamente se quita el controlador de eventos). Sin embargo, en ciertas circunstancias, podrían desear la duración de los objetos del agente de escucha esté controlada por otros factores, como si actualmente pertenece al árbol visual de la aplicación y no por la duración del origen. Cada vez que la duración del objeto de origen se extiende más allá de la duración de los objetos del agente de escucha, el patrón de eventos normales conduce a una pérdida de memoria: el agente de escucha se mantiene activo más tiempo del previsto.  
  
 El modelo de evento débil está diseñado para resolver este problema de pérdida de memoria. El modelo de evento débil se pueden usar cuando un agente de escucha debe suscribirse a un evento, pero el agente de escucha no sabe explícitamente cuándo se debe anular el registro. También se puede utilizar el modelo de evento débil siempre que la duración de los objetos del origen supera la duración de los objetos útiles del agente de escucha. (En este caso, *útil* se determina por el usuario.) El modelo de evento débil permite que el agente de escucha registrar y reciban el evento sin que afecte a las características de duración de objeto del agente de escucha de ninguna manera. De hecho, la referencia implícita del origen no determina si el agente de escucha es apto para la recolección de elementos no utilizados. La referencia es una referencia débil, por lo tanto la denominación de modelo de evento débil y relacionado [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]. El agente de escucha puede ser elementos no utilizados o en caso contrario, se destruye y el origen puede continuar sin conservar las referencias de controlador no recopilables a un objeto que se ha destruido.  
  
## <a name="who-should-implement-the-weak-event-pattern"></a>¿Que deben implementar el modelo de evento débil?  
 Implementar el patrón de eventos débiles es interesante principalmente para los autores de controles. Como autor de un control, es responsable en gran medida el comportamiento y la contención de su control y el impacto en las aplicaciones en el que se inserta. Esto incluye el comportamiento de duración de objetos de control, en particular el tratamiento del problema de pérdida de memoria descrito.  
  
 Algunos escenarios se prestan de forma inherente a la aplicación del modelo de evento débil. Uno de estos escenarios es el enlace de datos. En el enlace de datos, es común para el objeto de origen que sean completamente independientes del objeto de agente de escucha, que es un destino de un enlace. Muchos aspectos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enlace de datos ya tiene el modelo de evento débil aplicado en cómo se implementan los eventos.  
  
## <a name="how-to-implement-the-weak-event-pattern"></a>Cómo implementar el modelo de evento débil  
 Hay tres maneras de implementar el modelo de evento débil. En la tabla siguiente se enumera los tres enfoques y proporciona cierta orientación acerca de cuándo se debe utilizar cada una.  
  
|Enfoque|Cuándo implementar|  
|--------------|-----------------------|  
|Utilizar una clase de administrador de eventos débiles existente|Si el evento que desea suscribirse a tiene su correspondiente <xref:System.Windows.WeakEventManager>, use el Administrador de eventos débiles existentes. Para obtener una lista de administradores de eventos débiles que se incluyen con WPF, vea la jerarquía de herencia en la <xref:System.Windows.WeakEventManager> clase. Sin embargo, tenga en cuenta que hay relativamente pocos administradores de eventos débiles que se incluyen con WPF, por lo que probablemente tendrá que elegir uno de los otros métodos.|  
|Use una clase de administrador de eventos débiles genérico|Usar un tipo genérico <xref:System.Windows.WeakEventManager%602> cuando existente <xref:System.Windows.WeakEventManager> es no disponible, desea una manera fácil de implementar, y no están preocupada con eficacia. La interfaz genérica <xref:System.Windows.WeakEventManager%602> resulta menos eficaz que un administrador de eventos débiles existentes o personalizadas. Por ejemplo, la clase genérica hace más de reflexión para detectar el evento que tiene el nombre del evento. Además, el código para registrar el evento mediante la interfaz genérica <xref:System.Windows.WeakEventManager%602> es más detallado que el uso de una existente o personalizado <xref:System.Windows.WeakEventManager>.|  
|Crear una clase de administrador de eventos débiles personalizado|Crear una personalizada <xref:System.Windows.WeakEventManager> cuando se existente <xref:System.Windows.WeakEventManager> no está disponible y desea que la mejor eficacia. Usando un comparador <xref:System.Windows.WeakEventManager> para suscribirse a un evento será más eficaz, pero se incurre en el costo de escribir más código al principio.|  
  
 Las secciones siguientes describen cómo implementar el patrón de eventos débiles.  Para fines de este análisis, el evento para suscribirse a tiene las siguientes características.  
  
-   Es el nombre del evento `SomeEvent`.  
  
-   El evento es desencadenado por la `EventSource` clase.  
  
-   El controlador de eventos tiene el tipo: `SomeEventEventHandler` (o `EventHandler<SomeEventEventArgs>`).  
  
-   El evento pasa un parámetro de tipo `SomeEventEventArgs` a los controladores de eventos.  
  
### <a name="using-an-existing-weak-event-manager-class"></a>Usar una clase de evento Manager débil existente  
  
1.  Encuentra el Administrador de un evento débil existente.  
  
     Para obtener una lista de administradores de eventos débiles que se incluyen con WPF, vea la jerarquía de herencia en la <xref:System.Windows.WeakEventManager> clase.  
  
2.  Use el nuevo administrador de eventos débiles en lugar de los enlaces de eventos normales.  
  
     Por ejemplo, si el código usa el modelo siguiente para suscribirse a un evento:  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Cambia al siguiente patrón:  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     De forma similar, si el código usa el modelo siguiente para cancelar la suscripción a un evento:  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     Cambia al siguiente patrón:  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a>Uso de la clase de administrador de eventos débiles genérico  
  
1.  Usar la interfaz genérica <xref:System.Windows.WeakEventManager%602> clase en lugar de los enlaces de eventos normales.  
  
     Cuando usas <xref:System.Windows.WeakEventManager%602> para registrar los agentes de escucha de eventos, se proporciona el origen del evento y <xref:System.EventArgs> tipo como parámetros de tipo para la clase y llamar a <xref:System.Windows.WeakEventManager%602.AddHandler%2A> tal como se muestra en el código siguiente:  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a>Crear una clase de evento Manager débil personalizada  
  
1.  Copie la siguiente plantilla de clase al proyecto.  
  
     Esta clase hereda de la <xref:System.Windows.WeakEventManager> clase.  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2.  Reemplace el `SomeEventWeakEventManager` nombre con su propio nombre.  
  
3.  Reemplace los nombres de tres descritos previamente con los nombres correspondientes para el evento. (`SomeEvent`, `EventSource`, y `SomeEventEventArgs`)  
  
4.  Establecer la visibilidad (pública / interna / privada) de la clase de eventos débiles manager a la misma visibilidad que administra el evento.  
  
5.  Use el nuevo administrador de eventos débiles en lugar de los enlaces de eventos normales.  
  
     Por ejemplo, si el código usa el modelo siguiente para suscribirse a un evento:  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Cambia al siguiente patrón:  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     De forma similar, si el código usa el modelo siguiente para cancelar la suscripción a un evento:  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     Cambia al siguiente patrón:  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.WeakEventManager>  
 <xref:System.Windows.IWeakEventListener>  
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)
