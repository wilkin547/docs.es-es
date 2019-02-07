---
title: Diseño con tipos de referencia que aceptan valores NULL
description: En este tutorial avanzado se ofrece una introducción a los tipos de referencia que aceptan valores NULL. Sabrá expresar la intención de su diseño cuando los valores de referencia puedan ser NULL y hacer que el compilador aplique esas decisiones cuando no puedan ser NULL.
ms.date: 12/03/2018
ms.custom: mvc
ms.openlocfilehash: eec0c54c041db98595202ab982494df6ae3f743c
ms.sourcegitcommit: e39d93d358974b9ed4541cedf4e25c0101015c3c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "55204774"
---
# <a name="tutorial-express-your-design-intent-more-clearly-with-nullable-and-non-nullable-reference-types"></a><span data-ttu-id="89b5a-104">Tutorial: Expresar la intención del diseño con mayor claridad con tipos de referencia que aceptan valores NULL y que no aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="89b5a-104">Tutorial: Express your design intent more clearly with nullable and non-nullable reference types</span></span>

<span data-ttu-id="89b5a-105">C#8 presenta **tipos de referencia que aceptan valores NULL**, qué complementan a los tipos de referencia del mismo modo que los tipos de valor que aceptan valores NULL complementan a los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="89b5a-105">C# 8 introduces **nullable reference types**, which complement reference types the same way nullable value types complement value types.</span></span> <span data-ttu-id="89b5a-106">Declarará una variable para que sea un **tipo de referencia que acepta valores NULL** anexando un elemento `?` al tipo.</span><span class="sxs-lookup"><span data-stu-id="89b5a-106">You declare a variable to be a **nullable reference type** by appending a `?` to the type.</span></span> <span data-ttu-id="89b5a-107">Por ejemplo, `string?` representa un elemento `string` que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="89b5a-107">For example, `string?` represents a nullable `string`.</span></span> <span data-ttu-id="89b5a-108">Puede utilizar estos nuevos tipos para expresar más claramente la intención del diseño: algunas variables *siempre deben tener un valor*, y a otras *les puede faltar un valor*.</span><span class="sxs-lookup"><span data-stu-id="89b5a-108">You can use these new types to more clearly express your design intent: some variables *must always have a value*, others *may be missing a value*.</span></span>

<span data-ttu-id="89b5a-109">En este tutorial aprenderá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89b5a-109">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="89b5a-110">Incorporar los tipos de referencia que aceptan valores NULL y que no aceptan valores NULL en los diseños</span><span class="sxs-lookup"><span data-stu-id="89b5a-110">Incorporate nullable and non-nullable reference types into your designs</span></span>
> * <span data-ttu-id="89b5a-111">Habilitar las comprobaciones de tipos de referencia que aceptan valores NULL en todo el código</span><span class="sxs-lookup"><span data-stu-id="89b5a-111">Enable nullable reference type checks throughout your code.</span></span>
> * <span data-ttu-id="89b5a-112">Escribir código en la parte en la que el compilador aplica esas decisiones de diseño</span><span class="sxs-lookup"><span data-stu-id="89b5a-112">Write code where the compiler enforces those design decisions.</span></span>
> * <span data-ttu-id="89b5a-113">Usar la característica de referencia que acepta valores NULL en sus propios diseños</span><span class="sxs-lookup"><span data-stu-id="89b5a-113">Use the nullable reference feature in your own designs</span></span>

## <a name="prerequisites"></a><span data-ttu-id="89b5a-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="89b5a-114">Prerequisites</span></span>

<span data-ttu-id="89b5a-115">Deberá configurar la máquina para ejecutar .NET Core, incluido el compilador beta de C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="89b5a-115">You’ll need to set up your machine to run .NET Core, including the C# 8.0 beta compiler.</span></span> <span data-ttu-id="89b5a-116">El compilador beta de C# 8 está disponible con [la versión preliminar 1 de Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) o la [versión preliminar 1 de NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span><span class="sxs-lookup"><span data-stu-id="89b5a-116">The C# 8 beta compiler is available with [Visual Studio 2019 preview 1](https://visualstudio.microsoft.com/vs/preview/), or [.NET Core 3.0 preview 1](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="89b5a-117">En este tutorial se da por supuesto que está familiarizado con C# y. NET, incluidos Visual Studio o la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="89b5a-117">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="incorporate-nullable-reference-types-into-your-designs"></a><span data-ttu-id="89b5a-118">Incorporación de los tipos de referencia que aceptan valores NULL en los diseños</span><span class="sxs-lookup"><span data-stu-id="89b5a-118">Incorporate nullable reference types into your designs</span></span>

