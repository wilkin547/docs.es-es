---
title: Exponer datos con CacheMetadata
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 34832f23-e93b-40e6-a80b-606a855a00d9
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: aea620d740b7b95747395821d622f267943352da
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="exposing-data-with-cachemetadata"></a><span data-ttu-id="16762-102">Exponer datos con CacheMetadata</span><span class="sxs-lookup"><span data-stu-id="16762-102">Exposing data with CacheMetadata</span></span>
<span data-ttu-id="16762-103">Antes de ejecutar una actividad, el runtime de flujo de trabajo obtiene toda la información sobre la actividad que necesita para mantener su ejecución.</span><span class="sxs-lookup"><span data-stu-id="16762-103">Before executing an activity, the workflow runtime obtains all of the information about the activity that it needs in order to maintain its execution.</span></span> <span data-ttu-id="16762-104">El runtime de flujo de trabajo obtiene esta información durante la ejecución del método <xref:System.Activities.Activity.CacheMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="16762-104">The workflow runtime gets this information during the execution of the <xref:System.Activities.Activity.CacheMetadata%2A> method.</span></span> <span data-ttu-id="16762-105">La implementación predeterminada de este método proporciona al runtime todas las actividades secundarias, variables y argumentos públicos expuestos por la actividad en el momento de su ejecución; si la actividad necesita proporcionar más información al runtime que la especificada (como miembros privados o actividades que va a programar la actividad), este método se puede reemplazar para proporcionarla.</span><span class="sxs-lookup"><span data-stu-id="16762-105">The default implementation of this method provides the runtime with all of the public arguments, variables, and child activities exposed by the activity at the time it is executed; if the activity needs to give more information to the runtime than this (such as private members, or activities to be scheduled by the activity), this method can be overridden to provide it.</span></span>  
  
## <a name="default-cachemetadata-behavior"></a><span data-ttu-id="16762-106">Comportamiento de CacheMetadata predeterminado</span><span class="sxs-lookup"><span data-stu-id="16762-106">Default CacheMetadata behavior</span></span>  
 <span data-ttu-id="16762-107">La implementación predeterminada de <xref:System.Activities.NativeActivity.CacheMetadata%2A> para las actividades que derivan de <xref:System.Activities.NativeActivity> procesa los tipos de métodos siguientes de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="16762-107">The default implementation of <xref:System.Activities.NativeActivity.CacheMetadata%2A> for activities that derive from <xref:System.Activities.NativeActivity> processes the following method types in the following ways:</span></span>  
  
-   <span data-ttu-id="16762-108"><xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601> o <xref:System.Activities.InOutArgument%601> (argumentos genéricos): estos argumentos se exponen al runtime como argumentos con un nombre y un tipo iguales al nombre y el tipo de la propiedad expuesta, la dirección de argumento apropiada y algunos datos de validación.</span><span class="sxs-lookup"><span data-stu-id="16762-108"><xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601>, or <xref:System.Activities.InOutArgument%601> (generic arguments): These arguments are exposed to the runtime as arguments with a name and type equal to the exposed property name and type, the appropriate argument direction, and some validation data.</span></span>  
  
-   <span data-ttu-id="16762-109"><xref:System.Activities.Variable> o cualquier subclase de ella: estos miembros se exponen al runtime como variables públicas.</span><span class="sxs-lookup"><span data-stu-id="16762-109"><xref:System.Activities.Variable> or any subclass thereof: These members are exposed to the runtime as public variables.</span></span>  
  
-   <span data-ttu-id="16762-110"><xref:System.Activities.Activity> o cualquier subclase de ella: estos miembros se exponen al runtime como actividades secundarias públicas.</span><span class="sxs-lookup"><span data-stu-id="16762-110"><xref:System.Activities.Activity> or any subclass thereof: These members are exposed to the runtime as public child activities.</span></span> <span data-ttu-id="16762-111">El comportamiento predeterminado se puede implementar explícitamente llamando al método <xref:System.Activities.ActivityMetadata.AddImportedChild%2A> y pasando la actividad secundaria.</span><span class="sxs-lookup"><span data-stu-id="16762-111">The default behavior can be implemented explicity by calling <xref:System.Activities.ActivityMetadata.AddImportedChild%2A>, passing in the child activity.</span></span>  
  
