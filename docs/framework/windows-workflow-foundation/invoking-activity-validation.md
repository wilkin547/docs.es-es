---
title: Invocar validación de actividad
ms.date: 03/30/2017
ms.assetid: 22bef766-c505-4fd4-ac0f-7b363b238969
ms.openlocfilehash: 95e6b22fe9814133df080b1faadcc4be32b60bf9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279810"
---
# <a name="invoking-activity-validation"></a><span data-ttu-id="3ee39-102">Invocar validación de actividad</span><span class="sxs-lookup"><span data-stu-id="3ee39-102">Invoking Activity Validation</span></span>

<span data-ttu-id="3ee39-103">La validación de la actividad proporciona un método para identificar y notificar los errores en la configuración de cualquier actividad antes de su ejecución.</span><span class="sxs-lookup"><span data-stu-id="3ee39-103">Activity validation provides a method to identify and report errors in any activity’s configuration prior to its execution.</span></span> <span data-ttu-id="3ee39-104">La validación se produce cuando un flujo de trabajo se modifica en el diseñador de flujo de trabajo y cuando los errores de validación o advertencias se muestran en el diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3ee39-104">Validation occurs when a workflow is modified in the workflow designer and any validation errors or warnings are displayed in the workflow designer.</span></span> <span data-ttu-id="3ee39-105">La validación también se produce en tiempo de ejecución cuando se invoca un flujo de trabajo y si se producen algunos errores de validación; la lógica de validación predeterminada produce <xref:System.Activities.InvalidWorkflowException>.</span><span class="sxs-lookup"><span data-stu-id="3ee39-105">Validation also occurs at run time when a workflow is invoked and if any validation errors occur, an <xref:System.Activities.InvalidWorkflowException> is thrown by the default validation logic.</span></span> <span data-ttu-id="3ee39-106">Windows Workflow Foundation (WF) proporciona la <xref:System.Activities.Validation.ActivityValidationServices> clase que puede usar la aplicación de flujo de trabajo y los desarrolladores de herramientas para validar explícitamente una actividad.</span><span class="sxs-lookup"><span data-stu-id="3ee39-106">Windows Workflow Foundation (WF) provides the <xref:System.Activities.Validation.ActivityValidationServices> class that can be used by workflow application and tooling developers to explicitly validate an activity.</span></span> <span data-ttu-id="3ee39-107">En este tema se describe cómo usar <xref:System.Activities.Validation.ActivityValidationServices> para realizar la validación de actividad.</span><span class="sxs-lookup"><span data-stu-id="3ee39-107">This topic describes how to use <xref:System.Activities.Validation.ActivityValidationServices> to perform activity validation.</span></span>  
  
## <a name="using-activityvalidationservices"></a><span data-ttu-id="3ee39-108">Usar ActivityValidationServices</span><span class="sxs-lookup"><span data-stu-id="3ee39-108">Using ActivityValidationServices</span></span>  

 <span data-ttu-id="3ee39-109"><xref:System.Activities.Validation.ActivityValidationServices> tiene dos sobrecargas de <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> que se usan para invocar la lógica de validación de una actividad.</span><span class="sxs-lookup"><span data-stu-id="3ee39-109"><xref:System.Activities.Validation.ActivityValidationServices> has two <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> overloads that are used to invoke an activity’s validation logic.</span></span> <span data-ttu-id="3ee39-110">La primera sobrecarga toma la actividad raíz que se va a validar y devuelve una colección de errores de validación y advertencias.</span><span class="sxs-lookup"><span data-stu-id="3ee39-110">The first overload takes the root activity to be validated and returns a collection of validation errors and warnings.</span></span> <span data-ttu-id="3ee39-111">En el siguiente ejemplo, se usa una actividad `Add` personalizada que tiene dos argumentos necesarios.</span><span class="sxs-lookup"><span data-stu-id="3ee39-111">In the following example, a custom `Add` activity is used that has two required arguments.</span></span>  
  
