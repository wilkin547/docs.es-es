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
ms.openlocfilehash: b6b0cc99c9833e514d2d52ecf139ab8e110f73e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a>Cómo: Agregar detalles de fila a un control DataGrid
Cuando se usa el <xref:System.Windows.Controls.DataGrid> control, puede personalizar la presentación de datos mediante la adición de una sección de detalles de fila. Agregar una sección de detalles de la fila le permite agrupar algunos datos en una plantilla que está visible o contraído opcionalmente. Por ejemplo, puede agregar detalles de las filas a una <xref:System.Windows.Controls.DataGrid> que presenta únicamente un resumen de los datos para cada fila de la <xref:System.Windows.Controls.DataGrid>, pero presenta más campos de datos cuando el usuario selecciona una fila. Definir la plantilla para la sección de detalles de la fila en la <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> propiedad. En la siguiente ilustración muestra un ejemplo de una sección de detalles de fila.  
  
 ![DataGrid con detalles de las filas](../../../../docs/framework/wpf/controls/media/ndp-rowdetails.png "NDP_RowDetails")  
  
 Definir la plantilla de detalles de fila como XAML alineado o como un recurso. En los procedimientos siguientes se muestran ambos enfoques. Una plantilla de datos que se agrega como un recurso se puede usar en todo el proyecto sin necesidad de volver a crear la plantilla. Solo es accesible desde el control de una plantilla de datos que se agrega como alineado XAML donde se define.  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a>Para mostrar detalles de las filas mediante el uso de XAML en línea  
  
1.  Crear un <xref:System.Windows.Controls.DataGrid> que muestra los datos de un origen de datos.  
  
2.  En el elemento <xref:System.Windows.Controls.DataGrid>, agregue un elemento <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.  
  
3.  Crear un <xref:System.Windows.DataTemplate> que define el aspecto de la sección de detalles de fila.  
  
     El XAML siguiente se muestra la <xref:System.Windows.Controls.DataGrid> y cómo definir la <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> en línea. La <xref:System.Windows.Controls.DataGrid> muestra tres valores en cada fila y tres valores más cuando se selecciona la fila.  
  
     [!code-xaml[DataGrid_RowDetails#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     El código siguiente muestra la consulta que se usa para seleccionar los datos que se muestran en el <xref:System.Windows.Controls.DataGrid>. En este ejemplo, la consulta selecciona los datos de una entidad que contiene información del cliente.  
  
     [!code-csharp[DataGrid_RowDetails#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a>Para mostrar detalles de las filas con un recurso  
  
1.  Crear un <xref:System.Windows.Controls.DataGrid> que muestra los datos de un origen de datos.  
  
2.  Agregar un <xref:System.Windows.FrameworkElement.Resources%2A> elemento hasta el elemento raíz, como un <xref:System.Windows.Window> control o un <xref:System.Windows.Controls.Page> controlar o agregar un <xref:System.Windows.Application.Resources%2A> elemento a la <xref:System.Windows.Application> clase en el archivo App.xaml (o Application.xaml).  
  
3.  En el elemento de recursos, cree un <xref:System.Windows.DataTemplate> que define el aspecto de la sección de detalles de fila.  
  
     El XAML siguiente se muestra la <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> definido en el <xref:System.Windows.Application> clase.  
  
     [!code-xaml[DataGrid_RowDetails#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4.  En el <xref:System.Windows.DataTemplate>, establezca el [x: Key (directiva)](../../../../docs/framework/xaml-services/x-key-directive.md) en un valor que identifica de forma única la plantilla de datos.  
  
5.  En el <xref:System.Windows.Controls.DataGrid> elemento, establezca la <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> propiedad para el recurso definido en los pasos anteriores. Asigne el recurso como un recurso estático.  
  
     El XAML siguiente se muestra el <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> propiedad establecida en el recurso del ejemplo anterior.  
  
     [!code-xaml[DataGrid_RowDetails#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a>Para establecer la visibilidad y evitar el desplazamiento horizontal para obtener detalles de fila  
  
1.  Si es necesario, establezca el <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> propiedad a un <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> valor.  
  
     De forma predeterminada, el valor se establece en <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>. Puede establecerlo en <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> para mostrar los detalles de todas las filas o <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> para ocultar los detalles de todas las filas.  
  
2.  Si es necesario, establezca el <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> propiedad `true` evitar que la fila de detalles sección de desplazamiento horizontal.
