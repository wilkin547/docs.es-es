---
title: Información general sobre GridView
ms.date: 03/30/2017
helpviewer_keywords:
- GridView view mode [WPF]
- ListView controls [WPF], GridView view mode
- controls [WPF], ListView
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
ms.openlocfilehash: 98bc7985172cabeab19469af4b4c21e13a6bce73
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181900"
---
# <a name="gridview-overview"></a>Información general sobre GridView
<xref:System.Windows.Controls.GridView>modo de vista es uno <xref:System.Windows.Controls.ListView> de los modos de vista para un control. La <xref:System.Windows.Controls.GridView> clase y sus clases auxiliares le permiten a usted y a los usuarios ver colecciones de elementos en una tabla que normalmente usa botones como encabezados de columna interactivos. En este tema <xref:System.Windows.Controls.GridView> se presenta la clase y se describe su uso.  

<a name="DefiningaListViewthatusesGridViewView"></a>
## <a name="what-is-a-gridview-view"></a>¿Qué es una vista GridView?  
 El <xref:System.Windows.Controls.GridView> modo de vista muestra una lista de elementos de datos enlazando campos de datos a columnas y mostrando un encabezado de columna para identificar el campo. El <xref:System.Windows.Controls.GridView> estilo predeterminado implementa botones como encabezados de columna. Mediante el uso de botones para encabezados de columna, puede implementar importantes capacidades de interacción del usuario; por ejemplo, los usuarios pueden <xref:System.Windows.Controls.GridView> hacer clic en el encabezado de columna para ordenar los datos según el contenido de una columna específica.  
  
> [!NOTE]
> Los controles <xref:System.Windows.Controls.GridView> de botón que se <xref:System.Windows.Controls.Primitives.ButtonBase>usan para los encabezados de columna se derivan de .  
  
 En la siguiente <xref:System.Windows.Controls.GridView> ilustración se muestra una vista del <xref:System.Windows.Controls.ListView> contenido.  

 ![Captura de pantalla que muestra la vista GridView del contenido de ListView.](./media/gridview-overview/styled-listview-content.png)  
  
 <xref:System.Windows.Controls.GridView>las columnas están <xref:System.Windows.Controls.GridViewColumn> representadas por objetos, que pueden cambiar automáticamente el tamaño de su contenido. Opcionalmente, puede establecer explícitamente a <xref:System.Windows.Controls.GridViewColumn> a un ancho específico. Puede cambiar el tamaño de las columnas si arrastra la barra de redimensionamiento que se encuentra entre los encabezados de columna. También puede agregar, quitar, reemplazar y reordenar columnas dinámicamente porque <xref:System.Windows.Controls.GridView>esta funcionalidad está integrada en . Sin <xref:System.Windows.Controls.GridView> embargo, no puede actualizar directamente los datos que muestra.  
  
 En el ejemplo siguiente <xref:System.Windows.Controls.GridView> se muestra cómo definir un que muestra los datos de los empleados. En este <xref:System.Windows.Controls.ListView> ejemplo, `EmployeeInfoDataSource` define <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>el archivo . Las definiciones <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> de <xref:System.Windows.Controls.GridViewColumn> propiedad `EmployeeInfoDataSource` de enlazar contenido a categorías de datos.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 En la siguiente ilustración se muestra la tabla creada en el ejemplo anterior. El control GridView muestra datos de un objeto ItemsSource:

 ![Captura de pantalla que muestra un ListView con salida GridView.](./media/gridview-overview/listview-gridview-output.jpg)  
  
<a name="GridViewLayoutandStyle"></a>
## <a name="gridview-layout-and-style"></a>Estilo y diseño de GridView  
 Las celdas de columna <xref:System.Windows.Controls.GridViewColumn> y el encabezado de columna de a tienen el mismo ancho. De forma predeterminada, cada columna ajusta su anchura para ajustarse al contenido. Opcionalmente, puede establecer un ancho de columna fijo.  
  
 El contenido de datos relacionado se muestra en filas horizontales. Por ejemplo, en la ilustración anterior, el apellido, el nombre y el número de identificador de cada empleado se muestran como un conjunto porque aparecen en una fila horizontal.  
  
