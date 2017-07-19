---
title: "Validaci&#243;n imperativa basada en c&#243;digo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ae12537c-455e-42b1-82f4-cea4c46c023e
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Validaci&#243;n imperativa basada en c&#243;digo
La validación imperativa basada en código proporciona una manera sencilla para que una actividad proporcione la validación sobre ella misma y está disponible para aquellas actividades que derivan de <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> y <xref:System.Activities.NativeActivity>.El código de validación que determina cualquier error de validación o advertencias se agrega a la actividad.  
  
## Usar validación basada en código  
 Las actividades que derivan de <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> y <xref:System.Activities.NativeActivity> admiten la validación basada en código.El código de validación se puede colocar en el reemplazo de <xref:System.Activities.CodeActivity.CacheMetadata%2A>, mientras que los errores de validación o las advertencias se pueden agregar al argumento de metadatos.En el siguiente ejemplo, tomado del ejemplo [Validación básica](../../../docs/framework/windows-workflow-foundation/samples/basic-validation.md), si `Cost` es mayor que `Price`, se agrega un error de validación a los metadatos.  
  
> [!NOTE]
>  Observe que `Cost` y `Price` no son argumentos para la actividad, sino propiedades que se establecen en tiempo de diseño.Por eso sus valores se pueden validar en la invalidación de <xref:System.Activities.CodeActivity.CacheMetadata%2A>.El valor de los datos que atraviesan un argumento no se puede validar en tiempo de diseño porque los datos no fluyen hasta el tiempo de ejecución, pero los argumentos de actividad se pueden validar para asegurarse de que están enlazados mediante el atributo `RequiredArgument` y grupos de sobrecargas.Este código de ejemplo examina el atributo `RequiredArgument` para el argumento `Description` y si no está enlazado, se genera un error de validación.Los argumentos necesarios se tratan en [Argumentos necesarios y grupos de sobrecarga](../../../docs/framework/windows-workflow-foundation//required-arguments-and-overload-groups.md).  
  
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
  
 De forma predeterminada, se agrega un error de validación a los metadatos cuando se llama a <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A>.Para agregar una advertencia de validación, use la sobrecarga de <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> que toma una clase <xref:System.Activities.Validation.ValidationError> y especifica que <xref:System.Activities.Validation.ValidationError> representa una advertencia al establecer la propiedad <xref:System.Activities.Validation.ValidationError.IsWarning%2A>.  
  
 La validación se produce cuando un flujo de trabajo se modifica en el diseñador de flujo de trabajo y cuando los errores de validación o advertencias se muestran en el diseñador de flujo de trabajo.La validación también se produce en tiempo de ejecución cuando se invoca un flujo de trabajo y si se producen algunos errores de validación; la lógica de validación predeterminada produce <xref:System.Activities.InvalidWorkflowException>.[!INCLUDE[crabout](../../../includes/crabout-md.md)] cómo invocar la validación y tener acceso a las advertencias o errores de validación, vea [Invocar validación de actividad](../../../docs/framework/windows-workflow-foundation//invoking-activity-validation.md).  
  
 Cualquier excepción que se produzca desde el método <xref:System.Activities.CodeActivity.CacheMetadata%2A> no se trata como errores de validación.Estas excepciones escaparán de la llamada al método <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> y serán administradas por el llamador.  
  
 La validación basada en código es útil para validar la actividad que contiene el código, pero no tiene visibilidad en las otras actividades en el flujo de trabajo.La validación de restricciones declarativas proporciona la capacidad de validar las relaciones entre una actividad y otras actividades en el flujo de trabajo. Se trata en el tema [Restricciones declarativas](../../../docs/framework/windows-workflow-foundation//declarative-constraints.md).