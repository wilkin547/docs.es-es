---
description: Más información acerca de cómo invocar la validación de actividad
title: Invocar validación de actividad
ms.date: 03/30/2017
ms.assetid: 22bef766-c505-4fd4-ac0f-7b363b238969
ms.openlocfilehash: dc710e76134fbd76f5217df4ea569f20e6de4445
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792666"
---
# <a name="invoking-activity-validation"></a>Invocar validación de actividad

La validación de la actividad proporciona un método para identificar y notificar los errores en la configuración de cualquier actividad antes de su ejecución. La validación se produce cuando un flujo de trabajo se modifica en el diseñador de flujo de trabajo y cuando los errores de validación o advertencias se muestran en el diseñador de flujo de trabajo. La validación también se produce en tiempo de ejecución cuando se invoca un flujo de trabajo y si se producen algunos errores de validación; la lógica de validación predeterminada produce <xref:System.Activities.InvalidWorkflowException>. Windows Workflow Foundation (WF) proporciona la <xref:System.Activities.Validation.ActivityValidationServices> clase que puede usar la aplicación de flujo de trabajo y los desarrolladores de herramientas para validar explícitamente una actividad. En este tema se describe cómo usar <xref:System.Activities.Validation.ActivityValidationServices> para realizar la validación de actividad.  
  
## <a name="using-activityvalidationservices"></a>Usar ActivityValidationServices  

 <xref:System.Activities.Validation.ActivityValidationServices> tiene dos sobrecargas de <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> que se usan para invocar la lógica de validación de una actividad. La primera sobrecarga toma la actividad raíz que se va a validar y devuelve una colección de errores de validación y advertencias. En el siguiente ejemplo, se usa una actividad `Add` personalizada que tiene dos argumentos necesarios.  
  
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
  
 La actividad `Add` se usa dentro de <xref:System.Activities.Statements.Sequence>, aunque no se enlazan sus dos argumentos necesarios, tal y como se muestra en el siguiente ejemplo.  
  
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
  
 Este flujo de trabajo se puede validar llamando a <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>. <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> devuelve una colección de errores o advertencias de validación contenidos por la actividad y cualquier elemento secundario, tal y como se muestra en el siguiente ejemplo.  
  
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
  
 Cuando se llama a <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> en este flujo de trabajo de ejemplo, se devuelven dos errores de validación.  
  
 **Error: Value for a required activity argument 'Operand2' was not supplied.**  
**Error: Value for a required activity argument 'Operand1' was not supplied.**  Si se invocara este flujo de trabajo, se produciría una excepción <xref:System.Activities.InvalidWorkflowException>, tal y como se muestra en el siguiente ejemplo.  
  
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
  
 **System.Activities.InvalidWorkflowException:**  
**Se encontraron los siguientes errores al procesar el árbol de flujo de trabajo:** 
 **' Add ': no se proporcionó el valor de un argumento de actividad necesario ' Operand2 '.** 
 **' Add ': no se proporcionó el valor de un argumento de actividad necesario ' Operand1 '.**  Para que este flujo de trabajo de ejemplo sea válido, se deben enlazar los dos argumentos necesarios de la actividad `Add`. En el siguiente ejemplo, los dos argumentos necesarios se enlazan con las variables de flujo de trabajo junto con el valor de resultado. En este ejemplo, el argumento <xref:System.Activities.Activity%601.Result%2A> se enlaza con los dos argumentos necesarios. No se exige que se enlace el argumento <xref:System.Activities.Activity%601.Result%2A> y no provoca un error de validación si no lo está. Es responsabilidad del autor del flujo de trabajo enlazar <xref:System.Activities.Activity%601.Result%2A> si su valor se usa en otra parte en el flujo de trabajo.  
  
```csharp  
new Add  
{  
    Operand1 = Operand1,  
    Operand2 = Operand2,  
    Result = Result  
}  
```  
  
### <a name="validating-required-arguments-on-the-root-activity"></a>Validación de argumentos necesarios en la actividad raíz  

 Si la actividad raíz de un flujo de trabajo tiene argumentos, estos no se enlazan hasta que se invoca el flujo de trabajo y los parámetros se pasan al flujo de trabajo. El siguiente flujo de trabajo pasa la validación, pero se produce una excepción si el flujo de trabajo se invoca sin pasar los argumentos necesarios, tal y como se muestra en el ejemplo siguiente.  
  
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
  
 **System.ArgumentException: Los valores de argumento de la actividad raíz son incorrectos.**  
**Corrija la definición de flujo de trabajo o proporcione valores de entrada para corregir estos errores:** 
 **' Add ': no se proporcionó el valor de un argumento de actividad necesario ' Operand2 '.** 
 **' Add ': no se proporcionó el valor de un argumento de actividad necesario ' Operand1 '.**  Después de haber pasado los argumentos correctos, el flujo de trabajo se completa correctamente, tal y como se muestra en el siguiente ejemplo.  
  
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
> En este ejemplo, la actividad raíz se declaró como `Add` en lugar de `Activity`, tal y como se especificó en el ejemplo anterior. Esto permite al método `WorkflowInvoker.Invoke` devolver un entero único que representa los resultados de la actividad `Add` en lugar de un diccionario de argumentos `out`. La variable `wf` también se puede declarar como `Activity<int>`.  
  
 Al validar los argumentos raíz, la responsabilidad de la aplicación host es asegurarse de que se pasan todos los argumentos necesarios cuando se invoca el flujo de trabajo.  
  
