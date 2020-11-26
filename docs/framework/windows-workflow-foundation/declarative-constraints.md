---
title: Restricciones declarativas
ms.date: 03/30/2017
ms.assetid: 67001ed1-7f4d-4ada-ae57-a31176901a53
ms.openlocfilehash: 9098a3d79337689fef6d37e4cccf3633d8128a10
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236460"
---
# <a name="declarative-constraints"></a><span data-ttu-id="b8c12-102">Restricciones declarativas</span><span class="sxs-lookup"><span data-stu-id="b8c12-102">Declarative Constraints</span></span>

<span data-ttu-id="b8c12-103">Las restricciones declarativas proporcionan un método eficaz de validación para una actividad y sus relaciones con otras actividades.</span><span class="sxs-lookup"><span data-stu-id="b8c12-103">Declarative constraints provide a powerful method of validation for an activity and its relationships with other activities.</span></span> <span data-ttu-id="b8c12-104">Las restricciones se configuran para una actividad durante el proceso de creación, aunque el host del flujo de trabajo puede especificar también las restricciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="b8c12-104">Constraints are configured for an activity during the authoring process, but additional constraints can also be specified by the workflow host.</span></span> <span data-ttu-id="b8c12-105">En este tema se ofrece información general sobre cómo usar restricciones declarativas para proporcionar la validación de actividad.</span><span class="sxs-lookup"><span data-stu-id="b8c12-105">This topic provides an overview of using declarative constraints to provide activity validation.</span></span>  
  
## <a name="using-declarative-constraints"></a><span data-ttu-id="b8c12-106">Usar restricciones declarativas</span><span class="sxs-lookup"><span data-stu-id="b8c12-106">Using Declarative Constraints</span></span>  

 <span data-ttu-id="b8c12-107">Una restricción es una actividad que contiene la lógica de validación.</span><span class="sxs-lookup"><span data-stu-id="b8c12-107">A constraint is an activity that contains validation logic.</span></span> <span data-ttu-id="b8c12-108">Esta actividad de restricción se puede crear en código o en XAML.</span><span class="sxs-lookup"><span data-stu-id="b8c12-108">This constraint activity can be authored in code or in XAML.</span></span> <span data-ttu-id="b8c12-109">Una vez creada la actividad de restricción, los autores de actividad agregan esta restricción a la propiedad <xref:System.Activities.Activity.Constraints%2A> de la actividad que se vaya a validar, o bien usan la restricción para proporcionar validación adicional mediante la propiedad <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> de una instancia de <xref:System.Activities.Validation.ValidationSettings>.</span><span class="sxs-lookup"><span data-stu-id="b8c12-109">After a constraint activity is created, activity authors add this constraint to the <xref:System.Activities.Activity.Constraints%2A> property of the activity to validate, or they use the constraint to provide additional validation by using the <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> property of a <xref:System.Activities.Validation.ValidationSettings> instance.</span></span> <span data-ttu-id="b8c12-110">La lógica de validación puede estar compuesta de validaciones simples como, por ejemplo, validar los metadatos de una actividad, aunque también puede realizar la validación que tiene en cuenta la relación de la actividad actual para sus actividades primarias, secundarias y del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="b8c12-110">The validation logic can consist of simple validations such as validating an activity’s metadata, but it can also perform validation that takes into account the relationship of the current activity to its parent, children, and sibling activities.</span></span> <span data-ttu-id="b8c12-111">Las restricciones se crean mediante la actividad <xref:System.Activities.Validation.Constraint%601>. Además, se proporcionan varias actividades de validación para ayudar en la creación de errores de validación y advertencias, y para proporcionar información sobre actividades relacionadas en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b8c12-111">Constraints are authored by using the <xref:System.Activities.Validation.Constraint%601> activity, and several additional validation activities are provided to assist with the creation of validation errors and warnings and to provide information about related activities in the workflow.</span></span>  
  
