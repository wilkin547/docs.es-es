---
title: Filtrar para agregar detalles de fila a un control DataGrid
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
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59317901"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a><span data-ttu-id="a7755-102">Filtrar para agregar detalles de fila a un control DataGrid</span><span class="sxs-lookup"><span data-stu-id="a7755-102">How to: Add Row Details to a DataGrid Control</span></span>
<span data-ttu-id="a7755-103">Cuando se usa el <xref:System.Windows.Controls.DataGrid> control, puede personalizar la presentación de datos mediante la adición de una sección de detalles de fila.</span><span class="sxs-lookup"><span data-stu-id="a7755-103">When using the <xref:System.Windows.Controls.DataGrid> control, you can customize the data presentation by adding a row details section.</span></span> <span data-ttu-id="a7755-104">Agregar una sección de detalles de fila permite agrupar algunos datos en una plantilla que, opcionalmente, visible o contraída.</span><span class="sxs-lookup"><span data-stu-id="a7755-104">Adding a row details section enables you to group some data in a template that is optionally visible or collapsed.</span></span> <span data-ttu-id="a7755-105">Por ejemplo, puede agregar detalles de fila para un <xref:System.Windows.Controls.DataGrid> que presenta únicamente un resumen de los datos para cada fila de la <xref:System.Windows.Controls.DataGrid>, pero presenta más campos de datos cuando el usuario selecciona una fila.</span><span class="sxs-lookup"><span data-stu-id="a7755-105">For example, you can add row details to a <xref:System.Windows.Controls.DataGrid> that presents only a summary of the data for each row in the <xref:System.Windows.Controls.DataGrid>, but presents more data fields when the user selects a row.</span></span> <span data-ttu-id="a7755-106">Definir la plantilla para la sección de detalles de fila en la <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="a7755-106">You define the template for the row details section in the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property.</span></span> <span data-ttu-id="a7755-107">La siguiente ilustración muestra un ejemplo de una sección de detalles de fila.</span><span class="sxs-lookup"><span data-stu-id="a7755-107">The following illustration shows an example of a row details section.</span></span>  
  
 <span data-ttu-id="a7755-108">![DataGrid con detalles de fila](./media/ndp-rowdetails.png "NDP_RowDetails")</span><span class="sxs-lookup"><span data-stu-id="a7755-108">![DataGrid shown with row details](./media/ndp-rowdetails.png "NDP_RowDetails")</span></span>  
  
 <span data-ttu-id="a7755-109">Definir la plantilla de detalles de fila como en línea mediante XAML o como un recurso.</span><span class="sxs-lookup"><span data-stu-id="a7755-109">You define the row details template as either inline XAML or as a resource.</span></span> <span data-ttu-id="a7755-110">En los procedimientos siguientes se muestran ambos enfoques.</span><span class="sxs-lookup"><span data-stu-id="a7755-110">Both approaches are shown in the following procedures.</span></span> <span data-ttu-id="a7755-111">Una plantilla de datos que se agrega como un recurso puede usarse en todo el proyecto sin volver a crear la plantilla.</span><span class="sxs-lookup"><span data-stu-id="a7755-111">A data template that is added as a resource can be used throughout the project without re-creating the template.</span></span> <span data-ttu-id="a7755-112">Solo es accesible desde el control de una plantilla de datos que se agrega como inline XAML donde se define.</span><span class="sxs-lookup"><span data-stu-id="a7755-112">A data template that is added as inline XAML is only accessible from the control where it is defined.</span></span>  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a><span data-ttu-id="a7755-113">Para mostrar los detalles de fila mediante XAML insertado</span><span class="sxs-lookup"><span data-stu-id="a7755-113">To display row details by using inline XAML</span></span>  
  
1. <span data-ttu-id="a7755-114">Crear un <xref:System.Windows.Controls.DataGrid> que muestra los datos de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a7755-114">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="a7755-115">En el elemento <xref:System.Windows.Controls.DataGrid>, agregue un elemento <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="a7755-115">In the <xref:System.Windows.Controls.DataGrid> element, add a <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> element.</span></span>  
  
