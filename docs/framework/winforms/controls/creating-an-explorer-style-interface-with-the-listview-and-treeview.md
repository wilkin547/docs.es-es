---
title: 'Tutorial: Crear una interfaz de tipo Explorador con los controles ListView y TreeView mediante el diseñador'
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
ms.openlocfilehash: 8192151aa7cd5eddd99d39adb485e460074fdb99
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332123"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a><span data-ttu-id="019a3-102">Tutorial: Crear una interfaz de tipo Explorador con los controles ListView y TreeView mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="019a3-102">Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer</span></span>
<span data-ttu-id="019a3-103">Una de las ventajas de Visual Studio es la capacidad para crear aplicaciones de Windows Forms con aspecto profesional en muy poco tiempo.</span><span class="sxs-lookup"><span data-stu-id="019a3-103">One of the benefits of Visual Studio is the ability to create professional-looking Windows Forms applications in a short of amount of time.</span></span> <span data-ttu-id="019a3-104">Un escenario común es crear una interfaz de usuario (UI) con <xref:System.Windows.Forms.ListView> y <xref:System.Windows.Forms.TreeView> los controles que se parece a la característica Explorador de Windows de los sistemas operativos de Windows.</span><span class="sxs-lookup"><span data-stu-id="019a3-104">A common scenario is creating a user interface (UI) with <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls that resembles the Windows Explorer feature of Windows operating systems.</span></span> <span data-ttu-id="019a3-105">El Explorador de Windows muestra una estructura jerárquica de los archivos y carpetas en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="019a3-105">Windows Explorer displays a hierarchical structure of the files and folders on a user's computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="019a3-106">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="019a3-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="019a3-107">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="019a3-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="019a3-108">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="019a3-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a><span data-ttu-id="019a3-109">Para crear el formulario que contiene un control ListView y TreeView</span><span class="sxs-lookup"><span data-stu-id="019a3-109">To create the form containing a ListView and TreeView control</span></span>  
  
1. <span data-ttu-id="019a3-110">En el menú **Archivo** , elija **Nuevo**y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="019a3-110">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="019a3-111">En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="019a3-111">In the **New Project** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="019a3-112">En las categorías, elija **Visual Basic** o **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="019a3-112">In the categories, choose either **Visual Basic** or **Visual C#**.</span></span>  
  
    2.  <span data-ttu-id="019a3-113">En la lista de plantillas, elija **aplicación de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="019a3-113">In the list of templates, choose **Windows Forms Application**.</span></span>  
  
3. <span data-ttu-id="019a3-114">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="019a3-114">Click **OK**.</span></span> <span data-ttu-id="019a3-115">Se crea un nuevo proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="019a3-115">A new Windows Forms project is created.</span></span>  
  
4. <span data-ttu-id="019a3-116">Agregar un <xref:System.Windows.Forms.SplitContainer> control al formulario y establezca su <xref:System.Windows.Forms.SplitContainer.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="019a3-116">Add a <xref:System.Windows.Forms.SplitContainer> control to the form and set its <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
5. <span data-ttu-id="019a3-117">Agregar un <xref:System.Windows.Forms.ImageList> denominado `imageList1` al formulario y usar la ventana de propiedades para agregar dos imágenes: una imagen de una carpeta y una imagen de documento, en ese orden.</span><span class="sxs-lookup"><span data-stu-id="019a3-117">Add an <xref:System.Windows.Forms.ImageList> named `imageList1` to the form and use the Properties window to add two images: a folder image and a document image, in that order.</span></span>  
  
6. <span data-ttu-id="019a3-118">Agregar un <xref:System.Windows.Forms.TreeView> control denominado `treeview1` al formulario y colóquelo en el lado izquierdo de la <xref:System.Windows.Forms.SplitContainer> control.</span><span class="sxs-lookup"><span data-stu-id="019a3-118">Add a <xref:System.Windows.Forms.TreeView> control named `treeview1` to the form, and position it on the left side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="019a3-119">En la ventana Propiedades para `treeView1` haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="019a3-119">In the Properties window for `treeView1` do the following:</span></span>  
  
    1.  <span data-ttu-id="019a3-120">Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="019a3-120">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
    2.  <span data-ttu-id="019a3-121">Establecer el <xref:System.Windows.Forms.TreeView.ImageList%2A> propiedad</span><span class="sxs-lookup"><span data-stu-id="019a3-121">Set the <xref:System.Windows.Forms.TreeView.ImageList%2A> property to</span></span> `imagelist1.`  
  
