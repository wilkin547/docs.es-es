---
title: Diseño con tipos de referencia que aceptan valores NULL
description: En este tutorial avanzado se ofrece una introducción a los tipos de referencia que aceptan valores NULL. Sabrá expresar la intención de su diseño cuando los valores de referencia puedan ser NULL y hacer que el compilador aplique esas decisiones cuando no puedan ser NULL.
ms.date: 02/19/2019
ms.technology: csharp-null-safety
ms.custom: mvc
ms.openlocfilehash: b00050c1d151b95e330f94eb9393a4031e47d5a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78240072"
---
# <a name="tutorial-express-your-design-intent-more-clearly-with-nullable-and-non-nullable-reference-types"></a><span data-ttu-id="325a2-104">Tutorial: Expresar la intención del diseño con mayor claridad con tipos de referencia que aceptan valores NULL y que no aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="325a2-104">Tutorial: Express your design intent more clearly with nullable and non-nullable reference types</span></span>

<span data-ttu-id="325a2-105">C# 8.0 presenta [tipos de referencia que admiten un valor NULL](../nullable-references.md), que complementan a los tipos de referencia del mismo modo que los tipos de valor que admiten valores NULL complementan a los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="325a2-105">C# 8.0 introduces [nullable reference types](../nullable-references.md), which complement reference types the same way nullable value types complement value types.</span></span> <span data-ttu-id="325a2-106">Declarará una variable para que sea un **tipo de referencia que acepta valores NULL** anexando un elemento `?` al tipo.</span><span class="sxs-lookup"><span data-stu-id="325a2-106">You declare a variable to be a **nullable reference type** by appending a `?` to the type.</span></span> <span data-ttu-id="325a2-107">Por ejemplo, `string?` representa un elemento `string` que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="325a2-107">For example, `string?` represents a nullable `string`.</span></span> <span data-ttu-id="325a2-108">Puede utilizar estos nuevos tipos para expresar más claramente la intención del diseño: algunas variables *siempre deben tener un valor*, y a otras *les puede faltar un valor*.</span><span class="sxs-lookup"><span data-stu-id="325a2-108">You can use these new types to more clearly express your design intent: some variables *must always have a value*, others *may be missing a value*.</span></span>

<span data-ttu-id="325a2-109">En este tutorial aprenderá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="325a2-109">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="325a2-110">Incorporar los tipos de referencia que aceptan valores NULL y que no aceptan valores NULL en los diseños</span><span class="sxs-lookup"><span data-stu-id="325a2-110">Incorporate nullable and non-nullable reference types into your designs</span></span>
> - <span data-ttu-id="325a2-111">Habilitar las comprobaciones de tipos de referencia que aceptan valores NULL en todo el código</span><span class="sxs-lookup"><span data-stu-id="325a2-111">Enable nullable reference type checks throughout your code.</span></span>
> - <span data-ttu-id="325a2-112">Escribir código en la parte en la que el compilador aplica esas decisiones de diseño</span><span class="sxs-lookup"><span data-stu-id="325a2-112">Write code where the compiler enforces those design decisions.</span></span>
> - <span data-ttu-id="325a2-113">Usar la característica de referencia que acepta valores NULL en sus propios diseños</span><span class="sxs-lookup"><span data-stu-id="325a2-113">Use the nullable reference feature in your own designs</span></span>

## <a name="prerequisites"></a><span data-ttu-id="325a2-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="325a2-114">Prerequisites</span></span>

<span data-ttu-id="325a2-115">Deberá configurar la máquina para ejecutar .NET Core, incluido el compilador de C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="325a2-115">You'll need to set up your machine to run .NET Core, including the C# 8.0 compiler.</span></span> <span data-ttu-id="325a2-116">El compilador de C# 8.0 está disponible con [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o [.NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span><span class="sxs-lookup"><span data-stu-id="325a2-116">The C# 8.0 compiler is available with [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), or [.NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="325a2-117">En este tutorial se da por supuesto que está familiarizado con C# y. NET, incluidos Visual Studio o la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="325a2-117">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="incorporate-nullable-reference-types-into-your-designs"></a><span data-ttu-id="325a2-118">Incorporación de los tipos de referencia que aceptan valores NULL en los diseños</span><span class="sxs-lookup"><span data-stu-id="325a2-118">Incorporate nullable reference types into your designs</span></span>

