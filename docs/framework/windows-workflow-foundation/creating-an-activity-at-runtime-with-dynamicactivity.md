---
title: Crear una actividad en el tiempo de ejecución con DynamicActivity
description: DynamicActivity es una clase concreta sellada con un constructor público. Use la clase para ensamblar la funcionalidad de actividad en tiempo de ejecución mediante un DOM de actividad.
ms.date: 03/30/2017
ms.assetid: 1af85cc6-912d-449e-90c5-c5db3eca5ace
ms.openlocfilehash: 17ee14be7df4801018c7afd2e91f1fb07c34e8e1
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421545"
---
# <a name="creating-an-activity-at-runtime-with-dynamicactivity"></a><span data-ttu-id="7c49f-104">Crear una actividad en el tiempo de ejecución con DynamicActivity</span><span class="sxs-lookup"><span data-stu-id="7c49f-104">Creating an Activity at Runtime with DynamicActivity</span></span>
<span data-ttu-id="7c49f-105"><xref:System.Activities.DynamicActivity> es una clase concreta sellada con un constructor público.</span><span class="sxs-lookup"><span data-stu-id="7c49f-105"><xref:System.Activities.DynamicActivity> is a concrete, sealed class with a public constructor.</span></span> <span data-ttu-id="7c49f-106"><xref:System.Activities.DynamicActivity> se puede usar para ensamblar la funcionalidad de actividad en tiempo de ejecución usando un DOM de actividad.</span><span class="sxs-lookup"><span data-stu-id="7c49f-106"><xref:System.Activities.DynamicActivity> can be used to assemble activity functionality at runtime using an activity DOM.</span></span>  
  
## <a name="dynamicactivity-features"></a><span data-ttu-id="7c49f-107">Características de DynamicActivity</span><span class="sxs-lookup"><span data-stu-id="7c49f-107">DynamicActivity Features</span></span>  
 <span data-ttu-id="7c49f-108"><xref:System.Activities.DynamicActivity> tiene acceso a las propiedades, argumentos y variables de ejecución pero no a los servicios en tiempo de ejecución como la programación de actividades secundarias o el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="7c49f-108"><xref:System.Activities.DynamicActivity> has access to execution properties, arguments and variables, but no access to run-time services such as scheduling child activities or tracking.</span></span>  
  
 <span data-ttu-id="7c49f-109">Las propiedades de nivel superior se pueden establecer con los objetos <xref:System.Activities.Argument> de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7c49f-109">Top-level properties can be set using workflow <xref:System.Activities.Argument> objects.</span></span> <span data-ttu-id="7c49f-110">En código imperativo, estos argumentos se crean usando las propiedades CLR en un nuevo tipo.</span><span class="sxs-lookup"><span data-stu-id="7c49f-110">In imperative code, these arguments are created using CLR properties on a new type.</span></span> <span data-ttu-id="7c49f-111">En XAML, se declaran con las etiquetas `x:Class` y `x:Member`.</span><span class="sxs-lookup"><span data-stu-id="7c49f-111">In XAML, they are declared using `x:Class` and `x:Member` tags.</span></span>  
  
 <span data-ttu-id="7c49f-112">Las actividades se construyeron mediante la interfaz <xref:System.Activities.DynamicActivity> con el diseñador usando <xref:System.ComponentModel.ICustomTypeDescriptor>.</span><span class="sxs-lookup"><span data-stu-id="7c49f-112">Activities constructed using <xref:System.Activities.DynamicActivity> interface with the designer using <xref:System.ComponentModel.ICustomTypeDescriptor>.</span></span> <span data-ttu-id="7c49f-113">Las actividades creadas en el diseñador se pueden cargar dinámicamente mediante <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, tal y como se muestra en el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7c49f-113">Activities created in the designer can be loaded dynamically using <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, as demonstrated in the following procedure.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-imperative-code"></a><span data-ttu-id="7c49f-114">Para crear una actividad en el tiempo de ejecución usando el código imperativo</span><span class="sxs-lookup"><span data-stu-id="7c49f-114">To create an activity at runtime using imperative code</span></span>  
  
1. <span data-ttu-id="7c49f-115">OpenVisual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="7c49f-115">OpenVisual Studio 2010.</span></span>  
  