<span data-ttu-id="89b5a-119">En este tutorial, va a crear una biblioteca que modela la ejecución de una encuesta.</span><span class="sxs-lookup"><span data-stu-id="89b5a-119">In this tutorial, you'll build a library that models running a survey.</span></span> <span data-ttu-id="89b5a-120">El código usa tipos de referencia que aceptan valores NULL y tipos de referencia que no aceptan valores NULL para representar los conceptos del mundo real.</span><span class="sxs-lookup"><span data-stu-id="89b5a-120">The code uses both nullable reference types and non-nullable reference types to represent the real-world concepts.</span></span> <span data-ttu-id="89b5a-121">Las preguntas de la encuesta nunca pueden aceptar valores NULL.</span><span class="sxs-lookup"><span data-stu-id="89b5a-121">The survey questions can never be null.</span></span> <span data-ttu-id="89b5a-122">Un encuestado podría preferir no responder a una pregunta.</span><span class="sxs-lookup"><span data-stu-id="89b5a-122">A respondent might prefer not to answer a question.</span></span> <span data-ttu-id="89b5a-123">En este caso, las respuestas podrían aceptar valores NULL.</span><span class="sxs-lookup"><span data-stu-id="89b5a-123">The responses might be null in this case.</span></span>

<span data-ttu-id="89b5a-124">El código que escriba para este ejemplo expresa dicha intención y el compilador la exige.</span><span class="sxs-lookup"><span data-stu-id="89b5a-124">The code you'll write for this sample expresses that intent, and the compiler enforces that intent.</span></span>

## <a name="create-the-application-and-enable-nullable-reference-types"></a><span data-ttu-id="89b5a-125">Creación de la aplicación y habilitación de los tipos de referencia que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="89b5a-125">Create the application and enable nullable reference types</span></span>

