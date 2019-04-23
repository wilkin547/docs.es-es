---
title: Procedimiento para agregar detalles de fila a un control DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
ms.openlocfilehash: d5b6539f3d379088528b9654861267988b6fc69b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768649"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a>Procedimiento para agregar detalles de fila a un control DataGrid
Cuando se usa el <xref:System.Windows.Controls.DataGrid> control, puede personalizar la presentación de datos mediante la adición de una sección de detalles de fila. Agregar una sección de detalles de fila permite agrupar algunos datos en una plantilla que, opcionalmente, visible o contraída. Por ejemplo, puede agregar detalles de fila para un <xref:System.Windows.Controls.DataGrid> que presenta únicamente un resumen de los datos para cada fila de la <xref:System.Windows.Controls.DataGrid>, pero presenta más campos de datos cuando el usuario selecciona una fila. Definir la plantilla para la sección de detalles de fila en la <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> propiedad. La siguiente ilustración muestra un ejemplo de una sección de detalles de fila.  
  
 ![DataGrid con detalles de fila](./media/ndp-rowdetails.png "NDP_RowDetails")  
  
 Definir la plantilla de detalles de fila como en línea mediante XAML o como un recurso. En los procedimientos siguientes se muestran ambos enfoques. Una plantilla de datos que se agrega como un recurso puede usarse en todo el proyecto sin volver a crear la plantilla. Solo es accesible desde el control de una plantilla de datos que se agrega como inline XAML donde se define.  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a>Para mostrar los detalles de fila mediante XAML insertado  
  
1. Crear un <xref:System.Windows.Controls.DataGrid> que muestra los datos de un origen de datos.  
  
2. En el elemento <xref:System.Windows.Controls.DataGrid>, agregue un elemento <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.  
  
3. Crear un <xref:System.Windows.DataTemplate> que define la apariencia de la sección de detalles de fila.  
  
     El siguiente XAML muestra el <xref:System.Windows.Controls.DataGrid> y cómo definir el <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> en línea. La <xref:System.Windows.Controls.DataGrid> muestra tres valores en cada fila y tres más valores cuando se selecciona la fila.  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     El código siguiente muestra la consulta que se utiliza para seleccionar los datos que se muestran en el <xref:System.Windows.Controls.DataGrid>. En este ejemplo, la consulta selecciona los datos de una entidad que contiene la información del cliente.  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a>Para mostrar los detalles de fila mediante el uso de un recurso  
  
1. Crear un <xref:System.Windows.Controls.DataGrid> que muestra los datos de un origen de datos.  
  
2. Agregar un <xref:System.Windows.FrameworkElement.Resources%2A> elemento para el elemento raíz, como un <xref:System.Windows.Window> control o un <xref:System.Windows.Controls.Page> controlar o agregar un <xref:System.Windows.Application.Resources%2A> elemento a la <xref:System.Windows.Application> clase en el archivo App.xaml (o Application.xaml).  
  
3. En el elemento resources, cree un <xref:System.Windows.DataTemplate> que define la apariencia de la sección de detalles de fila.  
  
     El siguiente XAML muestra el <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> definido en el <xref:System.Windows.Application> clase.  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. En el <xref:System.Windows.DataTemplate>, establezca el [Directiva x: Key](../../xaml-services/x-key-directive.md) en un valor que identifica la plantilla de datos.  
  
5. En el <xref:System.Windows.Controls.DataGrid> elemento, establezca el <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> propiedad para el recurso definido en los pasos anteriores. Asigne al recurso como un recurso estático.  
  
     El siguiente XAML muestra el <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> propiedad establecida en el recurso del ejemplo anterior.  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a>Para establecer la visibilidad y evitar el desplazamiento horizontal para obtener detalles de fila  
  
1. Si es necesario, establezca el <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> propiedad a un <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> valor.  
  
     De forma predeterminada, el valor se establece en <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>. Puede establecerlo en <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> para mostrar los detalles de todas las filas o <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> para ocultar los detalles de todas las filas.  
  
2. Si es necesario, establezca el <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> propiedad `true` evitar que la fila de la sección de desplazamiento horizontal de detalles.
