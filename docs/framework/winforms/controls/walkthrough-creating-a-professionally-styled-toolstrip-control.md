---
title: 'Tutorial: Crear un control ToolStrip de estilo profesional'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
ms.openlocfilehash: 226e805d0240236899ee0cc290f1060a3b0aa391
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211770"
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="b1604-102">Tutorial: Crear un control ToolStrip de estilo profesional</span><span class="sxs-lookup"><span data-stu-id="b1604-102">Walkthrough: Creating a Professionally Styled ToolStrip Control</span></span>

<span data-ttu-id="b1604-103">Puedes usar la aplicación <xref:System.Windows.Forms.ToolStrip> controla un aspecto y comportamiento profesional escribiendo su propia clase derivada de la <xref:System.Windows.Forms.ToolStripProfessionalRenderer> tipo.</span><span class="sxs-lookup"><span data-stu-id="b1604-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>

<span data-ttu-id="b1604-104">Este tutorial muestra cómo usar <xref:System.Windows.Forms.ToolStrip> controles para crear un control compuesto que es similar a la **panel de navegación** proporcionado por Microsoft® Outlook®.</span><span class="sxs-lookup"><span data-stu-id="b1604-104">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that resembles the **Navigation Pane** provided by Microsoft® Outlook®.</span></span> <span data-ttu-id="b1604-105">En este tutorial se muestran las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b1604-105">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="b1604-106">Crear un proyecto de biblioteca de controles de Windows.</span><span class="sxs-lookup"><span data-stu-id="b1604-106">Creating a Windows Control Library project.</span></span>

- <span data-ttu-id="b1604-107">Diseñar el Control StackView.</span><span class="sxs-lookup"><span data-stu-id="b1604-107">Designing the StackView Control.</span></span>

- <span data-ttu-id="b1604-108">Implementación de un representador personalizado.</span><span class="sxs-lookup"><span data-stu-id="b1604-108">Implementing a Custom Renderer.</span></span>

<span data-ttu-id="b1604-109">Cuando haya terminado, tendrá un control de cliente personalizado reutilizable con la apariencia de un control de Microsoft Office XP professional.</span><span class="sxs-lookup"><span data-stu-id="b1604-109">When you are finished, you will have a reusable custom client control with the professional appearance of a Microsoft Office® XP control.</span></span>

