---
title: ForEach no genérico
ms.date: 03/30/2017
ms.assetid: 576cd07a-d58d-4536-b514-77bad60bff38
ms.openlocfilehash: b94ad54d248af7f6ad45c11b9860dd415db840f9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43419322"
---
# <a name="non-generic-foreach"></a>ForEach no genérico
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] se incluye en el cuadro de herramientas de un conjunto de actividades de flujo de Control, incluidos <xref:System.Activities.Statements.ForEach%601>, que permite recorrer <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` colecciones.  
  
 <xref:System.Activities.Statements.ForEach%601> requiere su <xref:System.Activities.Statements.ForEach%601.Values%2A> propiedad sea de tipo <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`. Esto impide que los usuarios recorrer en iteración las estructuras de datos que implementan <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` interfaz (por ejemplo, <xref:System.Collections.ArrayList>). La versión no genérica de <xref:System.Activities.Statements.ForEach%601> supera este requisito, a costa de una mayor complejidad del tiempo de ejecución para garantizar la compatibilidad de los tipos de los valores de la colección.  
  
 En este ejemplo se muestra cómo implementar una actividad <xref:System.Activities.Statements.ForEach%601> no genérica y su diseñador. Esta actividad se puede utilizar para recorrer en iteración <xref:System.Collections.ArrayList>.  
  
## <a name="foreach-activity"></a>Actividad ForEach  
 La instrucción `foreach` de C#/VB enumera los elementos de una colección y ejecuta una instrucción incrustada para cada elemento de la colección. Las actividades equivalentes de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] de `foreach` son <xref:System.Activities.Statements.ForEach%601> y <xref:System.Activities.Statements.ParallelForEach%601>. La actividad <xref:System.Activities.Statements.ForEach%601> contiene una lista de valores y un cuerpo. En el tiempo de ejecución, la lista se recorre en iteración y se ejecuta el cuerpo para cada valor de la lista.  
  
 En la mayoría de los casos, la versión genérica de la actividad debe ser la solución preferida, porque abarca la mayoría de los escenarios en los que se puede utilizar y proporciona comprobación de tipos en tiempo de compilación. La versión no genérica se puede utilizar para recorrer en iteración tipos que implementan la interfaz <xref:System.Collections.IEnumerable> no genérica.  
  
## <a name="class-definition"></a>Definición de clase  
 El siguiente ejemplo de código muestra la definición de una actividad `ForEach` no genérica.  
  
```  
[ContentProperty("Body")]  
public class ForEach : NativeActivity  
{  
    [RequiredArgument]  
    [DefaultValue(null)]  
    InArgument<IEnumerable> Values { get; set; }  
  
    [DefaultValue(null)]  
    [DependsOn("Values")]  
    ActivityAction<object> Body { get; set; }   
}  
```  
  
 Cuerpo (opcional)  
 <xref:System.Activities.ActivityAction> de tipo <xref:System.Object>, que se ejecuta para cada elemento en la colección. Cada elemento individual se pasa al cuerpo a través de su propiedad `Argument`.  
  
 Valores (opcional)  
 La colección de elementos que se recorre en iteración. La verificación de que todos los elementos de la colección son de tipos compatibles se realiza en el tiempo de ejecución.  
  
## <a name="example-of-using-foreach"></a>Ejemplo de uso de ForEach  
 El siguiente código muestra cómo utilizar la actividad ForEach en una aplicación.  
  
```  
string[] names = { "bill", "steve", "ray" };  
  
DelegateInArgument<object> iterationVariable = new DelegateInArgument<object>() { Name = "iterationVariable" };  
  
Activity sampleUsage =  
    new ForEach  
    {  
       Values = new InArgument<IEnumerable>(c=> names),  
       Body = new ActivityAction<object>   
       {                          
           Argument = iterationVariable,  
           Handler = new WriteLine  
           {  
               Text = new InArgument<string>(env => string.Format("Hello {0}",                                                               iterationVariable.Get(env)))  
           }  
       }  
   };  
```  
  
|Condición|Mensaje|Gravedad|Tipo de excepción|  
|---------------|-------------|--------------|--------------------|  
|Los valores son `null`|No se proporcionó el valor para un argumento de actividad necesario 'Values'.|Error|<xref:System.InvalidOperationException>|  
  
## <a name="foreach-designer"></a>Diseñador de ForEach  
 El diseñador de actividad del ejemplo es similar en aspecto al diseñador proporcionado para la actividad <xref:System.Activities.Statements.ForEach%601> integrada. El diseñador aparece en el cuadro de herramientas en el **ejemplos**, **actividades no genéricas** categoría. El diseñador se denomina **ForEachWithBodyFactory** en el cuadro de herramientas, porque la actividad expone un <xref:System.Activities.Presentation.IActivityTemplateFactory> en el cuadro de herramientas, que crea la actividad con un objeto configurado adecuadamente <xref:System.Activities.ActivityAction>.  
  
```  
public sealed class ForEachWithBodyFactory : IActivityTemplateFactory  
{  
    public Activity Create(DependencyObject target)  
    {  
        return new Microsoft.Samples.Activities.Statements.ForEach()  
        {  
            Body = new ActivityAction<object>()  
            {  
                Argument = new DelegateInArgument<object>()  
                {  
                    Name = "item"  
                }  
            }  
        };  
    }  
}  
```  
  
#### <a name="to-run-this-sample"></a>Para ejecutar este ejemplo  
  
1.  Establezca el proyecto que desee como el proyecto de inicio de la solución:  
  
    1.  **CodeTestClient** se muestra cómo usar la actividad mediante código.  
  
    2.  **DesignerTestClient** se muestra cómo usar la actividad dentro del diseñador.  
  
2.  Compile y ejecute el proyecto.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericForEach`
