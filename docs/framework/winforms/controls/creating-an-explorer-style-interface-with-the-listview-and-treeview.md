---
title: 'Tutorial: Crear una interfaz de tipo Explorador con los controles ListView y TreeView mediante el diseñador'
description: Obtenga información sobre cómo crear una interfaz de estilo del explorador con los controles Windows Forms ListView y TreeView mediante el diseñador.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Explorer-style applications [Windows Forms], walkthroughs
- TreeView control [Windows Forms], ListView controls used with
- ListView control [Windows Forms], TreeView controls used with
- Explorer-style applications
- TreeView control [Windows Forms], using for explorer-style interface
- ListView control [Windows Forms], explorer style interface
- ListView control [Windows Forms], explorer-style interface
ms.assetid: 9e5e7721-19e2-4890-b273-a43589fe99ff
ms.openlocfilehash: 44d4db1ef3da85dbf411498f486882b86a05c140
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174632"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a><span data-ttu-id="e80cb-103">Tutorial: Crear una interfaz de tipo Explorador con los controles ListView y TreeView mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="e80cb-103">Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer</span></span>

<span data-ttu-id="e80cb-104">Una de las ventajas de Visual Studio es la posibilidad de crear aplicaciones de Windows Forms de aspecto profesional en poco tiempo.</span><span class="sxs-lookup"><span data-stu-id="e80cb-104">One of the benefits of Visual Studio is the ability to create professional-looking Windows Forms applications in a short of amount of time.</span></span> <span data-ttu-id="e80cb-105">Un escenario común es la creación de una interfaz de usuario (UI) con <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> controles y que se parece a la característica explorador de Windows de los sistemas operativos Windows.</span><span class="sxs-lookup"><span data-stu-id="e80cb-105">A common scenario is creating a user interface (UI) with <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls that resembles the Windows Explorer feature of Windows operating systems.</span></span> <span data-ttu-id="e80cb-106">El explorador de Windows muestra una estructura jerárquica de los archivos y carpetas en el equipo de un usuario.</span><span class="sxs-lookup"><span data-stu-id="e80cb-106">Windows Explorer displays a hierarchical structure of the files and folders on a user's computer.</span></span>

### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a><span data-ttu-id="e80cb-107">Para crear el formulario que contiene un control ListView y TreeView</span><span class="sxs-lookup"><span data-stu-id="e80cb-107">To create the form containing a ListView and TreeView control</span></span>

1. <span data-ttu-id="e80cb-108">En el menú **Archivo** , seleccione **Nuevo**y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="e80cb-108">On the **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="e80cb-109">En el cuadro de diálogo **Nuevo proyecto** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e80cb-109">In the **New Project** dialog box, do the following:</span></span>

    1. <span data-ttu-id="e80cb-110">En las categorías, elija **Visual Basic** o **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="e80cb-110">In the categories, choose either **Visual Basic** or **Visual C#**.</span></span>

    2. <span data-ttu-id="e80cb-111">En la lista de plantillas, elija **Windows Forms aplicación**.</span><span class="sxs-lookup"><span data-stu-id="e80cb-111">In the list of templates, choose **Windows Forms Application**.</span></span>

3. <span data-ttu-id="e80cb-112">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e80cb-112">Click **OK**.</span></span> <span data-ttu-id="e80cb-113">Se crea un nuevo proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e80cb-113">A new Windows Forms project is created.</span></span>

4. <span data-ttu-id="e80cb-114">Agregue un <xref:System.Windows.Forms.SplitContainer> control al formulario y establezca su <xref:System.Windows.Forms.SplitContainer.Dock%2A> propiedad en <xref:System.Windows.Forms.DockStyle.Fill> .</span><span class="sxs-lookup"><span data-stu-id="e80cb-114">Add a <xref:System.Windows.Forms.SplitContainer> control to the form and set its <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

5. <span data-ttu-id="e80cb-115">Agregue un <xref:System.Windows.Forms.ImageList> denominado `imageList1` al formulario y use el ventana Propiedades para agregar dos imágenes: una imagen de carpeta y una imagen de documento, en ese orden.</span><span class="sxs-lookup"><span data-stu-id="e80cb-115">Add an <xref:System.Windows.Forms.ImageList> named `imageList1` to the form and use the Properties window to add two images: a folder image and a document image, in that order.</span></span>