<span data-ttu-id="325a2-119">En este tutorial, va a crear una biblioteca que modela la ejecución de una encuesta.</span><span class="sxs-lookup"><span data-stu-id="325a2-119">In this tutorial, you'll build a library that models running a survey.</span></span> <span data-ttu-id="325a2-120">El código usa tipos de referencia que aceptan valores NULL y tipos de referencia que no aceptan valores NULL para representar los conceptos del mundo real.</span><span class="sxs-lookup"><span data-stu-id="325a2-120">The code uses both nullable reference types and non-nullable reference types to represent the real-world concepts.</span></span> <span data-ttu-id="325a2-121">Las preguntas de la encuesta nunca pueden aceptar valores NULL.</span><span class="sxs-lookup"><span data-stu-id="325a2-121">The survey questions can never be null.</span></span> <span data-ttu-id="325a2-122">Un encuestado podría preferir no responder a una pregunta.</span><span class="sxs-lookup"><span data-stu-id="325a2-122">A respondent might prefer not to answer a question.</span></span> <span data-ttu-id="325a2-123">En este caso, las respuestas podrían ser `null`.</span><span class="sxs-lookup"><span data-stu-id="325a2-123">The responses might be `null` in this case.</span></span>

<span data-ttu-id="325a2-124">El código que escriba para este ejemplo expresa dicha intención y el compilador la exige.</span><span class="sxs-lookup"><span data-stu-id="325a2-124">The code you'll write for this sample expresses that intent, and the compiler enforces that intent.</span></span>

## <a name="create-the-application-and-enable-nullable-reference-types"></a><span data-ttu-id="325a2-125">Creación de la aplicación y habilitación de los tipos de referencia que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="325a2-125">Create the application and enable nullable reference types</span></span>

