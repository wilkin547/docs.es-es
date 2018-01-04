---
title: "Acceder a la información de identidad de un servicio de flujo de trabajo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b832127-b35b-468e-a45f-321381170cbc
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 06638a9f5aa031bec07a9aac510ce832f75980fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="accessing-identity-information-inside-a-workflow-service"></a><span data-ttu-id="517db-102">Acceder a la información de identidad de un servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="517db-102">Accessing Identity Information inside a Workflow Service</span></span>
<span data-ttu-id="517db-103">Para tener acceso a la información de identidad en un servicio de flujo de trabajo, debe implementar la interfaz <xref:System.ServiceModel.Activities.IReceiveMessageCallback> en una propiedad de ejecución personalizada.</span><span class="sxs-lookup"><span data-stu-id="517db-103">To access identity information inside a workflow service, you must implement the <xref:System.ServiceModel.Activities.IReceiveMessageCallback> interface in a custom execution property.</span></span> <span data-ttu-id="517db-104">En el método <xref:System.ServiceModel.Activities.IReceiveMessageCallback.OnReceiveMessage(System.ServiceModel.OperationContext,System.Activities.ExecutionProperties)> puede acceder a una clase <xref:System.ServiceModel.OperationContext.ServiceSecurityContext> para acceder a la información de identidad.</span><span class="sxs-lookup"><span data-stu-id="517db-104">In the <xref:System.ServiceModel.Activities.IReceiveMessageCallback.OnReceiveMessage(System.ServiceModel.OperationContext,System.Activities.ExecutionProperties)> method you can access the <xref:System.ServiceModel.OperationContext.ServiceSecurityContext> to access identity information.</span></span> <span data-ttu-id="517db-105">Este tema le guiará en la implementación de esta propiedad de ejecución, así como una actividad personalizada que mostrará esta propiedad en la actividad <xref:System.ServiceModel.Activities.Receive> en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="517db-105">This topic will walk you through implementing this execution property, as well as a custom activity that will surface this property to the <xref:System.ServiceModel.Activities.Receive> activity at runtime.</span></span>  <span data-ttu-id="517db-106">La actividad personalizada implementará el mismo comportamiento que un <!--zz <xref:System.ServiceModel.Activities.Sequence>--> `System.ServiceModel.Activities.Sequence` actividad, excepto que, cuando un <xref:System.ServiceModel.Activities.Receive> se coloca dentro de él, el <xref:System.ServiceModel.Activities.IReceiveMessageCallback> se llama y se recuperará la información de identidad.</span><span class="sxs-lookup"><span data-stu-id="517db-106">The custom activity will implement the same behavior as a <!--zz <xref:System.ServiceModel.Activities.Sequence>--> `System.ServiceModel.Activities.Sequence` activity, except that when a <xref:System.ServiceModel.Activities.Receive> is placed inside of it, the <xref:System.ServiceModel.Activities.IReceiveMessageCallback> will be called and the identity information will be retrieved.</span></span>  
  
### <a name="implement-ireceivemessagecallback"></a><span data-ttu-id="517db-107">Implementar IReceiveMessageCallback</span><span class="sxs-lookup"><span data-stu-id="517db-107">Implement IReceiveMessageCallback</span></span>  
  
1.  <span data-ttu-id="517db-108">Cree una solución [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] vacía.</span><span class="sxs-lookup"><span data-stu-id="517db-108">Create an empty [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] solution.</span></span>  
  
2.  <span data-ttu-id="517db-109">Agregue a la solución una nueva aplicación de consola denominada `Service`.</span><span class="sxs-lookup"><span data-stu-id="517db-109">Add a new console application called `Service` to the solution.</span></span>  
  
3.  <span data-ttu-id="517db-110">Agregue referencias a los siguientes ensamblados:</span><span class="sxs-lookup"><span data-stu-id="517db-110">Add references to the following assemblies:</span></span>  
  
    1.  <span data-ttu-id="517db-111">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="517db-111">System.Runtime.Serialization</span></span>  
  
    2.  <span data-ttu-id="517db-112">System.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="517db-112">System.ServiceModel</span></span>  
  
    3.  <span data-ttu-id="517db-113">System.ServiceModel.Activities</span><span class="sxs-lookup"><span data-stu-id="517db-113">System.ServiceModel.Activities</span></span>  
  
