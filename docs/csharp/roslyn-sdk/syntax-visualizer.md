---
title: Explorar código con el Visualizador de sintaxis Roslyn en Visual Studio
description: El Visualizador de sintaxis proporciona una herramienta visual para explorar los modelos que genera el SDK de .NET Compiler Platform para el código.
ms.date: 03/07/2018
ms.custom: mvc, vs-dotnet
ms.openlocfilehash: a911a99e78ad5a5f4c6771b91a3c541b1812d67c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167579"
---
# <a name="explore-code-with-the-roslyn-syntax-visualizer-in-visual-studio"></a>Explorar código con el Visualizador de sintaxis Roslyn en Visual Studio

En este artículo se ofrece información general de la herramienta Visualizador de sintaxis que se incluye como parte del SDK de .NET Compiler Platform ("Roslyn"). El Visualizador de sintaxis es una ventana de herramientas con la que puede inspeccionar y explorar árboles de sintaxis. Es una herramienta esencial para comprender los modelos de código que quiere analizar. También es útil para la depuración al desarrollar sus propias aplicaciones con el SDK de .NET Compiler Platform (“Roslyn”). Abra esta herramienta cuando vaya a crear sus primeros analizadores. Con el visualizador comprenderá los modelos usados por las API. También puede usar herramientas como [SharpLab](https://sharplab.io) o [LINQPad](https://www.linqpad.net/) para inspeccionar el código y comprender los árboles de sintaxis.

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

Para familiarizarse con los conceptos usados en el SDK de .NET Compiler Platform, lea el artículo [introductorio](compiler-api-model.md). Proporciona una introducción a los árboles de sintaxis, los nodos, los tokens y algunas curiosidades.

## <a name="syntax-visualizer"></a>Visualizador de sintaxis

**Syntax Visualizer** permite inspeccionar el árbol de sintaxis del archivo de código de C# o Visual Basic en la ventana del editor activo actual en el IDE de Visual Studio. El visualizador se puede iniciar haciendo clic en **Vista** > **Other Windows (Otras ventanas)**  > **Syntax Visualizer (Visualizador de sintaxis)** .  También puede usar la barra de herramientas **Inicio rápido** en la esquina superior derecha. Escriba "syntax" y se mostrará el comando para abrir el **Visualizador de sintaxis**.

Este comando abre el Visualizador de sintaxis como una ventana de herramientas flotante. Si no tiene abierta ninguna ventana de editor de código, la presentación está en blanco, tal como se muestra en esta imagen.

![Ventana de la herramienta Visualizador de sintaxis](media/syntax-visualizer/syntax-visualizer.png)

Acople esta ventana de herramienta en una ubicación cómoda dentro de Visual Studio, como por ejemplo, en el lado izquierdo. El visualizador muestra información sobre el archivo de código actual.

Cree un nuevo proyecto con los comandos **Archivo** > **Nuevo proyecto**. Puede crear un proyecto de Visual Basic o C#. Cuando Visual Studio abre el principal archivo de código para este proyecto, el visualizador muestra el árbol de sintaxis correspondiente. Puede abrir cualquier archivo de C# o Visual Basic existente en esta instancia de Visual Studio y el visualizador mostrará el árbol de sintaxis de ese archivo. Si tiene varios archivos de código abiertos dentro de Visual Studio, el visualizador muestra el árbol de sintaxis para el archivo de código activo (el archivo de código que tiene el foco de teclado).

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[C#](#tab/csharp)

![Visualizar un árbol de sintaxis de C#](media/syntax-visualizer/visualize-csharp.png)

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

![Visualización de un árbol de sintaxis de Visual Basic](media/syntax-visualizer/visualize-visual-basic.png)

---

Como se muestra en las imágenes anteriores, la ventana de herramientas del visualizador muestra el árbol de sintaxis en la parte superior y una cuadrícula de propiedades en la parte inferior. La cuadrícula de propiedades muestra las propiedades del elemento que está seleccionado actualmente en el árbol, incluido el *Tipo* de .NET y la *Variante* (SyntaxKind) del elemento.

Los árboles de sintaxis incluyen tres tipos de elementos: *nodos*, *tokens* y *curiosidades*. Encontrará más información sobre estos tipos en el artículo [Trabajar con sintaxis](work-with-syntax.md). Los elementos de cada tipo se representan mediante un color diferente. Haga clic en el botón “Leyenda” para saber más sobre los colores usados.

Cada elemento del árbol también muestra su propio **intervalo**. El **intervalo** está comprendido por los índices (la posición inicial y la final) de ese nodo en el archivo de texto.  En el anterior ejemplo de C#, el token “UsingKeyword [0..5)” seleccionado tiene un **intervalo** de cinco caracteres de ancho [0..5). La notación “[.)” significa que el índice inicial forma parte del intervalo, pero el índice final no.

Se puede navegar por el árbol de dos maneras:

* Expandir el árbol o hacer clic en él. El visualizador selecciona automáticamente el texto correspondiente al intervalo de este elemento en el editor de código.
* Hacer clic en el texto o seleccionarlo en el editor de código. En el ejemplo de Visual Basic anterior, si selecciona la línea que contiene "Module Module1" en el editor de código, el visualizador navega automáticamente al nodo ModuleStatement correspondiente en el árbol.

El visualizador resalta el elemento en el árbol cuyo intervalo coincide mejor con el intervalo del texto seleccionado en el editor.

El visualizador actualiza el árbol para coincidir con las modificaciones en el archivo de código activo. Agregue una llamada a `Console.WriteLine()` dentro de `Main()`. A medida que escribe, el visualizador actualiza el árbol.

Pare de escribir en cuanto escriba `Console.`. Verá que el árbol ha marcado en rosa algunos elementos. En este momento, hay errores (también denominados “diagnósticos”) en el código escrito. Estos errores se adjuntan a los nodos, los tokens y las curiosidades en el árbol de sintaxis. El visualizador muestra qué elementos tienen errores adjuntados a ellos resaltando el fondo en color rosa. Puede inspeccionar los errores en cualquier elemento marcado en rosa si desplaza el puntero sobre el elemento. El visualizador muestra solo los errores sintácticos (los errores relacionados con la sintaxis del código escrito) y no muestra los errores semánticos.

## <a name="syntax-graphs"></a>Gráficos de sintaxis

Haga clic con el botón derecho en cualquier elemento del árbol y haga clic en **View Directed Syntax Graph** (Ver gráfico de sintaxis dirigido).

# <a name="c"></a>[C#](#tab/csharp)

El visualizador muestra una representación gráfica del subárbol cuya raíz se encuentra en el elemento seleccionado. Siga estos pasos para el nodo **MethodDeclaration** correspondiente al método `Main()` en el ejemplo de C#. El visualizador muestra un gráfico de sintaxis que tiene este aspecto:

![Ver un gráfico de sintaxis de C#](media/syntax-visualizer/csharp-syntax-graph.png)

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

Pruebe lo mismo con el nodo **SubBlock** correspondiente al método `Main()` en el ejemplo de Visual Basic anterior. El visualizador muestra un gráfico de sintaxis que tiene este aspecto:

![Visualización de un gráfico de sintaxis de Visual Basic](media/syntax-visualizer/visual-basic-syntax-graph.png)

---

El visor de gráficos de sintaxis tiene una opción para mostrar una leyenda para su esquema de color. También puede pasar el puntero sobre determinados elementos en el gráfico de sintaxis para ver las propiedades correspondientes a ese elemento.

Puede ver gráficos de sintaxis de elementos diferentes en el árbol de manera repetida y los gráficos siempre se mostrarán en la misma ventana dentro de Visual Studio. Puede acoplar esta ventana en una ubicación cómoda en Visual Studio para no tener que cambiar entre pestañas para ver un nuevo gráfico de sintaxis. La parte inferior, debajo de las ventanas del editor de código, suele resultar cómoda.

Este es el diseño de acoplamiento que se usa con la ventana del visualizador y la ventana del gráfico de sintaxis:

![Un diseño de acoplamiento para la ventana del gráfico de sintaxis y del visualizador](media/syntax-visualizer/docking-layout.png)

Otra opción consiste en colocar la ventana del gráfico de sintaxis en un segundo monitor, en una configuración de monitor dual.

## <a name="inspecting-semantics"></a>Semántica de inspección

El Visualizador de sintaxis permite realizar una inspección rudimentaria de símbolos e información semántica. Escriba `double x = 1 + 1;` dentro de Main() en el ejemplo de C#. Después, seleccione la expresión `1 + 1` en la ventana del editor de código. El visualizador resalta el nodo **AddExpression** en el visualizador. Haga clic con el botón derecho en **AddExpression** y elija **View Symbol (if any)** [Ver símbolo (si existe)]. Tenga en cuenta que la mayoría de los elementos de menú tienen el calificador "si existe". El Visualizador de sintaxis inspecciona las propiedades de un nodo, incluidas las propiedades que es posible que no estén presentes para todos los nodos.

La cuadrícula de propiedades del visualizador se actualiza tal como se muestra en la figura siguiente: El símbolo de la expresión es un símbolo **SynthesizedIntrinsicOperatorSymbol** con **Kind = Method**.

![Propiedades de símbolo](media/syntax-visualizer/symbol-properties.png)

Intente **View TypeSymbol (if any)** [Ver TypeSymbol (si existe)] para el mismo nodo **AddExpression**. La cuadrícula de propiedades del visualizador se actualiza como se muestra en esta imagen, que indica que el tipo de la expresión seleccionada es `Int32`.

![Propiedades de TypeSymbol](media/syntax-visualizer/type-symbol-properties.png)

Intente **View Converted TypeSymbol (if any)** [Ver TypeSymbol convertido (si existe)] para el mismo nodo **AddExpression**. La cuadrícula de propiedades se actualiza para indicar que, aunque el tipo de la expresión es `Int32`, el tipo convertido de la expresión es `Double`, como se muestra en esta imagen. Este nodo incluye información de símbolo de tipo convertido porque la expresión `Int32` se produce en un contexto donde se debe convertir a `Double`. Esta conversión satisface el tipo `Double` especificado para la variable `x` en el lado izquierdo del operador de asignación.

![Propiedades de TypeSymbol convertido](media/syntax-visualizer/converted-type-symbol-properties.png)

Por último, intente **View Constant Value (if any)** [Ver valor de constante (si existe)] para el mismo nodo **AddExpression**. La cuadrícula de propiedades muestra que el valor de la expresión es una constante en tiempo de compilación con el valor `2`.

![Un valor de constante](media/syntax-visualizer/constant-value.png)

El ejemplo anterior también se puede replicar en Visual Basic. Escriba `Dim x As Double = 1 + 1` en un archivo de Visual Basic. Seleccione la expresión `1 + 1` en la ventana del editor de código. El visualizador resalta el nodo **AddExpression** correspondiente en el visualizador. Repita los pasos anteriores para **AddExpression** y deberían mostrarse resultados idénticos.

Examine más código en Visual Basic. Actualice el archivo principal de Visual Basic con este código:

```vb
Imports C = System.Console

Module Program
    Sub Main(args As String())
        C.WriteLine()
    End Sub
End Module
```

Este código incluye un alias llamado `C` que se asigna al tipo `System.Console` en la parte superior del archivo y usa este alias en `Main()`. Seleccione el uso de este alias, `C` en `C.WriteLine()`, dentro del método `Main()`. El visualizador selecciona el nodo **IdentifierName** correspondiente en el visualizador. Haga clic con el botón derecho en este nodo y elija **View Symbol (if any)** [Ver símbolo (si existe)]. La cuadrícula de propiedades indica que este identificador está enlazado al tipo `System.Console` tal como se muestra en esta imagen:

![Propiedades de símbolo](media/syntax-visualizer/symbol-visual-basic.png)

Intente **View AliasSymbol (if any)** [Ver AliasSymbol (si existe)] para el mismo nodo **IdentifierName**. La cuadrícula de propiedades indica que el identificador es un alias con el nombre `C` que está enlazado al destino `System.Console`. En otras palabras, la cuadrícula de propiedades proporciona información sobre el **AliasSymbol** correspondiente al identificador `C`.

![Propiedades de AliasSymbol](media/syntax-visualizer/alias-symbol.png)

Inspeccione el símbolo correspondiente a cualquier tipo, método o propiedad declarados. Seleccione el nodo correspondiente en el visualizador y haga clic en **View Symbol (if any)** [Ver símbolo (si existe)]. Seleccione el método `Sub Main()`, incluido el cuerpo del método. Haga clic en **View Symbol (if any)** [Ver símbolo (si existe)] para el nodo **SubBlock** correspondiente en el visualizador. La cuadrícula de propiedades muestra que **MethodSymbol** para este nodo **SubBlock** tiene el nombre `Main` con el tipo de valor devuelto `Void`.

![Ver símbolo de una declaración de método](media/syntax-visualizer/method-symbol.png)

Los ejemplos de Visual Basic anteriores se pueden replicar fácilmente en C#. Escriba `using C = System.Console;` en lugar de `Imports C = System.Console` para el alias. Los pasos anteriores en C# producen resultados idénticos en la ventana del visualizador.

Las operaciones de inspección semántica solo están disponibles en los nodos. No están disponibles en tokens o curiosidades. No todos los nodos tienen información semántica interesante que inspeccionar. Cuando un nodo no tiene información semántica interesante, al hacer clic en **View \* Symbol (if any)** [Ver símbolo (si existe)] se muestra una cuadrícula de propiedades en blanco.

Puede leer más sobre las API para realizar análisis semánticos en el documento introductorio [Trabajar con semántica](work-with-semantics.md).

## <a name="closing-the-syntax-visualizer"></a>Cerrar el Visualizador de sintaxis

Puede cerrar la ventana del visualizador cuando no esté usándolo para examinar el código fuente. Syntax Visualizer se actualiza a medida que navega por el código, y modifica o cambia el código fuente. Puede distraerse cuando no esté usándolo.