<span data-ttu-id="325a2-126">Cree una aplicación de consola en Visual Studio o desde la línea de comandos mediante `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="325a2-126">Create a new console application either in Visual Studio or from the command line using `dotnet new console`.</span></span> <span data-ttu-id="325a2-127">Asigne a la aplicación el nombre `NullableIntroduction`.</span><span class="sxs-lookup"><span data-stu-id="325a2-127">Name the application `NullableIntroduction`.</span></span> <span data-ttu-id="325a2-128">Una vez que se haya creado la aplicación, se deberá especificar que todo el proyecto se compila en un **contexto de anotaciones que admite un valor NULL** habilitado.</span><span class="sxs-lookup"><span data-stu-id="325a2-128">Once you've created the application, you'll need to specify that the entire project compiles in an enabled **nullable annotation context**.</span></span> <span data-ttu-id="325a2-129">Abra el archivo *.csproj* y agregue un elemento `Nullable` al elemento `PropertyGroup`.</span><span class="sxs-lookup"><span data-stu-id="325a2-129">Open the *.csproj* file and add a `Nullable` element to the `PropertyGroup` element.</span></span> <span data-ttu-id="325a2-130">Establezca su valor en `enable`.</span><span class="sxs-lookup"><span data-stu-id="325a2-130">Set its value to `enable`.</span></span> <span data-ttu-id="325a2-131">Debe optar por recibir la característica de **tipos de referencia que admiten un valor NULL**, incluso en proyectos de C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="325a2-131">You must opt into the **nullable reference types** feature, even in C# 8.0 projects.</span></span> <span data-ttu-id="325a2-132">El motivo es que, una vez que la característica está activada, las declaraciones de variables de referencia existentes se convierten en **tipos de referencia que no aceptan valores NULL**.</span><span class="sxs-lookup"><span data-stu-id="325a2-132">That's because once the feature is turned on, existing reference variable declarations become **non-nullable reference types**.</span></span> <span data-ttu-id="325a2-133">Aunque esa decisión lo ayudará a detectar problemas donde el código existente puede no tener comprobaciones de valores NULL adecuadas, es posible que no se refleje con precisión la intención del diseño original:</span><span class="sxs-lookup"><span data-stu-id="325a2-133">While that decision will help find issues where existing code may not have proper null-checks, it may not accurately reflect your original design intent:</span></span>

```xml
<Nullable>enable</Nullable>
```

### <a name="design-the-types-for-the-application"></a><span data-ttu-id="325a2-134">Diseño de los tipos para la aplicación</span><span class="sxs-lookup"><span data-stu-id="325a2-134">Design the types for the application</span></span>

<span data-ttu-id="325a2-135">Esta aplicación de encuesta requiere la creación de una serie de clases:</span><span class="sxs-lookup"><span data-stu-id="325a2-135">This survey application requires creating a number of classes:</span></span>

- <span data-ttu-id="325a2-136">Una clase que modela la lista de preguntas</span><span class="sxs-lookup"><span data-stu-id="325a2-136">A class that models the list of questions.</span></span>
- <span data-ttu-id="325a2-137">Una clase que modela una lista de personas contactadas para la encuesta</span><span class="sxs-lookup"><span data-stu-id="325a2-137">A class that models a list of people contacted for the survey.</span></span>
- <span data-ttu-id="325a2-138">Una clase que modela las respuestas de una persona que realizó la encuesta</span><span class="sxs-lookup"><span data-stu-id="325a2-138">A class that models the answers from a person that took the survey.</span></span>

<span data-ttu-id="325a2-139">Estos tipos usarán ambas los tipos de referencia que aceptan valores NULL y los que no aceptan valores NULL para expresar qué miembros que son necesarios y cuáles opcionales.</span><span class="sxs-lookup"><span data-stu-id="325a2-139">These types will make use of both nullable and non-nullable reference types to express which members are required and which members are optional.</span></span> <span data-ttu-id="325a2-140">Los tipos de referencia que aceptan valores NULL comunican claramente esa intención de diseño:</span><span class="sxs-lookup"><span data-stu-id="325a2-140">Nullable reference types communicate that design intent clearly:</span></span>

- <span data-ttu-id="325a2-141">Las preguntas que forman parte de la encuesta nunca pueden aceptar valores NULL: no tiene sentido formular una pregunta vacía.</span><span class="sxs-lookup"><span data-stu-id="325a2-141">The questions that are part of the survey can never be null: It makes no sense to ask an empty question.</span></span>
- <span data-ttu-id="325a2-142">Los encuestados nunca pueden aceptar valores NULL.</span><span class="sxs-lookup"><span data-stu-id="325a2-142">The respondents can never be null.</span></span> <span data-ttu-id="325a2-143">Quiere realizar un seguimiento de las personas contactadas, incluso de los encuestados que han rechazado participar.</span><span class="sxs-lookup"><span data-stu-id="325a2-143">You'll want to track people you contacted, even respondents that declined to participate.</span></span>
- <span data-ttu-id="325a2-144">Cualquier respuesta a una pregunta puede tener valores NULL.</span><span class="sxs-lookup"><span data-stu-id="325a2-144">Any response to a question may be null.</span></span> <span data-ttu-id="325a2-145">Los encuestados pueden negarse a responder a algunas preguntas o a todas.</span><span class="sxs-lookup"><span data-stu-id="325a2-145">Respondents can decline to answer some or all questions.</span></span>

<span data-ttu-id="325a2-146">Si ha programado en C#, puede estar tan acostumbrado a los tipos de referencia que permiten valores `null` que puede haber perdido otras oportunidades para declarar instancias que no admiten un valor NULL:</span><span class="sxs-lookup"><span data-stu-id="325a2-146">If you've programmed in C#, you may be so accustomed to reference types that allow `null` values that you may have missed other opportunities to declare non-nullable instances:</span></span>

- <span data-ttu-id="325a2-147">La colección de preguntas no debe aceptar valores NULL.</span><span class="sxs-lookup"><span data-stu-id="325a2-147">The collection of questions should be non-nullable.</span></span>
- <span data-ttu-id="325a2-148">La colección de encuestados debe aceptar valores NULL.</span><span class="sxs-lookup"><span data-stu-id="325a2-148">The collection of respondents should be non-nullable.</span></span>

<span data-ttu-id="325a2-149">A medida que escriba el código, verá que un tipo de referencia que no admite un valor NULL, como el predeterminado para las referencias, evita errores comunes que podrían generar <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="325a2-149">As you write the code, you'll see that a non-nullable reference type as the default for references avoids common mistakes that could lead to <xref:System.NullReferenceException>s.</span></span> <span data-ttu-id="325a2-150">Una lección de este tutorial es que tomó decisiones sobre qué variables podrían ser o no `null`.</span><span class="sxs-lookup"><span data-stu-id="325a2-150">One lesson from this tutorial is that you made decisions about which variables could or could not be `null`.</span></span> <span data-ttu-id="325a2-151">El lenguaje no proporcionó una sintaxis para expresar esas decisiones.</span><span class="sxs-lookup"><span data-stu-id="325a2-151">The language didn't provide syntax to express those decisions.</span></span> <span data-ttu-id="325a2-152">Ahora sí.</span><span class="sxs-lookup"><span data-stu-id="325a2-152">Now it does.</span></span>

<span data-ttu-id="325a2-153">La aplicación que compilará realiza los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="325a2-153">The app you'll build does the following steps:</span></span>

1. <span data-ttu-id="325a2-154">Crea una encuesta y agrega preguntas a dicha encuesta.</span><span class="sxs-lookup"><span data-stu-id="325a2-154">Creates a survey and adds questions to it.</span></span>
1. <span data-ttu-id="325a2-155">Crea un conjunto de encuestados pseudoaleatorios para la encuesta.</span><span class="sxs-lookup"><span data-stu-id="325a2-155">Creates a pseudo-random set of respondents for the survey.</span></span>
1. <span data-ttu-id="325a2-156">Se pone en contacto con los encuestados hasta que el tamaño de la encuesta completada alcanza el número objetivo.</span><span class="sxs-lookup"><span data-stu-id="325a2-156">Contacts respondents until the completed survey size reaches the goal number.</span></span>
1. <span data-ttu-id="325a2-157">Escribe estadísticas importantes en las respuestas de la encuesta.</span><span class="sxs-lookup"><span data-stu-id="325a2-157">Writes out important statistics on the survey responses.</span></span>

## <a name="build-the-survey-with-nullable-and-non-nullable-types"></a><span data-ttu-id="325a2-158">Compilación de la encuesta con tipos que aceptan valores NULL y que no aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="325a2-158">Build the survey with nullable and non-nullable types</span></span>

<span data-ttu-id="325a2-159">El primer código que escriba crea la encuesta.</span><span class="sxs-lookup"><span data-stu-id="325a2-159">The first code you'll write creates the survey.</span></span> <span data-ttu-id="325a2-160">Deberá escribir clases para modelar una pregunta de encuesta y una ejecución de encuesta.</span><span class="sxs-lookup"><span data-stu-id="325a2-160">You'll write classes to model a survey question and a survey run.</span></span> <span data-ttu-id="325a2-161">La encuesta tiene tres tipos de preguntas, que se distinguen por el formato de la respuesta: respuestas afirmativas/negativas, respuestas numéricas y respuestas de texto.</span><span class="sxs-lookup"><span data-stu-id="325a2-161">Your survey has three types of questions, distinguished by the format of the answer: Yes/No answers, number answers, and text answers.</span></span> <span data-ttu-id="325a2-162">Cree una clase `public SurveyQuestion`:</span><span class="sxs-lookup"><span data-stu-id="325a2-162">Create a `public SurveyQuestion` class:</span></span>

```csharp
namespace NullableIntroduction
{
    public class SurveyQuestion
    {
    }
}
```

<span data-ttu-id="325a2-163">El compilador interpreta cada declaración de variable de tipo de referencia como un tipo de referencia **que no admite un valor NULL** para el código en un contexto de anotaciones que admite un valor NULL habilitado.</span><span class="sxs-lookup"><span data-stu-id="325a2-163">The compiler interprets every reference type variable declaration as a **non-nullable** reference type for code in an enabled nullable annotation context.</span></span> <span data-ttu-id="325a2-164">Puede ver la primera advertencia agregando propiedades para el texto de la pregunta y el tipo de pregunta, tal y como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="325a2-164">You can see your first warning by adding properties for the question text and the type of question, as shown in the following code:</span></span>

```csharp
namespace NullableIntroduction
{
    public enum QuestionType
    {
        YesNo,
        Number,
        Text
    }