-   <span data-ttu-id="16762-112"><xref:System.Activities.ActivityDelegate> o cualquier subclase de ella: estos miembros se exponen al runtime como delegados públicos.</span><span class="sxs-lookup"><span data-stu-id="16762-112"><xref:System.Activities.ActivityDelegate> or any subclass thereof: These members are exposed to the runtime as public delegates.</span></span>  
  
-   <span data-ttu-id="16762-113"><xref:System.Collections.ICollection> de tipo <xref:System.Activities.Variable>: todos los elementos de la colección se exponen al runtime como variables públicas.</span><span class="sxs-lookup"><span data-stu-id="16762-113"><xref:System.Collections.ICollection> of type <xref:System.Activities.Variable>: All elements in the collection are exposed to the runtime as public variables.</span></span>  
  
-   <span data-ttu-id="16762-114"><xref:System.Collections.ICollection> de tipo <xref:System.Activities.Activity>: todos los elementos de la colección se exponen al runtime como elementos secundarios públicos.</span><span class="sxs-lookup"><span data-stu-id="16762-114"><xref:System.Collections.ICollection> of type <xref:System.Activities.Activity>: All elements in the collection are exposed to the runtime as public children.</span></span>  
  
-   <span data-ttu-id="16762-115"><xref:System.Collections.ICollection> de tipo <xref:System.Activities.ActivityDelegate>: todos los elementos de la colección se exponen al runtime como delegados públicos.</span><span class="sxs-lookup"><span data-stu-id="16762-115"><xref:System.Collections.ICollection> of type <xref:System.Activities.ActivityDelegate>: All elements in the collection are exposed to the runtime as public delegates.</span></span>  
  
 <span data-ttu-id="16762-116">El método <xref:System.Activities.Activity.CacheMetadata%2A> para las actividades que derivan de <xref:System.Activities.Activity>, <xref:System.Workflow.Activities.CodeActivity> y <xref:System.Activities.AsyncCodeActivity> también funciona como en los casos anteriores, exceptuando las diferencias siguientes:</span><span class="sxs-lookup"><span data-stu-id="16762-116">The <xref:System.Activities.Activity.CacheMetadata%2A> for activities that derive from <xref:System.Activities.Activity>, <xref:System.Workflow.Activities.CodeActivity>, and <xref:System.Activities.AsyncCodeActivity> also function as above, except for the following differences:</span></span>  
  
-   <span data-ttu-id="16762-117">Las clases que derivan de <xref:System.Activities.Activity> no pueden programar actividades secundarias ni delegados, por lo que dichos miembros se exponen como elementos secundarios y delegados importados.</span><span class="sxs-lookup"><span data-stu-id="16762-117">Classes that derive from <xref:System.Activities.Activity> cannot schedule child activities or delegates, so such members are exposed as imported children and delegates; the</span></span>  
  
-   <span data-ttu-id="16762-118">Las clases que derivan de <xref:System.Activities.CodeActivity> y <xref:System.Activities.AsyncCodeActivity> no admiten variables, elementos secundarios o delegados, por lo que solo se expondrán argumentos.</span><span class="sxs-lookup"><span data-stu-id="16762-118">Classes that derive from <xref:System.Activities.CodeActivity> and <xref:System.Activities.AsyncCodeActivity> do not support variables, children, or delegates, so only arguments will be exposed.</span></span>  
  
