---
title: 'Tutorial: Crear el primer analizador y la corrección de código'
description: En este tutorial se proporcionan instrucciones detalladas para compilar un analizador y la corrección del código con el SDK del compilador de .NET (API de Roslyn).
ms.date: 08/01/2018
ms.custom: mvc
ms.openlocfilehash: f6fc21c010f9b5fcd5e709ef822639c020a7c93b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78240555"
---
# <a name="tutorial-write-your-first-analyzer-and-code-fix"></a>Tutorial: Crear el primer analizador y la corrección de código

El SDK de .NET Compiler Platform proporciona las herramientas necesarias para crear advertencias personalizadas destinadas al código de C# o de Visual Basic. Su **analizador** contiene código que reconoce las infracciones de la regla. La **corrección del código** contiene el código que corrige la infracción. Las reglas implementadas pueden ser cualquier elemento de la estructura de código para codificar el estilo de las convenciones de nomenclatura y mucho más. .NET Compiler Platform proporciona el marco para ejecutar el análisis a medida que los desarrolladores escriben código y todas las características de la interfaz de usuario de Visual Studio para corregir código: mostrar líneas de subrayado en el editor, rellenar la lista de errores de Visual Studio, crear las sugerencias con "bombillas" y mostrar la vista previa enriquecida de las correcciones sugeridas.