```csharp  
public sealed class Add : CodeActivity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Operand1 { get; set; }  
  
    [RequiredArgument]  
    public InArgument<int> Operand2 { get; set; }  
  
    protected override int Execute(CodeActivityContext context)  
    {  
        return Operand1.Get(context) + Operand2.Get(context);  
    }  
}  
```  
  
 <span data-ttu-id="3ee39-112">La actividad `Add` se usa dentro de <xref:System.Activities.Statements.Sequence>, aunque no se enlazan sus dos argumentos necesarios, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3ee39-112">The `Add` activity is used inside a <xref:System.Activities.Statements.Sequence>, but its two required arguments are not bound, as shown in the following example.</span></span>  
  
```csharp  
Variable<int> Operand1 = new Variable<int>{ Default = 10 };  
Variable<int> Operand2 = new Variable<int>{ Default = 15 };  
Variable<int> Result = new Variable<int>();  
  
Activity wf = new Sequence  
{  
    Variables = { Operand1, Operand2, Result },  
    Activities =
    {  
        new Add(),  
        new WriteLine  
        {  
            Text = new InArgument<string>(env => "The result is " + Result.Get(env))  
        }  
    }  
};  
```  
  
 <span data-ttu-id="3ee39-113">Este flujo de trabajo se puede validar llamando a <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="3ee39-113">This workflow can be validated by calling <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span></span> <span data-ttu-id="3ee39-114"><xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> devuelve una colección de errores o advertencias de validación contenidos por la actividad y cualquier elemento secundario, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3ee39-114"><xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> returns a collection of any validation errors or warnings contained by the activity and any children, as shown in the following example.</span></span>  
  
```csharp  
ValidationResults results = ActivityValidationServices.Validate(wf);  
  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error: {0}", error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning: {0}", warning.Message);  
    }  
}  
```  
  
 <span data-ttu-id="3ee39-115">Cuando se llama a <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> en este flujo de trabajo de ejemplo, se devuelven dos errores de validación.</span><span class="sxs-lookup"><span data-stu-id="3ee39-115">When <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> is called on this sample workflow, two validation errors are returned.</span></span>  
  
 <span data-ttu-id="3ee39-116">**Error: Value for a required activity argument 'Operand2' was not supplied.**</span><span class="sxs-lookup"><span data-stu-id="3ee39-116">**Error: Value for a required activity argument 'Operand2' was not supplied.**</span></span>  
<span data-ttu-id="3ee39-117">**Error: Value for a required activity argument 'Operand1' was not supplied.**</span><span class="sxs-lookup"><span data-stu-id="3ee39-117">**Error: Value for a required activity argument 'Operand1' was not supplied.**</span></span>  <span data-ttu-id="3ee39-118">Si se invocara este flujo de trabajo, se produciría una excepción <xref:System.Activities.InvalidWorkflowException>, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3ee39-118">If this workflow was invoked, an <xref:System.Activities.InvalidWorkflowException> would be thrown, as shown in the following example.</span></span>  
  
```csharp  
try  
{  
    WorkflowInvoker.Invoke(wf);  
}  
catch (Exception ex)  
{  
    Console.WriteLine(ex);  
}  
```  
  
 <span data-ttu-id="3ee39-119">**System.Activities.InvalidWorkflowException:**</span><span class="sxs-lookup"><span data-stu-id="3ee39-119">**System.Activities.InvalidWorkflowException:**</span></span>  
