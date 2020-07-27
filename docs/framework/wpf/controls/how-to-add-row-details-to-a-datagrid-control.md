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
# <a name="how-to-add-row-details-to-a-datagrid-control"></a><span data-ttu-id="a183f-103">Procedimiento para agregar detalles de fila a un control DataGrid</span><span class="sxs-lookup"><span data-stu-id="a183f-103">How to: Add Row Details to a DataGrid Control</span></span>
<span data-ttu-id="a183f-104">Al utilizar el <xref:System.Windows.Controls.DataGrid> control, puede personalizar la presentación de datos agregando una sección de detalles de fila.</span><span class="sxs-lookup"><span data-stu-id="a183f-104">When using the <xref:System.Windows.Controls.DataGrid> control, you can customize the data presentation by adding a row details section.</span></span> <span data-ttu-id="a183f-105">Agregar una sección de detalles de fila le permite agrupar algunos datos en una plantilla que, opcionalmente, está visible o contraído.</span><span class="sxs-lookup"><span data-stu-id="a183f-105">Adding a row details section enables you to group some data in a template that is optionally visible or collapsed.</span></span> <span data-ttu-id="a183f-106">Por ejemplo, puede agregar detalles de fila a un <xref:System.Windows.Controls.DataGrid> que presente solo un resumen de los datos de cada fila de <xref:System.Windows.Controls.DataGrid> , pero presenta más campos de datos cuando el usuario selecciona una fila.</span><span class="sxs-lookup"><span data-stu-id="a183f-106">For example, you can add row details to a <xref:System.Windows.Controls.DataGrid> that presents only a summary of the data for each row in the <xref:System.Windows.Controls.DataGrid>, but presents more data fields when the user selects a row.</span></span> <span data-ttu-id="a183f-107">Defina la plantilla para la sección de detalles de fila en la <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="a183f-107">You define the template for the row details section in the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property.</span></span> <span data-ttu-id="a183f-108">En la ilustración siguiente se muestra un ejemplo de una sección de detalles de fila.</span><span class="sxs-lookup"><span data-stu-id="a183f-108">The following illustration shows an example of a row details section.</span></span>  
  
 <span data-ttu-id="a183f-109">![DataGrid con detalles de filas](./media/ndp-rowdetails.png "NDP_RowDetails")</span><span class="sxs-lookup"><span data-stu-id="a183f-109">![DataGrid shown with row details](./media/ndp-rowdetails.png "NDP_RowDetails")</span></span>  
  
 <span data-ttu-id="a183f-110">La plantilla de detalles de fila se define como XAML en línea o como un recurso.</span><span class="sxs-lookup"><span data-stu-id="a183f-110">You define the row details template as either inline XAML or as a resource.</span></span> <span data-ttu-id="a183f-111">Ambos enfoques se muestran en los procedimientos siguientes.</span><span class="sxs-lookup"><span data-stu-id="a183f-111">Both approaches are shown in the following procedures.</span></span> <span data-ttu-id="a183f-112">Una plantilla de datos que se agrega como un recurso se puede usar en todo el proyecto sin volver a crear la plantilla.</span><span class="sxs-lookup"><span data-stu-id="a183f-112">A data template that is added as a resource can be used throughout the project without re-creating the template.</span></span> <span data-ttu-id="a183f-113">Una plantilla de datos que se agrega como XAML en línea solo es accesible desde el control en el que se define.</span><span class="sxs-lookup"><span data-stu-id="a183f-113">A data template that is added as inline XAML is only accessible from the control where it is defined.</span></span>  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a><span data-ttu-id="a183f-114">Para mostrar los detalles de fila mediante XAML en línea</span><span class="sxs-lookup"><span data-stu-id="a183f-114">To display row details by using inline XAML</span></span>  
  
1. <span data-ttu-id="a183f-115">Cree un <xref:System.Windows.Controls.DataGrid> que muestre los datos de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a183f-115">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="a183f-116">En el elemento <xref:System.Windows.Controls.DataGrid>, agregue un elemento <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="a183f-116">In the <xref:System.Windows.Controls.DataGrid> element, add a <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> element.</span></span>  
  