<a name="DefiningandStylingColumnsinaGridView"></a>
### <a name="defining-and-styling-columns-in-a-gridview"></a>Definición y aplicación de estilos de columna en GridView  
 Al definir el campo de <xref:System.Windows.Controls.GridViewColumn>datos que <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>se <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A> va a mostrar en un , utilice las propiedades , , o . La <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> propiedad tiene prioridad sobre cualquiera de las propiedades de plantilla.  
  
 Para especificar la alineación del <xref:System.Windows.Controls.GridView>contenido en <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>una columna de un , defina un archivo . No utilice <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> las <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> propiedades <xref:System.Windows.Controls.ListView> y para el contenido <xref:System.Windows.Controls.GridView>que se muestra mediante un archivo .  
  
 Para especificar las propiedades de plantilla y <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.GridViewColumn>estilo <xref:System.Windows.Controls.GridViewColumnHeader> para los encabezados de columna, utilice las clases , , y . Para más información, consulte [Información general sobre plantillas y estilos de encabezado de columna en modo GridView](gridview-column-header-styles-and-templates-overview.md).  
  
<a name="AddingVisualElementstoaGridViewView"></a>
### <a name="adding-visual-elements-to-a-gridview"></a>Incorporación de elementos visuales a un control GridView  
 Para agregar elementos <xref:System.Windows.Controls.CheckBox> visuales, como y <xref:System.Windows.Controls.Button> controles, a un <xref:System.Windows.Controls.GridView> modo de vista, utilice plantillas o estilos.  
  
 Si define explícitamente un elemento visual como un elemento de <xref:System.Windows.Controls.GridView>datos, solo puede aparecer una vez en un archivo . Esta limitación existe porque un elemento puede tener un único elemento primario y, por tanto, puede aparecer solo una vez en el árbol visual.  
  
<a name="StylingRowsinaGridViewView"></a>
### <a name="styling-rows-in-a-gridview"></a>Aplicación de estilos a filas en GridView  
 Utilice <xref:System.Windows.Controls.GridViewRowPresenter> las <xref:System.Windows.Controls.GridViewHeaderRowPresenter> clases y para dar <xref:System.Windows.Controls.GridView>formato y mostrar las filas de un archivo . Para obtener un ejemplo de <xref:System.Windows.Controls.GridView> cómo aplicar estilo a las filas en un modo de vista, vea [Style a Row en un ListView que implementa un control GridView](how-to-style-a-row-in-a-listview-that-implements-a-gridview.md).  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>
### <a name="alignment-issues-when-you-use-itemcontainerstyle"></a>Problemas de alineación al usar ItemContainerStyle  
 Para evitar problemas de alineación entre encabezados de columna y celdas, no establezca <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>una propiedad ni especifique una plantilla que afecte al ancho de un elemento en un archivo . Por ejemplo, no <xref:System.Windows.FrameworkElement.Margin%2A> establezca la <xref:System.Windows.Controls.ControlTemplate> propiedad ni <xref:System.Windows.Controls.CheckBox> especifique <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> una que agregue <xref:System.Windows.Controls.ListView> a una definida en un control. En su lugar, especifique las propiedades y plantillas <xref:System.Windows.Controls.GridView> que afectan al ancho de columna directamente en las clases que definen un modo de vista.  
  
 Por ejemplo, para <xref:System.Windows.Controls.CheckBox> agregar a <xref:System.Windows.Controls.GridView> las filas <xref:System.Windows.Controls.CheckBox> en <xref:System.Windows.DataTemplate>modo de vista, agregue el valor a , y, a continuación, establezca la <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> propiedad en ese <xref:System.Windows.DataTemplate>archivo .  
  
<a name="InteractingwithaGridViewControl"></a>
## <a name="user-interactions-with-a-gridview"></a>Interacciones del usuario con GridView  
 Cuando se <xref:System.Windows.Controls.GridView> utiliza una aplicación en la aplicación, los <xref:System.Windows.Controls.GridView>usuarios pueden interactuar con el formato del archivo . Por ejemplo, los usuarios pueden reordenar las columnas, cambiar el tamaño de una columna, seleccionar elementos en una tabla y desplazarse por el contenido. También puede definir un controlador de eventos para que responda cuando un usuario hace clic en el botón de encabezado de columna. El controlador de eventos puede realizar operaciones como <xref:System.Windows.Controls.GridView> ordenar los datos que se muestran en el según el contenido de una columna.  
  
 En la lista siguiente se describen <xref:System.Windows.Controls.GridView> con más detalle las capacidades de uso para la interacción del usuario:  
  
