---
title: 'Tutorial: Habilitar la técnica de arrastrar y colocar en un control de usuario'
description: Obtenga información sobre cómo crear un control de usuario personalizado que pueda participar en la transferencia de datos de arrastrar y colocar en Windows Presentation Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: 12ad47035a09995094014841b083062743fc2574
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168285"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="a58d5-103">Tutorial: Habilitar la técnica de arrastrar y colocar en un control de usuario</span><span class="sxs-lookup"><span data-stu-id="a58d5-103">Walkthrough: Enabling Drag and Drop on a User Control</span></span>

<span data-ttu-id="a58d5-104">En este tutorial se muestra cómo crear un control de usuario personalizado que pueda participar en la transferencia de datos de arrastrar y colocar en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a58d5-104">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>

<span data-ttu-id="a58d5-105">En este tutorial, creará un WPF personalizado <xref:System.Windows.Controls.UserControl> que representa una forma circular.</span><span class="sxs-lookup"><span data-stu-id="a58d5-105">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="a58d5-106">Implementará la funcionalidad del control para habilitar la transferencia de datos mediante la técnica de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="a58d5-106">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="a58d5-107">Por ejemplo, si arrastra de un control de círculo a otro, se copian los datos del color de relleno del círculo de origen al de destino.</span><span class="sxs-lookup"><span data-stu-id="a58d5-107">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="a58d5-108">Si arrastra de un control de círculo a un <xref:System.Windows.Controls.TextBox> , la representación de cadena del color de relleno se copia en <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-108">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="a58d5-109">También creará una pequeña aplicación que contiene dos controles de panel y un <xref:System.Windows.Controls.TextBox> para probar la funcionalidad de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="a58d5-109">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="a58d5-110">Escribirá código para que los paneles puedan procesar los datos del círculo colocado, lo que le permitirá mover o copiar círculos de la colección secundaria de un panel a otro.</span><span class="sxs-lookup"><span data-stu-id="a58d5-110">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>

<span data-ttu-id="a58d5-111">En este tutorial se muestran las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a58d5-111">This walkthrough illustrates the following tasks:</span></span>

- <span data-ttu-id="a58d5-112">Crear un control de usuario personalizado.</span><span class="sxs-lookup"><span data-stu-id="a58d5-112">Create a custom user control.</span></span>

- <span data-ttu-id="a58d5-113">Permitir que el control de usuario sea un origen de arrastre.</span><span class="sxs-lookup"><span data-stu-id="a58d5-113">Enable the user control to be a drag source.</span></span>

- <span data-ttu-id="a58d5-114">Permitir que el control de usuario sea un destino de colocación.</span><span class="sxs-lookup"><span data-stu-id="a58d5-114">Enable the user control to be a drop target.</span></span>

- <span data-ttu-id="a58d5-115">Permitir que un panel reciba los datos que se colocan desde el control de usuario.</span><span class="sxs-lookup"><span data-stu-id="a58d5-115">Enable a panel to receive data dropped from the user control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a58d5-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a58d5-116">Prerequisites</span></span>

<span data-ttu-id="a58d5-117">Necesita Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="a58d5-117">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="a58d5-118">Crear el proyecto de aplicación</span><span class="sxs-lookup"><span data-stu-id="a58d5-118">Create the Application Project</span></span>
 <span data-ttu-id="a58d5-119">En esta sección, creará la infraestructura de la aplicación, que incluye una página principal con dos paneles y un <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-119">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>

1. <span data-ttu-id="a58d5-120">Cree un proyecto de aplicación de WPF en Visual Basic o Visual C# denominado `DragDropExample`.</span><span class="sxs-lookup"><span data-stu-id="a58d5-120">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="a58d5-121">Para obtener más información, vea [Tutorial: Mi primera aplicación de escritorio WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="a58d5-121">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

2. <span data-ttu-id="a58d5-122">Abra MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="a58d5-122">Open MainWindow.xaml.</span></span>

3. <span data-ttu-id="a58d5-123">Agregue el marcado siguiente entre las etiquetas de apertura y cierre <xref:System.Windows.Controls.Grid> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-123">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>

     <span data-ttu-id="a58d5-124">Este marcado crea la interfaz de usuario de la aplicación de prueba.</span><span class="sxs-lookup"><span data-stu-id="a58d5-124">This markup creates the user interface for the test application.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a><span data-ttu-id="a58d5-125">Agregar un nuevo control de usuario al proyecto</span><span class="sxs-lookup"><span data-stu-id="a58d5-125">Add a New User Control to the Project</span></span>
 <span data-ttu-id="a58d5-126">En esta sección, agregará un nuevo control de usuario al proyecto.</span><span class="sxs-lookup"><span data-stu-id="a58d5-126">In this section, you will add a new user control to the project.</span></span>

