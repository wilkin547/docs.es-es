---
title: "Informaci&#243;n general del control DataGrid (Formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DataGrid"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "conjuntos de datos [Windows Forms], enlazar al control DataGrid"
  - "enlace de datos, DataGrid (control)"
  - "columnas [Windows Forms], control DataGrid"
  - "orígenes de datos, enlazar al control DataGrid"
  - "tablas [Windows Forms], enlazar al control DataGrid"
  - "DataGrid (control) [formularios Windows Forms], enlace de datos"
  - "DataGrid (control) [formularios Windows Forms], acerca del control DataGrid"
  - "tablas primarias en el control DataGrid"
  - "tablas [Windows Forms], mostrar en el control DataGrid"
  - "cuadrículas de datos, acerca de las cuadrículas de datos"
  - "varias tablas en un control DataGrid"
  - "datos [Windows Forms], volver a ordenar"
  - "datos [Windows Forms], navegar"
  - "controles enlazados, DataGrid (control)"
  - "controles enlazados a datos, DataGrid"
  - "navegación por las tablas primarias en DataGrid"
  - "tablas secundarias, DataGrid (control)"
ms.assetid: 85604bce-bc03-49d9-9030-dda8896c44b1
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Informaci&#243;n general del control DataGrid (Formularios Windows Forms)
> [!NOTE]
>  El <xref:System.Windows.Forms.DataGridView> control reemplaza y agrega funcionalidad a la <xref:System.Windows.Forms.DataGrid> control; sin embargo, el <xref:System.Windows.Forms.DataGrid> control se conserva para compatibilidad con versiones anteriores y uso futuro, si elige. Para obtener más información, consulte [diferencias entre el Windows Forms controles DataGridView y DataGrid](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Los formularios Windows Forms <xref:System.Windows.Forms.DataGrid> control muestra los datos en una serie de filas y columnas. El caso más simple es cuando la cuadrícula está enlazada a un origen de datos con una sola tabla que no contiene relaciones. En ese caso, los datos aparecen en simples filas y columnas, como en una hoja de cálculo. Para obtener más información sobre cómo enlazar datos a otros controles, vea [enlace de datos y formularios Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md).  
  
 Si el <xref:System.Windows.Forms.DataGrid> está enlazado a datos con varias tablas relacionadas y, si está habilitado el desplazamiento en la cuadrícula, la cuadrícula mostrará expansores en cada fila. Con un expansor, el usuario puede pasar de una tabla primaria a una tabla secundaria. Al hacer clic en un nodo se muestra la tabla secundaria y al hacer clic en un botón de retroceso se muestra la tabla primaria original. De esta manera, la cuadrícula muestra las relaciones jerárquicas entre tablas.  
  
 La captura de pantalla siguiente muestra un control DataGrid enlazado a datos con varias tablas.  
  
 ![Un control DataGrid enlazado a datos con varias tablas](../../../../docs/framework/winforms/controls/media/vbcontrol1.gif "vbControl1")  
Un control DataGrid enlazado a datos con múltiples tablas  
  
 El <xref:System.Windows.Forms.DataGrid> puede proporcionar una interfaz de usuario para un conjunto de datos, navegación entre tablas relacionadas, formato enriquecido y capacidades de edición.  
  
 La presentación y manipulación de datos son funciones independientes: el control administra la interfaz de usuario, mientras que las actualizaciones de datos se administran mediante la arquitectura de enlace de datos de Windows Forms y los proveedores de datos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Por lo tanto, si hay varios controles enlazados al mismo origen de datos, estarán sincronizados.  
  
> [!NOTE]
>  Si está familiarizado con el control DataGrid en Visual Basic 6.0, encontrará algunas diferencias significativas en los formularios Windows Forms <xref:System.Windows.Forms.DataGrid> control.  
  
 Cuando la cuadrícula está enlazada a un <xref:System.Data.DataSet>, las columnas y filas se crean, con formato y automáticamente llena. Para obtener más información, consulta [Data Binding and Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md). Después de la generación de la <xref:System.Windows.Forms.DataGrid> control, se puede agregar, eliminar, reorganizar y dar formato a las columnas y filas según sus necesidades.  
  
## <a name="binding-data-to-the-control"></a>Enlazar datos al control  
 Para el <xref:System.Windows.Forms.DataGrid> de control para que funcione, debe estar enlazado a un origen de datos mediante la <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedades en tiempo de diseño o la <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método en tiempo de ejecución. Este enlace apunta el <xref:System.Windows.Forms.DataGrid> a un objeto de origen de datos de instancias, como un <xref:System.Data.DataSet> o <xref:System.Data.DataTable>). El <xref:System.Windows.Forms.DataGrid> control muestra los resultados de las acciones que se realizan en los datos. La mayoría de las acciones específicas de datos no se realizan a través de la <xref:System.Windows.Forms.DataGrid> , sino a través del origen de datos.  
  
 Si los datos del conjunto de datos enlazado se actualizan mediante cualquier mecanismo, el <xref:System.Windows.Forms.DataGrid> control refleja los cambios. Si la cuadrícula de datos y sus estilos de tabla y columna tienen la `ReadOnly` propiedad establecida en `false`, los datos del conjunto de datos se pueden actualizar a través de la <xref:System.Windows.Forms.DataGrid> control.  
  
 Se puede mostrar una única tabla en el <xref:System.Windows.Forms.DataGrid> a la vez. Si se define una relación primaria-secundaria entre las tablas, el usuario puede desplazarse entre las tablas relacionadas para seleccionar la tabla que se mostrarán en el <xref:System.Windows.Forms.DataGrid> control. Para obtener información sobre el enlace de un <xref:System.Windows.Forms.DataGrid> el control a una [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] el origen de datos en tiempo de diseño o en tiempo de ejecución, vea [Cómo: enlazar el DataGrid Control de formularios Windows Forms a un origen de datos](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
 Orígenes de datos válidos para el <xref:System.Windows.Forms.DataGrid> incluyen:  
  
-   <xref:System.Data.DataTable> (clase)  
  
-   <xref:System.Data.DataView> (clase)  
  
-   <xref:System.Data.DataSet> (clase)  
  
-   <xref:System.Data.DataViewManager> (clase)  
  
 Si su origen es un conjunto de datos, el conjunto de datos podría ser un objeto en el formulario o un objeto pasado al formulario por un servicio web XML. Puede enlazar a conjuntos de datos con tipo o sin tipo.  
  
 También puede enlazar un <xref:System.Windows.Forms.DataGrid> control a estructuras adicionales si los objetos de la estructura, como los elementos de una matriz, exponen propiedades públicas. La cuadrícula mostrará todas las propiedades públicas de los elementos de la estructura. Por ejemplo, si enlaza el <xref:System.Windows.Forms.DataGrid> objetos de control a una matriz de cliente, la cuadrícula mostrará todas las propiedades públicas de esos objetos customer. En algunas instancias esto significa que, aunque se puede enlazar con la estructura, la estructura enlazada resultante podría no tener aplicación práctica. Por ejemplo, se puede enlazar a una matriz de enteros, pero dado que el tipo de datos `Integer` no admite una propiedad pública, la cuadrícula no puede mostrar los datos.  
  
 Las siguientes estructuras se pueden enlazar si sus elementos exponen propiedades públicas:  
  
-   Cualquier componente que implemente la <xref:System.Collections.IList> interfaz. Esto incluye las matrices unidimensionales.  
  
-   Cualquier componente que implemente la <xref:System.ComponentModel.IListSource> interfaz.  
  
-   Cualquier componente que implemente la <xref:System.ComponentModel.IBindingList> interfaz.  
  
 Para obtener más información sobre posibles orígenes de datos, consulte [orígenes de datos compatibles con formularios Windows Forms](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md).  
  
## <a name="grid-display"></a>Visualización de la cuadrícula  
 Un uso común de la <xref:System.Windows.Forms.DataGrid> control es mostrar una única tabla de datos de un conjunto de datos. Sin embargo, el control también puede usarse para mostrar varias tablas, incluidas tablas relacionadas. La presentación de la cuadrícula se ajusta automáticamente conforme al origen de datos. En la tabla siguiente se indica lo que se muestra según las diferentes configuraciones.  
  
|Contenido del conjunto de datos|Qué se muestra|  
|--------------------------|-----------------------|  
|Tabla única.|La tabla se muestra en una cuadrícula.|  
|Varias tablas.|La cuadrícula puede mostrar una vista de árbol por la que los usuarios pueden desplazarse para localizar la tabla que desean mostrar.|  
|Varias tablas relacionadas.|La cuadrícula puede mostrar una vista de árbol para seleccionar las tablas, o usted puede especificar que la cuadrícula muestre la tabla primaria. Los registros de la tabla primaria permiten a los usuarios desplazarse a las filas secundarias relacionadas.|  
  
> [!NOTE]
>  Tablas en un conjunto de datos se relacionan mediante un <xref:System.Data.DataRelation>.  Consulte también [HYPERLINK "http://msdn.microsoft.com/library/dbwcse3d (110)" relaciones en conjuntos de datos](http://msdn.microsoft.com/library/dbwcse3d\(v=vs.110\)) o [relaciones en conjuntos de datos](http://msdn.microsoft.com/library/dbwcse3d\(v=vs.120\)).  
  
 Cuando el <xref:System.Windows.Forms.DataGrid> control muestra una tabla y la <xref:System.Windows.Forms.DataGrid.AllowSorting%2A> propiedad se establece en `true`, pueden volver a ordenar datos haciendo clic en los encabezados de columna. El usuario también puede agregar filas y modificar celdas.  
  
 Las relaciones entre un conjunto de tablas se muestran a los usuarios con una estructura de elementos primarios y secundarios de navegación. Las tablas primarias son el nivel más alto de los datos y las tablas secundarias son las tablas de datos que se derivan de los listados individuales de las tablas primarias. Los expansores se muestran en cada fila primaria que contiene una tabla secundaria. Al hacer clic en un expansor, se genera una lista de vínculos de tipo web a las tablas secundarias. Cuando el usuario selecciona un vínculo, se muestra la tabla secundaria. Haga clic en el icono de filas primarias de mostrar u ocultar (![icono Mostrar u ocultar las filas primarias](../../../../docs/framework/winforms/controls/media/vbicon.png "vbIcon")) se ocultará la información acerca de la tabla primaria o reaparecerá si el usuario ha ocultado previamente. El usuario puede hacer clic en un botón Atrás para volver a la tabla mostrada previamente.  
  
## <a name="columns-and-rows"></a>Columnas y filas  
 El <xref:System.Windows.Forms.DataGrid> consta de una colección de <xref:System.Windows.Forms.DataGridTableStyle> objetos incluidos en el <xref:System.Windows.Forms.DataGrid> control <xref:System.Windows.Forms.DataGrid.TableStyles%2A> propiedad. Un estilo de tabla puede contener una colección de <xref:System.Windows.Forms.DataGridColumnStyle> objetos incluidos en el <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> propiedad de la <xref:System.Windows.Forms.DataGridTableStyle>... Puede editar la <xref:System.Windows.Forms.DataGrid.TableStyles%2A> y <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> propiedades mediante los editores de colección que tiene acceso a través del **propiedades** ventana.  
  
 Cualquier <xref:System.Windows.Forms.DataGridTableStyle> asociados con el <xref:System.Windows.Forms.DataGrid> control puede obtenerse a través del <xref:System.Windows.Forms.GridTableStylesCollection>. El <xref:System.Windows.Forms.GridTableStylesCollection> se pueden editar en el diseñador con el <xref:System.Windows.Forms.DataGridTableStyle> editor de la colección, o mediante programación a través del <xref:System.Windows.Forms.DataGrid> del control <xref:System.Windows.Forms.DataGrid.TableStyles%2A> propiedad.  
  
 ![Objetos incluidos en el control DataGrid](../../../../docs/framework/winforms/controls/media/vbcolumns1.png "vbColumns1")  
La ilustración siguiente muestra los objetos incluidos en el control DataGrid.  
  
 Estilos de tabla y columna se sincronizan con <xref:System.Data.DataTable> objetos y <xref:System.Data.DataColumn> objetos estableciendo sus `MappingName` propiedades correspondientes <xref:System.Data.DataTable.TableName%2A> y <xref:System.Data.DataColumn.ColumnName%2A> propiedades. Cuando un <xref:System.Windows.Forms.DataGridTableStyle> que no tiene ninguna columna estilos se agrega a un <xref:System.Windows.Forms.DataGrid> control enlazado a un origen de datos válido y el <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> propiedad de esa tabla se establece en válido <xref:System.Data.DataTable.TableName%2A> propiedad, un conjunto de <xref:System.Windows.Forms.DataGridColumnStyle> se crean objetos para ese estilo de tabla. Para cada <xref:System.Data.DataColumn> se encuentra en la <xref:System.Data.DataTable.Columns%2A> colección de la <xref:System.Data.DataTable>, correspondiente <xref:System.Windows.Forms.DataGridColumnStyle> se agrega a la <xref:System.Windows.Forms.GridColumnStylesCollection>. <xref:System.Windows.Forms.GridColumnStylesCollection> se tiene acceso mediante la <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> propiedad de la <xref:System.Windows.Forms.DataGridTableStyle>. Las columnas se pueden agregar o eliminar desde la cuadrícula mediante el <xref:System.Windows.Forms.GridColumnStylesCollection.Add%2A> o <xref:System.Windows.Forms.GridColumnStylesCollection.Remove%2A> método en el <xref:System.Windows.Forms.GridColumnStylesCollection>. Para obtener más información, consulte [Cómo: agregar tablas y columnas al DataGrid Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md) y [Cómo: eliminar u ocultar columnas en el DataGrid Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md).  
  
 Una colección de tipos de columna extiende la <xref:System.Windows.Forms.DataGridColumnStyle> clase con formato enriquecido y capacidades de edición. Todos los tipos de columna se heredan de la <xref:System.Windows.Forms.DataGridColumnStyle> clase base. Depende de la clase que se crea el <xref:System.Data.DataColumn.DataType%2A> propiedad de la <xref:System.Data.DataColumn> desde el que el <xref:System.Web.UI.WebControls.DataGridColumn> se basa. Por ejemplo, un <xref:System.Data.DataColumn> que tiene su <xref:System.Data.DataColumn.DataType%2A> propiedad establecida en <xref:System.Boolean> se asociará el <xref:System.Windows.Forms.DataGridBoolColumn>. En la siguiente tabla se describe cada uno de estos tipos de columna.  
  
|Tipo de columna|Descripción|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.DataGridTextBoxColumn>|Acepta y muestra los datos como cadenas con o sin formato. Capacidades de edición son los mismos que para modificar los datos en un sencillo <xref:System.Windows.Forms.TextBox>. Hereda de <xref:System.Windows.Forms.DataGridColumnStyle>.|  
|<xref:System.Windows.Forms.DataGridBoolColumn>|Acepta y muestra `true`, `false` y valores null. Hereda de <xref:System.Windows.Forms.DataGridColumnStyle>.|  
  
 Al hacer doble clic en el borde derecho de una columna se cambia el tamaño de la columna para mostrar su leyenda completa y su entrada más ancha.  
  
## <a name="table-styles-and-column-styles"></a>Estilos de tabla y estilos de columna  
 Tan pronto como haya establecido el formato predeterminado de la <xref:System.Windows.Forms.DataGrid> control, puede personalizar los colores que se utilizará cuando se muestren determinadas tablas en la cuadrícula de datos.  
  
 Esto se logra mediante la creación de instancias de la <xref:System.Windows.Forms.DataGridTableStyle> clase. Estilos de tabla especifican el formato de tablas específicas, distinto del formato predeterminado de la <xref:System.Windows.Forms.DataGrid> propio control. Una tabla no puede tener más de un estilo definido.  
  
 Es posible que en ocasiones desee que una columna concreta tenga una apariencia diferente a la del resto de columnas de una tabla de datos. Puede crear un conjunto personalizado de estilos de columna mediante el <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> propiedad.  
  
 Los estilos de columna están relacionados con las columnas de un conjunto de datos del mismo modo que los estilos de tabla están relacionados con las tablas de datos. Al igual que sucede con las tablas, que no pueden tener más de un estilo de tabla definido, una columna no puede tener definido más de un estilo de columna en un estilo de tabla concreto. Esta relación se define en la columna <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> propiedad.  
  
 Si crea un estilo de tabla sin agregarle estilos de columna, [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] agregará estilos de columna predeterminados cuando se creen el formulario y la cuadrícula en tiempo de ejecución. Sin embargo, si crea un estilo de tabla y le agrega estilos de columna, [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] no creará ningún estilo de columna. Además, necesitará definir estilos de columna y asignarlos con el nombre de la asignación para que las columnas que desee aparezcan en la cuadrícula.  
  
 Dado que usted especifica las columnas que se incluyen en la cuadrícula de datos al asignarles un estilo de columna y no se les ha asignado ningún estilo de columna, puede incluir columnas de datos en el conjunto de datos que no se muestran en la cuadrícula. Sin embargo, dado que la columna de datos se incluye en el conjunto de datos, puede editar mediante programación los datos que no se muestran.  
  
> [!NOTE]
>  En general, es mejor que cree los estilos de columna y los agregue a la colección de estilos de columna antes de agregar estilos de tabla a la colección de estilos de tabla. Si agrega un estilo de tabla vacío a la colección, se generan automáticamente los estilos de columna. Por lo tanto, se producirá una excepción si intenta agregar estilos de columna nuevos con duplicado <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> valores a la colección de estilos de columna.  
>   
>  Es posible que en ocasiones desee quitar una sola columna de muchas; por ejemplo, si el conjunto de datos contiene 50 columnas y solo desea 49. En este caso, es más fácil importar las 50 columnas y quitar una mediante programación, en lugar de agregar mediante programación cada una de las 49 columnas que desee.  
  
## <a name="formatting"></a>Aplicación de formato  
 El formato que se pueden aplicar a la <xref:System.Windows.Forms.DataGrid> control incluye estilos de borde, estilos de cuadrícula, fuentes, propiedades de título, alineación de datos y alternar los colores de fondo entre filas. Para obtener más información, consulte [Cómo: dar formato el DataGrid Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-the-windows-forms-datagrid-control.md).  
  
## <a name="events"></a>Eventos  
 Además del control comunes eventos como <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.Enter>, y <xref:System.Windows.Forms.DataGrid.Scroll>, <xref:System.Windows.Forms.DataGrid> control admite eventos asociados con la edición y navegación dentro de la cuadrícula. El <xref:System.Windows.Forms.DataGrid.CurrentCell%2A> propiedad determina la celda seleccionada. El <xref:System.Windows.Forms.DataGrid.CurrentCellChanged> evento se desencadena cuando el usuario navega a una nueva celda. Cuando el usuario navega a una nueva tabla a través de relaciones de elementos primarios y secundarios, el <xref:System.Windows.Forms.DataGrid.Navigate> provoca el evento. El <xref:System.Windows.Forms.DataGrid.BackButtonClick> evento se desencadena cuando el usuario hace clic en el botón Atrás cuando el usuario está viendo una tabla secundaria y el <xref:System.Windows.Forms.DataGrid.ShowParentDetailsButtonClick> evento se provoca cuando se hace clic en el icono de filas primarias de mostrar u ocultar.  
  
## <a name="see-also"></a>Vea también  
 [DataGrid (Control)](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Cómo: enlazar el Control DataGrid de formularios Windows Forms a un origen de datos](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)   
 [Cómo: agregar tablas y columnas a Windows Forms DataGrid (Control)](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)   
 [Cómo: eliminar u ocultar columnas en Windows Forms DataGrid Control](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)   
 [Cómo: dar formato el Control DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-the-windows-forms-datagrid-control.md)