<span data-ttu-id="3ee39-120">**Se encontraron los siguientes errores al procesar el árbol de flujo de trabajo:** 
 **' Add ': no se proporcionó el valor de un argumento de actividad necesario ' Operand2 '.** 
 **' Add ': no se proporcionó el valor de un argumento de actividad necesario ' Operand1 '.**</span><span class="sxs-lookup"><span data-stu-id="3ee39-120">**The following errors were encountered while processing the workflow tree:**
 **'Add': Value for a required activity argument 'Operand2' was not supplied.**
 **'Add': Value for a required activity argument 'Operand1' was not supplied.**</span></span>  <span data-ttu-id="3ee39-121">Para que este flujo de trabajo de ejemplo sea válido, se deben enlazar los dos argumentos necesarios de la actividad `Add`.</span><span class="sxs-lookup"><span data-stu-id="3ee39-121">For this example workflow to be valid, the two required arguments of the `Add` activity must be bound.</span></span> <span data-ttu-id="3ee39-122">En el siguiente ejemplo, los dos argumentos necesarios se enlazan con las variables de flujo de trabajo junto con el valor de resultado.</span><span class="sxs-lookup"><span data-stu-id="3ee39-122">In the following example, the two required arguments are bound to workflow variables along with the result value.</span></span> <span data-ttu-id="3ee39-123">En este ejemplo, el argumento <xref:System.Activities.Activity%601.Result%2A> se enlaza con los dos argumentos necesarios.</span><span class="sxs-lookup"><span data-stu-id="3ee39-123">In this example the <xref:System.Activities.Activity%601.Result%2A> argument is bound along with the two required arguments.</span></span> <span data-ttu-id="3ee39-124">No se exige que se enlace el argumento <xref:System.Activities.Activity%601.Result%2A> y no provoca un error de validación si no lo está.</span><span class="sxs-lookup"><span data-stu-id="3ee39-124">The <xref:System.Activities.Activity%601.Result%2A> argument is not required to be bound and does not cause a validation error if it is not.</span></span> <span data-ttu-id="3ee39-125">Es responsabilidad del autor del flujo de trabajo enlazar <xref:System.Activities.Activity%601.Result%2A> si su valor se usa en otra parte en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3ee39-125">It is the responsibility of the workflow author to bind <xref:System.Activities.Activity%601.Result%2A> if its value is used elsewhere in the workflow.</span></span>  
  
```csharp  
new Add  
{  
    Operand1 = Operand1,  
    Operand2 = Operand2,  
    Result = Result  
}  
```  
  
### <a name="validating-required-arguments-on-the-root-activity"></a><span data-ttu-id="3ee39-126">Validación de argumentos necesarios en la actividad raíz</span><span class="sxs-lookup"><span data-stu-id="3ee39-126">Validating Required Arguments on the Root Activity</span></span>  

 <span data-ttu-id="3ee39-127">Si la actividad raíz de un flujo de trabajo tiene argumentos, estos no se enlazan hasta que se invoca el flujo de trabajo y los parámetros se pasan al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3ee39-127">If the root activity of a workflow has arguments, these are not bound until the workflow is invoked and parameters are passed to the workflow.</span></span> <span data-ttu-id="3ee39-128">El siguiente flujo de trabajo pasa la validación, pero se produce una excepción si el flujo de trabajo se invoca sin pasar los argumentos necesarios, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3ee39-128">The following workflow passes validation, but an exception is thrown if the workflow is invoked without passing in the required arguments, as shown in the following example.</span></span>  
  
```csharp  
Activity wf = new Add();  
  
ValidationResults results = ActivityValidationServices.Validate(wf);  
// results has no errors or warnings, but when the workflow  
// is invoked, an InvalidWorkflowException is thrown.  
try  
{  
    WorkflowInvoker.Invoke(wf);  
}  
catch (Exception ex)  
{  
    Console.WriteLine(ex);  
}  
```  
  
 <span data-ttu-id="3ee39-129">**System.ArgumentException: Los valores de argumento de la actividad raíz son incorrectos.**</span><span class="sxs-lookup"><span data-stu-id="3ee39-129">**System.ArgumentException: The root activity's argument settings are incorrect.**</span></span>  
