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
# <a name="declarative-constraints"></a>Restricciones declarativas

Las restricciones declarativas proporcionan un método eficaz de validación para una actividad y sus relaciones con otras actividades. Las restricciones se configuran para una actividad durante el proceso de creación, aunque el host del flujo de trabajo puede especificar también las restricciones adicionales. En este tema se ofrece información general sobre cómo usar restricciones declarativas para proporcionar la validación de actividad.  
  
## <a name="using-declarative-constraints"></a>Usar restricciones declarativas  

 Una restricción es una actividad que contiene la lógica de validación. Esta actividad de restricción se puede crear en código o en XAML. Una vez creada la actividad de restricción, los autores de actividad agregan esta restricción a la propiedad <xref:System.Activities.Activity.Constraints%2A> de la actividad que se vaya a validar, o bien usan la restricción para proporcionar validación adicional mediante la propiedad <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> de una instancia de <xref:System.Activities.Validation.ValidationSettings>. La lógica de validación puede estar compuesta de validaciones simples como, por ejemplo, validar los metadatos de una actividad, aunque también puede realizar la validación que tiene en cuenta la relación de la actividad actual para sus actividades primarias, secundarias y del mismo nivel. Las restricciones se crean mediante la actividad <xref:System.Activities.Validation.Constraint%601>. Además, se proporcionan varias actividades de validación para ayudar en la creación de errores de validación y advertencias, y para proporcionar información sobre actividades relacionadas en el flujo de trabajo.  
  
### <a name="assertvalidation-and-addvalidationerror"></a>AssertValidation y AddValidationError  

 La actividad <xref:System.Activities.Validation.AssertValidation> evalúa la expresión a la que se hace referencia con la propiedad <xref:System.Activities.Validation.AssertValidation.Assertion%2A>. Si la expresión se evalúa como `false`, se agrega un error de validación o advertencia a la clase <xref:System.Activities.Validation.ValidationResults>. La propiedad <xref:System.Activities.Validation.AssertValidation.Message%2A> describe el error de validación mientras que la propiedad <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> indica si el error de la validación es un error o una advertencia. El valor predeterminado de <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> es `false`.  
  
 En el siguiente ejemplo, se declara una restricción que devuelve una advertencia de validación si la propiedad <xref:System.Activities.Activity.DisplayName%2A> de la actividad que se está validando tiene dos caracteres o menos de longitud. El parámetro de tipo genérico usado para <xref:System.Activities.Validation.Constraint%601> especifica el tipo de actividad que valida la restricción. Esta restricción usa <xref:System.Activities.Activity> como el tipo genérico y se puede usar para validar todos los tipos de actividades.  
  
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
  
 Para especificar esta restricción para una actividad, se agrega a la propiedad <xref:System.Activities.Activity.Constraints%2A> de la actividad, tal y como se muestra en el siguiente código de ejemplo.  
  
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
  
 El host también puede especificar esta limitación para actividades de un flujo de trabajo mediante <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>, descrita en la sección siguiente  
  
 La actividad <xref:System.Activities.Validation.AddValidationError> se usa para generar un error de validación o advertencia sin tener que usar la evaluación de una expresión. Sus propiedades son similares a <xref:System.Activities.Validation.AssertValidation> y se puede usar junto con las actividades de control de flujo de una restricción como la actividad <xref:System.Activities.Statements.If>.
  
### <a name="workflow-relationship-activities"></a>Actividades de relación de flujo de trabajo

Hay disponibles varias actividades de validación que proporcionan información sobre las demás actividades del flujo de trabajo en relación con la actividad que se va a validar. <xref:System.Activities.Validation.GetParentChain> devuelve una colección de actividades que contiene todas las actividades entre la actividad actual y la actividad raíz. <xref:System.Activities.Validation.GetChildSubtree> proporciona una colección de actividades que contiene las actividades secundarias en un patrón recursivo y <xref:System.Activities.Validation.GetWorkflowTree> obtiene todas las actividades del flujo de trabajo.  
  
En el ejemplo siguiente, se define una actividad `CreateState` . La actividad `CreateState` debe estar dentro de una actividad `CreateCountry` y el método `GetParent` devuelve una restricción que aplica este requisito. `GetParent` usa la actividad <xref:System.Activities.Validation.GetParentChain> junto con una actividad <xref:System.Activities.Statements.ForEach%601> para inspeccionar las actividades primarias de la actividad `CreateState` para determinar si se cumple el requisito.  
  
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
  
## <a name="additional-constraints"></a>Restricciones adicionales  

 Los autores de host de flujo de trabajo pueden especificar las restricciones de validación adicionales para las actividades en un flujo de trabajo creando las restricciones y agregándolas al diccionario de la propiedad <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> de una instancia de <xref:System.Activities.Validation.ValidationSettings>. Cada elemento de <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> contiene el tipo de actividad en el que se aplican las restricciones y una lista de las restricciones adicionales para ese tipo de actividad. Cuando se invoca la validación para el flujo de trabajo, cada actividad del tipo especificado, incluidas las clases derivadas, evalúa las restricciones. En este ejemplo, la restricción `ActivityDisplayNameIsNotSetWarning` de la sección anterior se aplica a todas las actividades en un flujo de trabajo.  
  
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
  
 Si la propiedad <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> de <xref:System.Activities.Validation.ValidationSettings> es `true`, sólo se evaluarán las restricciones adicionales especificadas cuando la validación se invoca llamando al método <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>. Esto puede ser útil a la hora de inspeccionar flujos de trabajo para configuraciones de validación concretas. Sin embargo, tenga en cuenta que cuando se invoca el flujo de trabajo, la lógica de validación configurada en el flujo de trabajo se evalúa y se debe pasar para que el flujo de trabajo comience correctamente. Para obtener más información sobre cómo invocar la validación, vea [invocación](invoking-activity-validation.md)de la validación de actividad.
