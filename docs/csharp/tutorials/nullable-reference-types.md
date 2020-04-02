---
title: Diseño con tipos de referencia que aceptan valores NULL
description: En este tutorial avanzado se ofrece una introducción a los tipos de referencia que aceptan valores NULL. Sabrá expresar la intención de su diseño cuando los valores de referencia puedan ser NULL y hacer que el compilador aplique esas decisiones cuando no puedan ser NULL.
ms.date: 02/19/2019
ms.technology: csharp-null-safety
ms.custom: mvc
ms.openlocfilehash: 54cf9d812999cae837483b48cdedd89d9dc40fc9
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249134"
---
# <a name="tutorial-express-your-design-intent-more-clearly-with-nullable-and-non-nullable-reference-types"></a>Tutorial: Expresar la intención del diseño con mayor claridad con tipos de referencia que aceptan valores NULL y que no aceptan valores NULL

C# 8.0 presenta [tipos de referencia que admiten un valor NULL](../nullable-references.md), que complementan a los tipos de referencia del mismo modo que los tipos de valor que admiten valores NULL complementan a los tipos de valor. Declarará una variable para que sea un **tipo de referencia que acepta valores NULL** anexando un elemento `?` al tipo. Por ejemplo, `string?` representa un elemento `string` que acepta valores NULL. Puede utilizar estos nuevos tipos para expresar más claramente la intención del diseño: algunas variables *siempre deben tener un valor*, y a otras *les puede faltar un valor*.

En este tutorial aprenderá lo siguiente:

> [!div class="checklist"]
>
> - Incorporar los tipos de referencia que aceptan valores NULL y que no aceptan valores NULL en los diseños
> - Habilitar las comprobaciones de tipos de referencia que aceptan valores NULL en todo el código
> - Escribir código en la parte en la que el compilador aplica esas decisiones de diseño
> - Usar la característica de referencia que acepta valores NULL en sus propios diseños

## <a name="prerequisites"></a>Requisitos previos

Deberá configurar la máquina para ejecutar .NET Core, incluido el compilador de C# 8.0. El compilador de C# 8.0 está disponible con [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o [.NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0).

En este tutorial se da por supuesto que está familiarizado con C# y. NET, incluidos Visual Studio o la CLI de .NET Core.

## <a name="incorporate-nullable-reference-types-into-your-designs"></a>Incorporación de los tipos de referencia que aceptan valores NULL en los diseños

En este tutorial, va a crear una biblioteca que modela la ejecución de una encuesta. El código usa tipos de referencia que aceptan valores NULL y tipos de referencia que no aceptan valores NULL para representar los conceptos del mundo real. Las preguntas de la encuesta nunca pueden aceptar valores NULL. Un encuestado podría preferir no responder a una pregunta. En este caso, las respuestas podrían ser `null`.

El código que escriba para este ejemplo expresa dicha intención y el compilador la exige.

## <a name="create-the-application-and-enable-nullable-reference-types"></a>Creación de la aplicación y habilitación de los tipos de referencia que aceptan valores NULL

Cree una aplicación de consola en Visual Studio o desde la línea de comandos mediante `dotnet new console`. Asigne a la aplicación el nombre `NullableIntroduction`. Una vez que se haya creado la aplicación, se deberá especificar que todo el proyecto se compila en un **contexto de anotaciones que admite un valor NULL** habilitado. Abra el archivo *.csproj* y agregue un elemento `Nullable` al elemento `PropertyGroup`. Establezca su valor en `enable`. Debe optar por recibir la característica de **tipos de referencia que admiten un valor NULL**, incluso en proyectos de C# 8.0. El motivo es que, una vez que la característica está activada, las declaraciones de variables de referencia existentes se convierten en **tipos de referencia que no aceptan valores NULL**. Aunque esa decisión lo ayudará a detectar problemas donde el código existente puede no tener comprobaciones de valores NULL adecuadas, es posible que no se refleje con precisión la intención del diseño original:

```xml
<Nullable>enable</Nullable>
```

### <a name="design-the-types-for-the-application"></a>Diseño de los tipos para la aplicación

Esta aplicación de encuesta requiere la creación de una serie de clases:

- Una clase que modela la lista de preguntas
- Una clase que modela una lista de personas contactadas para la encuesta
- Una clase que modela las respuestas de una persona que realizó la encuesta

Estos tipos usarán ambas los tipos de referencia que aceptan valores NULL y los que no aceptan valores NULL para expresar qué miembros que son necesarios y cuáles opcionales. Los tipos de referencia que aceptan valores NULL comunican claramente esa intención de diseño:

- Las preguntas que forman parte de la encuesta nunca pueden ser NULL: no tiene sentido formular una pregunta vacía.
- Los encuestados nunca pueden aceptar valores NULL. Quiere realizar un seguimiento de las personas contactadas, incluso de los encuestados que han rechazado participar.
- Cualquier respuesta a una pregunta puede tener valores NULL. Los encuestados pueden negarse a responder a algunas preguntas o a todas.

