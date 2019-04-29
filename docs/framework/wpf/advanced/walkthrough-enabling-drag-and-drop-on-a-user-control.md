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
ms.openlocfilehash: a628665ccfa0a423667344b1fe81f132d6691b12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778953"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="f04f3-102">Tutorial: Habilitar la técnica de arrastrar y colocar en un control de usuario</span><span class="sxs-lookup"><span data-stu-id="f04f3-102">Walkthrough: Enabling Drag and Drop on a User Control</span></span>

<span data-ttu-id="f04f3-103">En este tutorial se muestra cómo crear un control de usuario personalizado que pueda participar en la transferencia de datos de arrastrar y colocar en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f04f3-103">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>

<span data-ttu-id="f04f3-104">En este tutorial, creará un WPF personalizado <xref:System.Windows.Controls.UserControl> que representa una forma de círculo.</span><span class="sxs-lookup"><span data-stu-id="f04f3-104">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="f04f3-105">Implementará la funcionalidad del control para habilitar la transferencia de datos mediante la técnica de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="f04f3-105">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="f04f3-106">Por ejemplo, si arrastra de un control de círculo a otro, se copian los datos del color de relleno del círculo de origen al de destino.</span><span class="sxs-lookup"><span data-stu-id="f04f3-106">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="f04f3-107">Si arrastra de un control de círculo a un <xref:System.Windows.Controls.TextBox>, la representación de cadena del color de relleno se copia en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-107">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="f04f3-108">También creará una pequeña aplicación que contiene dos controles de panel y un <xref:System.Windows.Controls.TextBox> para probar la funcionalidad de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="f04f3-108">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="f04f3-109">Escribirá código para que los paneles puedan procesar los datos del círculo colocado, lo que le permitirá mover o copiar círculos de la colección secundaria de un panel a otro.</span><span class="sxs-lookup"><span data-stu-id="f04f3-109">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>

<span data-ttu-id="f04f3-110">En este tutorial se muestran las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f04f3-110">This walkthrough illustrates the following tasks:</span></span>

- <span data-ttu-id="f04f3-111">Crear un control de usuario personalizado.</span><span class="sxs-lookup"><span data-stu-id="f04f3-111">Create a custom user control.</span></span>

- <span data-ttu-id="f04f3-112">Permitir que el control de usuario sea un origen de arrastre.</span><span class="sxs-lookup"><span data-stu-id="f04f3-112">Enable the user control to be a drag source.</span></span>

- <span data-ttu-id="f04f3-113">Permitir que el control de usuario sea un destino de colocación.</span><span class="sxs-lookup"><span data-stu-id="f04f3-113">Enable the user control to be a drop target.</span></span>

- <span data-ttu-id="f04f3-114">Permitir que un panel reciba los datos que se colocan desde el control de usuario.</span><span class="sxs-lookup"><span data-stu-id="f04f3-114">Enable a panel to receive data dropped from the user control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f04f3-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f04f3-115">Prerequisites</span></span>

<span data-ttu-id="f04f3-116">Necesita Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="f04f3-116">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="f04f3-117">Crear el proyecto de aplicación</span><span class="sxs-lookup"><span data-stu-id="f04f3-117">Create the Application Project</span></span>
 <span data-ttu-id="f04f3-118">En esta sección, creará la infraestructura de aplicación, que incluye una página principal con dos paneles y un <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-118">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>

1. <span data-ttu-id="f04f3-119">Cree un proyecto de aplicación de WPF en Visual Basic o Visual C# denominado `DragDropExample`.</span><span class="sxs-lookup"><span data-stu-id="f04f3-119">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="f04f3-120">Para obtener más información, vea [Tutorial: Mi primera aplicación de escritorio de WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="f04f3-120">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

2. <span data-ttu-id="f04f3-121">Abra MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="f04f3-121">Open MainWindow.xaml.</span></span>

3. <span data-ttu-id="f04f3-122">Agregue el marcado siguiente entre la apertura y cierre <xref:System.Windows.Controls.Grid> etiquetas.</span><span class="sxs-lookup"><span data-stu-id="f04f3-122">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>

     <span data-ttu-id="f04f3-123">Este marcado crea la interfaz de usuario de la aplicación de prueba.</span><span class="sxs-lookup"><span data-stu-id="f04f3-123">This markup creates the user interface for the test application.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a><span data-ttu-id="f04f3-124">Agregar un nuevo Control de usuario al proyecto</span><span class="sxs-lookup"><span data-stu-id="f04f3-124">Add a New User Control to the Project</span></span>
 <span data-ttu-id="f04f3-125">En esta sección, agregará un nuevo control de usuario al proyecto.</span><span class="sxs-lookup"><span data-stu-id="f04f3-125">In this section, you will add a new user control to the project.</span></span>

