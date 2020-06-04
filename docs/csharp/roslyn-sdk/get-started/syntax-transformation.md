---
title: Introducción a la transformación de sintaxis (API de Roslyn)
description: Introducción para recorrer y consultar árboles de sintaxis.
ms.date: 06/01/2018
ms.custom: mvc
ms.openlocfilehash: 5879dfd6ed0a5f6465829eec496d10cfcfd07362
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202119"
---
# <a name="get-started-with-syntax-transformation"></a>Introducción a la transformación de sintaxis

Este tutorial se basa en conceptos y técnicas explorados en los tutoriales rápidos [Introducción al análisis de sintaxis](syntax-analysis.md) e [Introducción al análisis semántico](semantic-analysis.md). Si aún no lo ha hecho, debería completar esos tutoriales antes de comenzar con este.

En este tutorial rápido, se exploran las técnicas para crear y transformar árboles de sintaxis. En combinación con las técnicas que aprendió en los tutoriales anteriores, podrá crear la primera refactorización de línea de comandos.

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

## <a name="immutability-and-the-net-compiler-platform"></a>Inmutabilidad y .NET Compiler Platform

La **inmutabilidad** es un principio fundamental de .NET Compiler Platform. Las estructuras de datos inmutables no se pueden cambiar una vez creadas. Las estructuras de datos inmutables se pueden compartir y someter al análisis de varios consumidores al mismo tiempo sin riesgo alguno. No se corre el peligro de que la acción de un consumidor afecte a otro de manera impredecible. El analizador no necesita bloqueos u otras medidas de simultaneidad. Esta regla se aplica a los árboles de sintaxis, las compilaciones, los símbolos, los modelos semánticos y cualquier otra estructura de datos que encuentre. En lugar de modificar las estructuras existentes, las API crean nuevos objetos según las diferencias especificadas en los antiguos. Este concepto se aplica a los árboles de sintaxis para crear nuevos árboles que usan transformaciones.

## <a name="create-and-transform-trees"></a>Creación y transformación de árboles

Elija una de las dos estrategias para las transformaciones de sintaxis. Los patrones de diseño **Factory Method** son útiles cuando se buscan nodos específicos para reemplazar, o ubicaciones específicas donde desea insertar el nuevo código. Las **reescrituras** son la mejor opción si desea buscar patrones de código que se van a reemplazar en todo un proyecto.

### <a name="create-nodes-with-factory-methods"></a>Creación de nodos con patrones de diseño Factory Method

En la primera transformación de sintaxis se muestran los patrones de diseño Factory Method. Va a reemplazar una instrucción `using System.Collections;` por una instrucción `using System.Collections.Generic;`. En este ejemplo se muestra cómo crear objetos <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxNode?displayProperty=nameWithType> mediante los patrones de diseño Factory Method <xref:Microsoft.CodeAnalysis.CSharp.SyntaxFactory?displayProperty=nameWithType>. Para cada tipo de **nodo**, **token** o **curiosidades** hay un patrón Factory Method que crea una instancia de ese tipo. Creará árboles de sintaxis mediante la composición de nodos jerárquicamente de abajo arriba. Luego, transformará el programa existente para reemplazar los nodos existentes por el nuevo árbol que ha creado.

Inicie Visual Studio y cree un proyecto de **Stand-Alone Code Analysis Tool** (Herramienta de análisis de código independiente) de C#. En Visual Studio, elija **Archivo** > **Nuevo** > **Proyecto** para mostrar el cuadro de diálogo Nuevo proyecto. En **Visual C#**  > **Extensibilidad**, elija **Stand-Alone Code Analysis Tool** (Herramienta de análisis de código independiente). Este tutorial rápido tiene dos proyectos de ejemplo, así que llame a la solución **SyntaxTransformationQuickStart** y al proyecto **ConstructionCS**. Haga clic en **Aceptar**.

Este proyecto usa los métodos de clase <xref:Microsoft.CodeAnalysis.CSharp.SyntaxFactory?displayProperty=nameWithType> para construir un <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax?displayProperty=nameWithType> que representa el espacio de nombres `System.Collections.Generic`.