2. <span data-ttu-id="7c49f-116">Seleccione **archivo**, **nuevo**, **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="7c49f-116">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="7c49f-117">Seleccione **flujo de trabajo 4,0** en **Visual C#** en la ventana **tipos de proyecto** y seleccione el nodo **V2010** .</span><span class="sxs-lookup"><span data-stu-id="7c49f-117">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="7c49f-118">Seleccione **aplicación de consola de flujos de trabajo secuenciales** en la ventana **plantillas** .</span><span class="sxs-lookup"><span data-stu-id="7c49f-118">Select **Sequential Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="7c49f-119">Proporcione el nombre siguiente al nuevo proyecto: DynamicActivitySample.</span><span class="sxs-lookup"><span data-stu-id="7c49f-119">Name the new project DynamicActivitySample.</span></span>  
  
3. <span data-ttu-id="7c49f-120">Haga clic con el botón secundario en Workflow1. XAML en el proyecto HelloActivity y seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="7c49f-120">Right-click Workflow1.xaml in the HelloActivity project and select **Delete**.</span></span>  
  
4. <span data-ttu-id="7c49f-121">Abra Program.cs.</span><span class="sxs-lookup"><span data-stu-id="7c49f-121">Open Program.cs.</span></span> <span data-ttu-id="7c49f-122">Agregue la siguiente directiva a la parte superior del archivo.</span><span class="sxs-lookup"><span data-stu-id="7c49f-122">Add the following directive to the top of the file.</span></span>  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
5. <span data-ttu-id="7c49f-123">Sustituya el contenido del método `Main` con el siguiente código, que crea una actividad <xref:System.Activities.Statements.Sequence> que contiene una actividad <xref:System.Activities.Statements.WriteLine> única y la asigna a la propiedad <xref:System.Activities.DynamicActivity.Implementation%2A> de una nueva actividad dinámica.</span><span class="sxs-lookup"><span data-stu-id="7c49f-123">Replace the contents of the `Main` method with the following code, which creates a <xref:System.Activities.Statements.Sequence> activity that contains a single <xref:System.Activities.Statements.WriteLine> activity and assigns it to the <xref:System.Activities.DynamicActivity.Implementation%2A> property of a new dynamic activity.</span></span>  
  
    ```csharp  
    //Define the input argument for the activity  
    var textOut = new InArgument<string>();  
    //Create the activity, property, and implementation  
                Activity dynamicWorkflow = new DynamicActivity()  
                {  
                    Properties =
                    {  
                        new DynamicActivityProperty  
                        {  
                            Name = "Text",  
                            Type = typeof(InArgument<String>),  
                            Value = textOut  
                        }  
                    },  
                    Implementation = () => new Sequence()  
                    {  
                        Activities =
                        {  
                            new WriteLine()  
                            {  
                                Text = new InArgument<string>(env => textOut.Get(env))  
                            }  
                        }  
                    }  
                };  
    //Execute the activity with a parameter dictionary  
                WorkflowInvoker.Invoke(dynamicWorkflow, new Dictionary<string, object> { { "Text", "Hello World!" } });  
                Console.ReadLine();  
    ```  
  
6. <span data-ttu-id="7c49f-124">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7c49f-124">Execute the application.</span></span> <span data-ttu-id="7c49f-125">Una ventana de consola con el texto "Hola mundo!"</span><span class="sxs-lookup"><span data-stu-id="7c49f-125">A console window with the text "Hello World!"</span></span> <span data-ttu-id="7c49f-126">aparecerá.</span><span class="sxs-lookup"><span data-stu-id="7c49f-126">displays.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-xaml"></a><span data-ttu-id="7c49f-127">Para crear una actividad en el tiempo de ejecución usando XAML</span><span class="sxs-lookup"><span data-stu-id="7c49f-127">To create an activity at runtime using XAML</span></span>  
  
1. <span data-ttu-id="7c49f-128">Abra Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="7c49f-128">Open Visual Studio 2010.</span></span>  
  
