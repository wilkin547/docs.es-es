---
title: "Modelos de evento d&#233;bil | Microsoft Docs"
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
  - "controladores de eventos, modelo de evento débil"
  - "IWeakEventListener (interfaz)"
  - "implementación del modelo de evento débil"
  - "WeakEventManager (clase)"
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Modelos de evento d&#233;bil
En las aplicaciones típicas, es posible que los controladores asociados a los orígenes de eventos no se destruyan en coordinación con el objeto de agente de escucha que adjuntó el controlador al origen.  Esta situación puede provocar pérdidas de memoria.  [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] introduce un modelo de diseño concreto que se puede usar para resolver este problema; para ello, proporciona una clase de administrador dedicada para eventos concretos e implementa una interfaz para los agentes de escucha de ese evento.  Este modelo de diseño se denomina *modelo de evento débil*.  
  
## ¿Por qué implementar el modelo de evento débil?  
 Realizar escuchas de eventos puede provocar pérdidas de memoria.  La técnica típica para realizar escuchas de eventos consiste en utilizar la sintaxis específica del lenguaje que asocia un controlador a un evento en un origen.  Por ejemplo, en [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)], esa sintaxis es: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.  
  
 Esta técnica crea una referencia segura desde el origen de evento al agente de escucha de evento.  En general, al adjuntar un controlador de eventos para un agente de escucha, la duración de objeto del origen influye en la duración de objeto del agente \(a menos que el controlador de eventos se quite explícitamente\).  Sin embargo, en determinadas circunstancias puede ser conveniente controlar la duración de objeto del agente de escucha mediante otros factores, tales como si pertenece actualmente al árbol visual de la aplicación, no mediante la duración del origen.  Cada vez que la duración de objeto del origen es superior a la del agente de escucha, el modelo de eventos normal provoca una pérdida de memoria: el agente de escucha se mantiene activo más tiempo del previsto.  
  
 El modelo de evento débil está diseñado para resolver este problema de pérdida de memoria.  Se puede utilizar el modelo de evento débil cada vez que un agente de escucha necesita registrarse para un evento, pero el agente de escucha no sabe explícitamente cuándo cancelar el registro.  También se puede usar el modelo de evento débil cuando la duración de los objetos del origen supera la duración útil de los objetos del agente de escucha.  \(En este caso, *útil* es determinado por el desarrollador\). El modelo de evento débil permite al agente de escucha registrarse para el evento y recibirlo sin que ello afecte en modo alguno a sus características de duración de objeto.  En efecto, la referencia implícita del origen no determina si el agente de escucha es apto para la recolección de elementos no utilizados.  Se trata de una referencia débil, concepto del que toman su nombre el modelo de evento débil y las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] relacionadas.  El agente de escucha puede someterse a la recopilación de elementos no utilizados o destruirse de alguna otra forma, y el origen puede continuar sin conservar las referencias al objeto que se ha destruido no recopilables en el controlador.  
  
## ¿Quién debe implementar el modelo de evento débil?  
 Implementar el modelo de evento débil resulta interesante principalmente para los autores de controles.  El autor de un control es responsable en gran medida del comportamiento y la contención del control y del efecto que ejerce en las aplicaciones en las que se inserta.  Esto incluye el comportamiento de la duración de objeto del control, y en particular de la administración del problema de pérdida de memoria descrito.  
  
 Algunos escenarios se prestan de forma inherente a la aplicación del modelo de evento débil.  Un escenario de este tipo es el enlace de datos.  En el enlace de datos, es común que el objeto de origen sea completamente independiente del objeto de agente de escucha, que es un destino de un enlace.  El modelo de evento débil ya se aplica a muchos aspectos del enlace de datos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en lo relativo a cómo se implementan los eventos.  
  
## Cómo implementar el modelo de evento débil  
 Hay tres maneras de implementar el modelo de evento débil.  La tabla siguiente se enumeran los tres enfoques y proporciona alguna orientación para cuándo debe utilizarse cada uno.  
  
