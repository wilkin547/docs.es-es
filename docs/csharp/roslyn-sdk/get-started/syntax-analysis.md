---
title: Introducción al análisis de sintaxis (API de Roslyn)
description: Introducción para recorrer y consultar árboles de sintaxis.
ms.date: 02/05/2018
ms.custom: mvc
ms.openlocfilehash: 22d1303c9daa2ae35cf130b0c857cd7a5efdbe76
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78240524"
---
# <a name="get-started-with-syntax-analysis"></a>Introducción al análisis de sintaxis

En este tutorial, explorará la **API de sintaxis**. La API de sintaxis proporciona acceso a las estructuras de datos que describen un programa de C# o Visual Basic. Estas estructuras de datos tienen suficientes detalles para representar completamente un programa de cualquier tamaño. Estas estructuras pueden describir programas completos que se compilen y ejecuten correctamente. También pueden describir programas incompletos, conforme los escribe, en el editor.

Para habilitar esta expresión completa, las estructuras de datos y las API que constituyen la API de sintaxis son necesariamente complejas. Empecemos con el aspecto de la estructura de datos para el programa típico “Hola mundo”:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

Mire el texto del programa anterior. Reconoce elementos conocidos. Todo el texto representa un único archivo de código fuente o una **unidad de compilación**. Las tres primeras líneas del archivo de código fuente son **directivas using**. El código fuente restante se encuentra en una **declaración de espacio de nombres**. La declaración de espacio de nombres contiene una **declaración de clase** secundaria. La declaración de clase contiene una **declaración de método**.

La API de sintaxis crea una estructura de árbol y la raíz representa la unidad de compilación. Los nodos del árbol representan las directivas using, la declaración del espacio de nombres y todos los demás elementos del programa. La estructura de árbol continúa hasta los niveles inferiores: la cadena "Hello World!" es un **token de literal de cadena** que es un descendiente de un **argumento**. La API de sintaxis proporciona acceso a la estructura del programa. Puede consultar los procedimientos de código concretos, recorrer el árbol completo para entender el código y crear árboles al modificar el árbol existente.

Esa descripción breve proporciona información general sobre el tipo de información accesible mediante la API de sintaxis. La API de sintaxis no es nada más que una API formal que describe las construcciones de código que ya conoce de C#. Entre las funcionalidades completas, se incluye información sobre cómo se da formato al código, incluidos los saltos de línea, los espacios en blanco y la sangría. Con esta información, puede representar por completo el código tal y como lo escriben y leen los programadores humanos o el compilador. Con esta estructura, puede interactuar con el código fuente de forma muy significativa. Ya no son cadenas de texto, sino datos que representan la estructura de un programa de C#.

Para empezar, debe instalar el **SDK de .NET Compiler Platform**:

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

## <a name="understanding-syntax-trees"></a>Comprender los árboles de sintaxis

Use la API de sintaxis para cualquier análisis de la estructura del código de C#. La **API de sintaxis** expone los analizadores, los árboles de sintaxis y las utilidades para analizar y construir árboles de sintaxis. Es la forma en que busca en el código cualquier elemento de sintaxis específica o lee el código de un programa.

Un árbol de sintaxis es una estructura de datos que usan los compiladores de C# y Visual Basic para comprender los programas de C# y Visual Basic. Los árboles de sintaxis los produce el mismo analizador que se ejecuta cuando se compila un proyecto o un programador presiona F5. Los árboles de sintaxis tienen una fidelidad completa con el lenguaje; cada bit de información en un archivo de código se representa en el árbol. Escribir un árbol de sintaxis en texto reproduce el texto original exacto que se ha analizado. Los árboles de sintaxis también son **inmutables**; una vez creado un árbol de sintaxis, nunca se puede modificar. Los consumidores de los árboles pueden analizarlos en varios subprocesos, sin bloqueos ni otras medidas de simultaneidad, sabiendo que los datos nunca cambian. Puede usar las API para crear árboles que sean el resultado de modificar un árbol existente.

Los cuatro pilares principales de los árboles de sintaxis son los siguientes:

* La clase <xref:Microsoft.CodeAnalysis.SyntaxTree?displayProperty=nameWithType>, una instancia de lo que representa un árbol de análisis completo. <xref:Microsoft.CodeAnalysis.SyntaxTree> es una clase abstracta que tiene derivados específicos del lenguaje. Use los métodos de análisis de la clase <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxTree?displayProperty=nameWithType> (o <xref:Microsoft.CodeAnalysis.VisualBasic.VisualBasicSyntaxTree?displayProperty=nameWithType>) para analizar texto en C# o Visual Basic.
* La clase <xref:Microsoft.CodeAnalysis.SyntaxNode?displayProperty=nameWithType>, instancias de lo que representan las construcciones sintácticas como declaraciones, instrucciones, cláusulas y expresiones.
* La estructura <xref:Microsoft.CodeAnalysis.SyntaxToken?displayProperty=nameWithType>, que representa una palabra clave, identificador, operador o puntuación individuales.
* Por último, la estructura <xref:Microsoft.CodeAnalysis.SyntaxTrivia?displayProperty=nameWithType>, que representa sintácticamente bits de información insignificante, como el espacio en blanco entre tokens, las directivas de preprocesamiento y los comentarios.

