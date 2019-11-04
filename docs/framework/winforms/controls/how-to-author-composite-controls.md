---
title: 'Cómo: Crear controles compuestos'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], creating composite controls
- user controls [Windows Forms], creating
- user controls [Windows Forms], inheriting from
- composite controls [Windows Forms], creating
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 42ea424507b89576df8099fd4849dd2665135a55
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459438"
---
# <a name="how-to-author-composite-controls"></a><span data-ttu-id="24ed5-102">Cómo: crear controles compuestos</span><span class="sxs-lookup"><span data-stu-id="24ed5-102">How to: Author composite controls</span></span>

<span data-ttu-id="24ed5-103">Los controles compuestos pueden emplearse de muchas formas.</span><span class="sxs-lookup"><span data-stu-id="24ed5-103">Composite controls can be employed in many ways.</span></span> <span data-ttu-id="24ed5-104">Puede crearlos como parte de un proyecto de aplicación de escritorio de Windows y utilizarlos solo en formularios del proyecto.</span><span class="sxs-lookup"><span data-stu-id="24ed5-104">You can author them as part of a Windows desktop application project, and use them only on forms in the project.</span></span> <span data-ttu-id="24ed5-105">También podría crearlos en un proyecto de Biblioteca de controles de Windows, compilar el proyecto en un ensamblado y utilizar los controles en otros proyectos.</span><span class="sxs-lookup"><span data-stu-id="24ed5-105">Or you can author them in a Windows Control Library project, compile the project into an assembly, and use the controls in other projects.</span></span> <span data-ttu-id="24ed5-106">Incluso puede heredar de ellos y utilizar la herencia visual para personalizarlos rápidamente para fines especiales.</span><span class="sxs-lookup"><span data-stu-id="24ed5-106">You can even inherit from them and use visual inheritance to customize them quickly for special purposes.</span></span>

## <a name="to-author-a-composite-control"></a><span data-ttu-id="24ed5-107">Para crear un control compuesto</span><span class="sxs-lookup"><span data-stu-id="24ed5-107">To author a composite control</span></span>

1. <span data-ttu-id="24ed5-108">En Visual Studio, cree un nuevo proyecto de **aplicación para Windows** y asígnele el nombre **DemoControlHost**.</span><span class="sxs-lookup"><span data-stu-id="24ed5-108">In Visual Studio, create a new **Windows Application** project, and name it **DemoControlHost**.</span></span>

2. <span data-ttu-id="24ed5-109">En el menú **Proyecto** , haga clic en **Agregar control de usuario**.</span><span class="sxs-lookup"><span data-stu-id="24ed5-109">On the **Project** menu, click **Add User Control**.</span></span>

3. <span data-ttu-id="24ed5-110">En el cuadro de diálogo **Agregar nuevo elemento**, dé al archivo de clase (archivo .vb o .cs) el nombre que desea para el control compuesto.</span><span class="sxs-lookup"><span data-stu-id="24ed5-110">In the **Add New Item** dialog box, give the class file (.vb or .cs file) the name you want the composite control to have.</span></span>

4. <span data-ttu-id="24ed5-111">Seleccione el botón **Agregar** para crear el archivo de clase para el control compuesto.</span><span class="sxs-lookup"><span data-stu-id="24ed5-111">Select the **Add** button to create the class file for the composite control.</span></span>

5. <span data-ttu-id="24ed5-112">Agregue controles del **Cuadro de herramientas** a la superficie del control compuesto.</span><span class="sxs-lookup"><span data-stu-id="24ed5-112">Add controls from the **Toolbox** to the composite control surface.</span></span>

6. <span data-ttu-id="24ed5-113">Escriba código en los procedimientos de evento para controlar los eventos que produzca el control compuesto o sus controles constituyentes.</span><span class="sxs-lookup"><span data-stu-id="24ed5-113">Place code in event procedures, to handle events raised by the composite control or by its constituent controls.</span></span>

7. <span data-ttu-id="24ed5-114">Cierre el diseñador para el control compuesto y guarde el archivo cuando se le indique.</span><span class="sxs-lookup"><span data-stu-id="24ed5-114">Close the designer for the composite control, and save the file when you are prompted.</span></span>

8. <span data-ttu-id="24ed5-115">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="24ed5-115">On the **Build** menu, click **Build Solution**.</span></span>

     <span data-ttu-id="24ed5-116">Para que los controles personalizados aparezcan en el **Cuadro de herramientas**, deberá compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="24ed5-116">The project must be built in order for custom controls to appear in the **Toolbox**.</span></span>

9. <span data-ttu-id="24ed5-117">Use la pestaña **DemoControlHost** del **Cuadro de herramientas** para agregar instancias del control a `Form1`.</span><span class="sxs-lookup"><span data-stu-id="24ed5-117">Use the **DemoControlHost** tab of the **Toolbox** to add instances of your control to `Form1`.</span></span>

## <a name="to-author-a-control-class-library"></a><span data-ttu-id="24ed5-118">Para crear una biblioteca de clases de controles</span><span class="sxs-lookup"><span data-stu-id="24ed5-118">To author a control class library</span></span>

