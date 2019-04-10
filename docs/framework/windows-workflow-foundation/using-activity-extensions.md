---
title: Utilizar extensiones de actividad
ms.date: 03/30/2017
ms.assetid: 500eb96a-c009-4247-b6b5-b36faffdf715
ms.openlocfilehash: e524f7e7127eb215be85b0c317474eee70830c2b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321294"
---
# <a name="using-activity-extensions"></a><span data-ttu-id="4c69d-102">Utilizar extensiones de actividad</span><span class="sxs-lookup"><span data-stu-id="4c69d-102">Using Activity Extensions</span></span>
<span data-ttu-id="4c69d-103">Las actividades pueden interactuar con extensiones de aplicación de flujo de trabajo que permiten al host proporcionar función adicional que no se modela explícitamente en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4c69d-103">Activities can interact with workflow application extensions that allow the host to provide additional functionality that is not explicitly modeled in the workflow.</span></span>  <span data-ttu-id="4c69d-104">En este tema se describe cómo crear y utilizar una extensión para contar el número de veces que la actividad se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="4c69d-104">This topic describes how to create and use an extension to count the number of times the activity executes.</span></span>

### <a name="to-use-an-activity-extension-to-count-executions"></a><span data-ttu-id="4c69d-105">Utilizar una extensión de actividad para contar las ejecuciones</span><span class="sxs-lookup"><span data-stu-id="4c69d-105">To use an activity extension to count executions</span></span>

1. <span data-ttu-id="4c69d-106">Abra Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="4c69d-106">Open Visual Studio 2010.</span></span> <span data-ttu-id="4c69d-107">Seleccione **nueva**, **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="4c69d-107">Select **New**, **Project**.</span></span> <span data-ttu-id="4c69d-108">En el **Visual C#** nodo, seleccione **flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="4c69d-108">Under the **Visual C#** node, select **Workflow**.</span></span>  <span data-ttu-id="4c69d-109">Seleccione **aplicación de consola de flujos de trabajo** desde la lista de plantillas.</span><span class="sxs-lookup"><span data-stu-id="4c69d-109">Select **Workflow Console Application** from the list of templates.</span></span> <span data-ttu-id="4c69d-110">Dé un nombre al proyecto `Extensions`.</span><span class="sxs-lookup"><span data-stu-id="4c69d-110">Name the project `Extensions`.</span></span> <span data-ttu-id="4c69d-111">Haga clic en **Aceptar** para crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4c69d-111">Click **OK** to create the project.</span></span>

2. <span data-ttu-id="4c69d-112">Agregar un `using` instrucción en el archivo Program.cs para el **System.Collections.Generic** espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="4c69d-112">Add a `using` statement in the Program.cs file for the **System.Collections.Generic** namespace.</span></span>

    ```
    using System.Collections.Generic;
    ```

3. <span data-ttu-id="4c69d-113">En el archivo Program.cs, cree una nueva clase denominada **ExecutionCountExtension**.</span><span class="sxs-lookup"><span data-stu-id="4c69d-113">In the Program.cs file, create a new class named **ExecutionCountExtension**.</span></span> <span data-ttu-id="4c69d-114">El código siguiente crea una extensión de flujo de trabajo que realiza el seguimiento de los identificadores de instancia cuando su **registrar** se llama al método.</span><span class="sxs-lookup"><span data-stu-id="4c69d-114">The following code creates a workflow extension that tracks instance IDs when its **Register** method is called.</span></span>

    ```
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

4. <span data-ttu-id="4c69d-115">Crear una actividad que consume el **ExecutionCountExtension**.</span><span class="sxs-lookup"><span data-stu-id="4c69d-115">Create an activity that consumes the **ExecutionCountExtension**.</span></span> <span data-ttu-id="4c69d-116">El código siguiente define una actividad que recupera el **ExecutionCountExtension** objeto desde el tiempo de ejecución y llama a su **registrar** método cuando se ejecuta la actividad.</span><span class="sxs-lookup"><span data-stu-id="4c69d-116">The following code defines an activity that retrieves the **ExecutionCountExtension** object from the runtime and calls its **Register** method when the activity executes.</span></span>

    ```
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

5. <span data-ttu-id="4c69d-117">Implemente la actividad en el **Main** método del archivo program.cs.</span><span class="sxs-lookup"><span data-stu-id="4c69d-117">Implement the activity in the **Main** method of the program.cs file.</span></span> <span data-ttu-id="4c69d-118">El siguiente código contiene los métodos para generar dos flujos de trabajo diferentes, ejecuta cada flujo de trabajo varias veces y muestra los datos resultantes que se contienen en la extensión.</span><span class="sxs-lookup"><span data-stu-id="4c69d-118">The following code contains methods to generate two different workflows, execute each workflow several times, and display the resulting data that is contained in the extension.</span></span>

    ```
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
