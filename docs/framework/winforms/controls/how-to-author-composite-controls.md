---
title: "Cómo: Crear controles compuestos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UserControl class [Windows Forms], creating composite controls
- user controls [Windows Forms], creating
- user controls [Windows Forms], inheriting from
- composite controls [Windows Forms], creating
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 72c68568f0178956d6154f0b3a070e69b6ff0502
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-author-composite-controls"></a><span data-ttu-id="3cb3b-102">Cómo: Crear controles compuestos</span><span class="sxs-lookup"><span data-stu-id="3cb3b-102">How to: Author Composite Controls</span></span>
<span data-ttu-id="3cb3b-103">Los controles compuestos pueden emplearse de muchas formas.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-103">Composite controls can be employed in many ways.</span></span> <span data-ttu-id="3cb3b-104">Puede crearlos como parte de un proyecto de aplicación de escritorio de Windows y utilizarlos solo en formularios del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-104">You can author them as part of a Windows desktop application project, and use them only on forms in the project.</span></span> <span data-ttu-id="3cb3b-105">También podría crearlos en un proyecto de Biblioteca de controles de Windows, compilar el proyecto en un ensamblado y utilizar los controles en otros proyectos.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-105">Or you can author them in a Windows Control Library project, compile the project into an assembly, and use the controls in other projects.</span></span> <span data-ttu-id="3cb3b-106">Es posible incluso heredar de ellos y utilizar la herencia visual para personalizarlos rápidamente para fines especiales.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-106">You can even inherit from them, and use visual inheritance to customize them quickly for special purposes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3cb3b-107">Si desea crear un control compuesto para utilizarlo en los formularios Web Forms, vea [Desarrollar controles de servidor ASP.NET personalizados](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).</span><span class="sxs-lookup"><span data-stu-id="3cb3b-107">If you want to author a composite control to use on Web Forms, see [Developing Custom ASP.NET Server Controls](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).</span></span>  
>   
>  <span data-ttu-id="3cb3b-108">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3cb3b-109">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="3cb3b-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3cb3b-110">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="3cb3b-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-author-a-composite-control"></a><span data-ttu-id="3cb3b-111">Para crear un control compuesto</span><span class="sxs-lookup"><span data-stu-id="3cb3b-111">To author a composite control</span></span>  
  
1.  <span data-ttu-id="3cb3b-112">Abra un nuevo proyecto **Aplicación Windows** denominado `DemoControlHost`.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-112">Open a new **Windows Application** project called `DemoControlHost`.</span></span>  
  
2.  <span data-ttu-id="3cb3b-113">En el menú **Proyecto**, haga clic en **Agregar control de usuario**.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-113">On the **Project**menu, click **Add User Control**.</span></span>  
  
3.  <span data-ttu-id="3cb3b-114">En el cuadro de diálogo **Agregar nuevo elemento**, dé al archivo de clase (archivo .vb o .cs) el nombre que desea para el control compuesto.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-114">In the **Add New Item** dialog box, give the class file (.vb or .cs file) the name you want the composite control to have.</span></span>  
  
4.  <span data-ttu-id="3cb3b-115">Haga clic en el botón **Agregar** para crear el archivo de clase para el control compuesto.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-115">Click the **Add** button to create the class file for the composite control.</span></span>  
  
5.  <span data-ttu-id="3cb3b-116">Agregue controles del **Cuadro de herramientas** a la superficie del control compuesto.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-116">Add controls from the **Toolbox** to the composite control surface.</span></span>  
  
6.  <span data-ttu-id="3cb3b-117">Escriba código en los procedimientos de evento para controlar los eventos que produzca el control compuesto o sus controles constituyentes.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-117">Place code in event procedures, to handle events raised by the composite control or by its constituent controls.</span></span>  
  
7.  <span data-ttu-id="3cb3b-118">Cierre el diseñador para el control compuesto y guarde el archivo cuando se le indique.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-118">Close the designer for the composite control, and save the file when you are prompted.</span></span>  
  
8.  <span data-ttu-id="3cb3b-119">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-119">On the **Build** menu, click **Build Solution**.</span></span>  
  
     <span data-ttu-id="3cb3b-120">Para que los controles personalizados aparezcan en el **Cuadro de herramientas**, deberá compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-120">The project must be built in order for custom controls to appear in the **Toolbox**.</span></span>  
  
9. <span data-ttu-id="3cb3b-121">Use la pestaña **DemoControlHost** del **Cuadro de herramientas** para agregar instancias del control a `Form1`.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-121">Use the **DemoControlHost** tab of the **Toolbox** to add instances of your control to `Form1`.</span></span>  
  
### <a name="to-author-a-control-class-library"></a><span data-ttu-id="3cb3b-122">Para crear una biblioteca de clases de controles</span><span class="sxs-lookup"><span data-stu-id="3cb3b-122">To author a control class library</span></span>  
  
