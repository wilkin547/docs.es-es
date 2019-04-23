---
title: Información general sobre GridView
ms.date: 03/30/2017
helpviewer_keywords:
- GridView view mode [WPF]
- ListView controls [WPF], GridView view mode
- controls [WPF], ListView
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
ms.openlocfilehash: d2f55db90fb130416ee4dcb15d440b6d367c0b06
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59201304"
---
# <a name="gridview-overview"></a>Información general sobre GridView
<xref:System.Windows.Controls.GridView> modo de vista es uno de los modos de visualización para un <xref:System.Windows.Controls.ListView> control. La <xref:System.Windows.Controls.GridView> clase y sus clases auxiliares permiten que usted y a los usuarios ver colecciones de elementos en una tabla que normalmente utiliza botones como encabezados de columna interactivos. Este tema se presenta la <xref:System.Windows.Controls.GridView> clase y describe su uso.  

<a name="DefiningaListViewthatusesGridViewView"></a>   
## <a name="what-is-a-gridview-view"></a>¿Qué es una vista GridView?  
 El <xref:System.Windows.Controls.GridView> modo muestra una lista de elementos de datos por campos de datos de enlace a las columnas y mostrar un encabezado de columna para identificar el campo de vista. El valor predeterminado <xref:System.Windows.Controls.GridView> estilo implementa botones como encabezados de columna. Mediante los botones para los encabezados de columna, puede implementar capacidades de interacción de usuario importantes; Por ejemplo, los usuarios hacer clic en el encabezado de columna para ordenar <xref:System.Windows.Controls.GridView> datos según el contenido de una columna específica.  
  
> [!NOTE]
>  Controla el botón que <xref:System.Windows.Controls.GridView> se derivan de los usos de los encabezados de columna <xref:System.Windows.Controls.Primitives.ButtonBase>.  
  
 La siguiente ilustración muestra un <xref:System.Windows.Controls.GridView> ver de <xref:System.Windows.Controls.ListView> contenido.  
    
 ![Captura de pantalla que muestra la vista GridView de contenido de ListView.](./media/gridview-overview/styled-listview-content.png)  
  
 <xref:System.Windows.Controls.GridView> las columnas se representan mediante <xref:System.Windows.Controls.GridViewColumn> objetos, que pueden ajustarse automáticamente a su contenido. Si lo desea, puede establecer explícitamente un <xref:System.Windows.Controls.GridViewColumn> a un ancho específico. Puede cambiar el tamaño de las columnas si arrastra la barra de redimensionamiento que se encuentra entre los encabezados de columna. Dinámicamente también puede agregar, quitar, reemplazar y reordenar columnas porque esta funcionalidad está integrada en <xref:System.Windows.Controls.GridView>. Sin embargo, <xref:System.Windows.Controls.GridView> no se puede actualizar directamente los datos que muestra.  
  
 El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.GridView> que muestra los datos de empleados. En este ejemplo, <xref:System.Windows.Controls.ListView> define la `EmployeeInfoDataSource` como el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Las definiciones de propiedad de <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> enlazar <xref:System.Windows.Controls.GridViewColumn> contenido a `EmployeeInfoDataSource` categorías de datos.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 En la siguiente ilustración se muestra la tabla creada en el ejemplo anterior. El control GridView muestra los datos de un objeto ItemsSource:
    
 ![Captura de pantalla que muestra un ListView con resultado GridView.](./media/gridview-overview/listview-gridview-output.jpg)  
  
<a name="GridViewLayoutandStyle"></a>   
## <a name="gridview-layout-and-style"></a>Estilo y diseño de GridView  
 Las celdas de columna y el encabezado de columna de un <xref:System.Windows.Controls.GridViewColumn> tienen la misma anchura. De forma predeterminada, cada columna ajusta su anchura para ajustarse al contenido. Opcionalmente, puede establecer un ancho de columna fijo.  
  
 El contenido de datos relacionado se muestra en filas horizontales. Por ejemplo, en la ilustración anterior, el apellido, el nombre y el número de identificador de cada empleado se muestran como un conjunto porque aparecen en una fila horizontal.  
  
