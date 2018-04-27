### <a name="gridviews-with-allowcustompaging-set-to-true-may-fire-the-pageindexchanging-event-when-leaving-the-final-page-of-the-view"></a>GridView con AllowCustomPaging establecido en true puede desencadenar el evento PageIndexChanging al salir de la última página de la vista

|   |   |
|---|---|
|Detalles|Un error en .NET Framework 4.5 hace que en ocasiones no se desencadene <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=name> para los elementos <xref:System.Web.UI.WebControls.GridView?displayProperty=name> en los que se ha habilitado <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=name>.|
|Sugerencia|Este problema se ha corregido en .NET Framework 4.6 y se puede solucionar mediante la actualización a esa versión de .NET Framework. Como una solución alternativa, la aplicación puede realizar una BindGrid explícita en cualquier método <code>Page_Load</code> que cumpla estas condiciones (la <xref:System.Web.UI.WebControls.GridView?displayProperty=name> está en la última página y Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=name> es diferente de <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=name>). Como alternativa, la aplicación se puede modificar para permitir la paginación (en lugar de la paginación personalizada), dado que ese escenario no ilustra el problema.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=nameWithType></li></ul>|

