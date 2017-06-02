---
title: "Caching in UI Automation Clients | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "UI Automation caching in clients"
  - "caching, UI Automation clients"
ms.assetid: 94c15031-4975-43cc-bcd5-c9439ed21c9c
caps.latest.revision: 24
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 24
---
# Caching in UI Automation Clients
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se presenta el almacenamiento en caché de los patrones de control y las propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
 En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], almacenamiento en caché implica la captura previa de datos. Así, es posible acceder a los datos sin necesidad de más comunicación entre procesos. Normalmente, el almacenamiento en caché se utiliza en aplicaciones cliente de Automatización de la interfaz de usuario para recuperar los patrones de control y las propiedades de forma masiva. La información se recupera después desde la caché según sea necesario. La aplicación actualiza periódicamente la caché, normalmente en respuesta a eventos que indican que algo en [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] ha cambiado.  
  
 Las ventajas del almacenamiento en caché se aprecian mejor con controles y controles personalizados de [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] que tengan proveedores de Automatización de la interfaz de usuario de lado servidor. Las ventajas son menores si se accede a proveedores de lado cliente, como los proveedores predeterminados de los controles de [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)].  
  
 El almacenamiento en caché se produce cuando la aplicación activa un elemento <xref:System.Windows.Automation.CacheRequest> y después utiliza cualquier método o propiedad que devuelva un elemento <xref:System.Windows.Automation.AutomationElement>; por ejemplo, <xref:System.Windows.Automation.AutomationElement.FindFirst%2A>, <xref:System.Windows.Automation.AutomationElement.FindAll%2A>. Los métodos de la clase <xref:System.Windows.Automation.TreeWalker> son una excepción; el almacenamiento en caché solo se realiza si se especifica un elemento <xref:System.Windows.Automation.CacheRequest> como un parámetro \(por ejemplo, <xref:System.Windows.Automation.TreeWalker.GetFirstChild%28System.Windows.Automation.AutomationElement%2CSystem.Windows.Automation.CacheRequest%29?displayProperty=fullName>\).  
  
 El almacenamiento en caché también se produce al suscribirse a un evento mientras un elemento <xref:System.Windows.Automation.CacheRequest> está activo. El elemento <xref:System.Windows.Automation.AutomationElement> que se pasa al controlador de eventos como el origen de un evento contiene los patrones y las propiedades almacenadas en caché que especifica el elemento <xref:System.Windows.Automation.CacheRequest> original. Los cambios realizados en el elemento <xref:System.Windows.Automation.CacheRequest> después de suscribirse al evento no tienen ningún efecto.  
  
 Los patrones de control y las propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] de un elemento pueden almacenarse en caché.  
  
<a name="Options_for_Caching"></a>   
## Opciones de almacenamiento en caché  
 <xref:System.Windows.Automation.CacheRequest> especifica las siguientes opciones para el almacenamiento en caché.  
  
<a name="Properties_to_Cache"></a>   
### Propiedades que se almacenarán en caché  
 Puede especificar las propiedades que se almacenarán en caché mediante una llamada a <xref:System.Windows.Automation.CacheRequest.Add%28System.Windows.Automation.AutomationProperty%29> por cada propiedad antes de activar la solicitud.  
  
<a name="Control_Patterns_to_Cache"></a>   
### Patrones de control que se almacenarán en caché  
 Puede especificar los patrones de control que se almacenarán en caché mediante una llamada a <xref:System.Windows.Automation.CacheRequest.Add%28System.Windows.Automation.AutomationPattern%29> por cada patrón antes de activar la solicitud. Cuando un patrón se almacena en caché, sus propiedades no se almacenan automáticamente; debe especificar las propiedades que quiera que se almacenen en caché mediante <xref:System.Windows.Automation.CacheRequest.Add%2A?displayProperty=fullName>.  
  
