---
description: 'Más información acerca de: validación de Code-Based imperativa'
title: Validación imperativa basada en código
ms.date: 03/30/2017
ms.assetid: ae12537c-455e-42b1-82f4-cea4c46c023e
ms.openlocfilehash: 36759572393be613a569c4846e3610fcbbde2a51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792705"
---
# <a name="imperative-code-based-validation"></a>Validación imperativa basada en código

La validación basada en código imperativo proporciona una manera sencilla para que una actividad proporcione la validación sobre ella misma y está disponible para aquellas actividades que derivan de <xref:System.Activities.CodeActivity>,  <xref:System.Activities.AsyncCodeActivity> y <xref:System.Activities.NativeActivity>. El código de validación se agrega a la actividad que determina cualquier error de validación o advertencias.  
  
## <a name="using-code-based-validation"></a>Usar validación basada en código

Las actividades que derivan de <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> y <xref:System.Activities.NativeActivity> admiten la validación basada en código. El código de la validación se puede colocar en el reemplazo de <xref:System.Activities.CodeActivity.CacheMetadata%2A>, mientras que los errores o advertencias de validación se pueden agregar al argumento de metadatos. En el siguiente ejemplo, si `Cost` es mayor que `Price`, se agrega un error de validación a los metadatos.  
  
> [!NOTE]
> Observe que `Cost` y `Price` no son argumentos para la actividad, sino propiedades que se establecen en tiempo de diseño. Por eso sus valores se pueden validar en la invalidación de <xref:System.Activities.CodeActivity.CacheMetadata%2A>. El valor de los datos que atraviesan un argumento no se puede validar en tiempo de diseño porque los datos no fluyen hasta el tiempo de ejecución, pero los argumentos de actividad se pueden validar para asegurarse de que están enlazados mediante el atributo `RequiredArgument` y grupos de sobrecargas. Este código de ejemplo examina el atributo `RequiredArgument` para el argumento `Description` y si no está enlazado, se genera un error de validación. Los argumentos necesarios se describen en los [argumentos necesarios y en los grupos de sobrecargas](required-arguments-and-overload-groups.md).  
  
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
  
 De forma predeterminada, se agrega un error de validación a los metadatos cuando se llama a <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A>. Para agregar una advertencia de validación, use la sobrecarga de <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> que toma una clase <xref:System.Activities.Validation.ValidationError> y especifica que <xref:System.Activities.Validation.ValidationError> representa una advertencia al establecer la propiedad <xref:System.Activities.Validation.ValidationError.IsWarning%2A>.  
  
 La validación se produce cuando un flujo de trabajo se modifica en el diseñador de flujo de trabajo y cuando los errores de validación o advertencias se muestran en el diseñador de flujo de trabajo. La validación también se produce en tiempo de ejecución cuando se invoca un flujo de trabajo y si se producen algunos errores de validación; la lógica de validación predeterminada produce <xref:System.Activities.InvalidWorkflowException>. Para obtener más información sobre cómo invocar la validación y obtener acceso a cualquier error o advertencia de validación, consulte [invocar la validación de actividad](invoking-activity-validation.md).  
  
 Cualquier excepción que se produzca desde el método <xref:System.Activities.CodeActivity.CacheMetadata%2A> no se trata como errores de validación. Estas excepciones escaparán de la llamada al método <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> y serán administradas por el autor de la llamada.  
  
 La validación basada en código es útil para validar la actividad que contiene el código, pero no tiene visibilidad en las otras actividades en el flujo de trabajo. La validación de restricciones declarativas proporciona la capacidad de validar las relaciones entre una actividad y otras actividades del flujo de trabajo, y se trata en el tema sobre las [restricciones declarativas](declarative-constraints.md) .
