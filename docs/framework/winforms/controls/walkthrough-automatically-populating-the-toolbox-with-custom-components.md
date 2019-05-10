---
title: 'Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados'
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 876de650f9c182c0f82a02d1c5b356faa4f7f118
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211153"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="d975b-102">Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados</span><span class="sxs-lookup"><span data-stu-id="d975b-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>

<span data-ttu-id="d975b-103">Si los componentes están definidos por un proyecto en la solución actualmente abierta, estas aparecerán automáticamente en el **cuadro de herramientas**, con ninguna acción requerida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="d975b-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="d975b-104">Puede rellenar manualmente el **cuadro de herramientas** con componentes personalizados mediante el uso de la [elegir elementos de cuadro de diálogo) (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), pero la **cuadro de herramientas** tiene en cuenta de elementos de la solución de resultados de la compilación con las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="d975b-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>

- <span data-ttu-id="d975b-105">Implementa <xref:System.ComponentModel.IComponent>;</span><span class="sxs-lookup"><span data-stu-id="d975b-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>

- <span data-ttu-id="d975b-106">No tiene <xref:System.ComponentModel.ToolboxItemAttribute> establecido en `false`;</span><span class="sxs-lookup"><span data-stu-id="d975b-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>

- <span data-ttu-id="d975b-107">No tiene <xref:System.ComponentModel.DesignTimeVisibleAttribute> establecido en `false`.</span><span class="sxs-lookup"><span data-stu-id="d975b-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>

> [!NOTE]
> <span data-ttu-id="d975b-108">El **cuadro de herramientas** no sigue las cadenas de referencia, por lo que no muestra los elementos que no se compilan en un proyecto de la solución.</span><span class="sxs-lookup"><span data-stu-id="d975b-108">The **Toolbox** does not follow reference chains, so it won't display items that are not built by a project in your solution.</span></span>

<span data-ttu-id="d975b-109">Este tutorial muestra cómo un componente personalizado aparece automáticamente en el **cuadro de herramientas** una vez que se basa el componente.</span><span class="sxs-lookup"><span data-stu-id="d975b-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="d975b-110">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="d975b-110">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="d975b-111">Crear un proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d975b-111">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="d975b-112">Creación de un componente personalizado.</span><span class="sxs-lookup"><span data-stu-id="d975b-112">Creating a custom component.</span></span>

- <span data-ttu-id="d975b-113">Creación de una instancia de un componente personalizado.</span><span class="sxs-lookup"><span data-stu-id="d975b-113">Creating an instance of a custom component.</span></span>

- <span data-ttu-id="d975b-114">Descarga y carga un componente personalizado.</span><span class="sxs-lookup"><span data-stu-id="d975b-114">Unloading and reloading a custom component.</span></span>

<span data-ttu-id="d975b-115">Cuando haya terminado, verá que el **cuadro de herramientas** se rellena con un componente que ha creado.</span><span class="sxs-lookup"><span data-stu-id="d975b-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="d975b-116">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="d975b-116">Create the project</span></span>

