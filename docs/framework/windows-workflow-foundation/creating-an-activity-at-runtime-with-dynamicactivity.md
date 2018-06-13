---
title: Crear una actividad en el tiempo de ejecución con DynamicActivity
ms.date: 03/30/2017
ms.assetid: 1af85cc6-912d-449e-90c5-c5db3eca5ace
ms.openlocfilehash: 0450a56059083f355f3fd71d95c83bf8dd1cf0e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515179"
---
# <a name="creating-an-activity-at-runtime-with-dynamicactivity"></a><span data-ttu-id="aa269-102">Crear una actividad en el tiempo de ejecución con DynamicActivity</span><span class="sxs-lookup"><span data-stu-id="aa269-102">Creating an Activity at Runtime with DynamicActivity</span></span>
<span data-ttu-id="aa269-103"><xref:System.Activities.DynamicActivity> es una clase concreta sellada con un constructor público.</span><span class="sxs-lookup"><span data-stu-id="aa269-103"><xref:System.Activities.DynamicActivity> is a concrete, sealed class with a public constructor.</span></span> <span data-ttu-id="aa269-104"><xref:System.Activities.DynamicActivity> se puede usar para ensamblar la funcionalidad de actividad en tiempo de ejecución usando un DOM de actividad.</span><span class="sxs-lookup"><span data-stu-id="aa269-104"><xref:System.Activities.DynamicActivity> can be used to assemble activity functionality at runtime using an activity DOM.</span></span>  
  
## <a name="dynamicactivity-features"></a><span data-ttu-id="aa269-105">Características de DynamicActivity</span><span class="sxs-lookup"><span data-stu-id="aa269-105">DynamicActivity Features</span></span>  
 <span data-ttu-id="aa269-106"><xref:System.Activities.DynamicActivity> tiene acceso a las propiedades, argumentos y variables de ejecución pero no a los servicios en tiempo de ejecución como la programación de actividades secundarias o el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="aa269-106"><xref:System.Activities.DynamicActivity> has access to execution properties, arguments and variables, but no access to run-time services such as scheduling child activities or tracking.</span></span>  
  
 <span data-ttu-id="aa269-107">Las propiedades de nivel superior se pueden establecer con los objetos <xref:System.Activities.Argument> de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="aa269-107">Top-level properties can be set using workflow <xref:System.Activities.Argument> objects.</span></span> <span data-ttu-id="aa269-108">En código imperativo, estos argumentos se crean usando las propiedades CLR en un nuevo tipo.</span><span class="sxs-lookup"><span data-stu-id="aa269-108">In imperative code, these arguments are created using CLR properties on a new type.</span></span> <span data-ttu-id="aa269-109">En XAML, se declaran con las etiquetas `x:Class` y `x:Member`.</span><span class="sxs-lookup"><span data-stu-id="aa269-109">In XAML, they are declared using `x:Class` and `x:Member` tags.</span></span>  
  
 <span data-ttu-id="aa269-110">Las actividades se construyeron mediante la interfaz <xref:System.Activities.DynamicActivity> con el diseñador usando <xref:System.ComponentModel.ICustomTypeDescriptor>.</span><span class="sxs-lookup"><span data-stu-id="aa269-110">Activities constructed using <xref:System.Activities.DynamicActivity> interface with the designer using <xref:System.ComponentModel.ICustomTypeDescriptor>.</span></span> <span data-ttu-id="aa269-111">Las actividades creadas en el diseñador se pueden cargar dinámicamente mediante <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, tal y como se muestra en el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="aa269-111">Activities created in the designer can be loaded dynamically using <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, as demonstrated in the following procedure.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-imperative-code"></a><span data-ttu-id="aa269-112">Para crear una actividad en el tiempo de ejecución usando el código imperativo</span><span class="sxs-lookup"><span data-stu-id="aa269-112">To create an activity at runtime using imperative code</span></span>  
  
