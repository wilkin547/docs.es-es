---
title: Modelos de evento débil
description: Obtenga información sobre el patrón de evento débil Windows Presentation Foundation, que soluciona el problema de los controladores que no se destruyen, evitando las pérdidas de memoria.
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: 75c6888c8ac20c41d13e3787005377c75248c5d9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168262"
---
# <a name="weak-event-patterns"></a>Modelos de evento débil
En las aplicaciones, es posible que los controladores asociados a los orígenes de eventos no se destruyan en coordinación con el objeto de agente de escucha que adjuntó el controlador al origen. Esta situación puede provocar pérdidas de memoria. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]presenta un modelo de diseño que se puede usar para solucionar este problema, proporcionando una clase de administrador dedicada para eventos concretos e implementando una interfaz en agentes de escucha para ese evento. Este modelo de diseño se conoce como el *patrón de evento débil*.  
  
## <a name="why-implement-the-weak-event-pattern"></a>¿Por qué implementar el patrón de evento débil?  
 La escucha de eventos puede dar lugar a pérdidas de memoria. La técnica típica para escuchar un evento es usar la sintaxis específica del lenguaje que asocia un controlador a un evento en un origen. Por ejemplo, en C#, esa sintaxis es: `source.SomeEvent += new SomeEventHandler(MyEventHandler)` .  
  
 Esta técnica crea una referencia segura desde el origen de eventos al agente de escucha de eventos. Normalmente, al adjuntar un controlador de eventos para un agente de escucha, el agente de escucha tiene una duración de objeto que se ve afectada por la duración del objeto del origen (a menos que se quite explícitamente el controlador de eventos). Pero en determinadas circunstancias, puede que desee que la duración del objeto del agente de escucha se controle por otros factores, como si actualmente pertenece al árbol visual de la aplicación, y no por la duración del origen. Cuando la duración del objeto de origen se extiende más allá de la duración del objeto del agente de escucha, el patrón de evento normal conduce a una fuga de memoria: el agente de escucha se mantiene activo más tiempo del previsto.  
  
 El patrón de evento débil está diseñado para resolver este problema de pérdida de memoria. El patrón de evento débil se puede usar siempre que un agente de escucha debe registrarse para un evento, pero el agente de escucha no sabe explícitamente Cuándo se debe anular el registro. El patrón de evento débil también se puede usar cuando la duración del objeto del origen supera la duración útil del objeto del agente de escucha. (En este *caso, lo* determina el usuario). El modelo de evento débil permite al agente de escucha registrarse y recibir el evento sin afectar a las características de la duración de los objetos del agente de escucha de ninguna manera. En efecto, la referencia implícita del origen no determina si el agente de escucha es válido para la recolección de elementos no utilizados. La referencia es una referencia débil, por lo tanto, la denominación del modelo de evento débil y las API relacionadas. El agente de escucha se puede recolectar o destruir de otro modo, y el origen puede continuar sin conservar las referencias de controlador no recopilables a un objeto ya destruido.  
  
## <a name="who-should-implement-the-weak-event-pattern"></a>¿Quién debe implementar el patrón de evento débil?  
 Implementar el patrón de evento débil es interesante principalmente para los autores de controles. Como autor de un control, es principalmente responsable del comportamiento y la contención del control y el impacto que tiene en las aplicaciones en las que se inserta. Esto incluye el comportamiento de duración del objeto de control, en particular el control del problema de pérdida de memoria que se describe.  
  
 Ciertos escenarios se prestan de forma inherente a la aplicación del modelo de evento débil. Uno de estos escenarios es el enlace de datos. En el enlace de datos, es habitual que el objeto de origen sea completamente independiente del objeto de agente de escucha, que es un destino de un enlace. Muchos aspectos del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enlace de datos ya tienen el patrón de evento débil aplicado en cómo se implementan los eventos.  
  
## <a name="how-to-implement-the-weak-event-pattern"></a>Cómo implementar el patrón de evento débil  
 Hay tres maneras de implementar el patrón de evento débil. En la tabla siguiente se enumeran los tres enfoques y se proporcionan instrucciones sobre cuándo se debe utilizar cada uno de ellos.  
  