<span data-ttu-id="b1604-110">Para copiar el código de este tema como una sola lista, vea [Cómo: Crear un Control ToolStrip de estilo profesional](how-to-create-a-professionally-styled-toolstrip-control.md).</span><span class="sxs-lookup"><span data-stu-id="b1604-110">To copy the code in this topic as a single listing, see [How to: Create a Professionally Styled ToolStrip Control](how-to-create-a-professionally-styled-toolstrip-control.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b1604-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b1604-111">Prerequisites</span></span>

<span data-ttu-id="b1604-112">Necesitará Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="b1604-112">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="b1604-113">Crear el proyecto de biblioteca de controles</span><span class="sxs-lookup"><span data-stu-id="b1604-113">Create the control library project</span></span>

1. <span data-ttu-id="b1604-114">En Visual Studio, cree un nuevo proyecto de biblioteca de controles de Windows denominado `StackViewLibrary`.</span><span class="sxs-lookup"><span data-stu-id="b1604-114">In Visual Studio, create a new Windows Control Library project named `StackViewLibrary`.</span></span>

2. <span data-ttu-id="b1604-115">En **el Explorador de soluciones**, elimine el control predeterminado del proyecto eliminando el archivo de origen denominado "UserControl1.cs" o "UserControl1.vb", dependiendo del lenguaje que prefiera.</span><span class="sxs-lookup"><span data-stu-id="b1604-115">In **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>

     <span data-ttu-id="b1604-116">Para obtener más información, vea [Cómo: Quitar, eliminar y excluir elementos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b1604-116">For more information, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>

3. <span data-ttu-id="b1604-117">Agregue un nuevo <xref:System.Windows.Forms.UserControl> elemento a la **StackViewLibrary** proyecto.</span><span class="sxs-lookup"><span data-stu-id="b1604-117">Add a new <xref:System.Windows.Forms.UserControl> item to the **StackViewLibrary** project.</span></span> <span data-ttu-id="b1604-118">Dé el nuevo archivo de origen en un nombre de base de `StackView`.</span><span class="sxs-lookup"><span data-stu-id="b1604-118">Give the new source file a base name of `StackView`.</span></span>

## <a name="design-the-stackview-control"></a><span data-ttu-id="b1604-119">Diseñar el control StackView</span><span class="sxs-lookup"><span data-stu-id="b1604-119">Design the StackView control</span></span>

<span data-ttu-id="b1604-120">El `StackView` control es un control compuesto con un elemento secundario <xref:System.Windows.Forms.ToolStrip> control.</span><span class="sxs-lookup"><span data-stu-id="b1604-120">The `StackView` control is a composite control with one child <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="b1604-121">Para obtener más información acerca de los controles compuestos, vea [variedades de controles personalizados](varieties-of-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="b1604-121">For more information about composite controls, see [Varieties of Custom Controls](varieties-of-custom-controls.md).</span></span>

1. <span data-ttu-id="b1604-122">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.ToolStrip> control a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="b1604-122">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStrip> control to the design surface.</span></span>

2. <span data-ttu-id="b1604-123">En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.ToolStrip> propiedades del control según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="b1604-123">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStrip> control's properties according to the following table.</span></span>

    |<span data-ttu-id="b1604-124">Propiedad</span><span class="sxs-lookup"><span data-stu-id="b1604-124">Property</span></span>|<span data-ttu-id="b1604-125">Valor</span><span class="sxs-lookup"><span data-stu-id="b1604-125">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="b1604-126">Name</span><span class="sxs-lookup"><span data-stu-id="b1604-126">Name</span></span>|`stackStrip`|
    |<span data-ttu-id="b1604-127">CanOverflow</span><span class="sxs-lookup"><span data-stu-id="b1604-127">CanOverflow</span></span>|`false`|
    |<span data-ttu-id="b1604-128">Acoplar</span><span class="sxs-lookup"><span data-stu-id="b1604-128">Dock</span></span>|<xref:System.Windows.Forms.DockStyle.Bottom>|
    |<span data-ttu-id="b1604-129">Fuente</span><span class="sxs-lookup"><span data-stu-id="b1604-129">Font</span></span>|`Tahoma, 10pt, style=Bold`|
    |<span data-ttu-id="b1604-130">GripStyle</span><span class="sxs-lookup"><span data-stu-id="b1604-130">GripStyle</span></span>|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|
    |<span data-ttu-id="b1604-131">LayoutStyle</span><span class="sxs-lookup"><span data-stu-id="b1604-131">LayoutStyle</span></span>|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|
    |<span data-ttu-id="b1604-132">Relleno</span><span class="sxs-lookup"><span data-stu-id="b1604-132">Padding</span></span>|`0, 7, 0, 0`|
    |<span data-ttu-id="b1604-133">RenderMode</span><span class="sxs-lookup"><span data-stu-id="b1604-133">RenderMode</span></span>|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|

3. <span data-ttu-id="b1604-134">En el Diseñador de formularios de Windows, haga clic en el <xref:System.Windows.Forms.ToolStrip> del control **agregar** botón y agregue un <xref:System.Windows.Forms.ToolStripButton> a la `stackStrip` control.</span><span class="sxs-lookup"><span data-stu-id="b1604-134">In the Windows Forms Designer, click the <xref:System.Windows.Forms.ToolStrip> control's **Add** button and add a <xref:System.Windows.Forms.ToolStripButton> to the `stackStrip` control.</span></span>

4. <span data-ttu-id="b1604-135">En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.ToolStripButton> propiedades del control según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="b1604-135">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStripButton> control's properties according to the following table.</span></span>

    |<span data-ttu-id="b1604-136">Propiedad</span><span class="sxs-lookup"><span data-stu-id="b1604-136">Property</span></span>|<span data-ttu-id="b1604-137">Valor</span><span class="sxs-lookup"><span data-stu-id="b1604-137">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="b1604-138">Name</span><span class="sxs-lookup"><span data-stu-id="b1604-138">Name</span></span>|`mailStackButton`|
    |<span data-ttu-id="b1604-139">CheckOnClick</span><span class="sxs-lookup"><span data-stu-id="b1604-139">CheckOnClick</span></span>|<span data-ttu-id="b1604-140">true</span><span class="sxs-lookup"><span data-stu-id="b1604-140">true</span></span>|
    |<span data-ttu-id="b1604-141">CheckState</span><span class="sxs-lookup"><span data-stu-id="b1604-141">CheckState</span></span>|<xref:System.Windows.Forms.CheckState.Checked>|
    |<span data-ttu-id="b1604-142">DisplayStyle</span><span class="sxs-lookup"><span data-stu-id="b1604-142">DisplayStyle</span></span>|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|
    |<span data-ttu-id="b1604-143">ImageAlign</span><span class="sxs-lookup"><span data-stu-id="b1604-143">ImageAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|
    |<span data-ttu-id="b1604-144">ImageScaling</span><span class="sxs-lookup"><span data-stu-id="b1604-144">ImageScaling</span></span>|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|
    |<span data-ttu-id="b1604-145">ImageTransparentColor</span><span class="sxs-lookup"><span data-stu-id="b1604-145">ImageTransparentColor</span></span>|`238, 238, 238`|
    |<span data-ttu-id="b1604-146">Margen</span><span class="sxs-lookup"><span data-stu-id="b1604-146">Margin</span></span>|`0, 0, 0, 0`|
    |<span data-ttu-id="b1604-147">Relleno</span><span class="sxs-lookup"><span data-stu-id="b1604-147">Padding</span></span>|`3, 3, 3, 3`|
    |<span data-ttu-id="b1604-148">Texto</span><span class="sxs-lookup"><span data-stu-id="b1604-148">Text</span></span>|<span data-ttu-id="b1604-149">**Correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="b1604-149">**Mail**</span></span>|
    |<span data-ttu-id="b1604-150">TextAlign</span><span class="sxs-lookup"><span data-stu-id="b1604-150">TextAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|

5. <span data-ttu-id="b1604-151">Repita el paso 7 para tres más <xref:System.Windows.Forms.ToolStripButton> controles.</span><span class="sxs-lookup"><span data-stu-id="b1604-151">Repeat step 7 for three more <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>

     <span data-ttu-id="b1604-152">Asigne a los controles `calendarStackButton`, `contactsStackButton`, y `tasksStackButton`.</span><span class="sxs-lookup"><span data-stu-id="b1604-152">Name the controls `calendarStackButton`, `contactsStackButton`, and `tasksStackButton`.</span></span> <span data-ttu-id="b1604-153">Establezca el valor de la <xref:System.Windows.Forms.Control.Text%2A> propiedad **calendario**, **contactos**, y **tareas**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b1604-153">Set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to **Calendar**, **Contacts**, and **Tasks**, respectively.</span></span>

## <a name="handle-events"></a><span data-ttu-id="b1604-154">Controlar eventos</span><span class="sxs-lookup"><span data-stu-id="b1604-154">Handle events</span></span>

<span data-ttu-id="b1604-155">Dos eventos son importantes para realizar la `StackView` control se comporten correctamente.</span><span class="sxs-lookup"><span data-stu-id="b1604-155">Two events are important to make the `StackView` control behave correctly.</span></span> <span data-ttu-id="b1604-156">Controlar la <xref:System.Windows.Forms.UserControl.Load> eventos para colocar el control correctamente.</span><span class="sxs-lookup"><span data-stu-id="b1604-156">Handle the <xref:System.Windows.Forms.UserControl.Load> event to position the control correctly.</span></span> <span data-ttu-id="b1604-157">Controlar la <xref:System.Windows.Forms.ToolStripItem.Click> eventos para cada <xref:System.Windows.Forms.ToolStripButton> para dar el `StackView` controlan el comportamiento de estado similar a la <xref:System.Windows.Forms.RadioButton> control.</span><span class="sxs-lookup"><span data-stu-id="b1604-157">Handle the <xref:System.Windows.Forms.ToolStripItem.Click> event for each <xref:System.Windows.Forms.ToolStripButton> to give the `StackView` control state behavior similar to the <xref:System.Windows.Forms.RadioButton> control.</span></span>

1. <span data-ttu-id="b1604-158">En el Diseñador de Windows Forms, seleccione el `StackView` control.</span><span class="sxs-lookup"><span data-stu-id="b1604-158">In the Windows Forms Designer, select the `StackView` control.</span></span>

2. <span data-ttu-id="b1604-159">En la ventana **Propiedades**, haga clic en **Eventos**.</span><span class="sxs-lookup"><span data-stu-id="b1604-159">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="b1604-160">Haga doble clic en el evento Load para generar el `StackView_Load` controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="b1604-160">Double-click the Load event to generate the `StackView_Load` event handler.</span></span>

4. <span data-ttu-id="b1604-161">En el controlador de eventos `StackView_Load`, copie y pegue el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="b1604-161">In the `StackView_Load` event handler, copy and paste the following code.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]

5. <span data-ttu-id="b1604-162">En el Diseñador de Windows Forms, seleccione el `mailStackButton` control.</span><span class="sxs-lookup"><span data-stu-id="b1604-162">In the Windows Forms Designer, select the `mailStackButton` control.</span></span>

6. <span data-ttu-id="b1604-163">En la ventana **Propiedades**, haga clic en **Eventos**.</span><span class="sxs-lookup"><span data-stu-id="b1604-163">In the **Properties** window, click **Events**.</span></span>

7. <span data-ttu-id="b1604-164">Haga doble clic en el evento Click.</span><span class="sxs-lookup"><span data-stu-id="b1604-164">Double-click the Click event.</span></span>

     <span data-ttu-id="b1604-165">El Diseñador de formularios de Windows genera el `mailStackButton_Click` controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="b1604-165">The Windows Forms Designer generates the `mailStackButton_Click` event handler.</span></span>

8. <span data-ttu-id="b1604-166">Cambiar el nombre de la `mailStackButton_Click` controlador de eventos `stackButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="b1604-166">Rename the `mailStackButton_Click` event handler to `stackButton_Click`.</span></span>

     <span data-ttu-id="b1604-167">Para obtener más información, consulte [cambiar el nombre de una refactorización de código símbolos](/visualstudio/ide/reference/rename).</span><span class="sxs-lookup"><span data-stu-id="b1604-167">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

9. <span data-ttu-id="b1604-168">Inserte el código siguiente en el `stackButton_Click` controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="b1604-168">Insert the following code into the `stackButton_Click` event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]

10. <span data-ttu-id="b1604-169">En el Diseñador de Windows Forms, seleccione el `calendarStackButton` control.</span><span class="sxs-lookup"><span data-stu-id="b1604-169">In the Windows Forms Designer, select the `calendarStackButton` control.</span></span>

11. <span data-ttu-id="b1604-170">En el **propiedades** ventana, establezca el evento Click en la `stackButton_Click` controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="b1604-170">In the **Properties** window, set the Click event to the `stackButton_Click` event handler.</span></span>

12. <span data-ttu-id="b1604-171">Repita los pasos 10 y 11 para el `contactsStackButton` y `tasksStackButton` controles.</span><span class="sxs-lookup"><span data-stu-id="b1604-171">Repeat steps 10 and 11 for the `contactsStackButton` and `tasksStackButton` controls.</span></span>

## <a name="define-icons"></a><span data-ttu-id="b1604-172">Definir los iconos</span><span class="sxs-lookup"><span data-stu-id="b1604-172">Define icons</span></span>

<span data-ttu-id="b1604-173">Cada `StackView` botón tiene un icono asociado.</span><span class="sxs-lookup"><span data-stu-id="b1604-173">Each `StackView` button has an associated icon.</span></span> <span data-ttu-id="b1604-174">Para mayor comodidad, cada icono se representa como una cadena codificada en Base64, que se deserializa antes un <xref:System.Drawing.Bitmap> se crea a partir de él.</span><span class="sxs-lookup"><span data-stu-id="b1604-174">For convenience, each icon is represented as a Base64-encoded string, which is deserialized before a <xref:System.Drawing.Bitmap> is created from it.</span></span> <span data-ttu-id="b1604-175">En un entorno de producción, se almacenan los datos de mapa de bits como un recurso y sus iconos aparecen en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b1604-175">In a production environment, you store bitmap data as a resource, and your icons appear in the Windows Forms Designer.</span></span> <span data-ttu-id="b1604-176">Para obtener más información, vea [Cómo: Agregar imágenes de fondo a formularios Windows](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b1604-176">For more information, see [How to: Add Background Images to Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).</span></span>

1. <span data-ttu-id="b1604-177">En el Editor de código, inserte el código siguiente en el `StackView` definición de clase.</span><span class="sxs-lookup"><span data-stu-id="b1604-177">In the Code Editor, insert the following code into the `StackView` class definition.</span></span> <span data-ttu-id="b1604-178">Este código inicializa los mapas de bits para el <xref:System.Windows.Forms.ToolStripButton> iconos.</span><span class="sxs-lookup"><span data-stu-id="b1604-178">This code initializes the bitmaps for the <xref:System.Windows.Forms.ToolStripButton> icons.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]

2. <span data-ttu-id="b1604-179">Agregue una llamada a la `InitializeImages` método en el `StackView` constructor de clase.</span><span class="sxs-lookup"><span data-stu-id="b1604-179">Add a call to the `InitializeImages` method in the `StackView` class constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="implement-a-custom-renderer"></a><span data-ttu-id="b1604-180">Implementar a un representador personalizado</span><span class="sxs-lookup"><span data-stu-id="b1604-180">Implement a custom renderer</span></span>

<span data-ttu-id="b1604-181">Puede personalizar la mayoría de los elementos de la `StackView` controlar implementando una clase que deriva la <xref:System.Windows.Forms.ToolStripRenderer> clase.</span><span class="sxs-lookup"><span data-stu-id="b1604-181">You can customize most elements of the `StackView` control my implementing a class that derives from the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="b1604-182">En este procedimiento, implementará un <xref:System.Windows.Forms.ToolStripProfessionalRenderer> clase que personaliza el control y dibuja los fondos de degradado para el <xref:System.Windows.Forms.ToolStripButton> controles.</span><span class="sxs-lookup"><span data-stu-id="b1604-182">In this procedure, you will implement a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class that customizes the grip and draws gradient backgrounds for the <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>

1. <span data-ttu-id="b1604-183">Inserte el código siguiente en el `StackView` controlar la definición.</span><span class="sxs-lookup"><span data-stu-id="b1604-183">Insert the following code into the `StackView` control definition.</span></span>

     <span data-ttu-id="b1604-184">Se trata de la definición de la `StackRenderer` clase, lo que invalida el <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, y <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> métodos para producir una apariencia personalizada.</span><span class="sxs-lookup"><span data-stu-id="b1604-184">This is the definition for the `StackRenderer` class, which overrides the <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, and <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> methods to produce a custom appearance.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]

2. <span data-ttu-id="b1604-185">En el `StackView` constructor del control, cree una nueva instancia de la `StackRenderer` clase y asignar esta instancia con el `stackStrip` del control <xref:System.Windows.Forms.ToolStrip.Renderer%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="b1604-185">In the `StackView` control's constructor, create a new instance of the `StackRenderer` class and assign this instance to the `stackStrip` control's <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="test-the-stackview-control"></a><span data-ttu-id="b1604-186">Probar el control StackView</span><span class="sxs-lookup"><span data-stu-id="b1604-186">Test the StackView control</span></span>

<span data-ttu-id="b1604-187">El `StackView` control se deriva de la <xref:System.Windows.Forms.UserControl> clase.</span><span class="sxs-lookup"><span data-stu-id="b1604-187">The `StackView` control derives from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="b1604-188">Por lo tanto, puede probar el control con el **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="b1604-188">Therefore, you can test the control with the **UserControl Test Container**.</span></span> <span data-ttu-id="b1604-189">Para obtener más información, vea [Cómo: Probar el comportamiento de tiempo de ejecución de una clase UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="b1604-189">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

1. <span data-ttu-id="b1604-190">Presione **F5** para compilar el proyecto e iniciar el **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="b1604-190">Press **F5** to build the project and start the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="b1604-191">Mueva el puntero sobre los botones de la `StackView` controlar y, a continuación, haga clic en un botón para ver el aspecto de su estado seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b1604-191">Move the pointer over the buttons of the `StackView` control, and then click a button to see the appearance of its selected state.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b1604-192">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b1604-192">Next steps</span></span>

<span data-ttu-id="b1604-193">En este tutorial, ha creado un control de cliente personalizado reutilizable con el aspecto de un control de Office XP professional.</span><span class="sxs-lookup"><span data-stu-id="b1604-193">In this walkthrough, you have created a reusable custom client control with the professional appearance of an Office XP control.</span></span> <span data-ttu-id="b1604-194">Puede usar el <xref:System.Windows.Forms.ToolStrip> familia de controles para muchos otros objetivos:</span><span class="sxs-lookup"><span data-stu-id="b1604-194">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="b1604-195">Crear menús contextuales para los controles con <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="b1604-195">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="b1604-196">Para obtener más información, consulte [información general del componente ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b1604-196">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="b1604-197">Crear un formulario con un menú estándar rellenado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b1604-197">Create a form with an automatically populated standard menu.</span></span> <span data-ttu-id="b1604-198">Para obtener más información, vea [Tutorial: Proporcionar elementos de menú estándar a un formulario](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="b1604-198">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="b1604-199">Crear un formulario de múltiples documentos (MDI) de la interfaz con acoplamiento <xref:System.Windows.Forms.ToolStrip> controles.</span><span class="sxs-lookup"><span data-stu-id="b1604-199">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="b1604-200">Para obtener más información, vea [Cómo: Crear un formulario MDI con combinación de menús y controles ToolStrip](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="b1604-200">For more information, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b1604-201">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1604-201">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="b1604-202">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="b1604-202">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="b1604-203">Cómo: Proporcionar elementos de menú estándar a un formulario</span><span class="sxs-lookup"><span data-stu-id="b1604-203">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