<a name="Scope_of_the_Caching"></a>   
### Ámbito y filtrado del almacenamiento en caché  
 Puede especificar los elementos cuyos patrones y propiedades quiera almacenar en caché mediante el establecimiento de la propiedad <xref:System.Windows.Automation.CacheRequest.TreeScope%2A?displayProperty=fullName> antes de activar la solicitud. El ámbito es relativo a los elementos que se recuperan mientras la solicitud está activa. Por ejemplo, si solo se define <xref:System.Windows.Automation.TreeScope> y después se recupera un elemento <xref:System.Windows.Automation.AutomationElement>, los patrones y las propiedades de los elementos secundarios de ese elemento se almacenan en caché, pero no sucede lo mismo con los del propio elemento. Para garantizar que se realiza el almacenamiento en caché para el propio elemento recuperado, debe incluir <xref:System.Windows.Automation.TreeScope> en la propiedad <xref:System.Windows.Automation.CacheRequest.TreeScope%2A>. No es posible establecer el ámbito en <xref:System.Windows.Automation.TreeScope> o <xref:System.Windows.Automation.TreeScope>. Sin embargo, es posible almacenar en caché un elemento primario cuando se almacena un elemento secundario en caché; consulte la sección Recuperación de elementos primarios y secundarios almacenados en caché de este tema.  
  
 El alcance del almacenamiento en caché también se ve afectado por la propiedad <xref:System.Windows.Automation.CacheRequest.TreeFilter%2A?displayProperty=fullName>. De forma predeterminada, el almacenamiento en caché se realiza solo para los elementos que aparecen en la vista de control del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Sin embargo, puede cambiar esta propiedad para aplicar el almacenamiento en caché a todos los elementos o solo a los que aparecen en la vista de contenido.  
  
<a name="Strength_of_the_Element_References"></a>   
### Solidez de las referencias de elemento  
 De forma predeterminada, cuando se recupera un elemento <xref:System.Windows.Automation.AutomationElement>, se tiene acceso a todas las propiedades y los patrones de ese elemento, incluidos los que no se almacenaron en caché. Sin embargo, para obtener una mayor eficacia, puede especificar que la referencia al elemento solo haga referencia a los datos almacenados en caché si establece la propiedad <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> del elemento <xref:System.Windows.Automation.CacheRequest> en <xref:System.Windows.Automation.AutomationElementMode>. En este caso, no tiene acceso a los patrones y propiedades no almacenados en caché de los elementos recuperados. Esto significa que no se puede acceder a las propiedades a través de <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> o la propiedad `Current` de <xref:System.Windows.Automation.AutomationElement>, ni con ningún patrón de control; tampoco se puede recuperar un patrón mediante <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> o <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>. En los patrones almacenados en caché, puede llamar a métodos que recuperen propiedades de matriz, como <xref:System.Windows.Automation.SelectionPattern.SelectionPatternInformation.GetSelection%2A?displayProperty=fullName>, pero no puede llamar a ninguno que realice acciones en el control, como <xref:System.Windows.Automation.InvokePattern.Invoke%2A?displayProperty=fullName>.  
  
 Un ejemplo de una aplicación que podría no necesitar referencias completas a objetos es un lector de pantalla, que capturaría previamente las propiedades <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A> y <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> de los elementos de una ventana, pero no necesitaría los propios objetos <xref:System.Windows.Automation.AutomationElement>.  
  
<a name="Activating_the_CacheRequest"></a>   
## Activación de CacheRequest  
 El almacenamiento en caché solo se realiza cuando se recuperan los objetos <xref:System.Windows.Automation.AutomationElement> mientras un elemento <xref:System.Windows.Automation.CacheRequest> está activo para el subproceso actual. Hay dos formas de activar un elemento <xref:System.Windows.Automation.CacheRequest>.  
  
 La manera habitual es llamar a <xref:System.Windows.Automation.CacheRequest.Activate%2A>. Este método devuelve un objeto que implementa <xref:System.IDisposable>. La solicitud permanecerá activa mientras exista el objeto <xref:System.IDisposable>. La manera más fácil de controlar la duración del objeto es incluir la llamada dentro de un bloque `using` \([!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)]\) o `Using` \([!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]\). Esto garantiza que la solicitud se extraerá de la pila, aunque se produzca una excepción.  
  
 Otra forma, que resulta útil cuando se quieren anidar solicitudes de almacenamiento en caché, es llamar a <xref:System.Windows.Automation.CacheRequest.Push%2A>. Esto coloca la solicitud en una pila y la activa. La solicitud permanece activa hasta que se quita de la pila mediante <xref:System.Windows.Automation.CacheRequest.Pop%2A>. La solicitud pasa a estar temporalmente inactiva si se inserta otra solicitud en la pila; solo la solicitud superior de la pila está activa.  
  
