---
title: Introducción al análisis semántico
description: En este tutorial, se proporciona una introducción sobre cómo trabajar con el análisis semántico mediante el SDK de .NET Compiler.
ms.date: 02/06/2018
ms.custom: mvc
ms.openlocfilehash: 3119363822328c0e5fc67c2a2a4a917a7d37cfd2
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104872566"
---
# <a name="get-started-with-semantic-analysis"></a>Introducción al análisis semántico

En este tutorial, se asume que conoce la API de sintaxis. En el artículo [Introducción al análisis de sintaxis](syntax-analysis.md) se proporciona una introducción suficiente.

En este tutorial, explorará las **API de símbolo** y **enlace**. Estas API ofrecen información sobre el _significado semántico_ de un programa. Le permiten formular y responder preguntas sobre los tipos representados por cualquier símbolo en el programa.

Deberá instalar el **SDK de .NET Compiler Platform**:

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

## <a name="understanding-compilations-and-symbols"></a>Comprender las compilaciones y los símbolos

Conforme trabaja más con el SDK de .NET Compiler, empieza a familiarizarse con las diferencias entre la API de sintaxis y la API semántica. La **API de sintaxis** le permite buscar en la _estructura_ de un programa. En cambio, a menudo quiere una información más completa sobre la semántica o el _significado_ de un programa. Aunque un fragmento de código o archivo de código dinámico de Visual Basic o C# se puede analizar sintácticamente de forma aislada, no tiene sentido formular preguntas como "¿cuál es el tipo de esta variable?" de manera unilateral. El significado de un nombre de tipo puede depender de las referencias de ensamblado, las importaciones de espacio de nombres u otros archivos de código. Esas preguntas se responden mediante la **API semántica**, concretamente la clase <xref:Microsoft.CodeAnalysis.Compilation?displayProperty=nameWithType>.

Una instancia de <xref:Microsoft.CodeAnalysis.Compilation> es análoga a un único proyecto, tal como muestra el compilador y representa todo lo necesario para compilar un programa de Visual Basic o C#. La **compilación** incluye el conjunto de archivos de código fuente que se compilarán, las referencias de ensamblado y las opciones del compilador. Puede analizar el significado del código con toda la demás información en este contexto. Una <xref:Microsoft.CodeAnalysis.Compilation> permite buscar **símbolos** (entidades como tipos, espacios de nombres, miembros y variables a los que hacen referencia nombres y otras expresiones). El proceso de asociar los nombres y las expresiones con **símbolos** se denomina **enlace**.

Como <xref:Microsoft.CodeAnalysis.SyntaxTree?displayProperty=nameWithType>, <xref:Microsoft.CodeAnalysis.Compilation> es una clase abstracta con derivados específicos del lenguaje. Al crear una instancia de la compilación, debe invocar un método de generador en la clase <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation?displayProperty=nameWithType> (o <xref:Microsoft.CodeAnalysis.VisualBasic.VisualBasicCompilation?displayProperty=nameWithType>).

## <a name="querying-symbols"></a>Consultar símbolos

En este tutorial, volverá a examinar el programa "Hola mundo". En esta ocasión, consultará los símbolos del programa para comprender qué tipos representan esos símbolos. Consultará los tipos en un espacio de nombres y aprenderá a buscar los métodos disponibles en un tipo.

