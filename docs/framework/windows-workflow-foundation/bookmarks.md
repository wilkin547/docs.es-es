---
description: 'Más información acerca de: marcadores'
title: 'Marcadores: WF'
ms.date: 03/30/2017
ms.assetid: 9b51a346-09ae-455c-a70a-e2264ddeb9e2
ms.openlocfilehash: b4f0e68e0868ecd4eb97673ff6c09ee8c806cf43
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787934"
---
# <a name="bookmarks"></a><span data-ttu-id="f136a-103">Marcadores</span><span class="sxs-lookup"><span data-stu-id="f136a-103">Bookmarks</span></span>

<span data-ttu-id="f136a-104">Los marcadores son el mecanismo que permite a una actividad esperar datos pasivamente sin tener que mantener un subproceso de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f136a-104">Bookmarks are the mechanism that enables an activity to passively wait for input without holding onto a workflow thread.</span></span> <span data-ttu-id="f136a-105">Cuando una actividad indica que está esperando un estímulo, puede crear un marcador.</span><span class="sxs-lookup"><span data-stu-id="f136a-105">When an activity signals that it is waiting for stimulus, it can create a bookmark.</span></span> <span data-ttu-id="f136a-106">Esto indica al tiempo de ejecución que la ejecución de la actividad no debería considerarse completada aun cuando se devuelva el método que se está ejecutando actualmente (que creó <xref:System.Activities.Bookmark>).</span><span class="sxs-lookup"><span data-stu-id="f136a-106">This indicates to the runtime that the activity’s execution should not be considered complete even when the currently executing method (which created the <xref:System.Activities.Bookmark>) returns.</span></span>  
  
## <a name="bookmark-basics"></a><span data-ttu-id="f136a-107">Fundamentos de los marcadores</span><span class="sxs-lookup"><span data-stu-id="f136a-107">Bookmark Basics</span></span>  

 <span data-ttu-id="f136a-108"><xref:System.Activities.Bookmark> representa un punto en el que la ejecución se puede reanudar (y, a través de la cual, se puede entregar los datos) dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f136a-108">A <xref:System.Activities.Bookmark> represents a point at which execution can be resumed (and through which input can be delivered) within a workflow instance.</span></span> <span data-ttu-id="f136a-109">Normalmente, a <xref:System.Activities.Bookmark> se le proporciona un nombre y el código externo (host o extensión) será el responsable de reanudar el marcador con datos pertinentes.</span><span class="sxs-lookup"><span data-stu-id="f136a-109">Typically, a <xref:System.Activities.Bookmark> is given a name and external (host or extension) code is responsible for resuming the bookmark with relevant data.</span></span> <span data-ttu-id="f136a-110">Cuando se reanuda <xref:System.Activities.Bookmark>, el tiempo de ejecución del flujo de trabajo programa el delegado de <xref:System.Activities.BookmarkCallback> que estuvo asociado con ese <xref:System.Activities.Bookmark> en el momento de su creación.</span><span class="sxs-lookup"><span data-stu-id="f136a-110">When a <xref:System.Activities.Bookmark> is resumed, the workflow runtime schedules the <xref:System.Activities.BookmarkCallback> delegate that was associated with that <xref:System.Activities.Bookmark> at the time of its creation.</span></span>  
  
