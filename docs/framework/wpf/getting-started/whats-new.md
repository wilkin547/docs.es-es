---
title: "Novedades de WPF versi&#243;n 4.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Windows Presentation Foundation, lo nuevo"
  - "WPF, lo nuevo"
ms.assetid: db086ae4-70bb-4862-95db-2eaca5216bc3
caps.latest.revision: 55
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 55
---
# Novedades de WPF versi&#243;n 4.5
<a name="introduction"></a> Este tema contiene información sobre las características nuevas y mejoradas de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] versión 4.5.  
  
 Este tema contiene las siguientes secciones:  
  
-   [Control de la cinta de opciones](#ribbon_control)  
  
-   [Rendimiento mejorado para mostrar conjuntos grandes de datos agrupados](#grouped_virtualization)  
  
-   [Nuevas características para el VirtualizingPanel](#VirtualizingPanel)  
  
-   [El enlace a las propiedades estáticas](#static_properties)  
  
-   [Colecciones de acceso en los subprocesos de la interfaz no de interfaz de usuario](#xthread_access)  
  
-   [Sincrónicamente y Permite que validan datos](#INotifyDataErrorInfo)  
  
-   [Actualizar automáticamente el origen de un enlace de datos](#delay)  
  
-   [El enlace a los tipos que implementan ICustomTypeProvider](#ICustomTypeProvider)  
  
-   [Recuperar información de enlace de datos de una expresión de enlace](#binding_state)  
  
-   [Comprobar el un objeto válido de DataContext](#DisconnectedSource)  
  
-   [Colocando datos como valores de datos cambie \(el cálculo de referencias Live\)](#live_shaping)  
  
-   [Compatibilidad mejorada con Establishing una referencia de Débil a un evento](#weak_event_pattern)  
  
-   [Nuevos métodos para la clase del distribuidor](#async)  
  
-   [Extensiones de marcado para los eventos](#events_markup_extenions)  
  
<a name="ribbon_control"></a>   
## Control de la cinta de opciones  
 Las naves de WPF 4,5 con <xref:System.Windows.Controls.Ribbon.Ribbon> controlan que hospeda una barra de herramientas de acceso rápido, un menú de aplicación, y pestañas.  Para obtener más información, vea [Información general sobre la cinta de opciones](../Topic/Ribbon%20Overview.md).  
  
<a name="grouped_virtualization"></a>   
## Rendimiento mejorado para mostrar conjuntos grandes de datos agrupados  
 La virtualización de la interfaz de usuario aparece cuando un subconjunto de elementos de \(UI\) de se representa la interfaz de usuario de un número mayor de elementos de datos basándose en los elementos que están visibles en la pantalla.  <xref:System.Windows.Controls.VirtualizingPanel> define la propiedad asociada <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> que habilita la virtualización de la interfaz de usuario para los datos agrupados.  Para obtener más información sobre los datos de agrupación, vea Cómo: Ordenar y agrupar los datos Mediante una vista en XAML.  Para obtener más información sobre la virtualización de datos agrupados, vea la propiedad asociada <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> .  
  
<a name="VirtualizingPanel"></a>   
## Nuevas características para el VirtualizingPanel  
  
1.  Puede especificar si <xref:System.Windows.Controls.VirtualizingPanel>, como <xref:System.Windows.Controls.VirtualizingStackPanel>, muestra elementos parciales mediante la propiedad asociada <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> .  Si <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> se establece en <xref:System.Windows.Controls.ScrollUnit>, <xref:System.Windows.Controls.VirtualizingPanel> mostrará sólo los elementos que están completamente visible.  Si <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> se establece en <xref:System.Windows.Controls.ScrollUnit>, <xref:System.Windows.Controls.VirtualizingPanel> puede mostrar elementos parcialmente visible.  
  
2.  Puede especificar el tamaño de caché antes y después de la ventanilla cuando <xref:System.Windows.Controls.VirtualizingPanel> está virtualizar mediante la propiedad asociada <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A> .  Caché es la cantidad de espacio encima o debajo de la ventanilla donde los elementos no se virtualizan.  Si utiliza la memoria caché evitar generar elementos de interfaz de usuario como se desplazan en la vista puede mejorar el rendimiento.  La memoria caché se rellena con una prioridad más baja de para no esté responde durante la operación.  La propiedad de <xref:System.Windows.Controls.VirtualizingPanel.CacheLengthUnit%2A?displayProperty=fullName> determina la unidad de medida utilizada por <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A?displayProperty=fullName>.  
  
<a name="static_properties"></a>   
## El enlace a las propiedades estáticas  
 Puede utilizar las propiedades estáticas como origen de un enlace de datos.  El motor de enlace de datos reconoce cuando cambie el valor de propiedad si se produce un evento estático.  Por ejemplo, si la clase `SomeClass` define `MyProperty`propiedad denominada estático, `SomeClass` puede definir un evento estático que se provoca cuando el valor de `MyProperty` cambia.  El evento estático puede utilizar cualquiera de las signaturas siguientes.  
  
-   `public static event EventHandler MyPropertyChanged;`  
  
-   `public static event EventHandler<PropertyChangedEventArgs> StaticPropertyChanged;`  
  
 Observe que en el primer caso, expuestos por la clase un evento estático denominado *PropertyName*`Changed` que pasa <xref:System.EventArgs> el controlador de eventos.  En el segundo, la clase expone un evento estático denominado `StaticPropertyChanged` que pasa <xref:System.ComponentModel.PropertyChangedEventArgs> el controlador de eventos.  Una clase que implementa la propiedad estática puede elegir para generar notificaciones de propiedad\- cambios mediante cualquier método.  
  
<a name="xthread_access"></a>   
## Colecciones de acceso en los subprocesos de la interfaz no de interfaz de usuario  
 WPF permite tener acceso y modificar a las recolecciones de datos en subprocesos distinto del que creó la colección.  Esto permite utilizar un subproceso de fondo para recibir datos de un origen externo, como una base de datos, y muestra los datos en el subproceso de la interfaz de usuario.  Mediante otro subproceso para modificar la colección, la interfaz de usuario permanece receptiva a la interacción del usuario.  
  
<a name="INotifyDataErrorInfo"></a>   
## Sincrónicamente y Permite que validan datos  
 La interfaz de <xref:System.ComponentModel.INotifyDataErrorInfo> permite que las clases de entidad de datos para aplicar reglas de validación personalizadas y exponer los resultados de la validación de forma asincrónica.  Esta interfaz también admite objetos error personalizado, varios errores por propiedad, errores de la cruce\- propiedad, y errores de entidad\- nivel.  Para obtener más información, vea <xref:System.ComponentModel.INotifyDataErrorInfo>.  
  
<a name="delay"></a>   
## Actualizar automáticamente el origen de un enlace de datos  
 Si utiliza un enlace de datos para actualizar un origen de datos, puede utilizar la propiedad de <xref:System.Windows.Data.BindingBase.Delay%2A> para especificar una cantidad de tiempo de pasar cuando cambie la propiedad del destino antes de las actualizaciones del origen.  Por ejemplo, suponga que tiene <xref:System.Windows.Controls.Slider> que tiene el enlace de datos bidireccional de la propiedad de <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> a una propiedad de un objeto de datos y la propiedad de <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> se establece en <xref:System.Windows.Data.UpdateSourceTrigger>.  En este ejemplo, cuando el usuario mueve <xref:System.Windows.Controls.Slider>, el origen para cada píxel que <xref:System.Windows.Controls.Slider> mueve.  El objeto de origen normalmente necesita el valor del control deslizante sólo cuando <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> slider detiene el cambiar.  Para impedir actualizar el origen demasiado a menudo, utilice <xref:System.Windows.Data.BindingBase.Delay%2A> para especificar que el origen no debe actualizarse hasta que transcurra un período de tiempo después de que el control detenga el desplazamiento.  
  
<a name="ICustomTypeProvider"></a>   
## El enlace a los tipos que implementan ICustomTypeProvider  
 WPF admite el enlace de datos a los objetos que implementan <xref:System.Reflection.ICustomTypeProvider>, también conocidos como tipos personalizados.  Puede utilizar tipos personalizados en los casos siguientes.  
  
1.  Como <xref:System.Windows.PropertyPath> en un enlace de datos.  Por ejemplo, la propiedad de <xref:System.Windows.Data.Binding.Path%2A> de <xref:System.Windows.Data.Binding> puede hacer referencia a una propiedad de un tipo personalizado.  
  
2.  Como valor de la propiedad de <xref:System.Windows.DataTemplate.DataType%2A> .  
  
3.  Como tipo que determina las columnas generadas automáticamente en <xref:System.Windows.Controls.DataGrid>.  
  
<a name="binding_state"></a>   
## Recuperar información de enlace de datos de una expresión de enlace  
 En algunos casos, podría obtener <xref:System.Windows.Data.BindingExpression> de <xref:System.Windows.Data.Binding> y necesita información sobre los objetos de origen y de destino del enlace.  Los nuevos API se han agregado para permitirle obtener el objeto de origen o de destino o la propiedad asociada.  Cuando tiene <xref:System.Windows.Data.BindingExpression>, utilice las API siguientes para obtener información sobre el destino y el origen.  
  
|Para encontrar esta opción de enlace|Utilice esta API|  
|------------------------------------------|----------------------|  
|El objeto de destino|<xref:System.Windows.Data.BindingExpressionBase.Target%2A?displayProperty=fullName>|  
|La propiedad de destino|<xref:System.Windows.Data.BindingExpressionBase.TargetProperty%2A?displayProperty=fullName>|  
|El objeto de origen|<xref:System.Windows.Data.BindingExpression.ResolvedSource%2A?displayProperty=fullName>|  
|La propiedad de origen|<xref:System.Windows.Data.BindingExpression.ResolvedSourcePropertyName%2A?displayProperty=fullName>|  
|Si <xref:System.Windows.Data.BindingExpression> pertenece a <xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingExpressionBase.BindingGroup%2A?displayProperty=fullName>|  
|El propietario de <xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingGroup.Owner%2A>|  
  
<a name="DisconnectedSource"></a>   
## Comprobar el un objeto válido de DataContext  
 Hay casos donde <xref:System.Windows.FrameworkElement.DataContext%2A> de un contenedor de elementos en <xref:System.Windows.Controls.ItemsControl> esté desconectado.  Un contenedor de elemento es el elemento de la interfaz de usuario que muestra un elemento en <xref:System.Windows.Controls.ItemsControl>.  Cuando <xref:System.Windows.Controls.ItemsControl> está enlazado a datos con una colección, un contenedor de elemento se genera para cada elemento.  En algunos casos, los contenedores de elementos se quitan del árbol visual.  Dos casos típicos donde se quita un contenedor de elemento son cuando un elemento se quita de la colección subyacente y cuando la virtualización está habilitada en <xref:System.Windows.Controls.ItemsControl>.  En estos casos, la propiedad de <xref:System.Windows.FrameworkElement.DataContext%2A> de contenedor de elemento se establecerá el objeto centinela devuelto por la propiedad estática de <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A?displayProperty=fullName> .  Debe comprobar si <xref:System.Windows.FrameworkElement.DataContext%2A> sea igual al objeto de <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A> antes de tener acceso <xref:System.Windows.FrameworkElement.DataContext%2A> de un contenedor de elementos.  
  
<a name="live_shaping"></a>   
## Colocando datos como valores de datos cambie \(el cálculo de referencias Live\)  
 Una recolección de datos puede agrupar, ordenar, filtrar o.  WPF 4,5 habilita los datos que se reorganizarán cuando se modifican los datos.  Por ejemplo, supongamos que una aplicación utiliza <xref:System.Windows.Controls.DataGrid> para mostrar acciones en un mercado de acciones y las acciones se ordenan por el valor común.  Si la ordenación activa está habilitada en <xref:System.Windows.Data.CollectionView>de las acciones, la posición de una acción en <xref:System.Windows.Controls.DataGrid> se mueve cuando el valor de acción se convierte en mayor o menor que el valor de otra acción.  Para obtener más información, vea la interfaz <xref:System.ComponentModel.ICollectionViewLiveShaping>.  
  
<a name="weak_event_pattern"></a>   
## Compatibilidad mejorada con Establishing una referencia de Débil a un evento  
 Implementar el modelo de evento débil resulta más fácil ahora porque los suscriptores a eventos pueden participar en él sin implementar una interfaz adicional.  La clase genérica de <xref:System.Windows.WeakEventManager> también permite suscriptores para participar en el modelo de evento débil si <xref:System.Windows.WeakEventManager> dedicado no existe para algún evento.  Para obtener más información, vea [Modelos de evento débil](../../../../docs/framework/wpf/advanced/weak-event-patterns.md).  
  
<a name="async"></a>   
## Nuevos métodos para la clase del distribuidor  
 La clase del distribuidor define los nuevos métodos para sincrónico y las operaciones asincrónicas.  El método sincrónico de <xref:System.Windows.Threading.Dispatcher.Invoke%2A> define las sobrecargas que toman un parámetro de <xref:System.Action> o de <xref:System.Func%601> .  El nuevo método asincrónico, <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>, también se <xref:System.Action> o <xref:System.Func%601> como parámetro de devolución de llamada y devuelve <xref:System.Windows.Threading.DispatcherOperation> o <xref:System.Windows.Threading.DispatcherOperation%601>.  Las clases de <xref:System.Windows.Threading.DispatcherOperation> y de <xref:System.Windows.Threading.DispatcherOperation%601> definen una propiedad de <xref:System.Threading.Tasks.Task> .  Cuando se llama a <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>, puede utilizar la palabra clave de `await` con <xref:System.Windows.Threading.DispatcherOperation> o <xref:System.Threading.Tasks.Task>asociado.  Si necesita esperar sincrónicamente <xref:System.Threading.Tasks.Task> devuelto por <xref:System.Windows.Threading.DispatcherOperation> o <xref:System.Windows.Threading.DispatcherOperation%601>, llame al método de extensión de <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> .  La llamada <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=fullName> dará como resultado un interbloqueo si la operación se pone en cola en un subproceso de llamada.  Para obtener más información sobre cómo utilizar <xref:System.Threading.Tasks.Task> para realizar operaciones asincrónicas, vea [Paralelismo de tareas \(Task Parallel Library\)](../../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md).  
  
<a name="events_markup_extenions"></a>   
## Extensiones de marcado para los eventos  
 Extensiones de marcado de la de WPF 4,5 para los eventos.  Mientras WPF no define una extensión de marcado que se utilizará para los eventos, los terceros pueden crear una extensión de marcado que se puede utilizar con eventos.  
  
## Vea también  
 [Novedades de .NET Framework](../../../../docs/framework/whats-new/index.md)