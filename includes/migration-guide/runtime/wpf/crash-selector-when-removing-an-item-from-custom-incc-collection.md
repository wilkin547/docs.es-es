### <a name="crash-in-selector-when-removing-an-item-from-a-custom-incc-collection"></a>Al quitar un elemento de una colección personalizada de INCC se produce un bloqueo en Selector

|   |   |
|---|---|
|Detalles|Se puede iniciar una excepción <code>T:System.InvalidOperationException</code> en el escenario siguiente:<ul><li>El ItemsSource de un control <code>T:System.Windows.Controls.Primitives.Selector</code> es una colección con una implementación personalizada de <code>T:System.Collections.Specialized.INotifyCollectionChanged</code>.</li><li>El elemento seleccionado se quita de la colección.</li><li><code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code> tiene <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code> = -1 (lo que indica una posición desconocida).</li></ul>La pila de llamadas de la excepción comienza en System.Windows.Threading.Dispatcher.VerifyAccess() en System.Windows.DependencyObject.GetValue(DependencyProperty dp) en System.Windows.Controls.Primitives.Selector.GetIsSelected(DependencyObject elemento). Esta excepción se puede iniciar en .NET 4.5 si la aplicación tiene más de un subproceso de distribuidor. En .NET 4.7, la excepción también se puede iniciar en las aplicaciones con un único subproceso de distribuidor. El problema se ha corregido en .NET 4.7.1.|
|Sugerencia|Actualice a .NET 4.7.1.|
|Ámbito|Secundaria|
|Versión|4.7|
|Tipo|Tiempo de ejecución|