<a name="DefiningandStylingColumnsinaGridView"></a>   
### <a name="defining-and-styling-columns-in-a-gridview"></a>Definición y aplicación de estilos de columna en GridView  
 Al definir el campo de datos para mostrar en un <xref:System.Windows.Controls.GridViewColumn>, utilice el <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>, <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>, o <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A> propiedades. El <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> propiedad tiene precedencia sobre cualquiera de las propiedades de plantilla.  
  
 Para especificar la alineación del contenido de una columna de un <xref:System.Windows.Controls.GridView>, defina un <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>. No utilice el <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> y <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> las propiedades de <xref:System.Windows.Controls.ListView> contenido que se muestra mediante el uso de un <xref:System.Windows.Controls.GridView>.  
  
 Para especificar las propiedades de plantilla y estilo de los encabezados de columna, utilice el <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridViewColumn>, y <xref:System.Windows.Controls.GridViewColumnHeader> clases. Para más información, consulte [Información general sobre plantillas y estilos de encabezado de columna en modo GridView](gridview-column-header-styles-and-templates-overview.md).  
  
<a name="AddingVisualElementstoaGridViewView"></a>   
### <a name="adding-visual-elements-to-a-gridview"></a>Incorporación de elementos visuales a un control GridView  
 Para agregar elementos visuales, tales como <xref:System.Windows.Controls.CheckBox> y <xref:System.Windows.Controls.Button> controles, un <xref:System.Windows.Controls.GridView> modo de vista, use plantillas o estilos.  
  
 Si se define explícitamente un elemento visual como un elemento de datos, puede aparecer solo una vez en un <xref:System.Windows.Controls.GridView>. Esta limitación existe porque un elemento puede tener un único elemento primario y, por tanto, puede aparecer solo una vez en el árbol visual.  
  
<a name="StylingRowsinaGridViewView"></a>   
### <a name="styling-rows-in-a-gridview"></a>Aplicación de estilos a filas en GridView  
 Use la <xref:System.Windows.Controls.GridViewRowPresenter> y <xref:System.Windows.Controls.GridViewHeaderRowPresenter> clases para dar formato y mostrar las filas de una <xref:System.Windows.Controls.GridView>. Para obtener un ejemplo de cómo aplicar estilos a filas en un <xref:System.Windows.Controls.GridView> el modo de vista, vea [aplicar estilo a una fila de un ListView que implementa un control GridView](how-to-style-a-row-in-a-listview-that-implements-a-gridview.md).  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>   
### <a name="alignment-issues-when-you-use-itemcontainerstyle"></a>Problemas de alineación al usar ItemContainerStyle  
 Para evitar problemas de alineación entre los encabezados de columna y las celdas, no establezca una propiedad o especificar una plantilla que afecta al ancho de un elemento en un <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>. Por ejemplo, no establezca la <xref:System.Windows.FrameworkElement.Margin%2A> propiedad o especificar un <xref:System.Windows.Controls.ControlTemplate> que agrega un <xref:System.Windows.Controls.CheckBox> a un <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> que se define en un <xref:System.Windows.Controls.ListView> control. En su lugar, especifique las propiedades y plantillas que afectan al ancho de columna directamente en las clases que definen un <xref:System.Windows.Controls.GridView> modo de vista.  
  
 Por ejemplo, para agregar un <xref:System.Windows.Controls.CheckBox> a las filas de <xref:System.Windows.Controls.GridView> modo de vista, agregue el <xref:System.Windows.Controls.CheckBox> a un <xref:System.Windows.DataTemplate>y, a continuación, establezca el <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> propiedad a la que <xref:System.Windows.DataTemplate>.  
  
<a name="InteractingwithaGridViewControl"></a>   
## <a name="user-interactions-with-a-gridview"></a>Interacciones del usuario con GridView  
 Cuando se usa un <xref:System.Windows.Controls.GridView> en la aplicación, los usuarios pueden interactuar con y modificar el formato de la <xref:System.Windows.Controls.GridView>. Por ejemplo, los usuarios pueden reordenar las columnas, cambiar el tamaño de una columna, seleccionar elementos en una tabla y desplazarse por el contenido. También puede definir un controlador de eventos para que responda cuando un usuario hace clic en el botón de encabezado de columna. El controlador de eventos puede realizar operaciones tales como ordenar los datos que se muestran en el <xref:System.Windows.Controls.GridView> según el contenido de una columna.  
  
 En la lista siguiente describe con más detalle las capacidades de <xref:System.Windows.Controls.GridView> para la interacción del usuario:  
  
