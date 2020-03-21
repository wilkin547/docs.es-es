---
title: Variables y argumentos
ms.date: 03/30/2017
ms.assetid: d03dbe34-5b2e-4f21-8b57-693ee49611b8
ms.openlocfilehash: f975f46a1858d204d12588f7570b7ea5a365e650
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182691"
---
# <a name="variables-and-arguments"></a><span data-ttu-id="0117b-102">Variables y argumentos</span><span class="sxs-lookup"><span data-stu-id="0117b-102">Variables and Arguments</span></span>
<span data-ttu-id="0117b-103">En Windows Workflow Foundation (WF), las variables representan el almacenamiento de datos y argumentos representan el flujo de datos dentro y fuera de una actividad.</span><span class="sxs-lookup"><span data-stu-id="0117b-103">In Windows Workflow Foundation (WF), variables represent the storage of data and arguments represent the flow of data into and out of an activity.</span></span> <span data-ttu-id="0117b-104">Una actividad tiene un conjunto de argumentos y constituyen la firma de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0117b-104">An activity has a set of arguments and they make up the signature of the activity.</span></span> <span data-ttu-id="0117b-105">Además, una actividad puede mantener una lista de variables a las que un desarrollador de software puede agregar o quitar variables durante el diseño de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0117b-105">Additionally, an activity can maintain a list of variables to which a developer can add or remove variables during the design of a workflow.</span></span> <span data-ttu-id="0117b-106">Los argumentos se enlazan mediante una expresión que devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="0117b-106">An argument is bound using an expression that returns a value.</span></span>  
  
## <a name="variables"></a><span data-ttu-id="0117b-107">variables</span><span class="sxs-lookup"><span data-stu-id="0117b-107">Variables</span></span>  
 <span data-ttu-id="0117b-108">Las variables son las ubicaciones de almacenamiento para los datos.</span><span class="sxs-lookup"><span data-stu-id="0117b-108">Variables are storage locations for data.</span></span> <span data-ttu-id="0117b-109">Las variables se declaran como parte de la definición de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0117b-109">Variables are declared as part of the definition of a workflow.</span></span> <span data-ttu-id="0117b-110">Las variables asumen los valores en el tiempo de ejecución y estos valores se almacenan como parte del estado de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0117b-110">Variables take on values at runtime and these values are stored as part of the state of a workflow instance.</span></span> <span data-ttu-id="0117b-111">La definición de variable especifica el tipo de la variable y, opcionalmente, el nombre.</span><span class="sxs-lookup"><span data-stu-id="0117b-111">A variable definition specifies the type of the variable and optionally, the name.</span></span> <span data-ttu-id="0117b-112">El siguiente código muestra cómo declarar una variable, asignar un valor a él mediante una actividad <xref:System.Activities.Statements.Assign%601> y, a continuación, muestra su valor en la consola usando una actividad <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="0117b-112">The following code shows how to declare a variable, assign a value to it using an <xref:System.Activities.Statements.Assign%601> activity, and then display its value to the console using a <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
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
  
 <span data-ttu-id="0117b-113">Como parte de una declaración de variable, se puede especificar de forma opcional una expresión de valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0117b-113">A default value expression can optionally be specified as part of a variable declaration.</span></span> <span data-ttu-id="0117b-114">Las variables también pueden tener modificadores.</span><span class="sxs-lookup"><span data-stu-id="0117b-114">Variables also can have modifiers.</span></span> <span data-ttu-id="0117b-115">Por ejemplo, si la variable es de solo lectura, se aplicará el modificador de la propiedad <xref:System.Activities.VariableModifiers>.</span><span class="sxs-lookup"><span data-stu-id="0117b-115">For example, if a variable is read-only then the read-only <xref:System.Activities.VariableModifiers> modifier can be applied.</span></span> <span data-ttu-id="0117b-116">En el siguiente ejemplo, se crea una variable de solo lectura que tiene un valor predeterminado asignado.</span><span class="sxs-lookup"><span data-stu-id="0117b-116">In the following example, a read-only variable is created that has a default value assigned.</span></span>  
  