4.  <span data-ttu-id="517db-114">Agregue una nueva clase denominada `AccessIdentityCallback` e implemente <xref:System.ServiceModel.Activities.IReceiveMessageCallback> como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="517db-114">Add a new class called `AccessIdentityCallback` and implement <xref:System.ServiceModel.Activities.IReceiveMessageCallback> as shown in the following example.</span></span>  
  
    ```csharp  
    class AccessIdentityCallback : IReceiveMessageCallback  
    {  
       public void OnReceiveMessage(System.ServiceModel.OperationContext operationContext, System.Activities.ExecutionProperties activityExecutionProperties)  
       {  
          try  
          {  
             Console.WriteLine("Received a message from a workflow with the following identity");  
             Console.WriteLine("Windows Identity Name: {0}", operationContext.ServiceSecurityContext.WindowsIdentity.Name);  
             Console.WriteLine("Windows Identity User: {0}", operationContext.ServiceSecurityContext.WindowsIdentity.User);  
             Console.WriteLine("Windows Identity IsAuthenticated: {0}", operationContext.ServiceSecurityContext.WindowsIdentity.IsAuthenticated);  
          }            
          catch (Exception ex)  
          {  
             Console.WriteLine("An exception occurred: " + ex.Message);  
          }  
        }  
    }  
    ```  
  
     <span data-ttu-id="517db-115">Este código usa la clase <xref:System.ServiceModel.OperationContext> pasada en el método para acceder a la información de identidad.</span><span class="sxs-lookup"><span data-stu-id="517db-115">This code uses the <xref:System.ServiceModel.OperationContext> passed into the method to access identity information.</span></span>  
  
### <a name="implement-a-native-activity-to-add-the-ireceivemessagecallback-implementation-to-the-nativeactivitycontext"></a><span data-ttu-id="517db-116">Implementar una actividad nativa para agregar la implementación de IReceiveMessageCallback a NativeActivityContext</span><span class="sxs-lookup"><span data-stu-id="517db-116">Implement a Native activity to add the IReceiveMessageCallback implementation to the NativeActivityContext</span></span>  
  
1.  <span data-ttu-id="517db-117">Agregue una nueva clase derivada de <xref:System.Activities.NativeActivity> denominada `AccessIdentityScope`.</span><span class="sxs-lookup"><span data-stu-id="517db-117">Add a new class derived from <xref:System.Activities.NativeActivity> called `AccessIdentityScope`.</span></span>  
  
2.  <span data-ttu-id="517db-118">Agregue variables locales para realizar el seguimiento de las actividades secundarias, variables, el índice de actividad actual y una devolución de llamada <xref:System.Activities.CompletionCallback>.</span><span class="sxs-lookup"><span data-stu-id="517db-118">Add local variables to keep track of child activities, variables, current activity index, and a <xref:System.Activities.CompletionCallback> callback.</span></span>  
  
    ```  
    public sealed class AccessIdentityScope : NativeActivity  
    {  
        Collection<Activity> children;  
        Collection<Variable> variables;  
        Variable<int> currentIndex;  
        CompletionCallback onChildComplete;  
    }  
    ```  
  
3.  <span data-ttu-id="517db-119">Implemente el constructor</span><span class="sxs-lookup"><span data-stu-id="517db-119">Implement the constructor</span></span>  
  
    ```  
    public AccessIdentityScope() : base()  
    {  
        this.children = new Collection<Activity>();  
        this.variables = new Collection<Variable>();  
        this.currentIndex = new Variable<int>();  
    }  
    ```  
  
4.  <span data-ttu-id="517db-120">Implemente las propiedades `Activities` y `Variables`.</span><span class="sxs-lookup"><span data-stu-id="517db-120">Implement the `Activities` and `Variables` properties.</span></span>  
  
    ```  
    public Collection<Activity> Activities  
    {  
         get { return this.children; }  
    }  
  
    public Collection<Variable> Variables  
    {  
        get { return this.variables; }  
    }  
    ```  
  
