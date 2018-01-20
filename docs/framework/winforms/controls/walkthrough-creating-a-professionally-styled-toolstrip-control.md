---
title: 'Tutorial: Crear un control ToolStrip de estilo profesional'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ab9adb72a174da25298b6ea104b002914de0cc40
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="37248-102">Tutorial: Crear un control ToolStrip de estilo profesional</span><span class="sxs-lookup"><span data-stu-id="37248-102">Walkthrough: Creating a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="37248-103">Puede permitir que la aplicación <xref:System.Windows.Forms.ToolStrip> controla un aspecto y comportamiento profesional escribiendo su propia clase derivada de la <xref:System.Windows.Forms.ToolStripProfessionalRenderer> tipo.</span><span class="sxs-lookup"><span data-stu-id="37248-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="37248-104">Este tutorial muestra cómo usar <xref:System.Windows.Forms.ToolStrip> controles para crear un control compuesto que se parezca a la **panel de navegación** proporcionado por Microsoft® Outlook®.</span><span class="sxs-lookup"><span data-stu-id="37248-104">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that resembles the **Navigation Pane** provided by Microsoft® Outlook®.</span></span> <span data-ttu-id="37248-105">En este tutorial se muestran las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="37248-105">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="37248-106">Crear un proyecto de biblioteca de controles de Windows.</span><span class="sxs-lookup"><span data-stu-id="37248-106">Creating a Windows Control Library project.</span></span>  
  
-   <span data-ttu-id="37248-107">Diseñar el Control StackView.</span><span class="sxs-lookup"><span data-stu-id="37248-107">Designing the StackView Control.</span></span>  
  
-   <span data-ttu-id="37248-108">Implementar a un representador personalizado.</span><span class="sxs-lookup"><span data-stu-id="37248-108">Implementing a Custom Renderer.</span></span>  
  
 <span data-ttu-id="37248-109">Cuando haya terminado, tendrá un control de cliente personalizado reutilizable con el aspecto de un control de Microsoft Office® XP professional.</span><span class="sxs-lookup"><span data-stu-id="37248-109">When you are finished, you will have a reusable custom client control with the professional appearance of a Microsoft Office® XP control.</span></span>  
  
 <span data-ttu-id="37248-110">Para copiar el código de este tema como una sola lista, vea [Cómo: crear un profesional ToolStrip Control de estilo](../../../../docs/framework/winforms/controls/how-to-create-a-professionally-styled-toolstrip-control.md).</span><span class="sxs-lookup"><span data-stu-id="37248-110">To copy the code in this topic as a single listing, see [How to: Create a Professionally Styled ToolStrip Control](../../../../docs/framework/winforms/controls/how-to-create-a-professionally-styled-toolstrip-control.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37248-111">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="37248-111">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="37248-112">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="37248-112">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="37248-113">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="37248-113">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="37248-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="37248-114">Prerequisites</span></span>  
 <span data-ttu-id="37248-115">Para poder completar este tutorial, necesitará:</span><span class="sxs-lookup"><span data-stu-id="37248-115">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="37248-116">Los permisos necesarios para poder crear y ejecutar proyectos de aplicación de Windows Forms en el equipo donde [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] está instalado.</span><span class="sxs-lookup"><span data-stu-id="37248-116">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] is installed.</span></span>  
  
## <a name="creating-a-windows-control-library-project"></a><span data-ttu-id="37248-117">Crear un proyecto de biblioteca de controles de Windows</span><span class="sxs-lookup"><span data-stu-id="37248-117">Creating a Windows Control Library Project</span></span>  
 <span data-ttu-id="37248-118">El primer paso es crear el proyecto de biblioteca de controles.</span><span class="sxs-lookup"><span data-stu-id="37248-118">The first step is to create the control library project.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="37248-119">Para crear el proyecto de biblioteca de controles</span><span class="sxs-lookup"><span data-stu-id="37248-119">To create the control library project</span></span>  
  
1.  <span data-ttu-id="37248-120">Crear un nuevo proyecto de biblioteca de controles de Windows denominado `StackViewLibrary`.</span><span class="sxs-lookup"><span data-stu-id="37248-120">Create a new Windows Control Library project named `StackViewLibrary`.</span></span>  
  
