---
title: Procedimiento para comprobar el comportamiento de UserControl en tiempo de ejecución
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 110036e5031a2956375b1edf0689237661522d39
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180206"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="63417-102">Procedimiento Probar el comportamiento en tiempo de ejecución de un control UserControl</span><span class="sxs-lookup"><span data-stu-id="63417-102">How to: Test the run-time behavior of a UserControl</span></span>

<span data-ttu-id="63417-103">Al desarrollar un <xref:System.Windows.Forms.UserControl>, debe probar su comportamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="63417-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="63417-104">Puede crear un proyecto de aplicación basado en Windows independiente y colocar el control en un formulario de prueba, pero este procedimiento no es práctico.</span><span class="sxs-lookup"><span data-stu-id="63417-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="63417-105">Una manera más rápida y sencilla es usar el **contenedor de pruebas de UserControl** que proporciona Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="63417-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="63417-106">Este contenedor de prueba se inicia directamente desde el proyecto de biblioteca de controles de Windows.</span><span class="sxs-lookup"><span data-stu-id="63417-106">This test container starts directly from your Windows control library project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="63417-107">Para que el contenedor de prueba cargue el <xref:System.Windows.Forms.UserControl>, el control debe tener al menos un constructor público.</span><span class="sxs-lookup"><span data-stu-id="63417-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="63417-108">No se C++ puede probar un control visual mediante **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="63417-108">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="63417-109">Probar el comportamiento en tiempo de ejecución de un control UserControl</span><span class="sxs-lookup"><span data-stu-id="63417-109">Test the run-time behavior of a UserControl</span></span>

1. <span data-ttu-id="63417-110">En Visual Studio, cree un proyecto de biblioteca de controles de Windows y asígnele el nombre **TestContainerExample**.</span><span class="sxs-lookup"><span data-stu-id="63417-110">In Visual Studio, create a Windows control library project, and name it **TestContainerExample**.</span></span>

2. <span data-ttu-id="63417-111">En el **Diseñador de Windows Forms**, arrastre un control <xref:System.Windows.Forms.Label> desde el **cuadro de herramientas** hasta la superficie de diseño del control.</span><span class="sxs-lookup"><span data-stu-id="63417-111">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="63417-112">Presione <kbd>F5</kbd> para compilar el proyecto y ejecutar **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="63417-112">Press <kbd>F5</kbd> to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="63417-113">El contenedor de prueba aparece con el <xref:System.Windows.Forms.UserControl> en el panel de **vista previa** .</span><span class="sxs-lookup"><span data-stu-id="63417-113">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="63417-114">Seleccione la propiedad <xref:System.Windows.Forms.Control.BackColor%2A> que se muestra en el control <xref:System.Windows.Forms.PropertyGrid> a la derecha del panel de **vista previa** .</span><span class="sxs-lookup"><span data-stu-id="63417-114">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="63417-115">Cambie su valor a **ControlDark**.</span><span class="sxs-lookup"><span data-stu-id="63417-115">Change its value to **ControlDark**.</span></span> <span data-ttu-id="63417-116">Observe que el control cambia a un color más oscuro.</span><span class="sxs-lookup"><span data-stu-id="63417-116">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="63417-117">Intente cambiar otros valores de propiedad y observe el efecto en el control.</span><span class="sxs-lookup"><span data-stu-id="63417-117">Try changing other property values and observe the effect on your control.</span></span>

5. <span data-ttu-id="63417-118">En el panel de **vista previa** , haga clic en la casilla **control de usuario acoplar relleno** .</span><span class="sxs-lookup"><span data-stu-id="63417-118">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="63417-119">Observe que el control cambia de tamaño para rellenar el panel.</span><span class="sxs-lookup"><span data-stu-id="63417-119">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="63417-120">Cambie el tamaño del contenedor de pruebas y observe que se cambia el tamaño del control con el panel.</span><span class="sxs-lookup"><span data-stu-id="63417-120">Resize the test container and observe that the control is resized with the pane.</span></span>

6. <span data-ttu-id="63417-121">Cierre el contenedor de prueba.</span><span class="sxs-lookup"><span data-stu-id="63417-121">Close the test container.</span></span>

