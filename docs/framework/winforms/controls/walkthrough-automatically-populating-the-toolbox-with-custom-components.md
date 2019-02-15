---
title: 'Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados'
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: b4c6bf42bdd1ba6b0f9ccddb730dc517dbaab963
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2019
ms.locfileid: "56304094"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="ba758-102">Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados</span><span class="sxs-lookup"><span data-stu-id="ba758-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>
<span data-ttu-id="ba758-103">Si los componentes están definidos por un proyecto en la solución actualmente abierta, estas aparecerán automáticamente en el **cuadro de herramientas**, con ninguna acción requerida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="ba758-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="ba758-104">Puede rellenar manualmente el **cuadro de herramientas** con componentes personalizados mediante el uso de la [elegir elementos de cuadro de diálogo) (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), pero la **cuadro de herramientas** tiene en cuenta de elementos de la solución de resultados de la compilación con las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="ba758-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>  
  
-   <span data-ttu-id="ba758-105">Implementa <xref:System.ComponentModel.IComponent>;</span><span class="sxs-lookup"><span data-stu-id="ba758-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>  
  
-   <span data-ttu-id="ba758-106">No tiene <xref:System.ComponentModel.ToolboxItemAttribute> establecido en `false`;</span><span class="sxs-lookup"><span data-stu-id="ba758-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>  
  
-   <span data-ttu-id="ba758-107">No tiene <xref:System.ComponentModel.DesignTimeVisibleAttribute> establecido en `false`.</span><span class="sxs-lookup"><span data-stu-id="ba758-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba758-108">El **cuadro de herramientas** no sigue las cadenas de referencia, por lo que no mostrará los elementos que no se compilan en un proyecto de la solución.</span><span class="sxs-lookup"><span data-stu-id="ba758-108">The **Toolbox** does not follow reference chains, so it will not display items that are not built by a project in your solution.</span></span>  
  
 <span data-ttu-id="ba758-109">Este tutorial muestra cómo un componente personalizado aparece automáticamente en el **cuadro de herramientas** una vez que se basa el componente.</span><span class="sxs-lookup"><span data-stu-id="ba758-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="ba758-110">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="ba758-110">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="ba758-111">Crear un proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ba758-111">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="ba758-112">Creación de un componente personalizado.</span><span class="sxs-lookup"><span data-stu-id="ba758-112">Creating a custom component.</span></span>  
  
-   <span data-ttu-id="ba758-113">Creación de una instancia de un componente personalizado.</span><span class="sxs-lookup"><span data-stu-id="ba758-113">Creating an instance of a custom component.</span></span>  
  
-   <span data-ttu-id="ba758-114">Descarga y carga un componente personalizado.</span><span class="sxs-lookup"><span data-stu-id="ba758-114">Unloading and reloading a custom component.</span></span>  
  
 <span data-ttu-id="ba758-115">Cuando haya terminado, verá que el **cuadro de herramientas** se rellena con un componente que ha creado.</span><span class="sxs-lookup"><span data-stu-id="ba758-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba758-116">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="ba758-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ba758-117">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="ba758-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ba758-118">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="ba758-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="ba758-119">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="ba758-119">Creating the Project</span></span>  
 <span data-ttu-id="ba758-120">El primer paso es crear el proyecto y configurar el formulario.</span><span class="sxs-lookup"><span data-stu-id="ba758-120">The first step is to create the project and to set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="ba758-121">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="ba758-121">To create the project</span></span>  
  
