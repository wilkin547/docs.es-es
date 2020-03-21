---
title: Marcadores - WF
ms.date: 03/30/2017
ms.assetid: 9b51a346-09ae-455c-a70a-e2264ddeb9e2
ms.openlocfilehash: c5bd8130ee623599e80014777baf92986c3b6969
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183010"
---
# <a name="bookmarks"></a>Marcadores
Los marcadores son el mecanismo que permite a una actividad esperar datos pasivamente sin tener que mantener un subproceso de flujo de trabajo. Cuando una actividad indica que está esperando un estímulo, puede crear un marcador. Esto indica al tiempo de ejecución que la ejecución de la actividad no debería considerarse completada aun cuando se devuelva el método que se está ejecutando actualmente (que creó <xref:System.Activities.Bookmark>).  
  
## <a name="bookmark-basics"></a>Fundamentos de los marcadores  
 <xref:System.Activities.Bookmark> representa un punto en el que la ejecución se puede reanudar (y, a través de la cual, se puede entregar los datos) dentro de una instancia de flujo de trabajo. Normalmente, a <xref:System.Activities.Bookmark> se le proporciona un nombre y el código externo (host o extensión) será el responsable de reanudar el marcador con datos pertinentes. Cuando se reanuda <xref:System.Activities.Bookmark>, el tiempo de ejecución del flujo de trabajo programa el delegado de <xref:System.Activities.BookmarkCallback> que estuvo asociado con ese <xref:System.Activities.Bookmark> en el momento de su creación.  
  
## <a name="bookmark-options"></a>Opciones de marcador  
 La clase <xref:System.Activities.BookmarkOptions> especifica el tipo de <xref:System.Activities.Bookmark> que se crea. Los posibles valores que no se excluyen mutuamente son <xref:System.Activities.BookmarkOptions.None>, <xref:System.Activities.BookmarkOptions.MultipleResume> y <xref:System.Activities.BookmarkOptions.NonBlocking>. Use <xref:System.Activities.BookmarkOptions.None>, el valor predeterminado, al crear un <xref:System.Activities.Bookmark> que se espera que se reanude una vez. Use <xref:System.Activities.BookmarkOptions.MultipleResume> al crear un <xref:System.Activities.Bookmark> que se puede reanudar varias veces. Use <xref:System.Activities.BookmarkOptions.NonBlocking> al crear un <xref:System.Activities.Bookmark> que posiblemente no se reanude nunca. A diferencia de los marcadores que se crean usando el <xref:System.Activities.BookmarkOptions>predeterminado, los marcadores <xref:System.Activities.BookmarkOptions.NonBlocking> no impiden que se complete una actividad.  
  
## <a name="bookmark-resumption"></a>Reanudar marcadores  
 Los marcadores pueden reanudarse según el código fuera de un flujo de trabajo usando una de las sobrecargas de <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A>. En este ejemplo, se crea una actividad `ReadLine`. Cuando se ejecuta, la actividad `ReadLine` crea un <xref:System.Activities.Bookmark>, registra una devolución de llamada y, a continuación, espera a que se reanude <xref:System.Activities.Bookmark>. Cuando lo haga, la actividad `ReadLine` asigna los datos que se pasaron con <xref:System.Activities.Bookmark> a su argumento <xref:System.Activities.Activity%601.Result%2A>.  
  
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
  
 En este ejemplo, se crea un flujo de trabajo que usa la actividad `ReadLine` para recopilar el nombre del usuario y mostrarlo en la ventana de la consola. La aplicación host realiza el trabajo real de recopilación de datos y los pasa al flujo de trabajo al reanudar <xref:System.Activities.Bookmark>.  
  
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
  
 Cuando se ejecuta la actividad `ReadLine`, crea un <xref:System.Activities.Bookmark> denominado `UserName` y, a continuación, espera a que se reanude el marcador. El host recopila los datos deseados y, a continuación, reanuda <xref:System.Activities.Bookmark>. El flujo de trabajo se reanuda, muestra el nombre y, a continuación, finaliza. Tenga en cuenta que no se necesita el código de sincronización con respecto a la reanudación del marcador. Se puede reanudar <xref:System.Activities.Bookmark> sólo cuando el flujo de trabajo está inactivo y, si no lo está, la llamada a <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> se bloquea hasta que el flujo de trabajo se vuelve inactivo.  
  
## <a name="bookmark-resumption-result"></a>Resultado de reanudación del marcador  
 <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> devuelve un valor de enumeración de <xref:System.Activities.BookmarkResumptionResult> para indicar los resultados de la solicitud de reanudación del marcador. Los valores de devolución posibles son <xref:System.Activities.BookmarkResumptionResult.Success>, <xref:System.Activities.BookmarkResumptionResult.NotReady> y <xref:System.Activities.BookmarkResumptionResult.NotFound>. Los hosts y extensiones pueden usar este valor para determinar cómo continuar.
