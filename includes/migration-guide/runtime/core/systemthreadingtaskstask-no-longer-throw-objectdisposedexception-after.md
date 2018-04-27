### <a name="systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>System.Threading.Tasks.Task ya no inicia una excepción ObjectDisposedException después de desechar un objeto

|   |   |
|---|---|
|Detalles|A excepción de <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle>, los métodos <xref:System.Threading.Tasks.Task?displayProperty=name> ya no inician una excepción <xref:System.ObjectDisposedException?displayProperty=name> después de desechar el objeto. Este cambio admite el uso de tareas en caché. Por ejemplo, un método puede devolver una tarea almacenada en caché para representar una operación completada en lugar de asignar una nueva tarea. Esto no era posible en versiones anteriores de .NET Framework, ya que cualquier consumidor de la tarea podía desecharla, lo que hacía que se volviera inutilizable.|
|Sugerencia|Tenga en cuenta que es posible que los métodos Task ya no inicien excepciones <xref:System.ObjectDisposedException?displayProperty=name> cuando el objeto se desecha. Si una aplicación dependía de esta excepción para conocer que se desechó una tarea, se debería actualizar para comprobar de forma explícita el estado de la tarea mediante <xref:System.Threading.Tasks.Task.Status>.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

