---
title: Información general sobre GridView
ms.date: 03/30/2017
helpviewer_keywords:
- GridView view mode [WPF]
- ListView controls [WPF], GridView view mode
- controls [WPF], ListView
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
ms.openlocfilehash: 6da556296679de1161f609a7731c6fbf14e94730
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966469"
---
# <a name="gridview-overview"></a>Información general sobre GridView
<xref:System.Windows.Controls.GridView>el modo de vista es uno de los modos de <xref:System.Windows.Controls.ListView> vista de un control. La <xref:System.Windows.Controls.GridView> clase y sus clases auxiliares permiten a usted y a los usuarios ver las colecciones de elementos de una tabla que normalmente utiliza los botones como encabezados de columna interactivos. En este tema se <xref:System.Windows.Controls.GridView> presenta la clase y se describe su uso.  

<a name="DefiningaListViewthatusesGridViewView"></a>   
## <a name="what-is-a-gridview-view"></a>¿Qué es una vista GridView?  
 El <xref:System.Windows.Controls.GridView> modo de vista muestra una lista de elementos de datos enlazando los campos de datos a las columnas y mostrando un encabezado de columna para identificar el campo. El estilo <xref:System.Windows.Controls.GridView> predeterminado implementa los botones como encabezados de columna. Mediante el uso de botones para los encabezados de columna, puede implementar capacidades importantes de interacción con el usuario; por ejemplo, los usuarios pueden hacer clic en el encabezado <xref:System.Windows.Controls.GridView> de columna para ordenar los datos según el contenido de una columna específica.  
  
> [!NOTE]
> Los controles de botón <xref:System.Windows.Controls.GridView> que usa para los encabezados de columna se <xref:System.Windows.Controls.Primitives.ButtonBase>derivan de.  
  
 En la ilustración siguiente se <xref:System.Windows.Controls.GridView> muestra una <xref:System.Windows.Controls.ListView> vista de contenido.  
    
 ![Captura de pantalla que muestra la vista de GridView del contenido de ListView.](./media/gridview-overview/styled-listview-content.png)  
  
 <xref:System.Windows.Controls.GridView>las columnas se representan <xref:System.Windows.Controls.GridViewColumn> mediante objetos, que pueden ajustarse automáticamente a su contenido. Opcionalmente, puede establecer explícitamente un <xref:System.Windows.Controls.GridViewColumn> valor de en un ancho específico. Puede cambiar el tamaño de las columnas si arrastra la barra de redimensionamiento que se encuentra entre los encabezados de columna. También puede Agregar, quitar, reemplazar y reordenar columnas de forma dinámica, ya que esta funcionalidad está <xref:System.Windows.Controls.GridView>integrada en. Sin embargo <xref:System.Windows.Controls.GridView> , no puede actualizar directamente los datos que muestra.  
  
 En el ejemplo siguiente se muestra cómo definir <xref:System.Windows.Controls.GridView> un que muestra los datos de los empleados. En este ejemplo, <xref:System.Windows.Controls.ListView> `EmployeeInfoDataSource` define como <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Las definiciones de propiedad <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> de <xref:System.Windows.Controls.GridViewColumn> enlazar `EmployeeInfoDataSource` contenido a categorías de datos.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 En la siguiente ilustración se muestra la tabla creada en el ejemplo anterior. El control GridView muestra los datos de un objeto ItemsSource:
    
 ![Captura de pantalla que muestra un control ListView con resultados de GridView.](./media/gridview-overview/listview-gridview-output.jpg)  
  
<a name="GridViewLayoutandStyle"></a>   
## <a name="gridview-layout-and-style"></a>Estilo y diseño de GridView  
 Las celdas de columna y el encabezado de columna <xref:System.Windows.Controls.GridViewColumn> de tienen el mismo ancho. De forma predeterminada, cada columna ajusta su anchura para ajustarse al contenido. Opcionalmente, puede establecer un ancho de columna fijo.  
  
 El contenido de datos relacionado se muestra en filas horizontales. Por ejemplo, en la ilustración anterior, el apellido, el nombre y el número de identificador de cada empleado se muestran como un conjunto porque aparecen en una fila horizontal.  
  