<span data-ttu-id="3ee39-130">**Corrija la definición de flujo de trabajo o proporcione valores de entrada para corregir estos errores:** 
 **' Add ': no se proporcionó el valor de un argumento de actividad necesario ' Operand2 '.** 
 **' Add ': no se proporcionó el valor de un argumento de actividad necesario ' Operand1 '.**</span><span class="sxs-lookup"><span data-stu-id="3ee39-130">**Either fix the workflow definition or supply input values to fix these errors:**
 **'Add': Value for a required activity argument 'Operand2' was not supplied.**
 **'Add': Value for a required activity argument 'Operand1' was not supplied.**</span></span>  <span data-ttu-id="3ee39-131">Después de haber pasado los argumentos correctos, el flujo de trabajo se completa correctamente, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3ee39-131">After the correct arguments are passed, the workflow completes successfully, as shown in the following example.</span></span>  
  
```csharp  
Add wf = new Add();  
  
ValidationResults results = ActivityValidationServices.Validate(wf);  
// results has no errors or warnings, and the workflow completes  
// successfully because the required arguments were passed.  
try  
{  
    Dictionary<string, object> wfparams = new Dictionary<string, object>  
    {  
        { "Operand1", 10 },  
        { "Operand2", 15 }  
    };  
  
    int result = WorkflowInvoker.Invoke(wf, wfparams);  
    Console.WriteLine("Result: {0}", result);  
}  
catch (Exception ex)  
{  
    Console.WriteLine(ex);  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="3ee39-132">En este ejemplo, la actividad raíz se declaró como `Add` en lugar de `Activity`, tal y como se especificó en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="3ee39-132">In this example, the root activity was declared as `Add` instead of `Activity` as in the previous example.</span></span> <span data-ttu-id="3ee39-133">Esto permite al método `WorkflowInvoker.Invoke` devolver un entero único que representa los resultados de la actividad `Add` en lugar de un diccionario de argumentos `out`.</span><span class="sxs-lookup"><span data-stu-id="3ee39-133">This allows the `WorkflowInvoker.Invoke` method to return a single integer that represents the results of the `Add` activity instead of a dictionary of `out` arguments.</span></span> <span data-ttu-id="3ee39-134">La variable `wf` también se puede declarar como `Activity<int>`.</span><span class="sxs-lookup"><span data-stu-id="3ee39-134">The variable `wf` could also have been declared as `Activity<int>`.</span></span>  
  
 <span data-ttu-id="3ee39-135">Al validar los argumentos raíz, la responsabilidad de la aplicación host es asegurarse de que se pasan todos los argumentos necesarios cuando se invoca el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3ee39-135">When validating root arguments, it is the responsibility of the host application to ensure that all required arguments are passed when the workflow is invoked.</span></span>  
  
### <a name="invoking-imperative-code-based-validation"></a><span data-ttu-id="3ee39-136">Invocar la validación imperativa basada en código</span><span class="sxs-lookup"><span data-stu-id="3ee39-136">Invoking Imperative Code-Based Validation</span></span>

<span data-ttu-id="3ee39-137">La validación basada en código imperativo proporciona una manera sencilla para que una actividad proporcione la validación sobre ella misma y está disponible para aquellas actividades que derivan de <xref:System.Activities.CodeActivity>,  <xref:System.Activities.AsyncCodeActivity> y <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="3ee39-137">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and is available for activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="3ee39-138">El código de validación se agrega a la actividad que determina cualquier error de validación o advertencias.</span><span class="sxs-lookup"><span data-stu-id="3ee39-138">Validation code that determines any validation errors or warnings is added to the activity.</span></span> <span data-ttu-id="3ee39-139">Cuando la validación se invoca en la actividad, estas advertencias o errores están contenidos en la colección devuelta por la llamada a <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="3ee39-139">When validation is invoked on the activity, these warnings or errors are contained in the collection returned by the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span></span> <span data-ttu-id="3ee39-140">En el ejemplo siguiente, se define una actividad `CreateProduct` .</span><span class="sxs-lookup"><span data-stu-id="3ee39-140">In the following example, a `CreateProduct` activity is defined.</span></span> <span data-ttu-id="3ee39-141">Si `Cost` es mayor que `Price`, se agrega un error de validación a los metadatos en la invalidación de <xref:System.Activities.CodeActivity.CacheMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="3ee39-141">If the `Cost` is greater than the `Price`, a validation error is added to the metadata in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override.</span></span>  
  
```csharp  
public sealed class CreateProduct : CodeActivity  
{  
    public double Price { get; set; }  
    public double Cost { get; set; }  
  