Si ha programado en C#, puede estar tan acostumbrado a los tipos de referencia que permiten valores `null` que puede haber perdido otras oportunidades para declarar instancias que no admiten un valor NULL:

- La colección de preguntas no debe aceptar valores NULL.
- La colección de encuestados debe aceptar valores NULL.

A medida que escriba el código, verá que un tipo de referencia que no admite un valor NULL, como el predeterminado para las referencias, evita errores comunes que podrían generar <xref:System.NullReferenceException>. Una lección de este tutorial es que tomó decisiones sobre qué variables podrían ser o no `null`. El lenguaje no proporcionó una sintaxis para expresar esas decisiones. Ahora sí.

La aplicación que compilará realiza los pasos siguientes:

1. Crea una encuesta y agrega preguntas a dicha encuesta.
1. Crea un conjunto de encuestados pseudoaleatorios para la encuesta.
1. Se pone en contacto con los encuestados hasta que el tamaño de la encuesta completada alcanza el número objetivo.
1. Escribe estadísticas importantes en las respuestas de la encuesta.

## <a name="build-the-survey-with-nullable-and-non-nullable-reference-types"></a>Compilación de la encuesta con tipos de referencia que aceptan y no aceptan valores NULL

El primer código que escriba crea la encuesta. Deberá escribir clases para modelar una pregunta de encuesta y una ejecución de encuesta. La encuesta tiene tres tipos de preguntas, que se distinguen por el formato de la respuesta: respuestas afirmativas/negativas, respuestas numéricas y respuestas de texto. Cree una clase `public SurveyQuestion`:

```csharp
namespace NullableIntroduction
{
    public class SurveyQuestion
    {
    }
}
```

El compilador interpreta cada declaración de variable de tipo de referencia como un tipo de referencia **que no admite un valor NULL** para el código en un contexto de anotaciones que admite un valor NULL habilitado. Puede ver la primera advertencia agregando propiedades para el texto de la pregunta y el tipo de pregunta, tal y como se muestra en el código siguiente:

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

Dado que no ha inicializado `QuestionText`, el compilador emite una advertencia de que aún no se ha inicializado una propiedad que no acepta valores NULL. Su diseño requiere que el texto de la pregunta no acepte valores NULL, por lo que debe agregar un constructor para inicializar ese elemento y el valor `QuestionType` también. La definición de clase finalizada es similar al código siguiente:

[!code-csharp[DefineQuestion](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyQuestion.cs)]

Al agregar el constructor, se quita la advertencia. El argumento del constructor también es un tipo de referencia que no acepta valores NULL, por lo que el compilador no emite advertencias.

A continuación, cree una clase `public` denominada "`SurveyRun`". Esta clase contiene una lista de objetos `SurveyQuestion` y métodos para agregar preguntas a la encuesta, tal como se muestra en el código siguiente:

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

Al igual que antes, debe inicializar el objeto de lista en un valor distinto a NULL o el compilador emitirá una advertencia. No hay ninguna comprobación de valores que aceptan valores NULL en la segunda sobrecarga de `AddQuestion` porque no son necesarias: ha declarado esa variable para que no acepte valores NULL. Su valor no puede ser `null`.

Cambie a *Program.cs* en el editor y reemplace el contenido de `Main` con las siguientes líneas de código:

