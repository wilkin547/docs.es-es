---
title: Novedades de WPF versión 4.5
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Presentation Foundation [WPF], what's new
- WPF [WPF], what's new
ms.assetid: db086ae4-70bb-4862-95db-2eaca5216bc3
ms.openlocfilehash: 708b2fc231bfe7a9bc1f52872a0ec41c91931f26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174711"
---
# <a name="whats-new-in-wpf-version-45"></a>Novedades de WPF versión 4.5
<a name="introduction"></a>Este tema contiene información sobre [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] las características nuevas y mejoradas de la versión 4.5.  
  
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
 WPF 4.5 incluye <xref:System.Windows.Controls.Ribbon.Ribbon> un control que hospeda una barra de herramientas de acceso rápido, menú de aplicaciones y fichas.  Para más información, consulte [Información general sobre la cinta](/visualstudio/vsto/ribbon-overview).  
  
<a name="grouped_virtualization"></a>
## <a name="improved-performance-when-displaying-large-sets-of-grouped-data"></a>Rendimiento mejorado al mostrar grandes conjuntos de datos agrupados  
 La virtualización de la interfaz de usuario (UI) se produce cuando un subconjunto de sus elementos se generan a partir de un mayor número de elementos de datos en función de qué elementos estén visibles en la pantalla. Define <xref:System.Windows.Controls.VirtualizingPanel> la <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> propiedad adjunta que habilita la virtualización de la interfaz de usuario para los datos agrupados.  Para más información acerca del agrupamiento de datos, consulte Cómo: Ordenar y agrupar datos mediante una vista en XAML.  Para obtener más información acerca de <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> la virtualización de datos agrupados, vea la propiedad adjunta.  
  
<a name="VirtualizingPanel"></a>
## <a name="new-features-for-the-virtualizingpanel"></a>Nuevas características para VirtualizingPanel  
  
1. Puede especificar si <xref:System.Windows.Controls.VirtualizingPanel>un , <xref:System.Windows.Controls.VirtualizingStackPanel>como el , <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> muestra elementos parciales mediante la propiedad adjunta. Si <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> se <xref:System.Windows.Controls.ScrollUnit.Item>establece <xref:System.Windows.Controls.VirtualizingPanel> en , solo se mostrarán los elementos que son completamente visibles. Si <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> se <xref:System.Windows.Controls.ScrollUnit.Pixel>establece <xref:System.Windows.Controls.VirtualizingPanel> en , el puede mostrar elementos parcialmente visibles.  
  
2. Puede especificar el tamaño de la memoria caché <xref:System.Windows.Controls.VirtualizingPanel> antes y después de la ventana gráfica cuando se está virtualizando mediante la <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A> propiedad adjunta.  La memoria caché es la cantidad de espacio encima o debajo de la ventanilla en el que no se virtualizarán elementos.  Usar una memoria caché para evitar que se generen elementos de UI a medida que van apareciendo por desplazamiento puede mejorar el rendimiento. La memoria caché se rellena con menor prioridad para que la aplicación no deje de responder durante la operación. La <xref:System.Windows.Controls.VirtualizingPanel.CacheLengthUnit%2A?displayProperty=nameWithType> propiedad determina la unidad de <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A?displayProperty=nameWithType>medida que utiliza .  
  
<a name="static_properties"></a>
## <a name="binding-to-static-properties"></a>Enlace a propiedades estáticas  
 Puede usar propiedades estáticas como origen de un enlace de datos. El motor de enlace de datos reconoce cuándo cambia el valor de la propiedad si se genera un evento estático.  Por ejemplo, si la clase `SomeClass` define una propiedad estática denominada `MyProperty`, `SomeClass` puede definir un evento estático que se genera cuando el valor de `MyProperty` cambia.  El evento estático puede utilizar cualquiera de las siguientes firmas.  
  
- `public static event EventHandler MyPropertyChanged;`  
  
- `public static event EventHandler<PropertyChangedEventArgs> StaticPropertyChanged;`  
  
 Tenga en cuenta que en el primer caso, la clase <xref:System.EventArgs> expone un evento estático denominado *PropertyName* `Changed` que pasa al controlador de eventos.  En el segundo caso, la clase `StaticPropertyChanged` expone un <xref:System.ComponentModel.PropertyChangedEventArgs> evento estático denominado que pasa al controlador de eventos. Una clase que implementa la propiedad estática puede elegir generar notificaciones de cambio de propiedad mediante cualquiera de estos métodos.  
  
<a name="xthread_access"></a>
## <a name="accessing-collections-on-non-ui-threads"></a>Acceso a colecciones en subprocesos que no son de la interfaz de usuario  
 WPF permite acceder a colecciones de datos en subprocesos distintos del que creó la colección y modificarlas.  Esto le permite usar un subproceso en segundo plano para recibir datos de un origen externo, como una base de datos, y mostrar los datos en el subproceso de interfaz de usuario.  Si usa otro subproceso para modificar la colección, la interfaz de usuario sigue respondiendo a la interacción del usuario.  
  
