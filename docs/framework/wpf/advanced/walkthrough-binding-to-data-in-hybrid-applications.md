---
title: "Tutorial: Enlazar a datos en aplicaciones híbridas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
caps.latest.revision: "39"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3afc0d2eabb7554d64a40863b182a6edefe169f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a><span data-ttu-id="45e65-102">Tutorial: Enlazar a datos en aplicaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="45e65-102">Walkthrough: Binding to Data in Hybrid Applications</span></span>
<span data-ttu-id="45e65-103">Enlazar un origen de datos a un control es esencial para proporcionar a los usuarios con acceso a datos subyacentes, si usas [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] o [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45e65-103">Binding a data source to a control is essential for providing users with access to underlying data, whether you are using [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] or [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="45e65-104">Este tutorial muestra cómo puede utilizar el enlace de datos en aplicaciones híbridas que incluyen ambos [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controles.</span><span class="sxs-lookup"><span data-stu-id="45e65-104">This walkthrough shows how you can use data binding in hybrid applications that include both [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls.</span></span>  
  
 <span data-ttu-id="45e65-105">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="45e65-105">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="45e65-106">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="45e65-106">Creating the project.</span></span>  
  
-   <span data-ttu-id="45e65-107">Definir la plantilla de datos.</span><span class="sxs-lookup"><span data-stu-id="45e65-107">Defining the data template.</span></span>  
  
-   <span data-ttu-id="45e65-108">Especificar el diseño del formulario.</span><span class="sxs-lookup"><span data-stu-id="45e65-108">Specifying the form layout.</span></span>  
  
-   <span data-ttu-id="45e65-109">Especificar los enlaces de datos.</span><span class="sxs-lookup"><span data-stu-id="45e65-109">Specifying data bindings.</span></span>  
  
-   <span data-ttu-id="45e65-110">Mostrar los datos mediante la interoperación.</span><span class="sxs-lookup"><span data-stu-id="45e65-110">Displaying data by using interoperation.</span></span>  
  
-   <span data-ttu-id="45e65-111">Agregar el origen de datos al proyecto.</span><span class="sxs-lookup"><span data-stu-id="45e65-111">Adding the data source to the project.</span></span>  
  
-   <span data-ttu-id="45e65-112">Enlazar al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="45e65-112">Binding to the data source.</span></span>  
  
 <span data-ttu-id="45e65-113">Para obtener una lista de código completa de las tareas ilustradas en este tutorial, vea [Data Binding in Hybrid Applications Sample](http://go.microsoft.com/fwlink/?LinkID=159983).</span><span class="sxs-lookup"><span data-stu-id="45e65-113">For a complete code listing of the tasks illustrated in this walkthrough, see [Data Binding in Hybrid Applications Sample](http://go.microsoft.com/fwlink/?LinkID=159983).</span></span>  
  
 <span data-ttu-id="45e65-114">Cuando acabe, entenderá mejor las características de enlace de datos en aplicaciones híbridas.</span><span class="sxs-lookup"><span data-stu-id="45e65-114">When you are finished, you will have an understanding of data binding features in hybrid applications.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="45e65-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="45e65-115">Prerequisites</span></span>  
 <span data-ttu-id="45e65-116">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="45e65-116">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="45e65-117">.</span><span class="sxs-lookup"><span data-stu-id="45e65-117">.</span></span>  
  
-   <span data-ttu-id="45e65-118">Acceso a la base de datos de ejemplo Northwind con Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="45e65-118">Access to the Northwind sample database running on Microsoft SQL Server.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="45e65-119">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="45e65-119">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="45e65-120">Para crear y configurar el proyecto</span><span class="sxs-lookup"><span data-stu-id="45e65-120">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="45e65-121">Cree un proyecto de aplicación WPF denominado `WPFWithWFAndDatabinding`.</span><span class="sxs-lookup"><span data-stu-id="45e65-121">Create a WPF Application project named `WPFWithWFAndDatabinding`.</span></span>  
  
2.  <span data-ttu-id="45e65-122">En el Explorador de soluciones, agregue referencias a los ensamblados siguientes.</span><span class="sxs-lookup"><span data-stu-id="45e65-122">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="45e65-123">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="45e65-123">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="45e65-124">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="45e65-124">System.Windows.Forms</span></span>  
  
3.  <span data-ttu-id="45e65-125">Abra MainWindow.xaml en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45e65-125">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="45e65-126">En el <xref:System.Windows.Window> elemento, agregue las siguientes [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] asignación de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="45e65-126">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespaces mapping.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="45e65-127">El valor predeterminado el nombre <xref:System.Windows.Controls.Grid> elemento `mainGrid` asignando el <xref:System.Windows.FrameworkElement.Name%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="45e65-127">Name the default <xref:System.Windows.Controls.Grid> element `mainGrid` by assigning the <xref:System.Windows.FrameworkElement.Name%2A> property.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]  
  
## <a name="defining-the-data-template"></a><span data-ttu-id="45e65-128">Definir la plantilla de datos</span><span class="sxs-lookup"><span data-stu-id="45e65-128">Defining the Data Template</span></span>  
 <span data-ttu-id="45e65-129">Se muestra la lista maestra de clientes en un <xref:System.Windows.Controls.ListBox> control.</span><span class="sxs-lookup"><span data-stu-id="45e65-129">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="45e65-130">En el ejemplo de código siguiente se define un <xref:System.Windows.DataTemplate> objeto denominado `ListItemsTemplate` que controla el árbol visual de la <xref:System.Windows.Controls.ListBox> control.</span><span class="sxs-lookup"><span data-stu-id="45e65-130">The following code example defines a <xref:System.Windows.DataTemplate> object named `ListItemsTemplate` that controls the visual tree of the <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="45e65-131">Esto <xref:System.Windows.DataTemplate> se asigna a la <xref:System.Windows.Controls.ListBox> del control <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="45e65-131">This <xref:System.Windows.DataTemplate> is assigned to the <xref:System.Windows.Controls.ListBox> control's <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> property.</span></span>  
  
#### <a name="to-define-the-data-template"></a><span data-ttu-id="45e65-132">Para definir la plantilla de datos</span><span class="sxs-lookup"><span data-stu-id="45e65-132">To define the data template</span></span>  
  
-   <span data-ttu-id="45e65-133">Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> declaración del elemento.</span><span class="sxs-lookup"><span data-stu-id="45e65-133">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]  
  
## <a name="specifying-the-form-layout"></a><span data-ttu-id="45e65-134">Especificar el diseño del formulario</span><span class="sxs-lookup"><span data-stu-id="45e65-134">Specifying the Form Layout</span></span>  
 <span data-ttu-id="45e65-135">El diseño del formulario se define mediante una cuadrícula con tres filas y tres columnas.</span><span class="sxs-lookup"><span data-stu-id="45e65-135">The layout of the form is defined by a grid with three rows and three columns.</span></span> <span data-ttu-id="45e65-136"><xref:System.Windows.Controls.Label>dispone de controles para identificar cada columna de la tabla Customers.</span><span class="sxs-lookup"><span data-stu-id="45e65-136"><xref:System.Windows.Controls.Label> controls are provided to identify each column in the Customers table.</span></span>  
  
#### <a name="to-set-up-the-grid-layout"></a><span data-ttu-id="45e65-137">Para configurar el diseño de cuadrícula</span><span class="sxs-lookup"><span data-stu-id="45e65-137">To set up the Grid layout</span></span>  
  
-   <span data-ttu-id="45e65-138">Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> declaración del elemento.</span><span class="sxs-lookup"><span data-stu-id="45e65-138">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]  
  
