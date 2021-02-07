---
description: 'Más información acerca de: uso de extensiones de actividad'
title: Utilizar extensiones de actividad
ms.date: 03/30/2017
ms.assetid: 500eb96a-c009-4247-b6b5-b36faffdf715
ms.openlocfilehash: d0286850bf685497d3a2471a3b4e0db4630070b1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755075"
---
# <a name="using-activity-extensions"></a><span data-ttu-id="b95ea-103">Utilizar extensiones de actividad</span><span class="sxs-lookup"><span data-stu-id="b95ea-103">Using Activity Extensions</span></span>

<span data-ttu-id="b95ea-104">Las actividades pueden interactuar con extensiones de aplicación de flujo de trabajo que permiten al host proporcionar función adicional que no se modela explícitamente en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b95ea-104">Activities can interact with workflow application extensions that allow the host to provide additional functionality that is not explicitly modeled in the workflow.</span></span>  <span data-ttu-id="b95ea-105">En este tema se describe cómo crear y utilizar una extensión para contar el número de veces que la actividad se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="b95ea-105">This topic describes how to create and use an extension to count the number of times the activity executes.</span></span>

### <a name="to-use-an-activity-extension-to-count-executions"></a><span data-ttu-id="b95ea-106">Utilizar una extensión de actividad para contar las ejecuciones</span><span class="sxs-lookup"><span data-stu-id="b95ea-106">To use an activity extension to count executions</span></span>

1. <span data-ttu-id="b95ea-107">Abra Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="b95ea-107">Open Visual Studio 2010.</span></span> <span data-ttu-id="b95ea-108">Seleccione **nuevo**, **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="b95ea-108">Select **New**, **Project**.</span></span> <span data-ttu-id="b95ea-109">En el nodo **Visual C#** , seleccione **flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="b95ea-109">Under the **Visual C#** node, select **Workflow**.</span></span>  <span data-ttu-id="b95ea-110">Seleccione **aplicación de consola de flujos de trabajo** en la lista de plantillas.</span><span class="sxs-lookup"><span data-stu-id="b95ea-110">Select **Workflow Console Application** from the list of templates.</span></span> <span data-ttu-id="b95ea-111">Dé un nombre al proyecto `Extensions`.</span><span class="sxs-lookup"><span data-stu-id="b95ea-111">Name the project `Extensions`.</span></span> <span data-ttu-id="b95ea-112">Haga clic en **Aceptar** para crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b95ea-112">Click **OK** to create the project.</span></span>

2. <span data-ttu-id="b95ea-113">Agregue una `using` instrucción en el archivo Program.CS para el espacio de nombres **System. Collections. Generic** .</span><span class="sxs-lookup"><span data-stu-id="b95ea-113">Add a `using` statement in the Program.cs file for the **System.Collections.Generic** namespace.</span></span>

    ```csharp
    using System.Collections.Generic;
    ```

3. <span data-ttu-id="b95ea-114">En el archivo Program.cs, cree una nueva clase denominada **ExecutionCountExtension**.</span><span class="sxs-lookup"><span data-stu-id="b95ea-114">In the Program.cs file, create a new class named **ExecutionCountExtension**.</span></span> <span data-ttu-id="b95ea-115">En el código siguiente se crea una extensión de flujo de trabajo que realiza el seguimiento de los identificadores de instancia cuando se llama a su método de **registro** .</span><span class="sxs-lookup"><span data-stu-id="b95ea-115">The following code creates a workflow extension that tracks instance IDs when its **Register** method is called.</span></span>

    ```csharp
    // This extension collects a list of workflow Ids
    public class ExecutionCountExtension
    {
        IList<Guid> instances = new List<Guid>();

        public int ExecutionCount
        {
            get
            {
                return this.instances.Count;
            }
        }

        public IEnumerable<Guid> InstanceIds
        {
            get
            {
                return this.instances;
            }
        }

        public void Register(Guid activityInstanceId)
        {
            if (!this.instances.Contains<Guid>(activityInstanceId))
            {
                instances.Add(activityInstanceId);
            }
        }
    }
    ```

4. <span data-ttu-id="b95ea-116">Cree una actividad que consuma **ExecutionCountExtension**.</span><span class="sxs-lookup"><span data-stu-id="b95ea-116">Create an activity that consumes the **ExecutionCountExtension**.</span></span> <span data-ttu-id="b95ea-117">En el código siguiente se define una actividad que recupera el objeto **ExecutionCountExtension** del Runtime y llama a su método de **registro** cuando se ejecuta la actividad.</span><span class="sxs-lookup"><span data-stu-id="b95ea-117">The following code defines an activity that retrieves the **ExecutionCountExtension** object from the runtime and calls its **Register** method when the activity executes.</span></span>

    ```csharp
    // Activity that consumes an extension provided by the host. If the extension is available
    // in the context, it will invoke (in this case, registers the Id of the executing workflow)
    public class MyActivity: CodeActivity
    {
        protected override void Execute(CodeActivityContext context)
        {
            ExecutionCountExtension ext = context.GetExtension<ExecutionCountExtension>();
            if (ext != null)
            {
                ext.Register(context.WorkflowInstanceId);
            }

        }
    }
    ```

5. <span data-ttu-id="b95ea-118">Implemente la actividad en el método **Main** del archivo Program.cs.</span><span class="sxs-lookup"><span data-stu-id="b95ea-118">Implement the activity in the **Main** method of the program.cs file.</span></span> <span data-ttu-id="b95ea-119">El siguiente código contiene los métodos para generar dos flujos de trabajo diferentes, ejecuta cada flujo de trabajo varias veces y muestra los datos resultantes que se contienen en la extensión.</span><span class="sxs-lookup"><span data-stu-id="b95ea-119">The following code contains methods to generate two different workflows, execute each workflow several times, and display the resulting data that is contained in the extension.</span></span>

    ```csharp
    class Program
    {
        // Creates a workflow that uses the activity that consumes the extension
        static Activity CreateWorkflow1()
        {
            return new Sequence
            {
                Activities =
                {
                    new MyActivity()
                }
            };
        }

        // Creates a workflow that uses two instances of the activity that consumes the extension
        static Activity CreateWorkflow2()
        {
            return new Sequence
            {
                Activities =
                {
                    new MyActivity(),
                    new MyActivity()
                }
            };
        }

        static void Main(string[] args)
        {
            // create the extension
            ExecutionCountExtension executionCountExt = new ExecutionCountExtension();

            // configure the first invoker and execute 3 times
            WorkflowInvoker invoker = new WorkflowInvoker(CreateWorkflow1());
            invoker.Extensions.Add(executionCountExt);
            invoker.Invoke();
            invoker.Invoke();
            invoker.Invoke();

            // configure the second invoker and execute 2 times
            WorkflowInvoker invoker2 = new WorkflowInvoker(CreateWorkflow2());
            invoker2.Extensions.Add(executionCountExt);
            invoker2.Invoke();
            invoker2.Invoke();

            // show the data in the extension
            Console.WriteLine("Executed {0} times", executionCountExt.ExecutionCount);
            executionCountExt.InstanceIds.ToList().ForEach(i => Console.WriteLine("...{0}", i));
        }
    }
    ```