### <a name="assertvalidation-and-addvalidationerror"></a><span data-ttu-id="b8c12-112">AssertValidation y AddValidationError</span><span class="sxs-lookup"><span data-stu-id="b8c12-112">AssertValidation and AddValidationError</span></span>  

 <span data-ttu-id="b8c12-113">La actividad <xref:System.Activities.Validation.AssertValidation> evalúa la expresión a la que se hace referencia con la propiedad <xref:System.Activities.Validation.AssertValidation.Assertion%2A>. Si la expresión se evalúa como `false`, se agrega un error de validación o advertencia a la clase <xref:System.Activities.Validation.ValidationResults>.</span><span class="sxs-lookup"><span data-stu-id="b8c12-113">The <xref:System.Activities.Validation.AssertValidation> activity evaluates the expression referenced by its <xref:System.Activities.Validation.AssertValidation.Assertion%2A> property, and if the expression evaluates to `false`, a validation error or warning is added to the <xref:System.Activities.Validation.ValidationResults>.</span></span> <span data-ttu-id="b8c12-114">La propiedad <xref:System.Activities.Validation.AssertValidation.Message%2A> describe el error de validación mientras que la propiedad <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> indica si el error de la validación es un error o una advertencia.</span><span class="sxs-lookup"><span data-stu-id="b8c12-114">The <xref:System.Activities.Validation.AssertValidation.Message%2A> property describes the validation error and the <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> property indicates whether the validation failure is an error or a warning.</span></span> <span data-ttu-id="b8c12-115">El valor predeterminado de <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> es `false`.</span><span class="sxs-lookup"><span data-stu-id="b8c12-115">The default value for <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> is `false`.</span></span>  
  
 <span data-ttu-id="b8c12-116">En el siguiente ejemplo, se declara una restricción que devuelve una advertencia de validación si la propiedad <xref:System.Activities.Activity.DisplayName%2A> de la actividad que se está validando tiene dos caracteres o menos de longitud.</span><span class="sxs-lookup"><span data-stu-id="b8c12-116">In the following example, a constraint is declared that returns a validation warning if the <xref:System.Activities.Activity.DisplayName%2A> of the activity being validated is two characters or less in length.</span></span> <span data-ttu-id="b8c12-117">El parámetro de tipo genérico usado para <xref:System.Activities.Validation.Constraint%601> especifica el tipo de actividad que valida la restricción.</span><span class="sxs-lookup"><span data-stu-id="b8c12-117">The generic type parameter used for <xref:System.Activities.Validation.Constraint%601> specifies the type of activity that is validated by the constraint.</span></span> <span data-ttu-id="b8c12-118">Esta restricción usa <xref:System.Activities.Activity> como el tipo genérico y se puede usar para validar todos los tipos de actividades.</span><span class="sxs-lookup"><span data-stu-id="b8c12-118">This constraint uses <xref:System.Activities.Activity> as the generic type and can be used to validate all types of activities.</span></span>  
  
```csharp  
public static Constraint ActivityDisplayNameIsNotSetWarning()  
{  
    DelegateInArgument<Activity> element = new DelegateInArgument<Activity>();  
  
    return new Constraint<Activity>  
    {  
        Body = new ActivityAction<Activity, ValidationContext>  
        {  
            Argument1 = element,  
            Handler = new AssertValidation  
            {  
                IsWarning = true,  
                Assertion = new InArgument<bool>(env => (element.Get(env).DisplayName.Length > 2)),  
                Message = new InArgument<string>("It is a best practice to have a DisplayName of more than 2 characters."),  
            }  
        }  
    };  
}  
```  
  
 <span data-ttu-id="b8c12-119">Para especificar esta restricción para una actividad, se agrega a la propiedad <xref:System.Activities.Activity.Constraints%2A> de la actividad, tal y como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b8c12-119">To specify this constraint for an activity, it is added to the <xref:System.Activities.Activity.Constraints%2A> of the activity, as shown in the following example code.</span></span>  
  
```csharp  
public sealed class SampleActivity : CodeActivity  
{  
    public SampleActivity()  
    {  
        base.Constraints.Add(ActivityDisplayNameIsNotSetWarning());  
    }  
  
    // Activity implementation omitted.  
}  
```  
  
 <span data-ttu-id="b8c12-120">El host también puede especificar esta limitación para actividades de un flujo de trabajo mediante <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>, descrita en la sección siguiente</span><span class="sxs-lookup"><span data-stu-id="b8c12-120">The host could also specify this constraint for activities in a workflow by using <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>, which is covered in the next section.</span></span>  
  
 <span data-ttu-id="b8c12-121">La actividad <xref:System.Activities.Validation.AddValidationError> se usa para generar un error de validación o advertencia sin tener que usar la evaluación de una expresión.</span><span class="sxs-lookup"><span data-stu-id="b8c12-121">The <xref:System.Activities.Validation.AddValidationError> activity is used to generate a validation error or warning without requiring the evaluation of an expression.</span></span> <span data-ttu-id="b8c12-122">Sus propiedades son similares a <xref:System.Activities.Validation.AssertValidation> y se puede usar junto con las actividades de control de flujo de una restricción como la actividad <xref:System.Activities.Statements.If>.</span><span class="sxs-lookup"><span data-stu-id="b8c12-122">Its properties are similar to <xref:System.Activities.Validation.AssertValidation> and it can be used in conjunction with flow control activities of a constraint such as the <xref:System.Activities.Statements.If> activity.</span></span>
  