Agregue esta directiva a la parte superior de `Program.cs`.

[!code-csharp[import the SyntaxFactory class](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#StaticUsings "import the Syntax Factory class and the System.Console class")]

Creará **nodos de sintaxis de nombre** para generar el árbol que representa la instrucción `using System.Collections.Generic;`. <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax> es la clase base para los cuatro tipos de nombres que aparecen en C#. Junte estos cuatro tipos de nombres para crear cualquier nombre que pueda aparecer en el lenguaje C#:

* <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax?displayProperty=nameWithType>, que representa los nombres de identificador único simple, como `System` y `Microsoft`.
* <xref:Microsoft.CodeAnalysis.CSharp.Syntax.GenericNameSyntax?displayProperty=nameWithType>, que representa un nombre de tipo o método genérico, como `List<int>`.
* <xref:Microsoft.CodeAnalysis.CSharp.Syntax.QualifiedNameSyntax?displayProperty=nameWithType>, que representa un nombre completo del formulario `<left-name>.<right-identifier-or-generic-name>`, como `System.IO`.
* <xref:Microsoft.CodeAnalysis.CSharp.Syntax.AliasQualifiedNameSyntax?displayProperty=nameWithType>, que representa un nombre que usa un alias de ensamblado externo, como `LibraryV2::Foo`.

Use el método <xref:Microsoft.CodeAnalysis.CSharp.SyntaxFactory.IdentifierName(System.String)> para crear un nodo <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax>. Agregue el código siguiente al método `Main` en `Program.cs`:

[!code-csharp[create the system identifier](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#CreateIdentifierName "Create and display the system name identifier")]

El código anterior crea un objeto <xref:Microsoft.CodeAnalysis.CSharp.Syntax.IdentifierNameSyntax> y lo asigna a la variable `name`. Muchas de las API de Roslyn devuelven clases base para que sea más fácil trabajar con tipos relacionados. La variable `name`, <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax>, puede volver a usarse al crear <xref:Microsoft.CodeAnalysis.CSharp.Syntax.QualifiedNameSyntax>. No use la inferencia de tipo al crear el ejemplo. Podrá automatizar ese paso en este proyecto.

Ha creado el nombre. Ahora, es el momento de crear más nodos en el árbol mediante la creación de <xref:Microsoft.CodeAnalysis.CSharp.Syntax.QualifiedNameSyntax>. El nuevo árbol usa `name` como parte izquierda del nombre, y un nuevo <xref:Microsoft.CodeAnalysis.CSharp.Syntax.IdentifierNameSyntax> para el espacio de nombres `Collections` como parte derecha de <xref:Microsoft.CodeAnalysis.CSharp.Syntax.QualifiedNameSyntax>. Agrega el código siguiente a `program.cs`:

[!code-csharp[create the collections identifier](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#CreateQualifiedIdentifierName "Build the System.Collections identifier")]

Vuelva a ejecutar el código y observe los resultados. Está creando un árbol de nodos que representa código. Continuará con este patrón para compilar <xref:Microsoft.CodeAnalysis.CSharp.Syntax.QualifiedNameSyntax> para el espacio de nombres `System.Collections.Generic`. Agrega el código siguiente a `Program.cs`:

[!code-csharp[create the full identifier](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#CreateFullNamespace "Build the System.Collections.Generic identifier")]

Ejecute el programa de nuevo para ver si ha creado el árbol para agregar el código.

### <a name="create-a-modified-tree"></a>Creación de un árbol modificado

Ha creado un pequeño árbol de sintaxis que contiene una instrucción. Las API para crear nuevos nodos son la opción correcta para crear instrucciones únicas u otros bloques de código pequeño. Sin embargo, para generar bloques más grandes de código, debe usar los métodos que reemplazan nodos o insertan nodos en un árbol existente. Recuerde que los árboles de sintaxis son inmutables. La **API de sintaxis** no proporciona ningún mecanismo para modificar un árbol de sintaxis existente después de la construcción. En su lugar, proporciona métodos que generan nuevos árboles en función de los cambios en los existentes. Se han definido métodos `With*` en clases concretas que se derivan de <xref:Microsoft.CodeAnalysis.SyntaxNode> o en métodos de extensión declarados en la clase <xref:Microsoft.CodeAnalysis.SyntaxNodeExtensions>. Estos métodos crean un nuevo nodo al aplicar cambios a las propiedades del elemento secundario de un nodo existente. Además, el método de extensión <xref:Microsoft.CodeAnalysis.SyntaxNodeExtensions.ReplaceNode%2A> se puede utilizar para reemplazar un nodo descendiente en un subárbol. Este método también actualiza el elemento primario para que apunte al formulario secundario recién creado y repite este proceso por todo el árbol: un proceso conocido como _volver a hacer girar el árbol_.

El siguiente paso consiste en crear un árbol que representa todo un programa (pequeño) y, a continuación, modificarlo. Agregue el siguiente código al principio de la clase `Program`:

[!code-csharp[create a parse tree](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#DeclareSampleCode "Create a tree that represents a small program")]

> [!NOTE]
> El código de ejemplo utiliza el espacio de nombres `System.Collections` y no el espacio de nombres `System.Collections.Generic`.

A continuación, agregue el código siguiente a la parte inferior del método `Main` para analizar el texto y crear un árbol:

[!code-csharp[create a parse tree](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#CreateParseTree "Create a tree that represents a small program")]

En este ejemplo se utiliza el método <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax.WithName(Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax)?displayProperty=NameWithType> para reemplazar el nombre de un nodo <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax> por el que se creó en el código anterior.

Cree un nuevo nodo <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax> mediante el método <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax.WithName(Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax)> para actualizar el nombre `System.Collections` con el nombre que creó en el código anterior. Agregue el siguiente código en la parte inferior del método `Main`:

[!code-csharp[create a new subtree](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#BuildNewUsing "Create the subtree with the replaced namespace")]

Ejecute el programa y observe con detenimiento el resultado. `newusing` todavía no se ha colocado en el árbol de la raíz. No se ha modificado el árbol original.

Agregue el siguiente código utilizando el método de extensión <xref:Microsoft.CodeAnalysis.SyntaxNodeExtensions.ReplaceNode%2A> para crear un nuevo árbol. El nuevo árbol es el resultado de reemplazar la importación existente por el nodo `newUsing` actualizado. Asigne este nuevo árbol a la variable `root` existente:

[!code-csharp[create a new root tree](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#TransformTree "Create the transformed root tree with the replaced namespace")]

Ejecute el programa otra vez. Esta vez el árbol importa correctamente el espacio de nombres `System.Collections.Generic`.

### <a name="transform-trees-using-syntaxrewriters"></a>Transformación de árboles mediante `SyntaxRewriters`

Los métodos `With*` y <xref:Microsoft.CodeAnalysis.SyntaxNodeExtensions.ReplaceNode%2A> proporcionan un medio cómodo para transformar ramas individuales de un árbol de sintaxis. La clase <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter?displayProperty=nameWithType> realiza varias transformaciones en un árbol de sintaxis. La clase <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter?displayProperty=nameWithType> es una subclase de <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor%601?displayProperty=nameWithType>. <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter> aplica una transformación a un tipo específico de <xref:Microsoft.CodeAnalysis.SyntaxNode>. Puede aplicar transformaciones a varios tipos de objetos <xref:Microsoft.CodeAnalysis.SyntaxNode> dondequiera que aparezcan en un árbol de sintaxis. En el segundo proyecto de este tutorial rápido se crea una refactorización de línea de comandos que quita tipos explícitos en declaraciones de variable local en cualquier lugar en que pudiera utilizarse una inferencia de tipos.

Cree un proyecto de **Stand-Alone Code Analysis Tool** (Herramienta de análisis de código independiente) de C#. En Visual Studio, haga clic en el nodo de la solución `SyntaxTransformationQuickStart`. Elija **Agregar** > **Nuevo proyecto** para mostrar el **cuadro de diálogo Nuevo proyecto**. En **Visual C#**  > **Extensibilidad**, elija **Stand-Alone Code Analysis Tool** (Herramienta de análisis de código independiente). Proporcione un nombre al proyecto `TransformationCS` y haga clic en Aceptar.

El primer paso es crear una clase que se derive de <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter> para realizar las transformaciones. Agregue un nuevo archivo de clase al proyecto. En Visual Studio, elija **Proyecto** > **Agregar clase...** . En el cuadro de diálogo **Agregar nuevo elemento**, escriba `TypeInferenceRewriter.cs` como nombre de archivo.

Agregue las siguientes directivas using al archivo `TypeInferenceRewriter.cs`:

[!code-csharp[add necessary usings](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#AddUsings "Add required usings")]

A continuación, haga que la clase `TypeInferenceRewriter` se extienda a la clase <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter>:

[!code-csharp[add base class](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#BaseClass "Add base class")]

Agregue el código siguiente para declarar un campo privado de solo lectura para que contenga un <xref:Microsoft.CodeAnalysis.SemanticModel> e inicializarlo en el constructor. Necesitará este campo más adelante para determinar donde se puede usar la inferencia de tipos:

[!code-csharp[initialize members](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#Construction "Declare and initialize member variables")]

Invalide el método <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter.VisitLocalDeclarationStatement(Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax)>:

```csharp
public override SyntaxNode VisitLocalDeclarationStatement(LocalDeclarationStatementSyntax node)
{

}
```

> [!NOTE]
> Muchas de las API de Roslyn declaran tipos de valor devuelto que son clases base de los tipos en tiempo de ejecución reales devueltos. En muchos escenarios, un tipo de nodo puede reemplazarse por otro tipo de nodo por completo, e incluso eliminarse. En este ejemplo, el método <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter.VisitLocalDeclarationStatement(Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax)> devuelve un <xref:Microsoft.CodeAnalysis.SyntaxNode>, en lugar del tipo derivado de <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax>. Este sistema de reescritura devuelve un nuevo nodo <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax> basado en el existente.

Este tutorial rápido controla las declaraciones de variable locales. Puede ampliarlo para otras declaraciones como bucles `foreach`, bucles `for`, expresiones LINQ y expresiones lambda. Además, este sistema de reescritura transformará solo las declaraciones de la forma más sencilla:

```csharp
Type variable = expression;
```

Si desea explorar por su cuenta, considere la posibilidad de extender el ejemplo finalizado para estos tipos de declaraciones de variable:

```csharp
// Multiple variables in a single declaration.
Type variable1 = expression1,
     variable2 = expression2;
// No initializer.
Type variable;
```

Agregue el código siguiente al cuerpo del método `VisitLocalDeclarationStatement` para que omita la reescritura de estas formas de declaraciones:

[!code-csharp[exclude other declarations](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#Exclusions "Exclude variables declarations not processed by this sample")]

El método indica que no se realiza la reescritura mediante la devolución del parámetro `node` sin modificar. Si ninguna de esas expresiones `if` son verdaderas, el nodo representa una declaración posible con la inicialización. Agregue estas instrucciones para extraer el nombre del tipo especificado en la declaración y asócielo con el campo <xref:Microsoft.CodeAnalysis.SemanticModel> para obtener un símbolo de tipo:

[!code-csharp[extract type name](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#ExtractTypeSymbol "Extract the type name specified by the declaration")]

Ahora, agregue esta instrucción para enlazar la expresión de inicializador:

[!code-csharp[bind initializer](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#BindInitializer "Bind the initializer expressions")]

Por último, agregue la siguiente instrucción `if` para reemplazar el nombre de tipo existente por la palabra clave `var` si el tipo de la expresión de inicializador coincide con el tipo especificado:

[!code-csharp[ReplaceNode](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#ReplaceNode "Replace the initializer node")]

El atributo condicional es necesario porque la declaración puede convertir la expresión de inicializador en una interfaz o clase base. Si se desea, los tipos del lado izquierdo y derecho de la asignación no coinciden. El hecho de quitar el tipo explícito en estos casos también cambiaría la semántica de un programa. `var` se especifica como un identificador en lugar de una palabra clave porque `var` es una palabra clave contextual. Las curiosidades iniciales y finales (espacios en blanco) se transfieren desde el nombre de tipo anterior a la palabra clave `var` para mantener el espacio en blanco vertical y la sangría. Es más fácil utilizar `ReplaceNode` en lugar de `With*` para transformar el <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax> porque el nombre de tipo es realmente el descendiente del elemento secundario de la instrucción de declaración.

Ha terminado el `TypeInferenceRewriter`. Ahora vuelva a su archivo `Program.cs` para finalizar el ejemplo. Cree una prueba <xref:Microsoft.CodeAnalysis.Compilation> y obtenga <xref:Microsoft.CodeAnalysis.SemanticModel> de ella. Use ese <xref:Microsoft.CodeAnalysis.SemanticModel> para probar su `TypeInferenceRewriter`. Llevará a cabo este último paso. Mientras tanto, declare una variable de marcador de posición que represente la compilación de prueba:

[!code-csharp[DeclareCompilation](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/Program.cs#DeclareTestCompilation "Declare the test compilation")]

Después de un momento de pausa, debería aparecer un subrayado ondulado de error que indica que no existe ningún método `CreateTestCompilation`. Presione **CTRL+Punto** para abrir la bombilla y, a continuación, presione Entrar para invocar el comando **Generar código auxiliar del método**. Este comando generará un código auxiliar para el método `CreateTestCompilation` en la clase `Program`. Podrá volver a rellenar este método más adelante:

![Generación de método de C# a partir del uso](./media/syntax-transformation/generate-from-usage.png)

Escriba el código siguiente para recorrer en iteración cada <xref:Microsoft.CodeAnalysis.SyntaxTree> en la prueba <xref:Microsoft.CodeAnalysis.Compilation>. Para cada una de ellas, inicialice un nuevo `TypeInferenceRewriter` con el <xref:Microsoft.CodeAnalysis.SemanticModel> para ese árbol:

[!code-csharp[IterateTrees](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/Program.cs#IterateTrees "Iterate all the source trees in the test compilation")]

Dentro de la instrucción `foreach` que ha creado, agregue el código siguiente para realizar la transformación en cada árbol de origen. Este código escribe condicionalmente el nuevo árbol transformado si se hicieron modificaciones. El sistema de reescritura sólo debe modificar un árbol si encuentra una o más declaraciones de variables locales que pudieron simplificarse mediante la inferencia de tipos:

[!code-csharp[TransformTrees](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/Program.cs#TransformTrees "Transform and save any trees that are modified by the rewriter")]

Debería ver los subrayados ondulados bajo el código `File.WriteAllText`. Seleccione la bombilla y agregue la instrucción `using System.IO;` necesaria.

Casi ha terminado. Queda un último paso: crear una prueba <xref:Microsoft.CodeAnalysis.Compilation>. Puesto que no ha utilizado ninguna inferencia de tipos durante este tutorial rápido, habría sido un caso de prueba perfecto. Desafortunadamente, la creación de una compilación desde un archivo de proyecto de C# queda fuera del ámbito de este tutorial. Pero afortunadamente, si ha seguido las instrucciones con cuidado, hay esperanza. Reemplace el contenido del método `CreateTestCompilation` con el código siguiente. Crea una compilación de prueba que casualmente coincide con el proyecto descrito en este tutorial rápido:

[!code-csharp[CreateTestCompilation](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/Program.cs#CreateTestCompilation "Create a test compilation using the code written for this quickstart.")]

Cruce los dedos y ejecute el proyecto. En Visual Studio, elija **Depurar** > **Iniciar depuración**. Visual Studio le debería notificar que los archivos de su proyecto han cambiado. Haga clic en "**Sí a todo**" para volver a cargar los archivos modificados. Examínelos para observar su genialidad. Observe que el código se ve mucho más limpio sin todos los especificadores de tipo explícitos y redundantes.

¡Enhorabuena! Ha usado las **API de compilador** para escribir su propia refactorización que busca en todos los archivos de un proyecto C# ciertos patrones sintácticos, analiza la semántica del código fuente que coincide con esos patrones y la transforma. ¡Ya es oficialmente un autor de refactorización!
