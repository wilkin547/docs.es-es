---
title: "Utilizar extensiones de actividad | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 500eb96a-c009-4247-b6b5-b36faffdf715
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Utilizar extensiones de actividad
Las actividades pueden interactuar con extensiones de aplicación de flujo de trabajo que permiten al host proporcionar función adicional que no se modela explícitamente en el flujo de trabajo.En este tema se describe cómo crear y utilizar una extensión para contar el número de veces que la actividad se ejecuta.  
  
### Utilizar una extensión de actividad para contar las ejecuciones  
  
1.  Abra [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].Seleccione **Nuevo**, **Proyecto**.Bajo el nodo **Visual C\#**, seleccione **Flujo de trabajo**.Seleccione **Aplicación de consola de flujos de trabajo** en la lista de plantillas.Asigne al proyecto el nombre `Extensiones`.Haga clic en **Aceptar** para crear el proyecto.  
  
2.  Agregue una instrucción `using` para el espacio de nombres **System.Collections.Generic** en el archivo Program.cs.  
  
    ```  
    using System.Collections.Generic;  
  
    ```  
  
3.  En el archivo Program.cs, cree una nueva clase denominada **ExecutionCountExtension**.El siguiente código crea una extensión de flujo de trabajo que realiza el seguimiento de los identificadores de instancia cuando se llama al método **Register**.  
  
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
  
4.  Cree una actividad que use **ExecutionCountExtension**.El siguiente código define una actividad que recupera el objeto **ExecutionCountExtension** del runtime y llama a su método **Register** cuando la actividad se ejecuta.  
  
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
  
5.  Implemente la actividad en el método **Main** del archivo program.cs.El siguiente código contiene los métodos para generar dos flujos de trabajo diferentes, ejecuta cada flujo de trabajo varias veces y muestra los datos resultantes que se contienen en la extensión.  
  
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