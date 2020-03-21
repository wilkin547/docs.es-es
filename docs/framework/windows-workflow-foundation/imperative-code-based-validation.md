---
title: Validación imperativa basada en código
ms.date: 03/30/2017
ms.assetid: ae12537c-455e-42b1-82f4-cea4c46c023e
ms.openlocfilehash: f3b07d0ab06b3753286c929b90e713a6941684ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143101"
---
# <a name="imperative-code-based-validation"></a><span data-ttu-id="a4bb9-102">Validación imperativa basada en código</span><span class="sxs-lookup"><span data-stu-id="a4bb9-102">Imperative Code-Based Validation</span></span>

<span data-ttu-id="a4bb9-103">La validación basada en código imperativo proporciona una manera sencilla para que una actividad proporcione la validación sobre ella misma y está disponible para aquellas actividades que derivan de <xref:System.Activities.CodeActivity>,  <xref:System.Activities.AsyncCodeActivity> y <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-103">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and is available for activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="a4bb9-104">El código de validación se agrega a la actividad que determina cualquier error de validación o advertencias.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-104">Validation code that determines any validation errors or warnings is added to the activity.</span></span>  
  
## <a name="using-code-based-validation"></a><span data-ttu-id="a4bb9-105">Usar validación basada en código</span><span class="sxs-lookup"><span data-stu-id="a4bb9-105">Using Code-Based Validation</span></span>

<span data-ttu-id="a4bb9-106">Las actividades que derivan de <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> y <xref:System.Activities.NativeActivity> admiten la validación basada en código.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-106">Code-based validation is supported by activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="a4bb9-107">El código de la validación se puede colocar en el reemplazo de <xref:System.Activities.CodeActivity.CacheMetadata%2A>, mientras que los errores o advertencias de validación se pueden agregar al argumento de metadatos.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-107">Validation code can be placed in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override, and validation errors or warnings can be added to the metadata argument.</span></span> <span data-ttu-id="a4bb9-108">En el siguiente ejemplo, si `Cost` es mayor que `Price`, se agrega un error de validación a los metadatos.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-108">In the following example, if the `Cost` is greater than the `Price`, a validation error is added to the metadata.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a4bb9-109">Observe que `Cost` y `Price` no son argumentos para la actividad, sino propiedades que se establecen en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-109">Note that `Cost` and `Price` are not arguments to the activity, but are properties that are set at design time.</span></span> <span data-ttu-id="a4bb9-110">Por eso sus valores se pueden validar en la invalidación de <xref:System.Activities.CodeActivity.CacheMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-110">That is why their values can be validated in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override.</span></span> <span data-ttu-id="a4bb9-111">El valor de los datos que atraviesan un argumento no se puede validar en tiempo de diseño porque los datos no fluyen hasta el tiempo de ejecución, pero los argumentos de actividad se pueden validar para asegurarse de que están enlazados mediante el atributo `RequiredArgument` y grupos de sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-111">The value of the data flowing through an argument cannot be validated at design time because the data does not flow until run time, but activity arguments can be validated to ensure that they are bound by using the `RequiredArgument` attribute and overload groups.</span></span> <span data-ttu-id="a4bb9-112">Este código de ejemplo examina el atributo `RequiredArgument` para el argumento `Description` y si no está enlazado, se genera un error de validación.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-112">This example code sees the `RequiredArgument` attribute for the `Description` argument, and if it is not bound then a validation error is generated.</span></span> <span data-ttu-id="a4bb9-113">Los argumentos necesarios se tratan en [Argumentos necesarios y Grupos](required-arguments-and-overload-groups.md)de sobrecarga .</span><span class="sxs-lookup"><span data-stu-id="a4bb9-113">Required arguments are covered in [Required Arguments and Overload Groups](required-arguments-and-overload-groups.md).</span></span>  
  
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
  
 <span data-ttu-id="a4bb9-114">De forma predeterminada, se agrega un error de validación a los metadatos cuando se llama a <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A>.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-114">By default, a validation error is added to the metadata when <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> is called.</span></span> <span data-ttu-id="a4bb9-115">Para agregar una advertencia de validación, use la sobrecarga de <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> que toma una clase <xref:System.Activities.Validation.ValidationError> y especifica que <xref:System.Activities.Validation.ValidationError> representa una advertencia al establecer la propiedad <xref:System.Activities.Validation.ValidationError.IsWarning%2A>.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-115">To add a validation warning, use the <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> overload that takes a <xref:System.Activities.Validation.ValidationError>, and specify that the <xref:System.Activities.Validation.ValidationError> represents a warning by setting the <xref:System.Activities.Validation.ValidationError.IsWarning%2A> property.</span></span>  
  
 <span data-ttu-id="a4bb9-116">La validación se produce cuando un flujo de trabajo se modifica en el diseñador de flujo de trabajo y cuando los errores de validación o advertencias se muestran en el diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-116">Validation occurs when a workflow is modified in the workflow designer and any validation errors or warnings are displayed in the workflow designer.</span></span> <span data-ttu-id="a4bb9-117">La validación también se produce en tiempo de ejecución cuando se invoca un flujo de trabajo y si se producen algunos errores de validación; la lógica de validación predeterminada produce <xref:System.Activities.InvalidWorkflowException>.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-117">Validation also occurs at run time when a workflow is invoked and if any validation errors occur, an <xref:System.Activities.InvalidWorkflowException> is thrown by the default validation logic.</span></span> <span data-ttu-id="a4bb9-118">Para obtener más información sobre cómo invocar la validación y obtener acceso a cualquier advertencia o error de validación, vea [Invocar validación](invoking-activity-validation.md)de actividad .</span><span class="sxs-lookup"><span data-stu-id="a4bb9-118">For more information about invoking validation and accessing any validation warnings or errors, see [Invoking Activity Validation](invoking-activity-validation.md).</span></span>  
  
 <span data-ttu-id="a4bb9-119">Cualquier excepción que se produzca desde el método <xref:System.Activities.CodeActivity.CacheMetadata%2A> no se trata como errores de validación.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-119">Any exceptions that are thrown from <xref:System.Activities.CodeActivity.CacheMetadata%2A> are not treated as validation errors.</span></span> <span data-ttu-id="a4bb9-120">Estas excepciones escaparán de la llamada al método <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> y serán administradas por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-120">These exceptions will escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span>  
  
 <span data-ttu-id="a4bb9-121">La validación basada en código es útil para validar la actividad que contiene el código, pero no tiene visibilidad en las otras actividades en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a4bb9-121">Code-based validation is useful for validating the activity that contains the code, but it does not have visibility into the other activities in the workflow.</span></span> <span data-ttu-id="a4bb9-122">La validación de restricciones declarativas proporciona la capacidad de validar las relaciones entre una actividad y otras actividades del flujo de trabajo y se trata en el tema [Restricciones declarativas.](declarative-constraints.md)</span><span class="sxs-lookup"><span data-stu-id="a4bb9-122">Declarative constraints validation provides the ability to validate the relationships between an activity and other activities in the workflow, and is covered in the [Declarative Constraints](declarative-constraints.md) topic.</span></span>
