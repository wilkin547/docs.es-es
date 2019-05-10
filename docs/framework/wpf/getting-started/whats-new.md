---
title: Novedades de WPF versión 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Presentation Foundation [WPF], what's new
- WPF [WPF], what's new
ms.assetid: db086ae4-70bb-4862-95db-2eaca5216bc3
ms.openlocfilehash: 0dbe038bed3fd62589b2f3906441e27761e0438a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649162"
---
# <a name="whats-new-in-wpf-version-45"></a>Novedades de WPF versión 4.5
<a name="introduction"></a> Este tema contiene información sobre las características nuevas y mejoradas de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] versión 4.5.  
  
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
 WPF 4.5 se distribuye con un <xref:System.Windows.Controls.Ribbon.Ribbon> control que hospeda una barra de herramientas de acceso rápido, un menú de la aplicación y pestañas.  Para más información, consulte [Información general sobre la cinta](/visualstudio/vsto/ribbon-overview).  
  
<a name="grouped_virtualization"></a>   
## <a name="improved-performance-when-displaying-large-sets-of-grouped-data"></a>Rendimiento mejorado al mostrar grandes conjuntos de datos agrupados  
 La virtualización de la interfaz de usuario (UI) se produce cuando un subconjunto de sus elementos se generan a partir de un mayor número de elementos de datos en función de qué elementos estén visibles en la pantalla. El <xref:System.Windows.Controls.VirtualizingPanel> define la <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> adjunta la propiedad que permite la virtualización de interfaz de usuario para los datos agrupados.  Para obtener más información acerca de la agrupación de datos, vea Cómo: Ordenar y agrupar datos mediante una vista en XAML.  Para obtener más información acerca de la virtualización de los datos agrupados, consulte el <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> propiedad adjunta.  
  
<a name="VirtualizingPanel"></a>   
## <a name="new-features-for-the-virtualizingpanel"></a>Nuevas características para VirtualizingPanel  
  
1. Puede especificar si una <xref:System.Windows.Controls.VirtualizingPanel>, como el <xref:System.Windows.Controls.VirtualizingStackPanel>, muestra elementos parciales mediante el <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> propiedad adjunta. Si <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> está establecido en <xref:System.Windows.Controls.ScrollUnit.Item>, el <xref:System.Windows.Controls.VirtualizingPanel> solo mostrará los elementos que estén completamente visibles. Si <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> está establecido en <xref:System.Windows.Controls.ScrollUnit.Pixel>, el <xref:System.Windows.Controls.VirtualizingPanel> puede mostrar los elementos parcialmente visibles.  
  
2. Puede especificar el tamaño de la memoria caché antes y después de la ventanilla cuando la <xref:System.Windows.Controls.VirtualizingPanel> esté virtualizando mediante la <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A> propiedad adjunta.  La memoria caché es la cantidad de espacio encima o debajo de la ventanilla en el que no se virtualizarán elementos.  Usar una memoria caché para evitar que se generen elementos de UI a medida que van apareciendo por desplazamiento puede mejorar el rendimiento. La memoria caché se rellena con menor prioridad para que la aplicación no deje de responder durante la operación. El <xref:System.Windows.Controls.VirtualizingPanel.CacheLengthUnit%2A?displayProperty=nameWithType> propiedad determina la unidad de medida que se usa por <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A?displayProperty=nameWithType>.  
  
<a name="static_properties"></a>   
## <a name="binding-to-static-properties"></a>Enlace a propiedades estáticas  
 Puede usar propiedades estáticas como origen de un enlace de datos. El motor de enlace de datos reconoce cuándo cambia el valor de la propiedad si se genera un evento estático.  Por ejemplo, si la clase `SomeClass` define una propiedad estática denominada `MyProperty`, `SomeClass` puede definir un evento estático que se genera cuando el valor de `MyProperty` cambia.  El evento estático puede utilizar cualquiera de las siguientes firmas.  
  
- `public static event EventHandler MyPropertyChanged;`  
  
- `public static event EventHandler<PropertyChangedEventArgs> StaticPropertyChanged;`  
  
 Tenga en cuenta que en el primer caso, la clase expone un evento estático denominado *PropertyName* `Changed` que pasa <xref:System.EventArgs> al controlador de eventos.  En el segundo caso, la clase expone un evento estático denominado `StaticPropertyChanged` que pasa <xref:System.ComponentModel.PropertyChangedEventArgs> al controlador de eventos. Una clase que implementa la propiedad estática puede elegir generar notificaciones de cambio de propiedad mediante cualquiera de estos métodos.  
  