<span data-ttu-id="89b5a-126">Cree una aplicación de consola en Visual Studio o desde la línea de comandos mediante `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="89b5a-126">Create a new console application either in Visual Studio or from the command line using `dotnet new console`.</span></span> <span data-ttu-id="89b5a-127">Asigne a la aplicación el nombre `NullableIntroduction`.</span><span class="sxs-lookup"><span data-stu-id="89b5a-127">Name the application `NullableIntroduction`.</span></span> <span data-ttu-id="89b5a-128">Una vez que haya creado la aplicación, deberá habilitar las características beta de C# 8.</span><span class="sxs-lookup"><span data-stu-id="89b5a-128">Once you've created the application, you'll need to enable C# 8 beta features.</span></span> <span data-ttu-id="89b5a-129">Abra el archivo `csproj` y agregue un elemento `LangVersion` al elemento `PropertyGroup`:</span><span class="sxs-lookup"><span data-stu-id="89b5a-129">Open the `csproj` file, and add a `LangVersion` element to the `PropertyGroup` element:</span></span>

```xml
<LangVersion>8.0</LangVersion>
```

<span data-ttu-id="89b5a-130">También puede usar las propiedades del proyecto de Visual Studio para habilitar C# 8.</span><span class="sxs-lookup"><span data-stu-id="89b5a-130">Alternatively, you can use the Visual Studio project properties to enable C# 8.</span></span> <span data-ttu-id="89b5a-131">En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="89b5a-131">In Solution Explorer, right click on the project node, select **Properties**.</span></span> <span data-ttu-id="89b5a-132">A continuación, seleccione la pestaña **Compilar** y haga clic en **Opciones avanzadas**. En la lista desplegable de la versión de lenguaje, seleccione  **C# 8.0 (beta)**.</span><span class="sxs-lookup"><span data-stu-id="89b5a-132">Then, select the **build** tab, and click **Advanced...**. In the dropdown for language version, select **C# 8.0 (beta)**.</span></span>

<span data-ttu-id="89b5a-133">Debe optar por recibir la característica de **tipos de referencia que aceptan valores NULL**, incluso en proyectos de C# 8.</span><span class="sxs-lookup"><span data-stu-id="89b5a-133">You must opt into the **nullable reference types** feature, even in C# 8 projects.</span></span> <span data-ttu-id="89b5a-134">El motivo es que, una vez que la característica está activada, las declaraciones de variables de referencia existentes se convierten en **tipos de referencia que no aceptan valores NULL**.</span><span class="sxs-lookup"><span data-stu-id="89b5a-134">That's because once the feature is turned on, existing reference variable declarations become **non-nullable reference types**.</span></span> <span data-ttu-id="89b5a-135">Aunque esa decisión lo ayudará a detectar problemas donde el código existente puede no tener comprobaciones de valores NULL adecuadas, es posible que no se refleje con precisión la intención del diseño original.</span><span class="sxs-lookup"><span data-stu-id="89b5a-135">While that decision will help find issues where existing code may not have proper null-checks, it may not accurately reflect your original design intent.</span></span> <span data-ttu-id="89b5a-136">Active la característica con una nueva directiva pragma:</span><span class="sxs-lookup"><span data-stu-id="89b5a-136">You turn on the feature with a new pragma:</span></span>

```csharp
#nullable enable
```

<span data-ttu-id="89b5a-137">Puede agregar la directiva pragma anterior en cualquier lugar de un archivo de origen, y la característica de tipos de referencia que aceptan valores NULL se activa desde ese punto.</span><span class="sxs-lookup"><span data-stu-id="89b5a-137">You can add the preceding pragma anywhere in a source file, and the nullable reference type feature is turned on from that point.</span></span> <span data-ttu-id="89b5a-138">La directiva pragma también admite el argumento `disable` para desactivar la característica.</span><span class="sxs-lookup"><span data-stu-id="89b5a-138">The pragma also supports the `disable` argument to turn off the feature.</span></span>

<span data-ttu-id="89b5a-139">También puede activar los**tipos de referencia que aceptan valores NULL** para todo un proyecto si agrega el elemento siguiente al archivo .csproj, por ejemplo, inmediatamente después del elemento `LangVersion` que habilitó C# 8.0:</span><span class="sxs-lookup"><span data-stu-id="89b5a-139">You can also turn on **nullable reference types** for an entire project by adding the following element to your .csproj file, for example, immediately following the `LangVersion` element that enabled C# 8.0:</span></span>

```xml
<NullableReferenceTypes>true</NullableReferenceTypes>
```

### <a name="design-the-types-for-the-application"></a><span data-ttu-id="89b5a-140">Diseño de los tipos para la aplicación</span><span class="sxs-lookup"><span data-stu-id="89b5a-140">Design the types for the application</span></span>

<span data-ttu-id="89b5a-141">Esta aplicación de encuesta requiere la creación de una serie de clases:</span><span class="sxs-lookup"><span data-stu-id="89b5a-141">This survey application requires creating a number of classes:</span></span>

- <span data-ttu-id="89b5a-142">Una clase que modela la lista de preguntas</span><span class="sxs-lookup"><span data-stu-id="89b5a-142">A class that models the list of questions.</span></span>
- <span data-ttu-id="89b5a-143">Una clase que modela una lista de personas contactadas para la encuesta</span><span class="sxs-lookup"><span data-stu-id="89b5a-143">A class that models a list of people contacted for the survey.</span></span>
- <span data-ttu-id="89b5a-144">Una clase que modela las respuestas de una persona que realizó la encuesta</span><span class="sxs-lookup"><span data-stu-id="89b5a-144">A class that models the answers from a person that took the survey.</span></span>

<span data-ttu-id="89b5a-145">Estos tipos usarán ambas los tipos de referencia que aceptan valores NULL y los que no aceptan valores NULL para expresar qué miembros que son necesarios y cuáles opcionales.</span><span class="sxs-lookup"><span data-stu-id="89b5a-145">These types will make use of both nullable and non-nullable reference types to express which members are required and which members are optional.</span></span> <span data-ttu-id="89b5a-146">Los tipos de referencia que aceptan valores NULL comunican claramente esa intención de diseño:</span><span class="sxs-lookup"><span data-stu-id="89b5a-146">Nullable reference types communicate that design intent clearly:</span></span>

- <span data-ttu-id="89b5a-147">Las preguntas que forman parte de la encuesta nunca pueden ser NULL: no tiene sentido formular una pregunta vacía.</span><span class="sxs-lookup"><span data-stu-id="89b5a-147">The questions that are part of the survey can never be null: It makes no sense to ask an empty question.</span></span>
- <span data-ttu-id="89b5a-148">Los encuestados nunca pueden aceptar valores NULL.</span><span class="sxs-lookup"><span data-stu-id="89b5a-148">The respondents can never be null.</span></span> <span data-ttu-id="89b5a-149">Quiere realizar un seguimiento de las personas contactadas, incluso de los encuestados que han rechazado participar.</span><span class="sxs-lookup"><span data-stu-id="89b5a-149">You'll want to track people you contacted, even respondents that declined to participate.</span></span>
- <span data-ttu-id="89b5a-150">Cualquier respuesta a una pregunta puede tener valores NULL.</span><span class="sxs-lookup"><span data-stu-id="89b5a-150">Any response to a question may be null.</span></span> <span data-ttu-id="89b5a-151">Los encuestados pueden negarse a responder a algunas preguntas o a todas.</span><span class="sxs-lookup"><span data-stu-id="89b5a-151">Respondents can decline to answer some or all questions.</span></span>

<span data-ttu-id="89b5a-152">Si ha programado en C#, puede estar tan acostumbrado a los tipos de referencia que permiten valores NULL que puede haber perdido otras oportunidades para declarar instancias que no aceptan valores NULL:</span><span class="sxs-lookup"><span data-stu-id="89b5a-152">If you've programmed in C#, you may be so accustomed to reference types that allow null values that you may have missed other opportunities to declare non-nullable instances:</span></span>

- <span data-ttu-id="89b5a-153">La colección de preguntas no debe aceptar valores NULL.</span><span class="sxs-lookup"><span data-stu-id="89b5a-153">The collection of questions should be non-nullable.</span></span>
- <span data-ttu-id="89b5a-154">La colección de encuestados debe aceptar valores NULL.</span><span class="sxs-lookup"><span data-stu-id="89b5a-154">The collection of respondents should be non-nullable.</span></span>

<span data-ttu-id="89b5a-155">A medida que escriba el código, verá que un tipo de referencia que no acepta valores NULL, como el predeterminado para las referencias, evita errores comunes que podrían generar excepciones de referencias que no pueden aceptar valores NULL.</span><span class="sxs-lookup"><span data-stu-id="89b5a-155">As you write the code, you'll see that a non-nullable reference type as the default for references avoids common mistakes that could lead to null reference exceptions.</span></span> <span data-ttu-id="89b5a-156">Una lección de este tutorial es que tomó decisiones sobre qué variables podrían aceptar valores NULL o no.</span><span class="sxs-lookup"><span data-stu-id="89b5a-156">One lesson from this tutorial is that you made decisions about which variables could or could not be null.</span></span> <span data-ttu-id="89b5a-157">El lenguaje no proporcionó una sintaxis para expresar esas decisiones.</span><span class="sxs-lookup"><span data-stu-id="89b5a-157">The language didn't provide syntax to express those decisions.</span></span> <span data-ttu-id="89b5a-158">Ahora sí.</span><span class="sxs-lookup"><span data-stu-id="89b5a-158">Now it does.</span></span>

<span data-ttu-id="89b5a-159">La aplicación que compilará realizará los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="89b5a-159">The app you'll build will do the following steps:</span></span>

1. <span data-ttu-id="89b5a-160">Cree una encuesta y agregue preguntas.</span><span class="sxs-lookup"><span data-stu-id="89b5a-160">Create a survey and add questions to it.</span></span>
1. <span data-ttu-id="89b5a-161">Crear un conjunto de encuestados pseudoaleatorios para la encuesta.</span><span class="sxs-lookup"><span data-stu-id="89b5a-161">Create a pseudo-random set of respondents for the survey.</span></span>
1. <span data-ttu-id="89b5a-162">Póngase en contacto con los encuestados hasta que el tamaño de la encuesta completada alcance el número objetivo.</span><span class="sxs-lookup"><span data-stu-id="89b5a-162">Contact respondents until the completed survey size reaches the goal number.</span></span>
1. <span data-ttu-id="89b5a-163">Escriba estadísticas importantes en las respuestas de la encuesta.</span><span class="sxs-lookup"><span data-stu-id="89b5a-163">Write out important statistics on the survey responses.</span></span>

## <a name="build-the-survey-with-nullable-and-non-nullable-types"></a><span data-ttu-id="89b5a-164">Compilación de la encuesta con tipos que aceptan valores NULL y que no aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="89b5a-164">Build the survey with nullable and non-nullable types</span></span>

<span data-ttu-id="89b5a-165">El primer código que escriba crea la encuesta.</span><span class="sxs-lookup"><span data-stu-id="89b5a-165">The first code you'll write creates the survey.</span></span> <span data-ttu-id="89b5a-166">Deberá escribir clases para modelar una pregunta de encuesta y una ejecución de encuesta.</span><span class="sxs-lookup"><span data-stu-id="89b5a-166">You'll write classes to model a survey question and a survey run.</span></span> <span data-ttu-id="89b5a-167">La encuesta tiene tres tipos de preguntas, que se distinguen por el formato de la respuesta: respuestas afirmativas/negativas, respuestas numéricas y respuestas de texto.</span><span class="sxs-lookup"><span data-stu-id="89b5a-167">Your survey has three types of questions, distinguished by the format of the answer: Yes/No answers, number answers, and text answers.</span></span> <span data-ttu-id="89b5a-168">Cree una clase `public` `SurveyQuestion`.</span><span class="sxs-lookup"><span data-stu-id="89b5a-168">Create a `public` `SurveyQuestion` class.</span></span> <span data-ttu-id="89b5a-169">Incluya la directiva pragma `#nullable enable` inmediatamente después de las instrucciones `using`:</span><span class="sxs-lookup"><span data-stu-id="89b5a-169">Include the `#nullable enable` pragma immediately after the `using` statements:</span></span>

