---
title: Utilizar extensiones de actividad
ms.date: 03/30/2017
ms.assetid: 500eb96a-c009-4247-b6b5-b36faffdf715
ms.openlocfilehash: 3a9cabda9fe92b2ea4e708da8f853f3029328775
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293291"
---
# <a name="using-activity-extensions"></a>Utilizar extensiones de actividad

Las actividades pueden interactuar con extensiones de aplicación de flujo de trabajo que permiten al host proporcionar función adicional que no se modela explícitamente en el flujo de trabajo.  En este tema se describe cómo crear y utilizar una extensión para contar el número de veces que la actividad se ejecuta.

### <a name="to-use-an-activity-extension-to-count-executions"></a>Utilizar una extensión de actividad para contar las ejecuciones

1. Abra Visual Studio 2010. Seleccione **nuevo**, **proyecto**. En el nodo **Visual C#** , seleccione **flujo de trabajo**.  Seleccione **aplicación de consola de flujos de trabajo** en la lista de plantillas. Dé un nombre al proyecto `Extensions`. Haga clic en **Aceptar** para crear el proyecto.

2. Agregue una `using` instrucción en el archivo Program.CS para el espacio de nombres **System. Collections. Generic** .

    ```csharp
    using System.Collections.Generic;
    ```

3. En el archivo Program.cs, cree una nueva clase denominada **ExecutionCountExtension**. En el código siguiente se crea una extensión de flujo de trabajo que realiza el seguimiento de los identificadores de instancia cuando se llama a su método de **registro** .

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

4. Cree una actividad que consuma **ExecutionCountExtension**. En el código siguiente se define una actividad que recupera el objeto **ExecutionCountExtension** del Runtime y llama a su método de **registro** cuando se ejecuta la actividad.

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

5. Implemente la actividad en el método **Main** del archivo Program.cs. El siguiente código contiene los métodos para generar dos flujos de trabajo diferentes, ejecuta cada flujo de trabajo varias veces y muestra los datos resultantes que se contienen en la extensión.

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