6. <span data-ttu-id="e80cb-116">Agregue un <xref:System.Windows.Forms.TreeView> control denominado `treeview1` al formulario y colóquelo en el lado izquierdo del <xref:System.Windows.Forms.SplitContainer> control.</span><span class="sxs-lookup"><span data-stu-id="e80cb-116">Add a <xref:System.Windows.Forms.TreeView> control named `treeview1` to the form, and position it on the left side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="e80cb-117">En el ventana Propiedades de, `treeView1` haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e80cb-117">In the Properties window for `treeView1` do the following:</span></span>

    1. <span data-ttu-id="e80cb-118">Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="e80cb-118">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    2. <span data-ttu-id="e80cb-119">Establezca la propiedad <xref:System.Windows.Forms.TreeView.ImageList%2A> en `imagelist1.`.</span><span class="sxs-lookup"><span data-stu-id="e80cb-119">Set the <xref:System.Windows.Forms.TreeView.ImageList%2A> property to `imagelist1.`</span></span>

7. <span data-ttu-id="e80cb-120">Agregue un <xref:System.Windows.Forms.ListView> control denominado `listView1` al formulario y colóquelo en el lado derecho del <xref:System.Windows.Forms.SplitContainer> control.</span><span class="sxs-lookup"><span data-stu-id="e80cb-120">Add a <xref:System.Windows.Forms.ListView> control named `listView1` to the form, and position it on the right side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="e80cb-121">En el ventana Propiedades de, `listview1` haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e80cb-121">In the Properties window for `listview1` do the following:</span></span>

    1. <span data-ttu-id="e80cb-122">Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="e80cb-122">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    2. <span data-ttu-id="e80cb-123">Establezca la propiedad <xref:System.Windows.Forms.ListView.View%2A> en <xref:System.Windows.Forms.View.Details>.</span><span class="sxs-lookup"><span data-stu-id="e80cb-123">Set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>

    3. <span data-ttu-id="e80cb-124">Abra el editor de la colección ColumnHeader haciendo clic en los puntos suspensivos ( ![ el botón de puntos suspensivos (...) en el ventana Propiedades de Visual Studio. ](./media/visual-studio-ellipsis-button.png) ) en la <xref:System.Windows.Forms.ListView.Columns%2A> propiedad **.**</span><span class="sxs-lookup"><span data-stu-id="e80cb-124">Open the ColumnHeader Collection Editor by clicking the ellipses (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) in the <xref:System.Windows.Forms.ListView.Columns%2A> property **.**</span></span> <span data-ttu-id="e80cb-125">Agregue tres columnas y establezca su <xref:System.Windows.Forms.ColumnHeader.Text%2A> propiedad en `Name` , `Type` y `Last Modified` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e80cb-125">Add three columns and set their <xref:System.Windows.Forms.ColumnHeader.Text%2A> property to `Name`, `Type`, and `Last Modified`, respectively.</span></span> <span data-ttu-id="e80cb-126">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e80cb-126">Click **OK** to close the dialog box.</span></span>

    4. <span data-ttu-id="e80cb-127">Establezca la propiedad <xref:System.Windows.Forms.ListView.SmallImageList%2A> en `imageList1.`.</span><span class="sxs-lookup"><span data-stu-id="e80cb-127">Set the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property to `imageList1.`</span></span>

8. <span data-ttu-id="e80cb-128">Implemente el código para rellenar <xref:System.Windows.Forms.TreeView> con los nodos y subnodos.</span><span class="sxs-lookup"><span data-stu-id="e80cb-128">Implement the code to populate the <xref:System.Windows.Forms.TreeView> with nodes and subnodes.</span></span> <span data-ttu-id="e80cb-129">Agregue este código a la clase `Form1`.</span><span class="sxs-lookup"><span data-stu-id="e80cb-129">Add this code to the `Form1` class.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]

9. <span data-ttu-id="e80cb-130">Dado que el código anterior usa el espacio de nombres System.IO, agregue la instrucción using o Import adecuada en la parte superior del formulario.</span><span class="sxs-lookup"><span data-stu-id="e80cb-130">Since the previous code uses the System.IO namespace, add the appropriate using or import statement at the top of the form.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]

10. <span data-ttu-id="e80cb-131">Llame al método de configuración desde el paso anterior en el constructor del formulario o el <xref:System.Windows.Forms.Form.Load> método de control de eventos.</span><span class="sxs-lookup"><span data-stu-id="e80cb-131">Call the set-up method from the previous step in the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span> <span data-ttu-id="e80cb-132">Agregue este código al constructor del formulario.</span><span class="sxs-lookup"><span data-stu-id="e80cb-132">Add this code to the form constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]