    // [RequiredArgument] attribute will generate a validation error
    // if the Description argument is not set.  
    [RequiredArgument]  
    public InArgument<string> Description { get; set; }  
  
    protected override void CacheMetadata(CodeActivityMetadata metadata)  
    {  
        base.CacheMetadata(metadata);  
        // Determine when the activity has been configured in an invalid way.  
        if (this.Cost > this.Price)  
        {  
            // Add a validation error with a custom message.  
            metadata.AddValidationError("The Cost must be less than or equal to the Price.");  
        }  
    }  
  
    protected override void Execute(CodeActivityContext context)  
    {  
        // Not needed for the sample.  
    }  
}  
```  
  
 <span data-ttu-id="3ee39-142">En este ejemplo, un flujo de trabajo se configura mediante la actividad `CreateProduct`.</span><span class="sxs-lookup"><span data-stu-id="3ee39-142">In this example, a workflow is configured using the `CreateProduct` activity.</span></span> <span data-ttu-id="3ee39-143">En este flujo de trabajo, `Cost` es mayor que `Price`, y el argumento `Description` necesario no está establecido.</span><span class="sxs-lookup"><span data-stu-id="3ee39-143">In this workflow, the `Cost` is greater than the `Price`, and the required `Description` argument is not set.</span></span> <span data-ttu-id="3ee39-144">Cuando se invoca la validación, se devuelven los siguientes errores.</span><span class="sxs-lookup"><span data-stu-id="3ee39-144">When validation is invoked, the following errors are returned.</span></span>  
  
```csharp  
Activity wf = new Sequence  
{  
    Activities =
    {  
        new CreateProduct  
        {  
            Cost = 75.00,  
            Price = 55.00  
            // Cost > Price and required Description argument not set.  
        },  
        new WriteLine  
        {  
            Text = "Product added."  
        }  
    }  
};  
  