3. <span data-ttu-id="a183f-117">Cree un <xref:System.Windows.DataTemplate> que defina la apariencia de la sección de detalles de fila.</span><span class="sxs-lookup"><span data-stu-id="a183f-117">Create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="a183f-118">En el siguiente código XAML se muestra <xref:System.Windows.Controls.DataGrid> y cómo definir el <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> .</span><span class="sxs-lookup"><span data-stu-id="a183f-118">The following XAML shows the <xref:System.Windows.Controls.DataGrid> and how to define the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline.</span></span> <span data-ttu-id="a183f-119"><xref:System.Windows.Controls.DataGrid>Muestra tres valores en cada fila y tres valores más cuando se selecciona la fila.</span><span class="sxs-lookup"><span data-stu-id="a183f-119">The <xref:System.Windows.Controls.DataGrid> displays three values in each row and three more values when the row is selected.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     <span data-ttu-id="a183f-120">En el código siguiente se muestra la consulta que se utiliza para seleccionar los datos que se muestran en el <xref:System.Windows.Controls.DataGrid> .</span><span class="sxs-lookup"><span data-stu-id="a183f-120">The following code shows the query that is used to select the data that is displayed in the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="a183f-121">En este ejemplo, la consulta selecciona los datos de una entidad que contiene información del cliente.</span><span class="sxs-lookup"><span data-stu-id="a183f-121">In this example, the query selects data from an entity that contains customer information.</span></span>  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a><span data-ttu-id="a183f-122">Para mostrar los detalles de fila mediante un recurso</span><span class="sxs-lookup"><span data-stu-id="a183f-122">To display row details by using a resource</span></span>  
  
1. <span data-ttu-id="a183f-123">Cree un <xref:System.Windows.Controls.DataGrid> que muestre los datos de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a183f-123">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="a183f-124">Agregue un <xref:System.Windows.FrameworkElement.Resources%2A> elemento al elemento raíz, como un <xref:System.Windows.Window> control o un <xref:System.Windows.Controls.Page> control, o agregue un <xref:System.Windows.Application.Resources%2A> elemento a la <xref:System.Windows.Application> clase en el archivo app. XAML (o Application. xaml).</span><span class="sxs-lookup"><span data-stu-id="a183f-124">Add a <xref:System.Windows.FrameworkElement.Resources%2A> element to the root element, such as a <xref:System.Windows.Window> control or a <xref:System.Windows.Controls.Page> control, or add a <xref:System.Windows.Application.Resources%2A> element to the <xref:System.Windows.Application> class in the App.xaml (or Application.xaml) file.</span></span>  
  
3. <span data-ttu-id="a183f-125">En el elemento Resources, cree un <xref:System.Windows.DataTemplate> que defina la apariencia de la sección de detalles de fila.</span><span class="sxs-lookup"><span data-stu-id="a183f-125">In the resources element, create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="a183f-126">En el siguiente código XAML se muestra el <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> definido en la <xref:System.Windows.Application> clase.</span><span class="sxs-lookup"><span data-stu-id="a183f-126">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> defined in the <xref:System.Windows.Application> class.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. <span data-ttu-id="a183f-127">En <xref:System.Windows.DataTemplate> , establezca la [Directiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) en un valor que identifique de forma única la plantilla de datos.</span><span class="sxs-lookup"><span data-stu-id="a183f-127">On the <xref:System.Windows.DataTemplate>, set the [x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md) to a value that uniquely identifies the data template.</span></span>  
  
5. <span data-ttu-id="a183f-128">En el <xref:System.Windows.Controls.DataGrid> elemento, establezca la <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> propiedad en el recurso definido en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="a183f-128">In the <xref:System.Windows.Controls.DataGrid> element, set the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property to the resource defined in the previous steps.</span></span> <span data-ttu-id="a183f-129">Asigne el recurso como un recurso estático.</span><span class="sxs-lookup"><span data-stu-id="a183f-129">Assign the resource as a static resource.</span></span>  
  
     <span data-ttu-id="a183f-130">En el código XAML siguiente <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> se muestra la propiedad establecida en el recurso del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="a183f-130">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property set to the resource from the previous example.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a><span data-ttu-id="a183f-131">Para establecer la visibilidad y evitar el desplazamiento horizontal de los detalles de fila</span><span class="sxs-lookup"><span data-stu-id="a183f-131">To set visibility and prevent horizontal scrolling for row details</span></span>  
  
1. <span data-ttu-id="a183f-132">Si es necesario, establezca la <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> propiedad en un <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> valor.</span><span class="sxs-lookup"><span data-stu-id="a183f-132">If needed, set the <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> property to a <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> value.</span></span>  
  
     <span data-ttu-id="a183f-133">De forma predeterminada, este valor se establece en <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span><span class="sxs-lookup"><span data-stu-id="a183f-133">By default, the value is set to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span></span> <span data-ttu-id="a183f-134">Puede establecerlo en <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> para mostrar los detalles de todas las filas u <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> ocultar los detalles de todas las filas.</span><span class="sxs-lookup"><span data-stu-id="a183f-134">You can set it to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> to show the details for all of the rows or <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> to hide the details for all rows.</span></span>  
  
2. <span data-ttu-id="a183f-135">Si es necesario, establezca la <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> propiedad en `true` para evitar que la sección de detalles de fila se desplace horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="a183f-135">If needed, set the <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> property to `true` to prevent the row details section from scrolling horizontally.</span></span>