|Enfoque|Cuándo implementar|  
|--------------|-----------------------|  
|Usar una clase de administrador de eventos débiles existente|Si el evento al que desea suscribirse tiene un correspondiente <xref:System.Windows.WeakEventManager> , use el administrador de eventos débiles existente. Para obtener una lista de los administradores de eventos débiles que se incluyen con WPF, vea la jerarquía de herencia en la <xref:System.Windows.WeakEventManager> clase. Dado que los administradores de eventos débiles incluidos están limitados, probablemente tendrá que elegir uno de los otros enfoques.|  
|Usar una clase genérica de administrador de eventos débiles|Usar una genérica <xref:System.Windows.WeakEventManager%602> cuando una existente <xref:System.Windows.WeakEventManager> no está disponible, desea una manera fácil de implementar y no le preocupa la eficacia. El genérico <xref:System.Windows.WeakEventManager%602> es menos eficaz que un administrador de eventos débil existente o personalizado. Por ejemplo, la clase genérica realiza más reflexión para detectar el evento dado el nombre del evento. Además, el código para registrar el evento utilizando el genérico <xref:System.Windows.WeakEventManager%602> es más detallado que el uso de un existente o personalizado <xref:System.Windows.WeakEventManager> .|  
|Creación de una clase de administrador de eventos débiles personalizada|Cree un personalizado <xref:System.Windows.WeakEventManager> cuando un existente <xref:System.Windows.WeakEventManager> no esté disponible y desee obtener la máxima eficacia. El uso de un personalizado <xref:System.Windows.WeakEventManager> para suscribirse a un evento será más eficaz, pero incurrirá en el costo de escribir más código al principio.|  
|Usar un administrador de eventos débil de terceros|NuGet tiene [varios administradores de eventos débiles](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) y muchos marcos de WPF también admiten el patrón (por ejemplo, consulte la [documentación de Prism sobre la suscripción a eventos de acoplamiento flexible](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/legacy/Communication.md#subscribing-to-events)).|

 En las secciones siguientes se describe cómo implementar el patrón de evento débil.  Para los fines de este debate, el evento al que se va a suscribir tiene las siguientes características.  
  
- El nombre del evento es `SomeEvent` .  
  
- El evento es desencadenado por la `EventSource` clase.  
  
- El controlador de eventos tiene el tipo: `SomeEventEventHandler` (o `EventHandler<SomeEventEventArgs>` ).  
  
- El evento pasa un parámetro de tipo `SomeEventEventArgs` a los controladores de eventos.  
  
### <a name="using-an-existing-weak-event-manager-class"></a>Usar una clase de administrador de eventos débiles existente  
  
1. Busque un administrador de eventos débil existente.  
  
     Para obtener una lista de los administradores de eventos débiles que se incluyen con WPF, vea la jerarquía de herencia en la <xref:System.Windows.WeakEventManager> clase.  
  
2. Use el nuevo administrador de eventos débiles en lugar del enlace de eventos normal.  
  
     Por ejemplo, si el código usa el siguiente patrón para suscribirse a un evento:  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Cámbielo al siguiente patrón:  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     Del mismo modo, si el código usa el siguiente patrón para cancelar la suscripción a un evento:  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Cámbielo al siguiente patrón:  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a>Usar la clase Generic Event Manager débil  
  
1. Use la <xref:System.Windows.WeakEventManager%602> clase genérica en lugar del enlace de eventos normal.  
  
     Cuando se usa <xref:System.Windows.WeakEventManager%602> para registrar agentes de escucha de eventos, se proporciona el origen del evento y el <xref:System.EventArgs> tipo como parámetros de tipo a la clase y se llama a <xref:System.Windows.WeakEventManager%602.AddHandler%2A> tal como se muestra en el código siguiente:  
  
    ```csharp  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a>Creación de una clase personalizada de administrador de eventos débiles  
  
1. Copie la siguiente plantilla de clase en el proyecto.  
  
     Esta clase hereda de la <xref:System.Windows.WeakEventManager> clase.  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2. Reemplace el `SomeEventWeakEventManager` nombre por su propio nombre.  
  
3. Reemplace los tres nombres descritos anteriormente con los nombres correspondientes del evento. ( `SomeEvent` , `EventSource` y `SomeEventEventArgs` )  
  
4. Establezca la visibilidad (pública/interna/privada) de la clase débil de Event Manager en la misma visibilidad que el evento que administra.  
  
5. Use el nuevo administrador de eventos débiles en lugar del enlace de eventos normal.  
  
     Por ejemplo, si el código usa el siguiente patrón para suscribirse a un evento:  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Cámbielo al siguiente patrón:  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     Del mismo modo, si el código usa el siguiente patrón para cancelar la suscripción a un evento:  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     Cámbielo al siguiente patrón:  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [Información general sobre eventos enrutados](routed-events-overview.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
