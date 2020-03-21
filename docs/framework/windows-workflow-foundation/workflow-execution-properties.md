---
title: Propiedades de ejecución del flujo de trabajo
ms.date: 03/30/2017
ms.assetid: a50e088e-3a45-4267-bd51-1a3e6c2d246d
ms.openlocfilehash: 0f958e7e112bfddc2740c2605d446493f2d49010
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182663"
---
# <a name="workflow-execution-properties"></a><span data-ttu-id="4a41f-102">Propiedades de ejecución del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="4a41f-102">Workflow Execution Properties</span></span>
<span data-ttu-id="4a41f-103">A través del almacenamiento local para el subproceso (TLS), el CLR mantiene un contexto de ejecución para cada subproceso.</span><span class="sxs-lookup"><span data-stu-id="4a41f-103">Through thread local storage (TLS), the CLR maintains an execution context for each thread.</span></span> <span data-ttu-id="4a41f-104">Este contexto de ejecución rige propiedades de subproceso bien conocidas, como la identidad del subproceso, la transacción ambiente y el conjunto de permisos actual así como las propiedades de subproceso definidas por el usuario como ranuras con nombre.</span><span class="sxs-lookup"><span data-stu-id="4a41f-104">This execution context governs well-known thread properties such as the thread identity, the ambient transaction, and the current permission set in addition to user-defined thread properties like named slots.</span></span>  
  
 <span data-ttu-id="4a41f-105">A diferencia de los programas que tienen por objetivo directo el CLR, los programas de flujo de trabajo son árboles con ámbito jerárquico de actividades que se ejecutan en un entorno independiente del subproceso.</span><span class="sxs-lookup"><span data-stu-id="4a41f-105">Unlike programs directly targeting the CLR, workflow programs are hierarchically scoped trees of activities that execute in a thread-agnostic environment.</span></span> <span data-ttu-id="4a41f-106">Esto implica que los mecanismos de TLS estándar no se pueden usar directamente para determinar qué contexto está en ámbito de un elemento de trabajo determinado.</span><span class="sxs-lookup"><span data-stu-id="4a41f-106">This implies that the standard TLS mechanisms cannot directly be used to determine what context is in scope for a given work item.</span></span> <span data-ttu-id="4a41f-107">Por ejemplo, dos bifurcaciones paralelas de ejecución podrían usar distintas transacciones, aunque es posible que el programador intercale su ejecución en el mismo subproceso de CLR.</span><span class="sxs-lookup"><span data-stu-id="4a41f-107">For example, two parallel branches of execution might use different transactions, yet the scheduler might interleave their execution on the same CLR thread.</span></span>  
  
 <span data-ttu-id="4a41f-108">Las propiedades de ejecución del flujo de trabajo proporcionan un mecanismo para agregar propiedades específicas del contexto al entorno de una actividad.</span><span class="sxs-lookup"><span data-stu-id="4a41f-108">Workflow execution properties provide a mechanism to add context specific properties to an activity’s environment.</span></span> <span data-ttu-id="4a41f-109">De esta forma se permite que una actividad declare qué propiedades están en ámbito para su subárbol y se proporcionen enlaces para configurar y destruir el TLS para interoperar correctamente con objetos CLR.</span><span class="sxs-lookup"><span data-stu-id="4a41f-109">This allows an activity to declare which properties are in scope for its sub-tree and also provides hooks for setting up and tearing down TLS to properly interoperate with CLR objects.</span></span>  
  
