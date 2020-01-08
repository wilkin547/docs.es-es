---
title: 'Cómo: Agregar detalles de fila a un control DataGrid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
ms.openlocfilehash: 4db414e1907d42071f7251c390077d4020fa577c
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559682"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a>Cómo: Agregar detalles de fila a un control DataGrid
Al usar el control de <xref:System.Windows.Controls.DataGrid>, puede personalizar la presentación de datos agregando una sección de detalles de fila. Agregar una sección de detalles de fila le permite agrupar algunos datos en una plantilla que, opcionalmente, está visible o contraído. Por ejemplo, puede agregar detalles de fila a un <xref:System.Windows.Controls.DataGrid> que presente solo un resumen de los datos de cada fila de la <xref:System.Windows.Controls.DataGrid>, pero presenta más campos de datos cuando el usuario selecciona una fila. Defina la plantilla para la sección de detalles de fila en la propiedad <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>. En la ilustración siguiente se muestra un ejemplo de una sección de detalles de fila.  
  
 ![DataGrid mostrado con detalles de fila](./media/ndp-rowdetails.png "NDP_RowDetails")  
  
 La plantilla de detalles de fila se define como XAML en línea o como un recurso. Ambos enfoques se muestran en los procedimientos siguientes. Una plantilla de datos que se agrega como un recurso se puede usar en todo el proyecto sin volver a crear la plantilla. Una plantilla de datos que se agrega como XAML en línea solo es accesible desde el control en el que se define.  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a>Para mostrar los detalles de fila mediante XAML en línea  
  
1. Cree un <xref:System.Windows.Controls.DataGrid> que muestre los datos de un origen de datos.  
  
2. En el elemento <xref:System.Windows.Controls.DataGrid>, agregue un elemento <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.  
  
3. Cree una <xref:System.Windows.DataTemplate> que defina la apariencia de la sección de detalles de fila.  
  
     En el siguiente código XAML se muestra el <xref:System.Windows.Controls.DataGrid> y cómo definir el <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> insertado. El <xref:System.Windows.Controls.DataGrid> muestra tres valores en cada fila y tres valores más cuando se selecciona la fila.  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     En el código siguiente se muestra la consulta que se utiliza para seleccionar los datos que se muestran en el <xref:System.Windows.Controls.DataGrid>. En este ejemplo, la consulta selecciona los datos de una entidad que contiene información del cliente.  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a>Para mostrar los detalles de fila mediante un recurso  
  
1. Cree un <xref:System.Windows.Controls.DataGrid> que muestre los datos de un origen de datos.  
  
2. Agregue un elemento <xref:System.Windows.FrameworkElement.Resources%2A> al elemento raíz, como un control <xref:System.Windows.Window> o un control <xref:System.Windows.Controls.Page>, o agregue un elemento <xref:System.Windows.Application.Resources%2A> a la clase <xref:System.Windows.Application> en el archivo app. XAML (o Application. xaml).  
  
3. En el elemento Resources, cree una <xref:System.Windows.DataTemplate> que defina la apariencia de la sección de detalles de fila.  
  
     En el siguiente código XAML se muestra el <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> definido en la clase <xref:System.Windows.Application>.  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. En el <xref:System.Windows.DataTemplate>, establezca la [Directiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) en un valor que identifique de forma única la plantilla de datos.  
  
5. En el elemento <xref:System.Windows.Controls.DataGrid>, establezca la propiedad <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> en el recurso definido en los pasos anteriores. Asigne el recurso como un recurso estático.  
  
     En el código XAML siguiente se muestra la propiedad <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> establecida en el recurso del ejemplo anterior.  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a>Para establecer la visibilidad y evitar el desplazamiento horizontal de los detalles de fila  
  
1. Si es necesario, establezca la propiedad <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> en un valor <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode>.  
  
     De forma predeterminada, este valor se establece en <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>. Puede establecerlo en <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> para mostrar los detalles de todas las filas o <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> para ocultar los detalles de todas las filas.  
  
2. Si es necesario, establezca la propiedad <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> en `true` para evitar que la sección de detalles de fila se desplace horizontalmente.