```csharp
#nullable enable
namespace NullableIntroduction
{
    public class SurveyQuestion
    {
    }
}
```

<span data-ttu-id="89b5a-170">Si agrega la directiva pragma `#nullable enable`, el compilador interpretará cada declaración de variable de tipos de referencia como un tipo de referencia **que no acepta valores NULL**.</span><span class="sxs-lookup"><span data-stu-id="89b5a-170">Adding the `#nullable enable` pragma means the compiler interprets every reference type variable declaration as a **non-nullable** reference type.</span></span> <span data-ttu-id="89b5a-171">Puede ver la primera advertencia agregando propiedades para el texto de la pregunta y el tipo de pregunta, tal y como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="89b5a-171">You can see your first warning by adding properties for the question text and the type of question, as shown in the following code:</span></span>

```csharp
#nullable enable
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

<span data-ttu-id="89b5a-172">Dado que no ha inicializado `QuestionText`, el compilador emite una advertencia de que aún no se ha inicializado una propiedad que no acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="89b5a-172">Because you haven't initialized `QuestionText`, the compiler issues a warning that a non-nullable property hasn't been initialized.</span></span> <span data-ttu-id="89b5a-173">Su diseño requiere que el texto de la pregunta no acepte valores NULL, por lo que debe agregar un constructor para inicializar ese elemento y el valor `QuestionType` también.</span><span class="sxs-lookup"><span data-stu-id="89b5a-173">Your design requires the question text to be non-null, so you add a constructor to initialize it and the `QuestionType` value as well.</span></span> <span data-ttu-id="89b5a-174">La definición de clase finalizada es similar al código siguiente:</span><span class="sxs-lookup"><span data-stu-id="89b5a-174">The finished class definition looks like the following code:</span></span>

[!code-csharp[DefineQuestion](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyQuestion.cs)]

<span data-ttu-id="89b5a-175">Al agregar el constructor, se quita la advertencia.</span><span class="sxs-lookup"><span data-stu-id="89b5a-175">Adding the constructor removes the warning.</span></span> <span data-ttu-id="89b5a-176">El argumento del constructor también es un tipo de referencia que no acepta valores NULL, por lo que el compilador no emite advertencias.</span><span class="sxs-lookup"><span data-stu-id="89b5a-176">The constructor argument is also a non-nullable reference type, so the compiler doesn't issue any warnings.</span></span>

<span data-ttu-id="89b5a-177">A continuación, cree una clase `public` denominada "`SurveyRun`".</span><span class="sxs-lookup"><span data-stu-id="89b5a-177">Next, create a `public` class named `SurveyRun`.</span></span> <span data-ttu-id="89b5a-178">Incluya la directiva pragma `#nullable enable` después de las instrucciones `using`.</span><span class="sxs-lookup"><span data-stu-id="89b5a-178">Include the `#nullable enable` pragma following the `using` statements.</span></span> <span data-ttu-id="89b5a-179">Esta clase contiene una lista de objetos `SurveyQuestion` y métodos para agregar preguntas a la encuesta, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="89b5a-179">This class contains a list of `SurveyQuestion` objects and methods to add questions to the survey, as shown in the following code:</span></span>