En este tutorial, explorará la creación de un **analizador** y una **corrección de código** complementaria con el uso de las API de Roslyn. Un analizador es una manera de realizar análisis de código fuente y notificar un problema al usuario. Opcionalmente, un analizador también puede proporcionar una corrección de código que representa una modificación del código fuente del usuario. Este tutorial crea un analizador que busca declaraciones de variable local que podrían declararse mediante el modificador `const`, aunque no están. La corrección de código complementaria modifica esas declaraciones para agregar el modificador `const`.

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2017](https://visualstudio.microsoft.com/vs/older-downloads/#visual-studio-2017-and-other-products)
- [Visual Studio 2019](https://www.visualstudio.com/downloads)

Debe instalar el **SDK de .NET Compiler Platform** a través del Instalador de Visual Studio:

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

Hay varios pasos para crear y validar su analizador:

1. Crear la solución.
1. Registrar el nombre del analizador y la descripción.
1. Notificar las recomendaciones y las advertencias del analizador.
1. Implementar la corrección de código para aceptar las recomendaciones.
1. Mejorar el análisis mediante las pruebas unitarias.

## <a name="explore-the-analyzer-template"></a>Exploración de la plantilla del analizador

El analizador notifica al usuario las declaraciones de variable local que se pueden convertir en constantes locales. Por ejemplo, considere el siguiente código:

```csharp
int x = 0;
Console.WriteLine(x);
```

En el código anterior, a `x` se le asigna un valor constante y nunca se modifica. Se puede declarar con el modificador `const`:

```csharp
const int x = 0;
Console.WriteLine(x);
```

El análisis para determinar si una variable se puede convertir en constante, que requiere un análisis sintáctico, un análisis constante de la expresión del inicializador y un análisis del flujo de datos para garantizar que no se escriba nunca en la variable. .NET Compiler Platform proporciona las API que facilita la realización de este análisis. El primer paso es crear un proyecto en C# del **analizador con corrección de código**.

- En Visual Studio, elija **Archivo > Nuevo > Proyecto...** para mostrar el cuadro de diálogo Nuevo proyecto.
- En **Visual C# > Extensibilidad**, elija **Analizador con corrección de código (.NET Standard)** .
- Asigne al proyecto el nombre "**MakeConst**" y haga clic en Aceptar.

La plantilla del analizador con corrección de código crea tres proyectos: uno contiene el analizador y la corrección de código, el segundo es un proyecto de prueba unitaria y el tercero es el proyecto de VSIX. El proyecto de inicio predeterminado es el proyecto de VSIX. Presione **F5** para iniciar el proyecto de VSIX. De esta forma se inicia una segunda instancia de Visual Studio que ha cargado el nuevo analizador.

> [!TIP]
> Al ejecutar el analizador, inicie una segunda copia de Visual Studio. Esta segunda copia usa un subárbol del registro diferente para almacenar la configuración. Le permite diferenciar la configuración visual en las dos copias de Visual Studio. Puede elegir un tema diferente para la ejecución experimental de Visual Studio. Además, no mueva la configuración o el inicio de sesión a la cuenta de Visual Studio con la ejecución experimental de Visual Studio. Así se mantiene una configuración diferente.

En la segunda instancia de Visual Studio que acaba de iniciar, cree un proyecto de aplicación de consola de C# (los proyectos de .NET Core o .NET Framework funcionarán; los analizadores funcionan a nivel de origen). Mantenga el mouse sobre el token con un subrayado ondulado y aparecerá el texto de advertencia proporcionado por un analizador.

La plantilla crea un analizador que notifica una advertencia en cada declaración de tipo, donde el nombre de tipo contiene letras minúsculas, tal como se muestra en la ilustración siguiente:

![Advertencia notificada por el analizador](media/how-to-write-csharp-analyzer-code-fix/report-warning.png)

La plantilla también proporciona una corrección de código que cambia cualquier nombre de tipo que contiene caracteres en minúsculas a mayúsculas. Puede hacer clic en la bombilla mostrada con la advertencia para ver los cambios sugeridos. Al aceptar los cambios sugeridos, se actualizan el nombre de tipo y todas las referencias a dicho tipo en la solución. Ahora que ha visto el analizador inicial en acción, cierre la segunda instancia de Visual Studio y vuelva a su proyecto de analizador.

No tiene que iniciar una segunda copia de Visual Studio, y cree código para probar todos los cambios en el analizador. La plantilla también crea un proyecto de prueba unitaria de forma automática. Este proyecto contiene dos pruebas. `TestMethod1` muestra el formato típico de una prueba que analiza el código sin que se desencadene un diagnóstico. `TestMethod2` muestra el formato de una prueba que desencadena un diagnóstico y, a continuación, se aplica una corrección de código sugerida. Al crear el analizador y la corrección de código, deberá escribir pruebas para diferentes estructuras de código para verificar el trabajo. Las pruebas unitarias de los analizadores son mucho más rápidas que las pruebas interactivas con Visual Studio.

> [!TIP]
> Las pruebas unitarias del analizador son una herramienta magnífica si se sabe qué construcciones de código deben y no deben desencadenar el analizador. Cargar el analizador en otra copia de Visual Studio es una herramienta magnífica para explorar y buscar construcciones en las que puede no haber pensado todavía.

## <a name="create-analyzer-registrations"></a>Creación de registros del analizador

La plantilla crea la clase `DiagnosticAnalyzer` inicial en el archivo **MakeConstAnalyzer.cs**. Este analizador inicial muestra dos propiedades importantes de cada analizador.

- Cada analizador de diagnóstico debe proporcionar un atributo `[DiagnosticAnalyzer]` que describe el lenguaje en el que opera.
- Cada analizador de diagnóstico debe derivar de la clase <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer>.

La plantilla también muestra las características básicas que forman parte de cualquier analizador:

1. Registre acciones. Las acciones representan los cambios de código que deben desencadenar el analizador para examinar el código para las infracciones. Cuando Visual Studio detecta las modificaciones del código que coinciden con una acción registrada, llama al método registrado del analizador.
1. Cree diagnósticos. Cuando el analizador detecta una infracción, crea un objeto de diagnóstico que Visual Studio usa para notificar la infracción al usuario.

Registre acciones en la invalidación del método <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer.Initialize(Microsoft.CodeAnalysis.Diagnostics.AnalysisContext)?displayProperty=nameWithType>. En este tutorial, repasará **nodos de sintaxis** que buscan declaraciones locales y verá cuáles de ellos tienen valores constantes. Si una declaración puede ser constante, el analizador creará y notificará un diagnóstico.

El primer paso es actualizar las constantes de registro y el método `Initialize`, por lo que estas constantes indican su analizador "Make Const". La mayoría de las constantes de cadena se definen en el archivo de recursos de cadena. Debe seguir dicha práctica para una localización más sencilla. Abra el archivo **Resources.resx** para el proyecto de analizador **MakeConst**. Muestra el editor de recursos. Actualice los recursos de cadena como sigue:

- Cambie `AnalyzerTitle` por "La variable puede convertirse en constante".
- Cambie `AnalyzerMessageFormat` por "Puede convertirse en constante".
- Cambie `AnalyzerDescription` por "Convertir en constante".

Cambie también el menú desplegable del **modificador de acceso** por `public`. De esta forma, se facilita el uso de estas constantes en las pruebas unitarias. Cuando haya terminado, el editor de recursos debe aparecer como se muestra en la figura siguiente:

![Actualización de los recursos de cadena](media/how-to-write-csharp-analyzer-code-fix/update-string-resources.png)

Los cambios restantes están en el archivo del analizador. Abra **MakeConstAnalyzer.cs** en Visual Studio. Cambie la acción registrada de una que actúa en los símbolos a una que actúa en la sintaxis. En el método `MakeConstAnalyzerAnalyzer.Initialize`, busque la línea que registra la acción en los símbolos:

```csharp
context.RegisterSymbolAction(AnalyzeSymbol, SymbolKind.NamedType);
```

Reemplácela por la línea siguiente:

[!code-csharp[Register the node action](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstAnalyzer.cs#RegisterNodeAction "Register a node action")]

Después de este cambio, puede eliminar el método `AnalyzeSymbol`. Este analizador examina <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.LocalDeclarationStatement?displayProperty=nameWithType>, no las instrucciones <xref:Microsoft.CodeAnalysis.SymbolKind.NamedType?displayProperty=nameWithType>. Tenga en cuenta que `AnalyzeNode` tiene un subrayado ondulado rojo debajo. El código recién agregado hace referencia a un método `AnalyzeNode` que no se ha declarado. Declare dicho método con el siguiente código:

```csharp
private void AnalyzeNode(SyntaxNodeAnalysisContext context)
{
}
```

Cambie `Category` por "Uso" en **MakeConstAnalyzer.cs** como se muestra en el código siguiente:

```csharp
private const string Category = "Usage";
```

## <a name="find-local-declarations-that-could-be-const"></a>Búsqueda de las declaraciones locales que podrían ser constantes

Es el momento de escribir la primera versión del método `AnalyzeNode`. Debe buscar una sola declaración local que podría ser `const` pero no lo es, al igual que el código siguiente:

```csharp
int x = 0;
Console.WriteLine(x);
```

El primer paso es encontrar las declaraciones locales. Agregue el código siguiente a `AnalyzeNode` en **MakeConstAnalyzer.cs**:

```csharp
var localDeclaration = (LocalDeclarationStatementSyntax)context.Node;
```

Esta conversión siempre se realiza correctamente porque el analizador registró los cambios de las declaraciones locales, y solo las declaraciones locales. Ningún otro tipo de nodo desencadena una llamada al método `AnalyzeNode`. A continuación, compruebe la declaración de cualquier modificador `const`. Si la encuentra, devuélvala de inmediato. El código siguiente busca cualquier modificador `const` en la declaración local:

```csharp
// make sure the declaration isn't already const:
if (localDeclaration.Modifiers.Any(SyntaxKind.ConstKeyword))
{
    return;
}
```

Por último, deberá comprobar que la variable podría ser `const`. Esto significa asegurarse de que nunca se asigne después de inicializarse.

Realizará algún análisis semántico con <xref:Microsoft.CodeAnalysis.Diagnostics.SyntaxNodeAnalysisContext>. Use el argumento `context` para determinar si la declaración de variable local puede convertirse en `const`. Una clase <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> representa toda la información semántica en un solo archivo de origen. Puede obtener más información en el artículo que trata los [modelos semánticos](../work-with-semantics.md). Deberá usar <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> para realizar análisis de flujo de datos en la instrucción de declaración local. A continuación, use los resultados de este análisis de flujo de datos para garantizar que la variable local no se escriba con un valor nuevo en cualquier otro lugar. Llame al método de extensión <xref:Microsoft.CodeAnalysis.ModelExtensions.GetDeclaredSymbol%2A> para recuperar <xref:Microsoft.CodeAnalysis.ILocalSymbol> para la variable y compruebe si no está incluido en la colección <xref:Microsoft.CodeAnalysis.DataFlowAnalysis.WrittenOutside%2A?displayProperty=nameWithType> del análisis de flujo de datos. Agregue el código siguiente al final del método `AnalyzeNode`:

```csharp
// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

// Retrieve the local symbol for each variable in the local declaration
// and ensure that it is not written outside of the data flow analysis region.
var variable = localDeclaration.Declaration.Variables.Single();
var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
{
    return;
}
```

El código recién agregado garantiza que no se modifique la variable y que se pueda convertir por tanto en `const`. Es el momento de generar el diagnóstico. Agregue el código siguiente a la última línea en `AnalyzeNode`:

```csharp
context.ReportDiagnostic(Diagnostic.Create(Rule, context.Node.GetLocation()));
```

Puede comprobar el progreso presionando **F5** para ejecutar el analizador. Puede cargar la aplicación de consola que creó anteriormente y después agregar el siguiente código de prueba:

```csharp
int x = 0;
Console.WriteLine(x);
```

Debe aparecer la bombilla, y el analizador debe informar de un diagnóstico. Sin embargo, la bombilla todavía indica que la plantilla generó la corrección de código e indica que se puede convertir en mayúsculas. En la sección siguiente se explica cómo escribir la corrección de código.

## <a name="write-the-code-fix"></a>Escritura de la corrección de código

Un analizador puede proporcionar una o varias correcciones de código. Una corrección de código define una edición que soluciona el problema notificado. Para el analizador que ha creado, puede proporcionar una corrección de código que inserta la palabra clave const:

```csharp
const int x = 0;
Console.WriteLine(x);
```

El usuario la elige en la interfaz de usuario de la bombilla del editor, y Visual Studio cambia el código.

Abra el archivo **MakeConstCodeFixProvider.cs** agregado por la plantilla.  Esta corrección de código ya está conectada con el identificador de diagnóstico generado por el analizador de diagnóstico, pero aún no implementa la transformación de código correcta. En primer lugar debe quitar parte del código de la plantilla. Cambie la cadena de título por "Convertir en constante":

[!code-csharp[Update the CodeFix title](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CodeFixTitle "Update the CodeFix title")]

Después, elimine el método `MakeUppercaseAsync`. Ya no se aplica.

Todos los proveedores de corrección de código se derivan de <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider>. Todas invalidan <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider.RegisterCodeFixesAsync(Microsoft.CodeAnalysis.CodeFixes.CodeFixContext)?displayProperty=nameWithType> para notificar las correcciones de código disponibles. En `RegisterCodeFixesAsync`, cambie el tipo de nodo antecesor que está buscando por <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax> para que coincida con el diagnóstico:

[!code-csharp[Find local declaration node](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FindDeclarationNode  "Find the local declaration node that raised the diagnostic")]

A continuación, cambie la última línea para registrar una corrección de código. La corrección creará un documento que resulta de agregar el modificador `const` a una declaración existente:

[!code-csharp[Register the new code fix](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#RegisterCodeFix  "Register the new code fix")]

Observará un subrayado ondulado rojo en el código que acaba de agregar en el símbolo `MakeConstAsync`. Agregue una declaración para `MakeConstAsync` como el código siguiente:

```csharp
private async Task<Document> MakeConstAsync(Document document,
   LocalDeclarationStatementSyntax localDeclaration,
   CancellationToken cancellationToken)
{
}
```

El nuevo método `MakeConstAsync` transformará la clase <xref:Microsoft.CodeAnalysis.Document> que representa el archivo de origen del usuario en una nueva clase <xref:Microsoft.CodeAnalysis.Document> que ahora contiene una declaración `const`.

Se crea un token de palabra clave `const` para insertarlo en la parte delantera de la instrucción de declaración. Tenga cuidado de quitar primero cualquier curiosidad inicial del primer token de la instrucción de declaración y adjúntela al token `const`. Agregue el código siguiente al método `MakeConstAsync`:

[!code-csharp[Create a new const keyword token](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CreateConstToken  "Create the new const keyword token")]

A continuación, agregue el token `const` a la declaración con el siguiente código:

```csharp
// Insert the const token into the modifiers list, creating a new modifiers list.
var newModifiers = trimmedLocal.Modifiers.Insert(0, constToken);
// Produce the new local declaration.
var newLocal = trimmedLocal
    .WithModifiers(newModifiers)
    .WithDeclaration(localDeclaration.Declaration);
```

Después aplique formato a la nueva declaración para que coincida con las reglas de formato de C#. Aplicar formato a los cambios para que coincidan con el código existente mejora la experiencia. Agregue la instrucción siguiente inmediatamente después del código existente:

[!code-csharp[Format the new declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FormatLocal  "Format the new declaration")]

Se requiere un nuevo espacio de nombres para este código. Agregue la siguiente instrucción `using` al principio del archivo:

```csharp
using Microsoft.CodeAnalysis.Formatting;
```

El último paso es realizar la edición. Hay tres pasos para este proceso:

1. Obtenga un identificador para el documento existente.
1. Cree un documento mediante el reemplazo de la declaración existente con la nueva declaración.
1. Devuelva el nuevo documento.

Agregue el código siguiente al final del método `MakeConstAsync`:

[!code-csharp[replace the declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceDocument  "Generate a new document by replacing the declaration")]

La corrección de código está lista para probarla.  Presione F5 para ejecutar el proyecto del analizador en una segunda instancia de Visual Studio. En la segunda instancia de Visual Studio, cree un proyecto de aplicación de consola de C# y agregue algunas declaraciones de variable local inicializadas con valores de constante para el método Main. Observará que se notifican como advertencias de la siguiente forma.

![Puede convertir las advertencias en constantes](media/how-to-write-csharp-analyzer-code-fix/make-const-warning.png)

Ha progresado bastante. Hay subrayados ondulados debajo de las declaraciones que pueden convertirse en `const`. Pero aún queda trabajo por hacer. Esto funciona bien si agrega `const` a las declaraciones a partir de `i`, luego `j` y, por último, `k`. Sin embargo, si agrega el modificador `const` en un orden diferente, a partir de `k`, el analizador crea errores: `k` no puede declararse como `const`, a menos que `i` y `j` ya sean `const`. Tiene que realizar más análisis para asegurarse de que controla la forma en que las variables pueden declararse e inicializarse.

## <a name="build-data-driven-tests"></a>Creación de pruebas basadas en datos

El analizador y la corrección de código funcionan en un caso sencillo de una única declaración que puede convertirse en const. Hay varias instrucciones de declaración posibles donde esta implementación comete errores. Abordará estos casos al trabajar con la biblioteca de pruebas unitarias escrita por la plantilla. Es mucho más rápido que abrir repetidamente una segunda copia de Visual Studio.

Abra el archivo **MakeConstUnitTests.cs** en el proyecto de prueba unitaria. La plantilla creó dos pruebas que siguen los dos patrones comunes para una prueba unitaria de la corrección de código y del analizador. `TestMethod1` muestra el patrón para una prueba que garantiza que el analizador no notifique un diagnóstico cuando no debe. `TestMethod2` muestra el patrón de notificación de un diagnóstico y de ejecución de la corrección de código.

El código para casi todas las pruebas del analizador sigue uno de estos dos patrones. Para el primer paso, puede reprocesar estas pruebas como pruebas basadas en datos. Después, será fácil crear pruebas con la adición de nuevas constantes de cadena para representar diferentes entradas de prueba.

Por cuestiones de eficacia, el primer paso es refactorizar las dos pruebas en pruebas basadas en datos. Después, solo necesita definir un par de constantes de cadena para cada prueba nueva. Durante la refactorización, cambie el nombre de ambos métodos por otros nombres mejores. Reemplace `TestMethod1` con esta prueba que garantiza que no se realizará ningún diagnóstico:

```csharp
[DataTestMethod]
[DataRow("")]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
{
    VerifyCSharpDiagnostic(testCode);
}
```

Puede crear una fila de datos para esta prueba mediante la definición de cualquier fragmento de código que no debería provocar que el diagnóstico desencadene una advertencia. Esta sobrecarga de `VerifyCSharpDiagnostic` pasa cuando no hay ningún diagnóstico desencadenado para el fragmento de código fuente.

Después, reemplace `TestMethod2` con esta prueba que garantiza la realización de un diagnóstico y la aplicación de una corrección de código para el fragmento de código fuente:

```csharp
[DataTestMethod]
[DataRow(LocalIntCouldBeConstant, LocalIntCouldBeConstantFixed, 10, 13)]
public void WhenDiagnosticIsRaisedFixUpdatesCode(
    string test,
    string fixTest,
    int line,
    int column)
{
    var expected = new DiagnosticResult
    {
        Id = MakeConstAnalyzer.DiagnosticId,
        Message = new LocalizableResourceString(nameof(MakeConst.Resources.AnalyzerMessageFormat), MakeConst.Resources.ResourceManager, typeof(MakeConst.Resources)).ToString(),
        Severity = DiagnosticSeverity.Warning,
        Locations =
            new[] {
                    new DiagnosticResultLocation("Test0.cs", line, column)
                }
    };

    VerifyCSharpDiagnostic(test, expected);

    VerifyCSharpFix(test, fixTest);
}
```

El código anterior también realizó un par de cambios en el código que compila el resultado de diagnóstico esperado. Usa las constantes públicas registradas en el analizador `MakeConst`. Además, utiliza dos constantes de cadena para el origen de entrada y fijo. Agregue las siguientes constantes de cadena a la clase `UnitTest`:

[!code-csharp[string constants for fix test](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FirstFixTest "string constants for fix test")]

Ejecute estas dos pruebas para asegurarse de que pasen. En Visual Studio, abra el **Explorador de pruebas**; para ello, seleccione **Prueba** > **Windows** > **Explorador de pruebas**.  Haga clic en el vínculo **Ejecutar todo**.

## <a name="create-tests-for-valid-declarations"></a>Creación de pruebas para declaraciones válidas

Por norma general, los analizadores deben existir lo más rápido posible, pero haciendo el mínimo trabajo. Visual Studio llama a los analizadores registrados a medida que el usuario edita el código. La capacidad de respuesta es un requisito clave. Hay varios casos de pruebas del código que no deben realizar un diagnóstico. El analizador ya controla una de esas pruebas, el caso en que una variable se asigna después de inicializarse. Agregue la siguiente constante de cadena a las pruebas para representar dicho caso:

[!code-csharp[variable assigned](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VariableAssigned "a variable that is assigned after being initialized won't raise the diagnostic")]

Después, agregue una fila de datos para esta prueba como se muestra en el fragmento de código siguiente:

```csharp
[DataTestMethod]
[DataRow(""),
 DataRow(VariableAssigned)]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
```

Esta prueba también pasa. Después, agregue constantes para las condiciones que aún no ha controlado:

- Declaraciones que ya son `const`, porque ya son constantes:

   [!code-csharp[already const declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#AlreadyConst "a declaration that is already const should not raise the diagnostic")]

- Declaraciones que no tienen inicializador, porque no hay ningún valor para usar:

   [!code-csharp[declarations that have no initializer](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#NoInitializer "a declaration that has no initializer should not raise the diagnostic")]

- Declaraciones donde el inicializador no es una constante, porque no pueden ser constantes en tiempo de compilación:

   [!code-csharp[declarations where the initializer isn't const](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#InitializerNotConstant "a declaration where the initializer is not a compile-time constant should not raise the diagnostic")]

Puede ser incluso más complicado, porque C# admite varias declaraciones como una instrucción. Considere la siguiente constante de cadena de caso de prueba:

[!code-csharp[multiple initializers](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#MultipleInitializers "A declaration can be made constant only if all variables in that statement can be made constant")]

La variable `i` puede convertirse en constante, pero la variable `j` no puede. Por tanto, esta instrucción no puede convertirse en una declaración de constante. Agregue las declaraciones `DataRow` para todas estas pruebas:

```csharp
[DataTestMethod]
[DataRow(""),
    DataRow(VariableAssigned),
    DataRow(AlreadyConst),
    DataRow(NoInitializer),
    DataRow(InitializerNotConstant),
    DataRow(MultipleInitializers)]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
```

Vuelva a ejecutar las pruebas y, después, observará que estos nuevos casos de prueba generarán errores.

## <a name="update-your-analyzer-to-ignore-correct-declarations"></a>Actualización del analizador para ignorar declaraciones correctas

Necesita algunas mejoras en el método `AnalyzeNode` del analizador para filtrar el código que cumple estas condiciones. Son todas condiciones relacionadas, por lo que los cambios similares corregirán todas estas condiciones. Realice los siguientes cambios en `AnalyzeNode`:

- El análisis semántico analizó una única declaración de variable. Este código necesita estar en un bucle `foreach` que examina todas las variables declaradas en la misma instrucción.
- Cada variable declarada necesita tener un inicializador.
- El inicializador de cada variable declarada debe ser una constante de tiempo de compilación.

En el método `AnalyzeNode`, reemplace el análisis semántico original:

```csharp
// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

// Retrieve the local symbol for each variable in the local declaration
// and ensure that it is not written outside of the data flow analysis region.
var variable = localDeclaration.Declaration.Variables.Single();
var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
{
    return;
}
```

por el siguiente fragmento de código:

```csharp
// Ensure that all variables in the local declaration have initializers that
// are assigned with constant values.
foreach (var variable in localDeclaration.Declaration.Variables)
{
    var initializer = variable.Initializer;
    if (initializer == null)
    {
        return;
    }

    var constantValue = context.SemanticModel.GetConstantValue(initializer.Value);
    if (!constantValue.HasValue)
    {
        return;
    }
}

// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

foreach (var variable in localDeclaration.Declaration.Variables)
{
    // Retrieve the local symbol for each variable in the local declaration
    // and ensure that it is not written outside of the data flow analysis region.
    var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
    if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
    {
        return;
    }
}
```

El primer bucle `foreach` examina cada declaración de variable con análisis sintácticos La primera comprobación garantiza que la variable tiene un inicializador. La segunda comprobación garantiza que el inicializador es una constante. El segundo bucle tiene el análisis semántico original. Las comprobaciones semánticas se encuentran en un bucle independiente porque afectan más al rendimiento. Vuelva a ejecutar las pruebas y observará que todas pasan.

## <a name="add-the-final-polish"></a>Adición de un retoque final

Casi ha terminado. Hay algunas condiciones más que el analizador tiene que cumplir. Visual Studio llama a los analizadores mientras el usuario escribe el código. Suele darse el caso de que se llama al analizador para código que no compila. El método `AnalyzeNode` del analizador de diagnóstico no comprueba si el valor de constante se puede convertir al tipo de variable. Por tanto, la implementación actual convertirá correctamente una declaración incorrecta, como int i = "abc"', en una constante local. Agregue una constante de cadena de origen para esa condición:

[!code-csharp[Mismatched types don't raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsInvalid "When the variable type and the constant type don't match, there's no diagnostic")]

Además, los tipos de referencia no se controlan correctamente. El único valor de constante permitido para un tipo de referencia es `null`, excepto en este caso de <xref:System.String?displayProperty=nameWithType>, que admite los literales de cadena. En otras palabras, `const string s = "abc"` es legal, pero `const object s = "abc"` no lo es. Este fragmento de código comprueba esa condición:

[!code-csharp[Reference types don't raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsntString "When the variable type is a reference type other than string, there's no diagnostic")]

Para ser exhaustivo, debe agregar otra prueba para asegurarse de que puede crear una declaración de constante para una cadena. El fragmento de código siguiente define el código que genera el diagnóstico y el código después de haber aplicado la corrección:

[!code-csharp[string reference types raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#ConstantIsString "When the variable type is string, it can be constant")]

Por último, si una variable se declara con la palabra clave `var`, la corrección de código hace una función incorrecta y genera una declaración `const var`, que el lenguaje C# no admite. Para corregir este error, la corrección de código debe reemplazar la palabra clave `var` por el nombre del tipo deducido:

[!code-csharp[var references need to use the inferred types](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VarDeclarations "Declarations made using var must have the type replaced with the inferred type")]

Estos cambios actualizan las declaraciones de la fila de datos en ambas pruebas. El código siguiente muestra estas pruebas con todos los atributos de la fila de datos:

[!code-csharp[The finished tests](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FinishedTests "The finished tests for the make const analyzer")]

Afortunadamente, todos los errores anteriores se pueden tratar con las mismas técnicas que acaba de aprender.

Para corregir el primer error, primero abra **DiagnosticAnalyzer.cs** y busque el bucle foreach donde cada uno de los inicializadores de la declaración local se comprueba para asegurarse de que se les asignan valores constantes. Inmediatamente _antes_ del primer bucle foreach, llame a `context.SemanticModel.GetTypeInfo()` para recuperar información detallada sobre el tipo declarado de la declaración local:

```csharp
var variableTypeName = localDeclaration.Declaration.Type;
var variableType = context.SemanticModel.GetTypeInfo(variableTypeName).ConvertedType;
```

Después, dentro del bucle `foreach`, compruebe cada inicializador para asegurarse de que se puede convertir al tipo de variable. Agregue la siguiente comprobación después de asegurarse de que el inicializador es una constante:

```csharp
// Ensure that the initializer value can be converted to the type of the
// local declaration without a user-defined conversion.
var conversion = context.SemanticModel.ClassifyConversion(initializer.Value, variableType);
if (!conversion.Exists || conversion.IsUserDefined)
{
    return;
}
```

El siguiente cambio se basa en el último. Antes de cerrar la llave del primer bucle foreach, agregue el código siguiente para comprobar el tipo de declaración local cuando la constante es una cadena o null.

```csharp
// Special cases:
//  * If the constant value is a string, the type of the local declaration
//    must be System.String.
//  * If the constant value is null, the type of the local declaration must
//    be a reference type.
if (constantValue.Value is string)
{
    if (variableType.SpecialType != SpecialType.System_String)
    {
        return;
    }
}
else if (variableType.IsReferenceType && constantValue.Value != null)
{
    return;
}
```

Debe escribir algo más de código en el proveedor de corrección de código para reemplazar la palabra clave var' por el nombre de tipo correcto. Vuelva a **CodeFixProvider.cs**. El código que se va a agregar realiza los pasos siguientes:

- Compruebe si la declaración es una declaración `var` y, en su caso:
- Cree un tipo para el tipo deducido.
- Asegúrese de que la declaración de tipo no es un alias. Si es así, es válido declarar `const var`.
- Asegúrese de que `var` no es un nombre de tipo en este programa. (Si es así, `const var` es válido).
- Simplificación del nombre de tipo completo

Parece mucho código. Pero no lo es. Reemplace la línea que declara e inicializa `newLocal` con el código siguiente. Va inmediatamente después de la inicialización de `newModifiers`:

[!code-csharp[Replace Var designations](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceVar "Replace a var designation with the explicit type")]

Deberá agregar una instrucción `using` para usar el tipo <xref:Microsoft.CodeAnalysis.Simplification.Simplifier>:

```csharp
using Microsoft.CodeAnalysis.Simplification;
```

Ejecute las pruebas, y todas deberían pasar. Felicítese por ejecutar el analizador terminado. Presione Ctrl + F5 para ejecutar el proyecto de analizador en una segunda instancia de Visual Studio con la extensión de la versión preliminar de Roslyn cargada.

- En la segunda instancia de Visual Studio, cree un proyecto de aplicación de consola de C# y agregue `int x = "abc";` al método Main. Gracias a la primera corrección de errores, no se debe notificar ninguna advertencia para esta declaración de variable local (aunque hay un error del compilador según lo esperado).
- A continuación, agregue `object s = "abc";` al método Main. Debido a la segunda corrección de errores, no se debe notificar ninguna advertencia.
- Por último, agregue otra variable local que usa la palabra clave `var`. Observará que se notifica una advertencia y que aparece una sugerencia debajo a la izquierda.
- Mueva el símbolo de intercalación del editor sobre el subrayado ondulado y presione Ctrl+ para mostrar la corrección de código sugerida. Al seleccionar la corrección de código, tenga en cuenta que la palabra clave var' ahora se controla correctamente.

Por último, agregue el código siguiente:

```csharp
int i = 2;
int j = 32;
int k = i + j;
```

Después de estos cambios, obtendrá un subrayado ondulado rojo solo en las dos primeras variables. Agregue `const` a `i` y `j`, y obtendrá una nueva advertencia sobre `k` porque ahora puede ser `const`.

¡Enhorabuena! Ha creado su primera extensión de .NET Compiler Platform que realiza un análisis de código sobre la marcha para detectar un problema y proporciona una solución rápida para corregirlo. Durante el proceso, ha aprendido muchas de las API de código que forman parte del SDK de .NET Compiler Platform (API de Roslyn). Puede comprobar su trabajo con el [ejemplo completo](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/Tutorials/MakeConst) en nuestro repositorio de ejemplos de GitHub.

## <a name="other-resources"></a>Otros recursos

- [Introducción al análisis de sintaxis](../get-started/syntax-analysis.md)
- [Introducción al análisis semántico](../get-started/semantic-analysis.md)