#### <a name="to-set-up-the-label-controls"></a><span data-ttu-id="45e65-139">Para configurar los controles de etiqueta</span><span class="sxs-lookup"><span data-stu-id="45e65-139">To set up the Label controls</span></span>  
  
-   <span data-ttu-id="45e65-140">Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> declaración del elemento.</span><span class="sxs-lookup"><span data-stu-id="45e65-140">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]  
  
## <a name="specifying-data-bindings"></a><span data-ttu-id="45e65-141">Especificar los enlaces de datos</span><span class="sxs-lookup"><span data-stu-id="45e65-141">Specifying Data Bindings</span></span>  
 <span data-ttu-id="45e65-142">Se muestra la lista maestra de clientes en un <xref:System.Windows.Controls.ListBox> control.</span><span class="sxs-lookup"><span data-stu-id="45e65-142">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="45e65-143">El archivo adjunto `ListItemsTemplate` enlaza un <xref:System.Windows.Controls.TextBlock> el control a la `ContactName` arrastrándolo desde la base de datos.</span><span class="sxs-lookup"><span data-stu-id="45e65-143">The attached `ListItemsTemplate` binds a <xref:System.Windows.Controls.TextBlock> control to the `ContactName` field from the database.</span></span>  
  
 <span data-ttu-id="45e65-144">Se muestran los detalles de cada registro de cliente en varios <xref:System.Windows.Controls.TextBox> controles.</span><span class="sxs-lookup"><span data-stu-id="45e65-144">The details of each customer record are displayed in several <xref:System.Windows.Controls.TextBox> controls.</span></span>  
  
#### <a name="to-specify-data-bindings"></a><span data-ttu-id="45e65-145">Para especificar los enlaces de datos</span><span class="sxs-lookup"><span data-stu-id="45e65-145">To specify data bindings</span></span>  
  
