---
title: Variables y argumentos
description: En este artículo se describen las variables, que representan el almacenamiento de datos, y los argumentos, que representan el flujo de datos hacia y desde una actividad en Workflow Foundation.
ms.date: 03/30/2017
ms.assetid: d03dbe34-5b2e-4f21-8b57-693ee49611b8
ms.openlocfilehash: 5cce9931e9b0a37d5fafbfb84527ffd543a0a50f
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201954"
---
# <a name="variables-and-arguments"></a>Variables y argumentos
En Windows Workflow Foundation (WF), las variables representan el almacenamiento de datos y los argumentos representan el flujo de datos dentro y fuera de una actividad. Una actividad tiene un conjunto de argumentos y constituyen la firma de la actividad. Además, una actividad puede mantener una lista de variables a las que un desarrollador de software puede agregar o quitar variables durante el diseño de un flujo de trabajo. Los argumentos se enlazan mediante una expresión que devuelve un valor.  
  
## <a name="variables"></a>variables  
 Las variables son las ubicaciones de almacenamiento para los datos. Las variables se declaran como parte de la definición de un flujo de trabajo. Las variables asumen los valores en el tiempo de ejecución y estos valores se almacenan como parte del estado de una instancia de flujo de trabajo. La definición de variable especifica el tipo de la variable y, opcionalmente, el nombre. El siguiente código muestra cómo declarar una variable, asignar un valor a él mediante una actividad <xref:System.Activities.Statements.Assign%601> y, a continuación, muestra su valor en la consola usando una actividad <xref:System.Activities.Statements.WriteLine>.  
  
```csharp  
// Define a variable named "str" of type string.  
Variable<string> var = new Variable<string>  
{  
    Name = "str"  
};  
  
// Declare the variable within a Sequence, assign  
// a value to it, and then display it.  
Activity wf = new Sequence()  
{  
    Variables = { var },  
    Activities =  
    {  
        new Assign<string>  
        {  
            To = var,  
            Value = "Hello World."  
        },  
        new WriteLine  
        {  
            Text = var  
        }  
    }  
};  
  
WorkflowInvoker.Invoke(wf);  
```  
  
 Como parte de una declaración de variable, se puede especificar de forma opcional una expresión de valor predeterminado. Las variables también pueden tener modificadores. Por ejemplo, si la variable es de solo lectura, se aplicará el modificador de la propiedad <xref:System.Activities.VariableModifiers>. En el siguiente ejemplo, se crea una variable de solo lectura que tiene un valor predeterminado asignado.  
  
```csharp  
// Define a read-only variable with a default value.  
Variable<string> var = new Variable<string>  
{  
    Default = "Hello World.",  
    Modifiers = VariableModifiers.ReadOnly  
};  
```  
  
## <a name="variable-scoping"></a>Ámbito de variable  
 La duración de una variable en el tiempo de ejecución es igual a la duración de la actividad que la declara. Cuando se completa una actividad, sus variables se limpian y ya no se puede hacer referencia a ellas.  
  
## <a name="arguments"></a>Argumentos  
 Los autores de actividad usan argumentos para definir la manera en que los datos fluyen hacia dentro de la actividad y fuera de ella. Cada argumento tiene una dirección especificada: <xref:System.Activities.ArgumentDirection.In>, <xref:System.Activities.ArgumentDirection.Out> o <xref:System.Activities.ArgumentDirection.InOut>.  
  
 El tiempo de ejecución del flujo de trabajo garantiza lo siguiente sobre el control de tiempo del movimiento de los datos dentro y fuera de las actividades:  
  
1. Cuando una actividad empieza a ejecutarse, se calculan los valores de todos sus argumentos de entrada y de entrada/salida. Por ejemplo, independientemente de cuándo se llame a <xref:System.Activities.Argument.Get%2A>, el valor devuelto lo calculará el tiempo de ejecución antes de la invocación de `Execute`.  
  
2. Cuando se llama a <xref:System.Activities.InOutArgument%601.Set%2A>, el tiempo de ejecución establece el valor inmediatamente.  
  
3. Los argumentos pueden opcionalmente tener especificado su <xref:System.Activities.Argument.EvaluationOrder%2A>. <xref:System.Activities.Argument.EvaluationOrder%2A>es un valor basado en cero que especifica el orden en el que se evalúa el argumento. De forma predeterminada, el orden de evaluación del argumento no está especificado y es igual al valor de <xref:System.Activities.Argument.UnspecifiedEvaluationOrder>. Para especificar un orden de evaluación para este argumento, establezca la propiedad <xref:System.Activities.Argument.EvaluationOrder%2A> con un valor mayor o igual que cero. Windows Workflow Foundation evalúa los argumentos con un orden de evaluación especificado en orden ascendente. Tenga en cuenta que los argumentos que no tienen orden de evaluación especificada se evalúan antes que los que tienen especificado un orden de evaluación.  
  
 Un autor de actividad puede usar un mecanismo fuertemente tipado para exponer sus argumentos. Esto se logra declarando propiedades de tipo <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601> y <xref:System.Activities.InOutArgument%601>. De esta forma se permite que un autor de actividad establezca un contrato concreto sobre la entrada y salida de datos de una actividad.  
  