## <a name="bookmark-options"></a><span data-ttu-id="f136a-111">Opciones de marcador</span><span class="sxs-lookup"><span data-stu-id="f136a-111">Bookmark Options</span></span>  

 <span data-ttu-id="f136a-112">La clase <xref:System.Activities.BookmarkOptions> especifica el tipo de <xref:System.Activities.Bookmark> que se crea.</span><span class="sxs-lookup"><span data-stu-id="f136a-112">The <xref:System.Activities.BookmarkOptions> class specifies the type of <xref:System.Activities.Bookmark> being created.</span></span> <span data-ttu-id="f136a-113">Los posibles valores que no se excluyen mutuamente son <xref:System.Activities.BookmarkOptions.None>, <xref:System.Activities.BookmarkOptions.MultipleResume> y <xref:System.Activities.BookmarkOptions.NonBlocking>.</span><span class="sxs-lookup"><span data-stu-id="f136a-113">The possible non mutually-exclusive values are <xref:System.Activities.BookmarkOptions.None>, <xref:System.Activities.BookmarkOptions.MultipleResume>, and <xref:System.Activities.BookmarkOptions.NonBlocking>.</span></span> <span data-ttu-id="f136a-114">Use <xref:System.Activities.BookmarkOptions.None>, el valor predeterminado, al crear un <xref:System.Activities.Bookmark> que se espera que se reanude una vez.</span><span class="sxs-lookup"><span data-stu-id="f136a-114">Use <xref:System.Activities.BookmarkOptions.None>, the default, when creating a <xref:System.Activities.Bookmark> that is expected to be resumed exactly once.</span></span> <span data-ttu-id="f136a-115">Use <xref:System.Activities.BookmarkOptions.MultipleResume> al crear un <xref:System.Activities.Bookmark> que se puede reanudar varias veces.</span><span class="sxs-lookup"><span data-stu-id="f136a-115">Use <xref:System.Activities.BookmarkOptions.MultipleResume> when creating a <xref:System.Activities.Bookmark> that can be resumed multiple times.</span></span> <span data-ttu-id="f136a-116">Use <xref:System.Activities.BookmarkOptions.NonBlocking> al crear un <xref:System.Activities.Bookmark> que posiblemente no se reanude nunca.</span><span class="sxs-lookup"><span data-stu-id="f136a-116">Use <xref:System.Activities.BookmarkOptions.NonBlocking> when creating a <xref:System.Activities.Bookmark> that might never be resumed.</span></span> <span data-ttu-id="f136a-117">A diferencia de los marcadores que se crean usando el <xref:System.Activities.BookmarkOptions>predeterminado, los marcadores <xref:System.Activities.BookmarkOptions.NonBlocking> no impiden que se complete una actividad.</span><span class="sxs-lookup"><span data-stu-id="f136a-117">Unlike bookmarks created using the default <xref:System.Activities.BookmarkOptions>, <xref:System.Activities.BookmarkOptions.NonBlocking> bookmarks do not prevent an activity from completing.</span></span>  
  
## <a name="bookmark-resumption"></a><span data-ttu-id="f136a-118">Reanudar marcadores</span><span class="sxs-lookup"><span data-stu-id="f136a-118">Bookmark Resumption</span></span>  

 <span data-ttu-id="f136a-119">Los marcadores pueden reanudarse según el código fuera de un flujo de trabajo usando una de las sobrecargas de <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A>.</span><span class="sxs-lookup"><span data-stu-id="f136a-119">Bookmarks can be resumed by code outside of a workflow using one of the <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> overloads.</span></span> <span data-ttu-id="f136a-120">En este ejemplo, se crea una actividad `ReadLine`.</span><span class="sxs-lookup"><span data-stu-id="f136a-120">In this example, a `ReadLine` activity is created.</span></span> <span data-ttu-id="f136a-121">Cuando se ejecuta, la actividad `ReadLine` crea un <xref:System.Activities.Bookmark>, registra una devolución de llamada y, a continuación, espera a que se reanude <xref:System.Activities.Bookmark>.</span><span class="sxs-lookup"><span data-stu-id="f136a-121">When executed, the `ReadLine` activity creates a <xref:System.Activities.Bookmark>, registers a callback, and then waits for the <xref:System.Activities.Bookmark> to be resumed.</span></span> <span data-ttu-id="f136a-122">Cuando lo haga, la actividad `ReadLine` asigna los datos que se pasaron con <xref:System.Activities.Bookmark> a su argumento <xref:System.Activities.Activity%601.Result%2A>.</span><span class="sxs-lookup"><span data-stu-id="f136a-122">When it is resumed, the `ReadLine` activity assigns the data that was passed with the <xref:System.Activities.Bookmark> to its <xref:System.Activities.Activity%601.Result%2A> argument.</span></span>  
  
```csharp  
public sealed class ReadLine : NativeActivity<string>  
{  
    [RequiredArgument]  
    public  InArgument<string> BookmarkName { get; set; }  
  
    protected override void Execute(NativeActivityContext context)  
    {  
        // Create a Bookmark and wait for it to be resumed.  
        context.CreateBookmark(BookmarkName.Get(context),
            new BookmarkCallback(OnResumeBookmark));  
    }  
  
    // NativeActivity derived activities that do asynchronous operations by calling
    // one of the CreateBookmark overloads defined on System.Activities.NativeActivityContext
    // must override the CanInduceIdle property and return true.  
    protected override bool CanInduceIdle  
    {  
        get { return true; }  
    }  
  
    public void OnResumeBookmark(NativeActivityContext context, Bookmark bookmark, object obj)  
    {  
        // When the Bookmark is resumed, assign its value to  
        // the Result argument.  
        Result.Set(context, (string)obj);  
    }  
}  
```  
  
 <span data-ttu-id="f136a-123">En este ejemplo, se crea un flujo de trabajo que usa la actividad `ReadLine` para recopilar el nombre del usuario y mostrarlo en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="f136a-123">In this example, a workflow is created that uses the `ReadLine` activity to gather the user’s name and display it to the console window.</span></span> <span data-ttu-id="f136a-124">La aplicación host realiza el trabajo real de recopilación de datos y los pasa al flujo de trabajo al reanudar <xref:System.Activities.Bookmark>.</span><span class="sxs-lookup"><span data-stu-id="f136a-124">The host application performs the actual work of gathering the input and passes it to the workflow by resuming the <xref:System.Activities.Bookmark>.</span></span>  
  