11. <span data-ttu-id="e80cb-133">Controle el <xref:System.Windows.Forms.TreeView.NodeMouseClick> evento de `treeview1` **,** e implemente el código para rellenar el `listview1` contenido de un nodo cuando se haga clic en un nodo.</span><span class="sxs-lookup"><span data-stu-id="e80cb-133">Handle the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event for `treeview1`**,** and implement the code to populate `listview1` with a node's contents when a node is clicked.</span></span> <span data-ttu-id="e80cb-134">Agregue este código a la clase `Form1`.</span><span class="sxs-lookup"><span data-stu-id="e80cb-134">Add this code to the `Form1` class.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]

     <span data-ttu-id="e80cb-135">Si usa C#, asegúrese de que tiene el <xref:System.Windows.Forms.TreeView.NodeMouseClick> evento asociado a su método de control de eventos.</span><span class="sxs-lookup"><span data-stu-id="e80cb-135">If you are using C#, make sure you have the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event associated with its event-handling method.</span></span> <span data-ttu-id="e80cb-136">Agregue este código al constructor del formulario.</span><span class="sxs-lookup"><span data-stu-id="e80cb-136">Add this code to the form constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]

## <a name="testing-the-application"></a><span data-ttu-id="e80cb-137">Prueba de la aplicación</span><span class="sxs-lookup"><span data-stu-id="e80cb-137">Testing the Application</span></span>

<span data-ttu-id="e80cb-138">Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.</span><span class="sxs-lookup"><span data-stu-id="e80cb-138">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="e80cb-139">Para comprobar el formulario</span><span class="sxs-lookup"><span data-stu-id="e80cb-139">To test the form</span></span>

- <span data-ttu-id="e80cb-140">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e80cb-140">Press F5 to run the application.</span></span>

     <span data-ttu-id="e80cb-141">Verá un formulario dividido que contiene un <xref:System.Windows.Forms.TreeView> control que muestra el directorio del proyecto en el lado izquierdo y un <xref:System.Windows.Forms.ListView> control en el lado derecho con tres columnas.</span><span class="sxs-lookup"><span data-stu-id="e80cb-141">You will see a split form containing a <xref:System.Windows.Forms.TreeView> control that displays your project directory on the left side, and a <xref:System.Windows.Forms.ListView> control on the right side with three columns.</span></span> <span data-ttu-id="e80cb-142">Puede atravesar el seleccionando los <xref:System.Windows.Forms.TreeView> nodos del directorio y el <xref:System.Windows.Forms.ListView> se rellena con el contenido del directorio seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e80cb-142">You can traverse the <xref:System.Windows.Forms.TreeView> by selecting directory nodes, and the <xref:System.Windows.Forms.ListView> is populated with the contents of the selected directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e80cb-143">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e80cb-143">Next Steps</span></span>

<span data-ttu-id="e80cb-144">Esta aplicación ofrece un ejemplo de una manera de usar <xref:System.Windows.Forms.TreeView> y <xref:System.Windows.Forms.ListView> controles juntos.</span><span class="sxs-lookup"><span data-stu-id="e80cb-144">This application gives you an example of a way you can use <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ListView> controls together.</span></span> <span data-ttu-id="e80cb-145">Para obtener más información sobre estos controles, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="e80cb-145">For more information on these controls, see the following topics:</span></span>

- [<span data-ttu-id="e80cb-146">Procedimiento para agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e80cb-146">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)

- [<span data-ttu-id="e80cb-147">Procedimiento para agregar funcionalidades de búsqueda a un control ListView</span><span class="sxs-lookup"><span data-stu-id="e80cb-147">How to: Add Search Capabilities to a ListView Control</span></span>](how-to-add-search-capabilities-to-a-listview-control.md)

- [<span data-ttu-id="e80cb-148">Procedimiento para asociar un menú contextual a un nodo TreeView</span><span class="sxs-lookup"><span data-stu-id="e80cb-148">How to: Attach a ShortCut Menu to a TreeView Node</span></span>](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)

## <a name="see-also"></a><span data-ttu-id="e80cb-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="e80cb-149">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [<span data-ttu-id="e80cb-150">Control ListView</span><span class="sxs-lookup"><span data-stu-id="e80cb-150">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="e80cb-151">Procedimiento para agregar y quitar nodos con el control TreeView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e80cb-151">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="e80cb-152">Procedimiento para agregar y quitar elementos con el control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e80cb-152">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="e80cb-153">Procedimiento para agregar columnas al control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e80cb-153">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