-   **Reordenar columnas con el método de arrastrar y colocar.**  
  
     Los usuarios pueden reordenar las columnas de una <xref:System.Windows.Controls.GridView> al presionar el botón primario del mouse mientras se encuentra sobre un encabezado de columna y, a continuación, arrastrar la columna a una nueva posición. Mientras el usuario arrastra el encabezado de columna, se muestra una versión flotante del encabezado, así como una línea negra sólida que muestra dónde insertar la columna.  
  
     Especifique si desea modificar el estilo predeterminado para la versión flotante de un encabezado, un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.GridViewColumnHeader> tipo que se desencadena cuando el <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> propiedad está establecida en <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>. Para más información, consulte [Crear un estilo para un encabezado de columna de GridView arrastrado](how-to-create-a-style-for-a-dragged-gridview-column-header.md).  
  
-   **Cambiar el tamaño de una columna para ajustarla a su contenido.**  
  
     Los usuarios pueden hacer doble clic en la barra de redimensionamiento a la derecha de un encabezado de columna para cambiar el tamaño de una columna con el fin de ajustarla a su contenido.  
  
    > [!NOTE]
    >  Puede establecer el <xref:System.Windows.Controls.GridViewColumn.Width%2A> propiedad `Double.NaN` para producir el mismo efecto.  
  
-   **Seleccionar elementos de fila.**  
  
     Los usuarios pueden seleccionar uno o varios elementos en un <xref:System.Windows.Controls.GridView>.  
  
     Si desea cambiar la <xref:System.Windows.Style> de un elemento seleccionado, vea [utilizar desencadenadores para el estilo de los elementos seleccionados en un ListView](how-to-use-triggers-to-style-selected-items-in-a-listview.md).  
  
-   **Desplazarse para ver el contenido que inicialmente no aparece en la pantalla.**  
  
     Si el tamaño de la <xref:System.Windows.Controls.GridView> es no suficientemente grande como para mostrar todos los elementos, los usuarios pueden desplazarse horizontalmente o verticalmente mediante el uso de las barras de desplazamiento, que se proporciona un <xref:System.Windows.Controls.ScrollViewer> control. Un <xref:System.Windows.Controls.Primitives.ScrollBar> se oculta si todo el contenido está visible en una dirección específica. Los encabezados de columna no se desplazan con una barra de desplazamiento vertical, sino que se desplazan en horizontal.  
  
-   **Interactuar con las columnas haciendo clic en los botones de encabezado de columna.**  
  
     Cuando los usuarios hacen clic en un botón de encabezado de columna, pueden ordenar los datos que se muestran en la columna si disponen de un algoritmo de ordenación.  
  
     Puede controlar la <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos para los botones de encabezado de columna con el fin de ofrecer funcionalidades como un algoritmo de ordenación. Para controlar la <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos para un solo encabezado de columna, establezca un controlador de eventos en el <xref:System.Windows.Controls.GridViewColumnHeader>. Para establecer un controlador de eventos que controla la <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos para todos los encabezados de columna, establezca el controlador en el <xref:System.Windows.Controls.ListView> control.  
  
<a name="Obtaining_Other_Custom_Views"></a>   
## <a name="obtaining-other-custom-views"></a>Obtención de otras vistas personalizadas  
 El <xref:System.Windows.Controls.GridView> (clase), que se deriva el <xref:System.Windows.Controls.ViewBase> clase abstracta, es solo uno de los posibles modos de visualización para el <xref:System.Windows.Controls.ListView> clase. Puede crear otras vistas personalizadas para <xref:System.Windows.Controls.ListView> derivando de la <xref:System.Windows.Controls.ViewBase> clase. Para obtener un ejemplo de un modo de visualización personalizado, vea [Crear un modo de vista personalizado para un control ListView](how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="GridViewSupportingClasses"></a>   
## <a name="gridview-supporting-classes"></a>Clases que admiten GridView  
 La siguiente las clases que admiten el <xref:System.Windows.Controls.GridView> modo de vista.  
  
-   <xref:System.Windows.Controls.GridViewColumn>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeader>  
  
-   <xref:System.Windows.Controls.GridViewRowPresenter>  
  
-   <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
  
-   <xref:System.Windows.Controls.GridViewColumnCollection>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Controls.GridViewColumn>
- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.ViewBase>
- [Información general sobre ListView](listview-overview.md)
- [Ordenar una columna de GridView cuando se hace clic en un encabezado](how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [Temas "Cómo..."](listview-how-to-topics.md)