```csharp  
// Define a read-only variable with a default value.  
Variable<string> var = new Variable<string>  
{  
    Default = "Hello World.",  
    Modifiers = VariableModifiers.ReadOnly  
};  
```  
  
## <a name="variable-scoping"></a><span data-ttu-id="0117b-117">Ámbito de variable</span><span class="sxs-lookup"><span data-stu-id="0117b-117">Variable Scoping</span></span>  
 <span data-ttu-id="0117b-118">La duración de una variable en el tiempo de ejecución es igual a la duración de la actividad que la declara.</span><span class="sxs-lookup"><span data-stu-id="0117b-118">The lifetime of a variable at runtime is equal to the lifetime of the activity that declares it.</span></span> <span data-ttu-id="0117b-119">Cuando se completa una actividad, sus variables se limpian y ya no se puede hacer referencia a ellas.</span><span class="sxs-lookup"><span data-stu-id="0117b-119">When an activity completes, its variables are cleaned up and can no longer be referenced.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="0117b-120">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0117b-120">Arguments</span></span>  
 <span data-ttu-id="0117b-121">Los autores de actividad usan argumentos para definir la manera en que los datos fluyen hacia dentro de la actividad y fuera de ella.</span><span class="sxs-lookup"><span data-stu-id="0117b-121">Activity authors use arguments to define the way data flows into and out of an activity.</span></span> <span data-ttu-id="0117b-122">Cada argumento tiene una dirección especificada: <xref:System.Activities.ArgumentDirection.In>, <xref:System.Activities.ArgumentDirection.Out> o <xref:System.Activities.ArgumentDirection.InOut>.</span><span class="sxs-lookup"><span data-stu-id="0117b-122">Each argument has a specified direction: <xref:System.Activities.ArgumentDirection.In>, <xref:System.Activities.ArgumentDirection.Out>, or <xref:System.Activities.ArgumentDirection.InOut>.</span></span>  
  
 <span data-ttu-id="0117b-123">El tiempo de ejecución del flujo de trabajo garantiza lo siguiente sobre el control de tiempo del movimiento de los datos dentro y fuera de las actividades:</span><span class="sxs-lookup"><span data-stu-id="0117b-123">The workflow runtime makes the following guarantees about the timing of data movement into and out of activities:</span></span>  
  
1. <span data-ttu-id="0117b-124">Cuando una actividad empieza a ejecutarse, se calculan los valores de todos sus argumentos de entrada y de entrada/salida.</span><span class="sxs-lookup"><span data-stu-id="0117b-124">When an activity starts executing, the values of all of its input and input/output arguments are calculated.</span></span> <span data-ttu-id="0117b-125">Por ejemplo, independientemente de cuándo se llame a <xref:System.Activities.Argument.Get%2A>, el valor devuelto lo calculará el tiempo de ejecución antes de la invocación de `Execute`.</span><span class="sxs-lookup"><span data-stu-id="0117b-125">For example, regardless of when <xref:System.Activities.Argument.Get%2A> is called, the value returned is the one calculated by the runtime prior to its invocation of `Execute`.</span></span>  
  
2. <span data-ttu-id="0117b-126">Cuando se llama a <xref:System.Activities.InOutArgument%601.Set%2A>, el tiempo de ejecución establece el valor inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="0117b-126">When <xref:System.Activities.InOutArgument%601.Set%2A> is called, the runtime sets the value immediately.</span></span>  
  