7. <span data-ttu-id="63417-122">Agregue otro control de usuario al proyecto **TestContainerExample** .</span><span class="sxs-lookup"><span data-stu-id="63417-122">Add another user control to the **TestContainerExample** project.</span></span>

8. <span data-ttu-id="63417-123">En el **Diseñador de Windows Forms**, arrastre un control <xref:System.Windows.Forms.Button> desde el **cuadro de herramientas** hasta la superficie de diseño del control.</span><span class="sxs-lookup"><span data-stu-id="63417-123">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>

9. <span data-ttu-id="63417-124">Presione <kbd>F5</kbd> para compilar el proyecto y ejecutar el contenedor de prueba.</span><span class="sxs-lookup"><span data-stu-id="63417-124">Press <kbd>F5</kbd> to build the project and run the test container.</span></span>

10. <span data-ttu-id="63417-125">Haga clic en **seleccionar control de usuario** <xref:System.Windows.Forms.ComboBox> para cambiar entre los dos controles de usuario.</span><span class="sxs-lookup"><span data-stu-id="63417-125">Click the **Select User Control** <xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>

## <a name="test-user-controls-from-another-project"></a><span data-ttu-id="63417-126">Probar controles de usuario desde otro proyecto</span><span class="sxs-lookup"><span data-stu-id="63417-126">Test user controls from another project</span></span>

<span data-ttu-id="63417-127">Puede probar los controles de usuario de otros proyectos en el contenedor de pruebas del proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="63417-127">You can test user controls from other projects in your current project's test container.</span></span>

1. <span data-ttu-id="63417-128">En Visual Studio, cree un proyecto de biblioteca de controles de Windows y asígnele el nombre **TestContainerExample2**.</span><span class="sxs-lookup"><span data-stu-id="63417-128">In Visual Studio, create a Windows control library project, and name it **TestContainerExample2**.</span></span>

2. <span data-ttu-id="63417-129">En el **Diseñador de Windows Forms**, arrastre un control <xref:System.Windows.Forms.RadioButton> desde el **cuadro de herramientas** hasta la superficie de diseño del control.</span><span class="sxs-lookup"><span data-stu-id="63417-129">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="63417-130">Presione <kbd>F5</kbd> para compilar el proyecto y ejecutar el contenedor de prueba.</span><span class="sxs-lookup"><span data-stu-id="63417-130">Press <kbd>F5</kbd> to build the project and run the test container.</span></span> <span data-ttu-id="63417-131">El contenedor de prueba aparece con el <xref:System.Windows.Forms.UserControl> en el panel de **vista previa** .</span><span class="sxs-lookup"><span data-stu-id="63417-131">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="63417-132">Haga clic en el botón **cargar** .</span><span class="sxs-lookup"><span data-stu-id="63417-132">Click the **Load** button.</span></span>

5. <span data-ttu-id="63417-133">En el cuadro de diálogo **abrir** , vaya a *TestContainerExample. dll*, que creó en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="63417-133">In the **Open** dialog box, navigate to *TestContainerExample.dll*, which you built in the previous procedure.</span></span> <span data-ttu-id="63417-134">Seleccione *TestContainerExample. dll* y haga clic en el botón **abrir** para cargar los controles de usuario.</span><span class="sxs-lookup"><span data-stu-id="63417-134">Select *TestContainerExample.dll* and click the **Open** button to load the user controls.</span></span>

6. <span data-ttu-id="63417-135">Use el **control de usuario Select** <xref:System.Windows.Forms.ComboBox> para cambiar entre los dos controles de usuario del proyecto **TestContainerExample** .</span><span class="sxs-lookup"><span data-stu-id="63417-135">Use the **Select User Control** <xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>

## <a name="see-also"></a><span data-ttu-id="63417-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="63417-136">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- <span data-ttu-id="63417-137">[Cómo: Crear controles compuestos @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="63417-137">[How to: Author Composite Controls](how-to-author-composite-controls.md)</span></span>
- <span data-ttu-id="63417-138">[Tutorial: Crear un control compuesto @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="63417-138">[Walkthrough: Authoring a Composite Control](walkthrough-authoring-a-composite-control-with-visual-csharp.md)</span></span>
- <span data-ttu-id="63417-139">[Diseñador de controles de usuario](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="63417-139">[User Control Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span></span>