Puede ver el código terminado de este ejemplo en [nuestro repositorio de GitHub](https://github.com/dotnet/samples/tree/main/csharp/roslyn-sdk/SemanticQuickStart).

> [!NOTE]
> Los tipos de árbol de sintaxis usan la herencia para describir los diferentes elementos de sintaxis que son válidos en diferentes ubicaciones del programa. A menudo, usar estas API significa convertir propiedades o miembros de colección en tipos derivados concretos. En los ejemplos siguientes, la asignación y las conversiones son instrucciones independientes, con variables con tipo explícito. Puede leer el código para ver los tipos de valor devuelto de la API y el tipo de motor de ejecución de los objetos devueltos. En la práctica, es más habitual usar variables con tipo implícito y basarse en nombres de API para describir el tipo de los objetos que se examinan.

Cree un proyecto de **Stand-Alone Code Analysis Tool** (Herramienta de análisis de código independiente) de C#:

* En Visual Studio, elija **Archivo** > **Nuevo** > **Proyecto** para mostrar el cuadro de diálogo Nuevo proyecto.
* En **Visual C#**  > **Extensibilidad**, elija **Stand-Alone Code Analysis Tool** (Herramienta de análisis de código independiente).
* Asigne al proyecto el nombre "**SemanticQuickStart**" y haga clic en Aceptar.

Va a analizar el programa básico "Hola mundo" mostrado anteriormente.
Agregue el texto para el programa Hola mundo como una constante en su clase `Program`:

[!code-csharp[Declare the program test](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#1 "Declare a constant string for the program text to analyze")]

A continuación, agregue el código siguiente para crear el árbol de sintaxis para el texto del código de la constante `programText`.  Agregue la línea siguiente al método `Main`:

[!code-csharp[Create the tree](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#2 "Create the syntax tree")]

A continuación, compile una <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation> del árbol que ya ha creado. El ejemplo "Hola mundo" se basa en los tipos <xref:System.String> y <xref:System.Console>. Debe hacer referencia al ensamblado que declara esos dos tipos en la compilación. Agregue la siguiente línea a su método `Main` para crear una compilación de su árbol de sintaxis, incluida la referencia al ensamblado adecuado:

[!code-csharp[Create the compilation](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#3 "Create the compilation for the semantic model")]

El método <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation.AddReferences%2A?displayProperty=nameWithType> agrega referencias a la compilación. El método <xref:Microsoft.CodeAnalysis.MetadataReference.CreateFromFile%2A?displayProperty=nameWithType> carga un ensamblado como referencia.

## <a name="querying-the-semantic-model"></a>Consultar el modelo semántico

Una vez que tenga una <xref:Microsoft.CodeAnalysis.Compilation>, puede pedirle un <xref:Microsoft.CodeAnalysis.SemanticModel> para cualquier <xref:Microsoft.CodeAnalysis.SyntaxTree> incluido en esa <xref:Microsoft.CodeAnalysis.Compilation>. Puede considerar el modelo semántico como el origen de toda la información que normalmente obtendría de IntelliSense. Un <xref:Microsoft.CodeAnalysis.SemanticModel> puede responder a preguntas como "¿Qué nombres entran en el ámbito de esta ubicación?", "¿A qué miembros se puede acceder desde este método?", "¿Qué variables se usan en este bloque de texto?" y "¿A qué hace referencia este nombre o expresión?". Agregue esta instrucción para crear el modelo semántico:

[!code-csharp[Create the semantic model](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#4 "Create the semantic model")]

## <a name="binding-a-name"></a>Enlazar un nombre

La <xref:Microsoft.CodeAnalysis.Compilation> crea el <xref:Microsoft.CodeAnalysis.SemanticModel> desde el <xref:Microsoft.CodeAnalysis.SyntaxTree>. Después de crear el modelo, puede consultarlo para buscar la primera directiva `using` y recuperar la información de símbolo del espacio de nombres `System`. Agregue estas dos líneas en su método `Main` para crear el modelo semántico y recuperar el símbolo de la primera instrucción using:

[!code-csharp[Find the namespace symbol for the first using](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#5 "Find the namespace symbol for the first using")]

En el código anterior se muestra cómo enlazar el nombre de la primera directiva de `using` para recuperar un <xref:Microsoft.CodeAnalysis.SymbolInfo?displayProperty=nameWithType> para el espacio de nombres `System`. El código anterior también muestra que usa el **modelo de sintaxis** para buscar la estructura del código y usa el **modelo semántico** para entender su significado. El **modelo de sintaxis** busca la cadena `System` en la instrucción using. El **modelo semántico** tiene toda la información sobre los tipos definidos en el espacio de nombres `System`.

Desde el objeto <xref:Microsoft.CodeAnalysis.SymbolInfo> puede obtener el <xref:Microsoft.CodeAnalysis.ISymbol?displayProperty=nameWithType> mediante la propiedad <xref:Microsoft.CodeAnalysis.SymbolInfo.Symbol?displayProperty=nameWithType>. Esta propiedad devuelve el símbolo al que hace referencia esta expresión. Para las expresiones que no hacen referencia a ningún elemento (por ejemplo, los literales numéricos), esta propiedad es `null`. Cuando el <xref:Microsoft.CodeAnalysis.SymbolInfo.Symbol?displayProperty=nameWithType> no es NULL, el <xref:Microsoft.CodeAnalysis.ISymbol.Kind?displayProperty=nameWithType> denota el tipo del símbolo. En este ejemplo, la propiedad <xref:Microsoft.CodeAnalysis.ISymbol.Kind?displayProperty=nameWithType> es un <xref:Microsoft.CodeAnalysis.SymbolKind.Namespace?displayProperty=nameWithType>. Agregue el código siguiente al método `Main`. Recupera el símbolo del espacio de nombres `System` y, después, muestra todos los espacios de nombres secundarios que se declaran en el espacio de nombres `System`:

[!code-csharp[Display all the child namespaces](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#6 "Display all the child namespaces from this compilation")]

Ejecute el programa y debería ver la siguiente salida:

```output
System.Collections
System.Configuration
System.Deployment
System.Diagnostics
System.Globalization
System.IO
System.Numerics
System.Reflection
System.Resources
System.Runtime
System.Security
System.StubHelpers
System.Text
System.Threading
Press any key to continue . . .
```

> [!NOTE]
> La salida no incluye todos los espacios de nombres que son secundarios del espacio de nombres `System`. Muestra cada espacio de nombres que se encuentra en esta compilación, que solo hace referencia al ensamblado donde se declara `System.String`. Esta compilación no conoce ningún espacio de nombres declarado en otros ensamblados.

### <a name="binding-an-expression"></a>Enlazar una expresión

El código anterior muestra cómo buscar un símbolo al enlazarlo a un nombre. Hay otras expresiones en un programa de C# que se pueden enlazar que no son nombres. Para demostrar esta funcionalidad, accederemos al enlace a un literal de cadena sencillo.

El programa "Hola mundo" contiene una <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LiteralExpressionSyntax?displayProperty=nameWithType>, la cadena "Hello, World!" que se muestra en la consola.

Encontrará la cadena "Hello, World!" si busca el literal de cadena único en el programa. A continuación, una vez que haya encontrado el nodo de sintaxis, obtenga la información de tipo de ese nodo del modelo semántico. Agregue el código siguiente al método `Main`:

[!code-csharp[Find the namespace symbol for the only using](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#7 "Find the namespace symbol for the only using")]

La estructura <xref:Microsoft.CodeAnalysis.TypeInfo?displayProperty=nameWithType> incluye una propiedad <xref:Microsoft.CodeAnalysis.TypeInfo.Type?displayProperty=nameWithType> que permite el acceso a la información semántica sobre el tipo del literal. En este ejemplo, es el tipo `string`. Agregue una declaración que asigne esta propiedad a una variable local:

[!code-csharp[Find the semantic information about the string type](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#8 "Use the string literal to access the semantic information in the string type.")]

Para finalizar este tutorial, crearemos una consulta LINQ que crea una secuencia de todos los métodos públicos declarados en el tipo `string` que devuelven una `string`. Esta consulta es más compleja, así que la compilaremos línea a línea y, después, la volveremos a construir como una única consulta. El origen de esta consulta es la secuencia de todos los miembros declarados en el tipo `string`:

[!code-csharp[Access the sequence of members on the string type](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#9 "Access the sequence of members on the string type.")]

Esa secuencia de origen contiene todos los miembros, incluidas las propiedades y los campos, de modo que tiene que filtrarlos con el método <xref:System.Collections.Immutable.ImmutableArray%601.OfType%2A?displayProperty=nameWithType> para buscar los elementos que son objetos <xref:Microsoft.CodeAnalysis.IMethodSymbol?displayProperty=nameWithType>:

[!code-csharp[Filter the sequence to only methods](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#10 "Find the subset of the collection that is the methods.")]

A continuación, agregue otro filtro para devolver solo aquellos métodos que son públicos y devuelven una `string`:

[!code-csharp[Filter on return type and accessibility](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#11 "Find only the public methods that return a string.")]

Seleccione solo la propiedad name y solo los nombres distintos; para ello, elimine las sobrecargas:

[!code-csharp[find the distinct names.](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#12 "Use the string literal to access the semantic information in the string type.")]

También puede compilar la consulta completa con la sintaxis de consulta LINQ y, después, mostrar todos los nombres de método en la consola:

[!code-csharp[build and display the results of this query.](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#13 "Build and display the results of the query.")]

Compile y ejecute el programa. Debería ver la siguiente salida:

```output
Join
Substring
Trim
TrimStart
TrimEnd
Normalize
PadLeft
PadRight
ToLower
ToLowerInvariant
ToUpper
ToUpperInvariant
ToString
Insert
Replace
Remove
Format
Copy
Concat
Intern
IsInterned
Press any key to continue . . .
```

Ha usado la API semántica para buscar y mostrar información sobre los símbolos que forman parte de este programa.