La trivialidad, los tokens y los nodos se componen de forma jerárquica para formar un árbol que representa por completo todo lo que hay en un fragmento de código de Visual Basic o C#. Puede ver esta estructura mediante la ventana **Syntax Visualizer** (Visualizador de sintaxis). En Visual Studio, elija **Vista** > **Otras ventanas** > **Syntax Visualizer** (Visualizador de sintaxis). Por ejemplo, el archivo de código fuente de C# anterior examinado con **Syntax Visualizer** (Visualizador de sintaxis) tiene el mismo aspecto que en la siguiente ilustración:

**SyntaxNode**: azul | **SyntaxToken**: verde | **SyntaxTrivia**: rojo ![Archivo de código de C#](media/walkthrough-csharp-syntax-figure1.png)

Si se desplaza por esta estructura de árbol, podrá encontrar cualquier instrucción, expresión, token o bit de espacio en blanco en un archivo de código.

Aunque puede buscar cualquier elemento en un archivo de código mediante las API de sintaxis, la mayoría de los escenarios implican examinar pequeños fragmentos de código o buscar instrucciones o fragmentos concretos. Los dos ejemplos siguientes muestran usos típicos para examinar la estructura del código o buscar instrucciones únicas.

## <a name="traversing-trees"></a>Recorrer árboles

Puede examinar los nodos de un árbol de sintaxis de dos maneras. Puede recorrer el árbol para examinar cada nodo o puede consultar elementos o nodos concretos.

### <a name="manual-traversal"></a>Recorrido manual

Puede ver el código terminado de este ejemplo en [nuestro repositorio de GitHub](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/SyntaxQuickStart).

> [!NOTE]
> Los tipos de árbol de sintaxis usan la herencia para describir los diferentes elementos de sintaxis que son válidos en diferentes ubicaciones del programa. A menudo, usar estas API significa convertir propiedades o miembros de colección en tipos derivados concretos. En los ejemplos siguientes, la asignación y las conversiones son instrucciones independientes, con variables con tipo explícito. Puede leer el código para ver los tipos de valor devuelto de la API y el tipo de motor de ejecución de los objetos devueltos. En la práctica, es más habitual usar variables con tipo implícito y basarse en nombres de API para describir el tipo de los objetos que se examinan.

Cree un proyecto de **Stand-Alone Code Analysis Tool** (Herramienta de análisis de código independiente) de C#:

* En Visual Studio, elija **Archivo** > **Nuevo** > **Proyecto** para mostrar el cuadro de diálogo Nuevo proyecto.
* En **Visual C#**  > **Extensibilidad**, elija **Stand-Alone Code Analysis Tool** (Herramienta de análisis de código independiente).
* Asigne al proyecto el nombre "**SyntaxTreeManualTraversal**" y haga clic en Aceptar.

Va a analizar el programa básico "Hola mundo" mostrado anteriormente.
Agregue el texto para el programa Hola mundo como una constante en su clase `Program`:

[!code-csharp[Declare the program text](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#1 "Declare a constant string for the program text to analyze")]

A continuación, agregue el código siguiente para crear el **árbol de sintaxis** para el texto del código de la constante `programText`.  Agregue la línea siguiente al método `Main`:

[!code-csharp[Create the tree](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#2 "Create the syntax tree")]

Estas dos líneas crean el árbol y recuperan su nodo raíz. Ahora puede examinar los nodos del árbol. Agregue estas líneas al método `Main` para mostrar algunas de las propiedades del nodo raíz en el árbol:

[!code-csharp[Examine the root node](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#3 "Examine the root node")]

Ejecute la aplicación para ver lo que ha detectado el código sobre el nodo raíz de este árbol.

Normalmente, recorrería el árbol para obtener información sobre el código. En este ejemplo, analiza código que conoce para explorar las API. Agregue el código siguiente para examinar el primer miembro del nodo `root`:

[!code-csharp[Find the first member](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#4 "Find the first member")]

Ese miembro es una <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NamespaceDeclarationSyntax?displayProperty=nameWithType>. Representa todo lo que se incluye en el ámbito de la declaración `namespace HelloWorld`. Agregue el código siguiente para examinar qué nodos se declaran en el espacio de nombres `HelloWorld`:

[!code-csharp[Find the class declaration](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#5 "Find the class declaration")]

Ejecute el programa para ver lo que ha aprendido.

Ahora que sabe que la declaración es una <xref:Microsoft.CodeAnalysis.CSharp.Syntax.ClassDeclarationSyntax?displayProperty=nameWithType>, declare una nueva variable de ese tipo para examinar la declaración de clase. Esta clase solo contiene un miembro: el método `Main`. Agregue el código siguiente para buscar el método `Main` y conviértalo en una <xref:Microsoft.CodeAnalysis.CSharp.Syntax.MethodDeclarationSyntax?displayProperty=nameWithType>.

[!code-csharp[Find the main declaration](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#6 "Find the main declaration")]

El nodo de declaración de método contiene toda la información sintáctica sobre el método. Vamos a mostrar el tipo de valor devuelto del método `Main`, el número y los tipos de los argumentos, y el texto del cuerpo del método. Agregue el código siguiente:

[!code-csharp[Examine the syntax of the main method](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#7 "Display information about the main method")]

Ejecute el programa para ver toda la información que ya conoce sobre este programa:

```text
The tree is a CompilationUnit node.
The tree has 1 elements in it.
The tree has 4 using statements. They are:
        System
        System.Collections
        System.Linq
        System.Text
The first member is a NamespaceDeclaration.
There are 1 members declared in this namespace.
The first member is a ClassDeclaration.
There are 1 members declared in the Program class.
The first member is a MethodDeclaration.
The return type of the Main method is void.
The method has 1 parameters.
The type of the args parameter is string[].
The body text of the Main method follows:
        {
            Console.WriteLine("Hello, World!");
        }
```

### <a name="query-methods"></a>Métodos de consulta

Además de recorrer árboles, también puede explorar el árbol de sintaxis mediante los métodos de consulta definidos en <xref:Microsoft.CodeAnalysis.SyntaxNode?displayProperty=nameWithType>. Cualquier persona que conozca XPath debería conocer estos métodos. Puede usarlos con LINQ para buscar elementos rápidamente en un árbol. <xref:Microsoft.CodeAnalysis.SyntaxNode> tiene métodos de consulta como <xref:Microsoft.CodeAnalysis.SyntaxNode.DescendantNodes%2A>, <xref:Microsoft.CodeAnalysis.SyntaxNode.AncestorsAndSelf%2A> y <xref:Microsoft.CodeAnalysis.SyntaxNode.ChildNodes%2A>.

Puede usar estos métodos de consulta para buscar el argumento para el método `Main` como una alternativa a navegar por el árbol. Agregue el siguiente código en la parte inferior del método `Main`:

[!code-csharp[Query the tree for the arguments to Main](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#8 "Query the tree for the arguments to Main")]

La primera instrucción usa una expresión LINQ y el método <xref:Microsoft.CodeAnalysis.SyntaxNode.DescendantNodes%2A> para buscar el mismo parámetro que en el ejemplo anterior.

Ejecute el programa y compruebe que la expresión LINQ ha encontrado el mismo parámetro que se encuentra al navegar por el árbol de forma manual.

En el ejemplo, se usan instrucciones `WriteLine` para mostrar información sobre los árboles de sintaxis conforme se recorren. Puede obtener mucha más información si ejecuta el programa terminado en el depurador. Puede examinar más propiedades y métodos que forman parte del árbol de sintaxis creado para el programa Hola mundo.

## <a name="syntax-walkers"></a>Rastreadores de sintaxis

A menudo, quiere buscar todos los nodos de un tipo concreto en un árbol de sintaxis, por ejemplo, todas las declaraciones de propiedad de un archivo. Si extiende la clase <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker?displayProperty=nameWithType> e invalida el método <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor.VisitPropertyDeclaration(Microsoft.CodeAnalysis.CSharp.Syntax.PropertyDeclarationSyntax)>, se procesan todas las declaraciones de propiedad de un árbol de sintaxis sin conocer su estructura de antemano. <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> es un tipo determinado de <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor> que visita de forma recurrente un nodo y todos sus elementos secundarios.

En este ejemplo, se implementa un <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> que examina un árbol de sintaxis. Recopila directivas `using` que determina que no implementan un espacio de nombres `System`.

Cree un proyecto de **Stand-Alone Code Analysis Tool** (Herramienta de análisis de código independiente) de C# y asígnele el nombre “**SyntaxWalker**”.

Puede ver el código terminado de este ejemplo en [nuestro repositorio de GitHub](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/SyntaxQuickStart). El ejemplo de GitHub contiene los dos proyectos que se describen en este tutorial.

Como en el ejemplo anterior, puede definir una constante de cadena para que contenga el texto del programa que se va a analizar:

[!code-csharp[Define the code text to analyzer](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/Program.cs#1 "Define the program text to analyze")]

Este texto de origen contiene directivas `using` dispersas por cuatro ubicaciones diferentes: el nivel de archivo, en el espacio de nombres de nivel superior y en los dos espacios de nombres anidados. En este ejemplo, se destaca un escenario principal para usar la clase <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> en el código de la consulta. Sería complejo visitar todos los nodos del árbol de sintaxis raíz para buscar las declaraciones using. En su lugar, cree una clase derivada y reemplace el método al que se llama solo cuando el nodo actual del árbol sea una directiva using. El visitante no hace ningún trabajo en ningún otro tipo de nodo. Este método único examina todas las instrucciones `using` y compila una colección de los espacios de nombres que no están en el espacio de nombres `System`. Compile un <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> que examine todas las instrucciones `using`, pero solo las instrucciones `using`.

Ahora que ha definido el texto del programa, debe crear un `SyntaxTree` y obtener la raíz de ese árbol:

[!code-csharp[Create the Syntax tree and access the root](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/Program.cs#2 "Create the Syntax tree and access the root node.")]

A continuación, cree una clase. En Visual Studio, elija **Proyecto** > **Agregar nuevo elemento**. En el cuadro de diálogo **Agregar nuevo elemento**, escriba *UsingCollector.cs* como nombre de archivo.

Implemente la funcionalidad del visitante `using` en la clase `UsingCollector`. Para empezar, haga que la clase `UsingCollector` derive de <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker>.

[!code-csharp[Declare the base class for the using collector](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/UsingCollector.cs#3 "Declare the base class for the UsingCollector")]

Necesita almacenamiento para contener los nodos del espacio de nombres que está recopilando.  Declare una propiedad pública de solo lectura en la clase `UsingCollector`; use esta variable para almacenar los nodos <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax> que encuentre:

[!code-csharp[Declare storage for the using syntax nodes](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/UsingCollector.cs#4 "Declare storage for the using syntax nodes")]

La clase base, <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker>, implementa la lógica para visitar todos los nodos del árbol de sintaxis. La clase derivada reemplaza los métodos llamados por los nodos específicos que le interesan. En este caso, le interesa cualquier directiva `using`. Por tanto, debe invalidar el método <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor.VisitUsingDirective(Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax)>. El único argumento de este método es un objeto <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax?displayProperty=nameWithType>. Se trata de una ventaja importante de usar los visitantes: llaman a los métodos invalidados con argumentos que ya se han convertido al tipo de nodo concreto. La clase <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax?displayProperty=nameWithType> tiene una propiedad <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax.Name> que almacena el nombre del espacio de nombres que se va a importar. Es una <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax?displayProperty=nameWithType>. Agregue el código siguiente en la invalidación <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor.VisitUsingDirective(Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax)>:

[!code-csharp[Examine using nodes for the System namespace](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/UsingCollector.cs#5 "Examine all using nodes for the System namespace.")]

Como con el ejemplo anterior, ha agregado una variedad de instrucciones `WriteLine` para ayudar a comprender este método. Puede ver cuándo se llama y qué argumentos se le pasan cada vez.

Por último, debe agregar dos líneas de código para crear el `UsingCollector` y hacer que visite el nodo raíz y recopile todas las instrucciones `using`. A continuación, agregue un bucle `foreach` para que muestre todas las instrucciones `using` que encuentre el recopilador:

[!code-csharp[Create the UsingCollector and visit the root node.](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/Program.cs#6 "Create the UsingCollector and visit the root node.")]

Compile y ejecute el programa. Debería ver los siguientes resultados:

```console
        VisitUsingDirective called with System.
        VisitUsingDirective called with System.Collections.Generic.
        VisitUsingDirective called with System.Linq.
        VisitUsingDirective called with System.Text.
        VisitUsingDirective called with Microsoft.CodeAnalysis.
                Success. Adding Microsoft.CodeAnalysis.
        VisitUsingDirective called with Microsoft.CodeAnalysis.CSharp.
                Success. Adding Microsoft.CodeAnalysis.CSharp.
        VisitUsingDirective called with Microsoft.
                Success. Adding Microsoft.
        VisitUsingDirective called with System.ComponentModel.
        VisitUsingDirective called with Microsoft.Win32.
                Success. Adding Microsoft.Win32.
        VisitUsingDirective called with System.Runtime.InteropServices.
        VisitUsingDirective called with System.CodeDom.
        VisitUsingDirective called with Microsoft.CSharp.
                Success. Adding Microsoft.CSharp.
Microsoft.CodeAnalysis
Microsoft.CodeAnalysis.CSharp
Microsoft
Microsoft.Win32
Microsoft.CSharp
Press any key to continue . . .
```

¡Enhorabuena! Ha usado la **API de sintaxis** para buscar tipos concretos de instrucciones y declaraciones de C# en el código fuente de C#.