<a name="INotifyDataErrorInfo"></a>
## <a name="synchronously-and-asynchronously-validating-data"></a>Validación sincrónica y asincrónica de datos  
 La <xref:System.ComponentModel.INotifyDataErrorInfo> interfaz permite que las clases de entidad de datos implementen reglas de validación personalizadas y expongan los resultados de validación de forma asincrónica. Además, esta interfaz admite objetos de error personalizados, varios errores por propiedad, errores entre propiedades y errores de nivel de entidad.  Para más información, consulte <xref:System.ComponentModel.INotifyDataErrorInfo>.  
  
<a name="delay"></a>
## <a name="automatically-updating-the-source-of-a-data-binding"></a>Actualización automática del origen de un enlace de datos  
 Si usa un enlace de datos para actualizar <xref:System.Windows.Data.BindingBase.Delay%2A> un origen de datos, puede usar la propiedad para especificar una cantidad de tiempo que debe pasar después de que la propiedad cambie en el destino antes de que se actualice el origen.  Por ejemplo, supongamos <xref:System.Windows.Controls.Slider> que tiene <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> un que tiene sus datos de propiedad <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> de forma <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>bidireccional enlazados a una propiedad de un objeto de datos y la propiedad se establece en .  En este ejemplo, cuando <xref:System.Windows.Controls.Slider>el usuario mueve el , <xref:System.Windows.Controls.Slider> el origen se actualiza para cada píxel que se mueve.  El objeto de origen normalmente necesita el valor <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> del control deslizante solo cuando el control deslizante deja de cambiar.  Para evitar la actualización del <xref:System.Windows.Data.BindingBase.Delay%2A> origen con demasiada frecuencia, utilice para especificar que el origen no debe actualizarse hasta que transcurra una cierta cantidad de tiempo después de que el pulgar deje de moverse.  
  
<a name="ICustomTypeProvider"></a>
## <a name="binding-to-types-that-implement-icustomtypeprovider"></a>Enlace a tipos que implementan ICustomTypeProvider  
 WPFWPF admite el enlace <xref:System.Reflection.ICustomTypeProvider>de datos a objetos que implementan, también conocidos como tipos personalizados.  Puede utilizar tipos personalizados en los casos siguientes.  
  
1. Como <xref:System.Windows.PropertyPath> un enlace de datos. Por ejemplo, <xref:System.Windows.Data.Binding.Path%2A> la <xref:System.Windows.Data.Binding> propiedad de a puede hacer referencia a una propiedad de un tipo personalizado.  
  
2. Como el valor <xref:System.Windows.DataTemplate.DataType%2A> de la propiedad.  
  
3. Como un tipo que determina las columnas <xref:System.Windows.Controls.DataGrid>generadas automáticamente en un archivo .  
  
<a name="binding_state"></a>
## <a name="retrieving-data-binding-information-from-a-binding-expression"></a>Recuperación de información sobre el enlace de datos de una expresión de enlace  
 En algunos casos, puede <xref:System.Windows.Data.BindingExpression> obtener <xref:System.Windows.Data.Binding> la de a y necesita información sobre los objetos de origen y destino del enlace.  Se agregaron nuevas API para permitirle obtener el objeto de origen o destino, o la propiedad asociada.  Cuando tenga <xref:System.Windows.Data.BindingExpression>un , use las siguientes API para obtener información sobre el destino y el origen.  
  
|Para encontrar este valor del enlace|Utilice esta API|  
|---------------------------------------|------------------|  
|Objeto de destino|<xref:System.Windows.Data.BindingExpressionBase.Target%2A?displayProperty=nameWithType>|  
|Propiedad de destino|<xref:System.Windows.Data.BindingExpressionBase.TargetProperty%2A?displayProperty=nameWithType>|  
|Objeto de origen|<xref:System.Windows.Data.BindingExpression.ResolvedSource%2A?displayProperty=nameWithType>|  
|Propiedad de origen|<xref:System.Windows.Data.BindingExpression.ResolvedSourcePropertyName%2A?displayProperty=nameWithType>|  
|Si <xref:System.Windows.Data.BindingExpression> el pertenece a un<xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingExpressionBase.BindingGroup%2A?displayProperty=nameWithType>|  
|El propietario de un<xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingGroup.Owner%2A>|  
  
