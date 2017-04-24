---
title: "Informaci&#243;n general sobre GridView | Microsoft Docs"
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
  - "controles, ListView"
  - "modo de vista para GridView"
  - "ListView (controles), modo de vista para GridView"
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
caps.latest.revision: 26
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Informaci&#243;n general sobre GridView
El modo de vista <xref:System.Windows.Controls.GridView> es uno de los modos de vista de los controles <xref:System.Windows.Controls.ListView>.  La clase <xref:System.Windows.Controls.GridView> y sus clases de respaldo permiten que programadores y usuarios vean las colecciones de elementos en una tabla que normalmente utiliza botones como encabezados de columna interactivos.  En este tema se presenta la clase <xref:System.Windows.Controls.GridView> y se describe su uso.  
  
   
  
<a name="DefiningaListViewthatusesGridViewView"></a>   
## ¿Qué es una vista GridView?  
 El modo de vista <xref:System.Windows.Controls.GridView> muestra una lista de elementos de datos enlazando campos de datos a columnas y mostrando un encabezado de columna para identificar el campo.  El estilo de <xref:System.Windows.Controls.GridView> predeterminado implementa botones como encabezados de columna.  Utilizando botones para los encabezados de columna, puede implementar importantes funciones de interacción con el usuario; por ejemplo, el usuario puede hacer clic en el encabezado de columna para ordenar los datos de <xref:System.Windows.Controls.GridView> según el contenido de una columna concreta.  
  