1.  <span data-ttu-id="3cb3b-123">Abra un nuevo proyecto de tipo **Biblioteca de controles de Windows**.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-123">Open a new **Windows Control Library** project.</span></span>  
  
     <span data-ttu-id="3cb3b-124">De forma predeterminada, el proyecto contiene un control compuesto.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-124">By default, the project contains a composite control.</span></span>  
  
2.  <span data-ttu-id="3cb3b-125">Agregue controles y código como se describió en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-125">Add controls and code as described in the procedure above.</span></span>  
  
3.  <span data-ttu-id="3cb3b-126">Elija un control cuyas clases de herencia no desee que cambien y establezca la propiedad **Modifiers** de este control en **Private**.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-126">Choose a control you do not want inheriting classes to change, and set the **Modifiers** property of this control to **Private**.</span></span>  
  
4.  <span data-ttu-id="3cb3b-127">Compile el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-127">Build the DLL.</span></span>  
  
### <a name="to-inherit-from-a-composite-control-in-a-control-class-library"></a><span data-ttu-id="3cb3b-128">Para heredar de un control compuesto de una biblioteca de clases de controles</span><span class="sxs-lookup"><span data-stu-id="3cb3b-128">To inherit from a composite control in a control class library</span></span>  
  
1.  <span data-ttu-id="3cb3b-129">En el menú **Archivo**, seleccione **Agregar** y **Nuevo proyecto** para agregar un nuevo proyecto **Aplicación Windows** a la solución.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-129">On the **File** menu, point to **Add** and select **New Project** to add a new **Windows Application** project to the solution.</span></span>  
  
2.  <span data-ttu-id="3cb3b-130">En el **Explorador de soluciones**, haga clic con el botón derecho en la carpeta **Referencias** del nuevo proyecto y elija **Agregar referencia** para abrir el cuadro de diálogo **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-130">In **Solution Explorer**, right-click the **References** folder for the new project and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>  
  
3.  <span data-ttu-id="3cb3b-131">Seleccione la pestaña **Proyectos** y haga doble clic en el proyecto de Biblioteca de controles.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-131">Select the **Projects** tab and double-click your control library project.</span></span>  
  
4.  <span data-ttu-id="3cb3b-132">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-132">On the **Build** menu, click **Build Solution**.</span></span>  
  
5.  <span data-ttu-id="3cb3b-133">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto de Biblioteca de controles y elija **Agregar nuevo elemento** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-133">In **Solution Explorer**, right-click your control library project and select **Add New Item** from the shortcut menu.</span></span>  
  
6.  <span data-ttu-id="3cb3b-134">Seleccione la plantilla **Control de usuario heredado** en el cuadro de diálogo **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-134">Select the **Inherited User Control** template from the **Add New Item** dialog box.</span></span>  
  
7.  <span data-ttu-id="3cb3b-135">En el cuadro de diálogo **Selector de herencia**, haga doble clic en el control del que desea heredar.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-135">In the **Inheritance Picker** dialog box, double-click the control you want to inherit from.</span></span>  
  
     <span data-ttu-id="3cb3b-136">Se agrega un nuevo control al proyecto.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-136">A new control is added to your project.</span></span>  
  
8.  <span data-ttu-id="3cb3b-137">Abra el diseñador visual para el nuevo control y agregue controles constituyentes adicionales.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-137">Open the visual designer for the new control and add additional constituent controls.</span></span>  
  
     <span data-ttu-id="3cb3b-138">Puede ver los controles constituyentes heredados del control de usuario en la DLL, así como alterar las propiedades de aquellos controles cuya propiedad **Modifiers** sea **Public**.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-138">You can see the constituent controls that were inherited from the composite control in your DLL, and you can alter the properties of controls whose **Modifiers** property is **Public**.</span></span> <span data-ttu-id="3cb3b-139">En cambio, no puede cambiar las propiedades del control cuya propiedad **Modifiers** sea **Private**.</span><span class="sxs-lookup"><span data-stu-id="3cb3b-139">You cannot change the properties of the control whose **Modifiers** property is **Private**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cb3b-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cb3b-140">See Also</span></span>  
 [<span data-ttu-id="3cb3b-141">Tutorial: Crear un control compuesto con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3cb3b-141">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [<span data-ttu-id="3cb3b-142">Tutorial: Crear un control compuesto con Visual C#</span><span class="sxs-lookup"><span data-stu-id="3cb3b-142">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 [<span data-ttu-id="3cb3b-143">Tutorial: Heredar de un control de Windows Forms con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3cb3b-143">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 [<span data-ttu-id="3cb3b-144">Tutorial: Heredar de un control de Windows Forms con Visual C#</span><span class="sxs-lookup"><span data-stu-id="3cb3b-144">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 [<span data-ttu-id="3cb3b-145">Recomendaciones sobre tipos de controles</span><span class="sxs-lookup"><span data-stu-id="3cb3b-145">Control Type Recommendations</span></span>](../../../../docs/framework/winforms/controls/control-type-recommendations.md)  
 [<span data-ttu-id="3cb3b-146">Cómo: Crear controles para Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3cb3b-146">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [<span data-ttu-id="3cb3b-147">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="3cb3b-147">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
