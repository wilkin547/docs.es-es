---
title: Novedades de WPF versión 4.5
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Presentation Foundation [WPF], what's new
- WPF [WPF], what's new
ms.assetid: db086ae4-70bb-4862-95db-2eaca5216bc3
ms.openlocfilehash: 8eff8da7746047c450b2e23af63d43b13f3b970c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746919"
---
# <a name="whats-new-in-wpf-version-45"></a>Novedades de WPF versión 4.5
<a name="introduction"></a>Este tema contiene información acerca de las características nuevas y mejoradas de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] versión 4,5.  
  
 Este tema contiene las siguientes secciones:  
  
- [Control Ribbon](#ribbon_control)  
  
- [Rendimiento mejorado al mostrar grandes conjuntos de datos agrupados](#grouped_virtualization)  
  
- [Nuevas características para VirtualizingPanel](#VirtualizingPanel)  
  
- [Enlace a propiedades estáticas](#static_properties)  
  
- [Acceso a colecciones en subprocesos que no son de la interfaz de usuario](#xthread_access)  
  
- [Validación sincrónica y asincrónica de datos](#INotifyDataErrorInfo)  
  
- [Actualización automática del origen de un enlace de datos](#delay)  
  
- [Enlace a tipos que implementan ICustomTypeProvider](#ICustomTypeProvider)  
  
- [Recuperación de información sobre el enlace de datos de una expresión de enlace](#binding_state)  
  
- [Búsqueda de un objeto DataContext válido](#DisconnectedSource)  
  
- [Reposición de los datos a medida que cambian sus valores (modelado dinámico)](#live_shaping)  
  
- [Compatibilidad mejorada para establecer una referencia débil a un evento](#weak_event_pattern)  
  
- [Nuevos métodos para la clase Dispatcher](#async)  
  
- [Extensiones de marcado para eventos](#events_markup_extenions)  
  
<a name="ribbon_control"></a>   
## <a name="ribbon-control"></a>Control Ribbon  
 WPF 4,5 incluye un control de <xref:System.Windows.Controls.Ribbon.Ribbon> que hospeda una barra de herramientas de acceso rápido, un menú de aplicación y pestañas.  Para más información, consulte [Información general sobre la cinta](/visualstudio/vsto/ribbon-overview).  
  
<a name="grouped_virtualization"></a>   
## <a name="improved-performance-when-displaying-large-sets-of-grouped-data"></a>Rendimiento mejorado al mostrar grandes conjuntos de datos agrupados  
 La virtualización de la interfaz de usuario (UI) se produce cuando un subconjunto de sus elementos se generan a partir de un mayor número de elementos de datos en función de qué elementos estén visibles en la pantalla. El <xref:System.Windows.Controls.VirtualizingPanel> define el <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> propiedad adjunta que habilita la virtualización de la interfaz de usuario para los datos agrupados.  Para más información acerca del agrupamiento de datos, consulte Cómo: Ordenar y agrupar datos mediante una vista en XAML.  Para obtener más información sobre la virtualización de datos agrupados, vea la <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> propiedad adjunta.  
  
<a name="VirtualizingPanel"></a>   
## <a name="new-features-for-the-virtualizingpanel"></a>Nuevas características para VirtualizingPanel  
  
1. Puede especificar si un <xref:System.Windows.Controls.VirtualizingPanel>, como el <xref:System.Windows.Controls.VirtualizingStackPanel>, muestra elementos parciales mediante el <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> propiedad adjunta. Si <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> se establece en <xref:System.Windows.Controls.ScrollUnit.Item>, el <xref:System.Windows.Controls.VirtualizingPanel> solo mostrará los elementos que estén totalmente visibles. Si <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> se establece en <xref:System.Windows.Controls.ScrollUnit.Pixel>, el <xref:System.Windows.Controls.VirtualizingPanel> puede mostrar elementos parcialmente visibles.  
  
2. Puede especificar el tamaño de la memoria caché antes y después de la ventanilla cuando se está virtualizando el <xref:System.Windows.Controls.VirtualizingPanel> mediante el <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A> propiedad adjunta.  La memoria caché es la cantidad de espacio encima o debajo de la ventanilla en el que no se virtualizarán elementos.  Usar una memoria caché para evitar que se generen elementos de UI a medida que van apareciendo por desplazamiento puede mejorar el rendimiento. La memoria caché se rellena con menor prioridad para que la aplicación no deje de responder durante la operación. La propiedad <xref:System.Windows.Controls.VirtualizingPanel.CacheLengthUnit%2A?displayProperty=nameWithType> determina la unidad de medida que usa <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A?displayProperty=nameWithType>.  
  
<a name="static_properties"></a>   
## <a name="binding-to-static-properties"></a>Enlace a propiedades estáticas  
 Puede usar propiedades estáticas como origen de un enlace de datos. El motor de enlace de datos reconoce cuándo cambia el valor de la propiedad si se genera un evento estático.  Por ejemplo, si la clase `SomeClass` define una propiedad estática denominada `MyProperty`, `SomeClass` puede definir un evento estático que se genera cuando el valor de `MyProperty` cambia.  El evento estático puede utilizar cualquiera de las siguientes firmas.  
  
- `public static event EventHandler MyPropertyChanged;`  
  
- `public static event EventHandler<PropertyChangedEventArgs> StaticPropertyChanged;`  
  
 Tenga en cuenta que en el primer caso, la clase expone un evento estático denominado *PropertyName*`Changed` que pasa <xref:System.EventArgs> al controlador de eventos.  En el segundo caso, la clase expone un evento estático denominado `StaticPropertyChanged` que pasa <xref:System.ComponentModel.PropertyChangedEventArgs> al controlador de eventos. Una clase que implementa la propiedad estática puede elegir generar notificaciones de cambio de propiedad mediante cualquiera de estos métodos.  
  
<a name="xthread_access"></a>   
## <a name="accessing-collections-on-non-ui-threads"></a>Acceso a colecciones en subprocesos que no son de la interfaz de usuario  
 WPF permite acceder a colecciones de datos en subprocesos distintos del que creó la colección y modificarlas.  Esto le permite usar un subproceso en segundo plano para recibir datos de un origen externo, como una base de datos, y mostrar los datos en el subproceso de interfaz de usuario.  Si usa otro subproceso para modificar la colección, la interfaz de usuario sigue respondiendo a la interacción del usuario.  
  
<a name="INotifyDataErrorInfo"></a>   
## <a name="synchronously-and-asynchronously-validating-data"></a>Validación sincrónica y asincrónica de datos  
 La interfaz <xref:System.ComponentModel.INotifyDataErrorInfo> permite a las clases de entidad de datos implementar reglas de validación personalizadas y exponer los resultados de la validación de forma asincrónica. Además, esta interfaz admite objetos de error personalizados, varios errores por propiedad, errores entre propiedades y errores de nivel de entidad.  Para más información, consulte <xref:System.ComponentModel.INotifyDataErrorInfo>.  
  
<a name="delay"></a>   
## <a name="automatically-updating-the-source-of-a-data-binding"></a>Actualización automática del origen de un enlace de datos  
 Si usa un enlace de datos para actualizar un origen de datos, puede usar la propiedad <xref:System.Windows.Data.BindingBase.Delay%2A> para especificar una cantidad de tiempo que debe transcurrir después de que la propiedad cambie en el destino antes de que se actualice el origen.  Por ejemplo, supongamos que tiene una <xref:System.Windows.Controls.Slider> que tiene sus datos de propiedad <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> enlazados en dos sentidos a una propiedad de un objeto de datos y la propiedad <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> está establecida en <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.  En este ejemplo, cuando el usuario mueve el <xref:System.Windows.Controls.Slider>, el origen se actualiza para cada píxel que mueve el <xref:System.Windows.Controls.Slider>.  Normalmente, el objeto de origen solo necesita el valor del control deslizante cuando el <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> del control deslizante deja de cambiar.  Para evitar que se actualice el origen con demasiada frecuencia, utilice <xref:System.Windows.Data.BindingBase.Delay%2A> para especificar que el origen no debe actualizarse hasta que transcurra un tiempo determinado después de que el control de posición deje de moverse.  
  
<a name="ICustomTypeProvider"></a>   
## <a name="binding-to-types-that-implement-icustomtypeprovider"></a>Enlace a tipos que implementan ICustomTypeProvider  
 WPF admite el enlace de datos a objetos que implementan <xref:System.Reflection.ICustomTypeProvider>, también conocidos como tipos personalizados.  Puede utilizar tipos personalizados en los casos siguientes.  
  
1. Como <xref:System.Windows.PropertyPath> en un enlace de datos. Por ejemplo, la propiedad <xref:System.Windows.Data.Binding.Path%2A> de una <xref:System.Windows.Data.Binding> puede hacer referencia a una propiedad de un tipo personalizado.  
  
2. Como valor de la propiedad <xref:System.Windows.DataTemplate.DataType%2A>.  
  
3. Como un tipo que determina las columnas generadas automáticamente en una <xref:System.Windows.Controls.DataGrid>.  
  
<a name="binding_state"></a>   
## <a name="retrieving-data-binding-information-from-a-binding-expression"></a>Recuperación de información sobre el enlace de datos de una expresión de enlace  
 En algunos casos, es posible que obtenga el <xref:System.Windows.Data.BindingExpression> de una <xref:System.Windows.Data.Binding> y necesite información sobre los objetos de origen y de destino del enlace.  Se agregaron nuevas API para permitirle obtener el objeto de origen o destino, o la propiedad asociada.  Cuando tenga un <xref:System.Windows.Data.BindingExpression>, utilice las siguientes API para obtener información sobre el destino y el origen.  
  
|Para encontrar este valor del enlace|Utilice esta API|  
|---------------------------------------|------------------|  
|Objeto de destino|<xref:System.Windows.Data.BindingExpressionBase.Target%2A?displayProperty=nameWithType>|  
|Propiedad de destino|<xref:System.Windows.Data.BindingExpressionBase.TargetProperty%2A?displayProperty=nameWithType>|  
|Objeto de origen|<xref:System.Windows.Data.BindingExpression.ResolvedSource%2A?displayProperty=nameWithType>|  
|Propiedad de origen|<xref:System.Windows.Data.BindingExpression.ResolvedSourcePropertyName%2A?displayProperty=nameWithType>|  
|Si el <xref:System.Windows.Data.BindingExpression> pertenece a un <xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingExpressionBase.BindingGroup%2A?displayProperty=nameWithType>|  
|Propietario de un <xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingGroup.Owner%2A>|  
  
<a name="DisconnectedSource"></a>   
## <a name="checking-for-a-valid-datacontext-object"></a>Búsqueda de un objeto DataContext válido  
 Hay casos en los que el <xref:System.Windows.FrameworkElement.DataContext%2A> de un contenedor de elementos de un <xref:System.Windows.Controls.ItemsControl> se desconecta.  Un contenedor de elementos es el elemento de la interfaz de usuario que muestra un elemento en un <xref:System.Windows.Controls.ItemsControl>.  Cuando un <xref:System.Windows.Controls.ItemsControl> tiene datos enlazados a una colección, se genera un contenedor de elementos para cada elemento. En algunos casos, los contenedores de elementos se quitan del árbol visual. Dos casos típicos en los que se quita un contenedor de elementos son cuando se quita un elemento de la colección subyacente y cuando se habilita la virtualización en el <xref:System.Windows.Controls.ItemsControl>. En estos casos, la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> del contenedor de elementos se establecerá en el objeto centinela devuelto por la propiedad estática <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A?displayProperty=nameWithType>.  Debe comprobar si el <xref:System.Windows.FrameworkElement.DataContext%2A> es igual al objeto <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A> antes de tener acceso a la <xref:System.Windows.FrameworkElement.DataContext%2A> de un contenedor de elementos.  
  
<a name="live_shaping"></a>   
## <a name="repositioning-data-as-the-datas-values-change-live-shaping"></a>Reposición de los datos a medida que cambian sus valores (modelado dinámico)  
 Una colección de datos se puede agrupar, ordenar o filtrar. WPF 4.5 permite que los datos se reorganicen cuando se modifican los datos. Por ejemplo, supongamos que una aplicación usa un <xref:System.Windows.Controls.DataGrid> para enumerar las existencias en un mercado de acciones y las acciones se ordenan por valor de existencias. Si está habilitada la ordenación en directo en el <xref:System.Windows.Data.CollectionView>de existencias, la posición de una acción en el <xref:System.Windows.Controls.DataGrid> se mueve cuando el valor de las existencias es mayor o menor que el valor de otra acción.   Para obtener más información, vea la interfaz <xref:System.ComponentModel.ICollectionViewLiveShaping>.  
  
<a name="weak_event_pattern"></a>   
## <a name="improved-support-for-establishing-a-weak-reference-to-an-event"></a>Compatibilidad mejorada para establecer una referencia débil a un evento  
 Ahora es más fácil implementar el patrón de evento débil, ya que los suscriptores a eventos pueden participar en él sin necesidad de implementar una interfaz adicional.  La clase <xref:System.Windows.WeakEventManager> genérica también permite a los suscriptores participar en el modelo de evento débil si no existe un <xref:System.Windows.WeakEventManager> dedicado para un evento determinado.  Para más información, consulte [Patrones de evento débil](../advanced/weak-event-patterns.md).  
  
<a name="async"></a>   
## <a name="new-methods-for-the-dispatcher-class"></a>Nuevos métodos para la clase Dispatcher  
 La clase Dispatcher define nuevos métodos para operaciones sincrónicas y asincrónicas.  El método de <xref:System.Windows.Threading.Dispatcher.Invoke%2A> sincrónico define las sobrecargas que toman un parámetro <xref:System.Action> o <xref:System.Func%601>. El nuevo método asincrónico, <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>, también toma un <xref:System.Action> o <xref:System.Func%601> como parámetro de devolución de llamada y devuelve un <xref:System.Windows.Threading.DispatcherOperation> o <xref:System.Windows.Threading.DispatcherOperation%601>.   Las clases <xref:System.Windows.Threading.DispatcherOperation> y <xref:System.Windows.Threading.DispatcherOperation%601> definen una propiedad <xref:System.Threading.Tasks.Task>.  Cuando llame a <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>, puede usar la palabra clave `await` con el <xref:System.Windows.Threading.DispatcherOperation> o el <xref:System.Threading.Tasks.Task>asociado. Si necesita esperar sincrónicamente el <xref:System.Threading.Tasks.Task> devuelto por un <xref:System.Windows.Threading.DispatcherOperation> o <xref:System.Windows.Threading.DispatcherOperation%601>, llame al método de extensión <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A>. La llamada a <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> producirá un interbloqueo si la operación se pone en cola en un subproceso que realiza la llamada. Para obtener más información sobre el uso de un <xref:System.Threading.Tasks.Task> para realizar operaciones asincrónicas, vea [paralelismo de tareas (Task Parallel Library)](../../../standard/parallel-programming/task-based-asynchronous-programming.md).  
  
<a name="events_markup_extenions"></a>   
## <a name="markup-extensions-for-events"></a>Extensiones de marcado para eventos  
 WPF 4.5 admite extensiones de marcado para eventos.  Aunque WPF no define ninguna extensión de marcado que se use para eventos, los terceros pueden crear una extensión de marcado que se puede utilizar con eventos.  
  
## <a name="see-also"></a>Consulte también

- [Novedades de .NET Framework](../../whats-new/index.md)