<a name="xthread_access"></a>   
## <a name="accessing-collections-on-non-ui-threads"></a>Acceso a colecciones en subprocesos que no son de la interfaz de usuario  
 WPF permite acceder a colecciones de datos en subprocesos distintos del que creó la colección y modificarlas.  Esto le permite usar un subproceso en segundo plano para recibir datos de un origen externo, como una base de datos, y mostrar los datos en el subproceso de interfaz de usuario.  Si usa otro subproceso para modificar la colección, la interfaz de usuario sigue respondiendo a la interacción del usuario.  
  
<a name="INotifyDataErrorInfo"></a>   
## <a name="synchronously-and-asynchronously-validating-data"></a>Validación sincrónica y asincrónica de datos  
 El <xref:System.ComponentModel.INotifyDataErrorInfo> interfaz permite que las clases de entidad de datos implementar reglas de validación personalizadas y exponer los resultados de validación de forma asincrónica. Además, esta interfaz admite objetos de error personalizados, varios errores por propiedad, errores entre propiedades y errores de nivel de entidad.  Para obtener más información, consulta <xref:System.ComponentModel.INotifyDataErrorInfo>.  
  
<a name="delay"></a>   
## <a name="automatically-updating-the-source-of-a-data-binding"></a>Actualización automática del origen de un enlace de datos  
 Si utiliza un enlace de datos para actualizar un origen de datos, puede usar el <xref:System.Windows.Data.BindingBase.Delay%2A> propiedad para especificar un período de tiempo que pasará después de los cambios de propiedad en el destino antes de las actualizaciones de origen.  Por ejemplo, suponga que tiene un <xref:System.Windows.Controls.Slider> que tiene su <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> datos bidireccionales de la propiedad enlazan a una propiedad de un objeto de datos y el <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propiedad está establecida en <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.  En este ejemplo, cuando el usuario mueve el <xref:System.Windows.Controls.Slider>, las actualizaciones de origen para cada píxel que el <xref:System.Windows.Controls.Slider> se mueve.  El objeto de origen necesita normalmente el valor del control deslizante solo cuando el control deslizante <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> deja cambiar.  Para evitar la actualización del origen con demasiada frecuencia, use <xref:System.Windows.Data.BindingBase.Delay%2A> para especificar que no se debe actualizar el origen hasta que transcurre una cierta cantidad de tiempo el control deje de moverse.  
  
<a name="ICustomTypeProvider"></a>   
## <a name="binding-to-types-that-implement-icustomtypeprovider"></a>Enlace a tipos que implementan ICustomTypeProvider  
 WPF admite enlace de datos a los objetos que implementan <xref:System.Reflection.ICustomTypeProvider>, también conocido como tipos personalizados.  Puede utilizar tipos personalizados en los casos siguientes.  
  
1. Como un <xref:System.Windows.PropertyPath> en un enlace de datos. Por ejemplo, el <xref:System.Windows.Data.Binding.Path%2A> propiedad de un <xref:System.Windows.Data.Binding> puede hacer referencia a una propiedad de un tipo personalizado.  
  
2. Como el valor de la <xref:System.Windows.DataTemplate.DataType%2A> propiedad.  
  
3. Como un tipo que determina las columnas generadas automáticamente en un <xref:System.Windows.Controls.DataGrid>.  
  
<a name="binding_state"></a>   
## <a name="retrieving-data-binding-information-from-a-binding-expression"></a>Recuperación de información sobre el enlace de datos de una expresión de enlace  
 En algunos casos, podría obtener el <xref:System.Windows.Data.BindingExpression> de un <xref:System.Windows.Data.Binding> y necesita información acerca de los objetos de origen y de destino del enlace.  Se agregaron nuevas API para permitirle obtener el objeto de origen o destino, o la propiedad asociada.  Cuando haya un <xref:System.Windows.Data.BindingExpression>, utilice las siguientes API para obtener información sobre el origen y destino.  
  
|Para encontrar este valor del enlace|Utilice esta API|  
|---------------------------------------|------------------|  
|Objeto de destino|<xref:System.Windows.Data.BindingExpressionBase.Target%2A?displayProperty=nameWithType>|  
|Propiedad de destino|<xref:System.Windows.Data.BindingExpressionBase.TargetProperty%2A?displayProperty=nameWithType>|  
|Objeto de origen|<xref:System.Windows.Data.BindingExpression.ResolvedSource%2A?displayProperty=nameWithType>|  
|Propiedad de origen|<xref:System.Windows.Data.BindingExpression.ResolvedSourcePropertyName%2A?displayProperty=nameWithType>|  
|Si el <xref:System.Windows.Data.BindingExpression> pertenece a un <xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingExpressionBase.BindingGroup%2A?displayProperty=nameWithType>|  
|El propietario de un <xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingGroup.Owner%2A>|  
  
