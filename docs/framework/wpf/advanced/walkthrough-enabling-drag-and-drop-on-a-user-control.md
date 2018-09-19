---
title: 'Tutorial: Habilitar la técnica de arrastrar y colocar en un control de usuario'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: e151eb7f428fecb330970210fd7addb1603a211f
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "45988717"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="f8835-102">Tutorial: Habilitar la técnica de arrastrar y colocar en un control de usuario</span><span class="sxs-lookup"><span data-stu-id="f8835-102">Walkthrough: Enabling Drag and Drop on a User Control</span></span>
<span data-ttu-id="f8835-103">En este tutorial se muestra cómo crear un control de usuario personalizado que pueda participar en la transferencia de datos de arrastrar y colocar en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8835-103">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="f8835-104">En este tutorial, creará un WPF personalizado <xref:System.Windows.Controls.UserControl> que representa una forma de círculo.</span><span class="sxs-lookup"><span data-stu-id="f8835-104">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="f8835-105">Implementará la funcionalidad del control para habilitar la transferencia de datos mediante la técnica de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="f8835-105">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="f8835-106">Por ejemplo, si arrastra de un control de círculo a otro, se copian los datos del color de relleno del círculo de origen al de destino.</span><span class="sxs-lookup"><span data-stu-id="f8835-106">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="f8835-107">Si arrastra de un control de círculo a un <xref:System.Windows.Controls.TextBox>, la representación de cadena del color de relleno se copia en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f8835-107">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="f8835-108">También creará una pequeña aplicación que contiene dos controles de panel y un <xref:System.Windows.Controls.TextBox> para probar la funcionalidad de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="f8835-108">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="f8835-109">Escribirá código para que los paneles puedan procesar los datos del círculo colocado, lo que le permitirá mover o copiar círculos de la colección secundaria de un panel a otro.</span><span class="sxs-lookup"><span data-stu-id="f8835-109">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>  
  
 <span data-ttu-id="f8835-110">En este tutorial se muestran las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f8835-110">This walkthrough illustrates the following tasks:</span></span>  
  
-   <span data-ttu-id="f8835-111">Crear un control de usuario personalizado.</span><span class="sxs-lookup"><span data-stu-id="f8835-111">Create a custom user control.</span></span>  
  
-   <span data-ttu-id="f8835-112">Permitir que el control de usuario sea un origen de arrastre.</span><span class="sxs-lookup"><span data-stu-id="f8835-112">Enable the user control to be a drag source.</span></span>  
  
-   <span data-ttu-id="f8835-113">Permitir que el control de usuario sea un destino de colocación.</span><span class="sxs-lookup"><span data-stu-id="f8835-113">Enable the user control to be a drop target.</span></span>  
  
-   <span data-ttu-id="f8835-114">Permitir que un panel reciba los datos que se colocan desde el control de usuario.</span><span class="sxs-lookup"><span data-stu-id="f8835-114">Enable a panel to receive data dropped from the user control.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f8835-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f8835-115">Prerequisites</span></span>  
 <span data-ttu-id="f8835-116">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="f8835-116">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="f8835-117">Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="f8835-117">Visual Studio 2010</span></span>  
  
## <a name="creating-the-application-project"></a><span data-ttu-id="f8835-118">Creación del proyecto de la aplicación</span><span class="sxs-lookup"><span data-stu-id="f8835-118">Creating the Application Project</span></span>  
 <span data-ttu-id="f8835-119">En esta sección, creará la infraestructura de aplicación, que incluye una página principal con dos paneles y un <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f8835-119">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
### <a name="to-create-the-project"></a><span data-ttu-id="f8835-120">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="f8835-120">To create the project</span></span>  
  
1.  <span data-ttu-id="f8835-121">Cree un proyecto de aplicación de WPF en Visual Basic o Visual C# denominado `DragDropExample`.</span><span class="sxs-lookup"><span data-stu-id="f8835-121">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="f8835-122">Para obtener más información, vea [Cómo: Crear un nuevo proyecto de aplicación de WPF](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="f8835-122">For more information, see [How to: Create a New WPF Application Project](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
2.  <span data-ttu-id="f8835-123">Abra MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="f8835-123">Open MainWindow.xaml.</span></span>  
  
3.  <span data-ttu-id="f8835-124">Agregue el marcado siguiente entre la apertura y cierre <xref:System.Windows.Controls.Grid> etiquetas.</span><span class="sxs-lookup"><span data-stu-id="f8835-124">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>  
  
     <span data-ttu-id="f8835-125">Este marcado crea la interfaz de usuario de la aplicación de prueba.</span><span class="sxs-lookup"><span data-stu-id="f8835-125">This markup creates the user interface for the test application.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]  
  