7. <span data-ttu-id="019a3-122">Agregar un <xref:System.Windows.Forms.ListView> control denominado `listView1` al formulario y colóquelo en el lado derecho de la <xref:System.Windows.Forms.SplitContainer> control.</span><span class="sxs-lookup"><span data-stu-id="019a3-122">Add a <xref:System.Windows.Forms.ListView> control named `listView1` to the form, and position it on the right side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="019a3-123">En la ventana Propiedades para `listview1` haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="019a3-123">In the Properties window for `listview1` do the following:</span></span>  
  
    1.  <span data-ttu-id="019a3-124">Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="019a3-124">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
    2.  <span data-ttu-id="019a3-125">Establezca la propiedad <xref:System.Windows.Forms.ListView.View%2A> en <xref:System.Windows.Forms.View.Details>.</span><span class="sxs-lookup"><span data-stu-id="019a3-125">Set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
    3.  <span data-ttu-id="019a3-126">Abra el Editor de la colección ColumnHeader haciendo clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) en el <xref:System.Windows.Forms.ListView.Columns%2A> propiedad **.**</span><span class="sxs-lookup"><span data-stu-id="019a3-126">Open the ColumnHeader Collection Editor by clicking the ellipses (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) in the <xref:System.Windows.Forms.ListView.Columns%2A> property **.**</span></span> <span data-ttu-id="019a3-127">Agregue tres columnas y establezca sus <xref:System.Windows.Forms.ColumnHeader.Text%2A> propiedad `Name`, `Type`, y `Last Modified`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="019a3-127">Add three columns and set their <xref:System.Windows.Forms.ColumnHeader.Text%2A> property to `Name`, `Type`, and `Last Modified`, respectively.</span></span> <span data-ttu-id="019a3-128">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="019a3-128">Click **OK** to close the dialog box.</span></span>  
  
    4.  <span data-ttu-id="019a3-129">Establecer el <xref:System.Windows.Forms.ListView.SmallImageList%2A> propiedad</span><span class="sxs-lookup"><span data-stu-id="019a3-129">Set the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property to</span></span> `imageList1.`  
  
8. <span data-ttu-id="019a3-130">Implemente el código para rellenar el <xref:System.Windows.Forms.TreeView> con nodos y subnodos.</span><span class="sxs-lookup"><span data-stu-id="019a3-130">Implement the code to populate the <xref:System.Windows.Forms.TreeView> with nodes and subnodes.</span></span> <span data-ttu-id="019a3-131">Agregue este código a la clase `Form1`.</span><span class="sxs-lookup"><span data-stu-id="019a3-131">Add this code to the `Form1` class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]  
  
9. <span data-ttu-id="019a3-132">Puesto que el código anterior usa el espacio de nombres System.IO, el uso adecuada de agregar o importar instrucción en la parte superior del formulario.</span><span class="sxs-lookup"><span data-stu-id="019a3-132">Since the previous code uses the System.IO namespace, add the appropriate using or import statement at the top of the form.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]  
  
10. <span data-ttu-id="019a3-133">Llame al método de instalación desde el paso anterior en el constructor del formulario o <xref:System.Windows.Forms.Form.Load> el método de control de eventos.</span><span class="sxs-lookup"><span data-stu-id="019a3-133">Call the set-up method from the previous step in the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span> <span data-ttu-id="019a3-134">Agregue este código al constructor del formulario.</span><span class="sxs-lookup"><span data-stu-id="019a3-134">Add this code to the form constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]  
  