## <a name="creating-and-using-workflow-execution-properties"></a><span data-ttu-id="4a41f-110">Crear y usar propiedades de ejecución de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="4a41f-110">Creating and Using Workflow Execution Properties</span></span>  
 <span data-ttu-id="4a41f-111">Las propiedades de ejecución de flujo de trabajo implementan generalmente la interfaz <xref:System.Activities.IExecutionProperty> , aunque las propiedades centradas en mensajería pueden implementar <xref:System.ServiceModel.Activities.ISendMessageCallback> y <xref:System.ServiceModel.Activities.IReceiveMessageCallback> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="4a41f-111">Workflow execution properties usually implement the <xref:System.Activities.IExecutionProperty> interface, though properties focused on messaging may implement <xref:System.ServiceModel.Activities.ISendMessageCallback> and <xref:System.ServiceModel.Activities.IReceiveMessageCallback> instead.</span></span> <span data-ttu-id="4a41f-112">Para crear una propiedad de ejecución de flujo de trabajo, cree una clase que implemente la interfaz <xref:System.Activities.IExecutionProperty> e implemente los miembros <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A> y <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A>.</span><span class="sxs-lookup"><span data-stu-id="4a41f-112">To create a workflow execution property, create a class that implements the <xref:System.Activities.IExecutionProperty> interface and implement the members <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A> and <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A>.</span></span> <span data-ttu-id="4a41f-113">Estos miembros le dan a la propiedad de ejecución la oportunidad de configurar y anular el almacenamiento local de subprocesos durante cada pulso de trabajo de la actividad que contiene la propiedad, incluidas las actividades secundarias.</span><span class="sxs-lookup"><span data-stu-id="4a41f-113">These members provide the execution property with an opportunity to properly set up and tear down the thread local storage during each pulse of work of the activity that contains the property, including any child activities.</span></span> <span data-ttu-id="4a41f-114">En este ejemplo, se crea `ConsoleColorProperty`, que establece `Console.ForegroundColor`.</span><span class="sxs-lookup"><span data-stu-id="4a41f-114">In this example, a `ConsoleColorProperty` is created that sets the `Console.ForegroundColor`.</span></span>  
  
```csharp  
class ConsoleColorProperty : IExecutionProperty  
{  
    public const string Name = "ConsoleColorProperty";  
  
    ConsoleColor original;  
    ConsoleColor color;  
  
    public ConsoleColorProperty(ConsoleColor color)  
    {  
        this.color = color;  
    }  
  
    void IExecutionProperty.SetupWorkflowThread()  
    {  
        original = Console.ForegroundColor;  
        Console.ForegroundColor = color;  
    }  
  
    void IExecutionProperty.CleanupWorkflowThread()  
    {  
        Console.ForegroundColor = original;  
    }  
}  
```  
  
 <span data-ttu-id="4a41f-115">Los autores de actividad pueden usar esta propiedad registrándola en el reemplazo de ejecución de la actividad.</span><span class="sxs-lookup"><span data-stu-id="4a41f-115">Activity authors can use this property by registering it in the activity’s execute override.</span></span> <span data-ttu-id="4a41f-116">En este ejemplo, se define una actividad `ConsoleColorScope` que registra `ConsoleColorProperty` al agregarla a la colección de <xref:System.Activities.NativeActivityContext.Properties%2A> de la clase <xref:System.Activities.NativeActivityContext> actual.</span><span class="sxs-lookup"><span data-stu-id="4a41f-116">In this example, a `ConsoleColorScope` activity is defined that registers the `ConsoleColorProperty` by adding it to the <xref:System.Activities.NativeActivityContext.Properties%2A> collection of the current <xref:System.Activities.NativeActivityContext>.</span></span>  
  