-   <span data-ttu-id="45e65-146">Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> declaración del elemento.</span><span class="sxs-lookup"><span data-stu-id="45e65-146">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>  
  
     <span data-ttu-id="45e65-147">El <xref:System.Windows.Data.Binding> clase enlaza la <xref:System.Windows.Controls.TextBox> controles a los campos correspondientes de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="45e65-147">The <xref:System.Windows.Data.Binding> class binds the <xref:System.Windows.Controls.TextBox> controls to the appropriate fields in the database.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]  
  
## <a name="displaying-data-by-using-interoperation"></a><span data-ttu-id="45e65-148">Mostrar los datos mediante la interoperación</span><span class="sxs-lookup"><span data-stu-id="45e65-148">Displaying Data by Using Interoperation</span></span>  
 <span data-ttu-id="45e65-149">Se muestran los pedidos correspondientes al cliente seleccionado en un <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> control denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="45e65-149">The orders corresponding to the selected customer are displayed in a <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> control named `dataGridView1`.</span></span> <span data-ttu-id="45e65-150">El `dataGridView1` control se enlaza al origen de datos en el archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="45e65-150">The `dataGridView1` control is bound to the data source in the code-behind file.</span></span> <span data-ttu-id="45e65-151">A <xref:System.Windows.Forms.Integration.WindowsFormsHost> control es el elemento primario de este [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span><span class="sxs-lookup"><span data-stu-id="45e65-151">A <xref:System.Windows.Forms.Integration.WindowsFormsHost> control is the parent of this [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-display-data-in-the-datagridview-control"></a><span data-ttu-id="45e65-152">Para mostrar los datos en el control DataGridView</span><span class="sxs-lookup"><span data-stu-id="45e65-152">To display data in the DataGridView control</span></span>  
  
-   <span data-ttu-id="45e65-153">Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> declaración del elemento.</span><span class="sxs-lookup"><span data-stu-id="45e65-153">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]  
  
## <a name="adding-the-data-source-to-the-project"></a><span data-ttu-id="45e65-154">Agregar el origen de datos al proyecto</span><span class="sxs-lookup"><span data-stu-id="45e65-154">Adding the Data Source to the Project</span></span>  
 <span data-ttu-id="45e65-155">Con [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], puede agregar fácilmente un origen de datos al proyecto.</span><span class="sxs-lookup"><span data-stu-id="45e65-155">With [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], you can easily add a data source to your project.</span></span> <span data-ttu-id="45e65-156">Este procedimiento agrega un conjunto de datos fuertemente tipados a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="45e65-156">This procedure adds a strongly typed data set to your project.</span></span> <span data-ttu-id="45e65-157">También se agregan otras clases de compatibilidad, como adaptadores de tabla para cada una de las tablas elegidas.</span><span class="sxs-lookup"><span data-stu-id="45e65-157">Several other support classes, such as table adapters for each of the chosen tables, are also added.</span></span>  
  
#### <a name="to-add-the-data-source"></a><span data-ttu-id="45e65-158">Para agregar el origen de datos</span><span class="sxs-lookup"><span data-stu-id="45e65-158">To add the data source</span></span>  
  
1.  <span data-ttu-id="45e65-159">Desde el **datos** menú, seleccione **Agregar nuevo origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="45e65-159">From the **Data** menu, select **Add New Data Source**.</span></span>  
  
2.  <span data-ttu-id="45e65-160">En el **Asistente para configuración de orígenes de datos**, crear una conexión a la base de datos Northwind mediante el uso de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="45e65-160">In the **Data Source Configuration Wizard**, create a connection to the Northwind database by using a dataset.</span></span> <span data-ttu-id="45e65-161">Para obtener más información, consulte [Cómo: conectarse a los datos en una base de datos](http://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556).</span><span class="sxs-lookup"><span data-stu-id="45e65-161">For more information, see [How to: Connect to Data in a Database](http://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556).</span></span>  
  
3.  <span data-ttu-id="45e65-162">Cuando se le solicite en el **Asistente para configuración de orígenes de datos**, guardar la cadena de conexión como `NorthwindConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="45e65-162">When you are prompted by the **Data Source Configuration Wizard**, save the connection string as `NorthwindConnectionString`.</span></span>  
  
4.  <span data-ttu-id="45e65-163">Cuando se le pida que elija los objetos de base de datos, seleccione la `Customers` y `Orders` tablas y el nombre del conjunto de datos generado `NorthwindDataSet`.</span><span class="sxs-lookup"><span data-stu-id="45e65-163">When you are prompted to choose your database objects, select the `Customers` and `Orders` tables, and name the generated data set `NorthwindDataSet`.</span></span>  
  
## <a name="binding-to-the-data-source"></a><span data-ttu-id="45e65-164">Enlazar al origen de datos</span><span class="sxs-lookup"><span data-stu-id="45e65-164">Binding to the Data Source</span></span>  
 <span data-ttu-id="45e65-165">El <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> componente proporciona una interfaz uniforme para el origen de datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="45e65-165">The <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> component provides a uniform interface for the application's data source.</span></span> <span data-ttu-id="45e65-166">El enlace al origen de datos se implementa en el archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="45e65-166">Binding to the data source is implemented in the code-behind file.</span></span>  
  
#### <a name="to-bind-to-the-data-source"></a><span data-ttu-id="45e65-167">Para enlazar al origen de datos</span><span class="sxs-lookup"><span data-stu-id="45e65-167">To bind to the data source</span></span>  
  
1.  <span data-ttu-id="45e65-168">Abra el archivo de código subyacente, denominado MainWindow.xaml.vb o MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="45e65-168">Open the code-behind file, which is named MainWindow.xaml.vb or MainWindow.xaml.cs.</span></span>  
  
2.  <span data-ttu-id="45e65-169">Copie el código siguiente en el `MainWindow` definición de clase.</span><span class="sxs-lookup"><span data-stu-id="45e65-169">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     <span data-ttu-id="45e65-170">Este código declara los <xref:System.Windows.Forms.BindingSource> componente y las clases auxiliares asociadas que se conectan a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="45e65-170">This code declares the <xref:System.Windows.Forms.BindingSource> component and associated helper classes that connect to the database.</span></span>  
  
     [!code-csharp[WPFWithWFAndDatabinding#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]  
  
3.  <span data-ttu-id="45e65-171">Copie el siguiente código en el constructor.</span><span class="sxs-lookup"><span data-stu-id="45e65-171">Copy the following code into the constructor.</span></span>  
  
     <span data-ttu-id="45e65-172">Este código crea e inicializa el <xref:System.Windows.Forms.BindingSource> componente.</span><span class="sxs-lookup"><span data-stu-id="45e65-172">This code creates and initializes the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
     [!code-csharp[WPFWithWFAndDatabinding#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]  
  
4.  <span data-ttu-id="45e65-173">Abra MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="45e65-173">Open MainWindow.xaml.</span></span>  
  
5.  <span data-ttu-id="45e65-174">En la vista Diseño o la vista XAML, seleccione la <xref:System.Windows.Window> elemento.</span><span class="sxs-lookup"><span data-stu-id="45e65-174">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>  
  
6.  <span data-ttu-id="45e65-175">En la ventana Propiedades, haga clic en el **eventos** ficha.</span><span class="sxs-lookup"><span data-stu-id="45e65-175">In the Properties window, click the **Events** tab.</span></span>  
  
7.  <span data-ttu-id="45e65-176">Haga doble clic en el <xref:System.Windows.FrameworkElement.Loaded> eventos.</span><span class="sxs-lookup"><span data-stu-id="45e65-176">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
8.  <span data-ttu-id="45e65-177">Copie el código siguiente en el <xref:System.Windows.FrameworkElement.Loaded> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="45e65-177">Copy the following code into the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>  
  
     <span data-ttu-id="45e65-178">Este código asigna la <xref:System.Windows.Forms.BindingSource> componente como el contexto de datos y rellena el `Customers` y `Orders` objetos de adaptador.</span><span class="sxs-lookup"><span data-stu-id="45e65-178">This code assigns the <xref:System.Windows.Forms.BindingSource> component as the data context and populates the `Customers` and `Orders` adapter objects.</span></span>  
  
     [!code-csharp[WPFWithWFAndDatabinding#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]  
  
9. <span data-ttu-id="45e65-179">Copie el código siguiente en el `MainWindow` definición de clase.</span><span class="sxs-lookup"><span data-stu-id="45e65-179">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     <span data-ttu-id="45e65-180">Este método controla la <xref:System.Windows.Data.CollectionView.CurrentChanged> eventos y actualiza el elemento actual del enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="45e65-180">This method handles the <xref:System.Windows.Data.CollectionView.CurrentChanged> event and updates the current item of the data binding.</span></span>  
  
     [!code-csharp[WPFWithWFAndDatabinding#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]  
  
10. <span data-ttu-id="45e65-181">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="45e65-181">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45e65-182">Vea también</span><span class="sxs-lookup"><span data-stu-id="45e65-182">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="45e65-183">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="45e65-183">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="45e65-184">Enlace de datos de ejemplo de aplicaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="45e65-184">Data Binding in Hybrid Applications Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159983)  
 [<span data-ttu-id="45e65-185">Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="45e65-185">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="45e65-186">Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="45e65-186">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