<a name="DefiningandStylingColumnsinaGridView"></a>   
### <a name="defining-and-styling-columns-in-a-gridview"></a>Definición y aplicación de estilos de columna en GridView  
 Al definir el campo de datos que se va <xref:System.Windows.Controls.GridViewColumn>a mostrar en <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>un, utilice <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A> las propiedades, <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>o. La <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> propiedad tiene prioridad sobre cualquiera de las propiedades de la plantilla.  
  
 Para especificar la alineación del contenido de una columna de <xref:System.Windows.Controls.GridView>, defina un. <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> No use las propiedades <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> y <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> para <xref:System.Windows.Controls.ListView> el contenido que se muestra <xref:System.Windows.Controls.GridView>mediante.  
  
 Para especificar las propiedades de plantilla y estilo de los encabezados de columna <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridViewColumn>use las <xref:System.Windows.Controls.GridViewColumnHeader> clases, y. Para más información, consulte [Información general sobre plantillas y estilos de encabezado de columna en modo GridView](gridview-column-header-styles-and-templates-overview.md).  
  
<a name="AddingVisualElementstoaGridViewView"></a>   
### <a name="adding-visual-elements-to-a-gridview"></a>Incorporación de elementos visuales a un control GridView  
 Para agregar elementos visuales, <xref:System.Windows.Controls.CheckBox> como controles y <xref:System.Windows.Controls.Button> , a un <xref:System.Windows.Controls.GridView> modo de vista, use plantillas o estilos.  
  
 Si define explícitamente un elemento visual como un elemento de datos, solo puede aparecer una vez en <xref:System.Windows.Controls.GridView>. Esta limitación existe porque un elemento puede tener un único elemento primario y, por tanto, puede aparecer solo una vez en el árbol visual.  
  
<a name="StylingRowsinaGridViewView"></a>   
### <a name="styling-rows-in-a-gridview"></a>Aplicación de estilos a filas en GridView  
 Utilice las <xref:System.Windows.Controls.GridViewRowPresenter> clases <xref:System.Windows.Controls.GridViewHeaderRowPresenter> y para dar formato y mostrar las filas de <xref:System.Windows.Controls.GridView>un. Para obtener un ejemplo de cómo aplicar estilo a las <xref:System.Windows.Controls.GridView> filas en un modo de vista, vea [aplicar un estilo a una fila en un control ListView que implementa un control GridView](how-to-style-a-row-in-a-listview-that-implements-a-gridview.md).  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>   
### <a name="alignment-issues-when-you-use-itemcontainerstyle"></a>Problemas de alineación al usar ItemContainerStyle  
 Para evitar problemas de alineación entre los encabezados de columna y las celdas, no establezca una propiedad o especifique una plantilla que afecte al ancho de un <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>elemento en. Por ejemplo, no establezca la <xref:System.Windows.FrameworkElement.Margin%2A> propiedad o especifique un <xref:System.Windows.Controls.ControlTemplate> que agregue un <xref:System.Windows.Controls.CheckBox> a un <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> que se define en un <xref:System.Windows.Controls.ListView> control. En su lugar, especifique las propiedades y plantillas que afectan al ancho de columna directamente en las <xref:System.Windows.Controls.GridView> clases que definen un modo de vista.  
  
 Por ejemplo, para agregar un <xref:System.Windows.Controls.CheckBox> a las filas en <xref:System.Windows.Controls.GridView> el modo de <xref:System.Windows.Controls.CheckBox> vista <xref:System.Windows.DataTemplate>, agregue a y, a continuación, <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> establezca la propiedad <xref:System.Windows.DataTemplate>en.  
  
<a name="InteractingwithaGridViewControl"></a>   
## <a name="user-interactions-with-a-gridview"></a>Interacciones del usuario con GridView  
 Cuando se utiliza un <xref:System.Windows.Controls.GridView> en la aplicación, los usuarios pueden interactuar con el formato <xref:System.Windows.Controls.GridView>de y modificarlo. Por ejemplo, los usuarios pueden reordenar las columnas, cambiar el tamaño de una columna, seleccionar elementos en una tabla y desplazarse por el contenido. También puede definir un controlador de eventos para que responda cuando un usuario hace clic en el botón de encabezado de columna. El controlador de eventos puede realizar operaciones como ordenar los datos que se muestran en <xref:System.Windows.Controls.GridView> de acuerdo con el contenido de una columna.  
  
 En la lista siguiente se describen con más detalle las capacidades de <xref:System.Windows.Controls.GridView> uso de para la interacción con el usuario:  
  