1. <span data-ttu-id="f04f3-126">En el menú Proyecto, seleccione **Agregar control de usuario**.</span><span class="sxs-lookup"><span data-stu-id="f04f3-126">On the Project menu, select **Add User Control**.</span></span>

2. <span data-ttu-id="f04f3-127">En el **Agregar nuevo elemento** diálogo cuadro, cambie el nombre a `Circle.xaml`y haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="f04f3-127">In the **Add New Item** dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>

     <span data-ttu-id="f04f3-128">Circle.xaml y su código subyacente se agregan al proyecto.</span><span class="sxs-lookup"><span data-stu-id="f04f3-128">Circle.xaml and its code-behind is added to the project.</span></span>

3. <span data-ttu-id="f04f3-129">Abra Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="f04f3-129">Open Circle.xaml.</span></span>

     <span data-ttu-id="f04f3-130">Este archivo contendrá los elementos de la interfaz de usuario del control de usuario.</span><span class="sxs-lookup"><span data-stu-id="f04f3-130">This file will contain the user interface elements of the user control.</span></span>

4. <span data-ttu-id="f04f3-131">Agregue el marcado siguiente a la raíz <xref:System.Windows.Controls.Grid> para crear un control de usuario simple que tiene un círculo azul como interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="f04f3-131">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>

     [!code-xaml[DragDropWalkthrough#EllipseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5. <span data-ttu-id="f04f3-132">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f04f3-132">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

6. <span data-ttu-id="f04f3-133">En C#, agregue el código siguiente después del constructor predeterminado para crear un constructor de copias.</span><span class="sxs-lookup"><span data-stu-id="f04f3-133">In C#, add the following code after the default constructor to create a copy constructor.</span></span> <span data-ttu-id="f04f3-134">En Visual Basic, agregue el código siguiente para crear un constructor predeterminado y un constructor de copias.</span><span class="sxs-lookup"><span data-stu-id="f04f3-134">In Visual Basic, add the following code to create both a default constructor and a copy constructor.</span></span>

     <span data-ttu-id="f04f3-135">Para permitir que se copie el control de usuario, puede agregar un método de constructor de copias en el archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="f04f3-135">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="f04f3-136">En el control de usuario de círculo simplificado, solo copiará el relleno y el tamaño del control de usuario.</span><span class="sxs-lookup"><span data-stu-id="f04f3-136">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>

     [!code-csharp[DragDropWalkthrough#CopyCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a><span data-ttu-id="f04f3-137">Agregar el control de usuario a la ventana principal</span><span class="sxs-lookup"><span data-stu-id="f04f3-137">Add the user control to the main window</span></span>

1. <span data-ttu-id="f04f3-138">Abra MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="f04f3-138">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="f04f3-139">Agregue el siguiente XAML a la apertura <xref:System.Windows.Window> etiqueta para crear una referencia de espacio de nombres XML a la aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="f04f3-139">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>

    ```
    xmlns:local="clr-namespace:DragDropExample"
    ```

3. <span data-ttu-id="f04f3-140">En la primera <xref:System.Windows.Controls.StackPanel>, agregue el siguiente XAML para crear dos instancias del control de usuario de círculo en el primer panel.</span><span class="sxs-lookup"><span data-stu-id="f04f3-140">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>

     [!code-xaml[DragDropWalkthrough#CirclesXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     <span data-ttu-id="f04f3-141">El código XAML completo del panel tendrá el aspecto siguiente.</span><span class="sxs-lookup"><span data-stu-id="f04f3-141">The full XAML for the panel looks like the following.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a><span data-ttu-id="f04f3-142">Implementar eventos del origen de arrastre en el Control de usuario</span><span class="sxs-lookup"><span data-stu-id="f04f3-142">Implement Drag Source Events in the User Control</span></span>
 <span data-ttu-id="f04f3-143">En esta sección, invalidará la <xref:System.Windows.UIElement.OnMouseMove%2A> método e inicie la operación de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="f04f3-143">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>

 <span data-ttu-id="f04f3-144">Si se inicia un arrastre (se presiona un botón del mouse y se mueve el mouse), empaquetará los datos que se transfieran a una <xref:System.Windows.DataObject>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-144">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="f04f3-145">En este caso, el control de círculo empaquetará tres elementos de datos: una representación de cadena de su color de relleno, una representación doble de su altura y una copia de sí mismo.</span><span class="sxs-lookup"><span data-stu-id="f04f3-145">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="f04f3-146">Para iniciar una operación de arrastrar y colocar</span><span class="sxs-lookup"><span data-stu-id="f04f3-146">To initiate a drag-and-drop operation</span></span>

1. <span data-ttu-id="f04f3-147">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f04f3-147">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="f04f3-148">Agregue el siguiente <xref:System.Windows.UIElement.OnMouseMove%2A> invalidación para proporcionar control de clases para el <xref:System.Windows.UIElement.MouseMove> eventos.</span><span class="sxs-lookup"><span data-stu-id="f04f3-148">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnMouseMove](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     <span data-ttu-id="f04f3-149">Esto <xref:System.Windows.UIElement.OnMouseMove%2A> invalidación realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f04f3-149">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="f04f3-150">Comprueba si el botón primario del mouse está presionado mientras este se mueve.</span><span class="sxs-lookup"><span data-stu-id="f04f3-150">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>

    - <span data-ttu-id="f04f3-151">Empaqueta los datos de círculo en un <xref:System.Windows.DataObject>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-151">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="f04f3-152">En este caso, el control de círculo empaqueta tres elementos de datos: una representación de cadena de su color de relleno, una representación doble de su altura y una copia de sí mismo.</span><span class="sxs-lookup"><span data-stu-id="f04f3-152">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

    - <span data-ttu-id="f04f3-153">Llama a estático <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> método para iniciar la operación de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="f04f3-153">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="f04f3-154">Pasar los tres parámetros siguientes para el <xref:System.Windows.DragDrop.DoDragDrop%2A> método:</span><span class="sxs-lookup"><span data-stu-id="f04f3-154">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>

        - <span data-ttu-id="f04f3-155">`dragSource`: una referencia a este control.</span><span class="sxs-lookup"><span data-stu-id="f04f3-155">`dragSource` – A reference to this control.</span></span>

        - <span data-ttu-id="f04f3-156">`data` – La <xref:System.Windows.DataObject> creado en el código anterior.</span><span class="sxs-lookup"><span data-stu-id="f04f3-156">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>

        - <span data-ttu-id="f04f3-157">`allowedEffects` : Las operaciones de arrastrar y colocar permitidas, que son <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-157">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="f04f3-158">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f04f3-158">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="f04f3-159">Haga clic en uno de los controles de círculo y arrástrelo sobre los paneles, el otro círculo y el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-159">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="f04f3-160">Al arrastrar sobre el <xref:System.Windows.Controls.TextBox>, el cursor cambia para indicar un movimiento.</span><span class="sxs-lookup"><span data-stu-id="f04f3-160">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>

5. <span data-ttu-id="f04f3-161">Al arrastrar un círculo sobre la <xref:System.Windows.Controls.TextBox>, presione el **Ctrl** clave.</span><span class="sxs-lookup"><span data-stu-id="f04f3-161">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the **Ctrl** key.</span></span> <span data-ttu-id="f04f3-162">Observe que el cursor cambia para indicar una copia.</span><span class="sxs-lookup"><span data-stu-id="f04f3-162">Notice how the cursor changes to indicate a copy.</span></span>

6. <span data-ttu-id="f04f3-163">Arrastre y coloque un círculo en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-163">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="f04f3-164">La representación de cadena del color de relleno del círculo se anexa a la <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-164">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>

     <span data-ttu-id="f04f3-165">![Representación de cadena del color de relleno del círculo](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="f04f3-165">![String representation of Circle's fill color](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>

<span data-ttu-id="f04f3-166">De forma predeterminada, el cursor cambiará durante una operación de arrastrar y colocar para indicar el efecto que tendrá la colocación de los datos.</span><span class="sxs-lookup"><span data-stu-id="f04f3-166">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="f04f3-167">Puede personalizar la respuesta al usuario controlando el <xref:System.Windows.UIElement.GiveFeedback> eventos y establecer un cursor diferente.</span><span class="sxs-lookup"><span data-stu-id="f04f3-167">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>

## <a name="give-feedback-to-the-user"></a><span data-ttu-id="f04f3-168">Proporcionar comentarios al usuario</span><span class="sxs-lookup"><span data-stu-id="f04f3-168">Give feedback to the user</span></span>

1. <span data-ttu-id="f04f3-169">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f04f3-169">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="f04f3-170">Agregue el siguiente <xref:System.Windows.UIElement.OnGiveFeedback%2A> invalidación para proporcionar control de clases para el <xref:System.Windows.UIElement.GiveFeedback> eventos.</span><span class="sxs-lookup"><span data-stu-id="f04f3-170">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     <span data-ttu-id="f04f3-171">Esto <xref:System.Windows.UIElement.OnGiveFeedback%2A> invalidación realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f04f3-171">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="f04f3-172">Comprueba la <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valores que se establecen en el destino de colocación <xref:System.Windows.UIElement.DragOver> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="f04f3-172">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

    - <span data-ttu-id="f04f3-173">Establece un cursor personalizado basado en la <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valor.</span><span class="sxs-lookup"><span data-stu-id="f04f3-173">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="f04f3-174">El cursor está diseñado para proporcionar información visual al usuario sobre el efecto que tendrá la colocación de los datos.</span><span class="sxs-lookup"><span data-stu-id="f04f3-174">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>

3. <span data-ttu-id="f04f3-175">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f04f3-175">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="f04f3-176">Arrastre uno del círculo se controla a través de los paneles, el otro círculo, y el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-176">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="f04f3-177">Tenga en cuenta que los cursores son ahora los cursores personalizados que especificó en el <xref:System.Windows.UIElement.OnGiveFeedback%2A> invalidar.</span><span class="sxs-lookup"><span data-stu-id="f04f3-177">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>

     <span data-ttu-id="f04f3-178">![Arrastrar y colocar con cursores personalizados](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="f04f3-178">![Drag and drop with custom cursors](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>

5. <span data-ttu-id="f04f3-179">Seleccione el texto `green` desde el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-179">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

6. <span data-ttu-id="f04f3-180">Arrastre el texto `green` a un control de círculo.</span><span class="sxs-lookup"><span data-stu-id="f04f3-180">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="f04f3-181">Observe que los cursores predeterminados se muestran para indicar los efectos de la operación de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="f04f3-181">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="f04f3-182">El origen de arrastre siempre establece el cursor de retroacción.</span><span class="sxs-lookup"><span data-stu-id="f04f3-182">The feedback cursor is always set by the drag source.</span></span>

## <a name="implement-drop-target-events-in-the-user-control"></a><span data-ttu-id="f04f3-183">Implementar eventos de destino de colocación en el Control de usuario</span><span class="sxs-lookup"><span data-stu-id="f04f3-183">Implement Drop Target Events in the User Control</span></span>
 <span data-ttu-id="f04f3-184">En esta sección, especificará que el control de usuario es un destino de colocación, invalidará los métodos que permiten que el control de usuario sea un destino de colocación y procesará los datos que se colocan en él.</span><span class="sxs-lookup"><span data-stu-id="f04f3-184">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="f04f3-185">Para permitir que el control de usuario sea un destino de colocación</span><span class="sxs-lookup"><span data-stu-id="f04f3-185">To enable the user control to be a drop target</span></span>

1. <span data-ttu-id="f04f3-186">Abra Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="f04f3-186">Open Circle.xaml.</span></span>

2. <span data-ttu-id="f04f3-187">En la apertura <xref:System.Windows.Controls.UserControl> etiqueta, agregue el <xref:System.Windows.UIElement.AllowDrop%2A> propiedad y establecerla en `true`.</span><span class="sxs-lookup"><span data-stu-id="f04f3-187">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>

     [!code-xaml[DragDropWalkthrough#UCTagXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

<span data-ttu-id="f04f3-188">El <xref:System.Windows.UIElement.OnDrop%2A> método se llama cuando el <xref:System.Windows.UIElement.AllowDrop%2A> propiedad está establecida en `true` y se colocan los datos del origen de arrastre en el control de usuario de círculo.</span><span class="sxs-lookup"><span data-stu-id="f04f3-188">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="f04f3-189">En este método, procesará los datos que se han colocado y aplicará los datos al círculo.</span><span class="sxs-lookup"><span data-stu-id="f04f3-189">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>

### <a name="to-process-the-dropped-data"></a><span data-ttu-id="f04f3-190">Para procesar los datos colocados</span><span class="sxs-lookup"><span data-stu-id="f04f3-190">To process the dropped data</span></span>

1. <span data-ttu-id="f04f3-191">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f04f3-191">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="f04f3-192">Agregue el siguiente <xref:System.Windows.UIElement.OnDrop%2A> invalidación para proporcionar control de clases para el <xref:System.Windows.UIElement.Drop> eventos.</span><span class="sxs-lookup"><span data-stu-id="f04f3-192">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     <span data-ttu-id="f04f3-193">Esto <xref:System.Windows.UIElement.OnDrop%2A> invalidación realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f04f3-193">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="f04f3-194">Usa el <xref:System.Windows.DataObject.GetDataPresent%2A> método para comprobar si los datos arrastrados contienen un objeto de cadena.</span><span class="sxs-lookup"><span data-stu-id="f04f3-194">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>

    - <span data-ttu-id="f04f3-195">Usa el <xref:System.Windows.DataObject.GetData%2A> método para extraer los datos de cadena, si está presente.</span><span class="sxs-lookup"><span data-stu-id="f04f3-195">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>

    - <span data-ttu-id="f04f3-196">Usa un <xref:System.Windows.Media.BrushConverter> para intentar convertir la cadena en un <xref:System.Windows.Media.Brush>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-196">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="f04f3-197">Si la conversión se realiza correctamente, se aplica el pincel para el <xref:System.Windows.Shapes.Shape.Fill%2A> de la <xref:System.Windows.Shapes.Ellipse> que proporciona la interfaz de usuario del control de círculo.</span><span class="sxs-lookup"><span data-stu-id="f04f3-197">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>

    - <span data-ttu-id="f04f3-198">Las marcas de la <xref:System.Windows.UIElement.Drop> evento como controlado.</span><span class="sxs-lookup"><span data-stu-id="f04f3-198">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="f04f3-199">Debe marcar el evento de colocación como controlado para que los elementos que reciban este evento sepan que el control de usuario de círculo lo ha controlado.</span><span class="sxs-lookup"><span data-stu-id="f04f3-199">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>

3. <span data-ttu-id="f04f3-200">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f04f3-200">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="f04f3-201">Seleccione el texto `green` en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-201">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="f04f3-202">Arrastre el texto a un control de círculo y colóquelo.</span><span class="sxs-lookup"><span data-stu-id="f04f3-202">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="f04f3-203">El círculo cambia de azul a verde.</span><span class="sxs-lookup"><span data-stu-id="f04f3-203">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="f04f3-204">![Convertir una cadena en un pincel](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="f04f3-204">![Convert a string to a brush](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>

6. <span data-ttu-id="f04f3-205">Escriba el texto `green` en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-205">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="f04f3-206">Seleccione el texto `gre` en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-206">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="f04f3-207">Arrástrelo a un control de círculo y colóquelo.</span><span class="sxs-lookup"><span data-stu-id="f04f3-207">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="f04f3-208">Observe que el cursor cambia para indicar que se permite la colocación, pero el color del círculo no cambia porque `gre` no es un color válido.</span><span class="sxs-lookup"><span data-stu-id="f04f3-208">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>

9. <span data-ttu-id="f04f3-209">Arrastre desde el control de círculo verde y coloque en el control de círculo azul.</span><span class="sxs-lookup"><span data-stu-id="f04f3-209">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="f04f3-210">El círculo cambia de azul a verde.</span><span class="sxs-lookup"><span data-stu-id="f04f3-210">The Circle changes from blue to green.</span></span> <span data-ttu-id="f04f3-211">Tenga en cuenta que el cursor que se muestra depende de si el <xref:System.Windows.Controls.TextBox> o el círculo es el origen de arrastre.</span><span class="sxs-lookup"><span data-stu-id="f04f3-211">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>

<span data-ttu-id="f04f3-212">Establecer el <xref:System.Windows.UIElement.AllowDrop%2A> propiedad `true` y procesar los datos colocados es todo lo que es necesario para habilitar un elemento para que sea un destino de colocación.</span><span class="sxs-lookup"><span data-stu-id="f04f3-212">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="f04f3-213">Sin embargo, para proporcionar una mejor experiencia de usuario, también debe controlar la <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, y <xref:System.Windows.UIElement.DragOver> eventos.</span><span class="sxs-lookup"><span data-stu-id="f04f3-213">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="f04f3-214">En estos eventos, puede realizar comprobaciones y proporcionar repuesta adicional al usuario antes de que se coloquen los datos.</span><span class="sxs-lookup"><span data-stu-id="f04f3-214">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>

<span data-ttu-id="f04f3-215">Cuando los datos se arrastran sobre el control de usuario de círculo, el control debe notificarle al origen de arrastre si puede procesar los datos que se están arrastrando.</span><span class="sxs-lookup"><span data-stu-id="f04f3-215">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="f04f3-216">Si el control no sabe cómo procesar los datos, debe rechazar la operación de colocar.</span><span class="sxs-lookup"><span data-stu-id="f04f3-216">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="f04f3-217">Para ello, controlará el <xref:System.Windows.UIElement.DragOver> evento y establecer el <xref:System.Windows.DragEventArgs.Effects%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f04f3-217">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>

### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="f04f3-218">Para comprobar que se permite la colocación de datos</span><span class="sxs-lookup"><span data-stu-id="f04f3-218">To verify that the data drop is allowed</span></span>

1. <span data-ttu-id="f04f3-219">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f04f3-219">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="f04f3-220">Agregue el siguiente <xref:System.Windows.UIElement.OnDragOver%2A> invalidación para proporcionar control de clases para el <xref:System.Windows.UIElement.DragOver> eventos.</span><span class="sxs-lookup"><span data-stu-id="f04f3-220">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     <span data-ttu-id="f04f3-221">Esto <xref:System.Windows.UIElement.OnDragOver%2A> invalidación realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f04f3-221">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="f04f3-222">Establece la propiedad <xref:System.Windows.DragEventArgs.Effects%2A> como <xref:System.Windows.DragDropEffects.None>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-222">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>

    - <span data-ttu-id="f04f3-223">Realiza las mismas comprobaciones que se realizan en el <xref:System.Windows.UIElement.OnDrop%2A> método para determinar si el control de usuario de círculo puede procesar los datos arrastrados.</span><span class="sxs-lookup"><span data-stu-id="f04f3-223">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>

    - <span data-ttu-id="f04f3-224">Si el control de usuario puede procesar los datos, Establece la <xref:System.Windows.DragEventArgs.Effects%2A> propiedad <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-224">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="f04f3-225">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f04f3-225">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="f04f3-226">Seleccione el texto `gre` en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-226">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="f04f3-227">Arrastre el texto a un control de círculo.</span><span class="sxs-lookup"><span data-stu-id="f04f3-227">Drag the text to a Circle control.</span></span> <span data-ttu-id="f04f3-228">Observe que ahora el cursor cambia para indicar que no se permite la colocación porque `gre` no es un color válido.</span><span class="sxs-lookup"><span data-stu-id="f04f3-228">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>

 <span data-ttu-id="f04f3-229">Puede mejorar la experiencia del usuario si aplica una vista previa de la operación de colocar.</span><span class="sxs-lookup"><span data-stu-id="f04f3-229">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="f04f3-230">Para el control de usuario de círculo, invalidará el <xref:System.Windows.UIElement.OnDragEnter%2A> y <xref:System.Windows.UIElement.OnDragLeave%2A> métodos.</span><span class="sxs-lookup"><span data-stu-id="f04f3-230">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="f04f3-231">Cuando se arrastran los datos sobre el control, el fondo actual <xref:System.Windows.Shapes.Shape.Fill%2A> se guarda en una variable de marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="f04f3-231">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="f04f3-232">La cadena se convierte en un pincel, a continuación y se aplica a la <xref:System.Windows.Shapes.Ellipse> que proporciona el círculo de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="f04f3-232">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="f04f3-233">Si los datos se arrastran fuera del círculo sin colocarse, el original <xref:System.Windows.Shapes.Shape.Fill%2A> valor se vuelve a aplicar al círculo.</span><span class="sxs-lookup"><span data-stu-id="f04f3-233">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="f04f3-234">Para obtener una vista previa de los efectos de la operación de arrastrar y colocar</span><span class="sxs-lookup"><span data-stu-id="f04f3-234">To preview the effects of the drag-and-drop operation</span></span>

1. <span data-ttu-id="f04f3-235">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f04f3-235">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="f04f3-236">En la clase Circle, declare una privada <xref:System.Windows.Media.Brush> variable denominada `_previousFill` e inicialícelo como `null`.</span><span class="sxs-lookup"><span data-stu-id="f04f3-236">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>

     [!code-csharp[DragDropWalkthrough#Brush](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3. <span data-ttu-id="f04f3-237">Agregue el siguiente <xref:System.Windows.UIElement.OnDragEnter%2A> invalidación para proporcionar control de clases para el <xref:System.Windows.UIElement.DragEnter> eventos.</span><span class="sxs-lookup"><span data-stu-id="f04f3-237">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     <span data-ttu-id="f04f3-238">Esto <xref:System.Windows.UIElement.OnDragEnter%2A> invalidación realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f04f3-238">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="f04f3-239">Guarda el <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad de la <xref:System.Windows.Shapes.Ellipse> en el `_previousFill` variable.</span><span class="sxs-lookup"><span data-stu-id="f04f3-239">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>

    - <span data-ttu-id="f04f3-240">Realiza las mismas comprobaciones que se realizan en el <xref:System.Windows.UIElement.OnDrop%2A> método para determinar si los datos pueden convertirse en un <xref:System.Windows.Media.Brush>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-240">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="f04f3-241">Si los datos se convierten en válido <xref:System.Windows.Media.Brush>, se aplica a la <xref:System.Windows.Shapes.Shape.Fill%2A> de la <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-241">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>

4. <span data-ttu-id="f04f3-242">Agregue el siguiente <xref:System.Windows.UIElement.OnDragLeave%2A> invalidación para proporcionar control de clases para el <xref:System.Windows.UIElement.DragLeave> eventos.</span><span class="sxs-lookup"><span data-stu-id="f04f3-242">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     <span data-ttu-id="f04f3-243">Esto <xref:System.Windows.UIElement.OnDragLeave%2A> invalidación realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f04f3-243">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="f04f3-244">Se aplica el <xref:System.Windows.Media.Brush> guardado en el `_previousFill` variable a la <xref:System.Windows.Shapes.Shape.Fill%2A> de la <xref:System.Windows.Shapes.Ellipse> que proporciona la interfaz de usuario del control de usuario de círculo.</span><span class="sxs-lookup"><span data-stu-id="f04f3-244">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>

5. <span data-ttu-id="f04f3-245">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f04f3-245">Press **F5** to build and run the application.</span></span>

6. <span data-ttu-id="f04f3-246">Seleccione el texto `green` en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-246">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="f04f3-247">Arrastre el texto sobre un control de círculo sin colocarlo.</span><span class="sxs-lookup"><span data-stu-id="f04f3-247">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="f04f3-248">El círculo cambia de azul a verde.</span><span class="sxs-lookup"><span data-stu-id="f04f3-248">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="f04f3-249">![Vista previa de los efectos de una operación de arrastrar y colocar](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="f04f3-249">![Preview the effects of a drag&#45;and&#45;drop operation](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>

8. <span data-ttu-id="f04f3-250">Arrastre el texto fuera del control de círculo.</span><span class="sxs-lookup"><span data-stu-id="f04f3-250">Drag the text away from the Circle control.</span></span> <span data-ttu-id="f04f3-251">El círculo cambia de verde a azul.</span><span class="sxs-lookup"><span data-stu-id="f04f3-251">The Circle changes from green back to blue.</span></span>

## <a name="enable-a-panel-to-receive-dropped-data"></a><span data-ttu-id="f04f3-252">Permitir que un Panel recibir datos colocados</span><span class="sxs-lookup"><span data-stu-id="f04f3-252">Enable a Panel to Receive Dropped Data</span></span>

<span data-ttu-id="f04f3-253">En esta sección, habilitará los paneles que hospedan los controles de usuario de círculo para que actúe como destinos de colocación de datos de círculo arrastrados.</span><span class="sxs-lookup"><span data-stu-id="f04f3-253">In this section, you enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="f04f3-254">Implementará código que le permite mover un círculo de un panel a otro, o para realizar una copia de un control de círculo manteniendo presionada la **Ctrl** clave mientras arrastra y coloca un círculo.</span><span class="sxs-lookup"><span data-stu-id="f04f3-254">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the **Ctrl** key while dragging and dropping a Circle.</span></span>

1. <span data-ttu-id="f04f3-255">Abra MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="f04f3-255">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="f04f3-256">Como se muestra en el siguiente XAML, en cada uno de los <xref:System.Windows.Controls.StackPanel> controles, agregue controladores para la <xref:System.Windows.UIElement.DragOver> y <xref:System.Windows.UIElement.Drop> eventos.</span><span class="sxs-lookup"><span data-stu-id="f04f3-256">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="f04f3-257">Nombre de la <xref:System.Windows.UIElement.DragOver> controlador de eventos, `panel_DragOver`y el nombre del <xref:System.Windows.UIElement.Drop> controlador de eventos, `panel_Drop`.</span><span class="sxs-lookup"><span data-stu-id="f04f3-257">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3. <span data-ttu-id="f04f3-258">Abra MainWindows.xaml.cs o MainWindow.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="f04f3-258">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>

4. <span data-ttu-id="f04f3-259">Agregue el siguiente código para el <xref:System.Windows.UIElement.DragOver> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="f04f3-259">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     <span data-ttu-id="f04f3-260">Esto <xref:System.Windows.UIElement.DragOver> controlador de eventos realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="f04f3-260">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="f04f3-261">Comprueba que los datos arrastrados contienen los datos de "Objeto" que se ha empaquetado en la <xref:System.Windows.DataObject> por el control de usuario de círculo y se pasa en la llamada a <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-261">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>

    - <span data-ttu-id="f04f3-262">Si los datos "Object" están presentes, comprueba si el **Ctrl** tecla está presionada.</span><span class="sxs-lookup"><span data-stu-id="f04f3-262">If the "Object" data is present, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="f04f3-263">Si el **Ctrl** presiona la tecla, Establece el <xref:System.Windows.DragEventArgs.Effects%2A> propiedad a <xref:System.Windows.DragDropEffects.Copy>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-263">If the **Ctrl** key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="f04f3-264">En caso contrario, establezca el <xref:System.Windows.DragEventArgs.Effects%2A> propiedad <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-264">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>

5. <span data-ttu-id="f04f3-265">Agregue el siguiente código para el <xref:System.Windows.UIElement.Drop> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="f04f3-265">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     <span data-ttu-id="f04f3-266">Esto <xref:System.Windows.UIElement.Drop> controlador de eventos realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="f04f3-266">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="f04f3-267">Comprueba si el <xref:System.Windows.UIElement.Drop> ya se ha controlado el evento.</span><span class="sxs-lookup"><span data-stu-id="f04f3-267">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="f04f3-268">Por ejemplo, si coloca un círculo en otro círculo que controla la <xref:System.Windows.UIElement.Drop> eventos, no desea que el panel que contiene el círculo también lo controle.</span><span class="sxs-lookup"><span data-stu-id="f04f3-268">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>

    - <span data-ttu-id="f04f3-269">Si el <xref:System.Windows.UIElement.Drop> eventos no se controla, comprueba si el **Ctrl** tecla está presionada.</span><span class="sxs-lookup"><span data-stu-id="f04f3-269">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="f04f3-270">Si el **Ctrl** se presiona la tecla cuando el <xref:System.Windows.UIElement.Drop> sucede, hace una copia del círculo, controla y agréguelo a la <xref:System.Windows.Controls.Panel.Children%2A> colección de la <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-270">If the **Ctrl** key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>

    - <span data-ttu-id="f04f3-271">Si el **Ctrl** no se presiona la tecla, se mueve el círculo de la <xref:System.Windows.Controls.Panel.Children%2A> colección de su panel primario a la <xref:System.Windows.Controls.Panel.Children%2A> colección del panel que se ha colocado.</span><span class="sxs-lookup"><span data-stu-id="f04f3-271">If the **Ctrl** key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>

    - <span data-ttu-id="f04f3-272">Establece el <xref:System.Windows.DragEventArgs.Effects%2A> propiedad para notificar a la <xref:System.Windows.DragDrop.DoDragDrop%2A> método si se realizó una operación de mover o copiar.</span><span class="sxs-lookup"><span data-stu-id="f04f3-272">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>

6. <span data-ttu-id="f04f3-273">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f04f3-273">Press **F5** to build and run the application.</span></span>

7. <span data-ttu-id="f04f3-274">Seleccione el texto `green` desde el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="f04f3-274">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="f04f3-275">Arrastre el texto sobre un control de círculo y colóquelo.</span><span class="sxs-lookup"><span data-stu-id="f04f3-275">Drag the text over a Circle control and drop it.</span></span>

9. <span data-ttu-id="f04f3-276">Arrastre un control de círculo del panel izquierdo al panel derecho y colóquelo.</span><span class="sxs-lookup"><span data-stu-id="f04f3-276">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="f04f3-277">El círculo se quita de la <xref:System.Windows.Controls.Panel.Children%2A> colección del panel izquierdo y se agrega a la colección de elementos secundarios del panel derecho.</span><span class="sxs-lookup"><span data-stu-id="f04f3-277">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>

10. <span data-ttu-id="f04f3-278">Arrastre un control de círculo del panel se encuentra en el panel de otros y colóquelo mientras presiona la **Ctrl** clave.</span><span class="sxs-lookup"><span data-stu-id="f04f3-278">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the **Ctrl** key.</span></span> <span data-ttu-id="f04f3-279">El círculo se copia y la copia se agrega a la <xref:System.Windows.Controls.Panel.Children%2A> colección del panel receptor.</span><span class="sxs-lookup"><span data-stu-id="f04f3-279">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>

     <span data-ttu-id="f04f3-280">![Arrastrar un círculo mientras se presiona la tecla Ctrl](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="f04f3-280">![Dragging a Circle while pressing the CTRL key](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>

## <a name="see-also"></a><span data-ttu-id="f04f3-281">Vea también</span><span class="sxs-lookup"><span data-stu-id="f04f3-281">See also</span></span>

- [<span data-ttu-id="f04f3-282">Información general sobre la función de arrastrar y colocar</span><span class="sxs-lookup"><span data-stu-id="f04f3-282">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)