```csharp  
Variable<string> name = new Variable<string>  
{  
    Name = "name"  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        name  
    },  
    Activities =  
    {  
        new WriteLine()  
        {  
            Text = "What is your name?"  
        },  
        new ReadLine()  
        {  
            BookmarkName = "UserName",  
            Result = name  
        },  
        new WriteLine()  
        {  
            Text = new InArgument<string>((env) => "Hello, " + name.Get(env))  
        }  
    }  
};  
  
AutoResetEvent syncEvent = new AutoResetEvent(false);  
  
// Create the WorkflowApplication using the desired  
// workflow definition.  
WorkflowApplication wfApp = new WorkflowApplication(wf);  
  
// Handle the desired lifecycle events.  
wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)  
{  
    // Signal the host that the workflow is complete.  
    syncEvent.Set();  
};  
  
// Start the workflow.  
wfApp.Run();  
  
// Collect the user's name and resume the bookmark.  
// Bookmark resumption only occurs when the workflow  
// is idle. If a call to ResumeBookmark is made and the workflow  
// is not idle, ResumeBookmark blocks until the workflow becomes  
// idle before resuming the bookmark.  
wfApp.ResumeBookmark("UserName", Console.ReadLine());  
  
// Wait for Completed to arrive and signal that  
// the workflow is complete.  
syncEvent.WaitOne();  
```  
  
 <span data-ttu-id="f136a-125">Cuando se ejecuta la actividad `ReadLine`, crea un <xref:System.Activities.Bookmark> denominado `UserName` y, a continuación, espera a que se reanude el marcador.</span><span class="sxs-lookup"><span data-stu-id="f136a-125">When the `ReadLine` activity is executed, it creates a <xref:System.Activities.Bookmark> named `UserName` and then waits for the bookmark to be resumed.</span></span> <span data-ttu-id="f136a-126">El host recopila los datos deseados y, a continuación, reanuda <xref:System.Activities.Bookmark>.</span><span class="sxs-lookup"><span data-stu-id="f136a-126">The host collects the desired data and then resumes the <xref:System.Activities.Bookmark>.</span></span> <span data-ttu-id="f136a-127">El flujo de trabajo se reanuda, muestra el nombre y, a continuación, finaliza.</span><span class="sxs-lookup"><span data-stu-id="f136a-127">The workflow resumes, displays the name, and then completes.</span></span> <span data-ttu-id="f136a-128">Tenga en cuenta que no se necesita el código de sincronización con respecto a la reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="f136a-128">Note that no synchronization code is required with regard to resuming the bookmark.</span></span> <span data-ttu-id="f136a-129">Se puede reanudar <xref:System.Activities.Bookmark> sólo cuando el flujo de trabajo está inactivo y, si no lo está, la llamada a <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> se bloquea hasta que el flujo de trabajo se vuelve inactivo.</span><span class="sxs-lookup"><span data-stu-id="f136a-129">A <xref:System.Activities.Bookmark> can only be resumed when the workflow is idle, and if the workflow is not idle, the call to <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> blocks until the workflow becomes idle.</span></span>  
  
## <a name="bookmark-resumption-result"></a><span data-ttu-id="f136a-130">Resultado de reanudación del marcador</span><span class="sxs-lookup"><span data-stu-id="f136a-130">Bookmark Resumption Result</span></span>  

 <span data-ttu-id="f136a-131"><xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> devuelve un valor de enumeración de <xref:System.Activities.BookmarkResumptionResult> para indicar los resultados de la solicitud de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="f136a-131"><xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> returns a <xref:System.Activities.BookmarkResumptionResult> enumeration value to indicate the results of the bookmark resumption request.</span></span> <span data-ttu-id="f136a-132">Los valores de devolución posibles son <xref:System.Activities.BookmarkResumptionResult.Success>, <xref:System.Activities.BookmarkResumptionResult.NotReady> y <xref:System.Activities.BookmarkResumptionResult.NotFound>.</span><span class="sxs-lookup"><span data-stu-id="f136a-132">The possible return values are <xref:System.Activities.BookmarkResumptionResult.Success>, <xref:System.Activities.BookmarkResumptionResult.NotReady>, and <xref:System.Activities.BookmarkResumptionResult.NotFound>.</span></span> <span data-ttu-id="f136a-133">Los hosts y extensiones pueden usar este valor para determinar cómo continuar.</span><span class="sxs-lookup"><span data-stu-id="f136a-133">Hosts and extensions can use this value to determine how to proceed.</span></span>