```csharp
using System.Collections.Generic;

#nullable enable
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

<span data-ttu-id="89b5a-180">Al igual que antes, debe inicializar el objeto de lista en un valor distinto a NULL o el compilador emitirá una advertencia.</span><span class="sxs-lookup"><span data-stu-id="89b5a-180">As before, you must initialize the list object to a non-null value or the compiler issues a warning.</span></span> <span data-ttu-id="89b5a-181">No hay ninguna comprobación de valores que aceptan valores NULL en la segunda sobrecarga de `AddQuestion` porque no son necesarias: ha declarado esa variable para que no acepte valores NULL.</span><span class="sxs-lookup"><span data-stu-id="89b5a-181">There are no null checks in the second overload of `AddQuestion` because they aren't needed: You've declared that variable to be non-nullable.</span></span> <span data-ttu-id="89b5a-182">Su valor no puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="89b5a-182">Its value can't be `null`.</span></span>

<span data-ttu-id="89b5a-183">Cambie a `Program.cs` en el editor y reemplace el contenido de `Main` con las siguientes líneas de código:</span><span class="sxs-lookup"><span data-stu-id="89b5a-183">Switch to `Program.cs` in your editor and replace the contents of `Main` with the following lines of code:</span></span>

[!code-csharp[AddQuestions](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#AddQuestions)]

<span data-ttu-id="89b5a-184">Sin la directiva pragma `#nullable enable` en la parte superior del archivo, el compilador no emitirá ninguna advertencia cuando pase `null` como texto del argumento `AddQuestion`.</span><span class="sxs-lookup"><span data-stu-id="89b5a-184">Without the `#nullable enable` pragma at the top of the file, the compiler doesn't issue a warning when you pass `null` as the text for the `AddQuestion` argument.</span></span> <span data-ttu-id="89b5a-185">Para solucionarlo, agregue `#nullable enable` después de la instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="89b5a-185">Fix that by adding `#nullable enable` following the `using` statement.</span></span> <span data-ttu-id="89b5a-186">Pruébelo agregando la siguiente línea a `Main`:</span><span class="sxs-lookup"><span data-stu-id="89b5a-186">Try it by adding the following line to `Main`:</span></span>