5.  <span data-ttu-id="517db-121">Invalide <xref:System.Activities.NativeActivity.CacheMetadata%2A></span><span class="sxs-lookup"><span data-stu-id="517db-121">Override <xref:System.Activities.NativeActivity.CacheMetadata%2A></span></span>  
  
    ```  
    protected override void CacheMetadata(NativeActivityMetadata metadata)  
    {  
        //call base.CacheMetadata to add the Activities and Variables to this activity's metadata  
        base.CacheMetadata(metadata);  
        //add the private implementation variable: currentIndex   
        metadata.AddImplementationVariable(this.currentIndex);  
    }  
    ```  
  
6.  <span data-ttu-id="517db-122">Invalide <xref:System.Activities.NativeActivity.Execute%2A></span><span class="sxs-lookup"><span data-stu-id="517db-122">Override <xref:System.Activities.NativeActivity.Execute%2A></span></span>  
  
    ```  
    protected override void Execute(NativeActivityContext context)  
    {  
       // Add the IReceiveMessageCallback implementation as an Execution property   
       context.Properties.Add("AccessIdentityCallback", new AccessIdentityCallback());  
       InternalExecute(context, null);  
    }  
  
    void InternalExecute(NativeActivityContext context, ActivityInstance instance)  
    {  
       //grab the index of the current Activity  
       int currentActivityIndex = this.currentIndex.Get(context);  
       if (currentActivityIndex == Activities.Count)  
       {  
          //if the currentActivityIndex is equal to the count of MySequence's Activities  
          //MySequence is complete  
          return;  
       }  
  
       if (this.onChildComplete == null)  
       {  
          //on completion of the current child, have the runtime call back on this method  
          this.onChildComplete = new CompletionCallback(InternalExecute);  
       }  
  
       //grab the next Activity in MySequence.Activities and schedule it  
       Activity nextChild = Activities[currentActivityIndex];  
       context.ScheduleActivity(nextChild, this.onChildComplete);  
  
       //increment the currentIndex  
       this.currentIndex.Set(context, ++currentActivityIndex);  
    }  
    ```  
  
### <a name="implement-the-workflow-service"></a><span data-ttu-id="517db-123">Implementar el servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="517db-123">Implement the workflow service</span></span>  
  
1.  <span data-ttu-id="517db-124">Abra el existente `Program` clase.</span><span class="sxs-lookup"><span data-stu-id="517db-124">Open the existing `Program` class.</span></span>  
  
2.  <span data-ttu-id="517db-125">Defina las constantes siguientes:</span><span class="sxs-lookup"><span data-stu-id="517db-125">Define the following constants:</span></span>  
  
    ```  
    class Program  
    {  
       const string addr = "http://localhost:8080/Service";  
       static XName contract = XName.Get("IService", "http://tempuri.org");  
    }  
    ```  
  
3.  <span data-ttu-id="517db-126">Agregue un método estático llamado `GetWorkflowService` que cree el servicio del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="517db-126">Add a static method called `GetWorkflowService` that creates the workflow service.</span></span>  
  
    ```  
    static Activity GetServiceWorkflow()  
    {  
       Variable<string> echoString = new Variable<string>();  
  
       // Create the Receive activity  
       Receive echoRequest = new Receive  
       {  
          CanCreateInstance = true,  
          ServiceContractName = contract,  
          OperationName = "Echo",  
          Content = new ReceiveParametersContent()  
          {  
             Parameters = { { "echoString", new OutArgument<string>(echoString) } }  
          }  
       };  
  
       return new AccessIdentityScope  
       {  
          Variables = { echoString },  
          Activities =  
          {  
             echoRequest,  
             new WriteLine { Text = new InArgument<string>( (e) => "Received: " + echoString.Get(e) ) },  
             new SendReply  
             {  
                Request = echoRequest,  
                Content = new SendParametersContent()  
                {  
                   Parameters = { { "result", new InArgument<string>(echoString) } }   
                }  
             }  
          }  
       };  
     }  
    ```  
  