## <a name="overriding-cachemetadata-to-provide-information-to-the-runtime"></a><span data-ttu-id="16762-119">Reemplazar CacheMetadata para proporcionar información al runtime</span><span class="sxs-lookup"><span data-stu-id="16762-119">Overriding CacheMetadata to provide information to the runtime</span></span>  
 <span data-ttu-id="16762-120">El siguiente fragmento de código muestra cómo agregar información sobre miembros a los metadatos de una actividad durante la ejecución del método <xref:System.Activities.Activity.CacheMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="16762-120">The following code snippet demonstrates how to add information about members to an activity’s metadata during the execution of the <xref:System.Activities.Activity.CacheMetadata%2A> method.</span></span> <span data-ttu-id="16762-121">Observe que se llama a la base del método para almacenar en memoria caché todos los datos públicos sobre la actividad.</span><span class="sxs-lookup"><span data-stu-id="16762-121">Note that the base of the method is called to cache all public data about the activity.</span></span>  
  
```  
protected override void CacheMetadata(NativeActivityMetadata metadata)  
{      
    base.CacheMetadata(metadata);  
    metadata.AddImplementationChild(this._writeLine);  
    metadata.AddVariable(this._myVariable);  
    metadata.AddImplementationVariable(this._myImplementationVariable);  
  
    RuntimeArgument argument = new RuntimeArgument("MyArgument", ArgumentDirection.In, typeof(SomeType));  
    metadata.Bind(argument, this.SomeName);  
    metadata.AddArgument(argument);  
}  
```  
  
## <a name="using-cachemetadata-to-expose-implementation-children"></a><span data-ttu-id="16762-122">Utilizar CacheMetadata para exponer los elementos secundarios de implementación</span><span class="sxs-lookup"><span data-stu-id="16762-122">Using CacheMetadata to expose implementation children</span></span>  
 <span data-ttu-id="16762-123">Para pasar datos a actividades secundarias que van a ser programadas por una actividad utilizando variables, es necesario agregar las variables como variables de implementación; las variables públicas no pueden tener establecidos sus valores de esta manera.</span><span class="sxs-lookup"><span data-stu-id="16762-123">In order to pass data to child activities that are to be scheduled by an activity using variables, it is necessary to add the variables as implementation variables; public variables cannot have their values set this way.</span></span> <span data-ttu-id="16762-124">La razón de ello es que las actividades están previstas para ser ejecutadas como implementaciones de funciones (que tienen parámetros), en lugar de clases encapsuladas (que tienen propiedades).</span><span class="sxs-lookup"><span data-stu-id="16762-124">The reason for this is that activities are intended to be executed more as implementations of functions (which have parameters), rather than encapsulated classes (which have properties).</span></span> <span data-ttu-id="16762-125">Sin embargo, hay situaciones en que los argumentos se deben establecer explícitamente, como cuando se utiliza <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, ya que la actividad programada no tiene acceso a los argumentos de la actividad principal de la manera que una actividad secundaria lo tendría.</span><span class="sxs-lookup"><span data-stu-id="16762-125">However, there are situations in which the arguments must be explicitly set, such as when using <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, since the scheduled activity doesn't have access to the parent activity's arguments in the way a child activity would.</span></span>  
  
 <span data-ttu-id="16762-126">El siguiente fragmento de código muestra cómo pasar un argumento de una actividad nativa a una actividad programada utilizando <xref:System.Activities.Activity.CacheMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="16762-126">The following code snippet demonstrates how to pass an argument form a native activity into a scheduled activity using <xref:System.Activities.Activity.CacheMetadata%2A>.</span></span>  
  
```  
public sealed class ChildActivity : NativeActivity  
{  
    public WriteLine _writeLine;  
    public InArgument<string> Message { get; set; }  
    private Variable<string> MessageVariable { get; set; }  
    public ChildActivity()  
    {  
        MessageVariable = new Variable<string>();  
        _writeLine = new WriteLine  
        {  
            Text = new InArgument<string>(MessageVariable),  
        };  
    }  
    protected override void CacheMetadata(NativeActivityMetadata metadata)  
    {  
        base.CacheMetadata(metadata);  
        metadata.AddImplementationVariable(this.MessageVariable);  
        metadata.AddImplementationChild(this._writeLine);  
    }  
    protected override void Execute(NativeActivityContext context)  
    {  
        string configuredMessage = context.GetValue(Message);  
        context.SetValue(MessageVariable, configuredMessage);  
        context.ScheduleActivity(this._writeLine);  
    }  
}  
```