3. <span data-ttu-id="0117b-127">Los argumentos pueden opcionalmente tener especificado su <xref:System.Activities.Argument.EvaluationOrder%2A>.</span><span class="sxs-lookup"><span data-stu-id="0117b-127">Arguments can optionally have their <xref:System.Activities.Argument.EvaluationOrder%2A> specified.</span></span> <span data-ttu-id="0117b-128"><xref:System.Activities.Argument.EvaluationOrder%2A>es un valor basado en cero que especifica el orden en el que se evalúa el argumento.</span><span class="sxs-lookup"><span data-stu-id="0117b-128"><xref:System.Activities.Argument.EvaluationOrder%2A> is a zero-based value that specifies the order in which the argument is evaluated.</span></span> <span data-ttu-id="0117b-129">De forma predeterminada, el orden de evaluación del argumento no está especificado y es igual al valor de <xref:System.Activities.Argument.UnspecifiedEvaluationOrder>.</span><span class="sxs-lookup"><span data-stu-id="0117b-129">By default, the evaluation order of the argument is unspecified and is equal to the <xref:System.Activities.Argument.UnspecifiedEvaluationOrder> value.</span></span> <span data-ttu-id="0117b-130">Para especificar un orden de evaluación para este argumento, establezca la propiedad <xref:System.Activities.Argument.EvaluationOrder%2A> con un valor mayor o igual que cero.</span><span class="sxs-lookup"><span data-stu-id="0117b-130">Set <xref:System.Activities.Argument.EvaluationOrder%2A> to a value greater or equal to zero to specify an evaluation order for this argument.</span></span> <span data-ttu-id="0117b-131">Windows Workflow Foundation evalúa los argumentos con un orden de evaluación especificado en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="0117b-131">Windows Workflow Foundation evaluates arguments with a specified evaluation order in ascending order.</span></span> <span data-ttu-id="0117b-132">Tenga en cuenta que los argumentos que no tienen orden de evaluación especificada se evalúan antes que los que tienen especificado un orden de evaluación.</span><span class="sxs-lookup"><span data-stu-id="0117b-132">Note that arguments with an unspecified evaluation order are evaluated before those with a specified evaluation order.</span></span>  
  
 <span data-ttu-id="0117b-133">Un autor de actividad puede usar un mecanismo fuertemente tipado para exponer sus argumentos.</span><span class="sxs-lookup"><span data-stu-id="0117b-133">An activity author can use a strongly-typed mechanism for exposing its arguments.</span></span> <span data-ttu-id="0117b-134">Esto se logra declarando propiedades de tipo <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601> y <xref:System.Activities.InOutArgument%601>.</span><span class="sxs-lookup"><span data-stu-id="0117b-134">This is accomplished by declaring properties of type <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601>, and <xref:System.Activities.InOutArgument%601>.</span></span> <span data-ttu-id="0117b-135">De esta forma se permite que un autor de actividad establezca un contrato concreto sobre la entrada y salida de datos de una actividad.</span><span class="sxs-lookup"><span data-stu-id="0117b-135">This allows an activity author to establish a specific contract about the data going into and out of an activity.</span></span>  
  
### <a name="defining-the-arguments-on-an-activity"></a><span data-ttu-id="0117b-136">Definir argumentos en una actividad</span><span class="sxs-lookup"><span data-stu-id="0117b-136">Defining the Arguments on an Activity</span></span>  
 <span data-ttu-id="0117b-137">Los argumentos se pueden definir en una actividad al especificar propiedades de tipo <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601> y <xref:System.Activities.InOutArgument%601>.</span><span class="sxs-lookup"><span data-stu-id="0117b-137">Arguments can be defined on an activity by specifying properties of type <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601>, and <xref:System.Activities.InOutArgument%601>.</span></span> <span data-ttu-id="0117b-138">El siguiente código muestra cómo definir los argumentos para una actividad `Prompt` que mostrará una cadena al usuario y devolverá otra con la respuesta del usuario.</span><span class="sxs-lookup"><span data-stu-id="0117b-138">The following code shows how to define the arguments for a `Prompt` activity that takes in a string to display to the user and returns a string that contains the user's response.</span></span>  
  