4.  <span data-ttu-id="517db-127">En el método `Main` existente, hospede el servicio del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="517db-127">In the existing `Main` method, host the workflow service.</span></span>  
  
    ```  
    static void Main(string[] args)  
    {  
       string addr = "http://localhost:8080/Service";  
  
       using (WorkflowServiceHost host = new WorkflowServiceHost(GetServiceWorkflow()))  
       {  
          WSHttpBinding binding = new WSHttpBinding(SecurityMode.Message);  
          host.AddServiceEndpoint(contract, binding, addr);  
  
          host.Open();  
          Console.WriteLine("Service waiting at: " + addr);  
          Console.WriteLine("Press [ENTER] to exit");  
          Console.ReadLine();  
          host.Close();  
       }  
    }  
    ```  
  
### <a name="implement-a-workflow-client"></a><span data-ttu-id="517db-128">Implementar un cliente de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="517db-128">Implement a workflow client</span></span>  
  
1.  <span data-ttu-id="517db-129">Cree un nuevo proyecto de aplicación de consola denominado `Client`.</span><span class="sxs-lookup"><span data-stu-id="517db-129">Create a new console application project called `Client`.</span></span>  
  
2.  <span data-ttu-id="517db-130">Agregue referencias a los siguientes ensamblados:</span><span class="sxs-lookup"><span data-stu-id="517db-130">Add references to the following assemblies:</span></span>  
  
    1.  <span data-ttu-id="517db-131">System.Activities</span><span class="sxs-lookup"><span data-stu-id="517db-131">System.Activities</span></span>  
  
    2.  <span data-ttu-id="517db-132">System.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="517db-132">System.ServiceModel</span></span>  
  
    3.  <span data-ttu-id="517db-133">System.ServiceModel.Activities</span><span class="sxs-lookup"><span data-stu-id="517db-133">System.ServiceModel.Activities</span></span>  
  
3.  <span data-ttu-id="517db-134">Abra el archivo Program.cs generado y agregue un método estático llamado `GetClientWorkflow` para crear el flujo de trabajo del cliente.</span><span class="sxs-lookup"><span data-stu-id="517db-134">Open the generated Program.cs file and add a static method called `GetClientWorkflow` to create the client workflow.</span></span>  
  
    ```  
    static Activity GetClientWorkflow()  
    {  
       Variable<string> echoString = new Variable<string>();  
  
       Endpoint clientEndpoint = new Endpoint  
       {  
          Binding = new WSHttpBinding(SecurityMode.Message),  
          AddressUri = new Uri("http://localhost:8080/Service")  
       };  
  
       Send echoRequest = new Send  
       {  
          Endpoint = clientEndpoint,  
          ServiceContractName = XName.Get("IService", "http://tempuri.org"),  
          OperationName = "Echo",  
          Content = new SendParametersContent()  
          {  
             Parameters = { { "echoString", new InArgument<string>("Hello, World") } }   
          }  
       };  
  
       return new Sequence  
       {  
          Variables = { echoString },  
          Activities =  
          {                      
             new CorrelationScope  
             {  
                Body = new Sequence  
                {  
                   Activities =   
                   {  
                      echoRequest,  
                      new ReceiveReply  
                      {  
                         Request = echoRequest,  
                         Content = new ReceiveParametersContent  
                         {  
                            Parameters = { { "result", new OutArgument<string>(echoString) } }  
                         }  
                      }  
                   }  
                }  
             },                      
             new WriteLine { Text = new InArgument<string>( (e) => "Received Text: " + echoString.Get(e) ) },                      
             }  
          };  
       }  
    }  
    ```  
  
4.  <span data-ttu-id="517db-135">Agregue el siguiente código de hospedaje para la `Main()` método.</span><span class="sxs-lookup"><span data-stu-id="517db-135">Add the following hosting code to the `Main()` method.</span></span>  
  
    ```  
    static void Main(string[] args)  
    {  
       Activity workflow = GetClientWorkflow();  
       WorkflowInvoker.Invoke(workflow);  
       WorkflowInvoker.Invoke(workflow);  
       Console.WriteLine("Press [ENTER] to exit");  
       Console.ReadLine();  
    }  
    ```  
  
## <a name="example"></a><span data-ttu-id="517db-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="517db-136">Example</span></span>  
 <span data-ttu-id="517db-137">A continuación, se muestra el código fuente completo que se emplea en este tema.</span><span class="sxs-lookup"><span data-stu-id="517db-137">Here is a complete listing of the source code used in this topic.</span></span>  
  