### <a name="invoking-imperative-code-based-validation"></a>Invocar la validación imperativa basada en código

La validación basada en código imperativo proporciona una manera sencilla para que una actividad proporcione la validación sobre ella misma y está disponible para aquellas actividades que derivan de <xref:System.Activities.CodeActivity>,  <xref:System.Activities.AsyncCodeActivity> y <xref:System.Activities.NativeActivity>. El código de validación se agrega a la actividad que determina cualquier error de validación o advertencias. Cuando la validación se invoca en la actividad, estas advertencias o errores están contenidos en la colección devuelta por la llamada a <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>. En el ejemplo siguiente, se define una actividad `CreateProduct` . Si `Cost` es mayor que `Price`, se agrega un error de validación a los metadatos en la invalidación de <xref:System.Activities.CodeActivity.CacheMetadata%2A>.  
  
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
  
 En este ejemplo, un flujo de trabajo se configura mediante la actividad `CreateProduct`. En este flujo de trabajo, `Cost` es mayor que `Price`, y el argumento `Description` necesario no está establecido. Cuando se invoca la validación, se devuelven los siguientes errores.  
  
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
  
 **Error: El costo debe ser menor o igual que el precio.**  
**Error: Value for a required activity argument 'Description' was not supplied.**
> [!NOTE]
> Los autores de actividades personalizadas pueden proporcionar lógica de validación en la invalidación del método <xref:System.Activities.CodeActivity.CacheMetadata%2A> de una actividad. Cualquier excepción que se produzca desde el método <xref:System.Activities.CodeActivity.CacheMetadata%2A> no se trata como errores de validación. Estas excepciones escaparán de la llamada al método <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> y serán administradas por el autor de la llamada.  
  
## <a name="using-validationsettings"></a>Usar ValidationSettings  

 De forma predeterminada, todas las actividades del árbol de actividad se evalúan cuando la validación se invoca mediante <xref:System.Activities.Validation.ActivityValidationServices>. <xref:System.Activities.Validation.ValidationSettings> permite personalizar la validación de varias maneras diferentes configurando sus tres propiedades. <xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> especifica si el validador debe recorrer el árbol de actividad completo o solo aplicar lógica de validación a la actividad proporcionada. Éste es el valor predeterminado de `false`. <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> especifica una asignación de restricción adicional de un tipo a una lista de restricciones. Para el tipo base de cada actividad en el árbol de actividad que se esté validando, hay una búsqueda en <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>. Si se encuentra una lista de restricciones que coincida, todas las restricciones de la lista se evalúan para la actividad. <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> especifica si el validador debe evaluar todas las restricciones o solo las especificadas en <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>. El valor predeterminado es `false`. <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> y <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> son útiles para que los autores de host de flujo de trabajo agreguen validación adicional a los flujos de trabajo, por ejemplo restricciones de directivas para herramientas como FxCop. Para obtener más información sobre las restricciones, vea [restricciones declarativas](declarative-constraints.md).  
  
 Para usar <xref:System.Activities.Validation.ValidationSettings>, configure las propiedades que desee y, a continuación, páselo en la llamada a <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>. En este ejemplo, se valida un flujo de trabajo que está compuesto de un <xref:System.Activities.Statements.Sequence> con una actividad `Add` personalizada. La actividad `Add` tiene dos argumentos necesarios.  
  
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
  
 La siguiente actividad `Add` se usa en <xref:System.Activities.Statements.Sequence>, pero no se enlazan sus dos argumentos necesarios.  
  
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
  
 En el ejemplo siguiente, la validación se realiza con la propiedad <xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> definida en `true`, por lo que sólo se valida la actividad raíz <xref:System.Activities.Statements.Sequence>.  
  
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
  
 Este código muestra el siguiente resultado:  
  
 **Sin advertencias ni errores** Aunque la `Add` actividad tiene argumentos necesarios que no están enlazados, la validación se realiza correctamente porque solo se evalúa la actividad raíz. Este tipo de validación es útil sólo para validar los elementos concretos en un árbol de actividad, como la validación de un cambio de propiedad de una actividad única en un diseñador. Tenga en cuenta que si se invoca este flujo de trabajo, se evalúa la validación completa configurada en el flujo de trabajo y se produciría <xref:System.Activities.InvalidWorkflowException>. <xref:System.Activities.Validation.ActivityValidationServices> y <xref:System.Activities.Validation.ValidationSettings> solo configuran la validación explícitamente invocada por el host, y no la validación que se produce cuando se invoca un flujo de trabajo.