```csharp  
public class Prompt : Activity  
{  
    public InArgument<string> Text { get; set; }  
    public OutArgument<string> Response { get; set; }  
    // Rest of activity definition omitted.  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="0117b-139">Las actividades que devuelven un valor único pueden derivar de <xref:System.Activities.Activity%601>, <xref:System.Activities.NativeActivity%601> o <xref:System.Activities.CodeActivity%601>.</span><span class="sxs-lookup"><span data-stu-id="0117b-139">Activities that return a single value can derive from <xref:System.Activities.Activity%601>, <xref:System.Activities.NativeActivity%601>, or <xref:System.Activities.CodeActivity%601>.</span></span> <span data-ttu-id="0117b-140">Estas actividades tienen una clase <xref:System.Activities.OutArgument%601> bien definida denominada <xref:System.Activities.Activity%601.Result%2A> que contiene el valor devuelto de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0117b-140">These activities have a well-defined <xref:System.Activities.OutArgument%601> named <xref:System.Activities.Activity%601.Result%2A> that contains the return value of the activity.</span></span>  
  
### <a name="using-variables-and-arguments-in-workflows"></a><span data-ttu-id="0117b-141">Usar variables y argumentos en flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="0117b-141">Using Variables and Arguments in Workflows</span></span>  
 <span data-ttu-id="0117b-142">El siguiente ejemplo muestra cómo se usan las variables y argumentos en un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0117b-142">The following example shows how variables and arguments are used in a workflow.</span></span> <span data-ttu-id="0117b-143">El flujo de trabajo es una secuencia que declara tres variables: `var1`, `var2` y `var3`.</span><span class="sxs-lookup"><span data-stu-id="0117b-143">The workflow is a sequence that declares three variables: `var1`, `var2`, and `var3`.</span></span> <span data-ttu-id="0117b-144">La primera actividad en el flujo de trabajo es una actividad `Assign` que asigna el valor de la variable `var1` a la variable `var2`.</span><span class="sxs-lookup"><span data-stu-id="0117b-144">The first activity in the workflow is an `Assign` activity that assigns the value of variable `var1` to the variable `var2`.</span></span> <span data-ttu-id="0117b-145">A esto le sigue una actividad `WriteLine` que imprime el valor de la variable `var2`.</span><span class="sxs-lookup"><span data-stu-id="0117b-145">This is followed by a `WriteLine` activity that prints the value of the `var2` variable.</span></span> <span data-ttu-id="0117b-146">A continuación, verá otra actividad `Assign` que asigna el valor de la variable `var2` a la variable `var3`.</span><span class="sxs-lookup"><span data-stu-id="0117b-146">Next is another `Assign` activity that assigns the value of variable `var2` to the variable `var3`.</span></span> <span data-ttu-id="0117b-147">Finalmente, hay otra actividad `WriteLine` que imprime el valor de la variable `var3`.</span><span class="sxs-lookup"><span data-stu-id="0117b-147">Finally there is another `WriteLine` activity that prints the value of the `var3` variable.</span></span> <span data-ttu-id="0117b-148">La primera actividad `Assign` usa `InArgument<string>` y los objetos `OutArgument<string>` que explícitamente representan los enlaces para los argumentos de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0117b-148">The first `Assign` activity uses `InArgument<string>` and `OutArgument<string>` objects that explicitly represent the bindings for the activity's arguments.</span></span> <span data-ttu-id="0117b-149">`InArgument<string>` se usa para <xref:System.Activities.Statements.Assign.Value%2A> porque el valor está fluyendo en la actividad <xref:System.Activities.Statements.Assign%601> a través de su argumento <xref:System.Activities.Statements.Assign.Value%2A> y `OutArgument<string>` se usa para <xref:System.Activities.Statements.Assign.To%2A> porque el valor está fluyendo del argumento <xref:System.Activities.Statements.Assign.To%2A> hacia la variable.</span><span class="sxs-lookup"><span data-stu-id="0117b-149">`InArgument<string>` is used for <xref:System.Activities.Statements.Assign.Value%2A> because the value is flowing into the <xref:System.Activities.Statements.Assign%601> activity through its <xref:System.Activities.Statements.Assign.Value%2A> argument, and `OutArgument<string>` is used for <xref:System.Activities.Statements.Assign.To%2A> because the value is flowing out of the <xref:System.Activities.Statements.Assign.To%2A> argument into the variable.</span></span> <span data-ttu-id="0117b-150">La segunda actividad `Assign` consigue lo mismo gracias a una sintaxis más compacta, pero equivalente, que usa conversiones implícitas.</span><span class="sxs-lookup"><span data-stu-id="0117b-150">The second `Assign` activity accomplishes the same thing with more compact but equivalent syntax that uses implicit casts.</span></span> <span data-ttu-id="0117b-151">Las actividades `WriteLine` también usan la sintaxis compacta.</span><span class="sxs-lookup"><span data-stu-id="0117b-151">The `WriteLine` activities also use the compact syntax.</span></span>  
  
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
  
### <a name="using-variables-and-arguments-in-code-based-activities"></a><span data-ttu-id="0117b-152">Usar variables y argumentos en actividades basadas en código</span><span class="sxs-lookup"><span data-stu-id="0117b-152">Using Variables and Arguments in Code-Based Activities</span></span>  
 <span data-ttu-id="0117b-153">En los ejemplos anteriores se muestra cómo usar argumentos y variables en flujos de trabajo y actividades declarativas.</span><span class="sxs-lookup"><span data-stu-id="0117b-153">The previous examples show how to use arguments and variables in workflows and declarative activities.</span></span> <span data-ttu-id="0117b-154">Las variables y argumentos también se usan en actividades basadas en código.</span><span class="sxs-lookup"><span data-stu-id="0117b-154">Arguments and variables are also used in code-based activities.</span></span> <span data-ttu-id="0117b-155">En lo que se refiere al concepto, el uso es muy similar.</span><span class="sxs-lookup"><span data-stu-id="0117b-155">Conceptually the usage is very similar.</span></span> <span data-ttu-id="0117b-156">Las variables representan el almacenamiento de datos dentro de la actividad, mientras que los argumentos representan el flujo de datos hacia dentro o fuera de la actividad. Ambos están enlazados a otras variables por el autor del flujo de trabajo o argumentos en el flujo de trabajo que representan el lugar hacia donde fluyen los datos, además de su procedencia.</span><span class="sxs-lookup"><span data-stu-id="0117b-156">Variables represent data storage within the activity, and arguments represent the flow of data into or out of the activity, and are bound by the workflow author to other variables or arguments in the workflow that represent where the data flows to or from.</span></span> <span data-ttu-id="0117b-157">Para obtener o establecer el valor de una variable o argumento en una actividad, se debe usar un contexto de actividad que represente el entorno de ejecución actual de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0117b-157">To get or set the value of a variable or argument in an activity, an activity context must be used that represents the current execution environment of the activity.</span></span> <span data-ttu-id="0117b-158">Será el tiempo de ejecución del flujo de trabajo el que lo pase hacia el método <xref:System.Activities.CodeActivity%601.Execute%2A> de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0117b-158">This is passed into the <xref:System.Activities.CodeActivity%601.Execute%2A> method of the activity by the workflow runtime.</span></span> <span data-ttu-id="0117b-159">En este ejemplo, se define una actividad `Add` personalizada que tiene dos argumentos <xref:System.Activities.ArgumentDirection.In>.</span><span class="sxs-lookup"><span data-stu-id="0117b-159">In this example, a custom `Add` activity is defined that has two <xref:System.Activities.ArgumentDirection.In> arguments.</span></span> <span data-ttu-id="0117b-160">Para tener acceso al valor de los argumentos, se usa el método <xref:System.Activities.Argument.Get%2A> y el contexto que pasó el tiempo de ejecución del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0117b-160">To access the value of the arguments, the <xref:System.Activities.Argument.Get%2A> method is used and the context that was passed in by the workflow runtime is used.</span></span>  
  
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
  
 <span data-ttu-id="0117b-161">Para obtener más información sobre cómo trabajar con argumentos, variables y expresiones en el código, vea Creación de flujos de [trabajo, actividades y expresiones mediante código imperativo](authoring-workflows-activities-and-expressions-using-imperative-code.md) y [argumentos necesarios y grupos](required-arguments-and-overload-groups.md)de sobrecarga .</span><span class="sxs-lookup"><span data-stu-id="0117b-161">For more information about working with arguments, variables, and expressions in code, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](authoring-workflows-activities-and-expressions-using-imperative-code.md) and [Required Arguments and Overload Groups](required-arguments-and-overload-groups.md).</span></span>
