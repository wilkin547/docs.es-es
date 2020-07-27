---
title: Procedimiento para agregar detalles de fila a un control DataGrid
description: Obtenga información sobre cómo personalizar la presentación de datos al usar el control DataGrid Windows Presentation Foundation agregando una sección de detalles de fila.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
ms.openlocfilehash: 8fd6b07f454681a0eed70d7a6208cfcc426dc920
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164949"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a>Procedimiento para agregar detalles de fila a un control DataGrid
Al utilizar el <xref:System.Windows.Controls.DataGrid> control, puede personalizar la presentación de datos agregando una sección de detalles de fila. Agregar una sección de detalles de fila le permite agrupar algunos datos en una plantilla que, opcionalmente, está visible o contraído. Por ejemplo, puede agregar detalles de fila a un <xref:System.Windows.Controls.DataGrid> que presente solo un resumen de los datos de cada fila de <xref:System.Windows.Controls.DataGrid> , pero presenta más campos de datos cuando el usuario selecciona una fila. Defina la plantilla para la sección de detalles de fila en la <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> propiedad. En la ilustración siguiente se muestra un ejemplo de una sección de detalles de fila.  
  
 ![DataGrid con detalles de filas](./media/ndp-rowdetails.png "NDP_RowDetails")  
  
 La plantilla de detalles de fila se define como XAML en línea o como un recurso. Ambos enfoques se muestran en los procedimientos siguientes. Una plantilla de datos que se agrega como un recurso se puede usar en todo el proyecto sin volver a crear la plantilla. Una plantilla de datos que se agrega como XAML en línea solo es accesible desde el control en el que se define.  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a>Para mostrar los detalles de fila mediante XAML en línea  
  
1. Cree un <xref:System.Windows.Controls.DataGrid> que muestre los datos de un origen de datos.  
  
2. En el elemento <xref:System.Windows.Controls.DataGrid>, agregue un elemento <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.  
  
3. Cree un <xref:System.Windows.DataTemplate> que defina la apariencia de la sección de detalles de fila.  
  
     En el siguiente código XAML se muestra <xref:System.Windows.Controls.DataGrid> y cómo definir el <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> . <xref:System.Windows.Controls.DataGrid>Muestra tres valores en cada fila y tres valores más cuando se selecciona la fila.  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     En el código siguiente se muestra la consulta que se utiliza para seleccionar los datos que se muestran en el <xref:System.Windows.Controls.DataGrid> . En este ejemplo, la consulta selecciona los datos de una entidad que contiene información del cliente.  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a>Para mostrar los detalles de fila mediante un recurso  
  
1. Cree un <xref:System.Windows.Controls.DataGrid> que muestre los datos de un origen de datos.  
  
2. Agregue un <xref:System.Windows.FrameworkElement.Resources%2A> elemento al elemento raíz, como un <xref:System.Windows.Window> control o un <xref:System.Windows.Controls.Page> control, o agregue un <xref:System.Windows.Application.Resources%2A> elemento a la <xref:System.Windows.Application> clase en el archivo app. XAML (o Application. xaml).  
  
3. En el elemento Resources, cree un <xref:System.Windows.DataTemplate> que defina la apariencia de la sección de detalles de fila.  
  
     En el siguiente código XAML se muestra el <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> definido en la <xref:System.Windows.Application> clase.  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. En <xref:System.Windows.DataTemplate> , establezca la [Directiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) en un valor que identifique de forma única la plantilla de datos.  
  
5. En el <xref:System.Windows.Controls.DataGrid> elemento, establezca la <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> propiedad en el recurso definido en los pasos anteriores. Asigne el recurso como un recurso estático.  
  
     En el código XAML siguiente <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> se muestra la propiedad establecida en el recurso del ejemplo anterior.  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a>Para establecer la visibilidad y evitar el desplazamiento horizontal de los detalles de fila  
  
1. Si es necesario, establezca la <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> propiedad en un <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> valor.  
  
     De forma predeterminada, este valor se establece en <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>. Puede establecerlo en <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> para mostrar los detalles de todas las filas u <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> ocultar los detalles de todas las filas.  
  
2. Si es necesario, establezca la <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> propiedad en `true` para evitar que la sección de detalles de fila se desplace horizontalmente.