    public class SurveyQuestion
    {
        public string QuestionText { get; }
        public QuestionType TypeOfQuestion { get; }
    }
}
```

<span data-ttu-id="325a2-165">Dado que no ha inicializado `QuestionText`, el compilador emite una advertencia de que aún no se ha inicializado una propiedad que no acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="325a2-165">Because you haven't initialized `QuestionText`, the compiler issues a warning that a non-nullable property hasn't been initialized.</span></span> <span data-ttu-id="325a2-166">Su diseño requiere que el texto de la pregunta no acepte valores NULL, por lo que debe agregar un constructor para inicializar ese elemento y el valor `QuestionType` también.</span><span class="sxs-lookup"><span data-stu-id="325a2-166">Your design requires the question text to be non-null, so you add a constructor to initialize it and the `QuestionType` value as well.</span></span> <span data-ttu-id="325a2-167">La definición de clase finalizada es similar al código siguiente:</span><span class="sxs-lookup"><span data-stu-id="325a2-167">The finished class definition looks like the following code:</span></span>

[!code-csharp[DefineQuestion](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyQuestion.cs)]

<span data-ttu-id="325a2-168">Al agregar el constructor, se quita la advertencia.</span><span class="sxs-lookup"><span data-stu-id="325a2-168">Adding the constructor removes the warning.</span></span> <span data-ttu-id="325a2-169">El argumento del constructor también es un tipo de referencia que no acepta valores NULL, por lo que el compilador no emite advertencias.</span><span class="sxs-lookup"><span data-stu-id="325a2-169">The constructor argument is also a non-nullable reference type, so the compiler doesn't issue any warnings.</span></span>

<span data-ttu-id="325a2-170">A continuación, cree una clase `public` denominada "`SurveyRun`".</span><span class="sxs-lookup"><span data-stu-id="325a2-170">Next, create a `public` class named `SurveyRun`.</span></span> <span data-ttu-id="325a2-171">Esta clase contiene una lista de objetos `SurveyQuestion` y métodos para agregar preguntas a la encuesta, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="325a2-171">This class contains a list of `SurveyQuestion` objects and methods to add questions to the survey, as shown in the following code:</span></span>

```csharp
using System.Collections.Generic;