### <a name="workflow-relationship-activities"></a><span data-ttu-id="b8c12-123">Actividades de relación de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b8c12-123">Workflow Relationship Activities</span></span>

<span data-ttu-id="b8c12-124">Hay disponibles varias actividades de validación que proporcionan información sobre las demás actividades del flujo de trabajo en relación con la actividad que se va a validar.</span><span class="sxs-lookup"><span data-stu-id="b8c12-124">Several validation activities are available that provide information about the other activities in the workflow in relation to the activity being validated.</span></span> <span data-ttu-id="b8c12-125"><xref:System.Activities.Validation.GetParentChain> devuelve una colección de actividades que contiene todas las actividades entre la actividad actual y la actividad raíz.</span><span class="sxs-lookup"><span data-stu-id="b8c12-125"><xref:System.Activities.Validation.GetParentChain> returns a collection of activities that contains all of the activities between the current activity and the root activity.</span></span> <span data-ttu-id="b8c12-126"><xref:System.Activities.Validation.GetChildSubtree> proporciona una colección de actividades que contiene las actividades secundarias en un patrón recursivo y <xref:System.Activities.Validation.GetWorkflowTree> obtiene todas las actividades del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b8c12-126"><xref:System.Activities.Validation.GetChildSubtree> provides a collection of activities that contains the child activities in a recursive pattern, and <xref:System.Activities.Validation.GetWorkflowTree> gets all the activities in the workflow.</span></span>  
  
<span data-ttu-id="b8c12-127">En el ejemplo siguiente, se define una actividad `CreateState` .</span><span class="sxs-lookup"><span data-stu-id="b8c12-127">In the following example, a `CreateState` activity is defined.</span></span> <span data-ttu-id="b8c12-128">La actividad `CreateState` debe estar dentro de una actividad `CreateCountry` y el método `GetParent` devuelve una restricción que aplica este requisito.</span><span class="sxs-lookup"><span data-stu-id="b8c12-128">The `CreateState` activity must be contained within a `CreateCountry` activity, and the `GetParent` method returns a constraint that enforces this requirement.</span></span> <span data-ttu-id="b8c12-129">`GetParent` usa la actividad <xref:System.Activities.Validation.GetParentChain> junto con una actividad <xref:System.Activities.Statements.ForEach%601> para inspeccionar las actividades primarias de la actividad `CreateState` para determinar si se cumple el requisito.</span><span class="sxs-lookup"><span data-stu-id="b8c12-129">`GetParent` uses the <xref:System.Activities.Validation.GetParentChain> activity in conjunction with a <xref:System.Activities.Statements.ForEach%601> activity to inspect the parent activities of the `CreateState` activity to determine if the requirement is met.</span></span>  
  
```csharp  
public sealed class CreateState : CodeActivity  
{  
    public CreateState()  
    {  
        base.Constraints.Add(CheckParent());  
        this.Cities = new List<Activity>();
    }  
  
    public List<Activity> Cities { get; set; }  
  
    public string Name { get; set; }
  
    static Constraint CheckParent()  
    {  
        DelegateInArgument<CreateState> element = new DelegateInArgument<CreateState>();  
        DelegateInArgument<ValidationContext> context = new DelegateInArgument<ValidationContext>();
        Variable<bool> result = new Variable<bool>();  
        DelegateInArgument<Activity> parent = new DelegateInArgument<Activity>();  
  
        return new Constraint<CreateState>  
        {
            Body = new ActivityAction<CreateState,ValidationContext>  
            {
                Argument1 = element,  
                Argument2 = context,  
                Handler = new Sequence  
                {  
                    Variables =  
                    {  
                        result
                    },  
                    Activities =  
                    {  
                        new ForEach<Activity>  
                        {
                            Values = new GetParentChain  
                            {  
                                ValidationContext = context
                            },  
                            Body = new ActivityAction<Activity>  
                            {
                                Argument = parent,
                                Handler = new If()  
                                {
                                    Condition = new InArgument<bool>((env) => object.Equals(parent.Get(env).GetType(),typeof(CreateCountry))),
                                    Then = new Assign<bool>  
                                    {  
                                        Value = true,  
                                        To = result  
                                    }  
                                }  
                            }
                        },  
                        new AssertValidation  
                        {  
                            Assertion = new InArgument<bool>(result),  
                            Message = new InArgument<string> ("CreateState has to be inside a CreateCountry activity"),
                        }  
                    }  
                }  
            }  
        };  
    }  
  
    protected override void Execute(CodeActivityContext context)  
    {  
        // not needed for the sample  
    }  
}  
```
  