> [!NOTE]
>  Los controles de botón que <xref:System.Windows.Controls.GridView> utiliza para los encabezados de columna se derivan de <xref:System.Windows.Controls.Primitives.ButtonBase>.  
  
 En la ilustración siguiente se muestra una vista de <xref:System.Windows.Controls.GridView> de contenido de <xref:System.Windows.Controls.ListView>.  
  
 **Vista de GridView de contenido de ListView**  
  
 ![ListView con estilo](../../../../docs/framework/wpf/controls/media/styledlistview.png "StyledListView")  
  
 Las columnas de <xref:System.Windows.Controls.GridView> se representan mediante objetos <xref:System.Windows.Controls.GridViewColumn>, que pueden ajustar su tamaño automáticamente al contenido.  Si lo prefiere, puede establecer explícitamente un objeto <xref:System.Windows.Controls.GridViewColumn> en un ancho específico.  Puede cambiar el tamaño de las columnas arrastrando el agarrador que aparece entre los encabezados de columna.  También puede agregar, quitar, reemplazar y reordenar dinámicamente las columnas, porque esta funcionalidad está integrada en <xref:System.Windows.Controls.GridView>.  Sin embargo, <xref:System.Windows.Controls.GridView> no puede actualizar directamente los datos que muestra.  
  
 En el ejemplo siguiente se muestra cómo definir un objeto <xref:System.Windows.Controls.GridView> que muestra datos de empleados.  En este ejemplo, <xref:System.Windows.Controls.ListView> define `EmployeeInfoDataSource` como <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>.  Las definiciones de propiedad de <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> enlazan el contenido de <xref:System.Windows.Controls.GridViewColumn> a las categorías de datos de `EmployeeInfoDataSource`.  
  
 [!code-xml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 En la ilustración siguiente se muestra la tabla creada por el ejemplo anterior.  
  
 **GridView que muestra los datos de ItemsSource**  
  
 ![ListView con resultado GridView](../../../../docs/framework/wpf/controls/media/listviewgridview.png "ListViewGridView")  
  
<a name="GridViewLayoutandStyle"></a>   
## Diseño y estilo de GridView  
 Las celdas y el encabezado de las columnas de un control <xref:System.Windows.Controls.GridViewColumn> tienen el mismo ancho.  De manera predeterminada, el ancho de cada columna se ajusta a su contenido.  Opcionalmente, puede establecer una columna en un ancho fijo.  
  
 El contenido de datos relacionados se muestra en filas horizontales.  Por ejemplo, en la ilustración anterior, el apellido, nombre y número del Id. de cada empleado se muestran como un conjunto porque aparecen en una fila horizontal.  
  
<a name="DefiningandStylingColumnsinaGridView"></a>   
### Definir columnas y aplicarles un estilo en un control GridView  
 Al definir el campo de datos que se mostrará en un control <xref:System.Windows.Controls.GridViewColumn>, se utilizan las propiedades <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>, <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> o <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A>.  La propiedad <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> tiene precedencia sobre cualquiera de las propiedades de plantilla.  
  
 Para especificar la alineación del contenido de una columna de <xref:System.Windows.Controls.GridView>, defina <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>.  No use las propiedades <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> y <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> para contenido de <xref:System.Windows.Controls.ListView> que se muestre mediante <xref:System.Windows.Controls.GridView>.  
  
 Para especificar las propiedades de plantilla y de estilo de los encabezados de columna, se utilizan las clases <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridViewColumn> y <xref:System.Windows.Controls.GridViewColumnHeader>.  Para obtener más información, vea [Información general sobre plantillas y estilos de encabezado de columna en modo GridView](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).  
  
<a name="AddingVisualElementstoaGridViewView"></a>   
### Agregar elementos visuales a un control GridView  
 Para agregar elementos visuales, como controles <xref:System.Windows.Controls.CheckBox> y <xref:System.Windows.Controls.Button>, a un modo de vista <xref:System.Windows.Controls.GridView>, se utilizan plantillas o estilos.  
  
 Si define explícitamente un elemento visual como un elemento de datos, puede aparecer una sola vez en un <xref:System.Windows.Controls.GridView>.  La razón de ser de esta es que un elemento puede tener un único elemento primario y, por consiguiente, puede aparecer una sola vez en el [árbol visual](GTMT).  
  
<a name="StylingRowsinaGridViewView"></a>   
### Aplicar estilo a las filas de un control GridView  
 Las clases <xref:System.Windows.Controls.GridViewRowPresenter> y <xref:System.Windows.Controls.GridViewHeaderRowPresenter> se utilizan para dar formato y mostrar las filas de <xref:System.Windows.Controls.GridView>.  Para obtener un ejemplo de cómo aplicar un estilo a las filas de un modo de vista <xref:System.Windows.Controls.GridView>, vea [Aplicar un estilo a una fila en un control ListView que implementa una clase GridView](../../../../docs/framework/wpf/controls/how-to-style-a-row-in-a-listview-that-implements-a-gridview.md).  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>   
### Problemas de alineación al utilizar ItemContainerStyle  
 Para evitar los problemas de alineación entre los encabezados y las celdas de las columnas, no establezca ninguna propiedad ni especifique ninguna plantilla que afecte al ancho de un elemento en una propiedad <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>.  Por ejemplo, no establezca la propiedad <xref:System.Windows.FrameworkElement.Margin%2A> ni especifique un objeto <xref:System.Windows.Controls.ControlTemplate> que agregue un control <xref:System.Windows.Controls.CheckBox> a una propiedad <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> definida en un control <xref:System.Windows.Controls.ListView>.  En su lugar, especifique las propiedades y plantillas que afectan directamente al ancho de columna en las clases que definen un modo de vista <xref:System.Windows.Controls.GridView>.  
  
 Por ejemplo, para agregar un control <xref:System.Windows.Controls.CheckBox> a las filas de un modo de vista <xref:System.Windows.Controls.GridView>, agregue el control <xref:System.Windows.Controls.CheckBox> a un objeto <xref:System.Windows.DataTemplate> y, a continuación, establezca la propiedad <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> en ese objeto <xref:System.Windows.DataTemplate>.  
  
<a name="InteractingwithaGridViewControl"></a>   
## Interacciones del usuario con un control GridView  
 Cuando se utiliza un control <xref:System.Windows.Controls.GridView> en la aplicación, el usuario puede interactuar con él y modificar el formato del <xref:System.Windows.Controls.GridView>.  Por ejemplo, los usuarios pueden reordenar las columnas, cambiar el tamaño una columna, seleccionar elementos en una tabla y desplazarse por el contenido.  También se puede definir un controlador de eventos que responda cuando un usuario haga clic en el botón de encabezado de columna.  El controlador de eventos puede realizar operaciones tales como ordenar los datos que se muestran en <xref:System.Windows.Controls.GridView> según el contenido de una columna.  
  
 En la lista siguiente se describen con más detalle las funciones de interacción con el usuario de un control <xref:System.Windows.Controls.GridView>:  
  
-   **Reordenar columnas mediante el método de arrastrar y colocar.**  
  
     Para reordenar las columnas de un control <xref:System.Windows.Controls.GridView>, el usuario presiona el botón primario con el cursor situado encima de un encabezado de columna y la arrastra hasta su nueva posición.  Mientras el usuario arrastra el encabezado de columna, se muestra una versión flotante del encabezado, así como una línea negra sólido que muestra dónde insertar la columna.  
  
     Si desea modificar el estilo predeterminado de la versión flotante de un encabezado, especifique un objeto <xref:System.Windows.Controls.ControlTemplate> para un tipo <xref:System.Windows.Controls.GridViewColumnHeader> que se active cuando la propiedad <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> se establezca en <xref:System.Windows.Controls.GridViewColumnHeaderRole>.  Para obtener más información, vea [Crear un estilo para un encabezado de columna de GridView arrastrado](../../../../docs/framework/wpf/controls/how-to-create-a-style-for-a-dragged-gridview-column-header.md).  
  
-   **Ajustar el tamaño de una columna a su contenido**  
  
     El usuario puede hacer doble clic en el agarrador situado a la derecha de un encabezado de columna para ajustar el tamaño de ésta a su contenido.  
  
    > [!NOTE]
    >  Puede establecer la propiedad <xref:System.Windows.Controls.GridViewColumn.Width%2A> en `Double.NaN` para crear el mismo efecto.  
  
-   **Seleccionar elementos de fila.**  
  
     El usuario puede seleccionar uno o más elementos de un control <xref:System.Windows.Controls.GridView>.  
  
     Si desea cambiar el objeto <xref:System.Windows.Style> de un elemento seleccionado, vea [Utilizar desencadenadores para aplicar un estilo a los elementos seleccionados en un control ListView](../../../../docs/framework/wpf/controls/how-to-use-triggers-to-style-selected-items-in-a-listview.md).  
  
-   **Desplazarse para ver contenido que no se muestra inicialmente en la pantalla.**  
  
     Si el tamaño de <xref:System.Windows.Controls.GridView> no es suficiente para mostrar todos los elementos, el usuario puede desplazarse en sentido horizontal o vertical mediante las barras de desplazamiento proporcionadas por un control <xref:System.Windows.Controls.ScrollViewer>.  Un control <xref:System.Windows.Controls.Primitives.ScrollBar> está oculto si está visible todo el contenido en una dirección concreta.  Los encabezados de columna no se desplazan con una barra de desplazamiento vertical, pero sí horizontalmente.  
  
-   **Interactuar con columnas haciendo clic en los botones de encabezado de columna.**  
  
     Cuando el usuario hace clic en un botón de encabezado de columna, puede ordenar los datos que se muestran en ella siempre que el programador haya proporcionado un algoritmo de ordenación.  
  
     Para proporcionar funcionalidad del tipo de un algoritmo de ordenación, controle el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> para los botones de encabezado de columna.  Para controlar el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> para un solo encabezado de columna, establezca un controlador de eventos para <xref:System.Windows.Controls.GridViewColumnHeader>.  Para establecer un controlador de eventos que controle el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> para todos los encabezados de columna, establezca el controlador para el control <xref:System.Windows.Controls.ListView>.  
  
<a name="Obtaining_Other_Custom_Views"></a>   
## Obtener otras vistas personalizadas  
 La clase <xref:System.Windows.Controls.GridView>, que se deriva de la clase abstracta <xref:System.Windows.Controls.ViewBase>, tan sólo es uno de los modos de vista posibles de la clase <xref:System.Windows.Controls.ListView>.  Puede crear otras vistas personalizadas para <xref:System.Windows.Controls.ListView> derivando de la clase <xref:System.Windows.Controls.ViewBase>.  Para obtener un ejemplo de un modo de vista personalizado, vea [Crear un modo de vista personalizado para un control ListView](../../../../docs/framework/wpf/controls/how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="GridViewSupportingClasses"></a>   
## Clases que admiten GridView  
 Las clases siguientes admiten el modo de vista <xref:System.Windows.Controls.GridView>.  
  
-   <xref:System.Windows.Controls.GridViewColumn>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeader>  
  
-   <xref:System.Windows.Controls.GridViewRowPresenter>  
  
-   <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
  
-   <xref:System.Windows.Controls.GridViewColumnCollection>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
  
## Vea también  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.ListViewItem>   
 <xref:System.Windows.Controls.GridViewColumn>   
 <xref:System.Windows.Controls.GridViewColumnHeader>   
 <xref:System.Windows.Controls.GridViewRowPresenter>   
 <xref:System.Windows.Controls.GridViewHeaderRowPresenter>   
 <xref:System.Windows.Controls.ViewBase>   
 [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Ordenar una columna de GridView cuando se hace clic en un encabezado](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)