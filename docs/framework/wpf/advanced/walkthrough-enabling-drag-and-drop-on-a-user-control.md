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
ms.openlocfilehash: 172e49c2c255db4d24d2180f919b1305326b5e82
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991810"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="d8d84-102">Tutorial: Habilitar la técnica de arrastrar y colocar en un control de usuario</span><span class="sxs-lookup"><span data-stu-id="d8d84-102">Walkthrough: Enabling Drag and Drop on a User Control</span></span>

<span data-ttu-id="d8d84-103">En este tutorial se muestra cómo crear un control de usuario personalizado que pueda participar en la transferencia de datos de arrastrar y colocar en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8d84-103">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>

<span data-ttu-id="d8d84-104">En este tutorial, creará un WPF <xref:System.Windows.Controls.UserControl> personalizado que representa una forma circular.</span><span class="sxs-lookup"><span data-stu-id="d8d84-104">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="d8d84-105">Implementará la funcionalidad del control para habilitar la transferencia de datos mediante la técnica de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="d8d84-105">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="d8d84-106">Por ejemplo, si arrastra de un control de círculo a otro, se copian los datos del color de relleno del círculo de origen al de destino.</span><span class="sxs-lookup"><span data-stu-id="d8d84-106">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="d8d84-107">Si arrastra de un control de círculo a un <xref:System.Windows.Controls.TextBox>, la representación de cadena del color de relleno se copia <xref:System.Windows.Controls.TextBox>en.</span><span class="sxs-lookup"><span data-stu-id="d8d84-107">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="d8d84-108">También creará una pequeña aplicación que contiene dos controles de panel y un <xref:System.Windows.Controls.TextBox> para probar la funcionalidad de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="d8d84-108">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="d8d84-109">Escribirá código para que los paneles puedan procesar los datos del círculo colocado, lo que le permitirá mover o copiar círculos de la colección secundaria de un panel a otro.</span><span class="sxs-lookup"><span data-stu-id="d8d84-109">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>

<span data-ttu-id="d8d84-110">En este tutorial se muestran las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d8d84-110">This walkthrough illustrates the following tasks:</span></span>

- <span data-ttu-id="d8d84-111">Crear un control de usuario personalizado.</span><span class="sxs-lookup"><span data-stu-id="d8d84-111">Create a custom user control.</span></span>

- <span data-ttu-id="d8d84-112">Permitir que el control de usuario sea un origen de arrastre.</span><span class="sxs-lookup"><span data-stu-id="d8d84-112">Enable the user control to be a drag source.</span></span>

- <span data-ttu-id="d8d84-113">Permitir que el control de usuario sea un destino de colocación.</span><span class="sxs-lookup"><span data-stu-id="d8d84-113">Enable the user control to be a drop target.</span></span>

- <span data-ttu-id="d8d84-114">Permitir que un panel reciba los datos que se colocan desde el control de usuario.</span><span class="sxs-lookup"><span data-stu-id="d8d84-114">Enable a panel to receive data dropped from the user control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d8d84-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d8d84-115">Prerequisites</span></span>

<span data-ttu-id="d8d84-116">Necesita Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="d8d84-116">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="d8d84-117">Crear el proyecto de aplicación</span><span class="sxs-lookup"><span data-stu-id="d8d84-117">Create the Application Project</span></span>
 <span data-ttu-id="d8d84-118">En esta sección, creará la infraestructura de la aplicación, que incluye una página principal con dos paneles y <xref:System.Windows.Controls.TextBox>un.</span><span class="sxs-lookup"><span data-stu-id="d8d84-118">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>

1. <span data-ttu-id="d8d84-119">Cree un proyecto de aplicación de WPF en Visual Basic o Visual C# denominado `DragDropExample`.</span><span class="sxs-lookup"><span data-stu-id="d8d84-119">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="d8d84-120">Para obtener más información, vea [Tutorial: Mi primera aplicación](../getting-started/walkthrough-my-first-wpf-desktop-application.md)de escritorio WPF.</span><span class="sxs-lookup"><span data-stu-id="d8d84-120">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

2. <span data-ttu-id="d8d84-121">Abra MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="d8d84-121">Open MainWindow.xaml.</span></span>

3. <span data-ttu-id="d8d84-122">Agregue el marcado siguiente entre las etiquetas de apertura <xref:System.Windows.Controls.Grid> y cierre.</span><span class="sxs-lookup"><span data-stu-id="d8d84-122">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>

     <span data-ttu-id="d8d84-123">Este marcado crea la interfaz de usuario de la aplicación de prueba.</span><span class="sxs-lookup"><span data-stu-id="d8d84-123">This markup creates the user interface for the test application.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a><span data-ttu-id="d8d84-124">Agregar un nuevo control de usuario al proyecto</span><span class="sxs-lookup"><span data-stu-id="d8d84-124">Add a New User Control to the Project</span></span>
 <span data-ttu-id="d8d84-125">En esta sección, agregará un nuevo control de usuario al proyecto.</span><span class="sxs-lookup"><span data-stu-id="d8d84-125">In this section, you will add a new user control to the project.</span></span>