1.  <span data-ttu-id="aa269-113">Abra [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa269-113">Open[!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="aa269-114">Seleccione **archivo**, **nueva**, **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="aa269-114">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="aa269-115">Seleccione **Workflow 4.0** en **Visual C#** en el **tipos de proyecto** ventana y seleccione el **v2010** nodo.</span><span class="sxs-lookup"><span data-stu-id="aa269-115">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="aa269-116">Seleccione **aplicación de consola de flujos de trabajo secuenciales** en el **plantillas** ventana.</span><span class="sxs-lookup"><span data-stu-id="aa269-116">Select **Sequential Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="aa269-117">Proporcione el nombre siguiente al nuevo proyecto: DynamicActivitySample.</span><span class="sxs-lookup"><span data-stu-id="aa269-117">Name the new project DynamicActivitySample.</span></span>  
  
3.  <span data-ttu-id="aa269-118">Haga clic en Workflow1.xaml en el proyecto HelloActivity y seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="aa269-118">Right-click Workflow1.xaml in the HelloActivity project and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="aa269-119">Abra Program.cs.</span><span class="sxs-lookup"><span data-stu-id="aa269-119">Open Program.cs.</span></span> <span data-ttu-id="aa269-120">Agregue la siguiente directiva a la parte superior del archivo.</span><span class="sxs-lookup"><span data-stu-id="aa269-120">Add the following directive to the top of the file.</span></span>  
  
    ```  
    using System.Collections.Generic;  
    ```  
  
5.  <span data-ttu-id="aa269-121">Sustituya el contenido del método `Main` con el siguiente código, que crea una actividad <xref:System.Activities.Statements.Sequence> que contiene una actividad <xref:System.Activities.Statements.WriteLine> única y la asigna a la propiedad <xref:System.Activities.DynamicActivity.Implementation%2A> de una nueva actividad dinámica.</span><span class="sxs-lookup"><span data-stu-id="aa269-121">Replace the contents of the `Main` method with the following code, which creates a <xref:System.Activities.Statements.Sequence> activity that contains a single <xref:System.Activities.Statements.WriteLine> activity and assigns it to the <xref:System.Activities.DynamicActivity.Implementation%2A> property of a new dynamic activity.</span></span>  
  
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
  
6.  <span data-ttu-id="aa269-122">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa269-122">Execute the application.</span></span> <span data-ttu-id="aa269-123">Una ventana de consola con el texto "¡Hello World!"</span><span class="sxs-lookup"><span data-stu-id="aa269-123">A console window with the text "Hello World!"</span></span> <span data-ttu-id="aa269-124">muestra.</span><span class="sxs-lookup"><span data-stu-id="aa269-124">displays.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-xaml"></a><span data-ttu-id="aa269-125">Para crear una actividad en el tiempo de ejecución usando XAML</span><span class="sxs-lookup"><span data-stu-id="aa269-125">To create an activity at runtime using XAML</span></span>  
  
1.  <span data-ttu-id="aa269-126">Abra [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa269-126">Open [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="aa269-127">Seleccione **archivo**, **nueva**, **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="aa269-127">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="aa269-128">Seleccione **Workflow 4.0** en **Visual C#** en el **tipos de proyecto** ventana y seleccione el **v2010** nodo.</span><span class="sxs-lookup"><span data-stu-id="aa269-128">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="aa269-129">Seleccione **aplicación de consola de flujos de trabajo** en el **plantillas** ventana.</span><span class="sxs-lookup"><span data-stu-id="aa269-129">Select  **Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="aa269-130">Proporcione el nombre siguiente al nuevo proyecto: DynamicActivitySample.</span><span class="sxs-lookup"><span data-stu-id="aa269-130">Name the new project DynamicActivitySample.</span></span>  
  
3.  <span data-ttu-id="aa269-131">Abra Workflow1.xaml en el proyecto HelloActivity.</span><span class="sxs-lookup"><span data-stu-id="aa269-131">Open Workflow1.xaml in the HelloActivity project.</span></span> <span data-ttu-id="aa269-132">Haga clic en el **argumentos** opción en la parte inferior del diseñador.</span><span class="sxs-lookup"><span data-stu-id="aa269-132">Click the **Arguments** option at the bottom of the designer.</span></span> <span data-ttu-id="aa269-133">Cree un nuevo argumento `In` llamado `TextToWrite` de tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="aa269-133">Create a new `In` argument called `TextToWrite` of type `String`.</span></span>  
  
4.  <span data-ttu-id="aa269-134">Arrastre un **WriteLine** actividad desde la **primitivas** sección del cuadro de herramientas a la superficie del diseñador.</span><span class="sxs-lookup"><span data-stu-id="aa269-134">Drag a **WriteLine** activity from the **Primitives** section of the toolbox onto the designer surface.</span></span> <span data-ttu-id="aa269-135">Asigne el valor `TextToWrite` a la **texto** propiedad de la actividad.</span><span class="sxs-lookup"><span data-stu-id="aa269-135">Assign the value `TextToWrite` to the **Text** property of the activity.</span></span>  
  
5.  <span data-ttu-id="aa269-136">Abra Program.cs.</span><span class="sxs-lookup"><span data-stu-id="aa269-136">Open Program.cs.</span></span> <span data-ttu-id="aa269-137">Agregue la siguiente directiva a la parte superior del archivo.</span><span class="sxs-lookup"><span data-stu-id="aa269-137">Add the following directive to the top of the file.</span></span>  
  
    ```  
    using System.Activities.XamlIntegration;  
    ```  
  
6.  <span data-ttu-id="aa269-138">Reemplace el contenido del método `Main` con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="aa269-138">Replace the contents of the `Main` method with the following code.</span></span>  
  
    ```  
    Activity act2 = ActivityXamlServices.Load(@"Workflow1.xaml");  
                    results = WorkflowInvoker.Invoke(act2, new Dictionary<string, object> { { "TextToWrite", "HelloWorld!" } });  
    Console.ReadLine();  
    ```  
  
7.  <span data-ttu-id="aa269-139">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa269-139">Execute the application.</span></span> <span data-ttu-id="aa269-140">Una ventana de consola con el texto "¡Hello World!"</span><span class="sxs-lookup"><span data-stu-id="aa269-140">A console window with the text "Hello World!"</span></span> <span data-ttu-id="aa269-141">aparece.</span><span class="sxs-lookup"><span data-stu-id="aa269-141">appears.</span></span>  
  
8.  <span data-ttu-id="aa269-142">Haga clic en el archivo Workflow1.xaml en el **el Explorador de soluciones** y seleccione **ver código**.</span><span class="sxs-lookup"><span data-stu-id="aa269-142">Right-click the Workflow1.xaml file in the **Solution Explorer** and select **View Code**.</span></span> <span data-ttu-id="aa269-143">Tenga en cuenta que la clase de actividad se crea con `x:Class` y la propiedad se crea con `x:Property`.</span><span class="sxs-lookup"><span data-stu-id="aa269-143">Note that the activity class is created with `x:Class` and the property is created with `x:Property`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa269-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa269-144">See Also</span></span>  
 [<span data-ttu-id="aa269-145">Creación de flujos de trabajo, actividades y expresiones mediante código imperativo</span><span class="sxs-lookup"><span data-stu-id="aa269-145">Authoring Workflows, Activities, and Expressions Using Imperative Code</span></span>](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md)  
 [<span data-ttu-id="aa269-146">Creación de DynamicActivity</span><span class="sxs-lookup"><span data-stu-id="aa269-146">DynamicActivity Creation</span></span>](../../../docs/framework/windows-workflow-foundation/samples/dynamicactivity-creation.md)