11. <span data-ttu-id="019a3-135">Controlar la <xref:System.Windows.Forms.TreeView.NodeMouseClick> eventos para `treeview1` **,** e implemente el código para rellenar `listview1` con contenido de un nodo cuando se hace clic en un nodo.</span><span class="sxs-lookup"><span data-stu-id="019a3-135">Handle the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event for `treeview1`**,** and implement the code to populate `listview1` with a node's contents when a node is clicked.</span></span> <span data-ttu-id="019a3-136">Agregue este código a la clase `Form1`.</span><span class="sxs-lookup"><span data-stu-id="019a3-136">Add this code to the `Form1` class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]  
  
     <span data-ttu-id="019a3-137">Si está utilizando C#, asegúrese de que tiene el <xref:System.Windows.Forms.TreeView.NodeMouseClick> evento asociado a su método de control de eventos.</span><span class="sxs-lookup"><span data-stu-id="019a3-137">If you are using C#, make sure you have the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event associated with its event-handling method.</span></span> <span data-ttu-id="019a3-138">Agregue este código al constructor del formulario.</span><span class="sxs-lookup"><span data-stu-id="019a3-138">Add this code to the form constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="019a3-139">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="019a3-139">Testing the Application</span></span>  
 <span data-ttu-id="019a3-140">Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.</span><span class="sxs-lookup"><span data-stu-id="019a3-140">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="019a3-141">Para comprobar el formulario</span><span class="sxs-lookup"><span data-stu-id="019a3-141">To test the form</span></span>  
  
-   <span data-ttu-id="019a3-142">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="019a3-142">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="019a3-143">Verá un formulario dividido que contenga un <xref:System.Windows.Forms.TreeView> control que muestra el directorio del proyecto en el lado izquierdo, y un <xref:System.Windows.Forms.ListView> control a la derecha con tres columnas.</span><span class="sxs-lookup"><span data-stu-id="019a3-143">You will see a split form containing a <xref:System.Windows.Forms.TreeView> control that displays your project directory on the left side, and a <xref:System.Windows.Forms.ListView> control on the right side with three columns.</span></span> <span data-ttu-id="019a3-144">Puede recorrer el <xref:System.Windows.Forms.TreeView> seleccionando los nodos del directorio y el <xref:System.Windows.Forms.ListView> se rellena con el contenido del directorio seleccionado.</span><span class="sxs-lookup"><span data-stu-id="019a3-144">You can traverse the <xref:System.Windows.Forms.TreeView> by selecting directory nodes, and the <xref:System.Windows.Forms.ListView> is populated with the contents of the selected directory.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="019a3-145">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="019a3-145">Next Steps</span></span>  
 <span data-ttu-id="019a3-146">Esta aplicación le ofrece un ejemplo de cómo puede usar <xref:System.Windows.Forms.TreeView> y <xref:System.Windows.Forms.ListView> controles juntos.</span><span class="sxs-lookup"><span data-stu-id="019a3-146">This application gives you an example of a way you can use <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ListView> controls together.</span></span> <span data-ttu-id="019a3-147">Para obtener más información sobre estos controles, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="019a3-147">For more information on these controls, see the following topics:</span></span>  
  
-   [<span data-ttu-id="019a3-148">Filtrar para agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="019a3-148">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)  
  
-   [<span data-ttu-id="019a3-149">Filtrar para agregar funcionalidades de búsqueda a un control ListView</span><span class="sxs-lookup"><span data-stu-id="019a3-149">How to: Add Search Capabilities to a ListView Control</span></span>](how-to-add-search-capabilities-to-a-listview-control.md)  
  
-   [<span data-ttu-id="019a3-150">Filtrar para asociar un menú contextual a un nodo TreeView</span><span class="sxs-lookup"><span data-stu-id="019a3-150">How to: Attach a ShortCut Menu to a TreeView Node</span></span>](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)  
  
## <a name="see-also"></a><span data-ttu-id="019a3-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="019a3-151">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [<span data-ttu-id="019a3-152">Control ListView</span><span class="sxs-lookup"><span data-stu-id="019a3-152">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="019a3-153">Filtrar para agregar y quitar nodos con el control TreeView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="019a3-153">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="019a3-154">Filtrar para agregar y quitar elementos con el control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="019a3-154">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="019a3-155">Filtrar para agregar columnas al control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="019a3-155">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
