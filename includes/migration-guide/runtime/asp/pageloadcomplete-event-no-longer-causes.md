### <a name="pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a>El evento Page.LoadComplete ya no hace que el control System.Web.UI.WebControls.EntityDataSource invoque un enlace de datos

|   |   |
|---|---|
|Detalles|El evento <xref:System.Web.UI.Page.LoadComplete> ya no hace que el control <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=name> llame al enlace de datos cuando se producen cambios al crear, actualizar o eliminar parámetros. Este cambio elimina un viaje superfluo a la base de datos, impide que se restablezcan los valores de los controles y produce un comportamiento coherente con otros controles de datos, como <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=name> y <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=name>. Este cambio produce un comportamiento diferente en el caso improbable de que las aplicaciones invoquen el enlace de datos en el evento <xref:System.Web.UI.Page.LoadComplete>.|
|Sugerencia|Si se necesita un enlace de datos, invóquelo manualmente en un evento anterior en la devolución.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

