---
title: Crear flujos de trabajo, actividades y expresiones mediante código imperativo
description: Una definición de flujo de trabajo de Workflow Foundation es un árbol de objetos de actividad configurados. Use código para crear definiciones de flujo de trabajo, actividades y expresiones.
ms.date: 03/30/2017
ms.assetid: cefc9cfc-2882-4eb9-8c94-7a6da957f2b2
ms.openlocfilehash: d169049c47c154858a2e653b5f286fa6b66ba44d
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063801"
---
# <a name="authoring-workflows-activities-and-expressions-using-imperative-code"></a>Crear flujos de trabajo, actividades y expresiones mediante código imperativo
Una definición de flujo de trabajo es un árbol de objetos de actividad configurados. Este árbol de actividades se puede definir de muchas maneras, incluido XAML editado a mano o el uso del Diseñador de flujo de trabajo para generar XAML. El uso de XAML, sin embargo, no es un requisito. También se pueden crear definiciones de flujo de trabajo mediante programación. Este tema proporciona información general sobre cómo crear definiciones de flujo de trabajo, actividades y expresiones mediante código. Para obtener ejemplos de cómo trabajar con flujos de trabajo de XAML mediante código, vea [serializar flujos de trabajo y actividades a y desde XAML](serializing-workflows-and-activities-to-and-from-xaml.md).  
  
## <a name="creating-workflow-definitions"></a>Crear definiciones de flujo de trabajo  
 Se puede crear una definición de flujo de trabajo creando instancias de un tipo de actividad y configurando las propiedades del objeto de la actividad. En el caso de actividades que no contengan actividades secundarias, puede llevarse a cabo con algunas líneas de código.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#47](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#47)]  
  
> [!NOTE]
> En los ejemplos de este tema se usa <xref:System.Activities.WorkflowInvoker> para ejecutar los flujos de trabajo de ejemplo. Para obtener más información sobre cómo invocar flujos de trabajo, pasar argumentos y las distintas opciones de hospedaje que están disponibles, vea [uso de WorkflowInvoker y WorkflowApplication](using-workflowinvoker-and-workflowapplication.md).  
  
 En este ejemplo se crea un flujo de trabajo que consta de una única actividad <xref:System.Activities.Statements.WriteLine>. Se establece el argumento <xref:System.Activities.Statements.WriteLine> de la actividad <xref:System.Activities.Statements.WriteLine.Text%2A> y se invoca el flujo de trabajo. Si una actividad contiene actividades secundarias, el método de construcción es similar. En el siguiente ejemplo se usa una actividad <xref:System.Activities.Statements.Sequence> que contiene dos actividades <xref:System.Activities.Statements.WriteLine>.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#48](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#48)]  
  