```  
// AccessIdentityCallback.cs  
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
  
using System;  
using System.ServiceModel;  
using System.ServiceModel.Activities;  
  
namespace Microsoft.Samples.AccessingOperationContext.Service  
{  
    class AccessIdentityCallback : IReceiveMessageCallback  
    {  
        public const string HeaderName = "InstanceIdHeader";  
        public const string HeaderNS = "http://Microsoft.Samples.AccessingOperationContext";  
  
        public void OnReceiveMessage(System.ServiceModel.OperationContext operationContext, System.Activities.ExecutionProperties activityExecutionProperties)  
        {  
            try  
            {  
                // Guid instanceId = operationContext.IncomingMessageHeaders.GetHeader<Guid>(HeaderName, HeaderNS);  
                Console.WriteLine("Received a message from a workflow with the following identity" ); // with instanceId = {0}", instanceId);  
                Console.WriteLine("Windows Identity Name: {0}", operationContext.ServiceSecurityContext.WindowsIdentity.Name);  
                Console.WriteLine("Windows Identity User: {0}", operationContext.ServiceSecurityContext.WindowsIdentity.User);  
                Console.WriteLine("Windows Identity IsAuthenticated: {0}", operationContext.ServiceSecurityContext.WindowsIdentity.IsAuthenticated);  
            }  
            catch (MessageHeaderException)  
            {  
                Console.WriteLine("This message must not be from a workflow.");  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("An exception occurred: " + ex.Message);  
            }  
        }  
    }  
}  
```  
  
```  
// AccessIdentityScope.cs  
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
  
using System.Activities;  
using System.Collections.ObjectModel;  
  
namespace Microsoft.Samples.AccessingOperationContext.Service  
{  
    public sealed class AccessIdentityScope : NativeActivity  
    {  
        Collection<Activity> children;  
        Collection<Variable> variables;  
        Variable<int> currentIndex;  
        CompletionCallback onChildComplete;  
  
        public AccessIdentityScope()  
            : base()  
        {  
            this.children = new Collection<Activity>();  
            this.variables = new Collection<Variable>();  
            this.currentIndex = new Variable<int>();  
        }  
  
        public Collection<Activity> Activities  
        {  
            get  
            {  
                return this.children;  
            }  
        }  
  
        public Collection<Variable> Variables  
        {  
            get  
            {  
                return this.variables;  
            }  
        }  
  
        protected override void CacheMetadata(NativeActivityMetadata metadata)  
        {  
            //call base.CacheMetadata to add the Activities and Variables to this activity's metadata  
            base.CacheMetadata(metadata);  
            //add the private implementation variable: currentIndex   
            metadata.AddImplementationVariable(this.currentIndex);  
        }                     
  
        protected override void Execute(  
            NativeActivityContext context)  
        {  
            context.Properties.Add("AccessIdentityCallback", new AccessIdentityCallback());  
            InternalExecute(context, null);  
        }  
  
        void InternalExecute(NativeActivityContext context, ActivityInstance instance)  
        {  
            //grab the index of the current Activity  
            int currentActivityIndex = this.currentIndex.Get(context);  
            if (currentActivityIndex == Activities.Count)  
            {  
                //if the currentActivityIndex is equal to the count of MySequence's Activities  
                //MySequence is complete  
                return;  
            }  
  
            if (this.onChildComplete == null)  
            {  
                //on completion of the current child, have the runtime call back on this method  
                this.onChildComplete = new CompletionCallback(InternalExecute);  
            }  
  
            //grab the next Activity in MySequence.Activities and schedule it  
            Activity nextChild = Activities[currentActivityIndex];  
            context.ScheduleActivity(nextChild, this.onChildComplete);  
  
            //increment the currentIndex  
            this.currentIndex.Set(context, ++currentActivityIndex);  
        }  
    }  
}  
```  
  