ValidationResults results = ActivityValidationServices.Validate(wf);  
  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error: {0}", error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning: {0}", warning.Message);  
    }  
}  
```  
  
 <span data-ttu-id="3ee39-145">**Error: El costo debe ser menor o igual que el precio.**</span><span class="sxs-lookup"><span data-stu-id="3ee39-145">**Error: The Cost must be less than or equal to the Price.**</span></span>  
<span data-ttu-id="3ee39-146">**Error: Value for a required activity argument 'Description' was not supplied.**</span><span class="sxs-lookup"><span data-stu-id="3ee39-146">**Error: Value for a required activity argument 'Description' was not supplied.**</span></span>
> [!NOTE]
> <span data-ttu-id="3ee39-147">Los autores de actividades personalizadas pueden proporcionar lógica de validación en la invalidación del método <xref:System.Activities.CodeActivity.CacheMetadata%2A> de una actividad.</span><span class="sxs-lookup"><span data-stu-id="3ee39-147">Custom activity authors can provide validation logic in an activity's <xref:System.Activities.CodeActivity.CacheMetadata%2A> override.</span></span> <span data-ttu-id="3ee39-148">Cualquier excepción que se produzca desde el método <xref:System.Activities.CodeActivity.CacheMetadata%2A> no se trata como errores de validación.</span><span class="sxs-lookup"><span data-stu-id="3ee39-148">Any exceptions that are thrown from <xref:System.Activities.CodeActivity.CacheMetadata%2A> are not treated as validation errors.</span></span> <span data-ttu-id="3ee39-149">Estas excepciones escaparán de la llamada al método <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> y serán administradas por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3ee39-149">These exceptions will escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span>  
  
## <a name="using-validationsettings"></a><span data-ttu-id="3ee39-150">Usar ValidationSettings</span><span class="sxs-lookup"><span data-stu-id="3ee39-150">Using ValidationSettings</span></span>  

 <span data-ttu-id="3ee39-151">De forma predeterminada, todas las actividades del árbol de actividad se evalúan cuando la validación se invoca mediante <xref:System.Activities.Validation.ActivityValidationServices>.</span><span class="sxs-lookup"><span data-stu-id="3ee39-151">By default, all activities in the activity tree are evaluated when validation is invoked by <xref:System.Activities.Validation.ActivityValidationServices>.</span></span> <span data-ttu-id="3ee39-152"><xref:System.Activities.Validation.ValidationSettings> permite personalizar la validación de varias maneras diferentes configurando sus tres propiedades.</span><span class="sxs-lookup"><span data-stu-id="3ee39-152"><xref:System.Activities.Validation.ValidationSettings> allows the validation to be customized in several different ways by configuring its three properties.</span></span> <span data-ttu-id="3ee39-153"><xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> especifica si el validador debe recorrer el árbol de actividad completo o solo aplicar lógica de validación a la actividad proporcionada.</span><span class="sxs-lookup"><span data-stu-id="3ee39-153"><xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> specifies whether the validator should walk the entire activity tree or only apply validation logic to the supplied activity.</span></span> <span data-ttu-id="3ee39-154">Éste es el valor predeterminado de `false`.</span><span class="sxs-lookup"><span data-stu-id="3ee39-154">The default for this value is `false`.</span></span> <span data-ttu-id="3ee39-155"><xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> especifica una asignación de restricción adicional de un tipo a una lista de restricciones.</span><span class="sxs-lookup"><span data-stu-id="3ee39-155"><xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> specifies additional constraint mapping from a type to a list of constraints.</span></span> <span data-ttu-id="3ee39-156">Para el tipo base de cada actividad en el árbol de actividad que se esté validando, hay una búsqueda en <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>.</span><span class="sxs-lookup"><span data-stu-id="3ee39-156">For the base type of each activity in the activity tree being validated there is a lookup into <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>.</span></span> <span data-ttu-id="3ee39-157">Si se encuentra una lista de restricciones que coincida, todas las restricciones de la lista se evalúan para la actividad.</span><span class="sxs-lookup"><span data-stu-id="3ee39-157">If a matching constraint list is found, all constraints in the list are evaluated for the activity.</span></span> <span data-ttu-id="3ee39-158"><xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> especifica si el validador debe evaluar todas las restricciones o solo las especificadas en <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>.</span><span class="sxs-lookup"><span data-stu-id="3ee39-158"><xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> specifies whether the validator should evaluate all constraints or only those specified in <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>.</span></span> <span data-ttu-id="3ee39-159">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="3ee39-159">The default value is `false`.</span></span> <span data-ttu-id="3ee39-160"><xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> y <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> son útiles para que los autores de host de flujo de trabajo agreguen validación adicional a los flujos de trabajo, por ejemplo restricciones de directivas para herramientas como FxCop.</span><span class="sxs-lookup"><span data-stu-id="3ee39-160"><xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> and <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> are useful for workflow host authors to add additional validation for workflows, such as policy constraints for tools such as FxCop.</span></span> <span data-ttu-id="3ee39-161">Para obtener más información sobre las restricciones, vea [restricciones declarativas](declarative-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="3ee39-161">For more information about constraints, see [Declarative Constraints](declarative-constraints.md).</span></span>  
  
 <span data-ttu-id="3ee39-162">Para usar <xref:System.Activities.Validation.ValidationSettings>, configure las propiedades que desee y, a continuación, páselo en la llamada a <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="3ee39-162">To use <xref:System.Activities.Validation.ValidationSettings>, configure the desired properties, and then pass it in the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span></span> <span data-ttu-id="3ee39-163">En este ejemplo, se valida un flujo de trabajo que está compuesto de un <xref:System.Activities.Statements.Sequence> con una actividad `Add` personalizada.</span><span class="sxs-lookup"><span data-stu-id="3ee39-163">In this example, a workflow that consists of a <xref:System.Activities.Statements.Sequence> with a custom `Add` activity is validated.</span></span> <span data-ttu-id="3ee39-164">La actividad `Add` tiene dos argumentos necesarios.</span><span class="sxs-lookup"><span data-stu-id="3ee39-164">The `Add` activity has two required arguments.</span></span>  
  
```csharp  
public sealed class Add : CodeActivity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Operand1 { get; set; }  
  
    [RequiredArgument]  
    public InArgument<int> Operand2 { get; set; }  
  
    protected override int Execute(CodeActivityContext context)  
    {  
        return Operand1.Get(context) + Operand2.Get(context);  
    }  
}  
```  
  
 <span data-ttu-id="3ee39-165">La siguiente actividad `Add` se usa en <xref:System.Activities.Statements.Sequence>, pero no se enlazan sus dos argumentos necesarios.</span><span class="sxs-lookup"><span data-stu-id="3ee39-165">The following `Add` activity is used in a <xref:System.Activities.Statements.Sequence>, but its two required arguments are not bound.</span></span>  
  
```csharp  
Variable<int> Operand1 = new Variable<int> { Default = 10 };  
Variable<int> Operand2 = new Variable<int> { Default = 15 };  
Variable<int> Result = new Variable<int>();  
  