## <a name="additional-constraints"></a><span data-ttu-id="b8c12-130">Restricciones adicionales</span><span class="sxs-lookup"><span data-stu-id="b8c12-130">Additional Constraints</span></span>  

 <span data-ttu-id="b8c12-131">Los autores de host de flujo de trabajo pueden especificar las restricciones de validación adicionales para las actividades en un flujo de trabajo creando las restricciones y agregándolas al diccionario de la propiedad <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> de una instancia de <xref:System.Activities.Validation.ValidationSettings>.</span><span class="sxs-lookup"><span data-stu-id="b8c12-131">Workflow host authors can specify additional validation constraints for activities in a workflow by creating constraints and adding them to the <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> dictionary of a <xref:System.Activities.Validation.ValidationSettings> instance.</span></span> <span data-ttu-id="b8c12-132">Cada elemento de <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> contiene el tipo de actividad en el que se aplican las restricciones y una lista de las restricciones adicionales para ese tipo de actividad.</span><span class="sxs-lookup"><span data-stu-id="b8c12-132">Each item in <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> contains the type of activity for which the constraints apply and a list of the additional constraints for that type of activity.</span></span> <span data-ttu-id="b8c12-133">Cuando se invoca la validación para el flujo de trabajo, cada actividad del tipo especificado, incluidas las clases derivadas, evalúa las restricciones.</span><span class="sxs-lookup"><span data-stu-id="b8c12-133">When validation is invoked for the workflow, each activity of the specified type, including derived classes, evaluates the constraints.</span></span> <span data-ttu-id="b8c12-134">En este ejemplo, la restricción `ActivityDisplayNameIsNotSetWarning` de la sección anterior se aplica a todas las actividades en un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b8c12-134">In this example, the `ActivityDisplayNameIsNotSetWarning` constraint from the previous section is applied to all activities in a workflow.</span></span>  
  
```csharp  
Activity wf = new Sequence  
{  
    // Workflow Details Omitted.  
};  
  
ValidationSettings settings = new ValidationSettings()  
{  
  
    AdditionalConstraints =  
    {  
        {typeof(Activity), new List<Constraint> {ActivityDisplayNameIsNotSetWarning()}},
    }  
};  
  
// Validate the workflow.  
ValidationResults results = ActivityValidationServices.Validate(wf, settings);  
  
// Evaluate the results.  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error in " + error.Source.DisplayName + ": " + error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning in " + warning.Source.DisplayName + ": " + warning.Message);  
    }  
}  
```  
  
 <span data-ttu-id="b8c12-135">Si la propiedad <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> de <xref:System.Activities.Validation.ValidationSettings> es `true`, sólo se evaluarán las restricciones adicionales especificadas cuando la validación se invoca llamando al método <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="b8c12-135">If the <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> property of <xref:System.Activities.Validation.ValidationSettings> is `true`, then only the specified additional constraints are evaluated when validation is invoked by calling <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span></span> <span data-ttu-id="b8c12-136">Esto puede ser útil a la hora de inspeccionar flujos de trabajo para configuraciones de validación concretas.</span><span class="sxs-lookup"><span data-stu-id="b8c12-136">This can be useful for inspecting workflows for specific validation configurations.</span></span> <span data-ttu-id="b8c12-137">Sin embargo, tenga en cuenta que cuando se invoca el flujo de trabajo, la lógica de validación configurada en el flujo de trabajo se evalúa y se debe pasar para que el flujo de trabajo comience correctamente.</span><span class="sxs-lookup"><span data-stu-id="b8c12-137">Note however that when the workflow is invoked, the validation logic configured in the workflow is evaluated and must pass for the workflow to successfully begin.</span></span> <span data-ttu-id="b8c12-138">Para obtener más información sobre cómo invocar la validación, vea [invocación](invoking-activity-validation.md)de la validación de actividad.</span><span class="sxs-lookup"><span data-stu-id="b8c12-138">For more information about invoking validation, see [Invoking Activity Validation](invoking-activity-validation.md).</span></span>