```csharp  
public sealed class ConsoleColorScope : NativeActivity  
{  
    public ConsoleColorScope()  
        : base()  
    {  
    }  
  
    public ConsoleColor Color { get; set; }  
    public Activity Body { get; set; }  
  
    protected override void Execute(NativeActivityContext context)  
    {  
        context.Properties.Add(ConsoleColorProperty.Name, new ConsoleColorProperty(this.Color));  
  
        if (this.Body != null)  
        {  
            context.ScheduleActivity(this.Body);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="4a41f-117">Cuando el cuerpo de la actividad comienza un pulso de trabajo, se llama al método <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A> de la propiedad y cuando el pulso de trabajo ha finalizado, se llama a <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A>.</span><span class="sxs-lookup"><span data-stu-id="4a41f-117">When the activity’s body starts a pulse of work, the <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A> method of the property is called, and when the pulse of work is complete, the <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A> is called.</span></span> <span data-ttu-id="4a41f-118">En este ejemplo, se crea un flujo de trabajo que usa una actividad <xref:System.Activities.Statements.Parallel> con tres bifurcaciones.</span><span class="sxs-lookup"><span data-stu-id="4a41f-118">In this example, a workflow is created that uses a <xref:System.Activities.Statements.Parallel> activity with three branches.</span></span> <span data-ttu-id="4a41f-119">Las primeras dos usan la actividad `ConsoleColorScope` mientras que la tercera no.</span><span class="sxs-lookup"><span data-stu-id="4a41f-119">The first two branches use the `ConsoleColorScope` activity and the third branch does not.</span></span> <span data-ttu-id="4a41f-120">Las tres bifurcaciones incluyen dos actividades <xref:System.Activities.Statements.WriteLine> y una actividad <xref:System.Activities.Statements.Delay>.</span><span class="sxs-lookup"><span data-stu-id="4a41f-120">All three branches contain two <xref:System.Activities.Statements.WriteLine> activities and a <xref:System.Activities.Statements.Delay> activity.</span></span> <span data-ttu-id="4a41f-121">Cuando la actividad <xref:System.Activities.Statements.Parallel> se ejecuta, las actividades contenidas en las bifurcaciones se ejecutan de modo intercalado, aunque cuando cada actividad secundaria se ejecuta, `ConsoleColorProperty` aplica el color de la consola correcto.</span><span class="sxs-lookup"><span data-stu-id="4a41f-121">When the <xref:System.Activities.Statements.Parallel> activity executes, the activities that are contained in the branches execute in an interleaved manner, but as each child activity executes the correct console color is applied by the `ConsoleColorProperty`.</span></span>  
  
```csharp  
Activity wf = new Parallel  
{  
    Branches =
    {  
        new ConsoleColorScope  
        {  
            Color = ConsoleColor.Blue,  
            Body = new Sequence  
            {  
                Activities =
                {  
                    new WriteLine  
                    {  
                        Text = "Start blue text."  
                    },  
                    new Delay  
                    {  
                        Duration = TimeSpan.FromSeconds(1)  
                    },  
                    new WriteLine  
                    {  
                        Text = "End blue text."  
                    }  
                }  
            }  
        },  
        new ConsoleColorScope  
        {  
            Color = ConsoleColor.Red,  
            Body = new Sequence  
            {  
                Activities =
                {  
                    new WriteLine  
                    {  
                        Text = "Start red text."  
                    },  
                    new Delay  
                    {  
                        Duration = TimeSpan.FromSeconds(1)  
                    },  
                    new WriteLine  
                    {  
                        Text = "End red text."  
                    }  
                }  
            }  
        },  
        new Sequence  
        {  
            Activities =
            {  
                new WriteLine  
                {  
                    Text = "Start default text."  
                },  
                new Delay  
                {  
                    Duration = TimeSpan.FromSeconds(1)  
                },  
                new WriteLine  
                {  
                    Text = "End default text."  
                }  
            }  
        }  
    }  
};  
  
WorkflowInvoker.Invoke(wf);  
```  
  
 <span data-ttu-id="4a41f-122">Cuando se invoca el flujo de trabajo, se escribe la siguiente salida en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="4a41f-122">When the workflow is invoked, the following output is written to the console window.</span></span>  
  
```console  
Start blue text.  
Start red text.  
Start default text.  
End blue text.  
End red text.  
End default text.  
```  
  
> [!NOTE]
> <span data-ttu-id="4a41f-123">Aunque no se muestra en la salida anterior, cada línea de texto en la ventana de la consola se muestra en el color indicado.</span><span class="sxs-lookup"><span data-stu-id="4a41f-123">Although it is not shown in the previous output, each line of text in the console window is displayed in the indicated color.</span></span>  
  
 <span data-ttu-id="4a41f-124">Los autores de actividad personalizados pueden usar las propiedades de ejecución del flujo de trabajo y también proporcionan el mecanismo para controlar la administración de las actividades como <xref:System.ServiceModel.Activities.CorrelationScope> y <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="4a41f-124">Workflow execution properties can be used by custom activity authors, and they also provide the mechanism for handle management for activities such as the <xref:System.ServiceModel.Activities.CorrelationScope> and <xref:System.Activities.Statements.TransactionScope> activities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a41f-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4a41f-125">See also</span></span>

- <xref:System.Activities.IExecutionProperty>
- <xref:System.Activities.IPropertyRegistrationCallback>
- <xref:System.Activities.RegistrationContext>