### <a name="using-object-initializers"></a>Usar inicializadores de objeto  
 Los ejemplos de este tema usan la sintaxis de inicialización del objeto. Esta sintaxis puede ser una forma útil de crear definiciones de flujo de trabajo en el código porque proporciona una vista jerárquica de las actividades en el flujo de trabajo y muestra la relación entre las actividades. No hay ningún requisito para usar la sintaxis de inicialización de objeto al crear los flujos de trabajo mediante programación. El ejemplo siguiente es equivalente en su funcionamiento al ejemplo anterior.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#49](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#49)]  
  
 Para obtener más información sobre los inicializadores de objeto, vea [Cómo: inicializar objetos sin llamar a un constructor (Guía de programación de C#)](../../csharp/programming-guide/classes-and-structs/how-to-initialize-objects-by-using-an-object-initializer.md) y [Cómo: declarar un objeto usando un inicializador de objeto](../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md).  
  
### <a name="working-with-variables-literal-values-and-expressions"></a>Trabajar con variables, valores literales y expresiones  
 Al crear una definición de flujo de trabajo mediante código, tenga en cuenta qué código se ejecuta como parte de la creación de la definición de flujo de trabajo y qué código se ejecuta como parte de la ejecución de una instancia de ese flujo de trabajo. Por ejemplo, el siguiente flujo de trabajo está pensado para generar un número aleatorio y escribirlo en la consola.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#50](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#50)]  
  
 Cuando se ejecuta este código de definición de flujo de trabajo, se realiza la llamada a `Random.Next` y el resultado se almacena en la definición de flujo de trabajo como un valor literal. Se pueden invocar muchas instancias de este flujo de trabajo y todas mostrarían el mismo número. Para que la generación de números aleatorios se produzcan durante la ejecución del flujo de trabajo, se debe usar una expresión que se evalúa con caja ejecución del flujo de trabajo. En el ejemplo siguiente, se usa una expresión de Visual Basic con <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#51](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#51)]  
  
 La expresión del ejemplo anterior también se puede implementar mediante <xref:Microsoft.CSharp.Activities.CSharpValue%601> y una expresión de C#.  
  
```csharp  
new Assign<int>  
{  
    To = n,  
    Value = new CSharpValue<int>("new Random().Next(1, 101)")  
}  
```  
  
 Es necesario compilar las expresiones de C# antes de que se invoque el flujo de trabajo que las contiene. Si las expresiones de C# no se compilan, <xref:System.NotSupportedException> se produce una excepción cuando se invoca el flujo de trabajo con un mensaje similar al siguiente: ``Expression Activity type 'CSharpValue`1' requires compilation in order to run.  Please ensure that the workflow has been compiled.`` en la mayoría de los escenarios que implican flujos de trabajo creados en Visual Studio, las expresiones de c# se compilan automáticamente, pero en algunos escenarios, como los flujos de trabajo de código, las expresiones de c# deben compilarse manualmente. Para obtener un ejemplo de cómo compilar expresiones de C#, consulte la sección [uso de expresiones de c# en flujos de trabajo de código](csharp-expressions.md#CodeWorkflows) del tema expresiones de [c#](csharp-expressions.md) .  
  
 <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> representa una expresión en la sintaxis de Visual Basic que se puede usar como valor r en una expresión y <xref:Microsoft.CSharp.Activities.CSharpValue%601> representa una expresión en la sintaxis de C# que se puede usar como valor r en una expresión. Se evalúan estas expresiones cada vez que se ejecuta la actividad que contienen. El resultado de la expresión se asigna a la variable de flujo de trabajo `n`. La actividad siguiente usa estos resultados en el flujo de trabajo. Para tener acceso al valor de la variable de flujo de trabajo `n` en el tiempo de ejecución, se necesita <xref:System.Activities.ActivityContext>. Se puede tener acceso a esto con la siguiente expresión lambda.  
  
> [!NOTE]
> Observe que ambos códigos son ejemplos que usan C# como lenguaje de programación, pero uno emplea <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> y el otro <xref:Microsoft.CSharp.Activities.CSharpValue%601>. <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> y <xref:Microsoft.CSharp.Activities.CSharpValue%601> se pueden usar en los proyectos de Visual Basic y C#. De forma predeterminada, las expresiones creadas en el diseñador de flujo de trabajo coinciden con el lenguaje del proyecto de hospedaje. Al crear flujos de trabajo en código, el lenguaje deseado está a discreción del autor del flujo de trabajo.  
  
 En estos ejemplos, el resultado de la expresión se asigna a la variable de flujo de trabajo `n`. La actividad siguiente usa estos resultados en el flujo de trabajo. Para tener acceso al valor de la variable de flujo de trabajo `n` en el tiempo de ejecución, se necesita <xref:System.Activities.ActivityContext>. Se puede tener acceso a esto con la siguiente expresión lambda.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#52](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#52)]  
  
 Para obtener más información sobre las expresiones lambda, vea [expresiones lambda (referencia de C#)](../../csharp/language-reference/operators/lambda-expressions.md) o [expresiones lambda (Visual Basic)](../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 Las expresiones lambda no son serializables para el formato XAML. Si se intenta serializar un flujo de trabajo con expresiones lambda, se produce <xref:System.Activities.Expressions.LambdaSerializationException> con el mensaje siguiente: “Este flujo de trabajo contiene expresiones lambda especificadas en código. Estas expresiones no se pueden serializar mediante XAML. Para que el flujo de trabajo se pueda serializar mediante XAML, use VisualBasicValue/VisualBasicReference o ExpressionServices.Convert(lambda). Esto convertirá las expresiones lambda en actividades de expresión”. Para que esta expresión sea compatible con XAML, use <xref:System.Activities.Expressions.ExpressionServices> y <xref:System.Activities.Expressions.ExpressionServices.Convert%2A>, tal y como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#53](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#53)]  
  
 También se puede utilizar <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>. Observe que no se necesita ninguna expresión lambda al usar una expresión de Visual Basic.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#54](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#54)]  
  
 En tiempo de ejecución, las expresiones de Visual Basic se compilan en expresiones LINQ. Ambos ejemplos anteriores son serializables en XAML, pero si el XAML serializado está diseñado para que se vea y edite en el diseñador de flujo de trabajo, use <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> para las expresiones. Los flujos de trabajo serializados que usan `ExpressionServices.Convert` se pueden abrir en el diseñador, pero el valor de la expresión estará en blanco. Para obtener más información sobre cómo serializar flujos de trabajo en XAML, vea [serializar flujos de trabajo y actividades a y desde XAML](serializing-workflows-and-activities-to-and-from-xaml.md).  
  
#### <a name="literal-expressions-and-reference-types"></a>Expresiones literales y tipos de referencia  
 Las expresiones literales se representan en flujos de trabajo mediante la actividad <xref:System.Activities.Expressions.Literal%601>. Las siguientes actividades <xref:System.Activities.Statements.WriteLine> tienen una funcionalidad equivalente.  
  
```csharp  
new WriteLine  
{  
    Text = "Hello World."  
},  
new WriteLine  
{  
    Text = new Literal<string>("Hello World.")  
}  
```  
  
 No se puede inicializar una expresión literal con cualquier tipo de referencia excepto <xref:System.String>. En el ejemplo siguiente, la propiedad <xref:System.Activities.Statements.Assign> de una actividad <xref:System.Activities.Statements.Assign.Value%2A> se inicializa con una expresión literal mediante `List<string>`.  
  
```csharp  
new Assign  
{  
    To = new OutArgument<List<string>>(items),  
    Value = new InArgument<List<string>>(new List<string>())  
},  
```  
  
 Cuando el flujo de trabajo que contiene esta actividad se valida, se devuelve el error de validación siguiente: "El literal solo admite tipos de valor y el tipo inmutable System.String. El tipo System.Collections.Generic.List`1[System.String] no se puede usar como literal”. Si se invoca el flujo de trabajo, se produce <xref:System.Activities.InvalidWorkflowException> que contiene el texto del error de validación. Esto es un error de validación porque al crear una expresión literal con un tipo de referencia no se crea una nueva instancia del tipo de referencia para cada instancia del flujo de trabajo. Para solucionarlo, reemplace la expresión literal con una que cree y devuelva una nueva instancia de tipo de referencia.  
  
```csharp  
new Assign  
{  
    To = new OutArgument<List<string>>(items),  
    Value = new InArgument<List<string>>(new VisualBasicValue<List<string>>("New List(Of String)"))  
},  
```  
  
 Para obtener más información sobre las expresiones, vea [expresiones](expressions.md).  
  
#### <a name="invoking-methods-on-objects-using-expressions-and-the-invokemethod-activity"></a>Invocar métodos en objetos mediante expresiones y la actividad InvokeMethod  
 La actividad <xref:System.Activities.Expressions.InvokeMethod%601> se puede usar para invocar métodos estáticos y de instancia de clases de .NET Framework. En un ejemplo anterior de este tema, se generaba un número aleatorio mediante la clase <xref:System.Random>.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#51](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#51)]  
  
 La actividad <xref:System.Activities.Expressions.InvokeMethod%601> podría haberse usado también para llamar al método <xref:System.Random.Next%2A> de la clase <xref:System.Random>.  
  
```csharp  
new InvokeMethod<int>  
{  
    TargetObject = new InArgument<Random>(new VisualBasicValue<Random>("New Random()")),  
    MethodName = "Next",  
    Parameters =
    {  
        new InArgument<int>(1),  
        new InArgument<int>(101)  
    },  
    Result = n  
}  
```  
  
 Debido a que <xref:System.Random.Next%2A> no es un método estático, se proporciona una instancia de la clase <xref:System.Random> para la propiedad de <xref:System.Activities.Expressions.InvokeMethod%601.TargetObject%2A>. En este ejemplo se crea una nueva instancia mediante una expresión de Visual Basic, pero también podría haberse creado previamente y almacenado en una variable de flujo de trabajo. En este ejemplo, sería más fácil usar la actividad <xref:System.Activities.Statements.Assign%601> en lugar de la actividad <xref:System.Activities.Expressions.InvokeMethod%601>. Si la llamada al método invocada en última instancia por las actividades <xref:System.Activities.Statements.Assign%601> o <xref:System.Activities.Expressions.InvokeMethod%601> es larga, <xref:System.Activities.Expressions.InvokeMethod%601> tiene una ventaja porque tiene una propiedad <xref:System.Activities.Expressions.InvokeMethod%601.RunAsynchronously%2A>. Cuando esta propiedad se establece en `true`, el método invocado se ejecutará de forma asincrónica con respecto al flujo de trabajo. Si hay actividades en paralelo, no se bloquearán mientras el método se esté ejecutando de forma asincrónica. Además, si el método que se va a invocar no tiene ningún valor devuelto, <xref:System.Activities.Expressions.InvokeMethod%601> es la manera adecuada de invocar el método.  
  
## <a name="arguments-and-dynamic-activities"></a>Argumentos y actividades dinámicas  
 Una definición de flujo de trabajo se crea en código ensamblando las actividades en un árbol de actividad y configurando propiedades y argumentos. Se pueden enlazar los argumentos existentes, aunque los nuevos no pueden agregarse a las actividades. Esto incluye argumentos de flujo de trabajo pasados a la actividad raíz. En código imperativo, los argumentos de flujo de trabajo se especifican como propiedades en un nuevo tipo CLR. En XAML se declaran usando `x:Class` y `x:Member`. Dado que no se ha creado ningún nuevo tipo de CLR cuando una definición de flujo de trabajo se crea como un árbol de objetos en memoria, no se pueden agregar argumentos. Sin embargo, los argumentos se pueden agregar a <xref:System.Activities.DynamicActivity>. En este ejemplo, se crea un <xref:System.Activities.DynamicActivity%601> que toma dos argumentos enteros y los agrega juntos y devuelve el resultado. <xref:System.Activities.DynamicActivityProperty> se crea para cada argumento y el resultado de la operación se asigna al argumento <xref:System.Activities.Activity%601.Result%2A> de <xref:System.Activities.DynamicActivity%601>.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#55](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#55)]  
  
 Para obtener más información sobre las actividades dinámicas, vea [crear una actividad en tiempo de ejecución](creating-an-activity-at-runtime-with-dynamicactivity.md).  
  
## <a name="compiled-activities"></a>Actividades compiladas  
 Las actividades dinámicas son una manera de definir una actividad que contiene argumentos mediante código, pero las actividades también se pueden crear en código y compilar en tipos. Se pueden crear actividades simples que derivan de <xref:System.Activities.CodeActivity> y actividades asincrónicas que derivan de <xref:System.Activities.AsyncCodeActivity>. Estas actividades pueden tener argumentos, valores devueltos y definir la lógica mediante código imperativo. Para obtener ejemplos de cómo crear estos tipos de actividades, vea [clase base CodeActivity](workflow-activity-authoring-using-the-codeactivity-class.md) y [crear actividades asincrónicas](creating-asynchronous-activities-in-wf.md).  
  
 Las actividades que derivan de <xref:System.Activities.NativeActivity> pueden definir su lógica mediante código imperativo y también pueden contener actividades secundarias que definen la lógica. También tienen acceso completo a las características del runtime como crear marcadores. Para obtener ejemplos de cómo crear una <xref:System.Activities.NativeActivity> actividad basada en, vea [clase base NativeActivity](nativeactivity-base-class.md), [Cómo: crear una actividad](how-to-create-an-activity.md)y el ejemplo de [composición personalizada mediante la actividad nativa](./samples/custom-composite-using-native-activity.md) .  
  
 Las actividades que derivan de <xref:System.Activities.Activity> definen la lógica únicamente con el uso de actividades secundarias. Estas actividades se crean normalmente mediante el diseñador de flujo de trabajo, pero también pueden definirse mediante código. En el siguiente ejemplo, se define una actividad `Square` que deriva de `Activity<int>`. La actividad `Square` tiene un único <xref:System.Activities.InArgument%601> denominado `Value` y define su lógica especificando una actividad <xref:System.Activities.Statements.Sequence> mediante la propiedad <xref:System.Activities.Activity.Implementation%2A>. La actividad <xref:System.Activities.Statements.Sequence> contiene una actividad <xref:System.Activities.Statements.WriteLine> y una actividad <xref:System.Activities.Statements.Assign%601>. Juntas, estas tres actividades implementan la lógica de la actividad `Square`.  
  
```csharp  
class Square : Activity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Value { get; set; }  
  
    public Square()  
    {  
        this.Implementation = () => new Sequence  
        {  
            Activities =  
            {  
                new WriteLine  
                {  
                    Text = new InArgument<string>((env) => "Squaring the value: " + this.Value.Get(env))  
                },  
                new Assign<int>  
                {  
                    To = new OutArgument<int>((env) => this.Result.Get(env)),  
                    Value = new InArgument<int>((env) => this.Value.Get(env) * this.Value.Get(env))  
                }  
            }  
        };  
    }  
}  
```  
  
 En el siguiente ejemplo se invoca una definición de flujo de trabajo formada por una sola actividad `Square` mediante <xref:System.Activities.WorkflowInvoker>.  
  
```csharp  
Dictionary<string, object> inputs = new Dictionary<string, object> {{ "Value", 5}};  
int result = WorkflowInvoker.Invoke(new Square(), inputs);  
Console.WriteLine("Result: {0}", result);  
```  
  
 Cuando se invoca el flujo de trabajo, en la consola se muestra el siguiente resultado:  
  
 **Calculando raíz cuadrada del valor: 5**  
**Resultado: 25**