1. <span data-ttu-id="24ed5-119">Abra un nuevo proyecto de tipo **Biblioteca de controles de Windows**.</span><span class="sxs-lookup"><span data-stu-id="24ed5-119">Open a new **Windows Control Library** project.</span></span>

     <span data-ttu-id="24ed5-120">De forma predeterminada, el proyecto contiene un control compuesto.</span><span class="sxs-lookup"><span data-stu-id="24ed5-120">By default, the project contains a composite control.</span></span>

2. <span data-ttu-id="24ed5-121">Agregue controles y código como se describió en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="24ed5-121">Add controls and code as described in the procedure above.</span></span>

3. <span data-ttu-id="24ed5-122">Elija un control cuyas clases de herencia no desee que cambien y establezca la propiedad **Modifiers** de este control en **Private**.</span><span class="sxs-lookup"><span data-stu-id="24ed5-122">Choose a control you do not want inheriting classes to change, and set the **Modifiers** property of this control to **Private**.</span></span>

4. <span data-ttu-id="24ed5-123">Compile el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="24ed5-123">Build the DLL.</span></span>

## <a name="to-inherit-from-a-composite-control-in-a-control-class-library"></a><span data-ttu-id="24ed5-124">Para heredar de un control compuesto de una biblioteca de clases de controles</span><span class="sxs-lookup"><span data-stu-id="24ed5-124">To inherit from a composite control in a control class library</span></span>

1. <span data-ttu-id="24ed5-125">En el menú **Archivo**, seleccione **Agregar** y **Nuevo proyecto** para agregar un nuevo proyecto **Aplicación Windows** a la solución.</span><span class="sxs-lookup"><span data-stu-id="24ed5-125">On the **File** menu, point to **Add** and select **New Project** to add a new **Windows Application** project to the solution.</span></span>

2. <span data-ttu-id="24ed5-126">En el **Explorador de soluciones**, haga clic con el botón derecho en la carpeta **Referencias** del nuevo proyecto y elija **Agregar referencia** para abrir el cuadro de diálogo **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="24ed5-126">In **Solution Explorer**, right-click the **References** folder for the new project and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

3. <span data-ttu-id="24ed5-127">Seleccione la pestaña **Proyectos** y haga doble clic en el proyecto de Biblioteca de controles.</span><span class="sxs-lookup"><span data-stu-id="24ed5-127">Select the **Projects** tab and double-click your control library project.</span></span>

4. <span data-ttu-id="24ed5-128">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="24ed5-128">On the **Build** menu, click **Build Solution**.</span></span>

5. <span data-ttu-id="24ed5-129">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto de Biblioteca de controles y elija **Agregar nuevo elemento** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="24ed5-129">In **Solution Explorer**, right-click your control library project and select **Add New Item** from the shortcut menu.</span></span>

6. <span data-ttu-id="24ed5-130">Seleccione la plantilla **Control de usuario heredado** en el cuadro de diálogo **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="24ed5-130">Select the **Inherited User Control** template from the **Add New Item** dialog box.</span></span>

7. <span data-ttu-id="24ed5-131">En el cuadro de diálogo **Selector de herencia**, haga doble clic en el control del que desea heredar.</span><span class="sxs-lookup"><span data-stu-id="24ed5-131">In the **Inheritance Picker** dialog box, double-click the control you want to inherit from.</span></span>

     <span data-ttu-id="24ed5-132">Se agrega un nuevo control al proyecto.</span><span class="sxs-lookup"><span data-stu-id="24ed5-132">A new control is added to your project.</span></span>

8. <span data-ttu-id="24ed5-133">Abra el diseñador visual para el nuevo control y agregue controles constituyentes adicionales.</span><span class="sxs-lookup"><span data-stu-id="24ed5-133">Open the visual designer for the new control and add additional constituent controls.</span></span>

     <span data-ttu-id="24ed5-134">Puede ver los controles constituyentes heredados del control de usuario en la DLL, así como alterar las propiedades de aquellos controles cuya propiedad **Modifiers** sea **Public**.</span><span class="sxs-lookup"><span data-stu-id="24ed5-134">You can see the constituent controls that were inherited from the composite control in your DLL, and you can alter the properties of controls whose **Modifiers** property is **Public**.</span></span> <span data-ttu-id="24ed5-135">En cambio, no puede cambiar las propiedades del control cuya propiedad **Modifiers** sea **Private**.</span><span class="sxs-lookup"><span data-stu-id="24ed5-135">You cannot change the properties of the control whose **Modifiers** property is **Private**.</span></span>

## <a name="see-also"></a><span data-ttu-id="24ed5-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="24ed5-136">See also</span></span>

- [<span data-ttu-id="24ed5-137">Tutorial: crear un control compuesto</span><span class="sxs-lookup"><span data-stu-id="24ed5-137">Walkthrough: Authoring a Composite Control</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [<span data-ttu-id="24ed5-138">Tutorial: heredar de un control Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24ed5-138">Walkthrough: Inheriting from a Windows Forms Control</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
- [<span data-ttu-id="24ed5-139">Recomendaciones sobre tipos de controles</span><span class="sxs-lookup"><span data-stu-id="24ed5-139">Control Type Recommendations</span></span>](control-type-recommendations.md)
- [<span data-ttu-id="24ed5-140">Cómo: Crear controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24ed5-140">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="24ed5-141">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="24ed5-141">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
