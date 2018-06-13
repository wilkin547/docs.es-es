---
title: 'Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados'
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: d446ab84cfe135e56483b8b309b696f7f15044fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540051"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="0f03f-102">Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados</span><span class="sxs-lookup"><span data-stu-id="0f03f-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>
<span data-ttu-id="0f03f-103">Si los componentes están definidos en un proyecto de la solución actualmente abierta, estas aparecerán automáticamente en el **cuadro de herramientas**, sin ninguna acción necesaria por parte del usuario.</span><span class="sxs-lookup"><span data-stu-id="0f03f-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="0f03f-104">Puede rellenar manualmente el **cuadro de herramientas** con componentes personalizados mediante el uso de la [elegir Toolbox Items Dialog Box (Visual Studio)](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb), pero la **cuadro de herramientas** tiene en cuenta de elementos de la solución generar resultados con todas las características siguientes:</span><span class="sxs-lookup"><span data-stu-id="0f03f-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>  
  
-   <span data-ttu-id="0f03f-105">Implementa <xref:System.ComponentModel.IComponent>;</span><span class="sxs-lookup"><span data-stu-id="0f03f-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>  
  
-   <span data-ttu-id="0f03f-106">No tiene <xref:System.ComponentModel.ToolboxItemAttribute> establecido en `false`;</span><span class="sxs-lookup"><span data-stu-id="0f03f-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>  
  
-   <span data-ttu-id="0f03f-107">No tiene <xref:System.ComponentModel.DesignTimeVisibleAttribute> establecido en `false`.</span><span class="sxs-lookup"><span data-stu-id="0f03f-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f03f-108">El **cuadro de herramientas** no sigue las cadenas de referencia, por lo que no se mostrarán los elementos que no se compilan en un proyecto de la solución.</span><span class="sxs-lookup"><span data-stu-id="0f03f-108">The **Toolbox** does not follow reference chains, so it will not display items that are not built by a project in your solution.</span></span>  
  
 <span data-ttu-id="0f03f-109">Este tutorial muestra cómo un componente personalizado aparece automáticamente en el **cuadro de herramientas** una vez que se basa el componente.</span><span class="sxs-lookup"><span data-stu-id="0f03f-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="0f03f-110">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="0f03f-110">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="0f03f-111">Crear un proyecto de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0f03f-111">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="0f03f-112">Crear un componente personalizado.</span><span class="sxs-lookup"><span data-stu-id="0f03f-112">Creating a custom component.</span></span>  
  
-   <span data-ttu-id="0f03f-113">Crear una instancia de un componente personalizado.</span><span class="sxs-lookup"><span data-stu-id="0f03f-113">Creating an instance of a custom component.</span></span>  
  
-   <span data-ttu-id="0f03f-114">Descargar y volver a cargar un componente personalizado.</span><span class="sxs-lookup"><span data-stu-id="0f03f-114">Unloading and reloading a custom component.</span></span>  
  
 <span data-ttu-id="0f03f-115">Cuando haya terminado, verá que el **cuadro de herramientas** se rellena con un componente que ha creado.</span><span class="sxs-lookup"><span data-stu-id="0f03f-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f03f-116">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="0f03f-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0f03f-117">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="0f03f-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0f03f-118">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="0f03f-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="0f03f-119">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="0f03f-119">Creating the Project</span></span>  
 <span data-ttu-id="0f03f-120">El primer paso es crear el proyecto y configurar el formulario.</span><span class="sxs-lookup"><span data-stu-id="0f03f-120">The first step is to create the project and to set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="0f03f-121">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="0f03f-121">To create the project</span></span>  
  