<a name="DisconnectedSource"></a>
## <a name="checking-for-a-valid-datacontext-object"></a>Búsqueda de un objeto DataContext válido  
 Hay casos en <xref:System.Windows.FrameworkElement.DataContext%2A> los que el <xref:System.Windows.Controls.ItemsControl> de un contenedor de elementos en un se desconecta.  Un contenedor de elementos es el <xref:System.Windows.Controls.ItemsControl>elemento de interfaz de usuario que muestra un elemento en un archivo .  Cuando <xref:System.Windows.Controls.ItemsControl> un es datos enlazados a una colección, se genera un contenedor de elementos para cada elemento. En algunos casos, los contenedores de elementos se quitan del árbol visual. Dos casos típicos en los que se quita un contenedor de elementos son <xref:System.Windows.Controls.ItemsControl>cuando se quita un elemento de la colección subyacente y cuando se habilita la virtualización en el archivo . En estos casos, la <xref:System.Windows.FrameworkElement.DataContext%2A> propiedad del contenedor de elementos se <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A?displayProperty=nameWithType> establecerá en el objeto centinela devuelto por la propiedad estática.  Debe comprobar si <xref:System.Windows.FrameworkElement.DataContext%2A> el es <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A> igual al <xref:System.Windows.FrameworkElement.DataContext%2A> objeto antes de tener acceso al contenedor de elementos.  
  
<a name="live_shaping"></a>
## <a name="repositioning-data-as-the-datas-values-change-live-shaping"></a>Reposición de los datos a medida que cambian sus valores (modelado dinámico)  
 Una colección de datos se puede agrupar, ordenar o filtrar. WPF 4.5 permite que los datos se reorganicen cuando se modifican los datos. Por ejemplo, supongamos que <xref:System.Windows.Controls.DataGrid> una aplicación utiliza a para enumerar acciones en un mercado de valores y las acciones se ordenan por valor de stock. Si la clasificación en vivo está <xref:System.Windows.Data.CollectionView>habilitada en las acciones, la posición de una acción en los <xref:System.Windows.Controls.DataGrid> movimientos cuando el valor de la acción se convierte en mayor o menor que el valor de otra acción.   Para obtener más <xref:System.ComponentModel.ICollectionViewLiveShaping> información, consulte la interfaz.  
  
<a name="weak_event_pattern"></a>
## <a name="improved-support-for-establishing-a-weak-reference-to-an-event"></a>Compatibilidad mejorada para establecer una referencia débil a un evento  
 Ahora es más fácil implementar el patrón de evento débil, ya que los suscriptores a eventos pueden participar en él sin necesidad de implementar una interfaz adicional.  La <xref:System.Windows.WeakEventManager> clase genérica también permite a los suscriptores <xref:System.Windows.WeakEventManager> participar en el patrón de eventos débiles si no existe un dedicado para un evento determinado.  Para más información, consulte [Patrones de evento débil](../advanced/weak-event-patterns.md).  
  
<a name="async"></a>
## <a name="new-methods-for-the-dispatcher-class"></a>Nuevos métodos para la clase Dispatcher  
 La clase Dispatcher define nuevos métodos para operaciones sincrónicas y asincrónicas.  El <xref:System.Windows.Threading.Dispatcher.Invoke%2A> método sincrónico define <xref:System.Action> <xref:System.Func%601> sobrecargas que toman un parámetro o. El nuevo método <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>asincrónico, , también toma un <xref:System.Action> parámetro de devolución de llamada o <xref:System.Func%601> como y devuelve un <xref:System.Windows.Threading.DispatcherOperation> o <xref:System.Windows.Threading.DispatcherOperation%601>.   Las <xref:System.Windows.Threading.DispatcherOperation> <xref:System.Windows.Threading.DispatcherOperation%601> clases <xref:System.Threading.Tasks.Task> y definen una propiedad.  Cuando llame <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>a , `await` puede utilizar <xref:System.Windows.Threading.DispatcherOperation> la palabra <xref:System.Threading.Tasks.Task>clave con el archivo . Si necesita esperar sincrónicamente para <xref:System.Threading.Tasks.Task> que <xref:System.Windows.Threading.DispatcherOperation> <xref:System.Windows.Threading.DispatcherOperation%601>se devuelva un o , llame al <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> método de extensión. La <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> llamada dará lugar a un interbloqueo si la operación se pone en cola en un subproceso que realiza la llamada. Para obtener más <xref:System.Threading.Tasks.Task> información sobre el uso de a para realizar operaciones asincrónicas, vea [Paralelismo](../../../standard/parallel-programming/task-based-asynchronous-programming.md)de tareas (Biblioteca paralela de tareas).  
  
<a name="events_markup_extenions"></a>
## <a name="markup-extensions-for-events"></a>Extensiones de marcado para eventos  
 WPF 4.5 admite extensiones de marcado para eventos.  Aunque WPF no define ninguna extensión de marcado que se use para eventos, los terceros pueden crear una extensión de marcado que se puede utilizar con eventos.  
  
## <a name="see-also"></a>Consulte también

- [Novedades de .NET Framework](../../whats-new/index.md)