|Método|cuándo implementar|  
|------------|------------------------|  
|Utilice una clase parcial existente del administrador de eventos|Si el evento que desea suscribirse tiene <xref:System.Windows.WeakEventManager>correspondiente, utilice el administrador parcial existente del evento.  Para obtener una lista de administradores débiles de eventos que se incluye con WPF, vea la jerarquía de herencia en la clase de <xref:System.Windows.WeakEventManager> .  Observe, sin embargo, que hay relativamente pocos administradores débiles de eventos incluidos en WPF, lo que probablemente necesitará elegir uno de los otros enfoques.|  
|Utilice una clase parcial genérica de administrador de evento|Utilice <xref:System.Windows.WeakEventManager%602> genérico cuando <xref:System.Windows.WeakEventManager> existente no está disponible, desea una manera fácil de implementar, y no le preocupa la eficacia.  <xref:System.Windows.WeakEventManager%602> genérico es menos eficaz que un existente o un administrador débil de eventos personalizados.  Por ejemplo, la clase genérica hace más reflexión para detectar el evento dado el nombre del evento.  Además, el código para registrar el evento con <xref:System.Windows.WeakEventManager%602> genérico es más detallado que mediante un existente o <xref:System.Windows.WeakEventManager>personalizado.|  
|Cree una clase parcial personalizada del administrador de eventos|Cree <xref:System.Windows.WeakEventManager> personalizado cuando se <xref:System.Windows.WeakEventManager> existente no está disponible y desea que la mejor eficacia.  Mediante un generador <xref:System.Windows.WeakEventManager> suscribirse a un evento será más eficaz, pero se incurre en el costo de escribir más código al principio.|  
  
 Las secciones siguientes describen cómo implementar el modelo de evento débil.  Para los propósitos de este tutorial, el evento para suscribirse tiene las siguientes características.  
  
-   el nombre de evento es `SomeEvent`.  
  
-   El evento es desencadenado por la clase de `EventSource` .  
  
-   el controlador de eventos ha escrito: `SomeEventEventHandler` \(o `EventHandler<SomeEventEventArgs>`\).  
  
-   El evento pasa un parámetro de `SomeEventEventArgs` escriba en los controladores de eventos.  
  
### Mediante una clase de administrador de evento existente Parciales  
  
1.  Busque un administrador parcial existente del evento.  
  
     Para obtener una lista de administradores débiles de eventos que se incluye con WPF, vea la jerarquía de herencia en la clase de <xref:System.Windows.WeakEventManager> .  
  
2.  Utilice el nuevo administrador de evento débil en lugar de vinculación normal del evento.  
  
     Por ejemplo, si el código usa el modelo siguiente para suscribirse a un evento:  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Cambiar el modelo siguiente:  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     De igual forma, si el código usa el modelo siguiente para cancelar la suscripción a un evento:  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     Cambiar el modelo siguiente:  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### Mediante la clase de administrador de evento genérica Parciales  
  
1.  Utilice la clase genérica de <xref:System.Windows.WeakEventManager%602> en lugar de vinculación normal del evento.  
  
     Cuando se utiliza <xref:System.Windows.WeakEventManager%602> para registrar los agentes de escucha de eventos, se proporciona el origen y <xref:System.EventArgs> escritos como los parámetros de tipo a la clase y llama a <xref:System.Windows.WeakEventManager%602.AddHandler%2A> tal y como se muestra en el código siguiente:  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### Crear una clase de administrador de evento débil  
  
1.  Copie la plantilla siguiente de clase al proyecto.  
  
     Esta clase se hereda de la clase <xref:System.Windows.WeakEventManager>.  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2.  reemplace el nombre de `SomeEventWeakEventManager` con el propio nombre.  
  
3.  Reemplace los tres nombres descritos previamente con nombres correspondientes para el evento.  \(`SomeEvent`, `EventSource`, y `SomeEventEventArgs`\)  
  
4.  Establezca la visibilidad \(pública\/interna o private\) de la clase parcial del administrador de eventos a la misma visibilidad que el evento administra.  
  
5.  Utilice el nuevo administrador de evento débil en lugar de vinculación normal del evento.  
  
     Por ejemplo, si el código usa el modelo siguiente para suscribirse a un evento:  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Cambiar el modelo siguiente:  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     De igual forma, si el código usa el modelo siguiente para cancelar la suscripción a un evento:  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     Cambiar el modelo siguiente:  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## Vea también  
 <xref:System.Windows.WeakEventManager>   
 <xref:System.Windows.IWeakEventListener>   
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)