### <a name="defining-the-arguments-on-an-activity"></a>Definir argumentos en una actividad  
 Los argumentos se pueden definir en una actividad al especificar propiedades de tipo <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601> y <xref:System.Activities.InOutArgument%601>. El siguiente código muestra cómo definir los argumentos para una actividad `Prompt` que mostrará una cadena al usuario y devolverá otra con la respuesta del usuario.  
  
```csharp  
public class Prompt : Activity  
{  
    public InArgument<string> Text { get; set; }  
    public OutArgument<string> Response { get; set; }  
    // Rest of activity definition omitted.  
}  
```  
  
> [!NOTE]
> Las actividades que devuelven un valor único pueden derivar de <xref:System.Activities.Activity%601>, <xref:System.Activities.NativeActivity%601> o <xref:System.Activities.CodeActivity%601>. Estas actividades tienen una clase <xref:System.Activities.OutArgument%601> bien definida denominada <xref:System.Activities.Activity%601.Result%2A> que contiene el valor devuelto de la actividad.  
  
### <a name="using-variables-and-arguments-in-workflows"></a>Usar variables y argumentos en flujos de trabajo  
 El siguiente ejemplo muestra cómo se usan las variables y argumentos en un flujo de trabajo. El flujo de trabajo es una secuencia que declara tres variables: `var1`, `var2` y `var3`. La primera actividad en el flujo de trabajo es una actividad `Assign` que asigna el valor de la variable `var1` a la variable `var2`. A esto le sigue una actividad `WriteLine` que imprime el valor de la variable `var2`. A continuación, verá otra actividad `Assign` que asigna el valor de la variable `var2` a la variable `var3`. Finalmente, hay otra actividad `WriteLine` que imprime el valor de la variable `var3`. La primera actividad `Assign` usa `InArgument<string>` y los objetos `OutArgument<string>` que explícitamente representan los enlaces para los argumentos de la actividad. `InArgument<string>` se usa para <xref:System.Activities.Statements.Assign.Value%2A> porque el valor está fluyendo en la actividad <xref:System.Activities.Statements.Assign%601> a través de su argumento <xref:System.Activities.Statements.Assign.Value%2A> y `OutArgument<string>` se usa para <xref:System.Activities.Statements.Assign.To%2A> porque el valor está fluyendo del argumento <xref:System.Activities.Statements.Assign.To%2A> hacia la variable. La segunda actividad `Assign` consigue lo mismo gracias a una sintaxis más compacta, pero equivalente, que usa conversiones implícitas. Las actividades `WriteLine` también usan la sintaxis compacta.  
  
```csharp  
// Declare three variables; the first one is given an initial value.  
Variable<string> var1 = new Variable<string>()  
{  
    Default = "one"  
};  
Variable<string> var2 = new Variable<string>();  
Variable<string> var3 = new Variable<string>();  
  
// Define the workflow  
Activity wf = new Sequence  
{  
    Variables = { var1, var2, var3 },  
    Activities =
    {  
        new Assign<string>()  
        {  
            Value = new InArgument<string>(var1),  
            To = new OutArgument<string>(var2)  
        },  
        new WriteLine() { Text = var2 },  
        new Assign<string>()  
        {  
            Value = var2,  
            To = var3  
        },  
        new WriteLine() { Text = var3 }  
    }  
};  
  
WorkflowInvoker.Invoke(wf);  
```  
  
### <a name="using-variables-and-arguments-in-code-based-activities"></a>Usar variables y argumentos en actividades basadas en código  
 En los ejemplos anteriores se muestra cómo usar argumentos y variables en flujos de trabajo y actividades declarativas. Las variables y argumentos también se usan en actividades basadas en código. En lo que se refiere al concepto, el uso es muy similar. Las variables representan el almacenamiento de datos dentro de la actividad, mientras que los argumentos representan el flujo de datos hacia dentro o fuera de la actividad. Ambos están enlazados a otras variables por el autor del flujo de trabajo o argumentos en el flujo de trabajo que representan el lugar hacia donde fluyen los datos, además de su procedencia. Para obtener o establecer el valor de una variable o argumento en una actividad, se debe usar un contexto de actividad que represente el entorno de ejecución actual de la actividad. Será el tiempo de ejecución del flujo de trabajo el que lo pase hacia el método <xref:System.Activities.CodeActivity%601.Execute%2A> de la actividad. En este ejemplo, se define una actividad `Add` personalizada que tiene dos argumentos <xref:System.Activities.ArgumentDirection.In>. Para tener acceso al valor de los argumentos, se usa el método <xref:System.Activities.Argument.Get%2A> y el contexto que pasó el tiempo de ejecución del flujo de trabajo.  
  
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
  
 Para obtener más información sobre cómo trabajar con argumentos, variables y expresiones en el código, vea [crear flujos de trabajo, actividades y expresiones mediante código imperativo](authoring-workflows-activities-and-expressions-using-imperative-code.md) y [argumentos necesarios y grupos de sobrecargas](required-arguments-and-overload-groups.md).