1. <span data-ttu-id="d975b-117">En Visual Studio, cree un proyecto de aplicación basada en Windows llamado `ToolboxExample` (**archivo** > **New** > **proyecto**  >  **Visual C#**  o **Visual Basic** > **escritorio clásico de** > **Windows Forms Aplicación**).</span><span class="sxs-lookup"><span data-stu-id="d975b-117">In Visual Studio, create a Windows-based application project called `ToolboxExample` (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="d975b-118">Agregue un nuevo componente al proyecto.</span><span class="sxs-lookup"><span data-stu-id="d975b-118">Add a new component to the project.</span></span> <span data-ttu-id="d975b-119">Asígnele el nombre `DemoComponent`.</span><span class="sxs-lookup"><span data-stu-id="d975b-119">Call it `DemoComponent`.</span></span>

     <span data-ttu-id="d975b-120">Para obtener más información, vea [Cómo: Agregar nuevos elementos de proyecto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d975b-120">For more information, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span>

3. <span data-ttu-id="d975b-121">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d975b-121">Build the project.</span></span>

4. <span data-ttu-id="d975b-122">Desde el **herramientas** menú, haga clic en el **opciones** elemento.</span><span class="sxs-lookup"><span data-stu-id="d975b-122">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="d975b-123">Haga clic en **General** bajo el **Diseñador de Windows Forms** de elementos y asegúrese de que el **AutoToolboxPopulate** opción está establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="d975b-123">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>

## <a name="create-an-instance-of-a-custom-component"></a><span data-ttu-id="d975b-124">Cree una instancia de un componente personalizado</span><span class="sxs-lookup"><span data-stu-id="d975b-124">Create an instance of a custom component</span></span>

<span data-ttu-id="d975b-125">El siguiente paso es crear una instancia del componente personalizado en el formulario.</span><span class="sxs-lookup"><span data-stu-id="d975b-125">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="d975b-126">Dado que el **cuadro de herramientas** automáticamente cuentas para el componente nuevo, esto es tan fácil como crear cualquier otro componente o control.</span><span class="sxs-lookup"><span data-stu-id="d975b-126">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>

1. <span data-ttu-id="d975b-127">Abra el formulario del proyecto en el **Diseñador de formularios**.</span><span class="sxs-lookup"><span data-stu-id="d975b-127">Open the project's form in the **Forms Designer**.</span></span>

2. <span data-ttu-id="d975b-128">En el **cuadro de herramientas**, haga clic en la nueva ficha denominada **Componentes ToolboxExample**.</span><span class="sxs-lookup"><span data-stu-id="d975b-128">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>

     <span data-ttu-id="d975b-129">Al hacer clic en la pestaña, verá **DemoComponent**.</span><span class="sxs-lookup"><span data-stu-id="d975b-129">Once you click the tab, you will see **DemoComponent**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d975b-130">Por motivos de rendimiento, los componentes en el área rellena automáticamente de la **cuadro de herramientas** no mostrar mapas de bits personalizados y el <xref:System.Drawing.ToolboxBitmapAttribute> no se admite.</span><span class="sxs-lookup"><span data-stu-id="d975b-130">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="d975b-131">Para mostrar un icono para un componente personalizado en el **cuadro de herramientas**, utilice el **elegir elementos del cuadro de herramientas** cuadro de diálogo para cargar el componente.</span><span class="sxs-lookup"><span data-stu-id="d975b-131">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>

3. <span data-ttu-id="d975b-132">Arrastre el componente al formulario.</span><span class="sxs-lookup"><span data-stu-id="d975b-132">Drag your component onto your form.</span></span>

     <span data-ttu-id="d975b-133">Se crea una instancia del componente y se agrega a la **Bandeja de componentes**.</span><span class="sxs-lookup"><span data-stu-id="d975b-133">An instance of the component is created and added to the **Component Tray**.</span></span>

## <a name="unload-and-reload-a-custom-component"></a><span data-ttu-id="d975b-134">Descargar y recargar un componente personalizado</span><span class="sxs-lookup"><span data-stu-id="d975b-134">Unload and reload a custom component</span></span>

<span data-ttu-id="d975b-135">El **cuadro de herramientas** tiene en cuenta los componentes en cada carga de proyecto y, cuando se descarga un proyecto, se quita las referencias a componentes del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d975b-135">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>

1. <span data-ttu-id="d975b-136">Descargue el proyecto de la solución.</span><span class="sxs-lookup"><span data-stu-id="d975b-136">Unload the project from the solution.</span></span>

     <span data-ttu-id="d975b-137">Para obtener más información sobre cómo descargar los proyectos, vea [Cómo: Descargar y recargar proyectos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d975b-137">For more information about unloading projects, see [How to: Unload and Reload Projects](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span></span> <span data-ttu-id="d975b-138">Si se le solicite guardar, elija **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d975b-138">If you are prompted to save, choose **Yes**.</span></span>

2. <span data-ttu-id="d975b-139">Agregue un nuevo **aplicación Windows** proyecto a la solución.</span><span class="sxs-lookup"><span data-stu-id="d975b-139">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="d975b-140">Abra el formulario en el **diseñador**.</span><span class="sxs-lookup"><span data-stu-id="d975b-140">Open the form in the **Designer**.</span></span>

     <span data-ttu-id="d975b-141">El **Componentes ToolboxExample** ficha desde el proyecto anterior es ahora han desaparecido.</span><span class="sxs-lookup"><span data-stu-id="d975b-141">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>

3. <span data-ttu-id="d975b-142">Volver a cargar el `ToolboxExample` proyecto.</span><span class="sxs-lookup"><span data-stu-id="d975b-142">Reload the `ToolboxExample` project.</span></span>

     <span data-ttu-id="d975b-143">El **Componentes ToolboxExample** pestaña ahora vuelve a aparecer.</span><span class="sxs-lookup"><span data-stu-id="d975b-143">The **ToolboxExample Components** tab now reappears.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d975b-144">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d975b-144">Next steps</span></span>

<span data-ttu-id="d975b-145">En este tutorial se muestra que el **cuadro de herramientas** tiene en cuenta los componentes de un proyecto, pero la **cuadro de herramientas** es también tiene en cuenta los controles.</span><span class="sxs-lookup"><span data-stu-id="d975b-145">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="d975b-146">Experimentar con sus propios controles personalizados mediante la adición y eliminación de proyectos de control de la solución.</span><span class="sxs-lookup"><span data-stu-id="d975b-146">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>

## <a name="see-also"></a><span data-ttu-id="d975b-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="d975b-147">See also</span></span>

- <span data-ttu-id="d975b-148">[General, Diseñador de formularios de Windows, cuadro de diálogo Opciones](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d975b-148">[General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span></span>
- <span data-ttu-id="d975b-149">[Cómo: Manipular las fichas del cuadro de herramientas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d975b-149">[How to: Manipulate Toolbox Tabs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span></span>
- <span data-ttu-id="d975b-150">[Elegir elementos del cuadro de herramientas (Cuadro de diálogo): Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d975b-150">[Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span></span>
- [<span data-ttu-id="d975b-151">Insertar controles en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d975b-151">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