3. <span data-ttu-id="a7755-116">Crear un <xref:System.Windows.DataTemplate> que define la apariencia de la sección de detalles de fila.</span><span class="sxs-lookup"><span data-stu-id="a7755-116">Create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="a7755-117">El siguiente XAML muestra el <xref:System.Windows.Controls.DataGrid> y cómo definir el <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> en línea.</span><span class="sxs-lookup"><span data-stu-id="a7755-117">The following XAML shows the <xref:System.Windows.Controls.DataGrid> and how to define the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline.</span></span> <span data-ttu-id="a7755-118">La <xref:System.Windows.Controls.DataGrid> muestra tres valores en cada fila y tres más valores cuando se selecciona la fila.</span><span class="sxs-lookup"><span data-stu-id="a7755-118">The <xref:System.Windows.Controls.DataGrid> displays three values in each row and three more values when the row is selected.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     <span data-ttu-id="a7755-119">El código siguiente muestra la consulta que se utiliza para seleccionar los datos que se muestran en el <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="a7755-119">The following code shows the query that is used to select the data that is displayed in the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="a7755-120">En este ejemplo, la consulta selecciona los datos de una entidad que contiene la información del cliente.</span><span class="sxs-lookup"><span data-stu-id="a7755-120">In this example, the query selects data from an entity that contains customer information.</span></span>  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a><span data-ttu-id="a7755-121">Para mostrar los detalles de fila mediante el uso de un recurso</span><span class="sxs-lookup"><span data-stu-id="a7755-121">To display row details by using a resource</span></span>  
  
1. <span data-ttu-id="a7755-122">Crear un <xref:System.Windows.Controls.DataGrid> que muestra los datos de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a7755-122">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="a7755-123">Agregar un <xref:System.Windows.FrameworkElement.Resources%2A> elemento para el elemento raíz, como un <xref:System.Windows.Window> control o un <xref:System.Windows.Controls.Page> controlar o agregar un <xref:System.Windows.Application.Resources%2A> elemento a la <xref:System.Windows.Application> clase en el archivo App.xaml (o Application.xaml).</span><span class="sxs-lookup"><span data-stu-id="a7755-123">Add a <xref:System.Windows.FrameworkElement.Resources%2A> element to the root element, such as a <xref:System.Windows.Window> control or a <xref:System.Windows.Controls.Page> control, or add a <xref:System.Windows.Application.Resources%2A> element to the <xref:System.Windows.Application> class in the App.xaml (or Application.xaml) file.</span></span>  
  
3. <span data-ttu-id="a7755-124">En el elemento resources, cree un <xref:System.Windows.DataTemplate> que define la apariencia de la sección de detalles de fila.</span><span class="sxs-lookup"><span data-stu-id="a7755-124">In the resources element, create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="a7755-125">El siguiente XAML muestra el <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> definido en el <xref:System.Windows.Application> clase.</span><span class="sxs-lookup"><span data-stu-id="a7755-125">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> defined in the <xref:System.Windows.Application> class.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. <span data-ttu-id="a7755-126">En el <xref:System.Windows.DataTemplate>, establezca el [Directiva x: Key](../../xaml-services/x-key-directive.md) en un valor que identifica la plantilla de datos.</span><span class="sxs-lookup"><span data-stu-id="a7755-126">On the <xref:System.Windows.DataTemplate>, set the [x:Key Directive](../../xaml-services/x-key-directive.md) to a value that uniquely identifies the data template.</span></span>  
  
5. <span data-ttu-id="a7755-127">En el <xref:System.Windows.Controls.DataGrid> elemento, establezca el <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> propiedad para el recurso definido en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="a7755-127">In the <xref:System.Windows.Controls.DataGrid> element, set the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property to the resource defined in the previous steps.</span></span> <span data-ttu-id="a7755-128">Asigne al recurso como un recurso estático.</span><span class="sxs-lookup"><span data-stu-id="a7755-128">Assign the resource as a static resource.</span></span>  
  
     <span data-ttu-id="a7755-129">El siguiente XAML muestra el <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> propiedad establecida en el recurso del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="a7755-129">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property set to the resource from the previous example.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a><span data-ttu-id="a7755-130">Para establecer la visibilidad y evitar el desplazamiento horizontal para obtener detalles de fila</span><span class="sxs-lookup"><span data-stu-id="a7755-130">To set visibility and prevent horizontal scrolling for row details</span></span>  
  
1. <span data-ttu-id="a7755-131">Si es necesario, establezca el <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> propiedad a un <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> valor.</span><span class="sxs-lookup"><span data-stu-id="a7755-131">If needed, set the <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> property to a <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> value.</span></span>  
  
     <span data-ttu-id="a7755-132">De forma predeterminada, el valor se establece en <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span><span class="sxs-lookup"><span data-stu-id="a7755-132">By default, the value is set to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span></span> <span data-ttu-id="a7755-133">Puede establecerlo en <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> para mostrar los detalles de todas las filas o <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> para ocultar los detalles de todas las filas.</span><span class="sxs-lookup"><span data-stu-id="a7755-133">You can set it to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> to show the details for all of the rows or <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> to hide the details for all rows.</span></span>  
  
2. <span data-ttu-id="a7755-134">Si es necesario, establezca el <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> propiedad `true` evitar que la fila de la sección de desplazamiento horizontal de detalles.</span><span class="sxs-lookup"><span data-stu-id="a7755-134">If needed, set the <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> property to `true` to prevent the row details section from scrolling horizontally.</span></span>