Activity wf = new Sequence  
{  
    Variables = { Operand1, Operand2, Result },  
    Activities =
    {  
        new Add(),  
        new WriteLine  
        {  
            Text = new InArgument<string>(env => "The result is " + Result.Get(env))  
        }  
    }  
};  
```  
  
 <span data-ttu-id="3ee39-166">En el ejemplo siguiente, la validación se realiza con la propiedad <xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> definida en `true`, por lo que sólo se valida la actividad raíz <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="3ee39-166">For the following example, validation is performed with <xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> set to `true`, so only the root <xref:System.Activities.Statements.Sequence> activity is validated.</span></span>  
  
```csharp  
ValidationSettings settings = new ValidationSettings  
{  
    SingleLevel = true  
};  
  
ValidationResults results = ActivityValidationServices.Validate(wf, settings);  
  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error: {0}", error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning: {0}", warning.Message);  
    }  
}  
```  
  
 <span data-ttu-id="3ee39-167">Este código muestra el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="3ee39-167">This code displays the following output:</span></span>  
  
 <span data-ttu-id="3ee39-168">**Sin advertencias ni errores** Aunque la `Add` actividad tiene argumentos necesarios que no están enlazados, la validación se realiza correctamente porque solo se evalúa la actividad raíz.</span><span class="sxs-lookup"><span data-stu-id="3ee39-168">**No warnings or errors** Even though the `Add` activity has required arguments that are not bound, validation is successful because only the root activity is evaluated.</span></span> <span data-ttu-id="3ee39-169">Este tipo de validación es útil sólo para validar los elementos concretos en un árbol de actividad, como la validación de un cambio de propiedad de una actividad única en un diseñador.</span><span class="sxs-lookup"><span data-stu-id="3ee39-169">This type of validation is useful for validating only specific elements in an activity tree, such as validation of a property change of a single activity in a designer.</span></span> <span data-ttu-id="3ee39-170">Tenga en cuenta que si se invoca este flujo de trabajo, se evalúa la validación completa configurada en el flujo de trabajo y se produciría <xref:System.Activities.InvalidWorkflowException>.</span><span class="sxs-lookup"><span data-stu-id="3ee39-170">Note that if this workflow is invoked, the full validation configured in the workflow is evaluated and an <xref:System.Activities.InvalidWorkflowException> would be thrown.</span></span> <span data-ttu-id="3ee39-171"><xref:System.Activities.Validation.ActivityValidationServices> y <xref:System.Activities.Validation.ValidationSettings> solo configuran la validación explícitamente invocada por el host, y no la validación que se produce cuando se invoca un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3ee39-171"><xref:System.Activities.Validation.ActivityValidationServices> and <xref:System.Activities.Validation.ValidationSettings> configure only validation explicitly invoked by the host, and not the validation that occurs when a workflow is invoked.</span></span>