[!code-csharp[AddQuestions](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/Program.cs#AddQuestions)]

Dado que todo el proyecto está habilitado para un contexto de anotaciones que admite un valor NULL, al pasar `null` a cualquier método que espera un tipo de referencia que no admite un valor NULL, recibirá una advertencia. Pruébelo agregando la siguiente línea a `Main`:

```csharp
surveyRun.AddQuestion(QuestionType.Text, default);
```

## <a name="create-respondents-and-get-answers-to-the-survey"></a>Creación de los encuestados y obtención de respuestas a la encuesta

A continuación, escriba el código que genera respuestas a la encuesta. Este proceso implica realizar varias pequeñas tareas:

1. Crear un método que genere objetos de encuestados. Estos representan a las personas a las que se les ha pedido que completen la encuesta.
1. Crear una lógica para simular la realización de preguntas a un encuestado y la recopilación de respuestas o de la ausencia de respuesta de un encuestado.
1. Repetir todo esto hasta que hayan respondido a la encuesta los suficientes encuestados.

Necesitará una clase para representar una respuesta de encuesta, así que agréguela en este momento. Habilite la compatibilidad con la aceptación de valores NULL. Agregue una propiedad `Id` y un constructor que la inicialice, tal como se muestra en el código siguiente:

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

A continuación, agregue un método `static` para crear nuevos participantes mediante la generación de un identificador aleatorio:

[!code-csharp[GenerateRespondents](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#Random)]

La responsabilidad principal de esta clase es generar las respuestas para que un participante de las preguntas de la encuesta. Esta responsabilidad implica una serie de pasos:

1. Solicitar la participación en la encuesta. Si la persona no da su consentimiento, devolver una respuesta con valores ausentes (o NULL).
1. Realizar cada pregunta y registrar la respuesta. Las respuestas también pueden tener valores ausentes (o NULL).

Agregue el siguiente código a la clase `SurveyResponse`:

[!code-csharp[AnswerSurvey](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#AnswerSurvey)]

El almacenamiento de las respuestas de la encuesta es una cadena `Dictionary<int, string>?`, que indica que puede aceptar valores NULL. Está usando la nueva característica de lenguaje para declarar la intención de diseño tanto para el compilador como para cualquiera que lea el código más adelante. Si alguna vez desreferencia `surveyResponses` sin comprobar el valor `null` en primer lugar, obtendrá una advertencia del compilador. No recibirá una advertencia en el método `AnswerSurvey` porque el compilador puede determinar que la variable `surveyResponses` se estableció en un valor distinto de NULL.

Al usar `null` en las respuestas que faltan se resalta un punto clave para trabajar con tipos de referencia que aceptan valores NULL: el objetivo no es quitar todos los valores `null` del programa. En cambio, de lo que se trata es de garantizar que el código que escribe expresa la intención del diseño. Los valores que faltan son un concepto necesario para expresar en el código. El valor `null` es una forma clara de expresar los valores que faltan. El intento de quitar todos los valores `null` solo lleva a definir alguna otra forma de expresar esos valores que faltan sin `null`.

A continuación, deberá escribir el método `PerformSurvey` en la clase `SurveyRun`. Agregue el código siguiente a la clase `SurveyRun`:

[!code-csharp[PerformSurvey](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#PerformSurvey)]

De nuevo, la elección de que un elemento `List<SurveyResponse>?` acepte valores NULL indica que la respuesta puede tener valores NULL. Esto indica que la encuesta no se ha asignado a los encuestados todavía. Tenga en cuenta que los encuestados se agregan hasta que hayan dado su consentimiento.

El último paso para ejecutar la encuesta es agregar una llamada al realizar la encuesta al final del método `Main`:

[!code-csharp[RunSurvey](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/Program.cs#RunSurvey)]

## <a name="examine-survey-responses"></a>Examen de las respuestas de la encuesta

El último paso es mostrar los resultados de la encuesta. Agregará código a muchas de las clases que ha escrito. Este código muestra el valor de distinguir entre tipos de referencia que aceptan valores NULL y que no aceptan valores NULL. Empiece agregando los siguientes dos miembros con forma de expresión a la clase `SurveyResponse`:

[!code-csharp[ReportResponses](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#SurveyStatus)]

Dado que `surveyResponses` es un tipo de referencia que admite un valor NULL, las comprobaciones de valores NULL son necesarias antes de desreferenciarlo. El método `Answer` devuelve una cadena que no admite un valor NULL, por lo que tenemos que cubrir el caso de que falte una respuesta mediante el operador de fusión de NULL.

A continuación, agregue estos tres miembros con forma de expresión a la clase `SurveyRun`:

[!code-csharp[ReportResults](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#RunReport)]

El miembro `AllParticipants` debe tener en cuenta que la variable `respondents` podría ser aceptar valores NULL, pero el valor devuelto no puede ser NULL. Si cambia esa expresión quitando `??` y la secuencia vacía de a continuación, el compilador advertirá de que el método podría devolver `null` y su firma de devolución devuelve un tipo que no acepta valores NULL.

Finalmente, agregue el siguiente bucle a la parte inferior del método `Main`:

[!code-csharp[DisplaySurveyResults](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/Program.cs#WriteAnswers)]

No necesita ninguna comprobación `null` en este código porque ha diseñado las interfaces subyacentes para que devuelvan todos los tipos de referencia que no aceptan valores NULL.

## <a name="get-the-code"></a>Obtención del código

Puede obtener el código del tutorial terminado en nuestro repositorio de [ejemplos](https://github.com/dotnet/samples) en la carpeta [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction).

Experimente cambiando las declaraciones de tipos entre tipos de referencia que aceptan valores NULL y que no aceptan valores NULL. Vea cómo así se generan advertencias diferentes para garantizar que no se desreferencia accidentalmente un valor `null`.

## <a name="next-steps"></a>Pasos siguientes

Más información sobre cómo migrar una aplicación existente para usar tipos de referencia que aceptan valores NULL:
> [!div class="nextstepaction"]
> [Actualización de aplicaciones para usar tipos de referencia que aceptan valores NULL](upgrade-to-nullable-references.md)