1. <span data-ttu-id="d8d84-126">En el menú Proyecto, seleccione **Agregar control de usuario**.</span><span class="sxs-lookup"><span data-stu-id="d8d84-126">On the Project menu, select **Add User Control**.</span></span>

2. <span data-ttu-id="d8d84-127">En el cuadro de diálogo **Agregar nuevo elemento** , cambie el nombre `Circle.xaml`a y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d8d84-127">In the **Add New Item** dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>

     <span data-ttu-id="d8d84-128">Circle.xaml y su código subyacente se agregan al proyecto.</span><span class="sxs-lookup"><span data-stu-id="d8d84-128">Circle.xaml and its code-behind is added to the project.</span></span>

3. <span data-ttu-id="d8d84-129">Abra Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="d8d84-129">Open Circle.xaml.</span></span>

     <span data-ttu-id="d8d84-130">Este archivo contendrá los elementos de la interfaz de usuario del control de usuario.</span><span class="sxs-lookup"><span data-stu-id="d8d84-130">This file will contain the user interface elements of the user control.</span></span>

4. <span data-ttu-id="d8d84-131">Agregue el siguiente marcado a la raíz <xref:System.Windows.Controls.Grid> para crear un control de usuario simple que tenga un círculo azul como su interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="d8d84-131">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>

     [!code-xaml[DragDropWalkthrough#EllipseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5. <span data-ttu-id="d8d84-132">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="d8d84-132">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

6. <span data-ttu-id="d8d84-133">En C#, agregue el código siguiente después del constructor sin parámetros para crear un constructor de copias.</span><span class="sxs-lookup"><span data-stu-id="d8d84-133">In C#, add the following code after the parameterless constructor to create a copy constructor.</span></span> <span data-ttu-id="d8d84-134">En Visual Basic, agregue el código siguiente para crear un constructor sin parámetros y un constructor de copias.</span><span class="sxs-lookup"><span data-stu-id="d8d84-134">In Visual Basic, add the following code to create both a parameterless constructor and a copy constructor.</span></span>

     <span data-ttu-id="d8d84-135">Para permitir que se copie el control de usuario, puede agregar un método de constructor de copias en el archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="d8d84-135">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="d8d84-136">En el control de usuario de círculo simplificado, solo copiará el relleno y el tamaño del control de usuario.</span><span class="sxs-lookup"><span data-stu-id="d8d84-136">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>

     [!code-csharp[DragDropWalkthrough#CopyCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a><span data-ttu-id="d8d84-137">Agregar el control de usuario a la ventana principal</span><span class="sxs-lookup"><span data-stu-id="d8d84-137">Add the user control to the main window</span></span>

1. <span data-ttu-id="d8d84-138">Abra MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="d8d84-138">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="d8d84-139">Agregue el código XAML siguiente a la <xref:System.Windows.Window> etiqueta de apertura para crear una referencia de espacio de nombres XML a la aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="d8d84-139">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>

    ```xaml
    xmlns:local="clr-namespace:DragDropExample"
    ```

3. <span data-ttu-id="d8d84-140">En la primera <xref:System.Windows.Controls.StackPanel>, agregue el código XAML siguiente para crear dos instancias del control de usuario de círculo en el primer panel.</span><span class="sxs-lookup"><span data-stu-id="d8d84-140">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>

     [!code-xaml[DragDropWalkthrough#CirclesXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     <span data-ttu-id="d8d84-141">El código XAML completo del panel tendrá el aspecto siguiente.</span><span class="sxs-lookup"><span data-stu-id="d8d84-141">The full XAML for the panel looks like the following.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a><span data-ttu-id="d8d84-142">Implementar eventos de origen de arrastre en el control de usuario</span><span class="sxs-lookup"><span data-stu-id="d8d84-142">Implement Drag Source Events in the User Control</span></span>
 <span data-ttu-id="d8d84-143">En esta sección, se invalidará <xref:System.Windows.UIElement.OnMouseMove%2A> el método y se iniciará la operación de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="d8d84-143">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>

 <span data-ttu-id="d8d84-144">Si se inicia un arrastre (se presiona un botón del mouse y se mueve el mouse), se empaquetarán los datos que se van a <xref:System.Windows.DataObject>transferir a.</span><span class="sxs-lookup"><span data-stu-id="d8d84-144">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="d8d84-145">En este caso, el control de círculo empaquetará tres elementos de datos: una representación de cadena de su color de relleno, una representación doble de su altura y una copia de sí mismo.</span><span class="sxs-lookup"><span data-stu-id="d8d84-145">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="d8d84-146">Para iniciar una operación de arrastrar y colocar</span><span class="sxs-lookup"><span data-stu-id="d8d84-146">To initiate a drag-and-drop operation</span></span>

1. <span data-ttu-id="d8d84-147">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="d8d84-147">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="d8d84-148">Agregue la siguiente <xref:System.Windows.UIElement.OnMouseMove%2A> invalidación para proporcionar el control de <xref:System.Windows.UIElement.MouseMove> clases para el evento.</span><span class="sxs-lookup"><span data-stu-id="d8d84-148">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnMouseMove](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     <span data-ttu-id="d8d84-149">Esta <xref:System.Windows.UIElement.OnMouseMove%2A> invalidación realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="d8d84-149">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="d8d84-150">Comprueba si el botón primario del mouse está presionado mientras este se mueve.</span><span class="sxs-lookup"><span data-stu-id="d8d84-150">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>

    - <span data-ttu-id="d8d84-151">Empaqueta los datos del círculo en <xref:System.Windows.DataObject>un.</span><span class="sxs-lookup"><span data-stu-id="d8d84-151">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="d8d84-152">En este caso, el control de círculo empaqueta tres elementos de datos: una representación de cadena de su color de relleno, una representación doble de su altura y una copia de sí mismo.</span><span class="sxs-lookup"><span data-stu-id="d8d84-152">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

    - <span data-ttu-id="d8d84-153">Llama al método <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> estático para iniciar la operación de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="d8d84-153">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="d8d84-154">Pase los tres parámetros siguientes al <xref:System.Windows.DragDrop.DoDragDrop%2A> método:</span><span class="sxs-lookup"><span data-stu-id="d8d84-154">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>

        - <span data-ttu-id="d8d84-155">`dragSource`: una referencia a este control.</span><span class="sxs-lookup"><span data-stu-id="d8d84-155">`dragSource` – A reference to this control.</span></span>

        - <span data-ttu-id="d8d84-156">`data`<xref:System.Windows.DataObject> : Creado en el código anterior.</span><span class="sxs-lookup"><span data-stu-id="d8d84-156">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>

        - <span data-ttu-id="d8d84-157">`allowedEffects`: Las operaciones de arrastrar y colocar permitidas, que son <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="d8d84-157">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="d8d84-158">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d8d84-158">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="d8d84-159">Haga clic en uno de los controles de círculo y arrástrelo sobre los paneles, el otro círculo y <xref:System.Windows.Controls.TextBox>el.</span><span class="sxs-lookup"><span data-stu-id="d8d84-159">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="d8d84-160">Al arrastrar sobre <xref:System.Windows.Controls.TextBox>, el cursor cambia para indicar un movimiento.</span><span class="sxs-lookup"><span data-stu-id="d8d84-160">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>

5. <span data-ttu-id="d8d84-161">Mientras arrastra un círculo sobre el <xref:System.Windows.Controls.TextBox>control, presione la tecla **Ctrl** .</span><span class="sxs-lookup"><span data-stu-id="d8d84-161">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the **Ctrl** key.</span></span> <span data-ttu-id="d8d84-162">Observe que el cursor cambia para indicar una copia.</span><span class="sxs-lookup"><span data-stu-id="d8d84-162">Notice how the cursor changes to indicate a copy.</span></span>

6. <span data-ttu-id="d8d84-163">Arrastre y coloque un círculo en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d8d84-163">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="d8d84-164">La representación de cadena del color de relleno del círculo se anexa al <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d8d84-164">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>

     <span data-ttu-id="d8d84-165">![Representación de cadena del color de relleno del círculo](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="d8d84-165">![String representation of Circle's fill color](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>

<span data-ttu-id="d8d84-166">De forma predeterminada, el cursor cambiará durante una operación de arrastrar y colocar para indicar el efecto que tendrá la colocación de los datos.</span><span class="sxs-lookup"><span data-stu-id="d8d84-166">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="d8d84-167">Puede personalizar los comentarios asignados al usuario controlando el <xref:System.Windows.UIElement.GiveFeedback> evento y estableciendo un cursor diferente.</span><span class="sxs-lookup"><span data-stu-id="d8d84-167">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>

## <a name="give-feedback-to-the-user"></a><span data-ttu-id="d8d84-168">Enviar comentarios al usuario</span><span class="sxs-lookup"><span data-stu-id="d8d84-168">Give feedback to the user</span></span>

1. <span data-ttu-id="d8d84-169">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="d8d84-169">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="d8d84-170">Agregue la siguiente <xref:System.Windows.UIElement.OnGiveFeedback%2A> invalidación para proporcionar el control de <xref:System.Windows.UIElement.GiveFeedback> clases para el evento.</span><span class="sxs-lookup"><span data-stu-id="d8d84-170">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     <span data-ttu-id="d8d84-171">Esta <xref:System.Windows.UIElement.OnGiveFeedback%2A> invalidación realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="d8d84-171">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="d8d84-172">Comprueba los <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valores que se establecen en el controlador de eventos <xref:System.Windows.UIElement.DragOver> del destino de colocación.</span><span class="sxs-lookup"><span data-stu-id="d8d84-172">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

    - <span data-ttu-id="d8d84-173">Establece un cursor personalizado basado en el <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valor.</span><span class="sxs-lookup"><span data-stu-id="d8d84-173">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="d8d84-174">El cursor está diseñado para proporcionar información visual al usuario sobre el efecto que tendrá la colocación de los datos.</span><span class="sxs-lookup"><span data-stu-id="d8d84-174">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>

3. <span data-ttu-id="d8d84-175">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d8d84-175">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="d8d84-176">Arrastre uno de los controles de círculo sobre los paneles, el otro círculo y <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d8d84-176">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="d8d84-177">Observe que los cursores son ahora los cursores personalizados que especificó en la <xref:System.Windows.UIElement.OnGiveFeedback%2A> invalidación.</span><span class="sxs-lookup"><span data-stu-id="d8d84-177">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>

     <span data-ttu-id="d8d84-178">![Arrastrar y colocar con cursores personalizados](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="d8d84-178">![Drag and drop with custom cursors](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>

5. <span data-ttu-id="d8d84-179">Seleccione el texto `green` de la <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d8d84-179">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

6. <span data-ttu-id="d8d84-180">Arrastre el texto `green` a un control de círculo.</span><span class="sxs-lookup"><span data-stu-id="d8d84-180">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="d8d84-181">Observe que los cursores predeterminados se muestran para indicar los efectos de la operación de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="d8d84-181">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="d8d84-182">El origen de arrastre siempre establece el cursor de retroacción.</span><span class="sxs-lookup"><span data-stu-id="d8d84-182">The feedback cursor is always set by the drag source.</span></span>

## <a name="implement-drop-target-events-in-the-user-control"></a><span data-ttu-id="d8d84-183">Implementar eventos de destino de colocación en el control de usuario</span><span class="sxs-lookup"><span data-stu-id="d8d84-183">Implement Drop Target Events in the User Control</span></span>
 <span data-ttu-id="d8d84-184">En esta sección, especificará que el control de usuario es un destino de colocación, invalidará los métodos que permiten que el control de usuario sea un destino de colocación y procesará los datos que se colocan en él.</span><span class="sxs-lookup"><span data-stu-id="d8d84-184">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="d8d84-185">Para permitir que el control de usuario sea un destino de colocación</span><span class="sxs-lookup"><span data-stu-id="d8d84-185">To enable the user control to be a drop target</span></span>

1. <span data-ttu-id="d8d84-186">Abra Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="d8d84-186">Open Circle.xaml.</span></span>

2. <span data-ttu-id="d8d84-187">En la etiqueta <xref:System.Windows.Controls.UserControl> de apertura, agregue <xref:System.Windows.UIElement.AllowDrop%2A> la propiedad y establézcala en `true`.</span><span class="sxs-lookup"><span data-stu-id="d8d84-187">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>

     [!code-xaml[DragDropWalkthrough#UCTagXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

<span data-ttu-id="d8d84-188">Se llama al <xref:System.Windows.UIElement.AllowDrop%2A> `true` método cuando la propiedad se establece en y los datos del origen de arrastre se colocan en el control de usuario del círculo. <xref:System.Windows.UIElement.OnDrop%2A></span><span class="sxs-lookup"><span data-stu-id="d8d84-188">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="d8d84-189">En este método, procesará los datos que se han colocado y aplicará los datos al círculo.</span><span class="sxs-lookup"><span data-stu-id="d8d84-189">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>

### <a name="to-process-the-dropped-data"></a><span data-ttu-id="d8d84-190">Para procesar los datos colocados</span><span class="sxs-lookup"><span data-stu-id="d8d84-190">To process the dropped data</span></span>

1. <span data-ttu-id="d8d84-191">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="d8d84-191">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="d8d84-192">Agregue la siguiente <xref:System.Windows.UIElement.OnDrop%2A> invalidación para proporcionar el control de <xref:System.Windows.UIElement.Drop> clases para el evento.</span><span class="sxs-lookup"><span data-stu-id="d8d84-192">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     <span data-ttu-id="d8d84-193">Esta <xref:System.Windows.UIElement.OnDrop%2A> invalidación realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="d8d84-193">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="d8d84-194">Utiliza el <xref:System.Windows.DataObject.GetDataPresent%2A> método para comprobar si los datos arrastrados contienen un objeto de cadena.</span><span class="sxs-lookup"><span data-stu-id="d8d84-194">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>

    - <span data-ttu-id="d8d84-195">Utiliza el <xref:System.Windows.DataObject.GetData%2A> método para extraer los datos de cadena si están presentes.</span><span class="sxs-lookup"><span data-stu-id="d8d84-195">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>

    - <span data-ttu-id="d8d84-196">Utiliza un <xref:System.Windows.Media.BrushConverter> para intentar convertir la cadena en un <xref:System.Windows.Media.Brush>.</span><span class="sxs-lookup"><span data-stu-id="d8d84-196">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="d8d84-197">Si la conversión se realiza correctamente, aplica el pincel al <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Ellipse> del que proporciona la interfaz de usuario del control de círculo.</span><span class="sxs-lookup"><span data-stu-id="d8d84-197">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>

    - <span data-ttu-id="d8d84-198">Marca el <xref:System.Windows.UIElement.Drop> evento como controlado.</span><span class="sxs-lookup"><span data-stu-id="d8d84-198">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="d8d84-199">Debe marcar el evento de colocación como controlado para que los elementos que reciban este evento sepan que el control de usuario de círculo lo ha controlado.</span><span class="sxs-lookup"><span data-stu-id="d8d84-199">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>

3. <span data-ttu-id="d8d84-200">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d8d84-200">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="d8d84-201">Seleccione el texto `green` en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d8d84-201">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="d8d84-202">Arrastre el texto a un control de círculo y colóquelo.</span><span class="sxs-lookup"><span data-stu-id="d8d84-202">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="d8d84-203">El círculo cambia de azul a verde.</span><span class="sxs-lookup"><span data-stu-id="d8d84-203">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="d8d84-204">![Convertir una cadena en un pincel](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="d8d84-204">![Convert a string to a brush](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>

6. <span data-ttu-id="d8d84-205">Escriba el texto `green` <xref:System.Windows.Controls.TextBox>en.</span><span class="sxs-lookup"><span data-stu-id="d8d84-205">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="d8d84-206">Seleccione el texto `gre` en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d8d84-206">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="d8d84-207">Arrástrelo a un control de círculo y colóquelo.</span><span class="sxs-lookup"><span data-stu-id="d8d84-207">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="d8d84-208">Observe que el cursor cambia para indicar que se permite la colocación, pero el color del círculo no cambia porque `gre` no es un color válido.</span><span class="sxs-lookup"><span data-stu-id="d8d84-208">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>

9. <span data-ttu-id="d8d84-209">Arrastre desde el control de círculo verde y coloque en el control de círculo azul.</span><span class="sxs-lookup"><span data-stu-id="d8d84-209">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="d8d84-210">El círculo cambia de azul a verde.</span><span class="sxs-lookup"><span data-stu-id="d8d84-210">The Circle changes from blue to green.</span></span> <span data-ttu-id="d8d84-211">Observe que el cursor que se muestra depende de si <xref:System.Windows.Controls.TextBox> el o el círculo es el origen de arrastre.</span><span class="sxs-lookup"><span data-stu-id="d8d84-211">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>

<span data-ttu-id="d8d84-212">La configuración <xref:System.Windows.UIElement.AllowDrop%2A> de la `true` propiedad en y el procesamiento de los datos colocados es todo lo necesario para permitir que un elemento sea un destino de colocación.</span><span class="sxs-lookup"><span data-stu-id="d8d84-212">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="d8d84-213">Sin embargo, para proporcionar una mejor experiencia de usuario, también debe controlar <xref:System.Windows.UIElement.DragEnter>los <xref:System.Windows.UIElement.DragLeave>eventos, <xref:System.Windows.UIElement.DragOver> y.</span><span class="sxs-lookup"><span data-stu-id="d8d84-213">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="d8d84-214">En estos eventos, puede realizar comprobaciones y proporcionar repuesta adicional al usuario antes de que se coloquen los datos.</span><span class="sxs-lookup"><span data-stu-id="d8d84-214">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>

<span data-ttu-id="d8d84-215">Cuando los datos se arrastran sobre el control de usuario de círculo, el control debe notificarle al origen de arrastre si puede procesar los datos que se están arrastrando.</span><span class="sxs-lookup"><span data-stu-id="d8d84-215">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="d8d84-216">Si el control no sabe cómo procesar los datos, debe rechazar la operación de colocar.</span><span class="sxs-lookup"><span data-stu-id="d8d84-216">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="d8d84-217">Para ello, controlará el <xref:System.Windows.UIElement.DragOver> evento y establecerá la <xref:System.Windows.DragEventArgs.Effects%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="d8d84-217">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>

### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="d8d84-218">Para comprobar que se permite la colocación de datos</span><span class="sxs-lookup"><span data-stu-id="d8d84-218">To verify that the data drop is allowed</span></span>

1. <span data-ttu-id="d8d84-219">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="d8d84-219">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="d8d84-220">Agregue la siguiente <xref:System.Windows.UIElement.OnDragOver%2A> invalidación para proporcionar el control de <xref:System.Windows.UIElement.DragOver> clases para el evento.</span><span class="sxs-lookup"><span data-stu-id="d8d84-220">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     <span data-ttu-id="d8d84-221">Esta <xref:System.Windows.UIElement.OnDragOver%2A> invalidación realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="d8d84-221">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="d8d84-222">Establece la propiedad <xref:System.Windows.DragEventArgs.Effects%2A> como <xref:System.Windows.DragDropEffects.None>.</span><span class="sxs-lookup"><span data-stu-id="d8d84-222">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>

    - <span data-ttu-id="d8d84-223">Realiza las mismas comprobaciones que se realizan en <xref:System.Windows.UIElement.OnDrop%2A> el método para determinar si el control de usuario de círculo puede procesar los datos arrastrados.</span><span class="sxs-lookup"><span data-stu-id="d8d84-223">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>

    - <span data-ttu-id="d8d84-224">Si el control de usuario puede procesar los datos, establece <xref:System.Windows.DragEventArgs.Effects%2A> la propiedad <xref:System.Windows.DragDropEffects.Copy> en <xref:System.Windows.DragDropEffects.Move>o.</span><span class="sxs-lookup"><span data-stu-id="d8d84-224">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="d8d84-225">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d8d84-225">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="d8d84-226">Seleccione el texto `gre` en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d8d84-226">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="d8d84-227">Arrastre el texto a un control de círculo.</span><span class="sxs-lookup"><span data-stu-id="d8d84-227">Drag the text to a Circle control.</span></span> <span data-ttu-id="d8d84-228">Observe que ahora el cursor cambia para indicar que no se permite la colocación porque `gre` no es un color válido.</span><span class="sxs-lookup"><span data-stu-id="d8d84-228">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>

 <span data-ttu-id="d8d84-229">Puede mejorar la experiencia del usuario si aplica una vista previa de la operación de colocar.</span><span class="sxs-lookup"><span data-stu-id="d8d84-229">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="d8d84-230">Para el control de usuario de círculo, invalidará <xref:System.Windows.UIElement.OnDragLeave%2A> los <xref:System.Windows.UIElement.OnDragEnter%2A> métodos y.</span><span class="sxs-lookup"><span data-stu-id="d8d84-230">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="d8d84-231">Cuando los datos se arrastran sobre el control, el fondo <xref:System.Windows.Shapes.Shape.Fill%2A> actual se guarda en una variable de marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="d8d84-231">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="d8d84-232">A continuación, la cadena se convierte en un pincel y se <xref:System.Windows.Shapes.Ellipse> aplica al que proporciona la interfaz de usuario del círculo.</span><span class="sxs-lookup"><span data-stu-id="d8d84-232">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="d8d84-233">Si los datos se arrastran fuera del círculo sin quitarlos, el valor original <xref:System.Windows.Shapes.Shape.Fill%2A> se vuelve a aplicar al círculo.</span><span class="sxs-lookup"><span data-stu-id="d8d84-233">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="d8d84-234">Para obtener una vista previa de los efectos de la operación de arrastrar y colocar</span><span class="sxs-lookup"><span data-stu-id="d8d84-234">To preview the effects of the drag-and-drop operation</span></span>

1. <span data-ttu-id="d8d84-235">Abra Circle.xaml.cs o Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="d8d84-235">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="d8d84-236">En la clase Circle, declare <xref:System.Windows.Media.Brush> una variable `_previousFill` privada denominada e inicialícela `null`en.</span><span class="sxs-lookup"><span data-stu-id="d8d84-236">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>

     [!code-csharp[DragDropWalkthrough#Brush](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3. <span data-ttu-id="d8d84-237">Agregue la siguiente <xref:System.Windows.UIElement.OnDragEnter%2A> invalidación para proporcionar el control de <xref:System.Windows.UIElement.DragEnter> clases para el evento.</span><span class="sxs-lookup"><span data-stu-id="d8d84-237">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     <span data-ttu-id="d8d84-238">Esta <xref:System.Windows.UIElement.OnDragEnter%2A> invalidación realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="d8d84-238">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="d8d84-239">Guarda la <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad <xref:System.Windows.Shapes.Ellipse> de en la `_previousFill` variable.</span><span class="sxs-lookup"><span data-stu-id="d8d84-239">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>

    - <span data-ttu-id="d8d84-240">Realiza las mismas comprobaciones que se realizan en <xref:System.Windows.UIElement.OnDrop%2A> el método para determinar si los datos se pueden convertir <xref:System.Windows.Media.Brush>en.</span><span class="sxs-lookup"><span data-stu-id="d8d84-240">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="d8d84-241">Si los datos se convierten en un <xref:System.Windows.Media.Brush>válido, se aplica a <xref:System.Windows.Shapes.Shape.Fill%2A> la de <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="d8d84-241">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>

4. <span data-ttu-id="d8d84-242">Agregue la siguiente <xref:System.Windows.UIElement.OnDragLeave%2A> invalidación para proporcionar el control de <xref:System.Windows.UIElement.DragLeave> clases para el evento.</span><span class="sxs-lookup"><span data-stu-id="d8d84-242">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     <span data-ttu-id="d8d84-243">Esta <xref:System.Windows.UIElement.OnDragLeave%2A> invalidación realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="d8d84-243">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="d8d84-244">Aplica el <xref:System.Windows.Media.Brush> guardado en la `_previousFill` <xref:System.Windows.Shapes.Shape.Fill%2A>variableal del queproporcionalainterfazdeusuariodelcontroldeusuariodecírculo.<xref:System.Windows.Shapes.Ellipse></span><span class="sxs-lookup"><span data-stu-id="d8d84-244">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>

5. <span data-ttu-id="d8d84-245">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d8d84-245">Press **F5** to build and run the application.</span></span>

6. <span data-ttu-id="d8d84-246">Seleccione el texto `green` en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d8d84-246">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="d8d84-247">Arrastre el texto sobre un control de círculo sin colocarlo.</span><span class="sxs-lookup"><span data-stu-id="d8d84-247">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="d8d84-248">El círculo cambia de azul a verde.</span><span class="sxs-lookup"><span data-stu-id="d8d84-248">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="d8d84-249">![Vista previa de los efectos de una operación de arrastrar y colocar](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="d8d84-249">![Preview the effects of a drag&#45;and&#45;drop operation](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>

8. <span data-ttu-id="d8d84-250">Arrastre el texto fuera del control de círculo.</span><span class="sxs-lookup"><span data-stu-id="d8d84-250">Drag the text away from the Circle control.</span></span> <span data-ttu-id="d8d84-251">El círculo cambia de verde a azul.</span><span class="sxs-lookup"><span data-stu-id="d8d84-251">The Circle changes from green back to blue.</span></span>

## <a name="enable-a-panel-to-receive-dropped-data"></a><span data-ttu-id="d8d84-252">Habilitar un panel para recibir datos colocados</span><span class="sxs-lookup"><span data-stu-id="d8d84-252">Enable a Panel to Receive Dropped Data</span></span>

<span data-ttu-id="d8d84-253">En esta sección, habilitará los paneles que hospedan los controles de usuario de círculo para que actúen como destinos de colocación de los datos de círculo arrastrados.</span><span class="sxs-lookup"><span data-stu-id="d8d84-253">In this section, you enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="d8d84-254">Implementará código que le permite mover un círculo de un panel a otro, o realizar una copia de un control de círculo manteniendo presionada la tecla **Ctrl** mientras arrastra y coloca un círculo.</span><span class="sxs-lookup"><span data-stu-id="d8d84-254">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the **Ctrl** key while dragging and dropping a Circle.</span></span>

1. <span data-ttu-id="d8d84-255">Abra MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="d8d84-255">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="d8d84-256">Como se muestra en el código XAML siguiente, en cada <xref:System.Windows.Controls.StackPanel> uno de los controles, agregue controladores <xref:System.Windows.UIElement.DragOver> para <xref:System.Windows.UIElement.Drop> los eventos y.</span><span class="sxs-lookup"><span data-stu-id="d8d84-256">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="d8d84-257">Asigne al <xref:System.Windows.UIElement.DragOver> controladorde<xref:System.Windows.UIElement.Drop> eventos el nombre, `panel_Drop` ,yelnombredelcontroladordeeventos,.`panel_DragOver`</span><span class="sxs-lookup"><span data-stu-id="d8d84-257">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3. <span data-ttu-id="d8d84-258">Abra MainWindows.xaml.cs o MainWindow.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="d8d84-258">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>

4. <span data-ttu-id="d8d84-259">Agregue el código siguiente para el <xref:System.Windows.UIElement.DragOver> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="d8d84-259">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     <span data-ttu-id="d8d84-260">Este <xref:System.Windows.UIElement.DragOver> controlador de eventos realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="d8d84-260">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="d8d84-261">Comprueba que los datos arrastrados contienen los datos de "objeto" empaquetados <xref:System.Windows.DataObject> por el control de usuario de círculo y que se han pasado en la llamada a. <xref:System.Windows.DragDrop.DoDragDrop%2A></span><span class="sxs-lookup"><span data-stu-id="d8d84-261">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>

    - <span data-ttu-id="d8d84-262">Si los datos de "objeto" están presentes, comprueba si se ha presionado la tecla **Ctrl** .</span><span class="sxs-lookup"><span data-stu-id="d8d84-262">If the "Object" data is present, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="d8d84-263">Si se presiona la tecla **Ctrl** , establece la <xref:System.Windows.DragEventArgs.Effects%2A> propiedad en <xref:System.Windows.DragDropEffects.Copy>.</span><span class="sxs-lookup"><span data-stu-id="d8d84-263">If the **Ctrl** key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="d8d84-264">En caso contrario, <xref:System.Windows.DragEventArgs.Effects%2A> establezca la <xref:System.Windows.DragDropEffects.Move>propiedad en.</span><span class="sxs-lookup"><span data-stu-id="d8d84-264">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>

5. <span data-ttu-id="d8d84-265">Agregue el código siguiente para el <xref:System.Windows.UIElement.Drop> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="d8d84-265">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     <span data-ttu-id="d8d84-266">Este <xref:System.Windows.UIElement.Drop> controlador de eventos realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="d8d84-266">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="d8d84-267">Comprueba si el <xref:System.Windows.UIElement.Drop> evento ya se ha controlado.</span><span class="sxs-lookup"><span data-stu-id="d8d84-267">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="d8d84-268">Por ejemplo, si se coloca un círculo en otro círculo que controla el <xref:System.Windows.UIElement.Drop> evento, no se desea que el panel que contiene el círculo también lo controle.</span><span class="sxs-lookup"><span data-stu-id="d8d84-268">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>

    - <span data-ttu-id="d8d84-269">Si no <xref:System.Windows.UIElement.Drop> se controla el evento, comprueba si se ha presionado la tecla **Ctrl** .</span><span class="sxs-lookup"><span data-stu-id="d8d84-269">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="d8d84-270">Si se presiona la tecla **Ctrl** <xref:System.Windows.UIElement.Drop> cuando sucede, realiza una copia del control de círculo y <xref:System.Windows.Controls.StackPanel>la agrega a la <xref:System.Windows.Controls.Panel.Children%2A> colección de.</span><span class="sxs-lookup"><span data-stu-id="d8d84-270">If the **Ctrl** key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>

    - <span data-ttu-id="d8d84-271">Si no se presiona la tecla **Ctrl** , mueve el círculo de la <xref:System.Windows.Controls.Panel.Children%2A> colección de su panel primario a la <xref:System.Windows.Controls.Panel.Children%2A> colección del panel en el que se colocó.</span><span class="sxs-lookup"><span data-stu-id="d8d84-271">If the **Ctrl** key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>

    - <span data-ttu-id="d8d84-272">Establece la <xref:System.Windows.DragEventArgs.Effects%2A> propiedad para notificar <xref:System.Windows.DragDrop.DoDragDrop%2A> al método si se realizó una operación de movimiento o copia.</span><span class="sxs-lookup"><span data-stu-id="d8d84-272">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>

6. <span data-ttu-id="d8d84-273">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d8d84-273">Press **F5** to build and run the application.</span></span>

7. <span data-ttu-id="d8d84-274">Seleccione el texto `green` de la <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d8d84-274">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="d8d84-275">Arrastre el texto sobre un control de círculo y colóquelo.</span><span class="sxs-lookup"><span data-stu-id="d8d84-275">Drag the text over a Circle control and drop it.</span></span>

9. <span data-ttu-id="d8d84-276">Arrastre un control de círculo del panel izquierdo al panel derecho y colóquelo.</span><span class="sxs-lookup"><span data-stu-id="d8d84-276">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="d8d84-277">El círculo se quita de la <xref:System.Windows.Controls.Panel.Children%2A> colección del panel izquierdo y se agrega a la colección de elementos secundarios del panel derecho.</span><span class="sxs-lookup"><span data-stu-id="d8d84-277">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>

10. <span data-ttu-id="d8d84-278">Arrastre un control Circle desde el panel en el que se encuentra al otro panel y colóquelo mientras presiona la tecla **Ctrl** .</span><span class="sxs-lookup"><span data-stu-id="d8d84-278">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the **Ctrl** key.</span></span> <span data-ttu-id="d8d84-279">Se copia el círculo y la copia se agrega a la <xref:System.Windows.Controls.Panel.Children%2A> colección del panel receptor.</span><span class="sxs-lookup"><span data-stu-id="d8d84-279">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>

     <span data-ttu-id="d8d84-280">![Arrastrar un círculo mientras se presiona la tecla Ctrl](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="d8d84-280">![Dragging a Circle while pressing the CTRL key](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>

## <a name="see-also"></a><span data-ttu-id="d8d84-281">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8d84-281">See also</span></span>

- [<span data-ttu-id="d8d84-282">Información general sobre la función de arrastrar y colocar</span><span class="sxs-lookup"><span data-stu-id="d8d84-282">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