## <a name="adding-a-new-user-control-to-the-project"></a><span data-ttu-id="f8835-126">Agregar un nuevo control de usuario al proyecto</span><span class="sxs-lookup"><span data-stu-id="f8835-126">Adding a New User Control to the Project</span></span>  
 <span data-ttu-id="f8835-127">En esta sección, agregará un nuevo control de usuario al proyecto.</span><span class="sxs-lookup"><span data-stu-id="f8835-127">In this section, you will add a new user control to the project.</span></span>  
  
### <a name="to-add-a-new-user-control"></a><span data-ttu-id="f8835-128">Para agregar un nuevo control de usuario</span><span class="sxs-lookup"><span data-stu-id="f8835-128">To add a new user control</span></span>  
  
1.  <span data-ttu-id="f8835-129">En el menú Proyecto, seleccione **Agregar control de usuario**.</span><span class="sxs-lookup"><span data-stu-id="f8835-129">On the Project menu, select **Add User Control**.</span></span>  
  
2.  <span data-ttu-id="f8835-130">En el cuadro de diálogo Agregar nuevo elemento, cambie el nombre a `Circle.xaml` y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f8835-130">In the Add New Item dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>  
  
     <span data-ttu-id="f8835-131">Circle.xaml y su código subyacente se agregan al proyecto.</span><span class="sxs-lookup"><span data-stu-id="f8835-131">Circle.xaml and its code-behind is added to the project.</span></span>  
  
3.  <span data-ttu-id="f8835-132">Abra Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="f8835-132">Open Circle.xaml.</span></span>  
  
     <span data-ttu-id="f8835-133">Este archivo contendrá los elementos de la interfaz de usuario del control de usuario.</span><span class="sxs-lookup"><span data-stu-id="f8835-133">This file will contain the user interface elements of the user control.</span></span>  
  
4.  <span data-ttu-id="f8835-134">Agregue el marcado siguiente a la raíz <xref:System.Windows.Controls.Grid> para crear un control de usuario simple que tiene un círculo azul como interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="f8835-134">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#EllipseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]  
  
5.  <span data-ttu-id="f8835-135">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f8835-135">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
6.  <span data-ttu-id="f8835-136">En C#, agregue el código siguiente después del constructor predeterminado para crear un constructor de copias.</span><span class="sxs-lookup"><span data-stu-id="f8835-136">In C#, add the following code after the default constructor to create a copy constructor.</span></span> <span data-ttu-id="f8835-137">En Visual Basic, agregue el código siguiente para crear un constructor predeterminado y un constructor de copias.</span><span class="sxs-lookup"><span data-stu-id="f8835-137">In Visual Basic, add the following code to create both a default constructor and a copy constructor.</span></span>  
  
     <span data-ttu-id="f8835-138">Para permitir que se copie el control de usuario, puede agregar un método de constructor de copias en el archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="f8835-138">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="f8835-139">En el control de usuario de círculo simplificado, solo copiará el relleno y el tamaño del control de usuario.</span><span class="sxs-lookup"><span data-stu-id="f8835-139">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]  
  
### <a name="to-add-the-user-control-to-the-main-window"></a><span data-ttu-id="f8835-140">Para agregar el control de usuario a la ventana principal</span><span class="sxs-lookup"><span data-stu-id="f8835-140">To add the user control to the main window</span></span>  
  
1.  <span data-ttu-id="f8835-141">Abra MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="f8835-141">Open MainWindow.xaml.</span></span>  
  
2.  <span data-ttu-id="f8835-142">Agregue el siguiente XAML a la apertura <xref:System.Windows.Window> etiqueta para crear una referencia de espacio de nombres XML a la aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="f8835-142">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>  
  
    ```  
    xmlns:local="clr-namespace:DragDropExample"  
    ```  
  
3.  <span data-ttu-id="f8835-143">En la primera <xref:System.Windows.Controls.StackPanel>, agregue el siguiente XAML para crear dos instancias del control de usuario de círculo en el primer panel.</span><span class="sxs-lookup"><span data-stu-id="f8835-143">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#CirclesXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]  
  
     <span data-ttu-id="f8835-144">El código XAML completo del panel tendrá el aspecto siguiente.</span><span class="sxs-lookup"><span data-stu-id="f8835-144">The full XAML for the panel looks like the following.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]  
  
## <a name="implementing-drag-source-events-in-the-user-control"></a><span data-ttu-id="f8835-145">Implementar eventos del origen de arrastre en el control de usuario</span><span class="sxs-lookup"><span data-stu-id="f8835-145">Implementing Drag Source Events in the User Control</span></span>  
 <span data-ttu-id="f8835-146">En esta sección, invalidará la <xref:System.Windows.UIElement.OnMouseMove%2A> método e inicie la operación de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="f8835-146">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>  
  
 <span data-ttu-id="f8835-147">Si se inicia un arrastre (se presiona un botón del mouse y se mueve el mouse), empaquetará los datos que se transfieran a una <xref:System.Windows.DataObject>.</span><span class="sxs-lookup"><span data-stu-id="f8835-147">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="f8835-148">En este caso, el control de círculo empaquetará tres elementos de datos: una representación de cadena de su color de relleno, una representación doble de su altura y una copia de sí mismo.</span><span class="sxs-lookup"><span data-stu-id="f8835-148">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>  
  
### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="f8835-149">Para iniciar una operación de arrastrar y colocar</span><span class="sxs-lookup"><span data-stu-id="f8835-149">To initiate a drag-and-drop operation</span></span>  
  
1.  <span data-ttu-id="f8835-150">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f8835-150">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="f8835-151">Agregue el siguiente <xref:System.Windows.UIElement.OnMouseMove%2A> invalidación para proporcionar control de clases para el <xref:System.Windows.UIElement.MouseMove> eventos.</span><span class="sxs-lookup"><span data-stu-id="f8835-151">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]  
  
     <span data-ttu-id="f8835-152">Esto <xref:System.Windows.UIElement.OnMouseMove%2A> invalidación realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f8835-152">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="f8835-153">Comprueba si el botón primario del mouse está presionado mientras este se mueve.</span><span class="sxs-lookup"><span data-stu-id="f8835-153">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>  
  
    -   <span data-ttu-id="f8835-154">Empaqueta los datos de círculo en un <xref:System.Windows.DataObject>.</span><span class="sxs-lookup"><span data-stu-id="f8835-154">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="f8835-155">En este caso, el control de círculo empaqueta tres elementos de datos: una representación de cadena de su color de relleno, una representación doble de su altura y una copia de sí mismo.</span><span class="sxs-lookup"><span data-stu-id="f8835-155">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>  
  
    -   <span data-ttu-id="f8835-156">Llama a estático <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> método para iniciar la operación de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="f8835-156">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="f8835-157">Pasar los tres parámetros siguientes para el <xref:System.Windows.DragDrop.DoDragDrop%2A> método:</span><span class="sxs-lookup"><span data-stu-id="f8835-157">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>  
  
        -   <span data-ttu-id="f8835-158">`dragSource`: una referencia a este control.</span><span class="sxs-lookup"><span data-stu-id="f8835-158">`dragSource` – A reference to this control.</span></span>  
  
        -   <span data-ttu-id="f8835-159">`data` – La <xref:System.Windows.DataObject> creado en el código anterior.</span><span class="sxs-lookup"><span data-stu-id="f8835-159">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>  
  
        -   <span data-ttu-id="f8835-160">`allowedEffects` : Las operaciones de arrastrar y colocar permitidas, que son <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="f8835-160">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>  
  
3.  <span data-ttu-id="f8835-161">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f8835-161">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="f8835-162">Haga clic en uno de los controles de círculo y arrástrelo sobre los paneles, el otro círculo y el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f8835-162">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="f8835-163">Al arrastrar sobre el <xref:System.Windows.Controls.TextBox>, el cursor cambia para indicar un movimiento.</span><span class="sxs-lookup"><span data-stu-id="f8835-163">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>  
  
5.  <span data-ttu-id="f8835-164">Al arrastrar un círculo sobre la <xref:System.Windows.Controls.TextBox>, presione la tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="f8835-164">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the CTRL key.</span></span> <span data-ttu-id="f8835-165">Observe que el cursor cambia para indicar una copia.</span><span class="sxs-lookup"><span data-stu-id="f8835-165">Notice how the cursor changes to indicate a copy.</span></span>  
  