```csharp
surveyRun.AddQuestion(QuestionType.Text, default);
```

## <a name="create-respondents-and-get-answers-to-the-survey"></a><span data-ttu-id="89b5a-187">Creación de los encuestados y obtención de respuestas a la encuesta</span><span class="sxs-lookup"><span data-stu-id="89b5a-187">Create respondents and get answers to the survey</span></span>

<span data-ttu-id="89b5a-188">A continuación, escriba el código que genera respuestas a la encuesta.</span><span class="sxs-lookup"><span data-stu-id="89b5a-188">Next, write the code that generates answers to the survey.</span></span> <span data-ttu-id="89b5a-189">Esto implica realizar varias pequeñas tareas:</span><span class="sxs-lookup"><span data-stu-id="89b5a-189">This involves several small tasks:</span></span>

1. <span data-ttu-id="89b5a-190">Crear un método que genere objetos de encuestados.</span><span class="sxs-lookup"><span data-stu-id="89b5a-190">Build a method that generates respondent objects.</span></span> <span data-ttu-id="89b5a-191">Estos representan a las personas a las que se les ha pedido que completen la encuesta.</span><span class="sxs-lookup"><span data-stu-id="89b5a-191">These represent people asked to fill out the survey.</span></span>
1. <span data-ttu-id="89b5a-192">Crear una lógica para simular la realización de preguntas a un encuestado y la recopilación de respuestas o de la ausencia de respuesta de un encuestado.</span><span class="sxs-lookup"><span data-stu-id="89b5a-192">Build logic to simulate asking the questions to a respondent and collecting answers or noting that a respondent didn't answer.</span></span>
1. <span data-ttu-id="89b5a-193">Repetir todo esto hasta que hayan respondido a la encuesta los suficientes encuestados.</span><span class="sxs-lookup"><span data-stu-id="89b5a-193">Repeat until enough respondents have answered the survey.</span></span>

<span data-ttu-id="89b5a-194">Necesitará una clase para representar una respuesta de encuesta, así que agréguela en este momento.</span><span class="sxs-lookup"><span data-stu-id="89b5a-194">You'll need a class to represent a survey response, so add that now.</span></span> <span data-ttu-id="89b5a-195">Habilite la compatibilidad con la aceptación de valores NULL.</span><span class="sxs-lookup"><span data-stu-id="89b5a-195">Enable nullable support.</span></span> <span data-ttu-id="89b5a-196">Agregue una propiedad `Id` y un constructor que la inicialice, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="89b5a-196">Add an `Id` property and a constructor that initializes it, as shown in the following code:</span></span>

```csharp
#nullable enable
namespace NullableIntroduction
{
    public class SurveyResponse
    {
        public int Id { get; }

        public SurveyResponse(int id) => Id = id;
    }
}
```

<span data-ttu-id="89b5a-197">A continuación, agregue un método `static` para crear nuevos participantes mediante la generación de un identificador aleatorio:</span><span class="sxs-lookup"><span data-stu-id="89b5a-197">Next, add a `static` method to create new participants by generating a random ID:</span></span>