1.  <span data-ttu-id="0f03f-122">Cree un proyecto de aplicación basada en Windows llamado `ToolboxExample`.</span><span class="sxs-lookup"><span data-stu-id="0f03f-122">Create a Windows-based application project called `ToolboxExample`.</span></span>  
  
     <span data-ttu-id="0f03f-123">Para más información, consulte [Cómo: Crear un proyecto de aplicación para Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="0f03f-123">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="0f03f-124">Agregue un nuevo componente al proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f03f-124">Add a new component to the project.</span></span> <span data-ttu-id="0f03f-125">Llámelo `DemoComponent`.</span><span class="sxs-lookup"><span data-stu-id="0f03f-125">Call it `DemoComponent`.</span></span>  
  
     <span data-ttu-id="0f03f-126">Para obtener más información, consulte [NIB: Cómo: agregar nuevos elementos de proyecto](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span><span class="sxs-lookup"><span data-stu-id="0f03f-126">For more information, see [NIB:How to: Add New Project Items](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span></span>  
  
3.  <span data-ttu-id="0f03f-127">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f03f-127">Build the project.</span></span>  
  
4.  <span data-ttu-id="0f03f-128">Desde el **herramientas** menú, haga clic en el **opciones** elemento.</span><span class="sxs-lookup"><span data-stu-id="0f03f-128">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="0f03f-129">Haga clic en **General** en el **Diseñador de Windows Forms** de elemento y asegúrese de que el **AutoToolboxPopulate** opción está establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="0f03f-129">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>  
  
## <a name="creating-an-instance-of-a-custom-component"></a><span data-ttu-id="0f03f-130">Crear una instancia de un componente personalizado</span><span class="sxs-lookup"><span data-stu-id="0f03f-130">Creating an Instance of a Custom Component</span></span>  
 <span data-ttu-id="0f03f-131">El siguiente paso es crear una instancia del componente personalizado en el formulario.</span><span class="sxs-lookup"><span data-stu-id="0f03f-131">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="0f03f-132">Dado que la **cuadro de herramientas** automáticamente las cuentas para el componente nuevo, esto es tan fácil como crear cualquier otro componente o control.</span><span class="sxs-lookup"><span data-stu-id="0f03f-132">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a><span data-ttu-id="0f03f-133">Para crear una instancia de un componente personalizado</span><span class="sxs-lookup"><span data-stu-id="0f03f-133">To create an instance of a custom component</span></span>  
  
1.  <span data-ttu-id="0f03f-134">Abra el formulario del proyecto en el **Diseñador de formularios**.</span><span class="sxs-lookup"><span data-stu-id="0f03f-134">Open the project's form in the **Forms Designer**.</span></span>  
  
2.  <span data-ttu-id="0f03f-135">En el **cuadro de herramientas**, haga clic en la nueva ficha denominada **Componentes ToolboxExample**.</span><span class="sxs-lookup"><span data-stu-id="0f03f-135">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>  
  
     <span data-ttu-id="0f03f-136">Una vez que haga clic en la pestaña, verá **DemoComponent**.</span><span class="sxs-lookup"><span data-stu-id="0f03f-136">Once you click the tab, you will see **DemoComponent**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0f03f-137">Por motivos de rendimiento, los componentes en el área rellena automáticamente de la **cuadro de herramientas** no se muestran los mapas de bits personalizados y el <xref:System.Drawing.ToolboxBitmapAttribute> no se admite.</span><span class="sxs-lookup"><span data-stu-id="0f03f-137">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="0f03f-138">Para mostrar un icono para un componente personalizado en el **cuadro de herramientas**, use la **elegir elementos del cuadro de herramientas** cuadro de diálogo para cargar el componente.</span><span class="sxs-lookup"><span data-stu-id="0f03f-138">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>  
  
3.  <span data-ttu-id="0f03f-139">Arrastre el componente al formulario.</span><span class="sxs-lookup"><span data-stu-id="0f03f-139">Drag your component onto your form.</span></span>  
  
     <span data-ttu-id="0f03f-140">Se crea una instancia del componente y se agrega a la **Bandeja de componentes**.</span><span class="sxs-lookup"><span data-stu-id="0f03f-140">An instance of the component is created and added to the **Component Tray**.</span></span>  
  
## <a name="unloading-and-reloading-a-custom-component"></a><span data-ttu-id="0f03f-141">Descargar y volver a cargar un componente personalizado</span><span class="sxs-lookup"><span data-stu-id="0f03f-141">Unloading and Reloading a Custom Component</span></span>  
 <span data-ttu-id="0f03f-142">El **cuadro de herramientas** tiene en cuenta los componentes en cada uno de ellos cargado el proyecto y, cuando se descarga un proyecto, quita las referencias a los componentes del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f03f-142">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a><span data-ttu-id="0f03f-143">Para experimentar con el efecto en el cuadro de herramientas de descarga y carga de componentes</span><span class="sxs-lookup"><span data-stu-id="0f03f-143">To experiment with the effect on the Toolbox of unloading and reloading components</span></span>  
  
1.  <span data-ttu-id="0f03f-144">Descargue el proyecto de la solución.</span><span class="sxs-lookup"><span data-stu-id="0f03f-144">Unload the project from the solution.</span></span>  
  
     <span data-ttu-id="0f03f-145">Para obtener más información acerca de cómo descargar los proyectos, vea [NIB: Cómo: descargar y volver a cargar proyectos](http://msdn.microsoft.com/library/abc0155b-8fcb-4ffc-95b6-698518a7100b).</span><span class="sxs-lookup"><span data-stu-id="0f03f-145">For more information about unloading projects, see [NIB:How to: Unload and Reload Projects](http://msdn.microsoft.com/library/abc0155b-8fcb-4ffc-95b6-698518a7100b).</span></span> <span data-ttu-id="0f03f-146">Si se pide que guarde, elija **Sí**.</span><span class="sxs-lookup"><span data-stu-id="0f03f-146">If you are prompted to save, choose **Yes**.</span></span>  
  
2.  <span data-ttu-id="0f03f-147">Agregue un nuevo **aplicación de Windows** proyecto a la solución.</span><span class="sxs-lookup"><span data-stu-id="0f03f-147">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="0f03f-148">Abra el formulario en el **diseñador**.</span><span class="sxs-lookup"><span data-stu-id="0f03f-148">Open the form in the **Designer**.</span></span>  
  
     <span data-ttu-id="0f03f-149">El **Componentes ToolboxExample** ficha desde el proyecto anterior es ahora desaparecido.</span><span class="sxs-lookup"><span data-stu-id="0f03f-149">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>  
  
3.  <span data-ttu-id="0f03f-150">Volver a cargar el `ToolboxExample` proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f03f-150">Reload the `ToolboxExample` project.</span></span>  
  
     <span data-ttu-id="0f03f-151">El **Componentes ToolboxExample** pestaña ahora vuelve a aparecer.</span><span class="sxs-lookup"><span data-stu-id="0f03f-151">The **ToolboxExample Components** tab now reappears.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0f03f-152">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="0f03f-152">Next Steps</span></span>  
 <span data-ttu-id="0f03f-153">En este tutorial se muestra que la **cuadro de herramientas** tiene en cuenta los componentes de un proyecto, pero la **cuadro de herramientas** es también tiene en cuenta los controles.</span><span class="sxs-lookup"><span data-stu-id="0f03f-153">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="0f03f-154">Experimentar con sus propios controles personalizados agregando y quitando proyectos de control de la solución.</span><span class="sxs-lookup"><span data-stu-id="0f03f-154">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f03f-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f03f-155">See Also</span></span>  
 [<span data-ttu-id="0f03f-156">General, Diseñador de Windows Forms, cuadro de diálogo Opciones</span><span class="sxs-lookup"><span data-stu-id="0f03f-156">General, Windows Forms Designer, Options Dialog Box</span></span>](http://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834)  
 [<span data-ttu-id="0f03f-157">Cómo: Manipular las fichas del cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="0f03f-157">How to: Manipulate Toolbox Tabs</span></span>](http://msdn.microsoft.com/library/21285050-cadd-455a-b1f5-a2289a89c4db)  
 [<span data-ttu-id="0f03f-158">Elegir elementos del cuadro de herramientas (Cuadro de diálogo): Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0f03f-158">Choose Toolbox Items Dialog Box (Visual Studio)</span></span>](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [<span data-ttu-id="0f03f-159">Insertar controles en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0f03f-159">Putting Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)