1.  <span data-ttu-id="ba758-122">Cree un proyecto de aplicación basada en Windows llamado `ToolboxExample` (**archivo** > **New** > **proyecto**  >  **Visual C#** o **Visual Basic** > **escritorio clásico de** > **aplicación de Windows Forms**).</span><span class="sxs-lookup"><span data-stu-id="ba758-122">Create a Windows-based application project called `ToolboxExample` (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="ba758-123">Agregue un nuevo componente al proyecto.</span><span class="sxs-lookup"><span data-stu-id="ba758-123">Add a new component to the project.</span></span> <span data-ttu-id="ba758-124">Asígnele el nombre `DemoComponent`.</span><span class="sxs-lookup"><span data-stu-id="ba758-124">Call it `DemoComponent`.</span></span>  
  
     <span data-ttu-id="ba758-125">Para obtener más información, vea [Cómo: Agregar nuevos elementos de proyecto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ba758-125">For more information, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span>  
  
3.  <span data-ttu-id="ba758-126">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ba758-126">Build the project.</span></span>  
  
4.  <span data-ttu-id="ba758-127">Desde el **herramientas** menú, haga clic en el **opciones** elemento.</span><span class="sxs-lookup"><span data-stu-id="ba758-127">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="ba758-128">Haga clic en **General** bajo el **Diseñador de Windows Forms** de elementos y asegúrese de que el **AutoToolboxPopulate** opción está establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="ba758-128">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>  
  
## <a name="creating-an-instance-of-a-custom-component"></a><span data-ttu-id="ba758-129">Creación de una instancia de un componente personalizado</span><span class="sxs-lookup"><span data-stu-id="ba758-129">Creating an Instance of a Custom Component</span></span>  
 <span data-ttu-id="ba758-130">El siguiente paso es crear una instancia del componente personalizado en el formulario.</span><span class="sxs-lookup"><span data-stu-id="ba758-130">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="ba758-131">Dado que el **cuadro de herramientas** automáticamente cuentas para el componente nuevo, esto es tan fácil como crear cualquier otro componente o control.</span><span class="sxs-lookup"><span data-stu-id="ba758-131">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a><span data-ttu-id="ba758-132">Para crear una instancia de un componente personalizado</span><span class="sxs-lookup"><span data-stu-id="ba758-132">To create an instance of a custom component</span></span>  
  
1.  <span data-ttu-id="ba758-133">Abra el formulario del proyecto en el **Diseñador de formularios**.</span><span class="sxs-lookup"><span data-stu-id="ba758-133">Open the project's form in the **Forms Designer**.</span></span>  
  
2.  <span data-ttu-id="ba758-134">En el **cuadro de herramientas**, haga clic en la nueva ficha denominada **Componentes ToolboxExample**.</span><span class="sxs-lookup"><span data-stu-id="ba758-134">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>  
  
     <span data-ttu-id="ba758-135">Al hacer clic en la pestaña, verá **DemoComponent**.</span><span class="sxs-lookup"><span data-stu-id="ba758-135">Once you click the tab, you will see **DemoComponent**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ba758-136">Por motivos de rendimiento, los componentes en el área rellena automáticamente de la **cuadro de herramientas** no mostrar mapas de bits personalizados y el <xref:System.Drawing.ToolboxBitmapAttribute> no se admite.</span><span class="sxs-lookup"><span data-stu-id="ba758-136">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="ba758-137">Para mostrar un icono para un componente personalizado en el **cuadro de herramientas**, utilice el **elegir elementos del cuadro de herramientas** cuadro de diálogo para cargar el componente.</span><span class="sxs-lookup"><span data-stu-id="ba758-137">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>  
  
3.  <span data-ttu-id="ba758-138">Arrastre el componente al formulario.</span><span class="sxs-lookup"><span data-stu-id="ba758-138">Drag your component onto your form.</span></span>  
  
     <span data-ttu-id="ba758-139">Se crea una instancia del componente y se agrega a la **Bandeja de componentes**.</span><span class="sxs-lookup"><span data-stu-id="ba758-139">An instance of the component is created and added to the **Component Tray**.</span></span>  
  
## <a name="unloading-and-reloading-a-custom-component"></a><span data-ttu-id="ba758-140">Descarga y carga un componente personalizado</span><span class="sxs-lookup"><span data-stu-id="ba758-140">Unloading and Reloading a Custom Component</span></span>  
 <span data-ttu-id="ba758-141">El **cuadro de herramientas** tiene en cuenta los componentes en cada carga de proyecto y, cuando se descarga un proyecto, se quita las referencias a componentes del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ba758-141">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a><span data-ttu-id="ba758-142">Para experimentar con el efecto en el cuadro de herramientas de descarga y carga de componentes</span><span class="sxs-lookup"><span data-stu-id="ba758-142">To experiment with the effect on the Toolbox of unloading and reloading components</span></span>  
  
1.  <span data-ttu-id="ba758-143">Descargue el proyecto de la solución.</span><span class="sxs-lookup"><span data-stu-id="ba758-143">Unload the project from the solution.</span></span>  
  
     <span data-ttu-id="ba758-144">Para obtener más información sobre cómo descargar los proyectos, vea [Cómo: Descargar y recargar proyectos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ba758-144">For more information about unloading projects, see [How to: Unload and Reload Projects](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span></span> <span data-ttu-id="ba758-145">Si se le solicite guardar, elija **Sí**.</span><span class="sxs-lookup"><span data-stu-id="ba758-145">If you are prompted to save, choose **Yes**.</span></span>  
  
2.  <span data-ttu-id="ba758-146">Agregue un nuevo **aplicación Windows** proyecto a la solución.</span><span class="sxs-lookup"><span data-stu-id="ba758-146">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="ba758-147">Abra el formulario en el **diseñador**.</span><span class="sxs-lookup"><span data-stu-id="ba758-147">Open the form in the **Designer**.</span></span>  
  
     <span data-ttu-id="ba758-148">El **Componentes ToolboxExample** ficha desde el proyecto anterior es ahora han desaparecido.</span><span class="sxs-lookup"><span data-stu-id="ba758-148">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>  
  
3.  <span data-ttu-id="ba758-149">Volver a cargar el `ToolboxExample` proyecto.</span><span class="sxs-lookup"><span data-stu-id="ba758-149">Reload the `ToolboxExample` project.</span></span>  
  
     <span data-ttu-id="ba758-150">El **Componentes ToolboxExample** pestaña ahora vuelve a aparecer.</span><span class="sxs-lookup"><span data-stu-id="ba758-150">The **ToolboxExample Components** tab now reappears.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ba758-151">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ba758-151">Next Steps</span></span>  
 <span data-ttu-id="ba758-152">En este tutorial se muestra que el **cuadro de herramientas** tiene en cuenta los componentes de un proyecto, pero la **cuadro de herramientas** es también tiene en cuenta los controles.</span><span class="sxs-lookup"><span data-stu-id="ba758-152">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="ba758-153">Experimentar con sus propios controles personalizados mediante la adición y eliminación de proyectos de control de la solución.</span><span class="sxs-lookup"><span data-stu-id="ba758-153">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba758-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba758-154">See also</span></span>
- <span data-ttu-id="ba758-155">[General, Diseñador de formularios de Windows, cuadro de diálogo Opciones](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ba758-155">[General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span></span>
- <span data-ttu-id="ba758-156">[Cómo: Manipular las fichas del cuadro de herramientas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ba758-156">[How to: Manipulate Toolbox Tabs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span></span>
- <span data-ttu-id="ba758-157">[Elegir elementos del cuadro de herramientas (Cuadro de diálogo): Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ba758-157">[Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span></span>
- [<span data-ttu-id="ba758-158">Insertar controles en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ba758-158">Putting Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)