- **Reordenar columnas con el método de arrastrar y colocar.**  
  
     Los usuarios pueden reordenar las <xref:System.Windows.Controls.GridView> columnas en un presionando el botón primario del mouse mientras se encuentra sobre un encabezado de columna y arrastrando después esa columna hasta una nueva posición. Mientras el usuario arrastra el encabezado de columna, se muestra una versión flotante del encabezado, así como una línea negra sólida que muestra dónde insertar la columna.  
  
     Si desea modificar el estilo predeterminado de la versión flotante de un <xref:System.Windows.Controls.ControlTemplate> encabezado, especifique para un <xref:System.Windows.Controls.GridViewColumnHeader> tipo que se desencadene cuando la <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> propiedad esté establecida en <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>. Para más información, consulte [Crear un estilo para un encabezado de columna de GridView arrastrado](how-to-create-a-style-for-a-dragged-gridview-column-header.md).  
  
- **Cambiar el tamaño de una columna para ajustarla a su contenido.**  
  
     Los usuarios pueden hacer doble clic en la barra de redimensionamiento a la derecha de un encabezado de columna para cambiar el tamaño de una columna con el fin de ajustarla a su contenido.  
  
    > [!NOTE]
    > Puede establecer la <xref:System.Windows.Controls.GridViewColumn.Width%2A> propiedad en `Double.NaN` para generar el mismo efecto.  
  
- **Seleccionar elementos de fila.**  
  
     Los usuarios pueden seleccionar uno o más elementos en <xref:System.Windows.Controls.GridView>un.  
  
     Si desea cambiar el <xref:System.Windows.Style> de un elemento seleccionado, consulte [usar desencadenadores para aplicar estilo a los elementos seleccionados en un control ListView](how-to-use-triggers-to-style-selected-items-in-a-listview.md).  
  
- **Desplazarse para ver el contenido que inicialmente no aparece en la pantalla.**  
  
     Si el tamaño de <xref:System.Windows.Controls.GridView> no es lo suficientemente grande como para mostrar todos los elementos, los usuarios se pueden desplazar horizontal o verticalmente con barras de desplazamiento, que son proporcionadas por un <xref:System.Windows.Controls.ScrollViewer> control. Un <xref:System.Windows.Controls.Primitives.ScrollBar> está oculto si todo el contenido está visible en una dirección específica. Los encabezados de columna no se desplazan con una barra de desplazamiento vertical, sino que se desplazan en horizontal.  
  
- **Interactuar con las columnas haciendo clic en los botones de encabezado de columna.**  
  
     Cuando los usuarios hacen clic en un botón de encabezado de columna, pueden ordenar los datos que se muestran en la columna si disponen de un algoritmo de ordenación.  
  
     Puede controlar el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> para los botones de encabezado de columna con el fin de proporcionar funcionalidad como un algoritmo de ordenación. Para controlar el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento de un encabezado de columna único, establezca un controlador <xref:System.Windows.Controls.GridViewColumnHeader>de eventos en. Para establecer un controlador de eventos que controle el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento para todos los encabezados de columna, establezca el controlador en el <xref:System.Windows.Controls.ListView> control.  
  
<a name="Obtaining_Other_Custom_Views"></a>   
## <a name="obtaining-other-custom-views"></a>Obtención de otras vistas personalizadas  
 La <xref:System.Windows.Controls.GridView> clase, que se deriva de la <xref:System.Windows.Controls.ViewBase> clase abstracta, es solo uno de los posibles modos de vista para <xref:System.Windows.Controls.ListView> la clase. Puede crear otras vistas personalizadas para <xref:System.Windows.Controls.ListView> Si deriva de la <xref:System.Windows.Controls.ViewBase> clase. Para obtener un ejemplo de un modo de visualización personalizado, vea [Crear un modo de vista personalizado para un control ListView](how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="GridViewSupportingClasses"></a>   
## <a name="gridview-supporting-classes"></a>Clases que admiten GridView  
 Las clases siguientes admiten <xref:System.Windows.Controls.GridView> el modo de vista.  
  
- <xref:System.Windows.Controls.GridViewColumn>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GridViewRowPresenter>  
  
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
  
- <xref:System.Windows.Controls.GridViewColumnCollection>  
  
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
  
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