2. <span data-ttu-id="7c49f-129">Seleccione **archivo**, **nuevo**, **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="7c49f-129">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="7c49f-130">Seleccione **flujo de trabajo 4,0** en **Visual C#** en la ventana **tipos de proyecto** y seleccione el nodo **V2010** .</span><span class="sxs-lookup"><span data-stu-id="7c49f-130">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="7c49f-131">Seleccione **aplicación de consola de flujos de trabajo** en la ventana **plantillas** .</span><span class="sxs-lookup"><span data-stu-id="7c49f-131">Select  **Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="7c49f-132">Proporcione el nombre siguiente al nuevo proyecto: DynamicActivitySample.</span><span class="sxs-lookup"><span data-stu-id="7c49f-132">Name the new project DynamicActivitySample.</span></span>  
  
3. <span data-ttu-id="7c49f-133">Abra Workflow1.xaml en el proyecto HelloActivity.</span><span class="sxs-lookup"><span data-stu-id="7c49f-133">Open Workflow1.xaml in the HelloActivity project.</span></span> <span data-ttu-id="7c49f-134">Haga clic en la opción **argumentos** en la parte inferior del diseñador.</span><span class="sxs-lookup"><span data-stu-id="7c49f-134">Click the **Arguments** option at the bottom of the designer.</span></span> <span data-ttu-id="7c49f-135">Cree un nuevo argumento `In` llamado `TextToWrite` de tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="7c49f-135">Create a new `In` argument called `TextToWrite` of type `String`.</span></span>  
  
4. <span data-ttu-id="7c49f-136">Arrastre una actividad **WriteLine** de la sección **primitivas** del cuadro de herramientas a la superficie del diseñador.</span><span class="sxs-lookup"><span data-stu-id="7c49f-136">Drag a **WriteLine** activity from the **Primitives** section of the toolbox onto the designer surface.</span></span> <span data-ttu-id="7c49f-137">Asigne el valor `TextToWrite` a la propiedad **Text** de la actividad.</span><span class="sxs-lookup"><span data-stu-id="7c49f-137">Assign the value `TextToWrite` to the **Text** property of the activity.</span></span>  
  
5. <span data-ttu-id="7c49f-138">Abra Program.cs.</span><span class="sxs-lookup"><span data-stu-id="7c49f-138">Open Program.cs.</span></span> <span data-ttu-id="7c49f-139">Agregue la siguiente directiva a la parte superior del archivo.</span><span class="sxs-lookup"><span data-stu-id="7c49f-139">Add the following directive to the top of the file.</span></span>  
  
    ```csharp  
    using System.Activities.XamlIntegration;  
    ```  
  
6. <span data-ttu-id="7c49f-140">Reemplace el contenido del método `Main` con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="7c49f-140">Replace the contents of the `Main` method with the following code.</span></span>  
  
    ```csharp  
    Activity act2 = ActivityXamlServices.Load(@"Workflow1.xaml");  
                    results = WorkflowInvoker.Invoke(act2, new Dictionary<string, object> { { "TextToWrite", "HelloWorld!" } });  
    Console.ReadLine();  
    ```  
  
7. <span data-ttu-id="7c49f-141">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7c49f-141">Execute the application.</span></span> <span data-ttu-id="7c49f-142">Una ventana de consola con el texto "Hola mundo!"</span><span class="sxs-lookup"><span data-stu-id="7c49f-142">A console window with the text "Hello World!"</span></span> <span data-ttu-id="7c49f-143">Aparece .</span><span class="sxs-lookup"><span data-stu-id="7c49f-143">appears.</span></span>  
  
8. <span data-ttu-id="7c49f-144">Haga clic con el botón secundario en el archivo Workflow1. XAML en el **Explorador de soluciones** y seleccione **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="7c49f-144">Right-click the Workflow1.xaml file in the **Solution Explorer** and select **View Code**.</span></span> <span data-ttu-id="7c49f-145">Tenga en cuenta que la clase de actividad se crea con `x:Class` y la propiedad se crea con `x:Property`.</span><span class="sxs-lookup"><span data-stu-id="7c49f-145">Note that the activity class is created with `x:Class` and the property is created with `x:Property`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c49f-146">Consulta también</span><span class="sxs-lookup"><span data-stu-id="7c49f-146">See also</span></span>

- [<span data-ttu-id="7c49f-147">Crear flujos de trabajo, actividades y expresiones mediante código imperativo</span><span class="sxs-lookup"><span data-stu-id="7c49f-147">Authoring Workflows, Activities, and Expressions Using Imperative Code</span></span>](authoring-workflows-activities-and-expressions-using-imperative-code.md)