1. <span data-ttu-id="a58d5-127">En el menú Proyecto, seleccione **Agregar control de usuario**.</span><span class="sxs-lookup"><span data-stu-id="a58d5-127">On the Project menu, select **Add User Control**.</span></span>

2. <span data-ttu-id="a58d5-128">En el cuadro de diálogo **Agregar nuevo elemento** , cambie el nombre a `Circle.xaml` y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a58d5-128">In the **Add New Item** dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>

     <span data-ttu-id="a58d5-129">Circle.xaml y su código subyacente se agregan al proyecto.</span><span class="sxs-lookup"><span data-stu-id="a58d5-129">Circle.xaml and its code-behind is added to the project.</span></span>

3. <span data-ttu-id="a58d5-130">Abra Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="a58d5-130">Open Circle.xaml.</span></span>

     <span data-ttu-id="a58d5-131">Este archivo contendrá los elementos de la interfaz de usuario del control de usuario.</span><span class="sxs-lookup"><span data-stu-id="a58d5-131">This file will contain the user interface elements of the user control.</span></span>

4. <span data-ttu-id="a58d5-132">Agregue el siguiente marcado a la raíz <xref:System.Windows.Controls.Grid> para crear un control de usuario simple que tenga un círculo azul como su interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="a58d5-132">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>

     [!code-xaml[DragDropWalkthrough#EllipseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5. <span data-ttu-id="a58d5-133">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="a58d5-133">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

6. <span data-ttu-id="a58d5-134">En C#, agregue el código siguiente después del constructor sin parámetros para crear un constructor de copias.</span><span class="sxs-lookup"><span data-stu-id="a58d5-134">In C#, add the following code after the parameterless constructor to create a copy constructor.</span></span> <span data-ttu-id="a58d5-135">En Visual Basic, agregue el código siguiente para crear un constructor sin parámetros y un constructor de copias.</span><span class="sxs-lookup"><span data-stu-id="a58d5-135">In Visual Basic, add the following code to create both a parameterless constructor and a copy constructor.</span></span>

     <span data-ttu-id="a58d5-136">Para permitir que se copie el control de usuario, puede agregar un método de constructor de copias en el archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="a58d5-136">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="a58d5-137">En el control de usuario de círculo simplificado, solo copiará el relleno y el tamaño del control de usuario.</span><span class="sxs-lookup"><span data-stu-id="a58d5-137">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>

     [!code-csharp[DragDropWalkthrough#CopyCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a><span data-ttu-id="a58d5-138">Agregar el control de usuario a la ventana principal</span><span class="sxs-lookup"><span data-stu-id="a58d5-138">Add the user control to the main window</span></span>

1. <span data-ttu-id="a58d5-139">Abra MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="a58d5-139">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="a58d5-140">Agregue el código XAML siguiente a la <xref:System.Windows.Window> etiqueta de apertura para crear una referencia de espacio de nombres XML a la aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="a58d5-140">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>

    ```xaml
    xmlns:local="clr-namespace:DragDropExample"
    ```

3. <span data-ttu-id="a58d5-141">En la primera <xref:System.Windows.Controls.StackPanel> , agregue el código XAML siguiente para crear dos instancias del control de usuario de círculo en el primer panel.</span><span class="sxs-lookup"><span data-stu-id="a58d5-141">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>

     [!code-xaml[DragDropWalkthrough#CirclesXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     <span data-ttu-id="a58d5-142">El código XAML completo del panel tendrá el aspecto siguiente.</span><span class="sxs-lookup"><span data-stu-id="a58d5-142">The full XAML for the panel looks like the following.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a><span data-ttu-id="a58d5-143">Implementar eventos de origen de arrastre en el control de usuario</span><span class="sxs-lookup"><span data-stu-id="a58d5-143">Implement Drag Source Events in the User Control</span></span>
 <span data-ttu-id="a58d5-144">En esta sección, se invalidará el <xref:System.Windows.UIElement.OnMouseMove%2A> método y se iniciará la operación de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="a58d5-144">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>

 <span data-ttu-id="a58d5-145">Si se inicia un arrastre (se presiona un botón del mouse y se mueve el mouse), se empaquetarán los datos que se van a transferir a <xref:System.Windows.DataObject> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-145">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="a58d5-146">En este caso, el control de círculo empaquetará tres elementos de datos: una representación de cadena de su color de relleno, una representación doble de su altura y una copia de sí mismo.</span><span class="sxs-lookup"><span data-stu-id="a58d5-146">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="a58d5-147">Para iniciar una operación de arrastrar y colocar</span><span class="sxs-lookup"><span data-stu-id="a58d5-147">To initiate a drag-and-drop operation</span></span>

1. <span data-ttu-id="a58d5-148">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="a58d5-148">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="a58d5-149">Agregue la siguiente <xref:System.Windows.UIElement.OnMouseMove%2A> invalidación para proporcionar el control de clases para el <xref:System.Windows.UIElement.MouseMove> evento.</span><span class="sxs-lookup"><span data-stu-id="a58d5-149">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnMouseMove](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     <span data-ttu-id="a58d5-150">Esta <xref:System.Windows.UIElement.OnMouseMove%2A> invalidación realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="a58d5-150">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="a58d5-151">Comprueba si el botón primario del mouse está presionado mientras este se mueve.</span><span class="sxs-lookup"><span data-stu-id="a58d5-151">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>

    - <span data-ttu-id="a58d5-152">Empaqueta los datos del círculo en un <xref:System.Windows.DataObject> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-152">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="a58d5-153">En este caso, el control de círculo empaqueta tres elementos de datos: una representación de cadena de su color de relleno, una representación doble de su altura y una copia de sí mismo.</span><span class="sxs-lookup"><span data-stu-id="a58d5-153">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

    - <span data-ttu-id="a58d5-154">Llama al <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> método estático para iniciar la operación de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="a58d5-154">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="a58d5-155">Pase los tres parámetros siguientes al <xref:System.Windows.DragDrop.DoDragDrop%2A> método:</span><span class="sxs-lookup"><span data-stu-id="a58d5-155">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>

        - <span data-ttu-id="a58d5-156">`dragSource`: una referencia a este control.</span><span class="sxs-lookup"><span data-stu-id="a58d5-156">`dragSource` – A reference to this control.</span></span>

        - <span data-ttu-id="a58d5-157">`data`: <xref:System.Windows.DataObject> Creado en el código anterior.</span><span class="sxs-lookup"><span data-stu-id="a58d5-157">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>

        - <span data-ttu-id="a58d5-158">`allowedEffects`: Las operaciones de arrastrar y colocar permitidas, que son <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-158">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="a58d5-159">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a58d5-159">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="a58d5-160">Haga clic en uno de los controles de círculo y arrástrelo sobre los paneles, el otro círculo y el <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-160">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="a58d5-161">Al arrastrar sobre <xref:System.Windows.Controls.TextBox> , el cursor cambia para indicar un movimiento.</span><span class="sxs-lookup"><span data-stu-id="a58d5-161">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>

5. <span data-ttu-id="a58d5-162">Mientras arrastra un círculo sobre el <xref:System.Windows.Controls.TextBox> **control** , presione la tecla Ctrl.</span><span class="sxs-lookup"><span data-stu-id="a58d5-162">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the **Ctrl** key.</span></span> <span data-ttu-id="a58d5-163">Observe que el cursor cambia para indicar una copia.</span><span class="sxs-lookup"><span data-stu-id="a58d5-163">Notice how the cursor changes to indicate a copy.</span></span>

6. <span data-ttu-id="a58d5-164">Arrastre y coloque un círculo en el <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-164">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="a58d5-165">La representación de cadena del color de relleno del círculo se anexa al <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-165">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>

     <span data-ttu-id="a58d5-166">![Representación de cadena del color de relleno del círculo](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="a58d5-166">![String representation of Circle's fill color](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>

<span data-ttu-id="a58d5-167">De forma predeterminada, el cursor cambiará durante una operación de arrastrar y colocar para indicar el efecto que tendrá la colocación de los datos.</span><span class="sxs-lookup"><span data-stu-id="a58d5-167">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="a58d5-168">Puede personalizar los comentarios asignados al usuario controlando el <xref:System.Windows.UIElement.GiveFeedback> evento y estableciendo un cursor diferente.</span><span class="sxs-lookup"><span data-stu-id="a58d5-168">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>

## <a name="give-feedback-to-the-user"></a><span data-ttu-id="a58d5-169">Enviar comentarios al usuario</span><span class="sxs-lookup"><span data-stu-id="a58d5-169">Give feedback to the user</span></span>

1. <span data-ttu-id="a58d5-170">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="a58d5-170">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="a58d5-171">Agregue la siguiente <xref:System.Windows.UIElement.OnGiveFeedback%2A> invalidación para proporcionar el control de clases para el <xref:System.Windows.UIElement.GiveFeedback> evento.</span><span class="sxs-lookup"><span data-stu-id="a58d5-171">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     <span data-ttu-id="a58d5-172">Esta <xref:System.Windows.UIElement.OnGiveFeedback%2A> invalidación realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="a58d5-172">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="a58d5-173">Comprueba los <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valores que se establecen en el controlador de eventos del destino de colocación <xref:System.Windows.UIElement.DragOver> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-173">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

    - <span data-ttu-id="a58d5-174">Establece un cursor personalizado basado en el <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valor.</span><span class="sxs-lookup"><span data-stu-id="a58d5-174">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="a58d5-175">El cursor está diseñado para proporcionar información visual al usuario sobre el efecto que tendrá la colocación de los datos.</span><span class="sxs-lookup"><span data-stu-id="a58d5-175">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>

3. <span data-ttu-id="a58d5-176">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a58d5-176">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="a58d5-177">Arrastre uno de los controles de círculo sobre los paneles, el otro círculo y <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-177">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="a58d5-178">Observe que los cursores son ahora los cursores personalizados que especificó en la <xref:System.Windows.UIElement.OnGiveFeedback%2A> invalidación.</span><span class="sxs-lookup"><span data-stu-id="a58d5-178">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>

     <span data-ttu-id="a58d5-179">![Arrastrar y colocar con cursores personalizados](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="a58d5-179">![Drag and drop with custom cursors](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>

5. <span data-ttu-id="a58d5-180">Seleccione el texto `green` de la <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-180">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

6. <span data-ttu-id="a58d5-181">Arrastre el texto `green` a un control de círculo.</span><span class="sxs-lookup"><span data-stu-id="a58d5-181">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="a58d5-182">Observe que los cursores predeterminados se muestran para indicar los efectos de la operación de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="a58d5-182">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="a58d5-183">El origen de arrastre siempre establece el cursor de retroacción.</span><span class="sxs-lookup"><span data-stu-id="a58d5-183">The feedback cursor is always set by the drag source.</span></span>

## <a name="implement-drop-target-events-in-the-user-control"></a><span data-ttu-id="a58d5-184">Implementar eventos de destino de colocación en el control de usuario</span><span class="sxs-lookup"><span data-stu-id="a58d5-184">Implement Drop Target Events in the User Control</span></span>
 <span data-ttu-id="a58d5-185">En esta sección, especificará que el control de usuario es un destino de colocación, invalidará los métodos que permiten que el control de usuario sea un destino de colocación y procesará los datos que se colocan en él.</span><span class="sxs-lookup"><span data-stu-id="a58d5-185">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="a58d5-186">Para permitir que el control de usuario sea un destino de colocación</span><span class="sxs-lookup"><span data-stu-id="a58d5-186">To enable the user control to be a drop target</span></span>

1. <span data-ttu-id="a58d5-187">Abra Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="a58d5-187">Open Circle.xaml.</span></span>

2. <span data-ttu-id="a58d5-188">En la etiqueta de apertura <xref:System.Windows.Controls.UserControl> , agregue la <xref:System.Windows.UIElement.AllowDrop%2A> propiedad y establézcala en `true` .</span><span class="sxs-lookup"><span data-stu-id="a58d5-188">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>

     [!code-xaml[DragDropWalkthrough#UCTagXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

<span data-ttu-id="a58d5-189"><xref:System.Windows.UIElement.OnDrop%2A>Se llama al método cuando la <xref:System.Windows.UIElement.AllowDrop%2A> propiedad se establece en `true` y los datos del origen de arrastre se colocan en el control de usuario del círculo.</span><span class="sxs-lookup"><span data-stu-id="a58d5-189">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="a58d5-190">En este método, procesará los datos que se han colocado y aplicará los datos al círculo.</span><span class="sxs-lookup"><span data-stu-id="a58d5-190">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>

### <a name="to-process-the-dropped-data"></a><span data-ttu-id="a58d5-191">Para procesar los datos colocados</span><span class="sxs-lookup"><span data-stu-id="a58d5-191">To process the dropped data</span></span>

1. <span data-ttu-id="a58d5-192">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="a58d5-192">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="a58d5-193">Agregue la siguiente <xref:System.Windows.UIElement.OnDrop%2A> invalidación para proporcionar el control de clases para el <xref:System.Windows.UIElement.Drop> evento.</span><span class="sxs-lookup"><span data-stu-id="a58d5-193">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     <span data-ttu-id="a58d5-194">Esta <xref:System.Windows.UIElement.OnDrop%2A> invalidación realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="a58d5-194">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="a58d5-195">Utiliza el <xref:System.Windows.DataObject.GetDataPresent%2A> método para comprobar si los datos arrastrados contienen un objeto de cadena.</span><span class="sxs-lookup"><span data-stu-id="a58d5-195">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>

    - <span data-ttu-id="a58d5-196">Utiliza el <xref:System.Windows.DataObject.GetData%2A> método para extraer los datos de cadena si están presentes.</span><span class="sxs-lookup"><span data-stu-id="a58d5-196">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>

    - <span data-ttu-id="a58d5-197">Utiliza un <xref:System.Windows.Media.BrushConverter> para intentar convertir la cadena en un <xref:System.Windows.Media.Brush> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-197">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="a58d5-198">Si la conversión se realiza correctamente, aplica el pincel al <xref:System.Windows.Shapes.Shape.Fill%2A> del <xref:System.Windows.Shapes.Ellipse> que proporciona la interfaz de usuario del control de círculo.</span><span class="sxs-lookup"><span data-stu-id="a58d5-198">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>

    - <span data-ttu-id="a58d5-199">Marca el <xref:System.Windows.UIElement.Drop> evento como controlado.</span><span class="sxs-lookup"><span data-stu-id="a58d5-199">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="a58d5-200">Debe marcar el evento de colocación como controlado para que los elementos que reciban este evento sepan que el control de usuario de círculo lo ha controlado.</span><span class="sxs-lookup"><span data-stu-id="a58d5-200">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>

3. <span data-ttu-id="a58d5-201">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a58d5-201">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="a58d5-202">Seleccione el texto `green` en el <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-202">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="a58d5-203">Arrastre el texto a un control de círculo y colóquelo.</span><span class="sxs-lookup"><span data-stu-id="a58d5-203">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="a58d5-204">El círculo cambia de azul a verde.</span><span class="sxs-lookup"><span data-stu-id="a58d5-204">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="a58d5-205">![Convertir una cadena en un pincel](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="a58d5-205">![Convert a string to a brush](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>

6. <span data-ttu-id="a58d5-206">Escriba el texto `green` en <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-206">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="a58d5-207">Seleccione el texto `gre` en el <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-207">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="a58d5-208">Arrástrelo a un control de círculo y colóquelo.</span><span class="sxs-lookup"><span data-stu-id="a58d5-208">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="a58d5-209">Observe que el cursor cambia para indicar que se permite la colocación, pero el color del círculo no cambia porque `gre` no es un color válido.</span><span class="sxs-lookup"><span data-stu-id="a58d5-209">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>

9. <span data-ttu-id="a58d5-210">Arrastre desde el control de círculo verde y coloque en el control de círculo azul.</span><span class="sxs-lookup"><span data-stu-id="a58d5-210">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="a58d5-211">El círculo cambia de azul a verde.</span><span class="sxs-lookup"><span data-stu-id="a58d5-211">The Circle changes from blue to green.</span></span> <span data-ttu-id="a58d5-212">Observe que el cursor que se muestra depende de si el <xref:System.Windows.Controls.TextBox> o el círculo es el origen de arrastre.</span><span class="sxs-lookup"><span data-stu-id="a58d5-212">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>

<span data-ttu-id="a58d5-213">La configuración de la <xref:System.Windows.UIElement.AllowDrop%2A> propiedad en `true` y el procesamiento de los datos colocados es todo lo necesario para permitir que un elemento sea un destino de colocación.</span><span class="sxs-lookup"><span data-stu-id="a58d5-213">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="a58d5-214">Sin embargo, para proporcionar una mejor experiencia de usuario, también debe controlar <xref:System.Windows.UIElement.DragEnter> los <xref:System.Windows.UIElement.DragLeave> eventos, y <xref:System.Windows.UIElement.DragOver> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-214">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="a58d5-215">En estos eventos, puede realizar comprobaciones y proporcionar repuesta adicional al usuario antes de que se coloquen los datos.</span><span class="sxs-lookup"><span data-stu-id="a58d5-215">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>

<span data-ttu-id="a58d5-216">Cuando los datos se arrastran sobre el control de usuario de círculo, el control debe notificarle al origen de arrastre si puede procesar los datos que se están arrastrando.</span><span class="sxs-lookup"><span data-stu-id="a58d5-216">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="a58d5-217">Si el control no sabe cómo procesar los datos, debe rechazar la operación de colocar.</span><span class="sxs-lookup"><span data-stu-id="a58d5-217">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="a58d5-218">Para ello, controlará el <xref:System.Windows.UIElement.DragOver> evento y establecerá la <xref:System.Windows.DragEventArgs.Effects%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="a58d5-218">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>

### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="a58d5-219">Para comprobar que se permite la colocación de datos</span><span class="sxs-lookup"><span data-stu-id="a58d5-219">To verify that the data drop is allowed</span></span>

1. <span data-ttu-id="a58d5-220">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="a58d5-220">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="a58d5-221">Agregue la siguiente <xref:System.Windows.UIElement.OnDragOver%2A> invalidación para proporcionar el control de clases para el <xref:System.Windows.UIElement.DragOver> evento.</span><span class="sxs-lookup"><span data-stu-id="a58d5-221">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     <span data-ttu-id="a58d5-222">Esta <xref:System.Windows.UIElement.OnDragOver%2A> invalidación realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="a58d5-222">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="a58d5-223">Establece la propiedad <xref:System.Windows.DragEventArgs.Effects%2A> como <xref:System.Windows.DragDropEffects.None>.</span><span class="sxs-lookup"><span data-stu-id="a58d5-223">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>

    - <span data-ttu-id="a58d5-224">Realiza las mismas comprobaciones que se realizan en el <xref:System.Windows.UIElement.OnDrop%2A> método para determinar si el control de usuario de círculo puede procesar los datos arrastrados.</span><span class="sxs-lookup"><span data-stu-id="a58d5-224">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>

    - <span data-ttu-id="a58d5-225">Si el control de usuario puede procesar los datos, establece la <xref:System.Windows.DragEventArgs.Effects%2A> propiedad en <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-225">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="a58d5-226">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a58d5-226">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="a58d5-227">Seleccione el texto `gre` en el <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-227">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="a58d5-228">Arrastre el texto a un control de círculo.</span><span class="sxs-lookup"><span data-stu-id="a58d5-228">Drag the text to a Circle control.</span></span> <span data-ttu-id="a58d5-229">Observe que ahora el cursor cambia para indicar que no se permite la colocación porque `gre` no es un color válido.</span><span class="sxs-lookup"><span data-stu-id="a58d5-229">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>

 <span data-ttu-id="a58d5-230">Puede mejorar la experiencia del usuario si aplica una vista previa de la operación de colocar.</span><span class="sxs-lookup"><span data-stu-id="a58d5-230">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="a58d5-231">Para el control de usuario de círculo, invalidará los <xref:System.Windows.UIElement.OnDragEnter%2A> <xref:System.Windows.UIElement.OnDragLeave%2A> métodos y.</span><span class="sxs-lookup"><span data-stu-id="a58d5-231">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="a58d5-232">Cuando los datos se arrastran sobre el control, el fondo actual <xref:System.Windows.Shapes.Shape.Fill%2A> se guarda en una variable de marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="a58d5-232">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="a58d5-233">A continuación, la cadena se convierte en un pincel y se aplica al <xref:System.Windows.Shapes.Ellipse> que proporciona la interfaz de usuario del círculo.</span><span class="sxs-lookup"><span data-stu-id="a58d5-233">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="a58d5-234">Si los datos se arrastran fuera del círculo sin quitarlos, el valor original <xref:System.Windows.Shapes.Shape.Fill%2A> se vuelve a aplicar al círculo.</span><span class="sxs-lookup"><span data-stu-id="a58d5-234">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="a58d5-235">Para obtener una vista previa de los efectos de la operación de arrastrar y colocar</span><span class="sxs-lookup"><span data-stu-id="a58d5-235">To preview the effects of the drag-and-drop operation</span></span>

1. <span data-ttu-id="a58d5-236">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="a58d5-236">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="a58d5-237">En la clase Circle, declare una <xref:System.Windows.Media.Brush> variable privada denominada `_previousFill` e inicialícela en `null` .</span><span class="sxs-lookup"><span data-stu-id="a58d5-237">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>

     [!code-csharp[DragDropWalkthrough#Brush](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3. <span data-ttu-id="a58d5-238">Agregue la siguiente <xref:System.Windows.UIElement.OnDragEnter%2A> invalidación para proporcionar el control de clases para el <xref:System.Windows.UIElement.DragEnter> evento.</span><span class="sxs-lookup"><span data-stu-id="a58d5-238">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     <span data-ttu-id="a58d5-239">Esta <xref:System.Windows.UIElement.OnDragEnter%2A> invalidación realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="a58d5-239">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="a58d5-240">Guarda la <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad de <xref:System.Windows.Shapes.Ellipse> en la `_previousFill` variable.</span><span class="sxs-lookup"><span data-stu-id="a58d5-240">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>

    - <span data-ttu-id="a58d5-241">Realiza las mismas comprobaciones que se realizan en el <xref:System.Windows.UIElement.OnDrop%2A> método para determinar si los datos se pueden convertir en <xref:System.Windows.Media.Brush> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-241">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="a58d5-242">Si los datos se convierten en un válido <xref:System.Windows.Media.Brush> , se aplica a la <xref:System.Windows.Shapes.Shape.Fill%2A> de <xref:System.Windows.Shapes.Ellipse> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-242">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>

4. <span data-ttu-id="a58d5-243">Agregue la siguiente <xref:System.Windows.UIElement.OnDragLeave%2A> invalidación para proporcionar el control de clases para el <xref:System.Windows.UIElement.DragLeave> evento.</span><span class="sxs-lookup"><span data-stu-id="a58d5-243">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     <span data-ttu-id="a58d5-244">Esta <xref:System.Windows.UIElement.OnDragLeave%2A> invalidación realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="a58d5-244">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="a58d5-245">Aplica el <xref:System.Windows.Media.Brush> guardado en la `_previousFill` variable al <xref:System.Windows.Shapes.Shape.Fill%2A> del <xref:System.Windows.Shapes.Ellipse> que proporciona la interfaz de usuario del control de usuario de círculo.</span><span class="sxs-lookup"><span data-stu-id="a58d5-245">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>

5. <span data-ttu-id="a58d5-246">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a58d5-246">Press **F5** to build and run the application.</span></span>

6. <span data-ttu-id="a58d5-247">Seleccione el texto `green` en el <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-247">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="a58d5-248">Arrastre el texto sobre un control de círculo sin colocarlo.</span><span class="sxs-lookup"><span data-stu-id="a58d5-248">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="a58d5-249">El círculo cambia de azul a verde.</span><span class="sxs-lookup"><span data-stu-id="a58d5-249">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="a58d5-250">![Obtener una vista previa de los efectos de una&#45;de arrastre y&#45;operación de colocar](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="a58d5-250">![Preview the effects of a drag&#45;and&#45;drop operation](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>

8. <span data-ttu-id="a58d5-251">Arrastre el texto fuera del control de círculo.</span><span class="sxs-lookup"><span data-stu-id="a58d5-251">Drag the text away from the Circle control.</span></span> <span data-ttu-id="a58d5-252">El círculo cambia de verde a azul.</span><span class="sxs-lookup"><span data-stu-id="a58d5-252">The Circle changes from green back to blue.</span></span>

## <a name="enable-a-panel-to-receive-dropped-data"></a><span data-ttu-id="a58d5-253">Habilitar un panel para recibir datos colocados</span><span class="sxs-lookup"><span data-stu-id="a58d5-253">Enable a Panel to Receive Dropped Data</span></span>

<span data-ttu-id="a58d5-254">En esta sección, habilitará los paneles que hospedan los controles de usuario de círculo para que actúen como destinos de colocación de los datos de círculo arrastrados.</span><span class="sxs-lookup"><span data-stu-id="a58d5-254">In this section, you enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="a58d5-255">Implementará código que le permite mover un círculo de un panel a otro, o realizar una copia de un control de círculo manteniendo presionada la tecla **Ctrl** mientras arrastra y coloca un círculo.</span><span class="sxs-lookup"><span data-stu-id="a58d5-255">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the **Ctrl** key while dragging and dropping a Circle.</span></span>

1. <span data-ttu-id="a58d5-256">Abra MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="a58d5-256">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="a58d5-257">Como se muestra en el código XAML siguiente, en cada uno de los <xref:System.Windows.Controls.StackPanel> controles, agregue Controladores para los <xref:System.Windows.UIElement.DragOver> <xref:System.Windows.UIElement.Drop> eventos y.</span><span class="sxs-lookup"><span data-stu-id="a58d5-257">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="a58d5-258">Asigne al controlador de eventos el nombre, <xref:System.Windows.UIElement.DragOver> `panel_DragOver` , y el nombre del <xref:System.Windows.UIElement.Drop> controlador de eventos, `panel_Drop` .</span><span class="sxs-lookup"><span data-stu-id="a58d5-258">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3. <span data-ttu-id="a58d5-259">Abra MainWindows.xaml.cs o MainWindow.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="a58d5-259">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>

4. <span data-ttu-id="a58d5-260">Agregue el código siguiente para el <xref:System.Windows.UIElement.DragOver> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="a58d5-260">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     <span data-ttu-id="a58d5-261">Este <xref:System.Windows.UIElement.DragOver> controlador de eventos realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="a58d5-261">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="a58d5-262">Comprueba que los datos arrastrados contienen los datos de "objeto" empaquetados <xref:System.Windows.DataObject> por el control de usuario de círculo y que se han pasado en la llamada a <xref:System.Windows.DragDrop.DoDragDrop%2A> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-262">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>

    - <span data-ttu-id="a58d5-263">Si los datos de "objeto" están presentes, comprueba si se ha presionado la tecla **Ctrl** .</span><span class="sxs-lookup"><span data-stu-id="a58d5-263">If the "Object" data is present, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="a58d5-264">Si se presiona la tecla **Ctrl** , establece la <xref:System.Windows.DragEventArgs.Effects%2A> propiedad en <xref:System.Windows.DragDropEffects.Copy> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-264">If the **Ctrl** key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="a58d5-265">En caso contrario, establezca la <xref:System.Windows.DragEventArgs.Effects%2A> propiedad en <xref:System.Windows.DragDropEffects.Move> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-265">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>

5. <span data-ttu-id="a58d5-266">Agregue el código siguiente para el <xref:System.Windows.UIElement.Drop> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="a58d5-266">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     <span data-ttu-id="a58d5-267">Este <xref:System.Windows.UIElement.Drop> controlador de eventos realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="a58d5-267">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="a58d5-268">Comprueba si el <xref:System.Windows.UIElement.Drop> evento ya se ha controlado.</span><span class="sxs-lookup"><span data-stu-id="a58d5-268">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="a58d5-269">Por ejemplo, si se coloca un círculo en otro círculo que controla el <xref:System.Windows.UIElement.Drop> evento, no se desea que el panel que contiene el círculo también lo controle.</span><span class="sxs-lookup"><span data-stu-id="a58d5-269">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>

    - <span data-ttu-id="a58d5-270">Si <xref:System.Windows.UIElement.Drop> no se controla el evento, comprueba si se ha presionado la tecla **Ctrl** .</span><span class="sxs-lookup"><span data-stu-id="a58d5-270">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="a58d5-271">Si se presiona la tecla **Ctrl** cuando <xref:System.Windows.UIElement.Drop> sucede, realiza una copia del control de círculo y la agrega a la <xref:System.Windows.Controls.Panel.Children%2A> colección de <xref:System.Windows.Controls.StackPanel> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-271">If the **Ctrl** key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>

    - <span data-ttu-id="a58d5-272">Si no se presiona la tecla **Ctrl** , mueve el círculo de la <xref:System.Windows.Controls.Panel.Children%2A> colección de su panel primario a la <xref:System.Windows.Controls.Panel.Children%2A> colección del panel en el que se colocó.</span><span class="sxs-lookup"><span data-stu-id="a58d5-272">If the **Ctrl** key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>

    - <span data-ttu-id="a58d5-273">Establece la <xref:System.Windows.DragEventArgs.Effects%2A> propiedad para notificar al <xref:System.Windows.DragDrop.DoDragDrop%2A> método si se realizó una operación de movimiento o copia.</span><span class="sxs-lookup"><span data-stu-id="a58d5-273">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>

6. <span data-ttu-id="a58d5-274">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a58d5-274">Press **F5** to build and run the application.</span></span>

7. <span data-ttu-id="a58d5-275">Seleccione el texto `green` de la <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="a58d5-275">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="a58d5-276">Arrastre el texto sobre un control de círculo y colóquelo.</span><span class="sxs-lookup"><span data-stu-id="a58d5-276">Drag the text over a Circle control and drop it.</span></span>

9. <span data-ttu-id="a58d5-277">Arrastre un control de círculo del panel izquierdo al panel derecho y colóquelo.</span><span class="sxs-lookup"><span data-stu-id="a58d5-277">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="a58d5-278">El círculo se quita de la <xref:System.Windows.Controls.Panel.Children%2A> colección del panel izquierdo y se agrega a la colección de elementos secundarios del panel derecho.</span><span class="sxs-lookup"><span data-stu-id="a58d5-278">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>

10. <span data-ttu-id="a58d5-279">Arrastre un control Circle desde el panel en el que se encuentra al otro panel y colóquelo mientras presiona la tecla **Ctrl** .</span><span class="sxs-lookup"><span data-stu-id="a58d5-279">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the **Ctrl** key.</span></span> <span data-ttu-id="a58d5-280">Se copia el círculo y la copia se agrega a la <xref:System.Windows.Controls.Panel.Children%2A> colección del panel receptor.</span><span class="sxs-lookup"><span data-stu-id="a58d5-280">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>

     <span data-ttu-id="a58d5-281">![Arrastrar un círculo mientras se presiona la tecla CTRL](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="a58d5-281">![Dragging a Circle while pressing the CTRL key](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>

## <a name="see-also"></a><span data-ttu-id="a58d5-282">Vea también</span><span class="sxs-lookup"><span data-stu-id="a58d5-282">See also</span></span>

- [<span data-ttu-id="a58d5-283">Información general sobre la función de arrastrar y colocar</span><span class="sxs-lookup"><span data-stu-id="a58d5-283">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