- **Reordenar columnas con el método de arrastrar y colocar.**  
  
     Los usuarios pueden <xref:System.Windows.Controls.GridView> reordenar las columnas en un presionando el botón izquierdo del ratón mientras está sobre un encabezado de columna y, a continuación, arrastrando esa columna a una nueva posición. Mientras el usuario arrastra el encabezado de columna, se muestra una versión flotante del encabezado, así como una línea negra sólida que muestra dónde insertar la columna.  
  
     Si desea modificar el estilo predeterminado para la versión <xref:System.Windows.Controls.ControlTemplate> flotante <xref:System.Windows.Controls.GridViewColumnHeader> de un encabezado, <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> especifique a <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>para un tipo que se desencadena cuando la propiedad se establece en . Para más información, consulte [Crear un estilo para un encabezado de columna de GridView arrastrado](how-to-create-a-style-for-a-dragged-gridview-column-header.md).  
  
- **Cambiar el tamaño de una columna para ajustarla a su contenido.**  
  
     Los usuarios pueden hacer doble clic en la barra de redimensionamiento a la derecha de un encabezado de columna para cambiar el tamaño de una columna con el fin de ajustarla a su contenido.  
  
    > [!NOTE]
    > Puede establecer <xref:System.Windows.Controls.GridViewColumn.Width%2A> la `Double.NaN` propiedad para producir el mismo efecto.  
  
- **Seleccionar elementos de fila.**  
  
     Los usuarios pueden seleccionar <xref:System.Windows.Controls.GridView>uno o varios elementos en un archivo .  
  
     Si desea cambiar <xref:System.Windows.Style> el elemento seleccionado, vea Usar desencadenadores para aplicar estilo a los [elementos seleccionados en un ListView](how-to-use-triggers-to-style-selected-items-in-a-listview.md).  
  
- **Desplazarse para ver el contenido que inicialmente no aparece en la pantalla.**  
  
     Si el tamaño <xref:System.Windows.Controls.GridView> de la no es lo suficientemente grande como para mostrar todos los elementos, los usuarios pueden desplazarse horizontal o verticalmente mediante barras de desplazamiento, que son proporcionadas por un <xref:System.Windows.Controls.ScrollViewer> control. A <xref:System.Windows.Controls.Primitives.ScrollBar> se oculta si todo el contenido está visible en una dirección específica. Los encabezados de columna no se desplazan con una barra de desplazamiento vertical, sino que se desplazan en horizontal.  
  
- **Interactuar con las columnas haciendo clic en los botones de encabezado de columna.**  
  
     Cuando los usuarios hacen clic en un botón de encabezado de columna, pueden ordenar los datos que se muestran en la columna si disponen de un algoritmo de ordenación.  
  
     Puede controlar <xref:System.Windows.Controls.Primitives.ButtonBase.Click> el evento para los botones de encabezado de columna para proporcionar funcionalidad como un algoritmo de ordenación. Para controlar <xref:System.Windows.Controls.Primitives.ButtonBase.Click> el evento de un único encabezado <xref:System.Windows.Controls.GridViewColumnHeader>de columna, establezca un controlador de eventos en el archivo . Para establecer un controlador <xref:System.Windows.Controls.Primitives.ButtonBase.Click> de eventos que controla el evento <xref:System.Windows.Controls.ListView> para todos los encabezados de columna, establezca el controlador en el control.  
  
<a name="Obtaining_Other_Custom_Views"></a>
## <a name="obtaining-other-custom-views"></a>Obtención de otras vistas personalizadas  
 La <xref:System.Windows.Controls.GridView> clase, que se <xref:System.Windows.Controls.ViewBase> deriva de la clase abstracta, es <xref:System.Windows.Controls.ListView> solo uno de los modos de vista posibles para la clase. Puede crear otras vistas <xref:System.Windows.Controls.ListView> personalizadas para <xref:System.Windows.Controls.ViewBase> derivar de la clase. Para obtener un ejemplo de un modo de visualización personalizado, vea [Crear un modo de vista personalizado para un control ListView](how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="GridViewSupportingClasses"></a>
## <a name="gridview-supporting-classes"></a>Clases que admiten GridView  
 Las clases <xref:System.Windows.Controls.GridView> siguientes admiten el modo de vista.  
  
- <xref:System.Windows.Controls.GridViewColumn>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GridViewRowPresenter>  
  
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
  
- <xref:System.Windows.Controls.GridViewColumnCollection>  
  
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Controls.GridViewColumn>
- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.ViewBase>
- [Información general sobre ListView](listview-overview.md)
- [Ordenar una columna de GridView cuando se hace clic en un encabezado](how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [Temas de información](listview-how-to-topics.md)