<a name="Retrieving_Cached_Properties"></a>   
## Recuperación de propiedades almacenadas en caché  
 Puede recuperar las propiedades almacenadas en caché de un elemento mediante los siguientes métodos y propiedades.  
  
-   <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>  
  
-   <xref:System.Windows.Automation.AutomationElement.Cached%2A>  
  
 Se produce una excepción si la propiedad solicitada no está en la caché.  
  
 <xref:System.Windows.Automation.AutomationElement.Cached%2A>, como <xref:System.Windows.Automation.AutomationElement.Current%2A>, expone propiedades individuales como miembros de una estructura. Sin embargo, no es necesario recuperar esta estructura; puede acceder a las propiedades individuales directamente. Por ejemplo, la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A> se puede obtener de `element.Cached.Name`, donde `element` es un elemento <xref:System.Windows.Automation.AutomationElement>.  
  
<a name="Retrieving_Cached_Control_Patterns"></a>   
## Recuperación de patrones de control almacenados en caché  
 Puede recuperar los patrones de control almacenados en caché de un elemento mediante los siguientes métodos.  
  
-   <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A>  
  
-   <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A>  
  
 Si el patrón no está almacenado en caché, <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> produce una excepción y <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> devuelve `false`.  
  
 Puede recuperar las propiedades almacenadas en caché de un patrón de control mediante la propiedad `Cached` del objeto de patrón. También puede recuperar los valores actuales mediante la propiedad `Current`, pero solo si no se especificó <xref:System.Windows.Automation.AutomationElementMode> cuando se recuperó <xref:System.Windows.Automation.AutomationElement>. \(<xref:System.Windows.Automation.AutomationElementMode> es el valor predeterminado y permite el acceso a los valores actuales\).  
  
<a name="Retrieving_Cached_Children_and_Parents"></a>   
## Recuperación de elementos primarios y secundarios almacenados en caché  
 Cuando se recupera un elemento <xref:System.Windows.Automation.AutomationElement> y se solicita almacenamiento en caché para los elementos secundarios de ese elemento mediante la propiedad <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> de la solicitud, es posible obtener posteriormente los elementos secundarios desde la propiedad <xref:System.Windows.Automation.AutomationElement.CachedChildren%2A> del elemento que recuperó.  
  
 Si <xref:System.Windows.Automation.TreeScope> se incluyó en el ámbito de la solicitud de caché, el elemento raíz de la solicitud estará posteriormente disponible desde la propiedad <xref:System.Windows.Automation.AutomationElement.CachedParent%2A> de cualquiera de los elementos secundarios.  
  
> [!NOTE]
>  No se pueden almacenar en caché los elementos primarios o antecesores del elemento raíz de la solicitud.  
  
<a name="Updating_the_Cache"></a>   
## Actualización de la caché  
 La caché solo es válida siempre y cuando no cambie nada en el elemento [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. La aplicación es responsable de actualizar la caché, normalmente como respuesta a eventos.  
  
 Si se suscribe a un evento mientras un elemento <xref:System.Windows.Automation.CacheRequest> está activo, obtendrá un elemento <xref:System.Windows.Automation.AutomationElement> con una caché actualizada como origen del evento cada vez que se llame a su delegado de controlador de eventos. También puede actualizar la información almacenada en caché de un elemento con una llamada a <xref:System.Windows.Automation.AutomationElement.GetUpdatedCache%2A>. Puede pasar el elemento <xref:System.Windows.Automation.CacheRequest> original para actualizar toda la información que se almacenó previamente en caché.  
  
 La actualización de la caché no modifica las propiedades de las referencias <xref:System.Windows.Automation.AutomationElement> existentes.  
  
## Vea también  
 [UI Automation Events for Clients](../../../docs/framework/ui-automation/ui-automation-events-for-clients.md)   
 [Use Caching in UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)   
 [FetchTimer Sample](http://msdn.microsoft.com/es-es/5b7d3294-de22-4f24-b2d6-d4785a304b90)