namespace NullableIntroduction
{
    public class SurveyRun
    {
        private List<SurveyQuestion> surveyQuestions = new List<SurveyQuestion>();

        public void AddQuestion(QuestionType type, string question) =>
            AddQuestion(new SurveyQuestion(type, question));
        public void AddQuestion(SurveyQuestion surveyQuestion) => surveyQuestions.Add(surveyQuestion);
    }
}
```

<span data-ttu-id="325a2-172">Al igual que antes, debe inicializar el objeto de lista en un valor distinto a NULL o el compilador emitirá una advertencia.</span><span class="sxs-lookup"><span data-stu-id="325a2-172">As before, you must initialize the list object to a non-null value or the compiler issues a warning.</span></span> <span data-ttu-id="325a2-173">No hay ninguna comprobación de valores que aceptan valores NULL en la segunda sobrecarga de `AddQuestion` porque no son necesarias: ha declarado esa variable para que no acepte valores NULL.</span><span class="sxs-lookup"><span data-stu-id="325a2-173">There are no null checks in the second overload of `AddQuestion` because they aren't needed: You've declared that variable to be non-nullable.</span></span> <span data-ttu-id="325a2-174">Su valor no puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="325a2-174">Its value can't be `null`.</span></span>

<span data-ttu-id="325a2-175">Cambie a *Program.cs* en el editor y reemplace el contenido de `Main` con las siguientes líneas de código:</span><span class="sxs-lookup"><span data-stu-id="325a2-175">Switch to *Program.cs* in your editor and replace the contents of `Main` with the following lines of code:</span></span>

[!code-csharp[AddQuestions](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/Program.cs#AddQuestions)]

<span data-ttu-id="325a2-176">Dado que todo el proyecto está habilitado para un contexto de anotaciones que admite un valor NULL, al pasar `null` a cualquier método que espera un tipo de referencia que no admite un valor NULL, recibirá una advertencia.</span><span class="sxs-lookup"><span data-stu-id="325a2-176">Because the entire project is in an enabled nullable annotation context, you'll get warnings when you pass `null` to any method expecting a non-nullable reference type.</span></span> <span data-ttu-id="325a2-177">Pruébelo agregando la siguiente línea a `Main`:</span><span class="sxs-lookup"><span data-stu-id="325a2-177">Try it by adding the following line to `Main`:</span></span>

```csharp
surveyRun.AddQuestion(QuestionType.Text, default);
```

## <a name="create-respondents-and-get-answers-to-the-survey"></a><span data-ttu-id="325a2-178">Creación de los encuestados y obtención de respuestas a la encuesta</span><span class="sxs-lookup"><span data-stu-id="325a2-178">Create respondents and get answers to the survey</span></span>

<span data-ttu-id="325a2-179">A continuación, escriba el código que genera respuestas a la encuesta.</span><span class="sxs-lookup"><span data-stu-id="325a2-179">Next, write the code that generates answers to the survey.</span></span> <span data-ttu-id="325a2-180">Este proceso implica realizar varias pequeñas tareas:</span><span class="sxs-lookup"><span data-stu-id="325a2-180">This process involves several small tasks:</span></span>

1. <span data-ttu-id="325a2-181">Crear un método que genere objetos de encuestados.</span><span class="sxs-lookup"><span data-stu-id="325a2-181">Build a method that generates respondent objects.</span></span> <span data-ttu-id="325a2-182">Estos representan a las personas a las que se les ha pedido que completen la encuesta.</span><span class="sxs-lookup"><span data-stu-id="325a2-182">These represent people asked to fill out the survey.</span></span>
1. <span data-ttu-id="325a2-183">Crear una lógica para simular la realización de preguntas a un encuestado y la recopilación de respuestas o de la ausencia de respuesta de un encuestado.</span><span class="sxs-lookup"><span data-stu-id="325a2-183">Build logic to simulate asking the questions to a respondent and collecting answers or noting that a respondent didn't answer.</span></span>
1. <span data-ttu-id="325a2-184">Repetir todo esto hasta que hayan respondido a la encuesta los suficientes encuestados.</span><span class="sxs-lookup"><span data-stu-id="325a2-184">Repeat until enough respondents have answered the survey.</span></span>

<span data-ttu-id="325a2-185">Necesitará una clase para representar una respuesta de encuesta, así que agréguela en este momento.</span><span class="sxs-lookup"><span data-stu-id="325a2-185">You'll need a class to represent a survey response, so add that now.</span></span> <span data-ttu-id="325a2-186">Habilite la compatibilidad con la aceptación de valores NULL.</span><span class="sxs-lookup"><span data-stu-id="325a2-186">Enable nullable support.</span></span> <span data-ttu-id="325a2-187">Agregue una propiedad `Id` y un constructor que la inicialice, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="325a2-187">Add an `Id` property and a constructor that initializes it, as shown in the following code:</span></span>

```csharp
namespace NullableIntroduction
{
    public class SurveyResponse
    {
        public int Id { get; }