[!code-csharp[GenerateRespondents](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#Random)]

<span data-ttu-id="89b5a-198">La responsabilidad principal de esta clase es generar las respuestas para que un participante de las preguntas de la encuesta.</span><span class="sxs-lookup"><span data-stu-id="89b5a-198">The main responsibility of this class is to generate the responses for a participant to the questions in the survey.</span></span> <span data-ttu-id="89b5a-199">Esta responsabilidad implica una serie de pasos:</span><span class="sxs-lookup"><span data-stu-id="89b5a-199">This responsibility has a few steps:</span></span>

1. <span data-ttu-id="89b5a-200">Solicitar la participación en la encuesta.</span><span class="sxs-lookup"><span data-stu-id="89b5a-200">Ask for participation in the survey.</span></span> <span data-ttu-id="89b5a-201">Si la persona no da su consentimiento, devolver una respuesta con valores ausentes (o NULL).</span><span class="sxs-lookup"><span data-stu-id="89b5a-201">If the person doesn't consent, return a missing (or null) response.</span></span>
1. <span data-ttu-id="89b5a-202">Realizar cada pregunta y registrar la respuesta.</span><span class="sxs-lookup"><span data-stu-id="89b5a-202">Ask each question and record the answer.</span></span> <span data-ttu-id="89b5a-203">Las respuestas también pueden tener valores ausentes (o NULL).</span><span class="sxs-lookup"><span data-stu-id="89b5a-203">Each answer may also be missing (or null).</span></span>

<span data-ttu-id="89b5a-204">Agregue el siguiente código a la clase `SurveyResponse`:</span><span class="sxs-lookup"><span data-stu-id="89b5a-204">Add the following code to your `SurveyResponse` class:</span></span>

[!code-csharp[AnswerSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#AnswerSurvey)]

<span data-ttu-id="89b5a-205">El almacenamiento de las respuestas de la encuesta es una cadena `Dictionary<int, string>?`, que indica que puede aceptar valores NULL.</span><span class="sxs-lookup"><span data-stu-id="89b5a-205">The storage for the survey answers is a `Dictionary<int, string>?`, indicating that it may be null.</span></span> <span data-ttu-id="89b5a-206">Está usando la nueva característica de lenguaje para declarar la intención de diseño tanto para el compilador como para cualquiera que lea el código más adelante.</span><span class="sxs-lookup"><span data-stu-id="89b5a-206">You're using the new language feature to declare your design intent, both to the compiler and to anyone reading your code later.</span></span> <span data-ttu-id="89b5a-207">Si alguna vez desreferencia `surveyResponses` sin comprobar el valor NULL en primer lugar, obtendrá una advertencia del compilador.</span><span class="sxs-lookup"><span data-stu-id="89b5a-207">If you ever dereference `surveyResponses` without checking for the null value first, you'll get a compiler warning.</span></span> <span data-ttu-id="89b5a-208">No recibirá una advertencia en el método `AnswerSurvey` porque el compilador puede determinar que la variable `surveyResponses` se estableció en un valor distinto de NULL.</span><span class="sxs-lookup"><span data-stu-id="89b5a-208">You don't get a warning in the `AnswerSurvey` method because the compiler can determine the `surveyResponses` variable was set to a non-null value above.</span></span>

<span data-ttu-id="89b5a-209">A continuación, deberá escribir el método `PerformSurvey` en la clase `SurveyRun`.</span><span class="sxs-lookup"><span data-stu-id="89b5a-209">Next, you need to write the `PerformSurvey` method in the `SurveyRun` class.</span></span> <span data-ttu-id="89b5a-210">Agregue el código siguiente a la clase `SurveyRun`:</span><span class="sxs-lookup"><span data-stu-id="89b5a-210">Add the following code in the `SurveyRun` class:</span></span>

[!code-csharp[PerformSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#PerformSurvey)]

<span data-ttu-id="89b5a-211">De nuevo, la elección de que un elemento `List<SurveyResponse>?` acepte valores NULL indica que la respuesta puede tener valores NULL.</span><span class="sxs-lookup"><span data-stu-id="89b5a-211">Here again, your choice of a nullable `List<SurveyResponse>?` indicates the response may be null.</span></span> <span data-ttu-id="89b5a-212">Esto indica que la encuesta no se ha asignado a los encuestados todavía.</span><span class="sxs-lookup"><span data-stu-id="89b5a-212">That indicates the survey hasn't been given to any respondents yet.</span></span> <span data-ttu-id="89b5a-213">Tenga en cuenta que los encuestados se agregan hasta que hayan dado su consentimiento.</span><span class="sxs-lookup"><span data-stu-id="89b5a-213">Notice that respondents are added until enough have consented.</span></span>

<span data-ttu-id="89b5a-214">El último paso para ejecutar la encuesta es agregar una llamada al realizar la encuesta al final del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="89b5a-214">The last step to run the survey is to add a call to perform the survey at the end of the `Main` method:</span></span>

[!code-csharp[RunSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#RunSurvey)]

## <a name="examine-survey-responses"></a><span data-ttu-id="89b5a-215">Examen de las respuestas de la encuesta</span><span class="sxs-lookup"><span data-stu-id="89b5a-215">Examine survey responses</span></span>

<span data-ttu-id="89b5a-216">El último paso es mostrar los resultados de la encuesta.</span><span class="sxs-lookup"><span data-stu-id="89b5a-216">The last step is to display survey results.</span></span> <span data-ttu-id="89b5a-217">Agregará código a muchas de las clases que ha escrito.</span><span class="sxs-lookup"><span data-stu-id="89b5a-217">You'll add code to many of the classes you've written.</span></span> <span data-ttu-id="89b5a-218">Este código muestra el valor de distinguir entre tipos de referencia que aceptan valores NULL y que no aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="89b5a-218">This code demonstrates the value of distinguishing nullable and non-nullable reference types.</span></span> <span data-ttu-id="89b5a-219">Empiece agregando los siguientes dos miembros con forma de expresión a la clase `SurveyResponse`:</span><span class="sxs-lookup"><span data-stu-id="89b5a-219">Start by adding the following two expression-bodied members to the `SurveyResponse` class:</span></span>

[!code-csharp[ReportResponses](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#SurveyStatus)]

<span data-ttu-id="89b5a-220">Dado que `surveyResponses` es un tipo de referencia que no acepta valores NULL, no es necesario escribir ninguna comprobación antes de desreferenciarla.</span><span class="sxs-lookup"><span data-stu-id="89b5a-220">Because `surveyResponses` is a non-nullable reference type, no checks are necessary before de-referencing it.</span></span> <span data-ttu-id="89b5a-221">El método `Answer` devuelve una cadena que no acepta valores NULL, así que elija la sobrecarga de `GetValueOrDefault` que tome un segundo argumento para el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="89b5a-221">The `Answer` method returns a non-nullable string, so choose the overload of `GetValueOrDefault` that takes a second argument for the default value.</span></span>

<span data-ttu-id="89b5a-222">A continuación, agregue estos tres miembros con forma de expresión a la clase `SurveyRun`:</span><span class="sxs-lookup"><span data-stu-id="89b5a-222">Next, add these three expression-bodied members to the `SurveyRun` class:</span></span>

[!code-csharp[ReportResults](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#RunReport)]

<span data-ttu-id="89b5a-223">El miembro `AllParticipants` debe tener en cuenta que la variable `respondents` podría ser aceptar valores NULL, pero el valor devuelto no puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="89b5a-223">The `AllParticipants` member must take into account that the `respondents` variable might be null, but the return value can't be null.</span></span> <span data-ttu-id="89b5a-224">Si cambia esa expresión quitando `??` y la secuencia vacía de a continuación, el compilador advertirá de que el método podría devolver `null` y su firma de devolución devuelve un tipo que no acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="89b5a-224">If you change that expression by removing the `??` and the empty sequence that follows, the compiler warns you the method might return `null` and its return signature returns a non-nullable type.</span></span>

<span data-ttu-id="89b5a-225">Finalmente, agregue el siguiente bucle a la parte inferior del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="89b5a-225">Finally, add the following loop at the bottom of the `Main` method:</span></span>

[!code-csharp[DisplaySurveyResults](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#WriteAnswers)]

<span data-ttu-id="89b5a-226">No necesita ninguna comprobación `null` en este código porque ha diseñado las interfaces subyacentes para que devuelvan todos los tipos de referencia que no aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="89b5a-226">You don't need any `null` checks in this code because you've designed the underlying interfaces so that they all return non-nullable reference types.</span></span>

## <a name="get-the-code"></a><span data-ttu-id="89b5a-227">Obtención del código</span><span class="sxs-lookup"><span data-stu-id="89b5a-227">Get the code</span></span>

<span data-ttu-id="89b5a-228">Puede obtener el código del tutorial terminado en nuestro repositorio de [ejemplos](https://github.com/dotnet/samples) en la carpeta [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction).</span><span class="sxs-lookup"><span data-stu-id="89b5a-228">You can get the code for the finished tutorial from our [samples](https://github.com/dotnet/samples) repository in the [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction) folder.</span></span>

<span data-ttu-id="89b5a-229">Experimente cambiando las declaraciones de tipos entre tipos de referencia que aceptan valores NULL y que no aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="89b5a-229">Experiment by changing the type declarations between nullable and non-nullable reference types.</span></span> <span data-ttu-id="89b5a-230">Vea cómo así se generan advertencias diferentes para garantizar que no se desreferencia accidentalmente un valor `null`.</span><span class="sxs-lookup"><span data-stu-id="89b5a-230">See how that generates different warnings to ensure you don't accidentally dereference a `null`.</span></span>

## <a name="next-steps"></a><span data-ttu-id="89b5a-231">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="89b5a-231">Next steps</span></span>

<span data-ttu-id="89b5a-232">Obtenga más información leyendo una introducción a los tipos de referencia que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="89b5a-232">Learn more by reading an overview of nullable reference types..</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="89b5a-233">Introducción a los tipos de referencia que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="89b5a-233">An overview of nullable references</span></span>](../nullable-references.md)