<a name="DisconnectedSource"></a>   
## <a name="checking-for-a-valid-datacontext-object"></a>Búsqueda de un objeto DataContext válido  
 Hay casos donde la <xref:System.Windows.FrameworkElement.DataContext%2A> de un contenedor de elementos en un <xref:System.Windows.Controls.ItemsControl> se desconecta.  Un contenedor de elementos es el elemento de interfaz de usuario que se muestra un elemento en un <xref:System.Windows.Controls.ItemsControl>.  Cuando un <xref:System.Windows.Controls.ItemsControl> son datos enlazados a una colección, se genera un contenedor de elementos para cada elemento. En algunos casos, los contenedores de elementos se quitan del árbol visual. Dos casos típicos donde se quita un contenedor de elementos son cuando se quita un elemento de la colección subyacente y cuando está habilitada la virtualización en el <xref:System.Windows.Controls.ItemsControl>. En estos casos, el <xref:System.Windows.FrameworkElement.DataContext%2A> se establecerá la propiedad del elemento contenedor en el objeto centinela devuelto por la <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A?displayProperty=nameWithType> propiedad estática.  Debe comprobar si el <xref:System.Windows.FrameworkElement.DataContext%2A> es igual a la <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A> objeto antes de acceder a la <xref:System.Windows.FrameworkElement.DataContext%2A> de un contenedor de elementos.  
  
<a name="live_shaping"></a>   
## <a name="repositioning-data-as-the-datas-values-change-live-shaping"></a>Reposición de los datos a medida que cambian sus valores (modelado dinámico)  
 Una colección de datos se puede agrupar, ordenar o filtrar. WPF 4.5 permite que los datos se reorganicen cuando se modifican los datos. Por ejemplo, suponga que una aplicación utiliza un <xref:System.Windows.Controls.DataGrid> para mostrar las existencias en una bolsa tanto están ordenados por valor de stock. Si está habilitada la ordenación activa en las poblaciones <xref:System.Windows.Data.CollectionView>, posición de una acción en el <xref:System.Windows.Controls.DataGrid> se desplaza cuando el valor de la acción pasa a ser mayor o menor que otra acción.   Para obtener más información, consulte el <xref:System.ComponentModel.ICollectionViewLiveShaping> interfaz.  
  
<a name="weak_event_pattern"></a>   
## <a name="improved-support-for-establishing-a-weak-reference-to-an-event"></a>Compatibilidad mejorada para establecer una referencia débil a un evento  
 Ahora es más fácil implementar el patrón de evento débil, ya que los suscriptores a eventos pueden participar en él sin necesidad de implementar una interfaz adicional.  La interfaz genérica <xref:System.Windows.WeakEventManager> clase también permite a los suscriptores participen en el modelo de evento débil si dedicada <xref:System.Windows.WeakEventManager> no existe para un determinado evento.  Para más información, consulte [Patrones de evento débil](../advanced/weak-event-patterns.md).  
  
<a name="async"></a>   
## <a name="new-methods-for-the-dispatcher-class"></a>Nuevos métodos para la clase Dispatcher  
 La clase Dispatcher define nuevos métodos para operaciones sincrónicas y asincrónicas.  Sincrónico <xref:System.Windows.Threading.Dispatcher.Invoke%2A> método define sobrecargas que toman un <xref:System.Action> o <xref:System.Func%601> parámetro. El nuevo método asincrónico, <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>, también toma un <xref:System.Action> o <xref:System.Func%601> como el parámetro de devolución de llamada y devuelve un <xref:System.Windows.Threading.DispatcherOperation> o <xref:System.Windows.Threading.DispatcherOperation%601>.   El <xref:System.Windows.Threading.DispatcherOperation> y <xref:System.Windows.Threading.DispatcherOperation%601> clases definen un <xref:System.Threading.Tasks.Task> propiedad.  Cuando se llama a <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>, puede usar el `await` palabra clave with ya sea el <xref:System.Windows.Threading.DispatcherOperation> o asociado <xref:System.Threading.Tasks.Task>. Si tiene que esperar de forma sincrónica el <xref:System.Threading.Tasks.Task> devuelta por un <xref:System.Windows.Threading.DispatcherOperation> o <xref:System.Windows.Threading.DispatcherOperation%601>, llame a la <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> método de extensión. Una llamada a <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> dará como resultado un interbloqueo si se pone en cola la operación en un subproceso que realiza la llamada. Para obtener más información sobre el uso de un <xref:System.Threading.Tasks.Task> para realizar operaciones asincrónicas, vea [Task Parallelism (Task Parallel Library)](../../../standard/parallel-programming/task-based-asynchronous-programming.md).  
  
<a name="events_markup_extenions"></a>   
## <a name="markup-extensions-for-events"></a>Extensiones de marcado para eventos  
 WPF 4.5 admite extensiones de marcado para eventos.  Aunque WPF no define ninguna extensión de marcado que se use para eventos, los terceros pueden crear una extensión de marcado que se puede utilizar con eventos.  
  
## <a name="see-also"></a>Vea también

- [Novedades de .NET Framework](../../whats-new/index.md)