6.  <span data-ttu-id="f8835-166">Arrastre y coloque un círculo en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f8835-166">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="f8835-167">La representación de cadena del color de relleno del círculo se anexa a la <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f8835-167">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
     <span data-ttu-id="f8835-168">![Representación de cadena del color de relleno del círculo](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="f8835-168">![String representation of Circle's fill color](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>  
  
 <span data-ttu-id="f8835-169">De forma predeterminada, el cursor cambiará durante una operación de arrastrar y colocar para indicar el efecto que tendrá la colocación de los datos.</span><span class="sxs-lookup"><span data-stu-id="f8835-169">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="f8835-170">Puede personalizar la respuesta al usuario controlando el <xref:System.Windows.UIElement.GiveFeedback> eventos y establecer un cursor diferente.</span><span class="sxs-lookup"><span data-stu-id="f8835-170">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>  
  
### <a name="to-give-feedback-to-the-user"></a><span data-ttu-id="f8835-171">Para mostrar la respuesta al usuario</span><span class="sxs-lookup"><span data-stu-id="f8835-171">To give feedback to the user</span></span>  
  
1.  <span data-ttu-id="f8835-172">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f8835-172">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="f8835-173">Agregue el siguiente <xref:System.Windows.UIElement.OnGiveFeedback%2A> invalidación para proporcionar control de clases para el <xref:System.Windows.UIElement.GiveFeedback> eventos.</span><span class="sxs-lookup"><span data-stu-id="f8835-173">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]  
  
     <span data-ttu-id="f8835-174">Esto <xref:System.Windows.UIElement.OnGiveFeedback%2A> invalidación realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f8835-174">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="f8835-175">Comprueba la <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valores que se establecen en el destino de colocación <xref:System.Windows.UIElement.DragOver> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="f8835-175">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>  
  
    -   <span data-ttu-id="f8835-176">Establece un cursor personalizado basado en la <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valor.</span><span class="sxs-lookup"><span data-stu-id="f8835-176">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="f8835-177">El cursor está diseñado para proporcionar información visual al usuario sobre el efecto que tendrá la colocación de los datos.</span><span class="sxs-lookup"><span data-stu-id="f8835-177">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>  
  
3.  <span data-ttu-id="f8835-178">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f8835-178">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="f8835-179">Arrastre uno del círculo se controla a través de los paneles, el otro círculo, y el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f8835-179">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="f8835-180">Tenga en cuenta que los cursores son ahora los cursores personalizados que especificó en el <xref:System.Windows.UIElement.OnGiveFeedback%2A> invalidar.</span><span class="sxs-lookup"><span data-stu-id="f8835-180">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>  
  
     <span data-ttu-id="f8835-181">![Arrastrar y colocar con cursores personalizados](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="f8835-181">![Drag and drop with custom cursors](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>  
  
5.  <span data-ttu-id="f8835-182">Seleccione el texto `green` desde el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f8835-182">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
6.  <span data-ttu-id="f8835-183">Arrastre el texto `green` a un control de círculo.</span><span class="sxs-lookup"><span data-stu-id="f8835-183">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="f8835-184">Observe que los cursores predeterminados se muestran para indicar los efectos de la operación de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="f8835-184">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="f8835-185">El origen de arrastre siempre establece el cursor de retroacción.</span><span class="sxs-lookup"><span data-stu-id="f8835-185">The feedback cursor is always set by the drag source.</span></span>  
  
## <a name="implementing-drop-target-events-in-the-user-control"></a><span data-ttu-id="f8835-186">Implementar eventos del destino de colocación en el control de usuario</span><span class="sxs-lookup"><span data-stu-id="f8835-186">Implementing Drop Target Events in the User Control</span></span>  
 <span data-ttu-id="f8835-187">En esta sección, especificará que el control de usuario es un destino de colocación, invalidará los métodos que permiten que el control de usuario sea un destino de colocación y procesará los datos que se colocan en él.</span><span class="sxs-lookup"><span data-stu-id="f8835-187">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>  
  
### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="f8835-188">Para permitir que el control de usuario sea un destino de colocación</span><span class="sxs-lookup"><span data-stu-id="f8835-188">To enable the user control to be a drop target</span></span>  
  
1.  <span data-ttu-id="f8835-189">Abra Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="f8835-189">Open Circle.xaml.</span></span>  
  
2.  <span data-ttu-id="f8835-190">En la apertura <xref:System.Windows.Controls.UserControl> etiqueta, agregue el <xref:System.Windows.UIElement.AllowDrop%2A> propiedad y establecerla en `true`.</span><span class="sxs-lookup"><span data-stu-id="f8835-190">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#UCTagXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]  
  
 <span data-ttu-id="f8835-191">El <xref:System.Windows.UIElement.OnDrop%2A> método se llama cuando el <xref:System.Windows.UIElement.AllowDrop%2A> propiedad está establecida en `true` y se colocan los datos del origen de arrastre en el control de usuario de círculo.</span><span class="sxs-lookup"><span data-stu-id="f8835-191">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="f8835-192">En este método, procesará los datos que se han colocado y aplicará los datos al círculo.</span><span class="sxs-lookup"><span data-stu-id="f8835-192">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>  
  
### <a name="to-process-the-dropped-data"></a><span data-ttu-id="f8835-193">Para procesar los datos colocados</span><span class="sxs-lookup"><span data-stu-id="f8835-193">To process the dropped data</span></span>  
  
1.  <span data-ttu-id="f8835-194">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f8835-194">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="f8835-195">Agregue el siguiente <xref:System.Windows.UIElement.OnDrop%2A> invalidación para proporcionar control de clases para el <xref:System.Windows.UIElement.Drop> eventos.</span><span class="sxs-lookup"><span data-stu-id="f8835-195">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]  
  
     <span data-ttu-id="f8835-196">Esto <xref:System.Windows.UIElement.OnDrop%2A> invalidación realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f8835-196">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="f8835-197">Usa el <xref:System.Windows.DataObject.GetDataPresent%2A> método para comprobar si los datos arrastrados contienen un objeto de cadena.</span><span class="sxs-lookup"><span data-stu-id="f8835-197">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>  
  
    -   <span data-ttu-id="f8835-198">Usa el <xref:System.Windows.DataObject.GetData%2A> método para extraer los datos de cadena, si está presente.</span><span class="sxs-lookup"><span data-stu-id="f8835-198">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>  
  
    -   <span data-ttu-id="f8835-199">Usa un <xref:System.Windows.Media.BrushConverter> para intentar convertir la cadena en un <xref:System.Windows.Media.Brush>.</span><span class="sxs-lookup"><span data-stu-id="f8835-199">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>  
  
    -   <span data-ttu-id="f8835-200">Si la conversión se realiza correctamente, se aplica el pincel para el <xref:System.Windows.Shapes.Shape.Fill%2A> de la <xref:System.Windows.Shapes.Ellipse> que proporciona la interfaz de usuario del control de círculo.</span><span class="sxs-lookup"><span data-stu-id="f8835-200">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>  
  
    -   <span data-ttu-id="f8835-201">Las marcas de la <xref:System.Windows.UIElement.Drop> evento como controlado.</span><span class="sxs-lookup"><span data-stu-id="f8835-201">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="f8835-202">Debe marcar el evento de colocación como controlado para que los elementos que reciban este evento sepan que el control de usuario de círculo lo ha controlado.</span><span class="sxs-lookup"><span data-stu-id="f8835-202">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>  
  
3.  <span data-ttu-id="f8835-203">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f8835-203">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="f8835-204">Seleccione el texto `green` en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f8835-204">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
5.  <span data-ttu-id="f8835-205">Arrastre el texto a un control de círculo y colóquelo.</span><span class="sxs-lookup"><span data-stu-id="f8835-205">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="f8835-206">El círculo cambia de azul a verde.</span><span class="sxs-lookup"><span data-stu-id="f8835-206">The Circle changes from blue to green.</span></span>  
  
     <span data-ttu-id="f8835-207">![Convertir una cadena en un pincel](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="f8835-207">![Convert a string to a brush](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>  
  
6.  <span data-ttu-id="f8835-208">Escriba el texto `green` en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f8835-208">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
7.  <span data-ttu-id="f8835-209">Seleccione el texto `gre` en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f8835-209">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
8.  <span data-ttu-id="f8835-210">Arrástrelo a un control de círculo y colóquelo.</span><span class="sxs-lookup"><span data-stu-id="f8835-210">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="f8835-211">Observe que el cursor cambia para indicar que se permite la colocación, pero el color del círculo no cambia porque `gre` no es un color válido.</span><span class="sxs-lookup"><span data-stu-id="f8835-211">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>  
  
9. <span data-ttu-id="f8835-212">Arrastre desde el control de círculo verde y coloque en el control de círculo azul.</span><span class="sxs-lookup"><span data-stu-id="f8835-212">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="f8835-213">El círculo cambia de azul a verde.</span><span class="sxs-lookup"><span data-stu-id="f8835-213">The Circle changes from blue to green.</span></span> <span data-ttu-id="f8835-214">Tenga en cuenta que el cursor que se muestra depende de si el <xref:System.Windows.Controls.TextBox> o el círculo es el origen de arrastre.</span><span class="sxs-lookup"><span data-stu-id="f8835-214">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>  
  
 <span data-ttu-id="f8835-215">Establecer el <xref:System.Windows.UIElement.AllowDrop%2A> propiedad `true` y procesar los datos colocados es todo lo que es necesario para habilitar un elemento para que sea un destino de colocación.</span><span class="sxs-lookup"><span data-stu-id="f8835-215">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="f8835-216">Sin embargo, para proporcionar una mejor experiencia de usuario, también debe controlar la <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, y <xref:System.Windows.UIElement.DragOver> eventos.</span><span class="sxs-lookup"><span data-stu-id="f8835-216">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="f8835-217">En estos eventos, puede realizar comprobaciones y proporcionar repuesta adicional al usuario antes de que se coloquen los datos.</span><span class="sxs-lookup"><span data-stu-id="f8835-217">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>  
  
 <span data-ttu-id="f8835-218">Cuando los datos se arrastran sobre el control de usuario de círculo, el control debe notificarle al origen de arrastre si puede procesar los datos que se están arrastrando.</span><span class="sxs-lookup"><span data-stu-id="f8835-218">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="f8835-219">Si el control no sabe cómo procesar los datos, debe rechazar la operación de colocar.</span><span class="sxs-lookup"><span data-stu-id="f8835-219">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="f8835-220">Para ello, controlará el <xref:System.Windows.UIElement.DragOver> evento y establecer el <xref:System.Windows.DragEventArgs.Effects%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f8835-220">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>  
  
### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="f8835-221">Para comprobar que se permite la colocación de datos</span><span class="sxs-lookup"><span data-stu-id="f8835-221">To verify that the data drop is allowed</span></span>  
  
1.  <span data-ttu-id="f8835-222">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f8835-222">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="f8835-223">Agregue el siguiente <xref:System.Windows.UIElement.OnDragOver%2A> invalidación para proporcionar control de clases para el <xref:System.Windows.UIElement.DragOver> eventos.</span><span class="sxs-lookup"><span data-stu-id="f8835-223">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]  
  
     <span data-ttu-id="f8835-224">Esto <xref:System.Windows.UIElement.OnDragOver%2A> invalidación realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f8835-224">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="f8835-225">Establece la propiedad <xref:System.Windows.DragEventArgs.Effects%2A> como <xref:System.Windows.DragDropEffects.None>.</span><span class="sxs-lookup"><span data-stu-id="f8835-225">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>  
  
    -   <span data-ttu-id="f8835-226">Realiza las mismas comprobaciones que se realizan en el <xref:System.Windows.UIElement.OnDrop%2A> método para determinar si el control de usuario de círculo puede procesar los datos arrastrados.</span><span class="sxs-lookup"><span data-stu-id="f8835-226">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>  
  
    -   <span data-ttu-id="f8835-227">Si el control de usuario puede procesar los datos, Establece la <xref:System.Windows.DragEventArgs.Effects%2A> propiedad <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="f8835-227">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>  
  
3.  <span data-ttu-id="f8835-228">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f8835-228">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="f8835-229">Seleccione el texto `gre` en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f8835-229">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
5.  <span data-ttu-id="f8835-230">Arrastre el texto a un control de círculo.</span><span class="sxs-lookup"><span data-stu-id="f8835-230">Drag the text to a Circle control.</span></span> <span data-ttu-id="f8835-231">Observe que ahora el cursor cambia para indicar que no se permite la colocación porque `gre` no es un color válido.</span><span class="sxs-lookup"><span data-stu-id="f8835-231">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>  
  
 <span data-ttu-id="f8835-232">Puede mejorar la experiencia del usuario si aplica una vista previa de la operación de colocar.</span><span class="sxs-lookup"><span data-stu-id="f8835-232">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="f8835-233">Para el control de usuario de círculo, invalidará el <xref:System.Windows.UIElement.OnDragEnter%2A> y <xref:System.Windows.UIElement.OnDragLeave%2A> métodos.</span><span class="sxs-lookup"><span data-stu-id="f8835-233">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="f8835-234">Cuando se arrastran los datos sobre el control, el fondo actual <xref:System.Windows.Shapes.Shape.Fill%2A> se guarda en una variable de marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="f8835-234">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="f8835-235">La cadena se convierte en un pincel, a continuación y se aplica a la <xref:System.Windows.Shapes.Ellipse> que proporciona el círculo de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="f8835-235">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="f8835-236">Si los datos se arrastran fuera del círculo sin colocarse, el original <xref:System.Windows.Shapes.Shape.Fill%2A> valor se vuelve a aplicar al círculo.</span><span class="sxs-lookup"><span data-stu-id="f8835-236">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>  
  
### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="f8835-237">Para obtener una vista previa de los efectos de la operación de arrastrar y colocar</span><span class="sxs-lookup"><span data-stu-id="f8835-237">To preview the effects of the drag-and-drop operation</span></span>  
  
1.  <span data-ttu-id="f8835-238">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f8835-238">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="f8835-239">En la clase Circle, declare una privada <xref:System.Windows.Media.Brush> variable denominada `_previousFill` e inicialícelo como `null`.</span><span class="sxs-lookup"><span data-stu-id="f8835-239">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#Brush](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]  
  
3.  <span data-ttu-id="f8835-240">Agregue el siguiente <xref:System.Windows.UIElement.OnDragEnter%2A> invalidación para proporcionar control de clases para el <xref:System.Windows.UIElement.DragEnter> eventos.</span><span class="sxs-lookup"><span data-stu-id="f8835-240">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]  
  
     <span data-ttu-id="f8835-241">Esto <xref:System.Windows.UIElement.OnDragEnter%2A> invalidación realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f8835-241">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="f8835-242">Guarda el <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad de la <xref:System.Windows.Shapes.Ellipse> en el `_previousFill` variable.</span><span class="sxs-lookup"><span data-stu-id="f8835-242">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>  
  
    -   <span data-ttu-id="f8835-243">Realiza las mismas comprobaciones que se realizan en el <xref:System.Windows.UIElement.OnDrop%2A> método para determinar si los datos pueden convertirse en un <xref:System.Windows.Media.Brush>.</span><span class="sxs-lookup"><span data-stu-id="f8835-243">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>  
  
    -   <span data-ttu-id="f8835-244">Si los datos se convierten en válido <xref:System.Windows.Media.Brush>, se aplica a la <xref:System.Windows.Shapes.Shape.Fill%2A> de la <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="f8835-244">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
4.  <span data-ttu-id="f8835-245">Agregue el siguiente <xref:System.Windows.UIElement.OnDragLeave%2A> invalidación para proporcionar control de clases para el <xref:System.Windows.UIElement.DragLeave> eventos.</span><span class="sxs-lookup"><span data-stu-id="f8835-245">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]  
  
     <span data-ttu-id="f8835-246">Esto <xref:System.Windows.UIElement.OnDragLeave%2A> invalidación realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f8835-246">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="f8835-247">Se aplica el <xref:System.Windows.Media.Brush> guardado en el `_previousFill` variable a la <xref:System.Windows.Shapes.Shape.Fill%2A> de la <xref:System.Windows.Shapes.Ellipse> que proporciona la interfaz de usuario del control de usuario de círculo.</span><span class="sxs-lookup"><span data-stu-id="f8835-247">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>  
  
5.  <span data-ttu-id="f8835-248">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f8835-248">Press F5 to build and run the application.</span></span>  
  
6.  <span data-ttu-id="f8835-249">Seleccione el texto `green` en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f8835-249">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
7.  <span data-ttu-id="f8835-250">Arrastre el texto sobre un control de círculo sin colocarlo.</span><span class="sxs-lookup"><span data-stu-id="f8835-250">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="f8835-251">El círculo cambia de azul a verde.</span><span class="sxs-lookup"><span data-stu-id="f8835-251">The Circle changes from blue to green.</span></span>  
  
     <span data-ttu-id="f8835-252">![Vista previa de los efectos de una operación de arrastrar y colocar](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="f8835-252">![Preview the effects of a drag&#45;and&#45;drop operation](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>  
  
8.  <span data-ttu-id="f8835-253">Arrastre el texto fuera del control de círculo.</span><span class="sxs-lookup"><span data-stu-id="f8835-253">Drag the text away from the Circle control.</span></span> <span data-ttu-id="f8835-254">El círculo cambia de verde a azul.</span><span class="sxs-lookup"><span data-stu-id="f8835-254">The Circle changes from green back to blue.</span></span>  
  
## <a name="enabling-a-panel-to-receive-dropped-data"></a><span data-ttu-id="f8835-255">Permitir que un panel reciba los datos colocados</span><span class="sxs-lookup"><span data-stu-id="f8835-255">Enabling a Panel to Receive Dropped Data</span></span>  
 <span data-ttu-id="f8835-256">En esta sección, habilitará los paneles que hospedan los controles de usuario de círculo de modo que actúen como destinos de colocación de los datos de círculo arrastrados.</span><span class="sxs-lookup"><span data-stu-id="f8835-256">In this section, you will enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="f8835-257">Implementará código que le permita mover un círculo de un panel a otro o hacer una copia de un control de círculo manteniendo presionada la tecla Ctrl mientras arrastra y coloca un círculo.</span><span class="sxs-lookup"><span data-stu-id="f8835-257">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the CTRL key while dragging and dropping a Circle.</span></span>  
  
### <a name="to-enable-the-panel-to-be-a-drop-target"></a><span data-ttu-id="f8835-258">Para permitir que el panel sea un destino de colocación</span><span class="sxs-lookup"><span data-stu-id="f8835-258">To enable the panel to be a drop target</span></span>  
  
1.  <span data-ttu-id="f8835-259">Abra MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="f8835-259">Open MainWindow.xaml.</span></span>  
  
2.  <span data-ttu-id="f8835-260">Como se muestra en el siguiente XAML, en cada uno de los <xref:System.Windows.Controls.StackPanel> controles, agregue controladores para la <xref:System.Windows.UIElement.DragOver> y <xref:System.Windows.UIElement.Drop> eventos.</span><span class="sxs-lookup"><span data-stu-id="f8835-260">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="f8835-261">Nombre de la <xref:System.Windows.UIElement.DragOver> controlador de eventos, `panel_DragOver`y el nombre del <xref:System.Windows.UIElement.Drop> controlador de eventos, `panel_Drop`.</span><span class="sxs-lookup"><span data-stu-id="f8835-261">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#PanelsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]  
  
3.  <span data-ttu-id="f8835-262">Abra MainWindows.xaml.cs o MainWindow.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f8835-262">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>  
  
4.  <span data-ttu-id="f8835-263">Agregue el siguiente código para el <xref:System.Windows.UIElement.DragOver> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="f8835-263">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]  
  
     <span data-ttu-id="f8835-264">Esto <xref:System.Windows.UIElement.DragOver> controlador de eventos realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="f8835-264">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="f8835-265">Comprueba que los datos arrastrados contienen los datos de "Objeto" que se ha empaquetado en la <xref:System.Windows.DataObject> por el control de usuario de círculo y se pasa en la llamada a <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span><span class="sxs-lookup"><span data-stu-id="f8835-265">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>  
  
    -   <span data-ttu-id="f8835-266">Si los datos "Object" están presentes, comprueba si se ha presionado la tecla Ctrl.</span><span class="sxs-lookup"><span data-stu-id="f8835-266">If the "Object" data is present, checks whether the CTRL key is pressed.</span></span>  
  
    -   <span data-ttu-id="f8835-267">Si se presiona la tecla CTRL, Establece el <xref:System.Windows.DragEventArgs.Effects%2A> propiedad <xref:System.Windows.DragDropEffects.Copy>.</span><span class="sxs-lookup"><span data-stu-id="f8835-267">If the CTRL key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="f8835-268">En caso contrario, establezca el <xref:System.Windows.DragEventArgs.Effects%2A> propiedad <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="f8835-268">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>  
  
5.  <span data-ttu-id="f8835-269">Agregue el siguiente código para el <xref:System.Windows.UIElement.Drop> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="f8835-269">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]  
  
     <span data-ttu-id="f8835-270">Esto <xref:System.Windows.UIElement.Drop> controlador de eventos realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="f8835-270">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="f8835-271">Comprueba si el <xref:System.Windows.UIElement.Drop> ya se ha controlado el evento.</span><span class="sxs-lookup"><span data-stu-id="f8835-271">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="f8835-272">Por ejemplo, si coloca un círculo en otro círculo que controla la <xref:System.Windows.UIElement.Drop> eventos, no desea que el panel que contiene el círculo también lo controle.</span><span class="sxs-lookup"><span data-stu-id="f8835-272">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>  
  
    -   <span data-ttu-id="f8835-273">Si el <xref:System.Windows.UIElement.Drop> eventos no se controla, comprueba si se presiona la tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="f8835-273">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the CTRL key is pressed.</span></span>  
  
    -   <span data-ttu-id="f8835-274">Si se presiona la tecla CTRL cuando el <xref:System.Windows.UIElement.Drop> sucede, hace una copia del círculo, controla y agréguelo a la <xref:System.Windows.Controls.Panel.Children%2A> colección de la <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="f8835-274">If the CTRL key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
    -   <span data-ttu-id="f8835-275">Si no presiona la tecla CTRL, mueve el círculo de la <xref:System.Windows.Controls.Panel.Children%2A> colección de su panel primario a la <xref:System.Windows.Controls.Panel.Children%2A> colección del panel que se ha colocado.</span><span class="sxs-lookup"><span data-stu-id="f8835-275">If the CTRL key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>  
  
    -   <span data-ttu-id="f8835-276">Establece el <xref:System.Windows.DragEventArgs.Effects%2A> propiedad para notificar a la <xref:System.Windows.DragDrop.DoDragDrop%2A> método si se realizó una operación de mover o copiar.</span><span class="sxs-lookup"><span data-stu-id="f8835-276">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>  
  
6.  <span data-ttu-id="f8835-277">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f8835-277">Press F5 to build and run the application.</span></span>  
  
7.  <span data-ttu-id="f8835-278">Seleccione el texto `green` desde el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f8835-278">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
8.  <span data-ttu-id="f8835-279">Arrastre el texto sobre un control de círculo y colóquelo.</span><span class="sxs-lookup"><span data-stu-id="f8835-279">Drag the text over a Circle control and drop it.</span></span>  
  
9. <span data-ttu-id="f8835-280">Arrastre un control de círculo del panel izquierdo al panel derecho y colóquelo.</span><span class="sxs-lookup"><span data-stu-id="f8835-280">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="f8835-281">El círculo se quita de la <xref:System.Windows.Controls.Panel.Children%2A> colección del panel izquierdo y se agrega a la colección de elementos secundarios del panel derecho.</span><span class="sxs-lookup"><span data-stu-id="f8835-281">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>  
  
10. <span data-ttu-id="f8835-282">Arrastre un control círculo del panel en el que se encuentra al otro panel y colóquelo mientras presiona la tecla Ctrl.</span><span class="sxs-lookup"><span data-stu-id="f8835-282">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the CTRL key.</span></span> <span data-ttu-id="f8835-283">El círculo se copia y la copia se agrega a la <xref:System.Windows.Controls.Panel.Children%2A> colección del panel receptor.</span><span class="sxs-lookup"><span data-stu-id="f8835-283">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>  
  
     <span data-ttu-id="f8835-284">![Arrastrar un círculo mientras se presiona la tecla Ctrl](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="f8835-284">![Dragging a Circle while pressing the CTRL key](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8835-285">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8835-285">See Also</span></span>  
 [<span data-ttu-id="f8835-286">Información general sobre la función de arrastrar y colocar</span><span class="sxs-lookup"><span data-stu-id="f8835-286">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