```  
// Service.cs  
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
  
using System;  
using System.Activities;  
using System.Activities.Statements;  
using System.ServiceModel;  
using System.ServiceModel.Activities;  
using System.Xml.Linq;  
  
namespace Microsoft.Samples.AccessingOperationContext.Service  
{      
    class Program  
    {  
        const string addr = "http://localhost:8080/Service";  
        static XName contract = XName.Get("IService", "http://tempuri.org");  
  
        static void Main(string[] args)  
        {  
            string addr = "http://localhost:8080/Service";  
  
            using (WorkflowServiceHost host = new WorkflowServiceHost(GetServiceWorkflow()))  
            {  
                WSHttpBinding binding = new WSHttpBinding(SecurityMode.Message);  
                host.AddServiceEndpoint(contract, binding, addr);  
  
                host.Open();  
                Console.WriteLine("Service waiting at: " + addr);  
                Console.WriteLine("Press [ENTER] to exit");  
                Console.ReadLine();  
                host.Close();  
            }  
  
        }  
  
        static Activity GetServiceWorkflow()  
        {  
            Variable<string> echoString = new Variable<string>();  
  
            Receive echoRequest = new Receive  
            {  
                CanCreateInstance = true,  
                ServiceContractName = contract,  
                OperationName = "Echo",  
                Content = new ReceiveParametersContent()  
                {  
                    Parameters = { { "echoString", new OutArgument<string>(echoString) } }  
                }  
            };  
  
            return new AccessIdentityScope  
            {  
                Variables = { echoString },  
                Activities =  
                {  
                    echoRequest,  
                    new WriteLine { Text = new InArgument<string>( (e) => "Received: " + echoString.Get(e) ) },  
                    new SendReply  
                    {  
                        Request = echoRequest,  
                        Content = new SendParametersContent()  
                        {  
                            Parameters = { { "result", new InArgument<string>(echoString) } }   
                        }  
                    }  
                }  
            };  
        }  
    }  
}  
```  
  
```  
// client.cs   
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
  
using System;  
using System.Activities;  
using System.Activities.Statements;  
using System.ServiceModel;  
using System.ServiceModel.Activities;  
using System.Xml.Linq;  
  
namespace Microsoft.Samples.AccessingOperationContext.Client  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Activity workflow = GetClientWorkflow();  
            WorkflowInvoker.Invoke(workflow);  
            WorkflowInvoker.Invoke(workflow);  
            Console.WriteLine("Press [ENTER] to exit");  
            Console.ReadLine();  
        }  
  
        static Activity GetClientWorkflow()  
        {  
            Variable<string> echoString = new Variable<string>();  
  
            Endpoint clientEndpoint = new Endpoint  
            {  
                Binding = new WSHttpBinding(SecurityMode.Message),  
                AddressUri = new Uri("http://localhost:8080/Service")  
            };  
  
            Send echoRequest = new Send  
            {  
                Endpoint = clientEndpoint,  
                ServiceContractName = XName.Get("IService", "http://tempuri.org"),  
                OperationName = "Echo",  
                Content = new SendParametersContent()  
                {  
                    Parameters = { { "echoString", new InArgument<string>("Hello, World") } }   
                }  
            };  
  
            return new Sequence  
            {  
                Variables = { echoString },  
                Activities =  
                {                      
                    new CorrelationScope  
                    {  
                        Body = new Sequence  
                        {  
                            Activities =   
                            {  
                                echoRequest,  
                                new ReceiveReply  
                                {  
                                    Request = echoRequest,  
                                    Content = new ReceiveParametersContent  
                                    {  
                                        Parameters = { { "result", new OutArgument<string>(echoString) } }  
                                    }  
                                }  
                            }  
                        }  
                    },                      
                    new WriteLine { Text = new InArgument<string>( (e) => "Received Text: " + echoString.Get(e) ) },                      
                }  
            };  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="517db-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="517db-138">See Also</span></span>  
 [<span data-ttu-id="517db-139">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="517db-139">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="517db-140">Acceso a OperationContext</span><span class="sxs-lookup"><span data-stu-id="517db-140">Accessing OperationContext</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/accessing-operationcontext.md)  
 [<span data-ttu-id="517db-141">Creación de flujos de trabajo, actividades y expresiones mediante código imperativo</span><span class="sxs-lookup"><span data-stu-id="517db-141">Authoring Workflows, Activities, and Expressions Using Imperative Code</span></span>](../../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md)