2.  <span data-ttu-id="37248-121">En **el Explorador de soluciones**, elimine el control predeterminado del proyecto eliminando el archivo de código fuente denominado "UserControl1.cs" o "UserControl1.vb", dependiendo del lenguaje elegido.</span><span class="sxs-lookup"><span data-stu-id="37248-121">In **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>  
  
     <span data-ttu-id="37248-122">Para obtener más información, consulte [NIB: Cómo: quitar, eliminar y excluir elementos](http://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span><span class="sxs-lookup"><span data-stu-id="37248-122">For more information, see [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span></span>  
  
3.  <span data-ttu-id="37248-123">Agregue un nuevo <xref:System.Windows.Forms.UserControl> elemento a la **StackViewLibrary** proyecto.</span><span class="sxs-lookup"><span data-stu-id="37248-123">Add a new <xref:System.Windows.Forms.UserControl> item to the **StackViewLibrary** project.</span></span> <span data-ttu-id="37248-124">Asigne al archivo de origen nuevo un nombre de base de `StackView`.</span><span class="sxs-lookup"><span data-stu-id="37248-124">Give the new source file a base name of `StackView`.</span></span>  
  
## <a name="designing-the-stackview-control"></a><span data-ttu-id="37248-125">Diseñar el Control StackView</span><span class="sxs-lookup"><span data-stu-id="37248-125">Designing the StackView Control</span></span>  
 <span data-ttu-id="37248-126">El `StackView` control es un control compuesto con un elemento secundario <xref:System.Windows.Forms.ToolStrip> control.</span><span class="sxs-lookup"><span data-stu-id="37248-126">The `StackView` control is a composite control with one child <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="37248-127">Para obtener más información sobre los controles compuestos, vea [variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="37248-127">For more information about composite controls, see [Varieties of Custom Controls](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md).</span></span>  
  
#### <a name="to-design-the-stackview-control"></a><span data-ttu-id="37248-128">Para diseñar el control StackView</span><span class="sxs-lookup"><span data-stu-id="37248-128">To design the StackView control</span></span>  
  
1.  <span data-ttu-id="37248-129">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.ToolStrip> control a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="37248-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStrip> control to the design surface.</span></span>  
  
2.  <span data-ttu-id="37248-130">En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.ToolStrip> propiedades del control según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="37248-130">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStrip> control's properties according to the following table.</span></span>  
  
    |<span data-ttu-id="37248-131">Property</span><span class="sxs-lookup"><span data-stu-id="37248-131">Property</span></span>|<span data-ttu-id="37248-132">Valor</span><span class="sxs-lookup"><span data-stu-id="37248-132">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="37248-133">nombre</span><span class="sxs-lookup"><span data-stu-id="37248-133">Name</span></span>|`stackStrip`|  
    |<span data-ttu-id="37248-134">CanOverflow</span><span class="sxs-lookup"><span data-stu-id="37248-134">CanOverflow</span></span>|`false`|  
    |<span data-ttu-id="37248-135">Acoplar</span><span class="sxs-lookup"><span data-stu-id="37248-135">Dock</span></span>|<xref:System.Windows.Forms.DockStyle.Bottom>|  
    |<span data-ttu-id="37248-136">Tipo de letra</span><span class="sxs-lookup"><span data-stu-id="37248-136">Font</span></span>|`Tahoma, 10pt, style=Bold`|  
    |<span data-ttu-id="37248-137">GripStyle</span><span class="sxs-lookup"><span data-stu-id="37248-137">GripStyle</span></span>|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|  
    |<span data-ttu-id="37248-138">LayoutStyle</span><span class="sxs-lookup"><span data-stu-id="37248-138">LayoutStyle</span></span>|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|  
    |<span data-ttu-id="37248-139">Relleno</span><span class="sxs-lookup"><span data-stu-id="37248-139">Padding</span></span>|`0, 7, 0, 0`|  
    |<span data-ttu-id="37248-140">RenderMode</span><span class="sxs-lookup"><span data-stu-id="37248-140">RenderMode</span></span>|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|  
  
3.  <span data-ttu-id="37248-141">En el Diseñador de Windows Forms, haga clic en el <xref:System.Windows.Forms.ToolStrip> del control **agregar** botón y agregue un <xref:System.Windows.Forms.ToolStripButton> a la `stackStrip` control.</span><span class="sxs-lookup"><span data-stu-id="37248-141">In the Windows Forms Designer, click the <xref:System.Windows.Forms.ToolStrip> control's **Add** button and add a <xref:System.Windows.Forms.ToolStripButton> to the `stackStrip` control.</span></span>  
  
4.  <span data-ttu-id="37248-142">En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.ToolStripButton> propiedades del control según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="37248-142">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStripButton> control's properties according to the following table.</span></span>  
  
    |<span data-ttu-id="37248-143">Property</span><span class="sxs-lookup"><span data-stu-id="37248-143">Property</span></span>|<span data-ttu-id="37248-144">Valor</span><span class="sxs-lookup"><span data-stu-id="37248-144">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="37248-145">nombre</span><span class="sxs-lookup"><span data-stu-id="37248-145">Name</span></span>|`mailStackButton`|  
    |<span data-ttu-id="37248-146">CheckOnClick</span><span class="sxs-lookup"><span data-stu-id="37248-146">CheckOnClick</span></span>|<span data-ttu-id="37248-147">true</span><span class="sxs-lookup"><span data-stu-id="37248-147">true</span></span>|  
    |<span data-ttu-id="37248-148">CheckState</span><span class="sxs-lookup"><span data-stu-id="37248-148">CheckState</span></span>|<xref:System.Windows.Forms.CheckState.Checked>|  
    |<span data-ttu-id="37248-149">DisplayStyle</span><span class="sxs-lookup"><span data-stu-id="37248-149">DisplayStyle</span></span>|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|  
    |<span data-ttu-id="37248-150">ImageAlign</span><span class="sxs-lookup"><span data-stu-id="37248-150">ImageAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
    |<span data-ttu-id="37248-151">ImageScaling</span><span class="sxs-lookup"><span data-stu-id="37248-151">ImageScaling</span></span>|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|  
    |<span data-ttu-id="37248-152">ImageTransparentColor</span><span class="sxs-lookup"><span data-stu-id="37248-152">ImageTransparentColor</span></span>|`238, 238, 238`|  
    |<span data-ttu-id="37248-153">Margin</span><span class="sxs-lookup"><span data-stu-id="37248-153">Margin</span></span>|`0, 0, 0, 0`|  
    |<span data-ttu-id="37248-154">Relleno</span><span class="sxs-lookup"><span data-stu-id="37248-154">Padding</span></span>|`3, 3, 3, 3`|  
    |<span data-ttu-id="37248-155">Texto</span><span class="sxs-lookup"><span data-stu-id="37248-155">Text</span></span>|<span data-ttu-id="37248-156">**Mail**</span><span class="sxs-lookup"><span data-stu-id="37248-156">**Mail**</span></span>|  
    |<span data-ttu-id="37248-157">TextAlign</span><span class="sxs-lookup"><span data-stu-id="37248-157">TextAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
  
5.  <span data-ttu-id="37248-158">Repita el paso 7 para tres más <xref:System.Windows.Forms.ToolStripButton> controles.</span><span class="sxs-lookup"><span data-stu-id="37248-158">Repeat step 7 for three more <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>  
  
     <span data-ttu-id="37248-159">El nombre de los controles `calendarStackButton`, `contactsStackButton`, y `tasksStackButton`.</span><span class="sxs-lookup"><span data-stu-id="37248-159">Name the controls `calendarStackButton`, `contactsStackButton`, and `tasksStackButton`.</span></span> <span data-ttu-id="37248-160">Establezca el valor de la <xref:System.Windows.Forms.Control.Text%2A> propiedad **calendario**, **contactos**, y **tareas**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="37248-160">Set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to **Calendar**, **Contacts**, and **Tasks**, respectively.</span></span>  
  
## <a name="handling-events"></a><span data-ttu-id="37248-161">Controlar eventos</span><span class="sxs-lookup"><span data-stu-id="37248-161">Handling Events</span></span>  
 <span data-ttu-id="37248-162">Dos eventos son importantes para hacer el `StackView` control se comporten correctamente.</span><span class="sxs-lookup"><span data-stu-id="37248-162">Two events are important to make the `StackView` control behave correctly.</span></span> <span data-ttu-id="37248-163">Controlar la <xref:System.Windows.Forms.UserControl.Load> eventos para colocar el control correctamente.</span><span class="sxs-lookup"><span data-stu-id="37248-163">Handle the <xref:System.Windows.Forms.UserControl.Load> event to position the control correctly.</span></span> <span data-ttu-id="37248-164">Controlar la <xref:System.Windows.Forms.ToolStripItem.Click> eventos para cada <xref:System.Windows.Forms.ToolStripButton> para dar el `StackView` controlan el comportamiento de estado similar a la <xref:System.Windows.Forms.RadioButton> control.</span><span class="sxs-lookup"><span data-stu-id="37248-164">Handle the <xref:System.Windows.Forms.ToolStripItem.Click> event for each <xref:System.Windows.Forms.ToolStripButton> to give the `StackView` control state behavior similar to the <xref:System.Windows.Forms.RadioButton> control.</span></span>  
  
#### <a name="to-handle-events"></a><span data-ttu-id="37248-165">Para controlar eventos</span><span class="sxs-lookup"><span data-stu-id="37248-165">To handle events</span></span>  
  
1.  <span data-ttu-id="37248-166">En el Diseñador de Windows Forms, seleccione el `StackView` control.</span><span class="sxs-lookup"><span data-stu-id="37248-166">In the Windows Forms Designer, select the `StackView` control.</span></span>  
  
2.  <span data-ttu-id="37248-167">En el **propiedades** ventana, haga clic en **eventos**.</span><span class="sxs-lookup"><span data-stu-id="37248-167">In the **Properties** window, click **Events**.</span></span>  
  
3.  <span data-ttu-id="37248-168">Haga doble clic en el evento Load para generar el `StackView_Load` controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="37248-168">Double-click the Load event to generate the `StackView_Load` event handler.</span></span>  
  
4.  <span data-ttu-id="37248-169">En el controlador de eventos `StackView_Load`, copie y pegue el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="37248-169">In the `StackView_Load` event handler, copy and paste the following code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]  
  
5.  <span data-ttu-id="37248-170">En el Diseñador de Windows Forms, seleccione el `mailStackButton` control.</span><span class="sxs-lookup"><span data-stu-id="37248-170">In the Windows Forms Designer, select the `mailStackButton` control.</span></span>  
  
6.  <span data-ttu-id="37248-171">En el **propiedades** ventana, haga clic en **eventos**.</span><span class="sxs-lookup"><span data-stu-id="37248-171">In the **Properties** window, click **Events**.</span></span>  
  
7.  <span data-ttu-id="37248-172">Haga doble clic en el evento de clic.</span><span class="sxs-lookup"><span data-stu-id="37248-172">Double-click the Click event.</span></span>  
  
     <span data-ttu-id="37248-173">El Diseñador de Windows Forms genera el `mailStackButton_Click` controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="37248-173">The Windows Forms Designer generates the `mailStackButton_Click` event handler.</span></span>  
  
8.  <span data-ttu-id="37248-174">Cambiar el nombre de la `mailStackButton_Click` controlador de eventos para `stackButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="37248-174">Rename the `mailStackButton_Click` event handler to `stackButton_Click`.</span></span>  
  
     <span data-ttu-id="37248-175">Para obtener más información, consulte [Cómo: cambiar el nombre de un identificador (Visual Basic)](http://msdn.microsoft.com/library/e5a5edf8-3dba-4119-81f4-fc2aba180e0c).</span><span class="sxs-lookup"><span data-stu-id="37248-175">For more information, see [How to: Rename an Identifier (Visual Basic)](http://msdn.microsoft.com/library/e5a5edf8-3dba-4119-81f4-fc2aba180e0c).</span></span>  
  
9. <span data-ttu-id="37248-176">Inserte el siguiente código en el `stackButton_Click` controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="37248-176">Insert the following code into the `stackButton_Click` event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]  
  
10. <span data-ttu-id="37248-177">En el Diseñador de Windows Forms, seleccione el `calendarStackButton` control.</span><span class="sxs-lookup"><span data-stu-id="37248-177">In the Windows Forms Designer, select the `calendarStackButton` control.</span></span>  
  
11. <span data-ttu-id="37248-178">En el **propiedades** ventana, establezca el evento Click en la `stackButton_Click` controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="37248-178">In the **Properties** window, set the Click event to the `stackButton_Click` event handler.</span></span>  
  
12. <span data-ttu-id="37248-179">Repita los pasos 10 y 11 para el `contactsStackButton` y `tasksStackButton` controles.</span><span class="sxs-lookup"><span data-stu-id="37248-179">Repeat steps 10 and 11 for the `contactsStackButton` and `tasksStackButton` controls.</span></span>  
  
## <a name="defining-icons"></a><span data-ttu-id="37248-180">Definición de iconos</span><span class="sxs-lookup"><span data-stu-id="37248-180">Defining Icons</span></span>  
 <span data-ttu-id="37248-181">Cada `StackView` botón tiene un icono asociado.</span><span class="sxs-lookup"><span data-stu-id="37248-181">Each `StackView` button has an associated icon.</span></span> <span data-ttu-id="37248-182">Para mayor comodidad, cada icono se representa como una cadena codificada en Base64, que se deserializa antes un <xref:System.Drawing.Bitmap> creada a partir de él.</span><span class="sxs-lookup"><span data-stu-id="37248-182">For convenience, each icon is represented as a Base64-encoded string, which is deserialized before a <xref:System.Drawing.Bitmap> is created from it.</span></span> <span data-ttu-id="37248-183">En un entorno de producción, almacenar datos de mapa de bits como un recurso y sus iconos aparecen en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="37248-183">In a production environment, you store bitmap data as a resource, and your icons appear in the Windows Forms Designer.</span></span> <span data-ttu-id="37248-184">Para obtener más información, consulte [Cómo: agregar imágenes de fondo a formularios Windows Forms](http://msdn.microsoft.com/library/7a509ba2-055c-4ae6-b88a-54625c6d9aff).</span><span class="sxs-lookup"><span data-stu-id="37248-184">For more information, see [How to: Add Background Images to Windows Forms](http://msdn.microsoft.com/library/7a509ba2-055c-4ae6-b88a-54625c6d9aff).</span></span>  
  
#### <a name="to-define-icons"></a><span data-ttu-id="37248-185">Para definir los iconos</span><span class="sxs-lookup"><span data-stu-id="37248-185">To define icons</span></span>  
  
1.  <span data-ttu-id="37248-186">En el Editor de código, inserte el código siguiente en el `StackView` definición de clase.</span><span class="sxs-lookup"><span data-stu-id="37248-186">In the Code Editor, insert the following code into the `StackView` class definition.</span></span> <span data-ttu-id="37248-187">Este código inicializa los mapas de bits para el <xref:System.Windows.Forms.ToolStripButton> iconos.</span><span class="sxs-lookup"><span data-stu-id="37248-187">This code initializes the bitmaps for the <xref:System.Windows.Forms.ToolStripButton> icons.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]  
  
2.  <span data-ttu-id="37248-188">Agregue una llamada a la `InitializeImages` método en el `StackView` constructor de clase.</span><span class="sxs-lookup"><span data-stu-id="37248-188">Add a call to the `InitializeImages` method in the `StackView` class constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="implementing-a-custom-renderer"></a><span data-ttu-id="37248-189">Implementar a un representador personalizado</span><span class="sxs-lookup"><span data-stu-id="37248-189">Implementing a Custom Renderer</span></span>  
 <span data-ttu-id="37248-190">Puede personalizar la mayoría de los elementos de la `StackView` controlar implementando una clase que deriva de la <xref:System.Windows.Forms.ToolStripRenderer> clase.</span><span class="sxs-lookup"><span data-stu-id="37248-190">You can customize most elements of the `StackView` control my implementing a class that derives from the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="37248-191">En este procedimiento, implementará un <xref:System.Windows.Forms.ToolStripProfessionalRenderer> clase que personaliza el control y dibuja los fondos del degradado de la <xref:System.Windows.Forms.ToolStripButton> controles.</span><span class="sxs-lookup"><span data-stu-id="37248-191">In this procedure, you will implement a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class that customizes the grip and draws gradient backgrounds for the <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>  
  
#### <a name="to-implement-a-custom-renderer"></a><span data-ttu-id="37248-192">Para implementar a un representador personalizado</span><span class="sxs-lookup"><span data-stu-id="37248-192">To implement a custom renderer</span></span>  
  
1.  <span data-ttu-id="37248-193">Inserte el siguiente código en el `StackView` controlar definición.</span><span class="sxs-lookup"><span data-stu-id="37248-193">Insert the following code into the `StackView` control definition.</span></span>  
  
     <span data-ttu-id="37248-194">Se trata de la definición de la `StackRenderer` de la clase, lo que invalida el <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, y <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> métodos para generar un aspecto personalizado.</span><span class="sxs-lookup"><span data-stu-id="37248-194">This is the definition for the `StackRenderer` class, which overrides the <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, and <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> methods to produce a custom appearance.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]  
  
2.  <span data-ttu-id="37248-195">En el `StackView` constructor del control, cree una nueva instancia de la `StackRenderer` clase y asigne esta instancia a la `stackStrip` del control <xref:System.Windows.Forms.ToolStrip.Renderer%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="37248-195">In the `StackView` control's constructor, create a new instance of the `StackRenderer` class and assign this instance to the `stackStrip` control's <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="testing-the-stackview-control"></a><span data-ttu-id="37248-196">Probar el Control StackView</span><span class="sxs-lookup"><span data-stu-id="37248-196">Testing the StackView Control</span></span>  
 <span data-ttu-id="37248-197">El `StackView` control se deriva de la <xref:System.Windows.Forms.UserControl> clase.</span><span class="sxs-lookup"><span data-stu-id="37248-197">The `StackView` control derives from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="37248-198">Por lo tanto, puede probar el control con el **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="37248-198">Therefore, you can test the control with the **UserControl Test Container**.</span></span> <span data-ttu-id="37248-199">Para más información, consulte [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="37248-199">For more information, see [How to: Test the Run-Time Behavior of a UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
#### <a name="to-test-the-stackview-control"></a><span data-ttu-id="37248-200">Para probar el control StackView</span><span class="sxs-lookup"><span data-stu-id="37248-200">To test the StackView control</span></span>  
  
1.  <span data-ttu-id="37248-201">Presione F5 para compilar el proyecto e iniciar la **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="37248-201">Press F5 to build the project and start the **UserControl Test Container**.</span></span>  
  
2.  <span data-ttu-id="37248-202">Mueva el puntero sobre los botones de la `StackView` de control y, a continuación, haga clic en un botón para ver el aspecto de su estado seleccionado.</span><span class="sxs-lookup"><span data-stu-id="37248-202">Move the pointer over the buttons of the `StackView` control, and then click a button to see the appearance of its selected state.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="37248-203">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="37248-203">Next Steps</span></span>  
 <span data-ttu-id="37248-204">En este tutorial, ha creado un control de cliente personalizado reutilizable con el aspecto profesional de un control de Office XP.</span><span class="sxs-lookup"><span data-stu-id="37248-204">In this walkthrough, you have created a reusable custom client control with the professional appearance of an Office XP control.</span></span> <span data-ttu-id="37248-205">Puede usar el <xref:System.Windows.Forms.ToolStrip> familia de controles para muchos otros objetivos:</span><span class="sxs-lookup"><span data-stu-id="37248-205">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="37248-206">Crear menús contextuales para los controles con <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="37248-206">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="37248-207">Para obtener más información, consulte [información general del componente ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="37248-207">For more information, see [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="37248-208">Crear un formulario con un menú estándar rellenado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="37248-208">Create a form with an automatically populated standard menu.</span></span> <span data-ttu-id="37248-209">Para obtener más información, consulte [Tutorial: proporcionar elementos de menú estándar a un formulario](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="37248-209">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
-   <span data-ttu-id="37248-210">Crear un formulario de múltiples documentos (MDI) de la interfaz con acoplamiento <xref:System.Windows.Forms.ToolStrip> controles.</span><span class="sxs-lookup"><span data-stu-id="37248-210">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="37248-211">Para obtener más información, consulte [Cómo: crear un formulario MDI con combinación de menús y controles ToolStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="37248-211">For more information, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37248-212">Vea también</span><span class="sxs-lookup"><span data-stu-id="37248-212">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="37248-213">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="37248-213">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [<span data-ttu-id="37248-214">Cómo: Proporcionar elementos de menú estándar a un formulario</span><span class="sxs-lookup"><span data-stu-id="37248-214">How to: Provide Standard Menu Items to a Form</span></span>](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)