        public SurveyResponse(int id) => Id = id;
    }
}
```

<span data-ttu-id="325a2-188">A continuación, agregue un método `static` para crear nuevos participantes mediante la generación de un identificador aleatorio:</span><span class="sxs-lookup"><span data-stu-id="325a2-188">Next, add a `static` method to create new participants by generating a random ID:</span></span>

[!code-csharp[GenerateRespondents](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#Random)]

<span data-ttu-id="325a2-189">La responsabilidad principal de esta clase es generar las respuestas para que un participante de las preguntas de la encuesta.</span><span class="sxs-lookup"><span data-stu-id="325a2-189">The main responsibility of this class is to generate the responses for a participant to the questions in the survey.</span></span> <span data-ttu-id="325a2-190">Esta responsabilidad implica una serie de pasos:</span><span class="sxs-lookup"><span data-stu-id="325a2-190">This responsibility has a few steps:</span></span>

1. <span data-ttu-id="325a2-191">Solicitar la participación en la encuesta.</span><span class="sxs-lookup"><span data-stu-id="325a2-191">Ask for participation in the survey.</span></span> <span data-ttu-id="325a2-192">Si la persona no da su consentimiento, devolver una respuesta con valores ausentes (o NULL).</span><span class="sxs-lookup"><span data-stu-id="325a2-192">If the person doesn't consent, return a missing (or null) response.</span></span>
1. <span data-ttu-id="325a2-193">Realizar cada pregunta y registrar la respuesta.</span><span class="sxs-lookup"><span data-stu-id="325a2-193">Ask each question and record the answer.</span></span> <span data-ttu-id="325a2-194">Las respuestas también pueden tener valores ausentes (o NULL).</span><span class="sxs-lookup"><span data-stu-id="325a2-194">Each answer may also be missing (or null).</span></span>

<span data-ttu-id="325a2-195">Agregue el siguiente código a la clase `SurveyResponse`:</span><span class="sxs-lookup"><span data-stu-id="325a2-195">Add the following code to your `SurveyResponse` class:</span></span>

[!code-csharp[AnswerSurvey](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#AnswerSurvey)]

<span data-ttu-id="325a2-196">El almacenamiento de las respuestas de la encuesta es una cadena `Dictionary<int, string>?`, que indica que puede aceptar valores NULL.</span><span class="sxs-lookup"><span data-stu-id="325a2-196">The storage for the survey answers is a `Dictionary<int, string>?`, indicating that it may be null.</span></span> <span data-ttu-id="325a2-197">Está usando la nueva característica de lenguaje para declarar la intención de diseño tanto para el compilador como para cualquiera que lea el código más adelante.</span><span class="sxs-lookup"><span data-stu-id="325a2-197">You're using the new language feature to declare your design intent, both to the compiler and to anyone reading your code later.</span></span> <span data-ttu-id="325a2-198">Si alguna vez desreferencia `surveyResponses` sin comprobar el valor `null` en primer lugar, obtendrá una advertencia del compilador.</span><span class="sxs-lookup"><span data-stu-id="325a2-198">If you ever dereference `surveyResponses` without checking for the `null` value first, you'll get a compiler warning.</span></span> <span data-ttu-id="325a2-199">No recibirá una advertencia en el método `AnswerSurvey` porque el compilador puede determinar que la variable `surveyResponses` se estableció en un valor distinto de NULL.</span><span class="sxs-lookup"><span data-stu-id="325a2-199">You don't get a warning in the `AnswerSurvey` method because the compiler can determine the `surveyResponses` variable was set to a non-null value above.</span></span>

<span data-ttu-id="325a2-200">Al usar `null` en las respuestas que faltan se resalta un punto clave para trabajar con tipos de referencia que aceptan valores NULL: el objetivo no es quitar todos los valores `null` del programa.</span><span class="sxs-lookup"><span data-stu-id="325a2-200">Using `null` for missing answers highlights a key point for working with nullable reference types: your goal isn't to remove all `null` values from your program.</span></span> <span data-ttu-id="325a2-201">En cambio, de lo que se trata es de garantizar que el código que escribe expresa la intención del diseño.</span><span class="sxs-lookup"><span data-stu-id="325a2-201">Rather, your goal is to ensure that the code you write expresses the intent of your design.</span></span> <span data-ttu-id="325a2-202">Los valores que faltan son un concepto necesario para expresar en el código.</span><span class="sxs-lookup"><span data-stu-id="325a2-202">Missing values are a necessary concept to express in your code.</span></span> <span data-ttu-id="325a2-203">El valor `null` es una forma clara de expresar los valores que faltan.</span><span class="sxs-lookup"><span data-stu-id="325a2-203">The `null` value is a clear way to express those missing values.</span></span> <span data-ttu-id="325a2-204">El intento de quitar todos los valores `null` solo lleva a definir alguna otra forma de expresar esos valores que faltan sin `null`.</span><span class="sxs-lookup"><span data-stu-id="325a2-204">Trying to remove all `null` values only leads to defining some other way to express those missing values without `null`.</span></span>

<span data-ttu-id="325a2-205">A continuación, deberá escribir el método `PerformSurvey` en la clase `SurveyRun`.</span><span class="sxs-lookup"><span data-stu-id="325a2-205">Next, you need to write the `PerformSurvey` method in the `SurveyRun` class.</span></span> <span data-ttu-id="325a2-206">Agregue el código siguiente a la clase `SurveyRun`:</span><span class="sxs-lookup"><span data-stu-id="325a2-206">Add the following code in the `SurveyRun` class:</span></span>

[!code-csharp[PerformSurvey](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#PerformSurvey)]

<span data-ttu-id="325a2-207">De nuevo, la elección de que un elemento `List<SurveyResponse>?` acepte valores NULL indica que la respuesta puede tener valores NULL.</span><span class="sxs-lookup"><span data-stu-id="325a2-207">Here again, your choice of a nullable `List<SurveyResponse>?` indicates the response may be null.</span></span> <span data-ttu-id="325a2-208">Esto indica que la encuesta no se ha asignado a los encuestados todavía.</span><span class="sxs-lookup"><span data-stu-id="325a2-208">That indicates the survey hasn't been given to any respondents yet.</span></span> <span data-ttu-id="325a2-209">Tenga en cuenta que los encuestados se agregan hasta que hayan dado su consentimiento.</span><span class="sxs-lookup"><span data-stu-id="325a2-209">Notice that respondents are added until enough have consented.</span></span>

<span data-ttu-id="325a2-210">El último paso para ejecutar la encuesta es agregar una llamada al realizar la encuesta al final del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="325a2-210">The last step to run the survey is to add a call to perform the survey at the end of the `Main` method:</span></span>

[!code-csharp[RunSurvey](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/Program.cs#RunSurvey)]

## <a name="examine-survey-responses"></a><span data-ttu-id="325a2-211">Examen de las respuestas de la encuesta</span><span class="sxs-lookup"><span data-stu-id="325a2-211">Examine survey responses</span></span>

<span data-ttu-id="325a2-212">El último paso es mostrar los resultados de la encuesta.</span><span class="sxs-lookup"><span data-stu-id="325a2-212">The last step is to display survey results.</span></span> <span data-ttu-id="325a2-213">Agregará código a muchas de las clases que ha escrito.</span><span class="sxs-lookup"><span data-stu-id="325a2-213">You'll add code to many of the classes you've written.</span></span> <span data-ttu-id="325a2-214">Este código muestra el valor de distinguir entre tipos de referencia que aceptan valores NULL y que no aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="325a2-214">This code demonstrates the value of distinguishing nullable and non-nullable reference types.</span></span> <span data-ttu-id="325a2-215">Empiece agregando los siguientes dos miembros con forma de expresión a la clase `SurveyResponse`:</span><span class="sxs-lookup"><span data-stu-id="325a2-215">Start by adding the following two expression-bodied members to the `SurveyResponse` class:</span></span>

[!code-csharp[ReportResponses](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#SurveyStatus)]

<span data-ttu-id="325a2-216">Dado que `surveyResponses` es un tipo de referencia que admite un valor NULL, las comprobaciones de valores NULL son necesarias antes de desreferenciarlo.</span><span class="sxs-lookup"><span data-stu-id="325a2-216">Because `surveyResponses` is a nullable reference type, null checks are necessary before de-referencing it.</span></span> <span data-ttu-id="325a2-217">El método `Answer` devuelve una cadena que no admite un valor NULL, por lo que tenemos que cubrir el caso de que falte una respuesta mediante el operador de fusión de NULL.</span><span class="sxs-lookup"><span data-stu-id="325a2-217">The `Answer` method returns a non-nullable string, so we have to cover the case of a missing answer by using the null-coalescing operator.</span></span>

<span data-ttu-id="325a2-218">A continuación, agregue estos tres miembros con forma de expresión a la clase `SurveyRun`:</span><span class="sxs-lookup"><span data-stu-id="325a2-218">Next, add these three expression-bodied members to the `SurveyRun` class:</span></span>

[!code-csharp[ReportResults](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#RunReport)]

<span data-ttu-id="325a2-219">El miembro `AllParticipants` debe tener en cuenta que la variable `respondents` podría ser aceptar valores NULL, pero el valor devuelto no puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="325a2-219">The `AllParticipants` member must take into account that the `respondents` variable might be null, but the return value can't be null.</span></span> <span data-ttu-id="325a2-220">Si cambia esa expresión quitando `??` y la secuencia vacía de a continuación, el compilador advertirá de que el método podría devolver `null` y su firma de devolución devuelve un tipo que no acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="325a2-220">If you change that expression by removing the `??` and the empty sequence that follows, the compiler warns you the method might return `null` and its return signature returns a non-nullable type.</span></span>

<span data-ttu-id="325a2-221">Finalmente, agregue el siguiente bucle a la parte inferior del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="325a2-221">Finally, add the following loop at the bottom of the `Main` method:</span></span>

[!code-csharp[DisplaySurveyResults](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/Program.cs#WriteAnswers)]

<span data-ttu-id="325a2-222">No necesita ninguna comprobación `null` en este código porque ha diseñado las interfaces subyacentes para que devuelvan todos los tipos de referencia que no aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="325a2-222">You don't need any `null` checks in this code because you've designed the underlying interfaces so that they all return non-nullable reference types.</span></span>

## <a name="get-the-code"></a><span data-ttu-id="325a2-223">Obtención del código</span><span class="sxs-lookup"><span data-stu-id="325a2-223">Get the code</span></span>

<span data-ttu-id="325a2-224">Puede obtener el código del tutorial terminado en nuestro repositorio de [ejemplos](https://github.com/dotnet/samples) en la carpeta [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction).</span><span class="sxs-lookup"><span data-stu-id="325a2-224">You can get the code for the finished tutorial from our [samples](https://github.com/dotnet/samples) repository in the [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction) folder.</span></span>

<span data-ttu-id="325a2-225">Experimente cambiando las declaraciones de tipos entre tipos de referencia que aceptan valores NULL y que no aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="325a2-225">Experiment by changing the type declarations between nullable and non-nullable reference types.</span></span> <span data-ttu-id="325a2-226">Vea cómo así se generan advertencias diferentes para garantizar que no se desreferencia accidentalmente un valor `null`.</span><span class="sxs-lookup"><span data-stu-id="325a2-226">See how that generates different warnings to ensure you don't accidentally dereference a `null`.</span></span>

## <a name="next-steps"></a><span data-ttu-id="325a2-227">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="325a2-227">Next steps</span></span>

<span data-ttu-id="325a2-228">Más información sobre cómo migrar una aplicación existente para usar tipos de referencia que aceptan valores NULL:</span><span class="sxs-lookup"><span data-stu-id="325a2-228">Learn more by migrating an existing application to use nullable reference types:</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="325a2-229">Actualización de aplicaciones para usar tipos de referencia que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="325a2-229">Upgrade an application to use nullable reference types</span></span>](upgrade-to-nullable-references.md)
