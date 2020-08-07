---
title: 'Tutorial: Crear el primer analizador y la corrección de código'
description: En este tutorial se proporcionan instrucciones detalladas para compilar un analizador y la corrección del código con el SDK del compilador de .NET (API de Roslyn).
ms.date: 08/01/2018
ms.custom: mvc
ms.openlocfilehash: e79907f364939462b7d0d5814c4752be23bcfdf3
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381598"
---
# <a name="tutorial-write-your-first-analyzer-and-code-fix"></a><span data-ttu-id="d3456-103">Tutorial: Crear el primer analizador y la corrección de código</span><span class="sxs-lookup"><span data-stu-id="d3456-103">Tutorial: Write your first analyzer and code fix</span></span>

<span data-ttu-id="d3456-104">El SDK de .NET Compiler Platform proporciona las herramientas necesarias para crear advertencias personalizadas destinadas al código de C# o de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d3456-104">The .NET Compiler Platform SDK provides the tools you need to create custom warnings that target C# or Visual Basic code.</span></span> <span data-ttu-id="d3456-105">Su **analizador** contiene código que reconoce las infracciones de la regla.</span><span class="sxs-lookup"><span data-stu-id="d3456-105">Your **analyzer** contains code that recognizes violations of your rule.</span></span> <span data-ttu-id="d3456-106">La **corrección del código** contiene el código que corrige la infracción.</span><span class="sxs-lookup"><span data-stu-id="d3456-106">Your **code fix** contains the code that fixes the violation.</span></span> <span data-ttu-id="d3456-107">Las reglas implementadas pueden ser cualquier elemento de la estructura de código para codificar el estilo de las convenciones de nomenclatura y mucho más.</span><span class="sxs-lookup"><span data-stu-id="d3456-107">The rules you implement can be anything from code structure to coding style to naming conventions and more.</span></span> <span data-ttu-id="d3456-108">.NET Compiler Platform proporciona el marco para ejecutar el análisis a medida que los desarrolladores escriben código y todas las características de la interfaz de usuario de Visual Studio para corregir código: mostrar líneas de subrayado en el editor, rellenar la lista de errores de Visual Studio, crear las sugerencias con "bombillas" y mostrar la vista previa enriquecida de las correcciones sugeridas.</span><span class="sxs-lookup"><span data-stu-id="d3456-108">The .NET Compiler Platform provides the framework for running analysis as developers are writing code, and all the Visual Studio UI features for fixing code: showing squiggles in the editor, populating the Visual Studio Error List, creating the "light bulb" suggestions and showing the rich preview of the suggested fixes.</span></span>

<span data-ttu-id="d3456-109">En este tutorial, explorará la creación de un **analizador** y una **corrección de código** complementaria con el uso de las API de Roslyn.</span><span class="sxs-lookup"><span data-stu-id="d3456-109">In this tutorial, you'll explore the creation of an **analyzer** and an accompanying **code fix** using the Roslyn APIs.</span></span> <span data-ttu-id="d3456-110">Un analizador es una manera de realizar análisis de código fuente y notificar un problema al usuario.</span><span class="sxs-lookup"><span data-stu-id="d3456-110">An analyzer is a way to perform source code analysis and report a problem to the user.</span></span> <span data-ttu-id="d3456-111">Opcionalmente, un analizador también puede proporcionar una corrección de código que representa una modificación del código fuente del usuario.</span><span class="sxs-lookup"><span data-stu-id="d3456-111">Optionally, an analyzer can also provide a code fix that represents a modification to the user's source code.</span></span> <span data-ttu-id="d3456-112">Este tutorial crea un analizador que busca declaraciones de variable local que podrían declararse mediante el modificador `const`, aunque no están.</span><span class="sxs-lookup"><span data-stu-id="d3456-112">This tutorial creates an analyzer that finds local variable declarations that could be declared using the `const` modifier but are not.</span></span> <span data-ttu-id="d3456-113">La corrección de código complementaria modifica esas declaraciones para agregar el modificador `const`.</span><span class="sxs-lookup"><span data-stu-id="d3456-113">The accompanying code fix modifies those declarations to add the `const` modifier.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d3456-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d3456-114">Prerequisites</span></span>

> [!NOTE]
> <span data-ttu-id="d3456-115">La plantilla actual de Visual Studio **Analyzer con corrección de código (.NET Standard)** tiene un error conocido y debe corregirse en la versión 16.7 de Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="d3456-115">The current Visual Studio **Analyzer with code fix (.NET Standard)** template has a known bug in it and should be fixed in Visual Studio 2019 version 16.7.</span></span> <span data-ttu-id="d3456-116">Los proyectos de la plantilla no se compilarán a menos que se realicen los siguientes cambios:</span><span class="sxs-lookup"><span data-stu-id="d3456-116">The projects in the template will not compile unless the following changes are made:</span></span>
>
> 1. <span data-ttu-id="d3456-117">Seleccione **Herramientas** > **Opciones** > **Administrador de paquetes NuGet** > **Orígenes de paquetes**</span><span class="sxs-lookup"><span data-stu-id="d3456-117">Select **Tools** > **Options** > **NuGet Package Manager** > **Package Sources**</span></span>
>    - <span data-ttu-id="d3456-118">Haga clic en el signo más (+) para agregar un nuevo origen:</span><span class="sxs-lookup"><span data-stu-id="d3456-118">Select the plus button, to add a new source:</span></span>
>    - <span data-ttu-id="d3456-119">Establezca el **Origen** en `https://dotnet.myget.org/F/roslyn-analyzers/api/v3/index.json` y seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="d3456-119">Set the **Source** to `https://dotnet.myget.org/F/roslyn-analyzers/api/v3/index.json` and select **Update**</span></span>
> 1. <span data-ttu-id="d3456-120">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **MakeConst.Vsix** y seleccione **Editar archivo del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="d3456-120">From the **Solution Explorer**, right-click on the **MakeConst.Vsix** project, and select **Edit Project File**</span></span>
>    - <span data-ttu-id="d3456-121">Actualice el nodo `<AssemblyName>` para agregar el sufijo `.Visx`:</span><span class="sxs-lookup"><span data-stu-id="d3456-121">Update the `<AssemblyName>` node to add the `.Visx` suffix:</span></span>
>      - `<AssemblyName>MakeConst.Vsix</AssemblyName>`
>    - <span data-ttu-id="d3456-122">Actualice el nodo `<ProjectReference>` en la línea 41 para modificar el valor `TargetFramework`:</span><span class="sxs-lookup"><span data-stu-id="d3456-122">Update the `<ProjectReference>` node on line 41 to alter the `TargetFramework` value:</span></span>
>      - `<ProjectReference Update="@(ProjectReference)" AdditionalProperties="TargetFramework=netstandard2.0" />`
> 1. <span data-ttu-id="d3456-123">Actualice el archivo *MakeConstUnitTests.cs* en el proyecto *MakeConst.Test*:</span><span class="sxs-lookup"><span data-stu-id="d3456-123">Update the *MakeConstUnitTests.cs* file, in the *MakeConst.Test* project:</span></span>
>    - <span data-ttu-id="d3456-124">Cambie la línea 9 a la siguiente, observe la modificación del espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="d3456-124">Change line 9 to the following, notice namespace alteration:</span></span>
>      - `using Verify = Microsoft.CodeAnalysis.CSharp.Testing.MSTest.CodeFixVerifier<`
>    - <span data-ttu-id="d3456-125">Cambie la línea 24 al siguiente método:</span><span class="sxs-lookup"><span data-stu-id="d3456-125">Change line 24 to the following method:</span></span>
>      - `await Verify.VerifyAnalyzerAsync(test);`
>    - <span data-ttu-id="d3456-126">Cambie la línea 62 al siguiente método:</span><span class="sxs-lookup"><span data-stu-id="d3456-126">Change line 62 to the following method:</span></span>
>      - `await Verify.VerifyCodeFixAsync(test, expected, fixtest);`

- [<span data-ttu-id="d3456-127">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="d3456-127">Visual Studio 2017</span></span>](https://visualstudio.microsoft.com/vs/older-downloads/#visual-studio-2017-and-other-products)
- [<span data-ttu-id="d3456-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="d3456-128">Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads)

<span data-ttu-id="d3456-129">Debe instalar el **SDK de .NET Compiler Platform** a través del Instalador de Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="d3456-129">You'll need to install the **.NET Compiler Platform SDK** via the Visual Studio Installer:</span></span>

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

<span data-ttu-id="d3456-130">Hay varios pasos para crear y validar su analizador:</span><span class="sxs-lookup"><span data-stu-id="d3456-130">There are several steps to creating and validating your analyzer:</span></span>

1. <span data-ttu-id="d3456-131">Crear la solución.</span><span class="sxs-lookup"><span data-stu-id="d3456-131">Create the solution.</span></span>
1. <span data-ttu-id="d3456-132">Registrar el nombre del analizador y la descripción.</span><span class="sxs-lookup"><span data-stu-id="d3456-132">Register the analyzer name and description.</span></span>
1. <span data-ttu-id="d3456-133">Notificar las recomendaciones y las advertencias del analizador.</span><span class="sxs-lookup"><span data-stu-id="d3456-133">Report analyzer warnings and recommendations.</span></span>
1. <span data-ttu-id="d3456-134">Implementar la corrección de código para aceptar las recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="d3456-134">Implement the code fix to accept recommendations.</span></span>
1. <span data-ttu-id="d3456-135">Mejorar el análisis mediante las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="d3456-135">Improve the analysis through unit tests.</span></span>

## <a name="explore-the-analyzer-template"></a><span data-ttu-id="d3456-136">Exploración de la plantilla del analizador</span><span class="sxs-lookup"><span data-stu-id="d3456-136">Explore the analyzer template</span></span>

<span data-ttu-id="d3456-137">El analizador notifica al usuario las declaraciones de variable local que se pueden convertir en constantes locales.</span><span class="sxs-lookup"><span data-stu-id="d3456-137">Your analyzer reports to the user any local variable declarations that can be converted to local constants.</span></span> <span data-ttu-id="d3456-138">Por ejemplo, considere el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="d3456-138">For example, consider the following code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="d3456-139">En el código anterior, a `x` se le asigna un valor constante y nunca se modifica.</span><span class="sxs-lookup"><span data-stu-id="d3456-139">In the code above, `x` is assigned a constant value and is never modified.</span></span> <span data-ttu-id="d3456-140">Se puede declarar con el modificador `const`:</span><span class="sxs-lookup"><span data-stu-id="d3456-140">It can be declared using the `const` modifier:</span></span>

```csharp
const int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="d3456-141">El análisis para determinar si una variable se puede convertir en constante, que requiere un análisis sintáctico, un análisis constante de la expresión del inicializador y un análisis del flujo de datos para garantizar que no se escriba nunca en la variable.</span><span class="sxs-lookup"><span data-stu-id="d3456-141">The analysis to determine whether a variable can be made constant is involved, requiring syntactic analysis, constant analysis of the initializer expression and dataflow analysis to ensure that the variable is never written to.</span></span> <span data-ttu-id="d3456-142">.NET Compiler Platform proporciona las API que facilita la realización de este análisis.</span><span class="sxs-lookup"><span data-stu-id="d3456-142">The .NET Compiler Platform provides APIs that make it easier to perform this analysis.</span></span> <span data-ttu-id="d3456-143">El primer paso es crear un proyecto en C# del **analizador con corrección de código**.</span><span class="sxs-lookup"><span data-stu-id="d3456-143">The first step is to create a new C# **Analyzer with code fix** project.</span></span>

- <span data-ttu-id="d3456-144">En Visual Studio, elija **Archivo > Nuevo > Proyecto...** para mostrar el cuadro de diálogo Nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="d3456-144">In Visual Studio, choose **File > New > Project...** to display the New Project dialog.</span></span>
- <span data-ttu-id="d3456-145">En **Visual C# > Extensibilidad**, elija **Analizador con corrección de código (.NET Standard)** .</span><span class="sxs-lookup"><span data-stu-id="d3456-145">Under **Visual C# > Extensibility**, choose **Analyzer with code fix (.NET Standard)**.</span></span>
- <span data-ttu-id="d3456-146">Asigne al proyecto el nombre "**MakeConst**" y haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="d3456-146">Name your project "**MakeConst**" and click OK.</span></span>

<span data-ttu-id="d3456-147">La plantilla del analizador con corrección de código crea tres proyectos: uno contiene el analizador y la corrección de código, el segundo es un proyecto de prueba unitaria y el tercero es el proyecto de VSIX.</span><span class="sxs-lookup"><span data-stu-id="d3456-147">The analyzer with code fix template creates three projects: one contains the analyzer and code fix, the second is a unit test project, and the third is the VSIX project.</span></span> <span data-ttu-id="d3456-148">El proyecto de inicio predeterminado es el proyecto de VSIX.</span><span class="sxs-lookup"><span data-stu-id="d3456-148">The default startup project is the VSIX project.</span></span> <span data-ttu-id="d3456-149">Presione <kbd>F5</kbd> para iniciar el proyecto de VSIX.</span><span class="sxs-lookup"><span data-stu-id="d3456-149">Press <kbd>F5</kbd> to start the VSIX project.</span></span> <span data-ttu-id="d3456-150">De esta forma se inicia una segunda instancia de Visual Studio que ha cargado el nuevo analizador.</span><span class="sxs-lookup"><span data-stu-id="d3456-150">This starts a second instance of Visual Studio that has loaded your new analyzer.</span></span>

> [!TIP]
> <span data-ttu-id="d3456-151">Al ejecutar el analizador, inicie una segunda copia de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d3456-151">When you run your analyzer, you start a second copy of Visual Studio.</span></span> <span data-ttu-id="d3456-152">Esta segunda copia usa un subárbol del registro diferente para almacenar la configuración.</span><span class="sxs-lookup"><span data-stu-id="d3456-152">This second copy uses a different registry hive to store settings.</span></span> <span data-ttu-id="d3456-153">Le permite diferenciar la configuración visual en las dos copias de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d3456-153">That enables you to differentiate the visual settings in the two copies of Visual Studio.</span></span> <span data-ttu-id="d3456-154">Puede elegir un tema diferente para la ejecución experimental de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d3456-154">You can pick a different theme for the experimental run of Visual Studio.</span></span> <span data-ttu-id="d3456-155">Además, no mueva la configuración o el inicio de sesión a la cuenta de Visual Studio con la ejecución experimental de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d3456-155">In addition, don't roam your settings or login to your Visual Studio account using the experimental run of Visual Studio.</span></span> <span data-ttu-id="d3456-156">Así se mantiene una configuración diferente.</span><span class="sxs-lookup"><span data-stu-id="d3456-156">That keeps the settings different.</span></span>

<span data-ttu-id="d3456-157">En la segunda instancia de Visual Studio que acaba de iniciar, cree un proyecto de aplicación de consola de C# (los proyectos de .NET Core o .NET Framework funcionarán; los analizadores funcionan a nivel de origen). Mantenga el mouse sobre el token con un subrayado ondulado y aparecerá el texto de advertencia proporcionado por un analizador.</span><span class="sxs-lookup"><span data-stu-id="d3456-157">In the second Visual Studio instance that you just started, create a new C# Console Application project (either .NET Core or .NET Framework project will work -- analyzers work at the source level.) Hover over the token with a wavy underline, and the warning text provided by an analyzer appears.</span></span>

<span data-ttu-id="d3456-158">La plantilla crea un analizador que notifica una advertencia en cada declaración de tipo, donde el nombre de tipo contiene letras minúsculas, tal como se muestra en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3456-158">The template creates an analyzer that reports a warning on each type declaration where the type name contains lowercase letters, as shown in the following figure:</span></span>

![Advertencia notificada por el analizador](media/how-to-write-csharp-analyzer-code-fix/report-warning.png)

<span data-ttu-id="d3456-160">La plantilla también proporciona una corrección de código que cambia cualquier nombre de tipo que contiene caracteres en minúsculas a mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="d3456-160">The template also provides a code fix that changes any type name containing lower case characters to all upper case.</span></span> <span data-ttu-id="d3456-161">Puede hacer clic en la bombilla mostrada con la advertencia para ver los cambios sugeridos.</span><span class="sxs-lookup"><span data-stu-id="d3456-161">You can click on the light bulb displayed with the warning to see the suggested changes.</span></span> <span data-ttu-id="d3456-162">Al aceptar los cambios sugeridos, se actualizan el nombre de tipo y todas las referencias a dicho tipo en la solución.</span><span class="sxs-lookup"><span data-stu-id="d3456-162">Accepting the suggested changes updates the type name and all references to that type in the solution.</span></span> <span data-ttu-id="d3456-163">Ahora que ha visto el analizador inicial en acción, cierre la segunda instancia de Visual Studio y vuelva a su proyecto de analizador.</span><span class="sxs-lookup"><span data-stu-id="d3456-163">Now that you've seen the initial analyzer in action, close the second Visual Studio instance and return to your analyzer project.</span></span>

<span data-ttu-id="d3456-164">No tiene que iniciar una segunda copia de Visual Studio, y cree código para probar todos los cambios en el analizador.</span><span class="sxs-lookup"><span data-stu-id="d3456-164">You don't have to start a second copy of Visual Studio and create new code to test every change in your analyzer.</span></span> <span data-ttu-id="d3456-165">La plantilla también crea un proyecto de prueba unitaria de forma automática.</span><span class="sxs-lookup"><span data-stu-id="d3456-165">The template also creates a unit test project for you.</span></span> <span data-ttu-id="d3456-166">Este proyecto contiene dos pruebas.</span><span class="sxs-lookup"><span data-stu-id="d3456-166">That project contains two tests.</span></span> <span data-ttu-id="d3456-167">`TestMethod1` muestra el formato típico de una prueba que analiza el código sin que se desencadene un diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="d3456-167">`TestMethod1` shows the typical format of a test that analyzes code without triggering a diagnostic.</span></span> <span data-ttu-id="d3456-168">`TestMethod2` muestra el formato de una prueba que desencadena un diagnóstico y, a continuación, se aplica una corrección de código sugerida.</span><span class="sxs-lookup"><span data-stu-id="d3456-168">`TestMethod2` shows the format of a test that triggers a diagnostic, and then applies a suggested code fix.</span></span> <span data-ttu-id="d3456-169">Al crear el analizador y la corrección de código, deberá escribir pruebas para diferentes estructuras de código para verificar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="d3456-169">As you build your analyzer and code fix, you'll write tests for different code structures to verify your work.</span></span> <span data-ttu-id="d3456-170">Las pruebas unitarias de los analizadores son mucho más rápidas que las pruebas interactivas con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d3456-170">Unit tests for analyzers are much quicker than testing them interactively with Visual Studio.</span></span>

> [!TIP]
> <span data-ttu-id="d3456-171">Las pruebas unitarias del analizador son una herramienta magnífica si se sabe qué construcciones de código deben y no deben desencadenar el analizador.</span><span class="sxs-lookup"><span data-stu-id="d3456-171">Analyzer unit tests are a great tool when you know what code constructs should and shouldn't trigger your analyzer.</span></span> <span data-ttu-id="d3456-172">Cargar el analizador en otra copia de Visual Studio es una herramienta magnífica para explorar y buscar construcciones en las que puede no haber pensado todavía.</span><span class="sxs-lookup"><span data-stu-id="d3456-172">Loading your analyzer in another copy of Visual Studio is a great tool to explore and find constructs you may not have thought about yet.</span></span>

## <a name="create-analyzer-registrations"></a><span data-ttu-id="d3456-173">Creación de registros del analizador</span><span class="sxs-lookup"><span data-stu-id="d3456-173">Create analyzer registrations</span></span>

<span data-ttu-id="d3456-174">La plantilla crea la clase `DiagnosticAnalyzer` inicial en el archivo **MakeConstAnalyzer.cs**.</span><span class="sxs-lookup"><span data-stu-id="d3456-174">The template creates the initial `DiagnosticAnalyzer` class, in the **MakeConstAnalyzer.cs** file.</span></span> <span data-ttu-id="d3456-175">Este analizador inicial muestra dos propiedades importantes de cada analizador.</span><span class="sxs-lookup"><span data-stu-id="d3456-175">This initial analyzer shows two important properties of every analyzer.</span></span>

- <span data-ttu-id="d3456-176">Cada analizador de diagnóstico debe proporcionar un atributo `[DiagnosticAnalyzer]` que describe el lenguaje en el que opera.</span><span class="sxs-lookup"><span data-stu-id="d3456-176">Every diagnostic analyzer must provide a `[DiagnosticAnalyzer]` attribute that describes the language it operates on.</span></span>
- <span data-ttu-id="d3456-177">Cada analizador de diagnóstico debe derivar de la clase <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer>.</span><span class="sxs-lookup"><span data-stu-id="d3456-177">Every diagnostic analyzer must derive from the <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer> class.</span></span>

<span data-ttu-id="d3456-178">La plantilla también muestra las características básicas que forman parte de cualquier analizador:</span><span class="sxs-lookup"><span data-stu-id="d3456-178">The template also shows the basic features that are part of any analyzer:</span></span>

1. <span data-ttu-id="d3456-179">Registre acciones.</span><span class="sxs-lookup"><span data-stu-id="d3456-179">Register actions.</span></span> <span data-ttu-id="d3456-180">Las acciones representan los cambios de código que deben desencadenar el analizador para examinar el código para las infracciones.</span><span class="sxs-lookup"><span data-stu-id="d3456-180">The actions represent code changes that should trigger your analyzer to examine code for violations.</span></span> <span data-ttu-id="d3456-181">Cuando Visual Studio detecta las modificaciones del código que coinciden con una acción registrada, llama al método registrado del analizador.</span><span class="sxs-lookup"><span data-stu-id="d3456-181">When Visual Studio detects code edits that match a registered action, it calls your analyzer's registered method.</span></span>
1. <span data-ttu-id="d3456-182">Cree diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="d3456-182">Create diagnostics.</span></span> <span data-ttu-id="d3456-183">Cuando el analizador detecta una infracción, crea un objeto de diagnóstico que Visual Studio usa para notificar la infracción al usuario.</span><span class="sxs-lookup"><span data-stu-id="d3456-183">When your analyzer detects a violation, it creates a diagnostic object that Visual Studio uses to notify the user of the violation.</span></span>

<span data-ttu-id="d3456-184">Registre acciones en la invalidación del método <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer.Initialize(Microsoft.CodeAnalysis.Diagnostics.AnalysisContext)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d3456-184">You register actions in your override of <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer.Initialize(Microsoft.CodeAnalysis.Diagnostics.AnalysisContext)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d3456-185">En este tutorial, repasará **nodos de sintaxis** que buscan declaraciones locales y verá cuáles de ellos tienen valores constantes.</span><span class="sxs-lookup"><span data-stu-id="d3456-185">In this tutorial, you'll visit **syntax nodes** looking for local declarations, and see which of those have constant values.</span></span> <span data-ttu-id="d3456-186">Si una declaración puede ser constante, el analizador creará y notificará un diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="d3456-186">If a declaration could be constant, your analyzer will create and report a diagnostic.</span></span>

<span data-ttu-id="d3456-187">El primer paso es actualizar las constantes de registro y el método `Initialize`, por lo que estas constantes indican su analizador "Make Const".</span><span class="sxs-lookup"><span data-stu-id="d3456-187">The first step is to update the registration constants and `Initialize` method so these constants indicate your "Make Const" analyzer.</span></span> <span data-ttu-id="d3456-188">La mayoría de las constantes de cadena se definen en el archivo de recursos de cadena.</span><span class="sxs-lookup"><span data-stu-id="d3456-188">Most of the string constants are defined in the string resource file.</span></span> <span data-ttu-id="d3456-189">Debe seguir dicha práctica para una localización más sencilla.</span><span class="sxs-lookup"><span data-stu-id="d3456-189">You should follow that practice for easier localization.</span></span> <span data-ttu-id="d3456-190">Abra el archivo **Resources.resx** para el proyecto de analizador **MakeConst**.</span><span class="sxs-lookup"><span data-stu-id="d3456-190">Open the **Resources.resx** file for the **MakeConst** analyzer project.</span></span> <span data-ttu-id="d3456-191">Muestra el editor de recursos.</span><span class="sxs-lookup"><span data-stu-id="d3456-191">This displays the resource editor.</span></span> <span data-ttu-id="d3456-192">Actualice los recursos de cadena como sigue:</span><span class="sxs-lookup"><span data-stu-id="d3456-192">Update the string resources as follows:</span></span>

- <span data-ttu-id="d3456-193">Cambie `AnalyzerTitle` por "La variable puede convertirse en constante".</span><span class="sxs-lookup"><span data-stu-id="d3456-193">Change `AnalyzerTitle` to "Variable can be made constant".</span></span>
- <span data-ttu-id="d3456-194">Cambie `AnalyzerMessageFormat` por "Puede convertirse en constante".</span><span class="sxs-lookup"><span data-stu-id="d3456-194">Change `AnalyzerMessageFormat` to "Can be made constant".</span></span>
- <span data-ttu-id="d3456-195">Cambie `AnalyzerDescription` por "Convertir en constante".</span><span class="sxs-lookup"><span data-stu-id="d3456-195">Change `AnalyzerDescription` to "Make Constant".</span></span>

<span data-ttu-id="d3456-196">Cambie también el menú desplegable del **modificador de acceso** por `public`.</span><span class="sxs-lookup"><span data-stu-id="d3456-196">Also, change the **Access Modifier** drop-down to `public`.</span></span> <span data-ttu-id="d3456-197">De esta forma, se facilita el uso de estas constantes en las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="d3456-197">That makes it easier to use these constants in unit tests.</span></span> <span data-ttu-id="d3456-198">Cuando haya terminado, el editor de recursos debe aparecer como se muestra en la figura siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3456-198">When you have finished, the resource editor should appear as follow figure shows:</span></span>

![Actualización de los recursos de cadena](media/how-to-write-csharp-analyzer-code-fix/update-string-resources.png)

<span data-ttu-id="d3456-200">Los cambios restantes están en el archivo del analizador.</span><span class="sxs-lookup"><span data-stu-id="d3456-200">The remaining changes are in the analyzer file.</span></span> <span data-ttu-id="d3456-201">Abra **MakeConstAnalyzer.cs** en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d3456-201">Open **MakeConstAnalyzer.cs** in Visual Studio.</span></span> <span data-ttu-id="d3456-202">Cambie la acción registrada de una que actúa en los símbolos a una que actúa en la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="d3456-202">Change the registered action from one that acts on symbols to one that acts on syntax.</span></span> <span data-ttu-id="d3456-203">En el método `MakeConstAnalyzerAnalyzer.Initialize`, busque la línea que registra la acción en los símbolos:</span><span class="sxs-lookup"><span data-stu-id="d3456-203">In the `MakeConstAnalyzerAnalyzer.Initialize` method, find the line that registers the action on symbols:</span></span>

```csharp
context.RegisterSymbolAction(AnalyzeSymbol, SymbolKind.NamedType);
```

<span data-ttu-id="d3456-204">Reemplácela por la línea siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3456-204">Replace it with the following line:</span></span>

[!code-csharp[Register the node action](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstAnalyzer.cs#RegisterNodeAction "Register a node action")]

<span data-ttu-id="d3456-205">Después de este cambio, puede eliminar el método `AnalyzeSymbol`.</span><span class="sxs-lookup"><span data-stu-id="d3456-205">After that change, you can delete the `AnalyzeSymbol` method.</span></span> <span data-ttu-id="d3456-206">Este analizador examina <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.LocalDeclarationStatement?displayProperty=nameWithType>, no las instrucciones <xref:Microsoft.CodeAnalysis.SymbolKind.NamedType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d3456-206">This analyzer examines <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.LocalDeclarationStatement?displayProperty=nameWithType>, not <xref:Microsoft.CodeAnalysis.SymbolKind.NamedType?displayProperty=nameWithType> statements.</span></span> <span data-ttu-id="d3456-207">Tenga en cuenta que `AnalyzeNode` tiene un subrayado ondulado rojo debajo.</span><span class="sxs-lookup"><span data-stu-id="d3456-207">Notice that `AnalyzeNode` has red squiggles under it.</span></span> <span data-ttu-id="d3456-208">El código recién agregado hace referencia a un método `AnalyzeNode` que no se ha declarado.</span><span class="sxs-lookup"><span data-stu-id="d3456-208">The code you just added references an `AnalyzeNode` method that hasn't been declared.</span></span> <span data-ttu-id="d3456-209">Declare dicho método con el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="d3456-209">Declare that method using the following code:</span></span>

```csharp
private void AnalyzeNode(SyntaxNodeAnalysisContext context)
{
}
```

<span data-ttu-id="d3456-210">Cambie `Category` por "Uso" en **MakeConstAnalyzer.cs** como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3456-210">Change the `Category` to "Usage" in **MakeConstAnalyzer.cs** as shown in the following code:</span></span>

```csharp
private const string Category = "Usage";
```

## <a name="find-local-declarations-that-could-be-const"></a><span data-ttu-id="d3456-211">Búsqueda de las declaraciones locales que podrían ser constantes</span><span class="sxs-lookup"><span data-stu-id="d3456-211">Find local declarations that could be const</span></span>

<span data-ttu-id="d3456-212">Es el momento de escribir la primera versión del método `AnalyzeNode`.</span><span class="sxs-lookup"><span data-stu-id="d3456-212">It's time to write the first version of the `AnalyzeNode` method.</span></span> <span data-ttu-id="d3456-213">Debe buscar una sola declaración local que podría ser `const` pero no lo es, al igual que el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3456-213">It should look for a single local declaration that could be `const` but is not, like the following code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="d3456-214">El primer paso es encontrar las declaraciones locales.</span><span class="sxs-lookup"><span data-stu-id="d3456-214">The first step is to find local declarations.</span></span> <span data-ttu-id="d3456-215">Agregue el código siguiente a `AnalyzeNode` en **MakeConstAnalyzer.cs**:</span><span class="sxs-lookup"><span data-stu-id="d3456-215">Add the following code to `AnalyzeNode` in **MakeConstAnalyzer.cs**:</span></span>

```csharp
var localDeclaration = (LocalDeclarationStatementSyntax)context.Node;
```

<span data-ttu-id="d3456-216">Esta conversión siempre se realiza correctamente porque el analizador registró los cambios de las declaraciones locales, y solo las declaraciones locales.</span><span class="sxs-lookup"><span data-stu-id="d3456-216">This cast always succeeds because your analyzer registered for changes to local declarations, and only local declarations.</span></span> <span data-ttu-id="d3456-217">Ningún otro tipo de nodo desencadena una llamada al método `AnalyzeNode`.</span><span class="sxs-lookup"><span data-stu-id="d3456-217">No other node type triggers a call to your `AnalyzeNode` method.</span></span> <span data-ttu-id="d3456-218">A continuación, compruebe la declaración de cualquier modificador `const`.</span><span class="sxs-lookup"><span data-stu-id="d3456-218">Next, check the declaration for any `const` modifiers.</span></span> <span data-ttu-id="d3456-219">Si la encuentra, devuélvala de inmediato.</span><span class="sxs-lookup"><span data-stu-id="d3456-219">If you find them, return immediately.</span></span> <span data-ttu-id="d3456-220">El código siguiente busca cualquier modificador `const` en la declaración local:</span><span class="sxs-lookup"><span data-stu-id="d3456-220">The following code looks for any `const` modifiers on the local declaration:</span></span>

```csharp
// make sure the declaration isn't already const:
if (localDeclaration.Modifiers.Any(SyntaxKind.ConstKeyword))
{
    return;
}
```

<span data-ttu-id="d3456-221">Por último, deberá comprobar que la variable podría ser `const`.</span><span class="sxs-lookup"><span data-stu-id="d3456-221">Finally, you need to check that the variable could be `const`.</span></span> <span data-ttu-id="d3456-222">Esto significa asegurarse de que nunca se asigne después de inicializarse.</span><span class="sxs-lookup"><span data-stu-id="d3456-222">That means making sure it is never assigned after it is initialized.</span></span>

<span data-ttu-id="d3456-223">Realizará algún análisis semántico con <xref:Microsoft.CodeAnalysis.Diagnostics.SyntaxNodeAnalysisContext>.</span><span class="sxs-lookup"><span data-stu-id="d3456-223">You'll perform some semantic analysis using the <xref:Microsoft.CodeAnalysis.Diagnostics.SyntaxNodeAnalysisContext>.</span></span> <span data-ttu-id="d3456-224">Use el argumento `context` para determinar si la declaración de variable local puede convertirse en `const`.</span><span class="sxs-lookup"><span data-stu-id="d3456-224">You use the `context` argument to determine whether the local variable declaration can be made `const`.</span></span> <span data-ttu-id="d3456-225">Una clase <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> representa toda la información semántica en un solo archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="d3456-225">A <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> represents all of semantic information in a single source file.</span></span> <span data-ttu-id="d3456-226">Puede obtener más información en el artículo que trata los [modelos semánticos](../work-with-semantics.md).</span><span class="sxs-lookup"><span data-stu-id="d3456-226">You can learn more in the article that covers [semantic models](../work-with-semantics.md).</span></span> <span data-ttu-id="d3456-227">Deberá usar <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> para realizar análisis de flujo de datos en la instrucción de declaración local.</span><span class="sxs-lookup"><span data-stu-id="d3456-227">You'll use the <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> to perform data flow analysis on the local declaration statement.</span></span> <span data-ttu-id="d3456-228">A continuación, use los resultados de este análisis de flujo de datos para garantizar que la variable local no se escriba con un valor nuevo en cualquier otro lugar.</span><span class="sxs-lookup"><span data-stu-id="d3456-228">Then, you use the results of this data flow analysis to ensure that the local variable isn't written with a new value anywhere else.</span></span> <span data-ttu-id="d3456-229">Llame al método de extensión <xref:Microsoft.CodeAnalysis.ModelExtensions.GetDeclaredSymbol%2A> para recuperar <xref:Microsoft.CodeAnalysis.ILocalSymbol> para la variable y compruebe si no está incluido en la colección <xref:Microsoft.CodeAnalysis.DataFlowAnalysis.WrittenOutside%2A?displayProperty=nameWithType> del análisis de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="d3456-229">Call the <xref:Microsoft.CodeAnalysis.ModelExtensions.GetDeclaredSymbol%2A> extension method to retrieve the <xref:Microsoft.CodeAnalysis.ILocalSymbol> for the variable and check that it isn't contained with the <xref:Microsoft.CodeAnalysis.DataFlowAnalysis.WrittenOutside%2A?displayProperty=nameWithType> collection of the data flow analysis.</span></span> <span data-ttu-id="d3456-230">Agregue el código siguiente al final del método `AnalyzeNode`:</span><span class="sxs-lookup"><span data-stu-id="d3456-230">Add the following code to the end of the `AnalyzeNode` method:</span></span>

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

<span data-ttu-id="d3456-231">El código recién agregado garantiza que no se modifique la variable y que se pueda convertir por tanto en `const`.</span><span class="sxs-lookup"><span data-stu-id="d3456-231">The code just added ensures that the variable isn't modified, and can therefore be made `const`.</span></span> <span data-ttu-id="d3456-232">Es el momento de generar el diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="d3456-232">It's time to raise the diagnostic.</span></span> <span data-ttu-id="d3456-233">Agregue el código siguiente a la última línea en `AnalyzeNode`:</span><span class="sxs-lookup"><span data-stu-id="d3456-233">Add the following code as the last line in `AnalyzeNode`:</span></span>

```csharp
context.ReportDiagnostic(Diagnostic.Create(Rule, context.Node.GetLocation()));
```

<span data-ttu-id="d3456-234">Puede comprobar el progreso presionando <kbd>F5</kbd> para ejecutar el analizador.</span><span class="sxs-lookup"><span data-stu-id="d3456-234">You can check your progress by pressing <kbd>F5</kbd> to run your analyzer.</span></span> <span data-ttu-id="d3456-235">Puede cargar la aplicación de consola que creó anteriormente y después agregar el siguiente código de prueba:</span><span class="sxs-lookup"><span data-stu-id="d3456-235">You can load the console application you created earlier and then add the following test code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="d3456-236">Debe aparecer la bombilla, y el analizador debe informar de un diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="d3456-236">The light bulb should appear, and your analyzer should report a diagnostic.</span></span> <span data-ttu-id="d3456-237">Sin embargo, la bombilla todavía indica que la plantilla generó la corrección de código e indica que se puede convertir en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="d3456-237">However, the light bulb still uses the template generated code fix, and tells you it can be made upper case.</span></span> <span data-ttu-id="d3456-238">En la sección siguiente se explica cómo escribir la corrección de código.</span><span class="sxs-lookup"><span data-stu-id="d3456-238">The next section explains how to write the code fix.</span></span>

## <a name="write-the-code-fix"></a><span data-ttu-id="d3456-239">Escritura de la corrección de código</span><span class="sxs-lookup"><span data-stu-id="d3456-239">Write the code fix</span></span>

<span data-ttu-id="d3456-240">Un analizador puede proporcionar una o varias correcciones de código.</span><span class="sxs-lookup"><span data-stu-id="d3456-240">An analyzer can provide one or more code fixes.</span></span> <span data-ttu-id="d3456-241">Una corrección de código define una edición que soluciona el problema notificado.</span><span class="sxs-lookup"><span data-stu-id="d3456-241">A code fix defines an edit that addresses the reported issue.</span></span> <span data-ttu-id="d3456-242">Para el analizador que ha creado, puede proporcionar una corrección de código que inserta la palabra clave const:</span><span class="sxs-lookup"><span data-stu-id="d3456-242">For the analyzer that you created, you can provide a code fix that inserts the const keyword:</span></span>

```csharp
const int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="d3456-243">El usuario la elige en la interfaz de usuario de la bombilla del editor, y Visual Studio cambia el código.</span><span class="sxs-lookup"><span data-stu-id="d3456-243">The user chooses it from the light bulb UI in the editor and Visual Studio changes the code.</span></span>

<span data-ttu-id="d3456-244">Abra el archivo **MakeConstCodeFixProvider.cs** agregado por la plantilla.</span><span class="sxs-lookup"><span data-stu-id="d3456-244">Open the **MakeConstCodeFixProvider.cs** file added by the template.</span></span>  <span data-ttu-id="d3456-245">Esta corrección de código ya está conectada con el identificador de diagnóstico generado por el analizador de diagnóstico, pero aún no implementa la transformación de código correcta.</span><span class="sxs-lookup"><span data-stu-id="d3456-245">This code fix is already wired up to the Diagnostic ID produced by your diagnostic analyzer, but it doesn't yet implement the right code transform.</span></span> <span data-ttu-id="d3456-246">En primer lugar debe quitar parte del código de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="d3456-246">First you should remove some of the template code.</span></span> <span data-ttu-id="d3456-247">Cambie la cadena de título por "Convertir en constante":</span><span class="sxs-lookup"><span data-stu-id="d3456-247">Change the title string to "Make constant":</span></span>

[!code-csharp[Update the CodeFix title](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CodeFixTitle "Update the CodeFix title")]

<span data-ttu-id="d3456-248">Después, elimine el método `MakeUppercaseAsync`.</span><span class="sxs-lookup"><span data-stu-id="d3456-248">Next, delete the `MakeUppercaseAsync` method.</span></span> <span data-ttu-id="d3456-249">Ya no se aplica.</span><span class="sxs-lookup"><span data-stu-id="d3456-249">It no longer applies.</span></span>

<span data-ttu-id="d3456-250">Todos los proveedores de corrección de código se derivan de <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider>.</span><span class="sxs-lookup"><span data-stu-id="d3456-250">All code fix providers derive from <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider>.</span></span> <span data-ttu-id="d3456-251">Todas invalidan <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider.RegisterCodeFixesAsync(Microsoft.CodeAnalysis.CodeFixes.CodeFixContext)?displayProperty=nameWithType> para notificar las correcciones de código disponibles.</span><span class="sxs-lookup"><span data-stu-id="d3456-251">They all override <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider.RegisterCodeFixesAsync(Microsoft.CodeAnalysis.CodeFixes.CodeFixContext)?displayProperty=nameWithType> to report available code fixes.</span></span> <span data-ttu-id="d3456-252">En `RegisterCodeFixesAsync`, cambie el tipo de nodo antecesor que está buscando por <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax> para que coincida con el diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="d3456-252">In `RegisterCodeFixesAsync`, change the ancestor node type you're searching for to a <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax> to match the diagnostic:</span></span>

[!code-csharp[Find local declaration node](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FindDeclarationNode  "Find the local declaration node that raised the diagnostic")]

<span data-ttu-id="d3456-253">A continuación, cambie la última línea para registrar una corrección de código.</span><span class="sxs-lookup"><span data-stu-id="d3456-253">Next, change the last line to register a code fix.</span></span> <span data-ttu-id="d3456-254">La corrección creará un documento que resulta de agregar el modificador `const` a una declaración existente:</span><span class="sxs-lookup"><span data-stu-id="d3456-254">Your fix will create a new document that results from adding the `const` modifier to an existing declaration:</span></span>

[!code-csharp[Register the new code fix](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#RegisterCodeFix  "Register the new code fix")]

<span data-ttu-id="d3456-255">Observará un subrayado ondulado rojo en el código que acaba de agregar en el símbolo `MakeConstAsync`.</span><span class="sxs-lookup"><span data-stu-id="d3456-255">You'll notice red squiggles in the code you just added on the symbol `MakeConstAsync`.</span></span> <span data-ttu-id="d3456-256">Agregue una declaración para `MakeConstAsync` como el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3456-256">Add a declaration for `MakeConstAsync` like the following code:</span></span>

```csharp
private async Task<Document> MakeConstAsync(Document document,
   LocalDeclarationStatementSyntax localDeclaration,
   CancellationToken cancellationToken)
{
}
```

<span data-ttu-id="d3456-257">El nuevo método `MakeConstAsync` transformará la clase <xref:Microsoft.CodeAnalysis.Document> que representa el archivo de origen del usuario en una nueva clase <xref:Microsoft.CodeAnalysis.Document> que ahora contiene una declaración `const`.</span><span class="sxs-lookup"><span data-stu-id="d3456-257">Your new `MakeConstAsync` method will transform the <xref:Microsoft.CodeAnalysis.Document> representing the user's source file into a new <xref:Microsoft.CodeAnalysis.Document> that now contains a `const` declaration.</span></span>

<span data-ttu-id="d3456-258">Se crea un token de palabra clave `const` para insertarlo en la parte delantera de la instrucción de declaración.</span><span class="sxs-lookup"><span data-stu-id="d3456-258">You create a new `const` keyword token to insert at the front of the declaration statement.</span></span> <span data-ttu-id="d3456-259">Tenga cuidado de quitar primero cualquier curiosidad inicial del primer token de la instrucción de declaración y adjúntela al token `const`.</span><span class="sxs-lookup"><span data-stu-id="d3456-259">Be careful to first remove any leading trivia from the first token of the declaration statement and attach it to the `const` token.</span></span> <span data-ttu-id="d3456-260">Agregue el código siguiente al método `MakeConstAsync`:</span><span class="sxs-lookup"><span data-stu-id="d3456-260">Add the following code to the `MakeConstAsync` method:</span></span>

[!code-csharp[Create a new const keyword token](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CreateConstToken  "Create the new const keyword token")]

<span data-ttu-id="d3456-261">A continuación, agregue el token `const` a la declaración con el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="d3456-261">Next, add the `const` token to the declaration using the following code:</span></span>

```csharp
// Insert the const token into the modifiers list, creating a new modifiers list.
var newModifiers = trimmedLocal.Modifiers.Insert(0, constToken);
// Produce the new local declaration.
var newLocal = trimmedLocal
    .WithModifiers(newModifiers)
    .WithDeclaration(localDeclaration.Declaration);
```

<span data-ttu-id="d3456-262">Después aplique formato a la nueva declaración para que coincida con las reglas de formato de C#.</span><span class="sxs-lookup"><span data-stu-id="d3456-262">Next, format the new declaration to match C# formatting rules.</span></span> <span data-ttu-id="d3456-263">Aplicar formato a los cambios para que coincidan con el código existente mejora la experiencia.</span><span class="sxs-lookup"><span data-stu-id="d3456-263">Formatting your changes to match existing code creates a better experience.</span></span> <span data-ttu-id="d3456-264">Agregue la instrucción siguiente inmediatamente después del código existente:</span><span class="sxs-lookup"><span data-stu-id="d3456-264">Add the following statement immediately after the existing code:</span></span>

[!code-csharp[Format the new declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FormatLocal  "Format the new declaration")]

<span data-ttu-id="d3456-265">Se requiere un nuevo espacio de nombres para este código.</span><span class="sxs-lookup"><span data-stu-id="d3456-265">A new namespace is required for this code.</span></span> <span data-ttu-id="d3456-266">Agregue la siguiente directiva `using` al principio del archivo:</span><span class="sxs-lookup"><span data-stu-id="d3456-266">Add the following `using` directive to the top of the file:</span></span>

```csharp
using Microsoft.CodeAnalysis.Formatting;
```

<span data-ttu-id="d3456-267">El último paso es realizar la edición.</span><span class="sxs-lookup"><span data-stu-id="d3456-267">The final step is to make your edit.</span></span> <span data-ttu-id="d3456-268">Hay tres pasos para este proceso:</span><span class="sxs-lookup"><span data-stu-id="d3456-268">There are three steps to this process:</span></span>

1. <span data-ttu-id="d3456-269">Obtenga un identificador para el documento existente.</span><span class="sxs-lookup"><span data-stu-id="d3456-269">Get a handle to the existing document.</span></span>
1. <span data-ttu-id="d3456-270">Cree un documento mediante el reemplazo de la declaración existente con la nueva declaración.</span><span class="sxs-lookup"><span data-stu-id="d3456-270">Create a new document by replacing the existing declaration with the new declaration.</span></span>
1. <span data-ttu-id="d3456-271">Devuelva el nuevo documento.</span><span class="sxs-lookup"><span data-stu-id="d3456-271">Return the new document.</span></span>

<span data-ttu-id="d3456-272">Agregue el código siguiente al final del método `MakeConstAsync`:</span><span class="sxs-lookup"><span data-stu-id="d3456-272">Add the following code to the end of the `MakeConstAsync` method:</span></span>

[!code-csharp[replace the declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceDocument  "Generate a new document by replacing the declaration")]

<span data-ttu-id="d3456-273">La corrección de código está lista para probarla.</span><span class="sxs-lookup"><span data-stu-id="d3456-273">Your code fix is ready to try.</span></span>  <span data-ttu-id="d3456-274">Presione <kbd>F5</kbd> para ejecutar el proyecto del analizador en una segunda instancia de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d3456-274">Press <kbd>F5</kbd> to run the analyzer project in a second instance of Visual Studio.</span></span> <span data-ttu-id="d3456-275">En la segunda instancia de Visual Studio, cree un proyecto de aplicación de consola de C# y agregue algunas declaraciones de variable local inicializadas con valores de constante para el método Main.</span><span class="sxs-lookup"><span data-stu-id="d3456-275">In the second Visual Studio instance, create a new C# Console Application project and add a few local variable declarations initialized with constant values to the Main method.</span></span> <span data-ttu-id="d3456-276">Observará que se notifican como advertencias de la siguiente forma.</span><span class="sxs-lookup"><span data-stu-id="d3456-276">You'll see that they are reported as warnings as below.</span></span>

![Puede convertir las advertencias en constantes](media/how-to-write-csharp-analyzer-code-fix/make-const-warning.png)

<span data-ttu-id="d3456-278">Ha progresado bastante.</span><span class="sxs-lookup"><span data-stu-id="d3456-278">You've made a lot of progress.</span></span> <span data-ttu-id="d3456-279">Hay subrayados ondulados debajo de las declaraciones que pueden convertirse en `const`.</span><span class="sxs-lookup"><span data-stu-id="d3456-279">There are squiggles under the declarations that can be made `const`.</span></span> <span data-ttu-id="d3456-280">Pero aún queda trabajo por hacer.</span><span class="sxs-lookup"><span data-stu-id="d3456-280">But there is still work to do.</span></span> <span data-ttu-id="d3456-281">Esto funciona bien si agrega `const` a las declaraciones a partir de `i`, luego `j` y, por último, `k`.</span><span class="sxs-lookup"><span data-stu-id="d3456-281">This works fine if you add `const` to the declarations starting with `i`, then `j` and finally `k`.</span></span> <span data-ttu-id="d3456-282">Sin embargo, si agrega el modificador `const` en un orden diferente, a partir de `k`, el analizador crea errores: `k` no puede declararse como `const`, a menos que `i` y `j` ya sean `const`.</span><span class="sxs-lookup"><span data-stu-id="d3456-282">But, if you add the `const` modifier in a different order, starting with `k`, your analyzer creates errors: `k` can't be declared `const`, unless `i` and `j` are both already `const`.</span></span> <span data-ttu-id="d3456-283">Tiene que realizar más análisis para asegurarse de que controla la forma en que las variables pueden declararse e inicializarse.</span><span class="sxs-lookup"><span data-stu-id="d3456-283">You've got to do more analysis to ensure you handle the different ways variables can be declared and initialized.</span></span>

## <a name="build-data-driven-tests"></a><span data-ttu-id="d3456-284">Creación de pruebas basadas en datos</span><span class="sxs-lookup"><span data-stu-id="d3456-284">Build data driven tests</span></span>

<span data-ttu-id="d3456-285">El analizador y la corrección de código funcionan en un caso sencillo de una única declaración que puede convertirse en const.</span><span class="sxs-lookup"><span data-stu-id="d3456-285">Your analyzer and code fix work on a simple case of a single declaration that can be made const.</span></span> <span data-ttu-id="d3456-286">Hay varias instrucciones de declaración posibles donde esta implementación comete errores.</span><span class="sxs-lookup"><span data-stu-id="d3456-286">There are numerous possible declaration statements where this implementation makes mistakes.</span></span> <span data-ttu-id="d3456-287">Abordará estos casos al trabajar con la biblioteca de pruebas unitarias escrita por la plantilla.</span><span class="sxs-lookup"><span data-stu-id="d3456-287">You'll address these cases by working with the unit test library written by the template.</span></span> <span data-ttu-id="d3456-288">Es mucho más rápido que abrir repetidamente una segunda copia de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d3456-288">It's much faster than repeatedly opening a second copy of Visual Studio.</span></span>

<span data-ttu-id="d3456-289">Abra el archivo **MakeConstUnitTests.cs** en el proyecto de prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="d3456-289">Open the **MakeConstUnitTests.cs** file in the unit test project.</span></span> <span data-ttu-id="d3456-290">La plantilla creó dos pruebas que siguen los dos patrones comunes para una prueba unitaria de la corrección de código y del analizador.</span><span class="sxs-lookup"><span data-stu-id="d3456-290">The template created two tests that follow the two common patterns for an analyzer and code fix unit test.</span></span> <span data-ttu-id="d3456-291">`TestMethod1` muestra el patrón para una prueba que garantiza que el analizador no notifique un diagnóstico cuando no debe.</span><span class="sxs-lookup"><span data-stu-id="d3456-291">`TestMethod1` shows the pattern for a test that ensures the analyzer doesn't report a diagnostic when it shouldn't.</span></span> <span data-ttu-id="d3456-292">`TestMethod2` muestra el patrón de notificación de un diagnóstico y de ejecución de la corrección de código.</span><span class="sxs-lookup"><span data-stu-id="d3456-292">`TestMethod2` shows the pattern for reporting a diagnostic and running the code fix.</span></span>

<span data-ttu-id="d3456-293">El código para casi todas las pruebas del analizador sigue uno de estos dos patrones.</span><span class="sxs-lookup"><span data-stu-id="d3456-293">The code for almost every test for your analyzer follows one of these two patterns.</span></span> <span data-ttu-id="d3456-294">Para el primer paso, puede reprocesar estas pruebas como pruebas basadas en datos.</span><span class="sxs-lookup"><span data-stu-id="d3456-294">For the first step, you can rework these tests as data driven tests.</span></span> <span data-ttu-id="d3456-295">Después, será fácil crear pruebas con la adición de nuevas constantes de cadena para representar diferentes entradas de prueba.</span><span class="sxs-lookup"><span data-stu-id="d3456-295">Then, it will be easy to create new tests by adding new string constants to represent different test inputs.</span></span>

<span data-ttu-id="d3456-296">Por cuestiones de eficacia, el primer paso es refactorizar las dos pruebas en pruebas basadas en datos.</span><span class="sxs-lookup"><span data-stu-id="d3456-296">For efficiency, the first step is to refactor the two tests into data driven tests.</span></span> <span data-ttu-id="d3456-297">Después, solo necesita definir un par de constantes de cadena para cada prueba nueva.</span><span class="sxs-lookup"><span data-stu-id="d3456-297">Then, you only need to define a couple string constants for each new test.</span></span> <span data-ttu-id="d3456-298">Durante la refactorización, cambie el nombre de ambos métodos por otros nombres mejores.</span><span class="sxs-lookup"><span data-stu-id="d3456-298">While you are refactoring, rename both methods to better names.</span></span> <span data-ttu-id="d3456-299">Reemplace `TestMethod1` con esta prueba que garantiza que no se realizará ningún diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="d3456-299">Replace `TestMethod1` with this test that ensures no diagnostic is raised:</span></span>

```csharp
[DataTestMethod]
[DataRow("")]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
{
    VerifyCSharpDiagnostic(testCode);
}
```

<span data-ttu-id="d3456-300">Puede crear una fila de datos para esta prueba mediante la definición de cualquier fragmento de código que no debería provocar que el diagnóstico desencadene una advertencia.</span><span class="sxs-lookup"><span data-stu-id="d3456-300">You can create a new data row for this test by defining any code fragment that should not cause your diagnostic to trigger a warning.</span></span> <span data-ttu-id="d3456-301">Esta sobrecarga de `VerifyCSharpDiagnostic` pasa cuando no hay ningún diagnóstico desencadenado para el fragmento de código fuente.</span><span class="sxs-lookup"><span data-stu-id="d3456-301">This overload of `VerifyCSharpDiagnostic` passes when there are no diagnostics triggered for the source code fragment.</span></span>

<span data-ttu-id="d3456-302">Después, reemplace `TestMethod2` con esta prueba que garantiza la realización de un diagnóstico y la aplicación de una corrección de código para el fragmento de código fuente:</span><span class="sxs-lookup"><span data-stu-id="d3456-302">Next, replace `TestMethod2` with this test that ensures a diagnostic is raised and a code fix applied for the source code fragment:</span></span>

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

<span data-ttu-id="d3456-303">El código anterior también realizó un par de cambios en el código que compila el resultado de diagnóstico esperado.</span><span class="sxs-lookup"><span data-stu-id="d3456-303">The preceding code also made a couple changes to the code that builds the expected diagnostic result.</span></span> <span data-ttu-id="d3456-304">Usa las constantes públicas registradas en el analizador `MakeConst`.</span><span class="sxs-lookup"><span data-stu-id="d3456-304">It uses the public constants registered in the `MakeConst` analyzer.</span></span> <span data-ttu-id="d3456-305">Además, utiliza dos constantes de cadena para el origen de entrada y fijo.</span><span class="sxs-lookup"><span data-stu-id="d3456-305">In addition, it uses two string constants for the input and fixed source.</span></span> <span data-ttu-id="d3456-306">Agregue las siguientes constantes de cadena a la clase `UnitTest`:</span><span class="sxs-lookup"><span data-stu-id="d3456-306">Add the following string constants to the `UnitTest` class:</span></span>

[!code-csharp[string constants for fix test](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FirstFixTest "string constants for fix test")]

<span data-ttu-id="d3456-307">Ejecute estas dos pruebas para asegurarse de que pasen.</span><span class="sxs-lookup"><span data-stu-id="d3456-307">Run these two tests to make sure they pass.</span></span> <span data-ttu-id="d3456-308">En Visual Studio, abra el **Explorador de pruebas**; para ello, seleccione **Prueba** > **Windows** > **Explorador de pruebas**.</span><span class="sxs-lookup"><span data-stu-id="d3456-308">In Visual Studio, open the **Test Explorer** by selecting **Test** > **Windows** > **Test Explorer**.</span></span> <span data-ttu-id="d3456-309">A continuación, seleccione el vínculo **Ejecutar todo**.</span><span class="sxs-lookup"><span data-stu-id="d3456-309">Then select the **Run All** link.</span></span>

## <a name="create-tests-for-valid-declarations"></a><span data-ttu-id="d3456-310">Creación de pruebas para declaraciones válidas</span><span class="sxs-lookup"><span data-stu-id="d3456-310">Create tests for valid declarations</span></span>

<span data-ttu-id="d3456-311">Por norma general, los analizadores deben existir lo más rápido posible, pero haciendo el mínimo trabajo.</span><span class="sxs-lookup"><span data-stu-id="d3456-311">As a general rule, analyzers should exit as quickly as possible, doing minimal work.</span></span> <span data-ttu-id="d3456-312">Visual Studio llama a los analizadores registrados a medida que el usuario edita el código.</span><span class="sxs-lookup"><span data-stu-id="d3456-312">Visual Studio calls registered analyzers as the user edits code.</span></span> <span data-ttu-id="d3456-313">La capacidad de respuesta es un requisito clave.</span><span class="sxs-lookup"><span data-stu-id="d3456-313">Responsiveness is a key requirement.</span></span> <span data-ttu-id="d3456-314">Hay varios casos de pruebas del código que no deben realizar un diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="d3456-314">There are several test cases for code that should not raise your diagnostic.</span></span> <span data-ttu-id="d3456-315">El analizador ya controla una de esas pruebas, el caso en que una variable se asigna después de inicializarse.</span><span class="sxs-lookup"><span data-stu-id="d3456-315">Your analyzer already handles one of those tests, the case where a variable is assigned after being initialized.</span></span> <span data-ttu-id="d3456-316">Agregue la siguiente constante de cadena a las pruebas para representar dicho caso:</span><span class="sxs-lookup"><span data-stu-id="d3456-316">Add the following string constant to your tests to represent that case:</span></span>

[!code-csharp[variable assigned](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VariableAssigned "a variable that is assigned after being initialized won't raise the diagnostic")]

<span data-ttu-id="d3456-317">Después, agregue una fila de datos para esta prueba como se muestra en el fragmento de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3456-317">Then, add a data row for this test as shown in the snippet below:</span></span>

```csharp
[DataTestMethod]
[DataRow(""),
 DataRow(VariableAssigned)]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
```

<span data-ttu-id="d3456-318">Esta prueba también pasa.</span><span class="sxs-lookup"><span data-stu-id="d3456-318">This test passes as well.</span></span> <span data-ttu-id="d3456-319">Después, agregue constantes para las condiciones que aún no ha controlado:</span><span class="sxs-lookup"><span data-stu-id="d3456-319">Next, add constants for conditions you haven't handled yet:</span></span>

- <span data-ttu-id="d3456-320">Declaraciones que ya son `const`, porque ya son constantes:</span><span class="sxs-lookup"><span data-stu-id="d3456-320">Declarations that are already `const`, because they are already const:</span></span>

   [!code-csharp[already const declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#AlreadyConst "a declaration that is already const should not raise the diagnostic")]

- <span data-ttu-id="d3456-321">Declaraciones que no tienen inicializador, porque no hay ningún valor para usar:</span><span class="sxs-lookup"><span data-stu-id="d3456-321">Declarations that have no initializer, because there is no value to use:</span></span>

   [!code-csharp[declarations that have no initializer](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#NoInitializer "a declaration that has no initializer should not raise the diagnostic")]

- <span data-ttu-id="d3456-322">Declaraciones donde el inicializador no es una constante, porque no pueden ser constantes en tiempo de compilación:</span><span class="sxs-lookup"><span data-stu-id="d3456-322">Declarations where the initializer is not a constant, because they can't be compile-time constants:</span></span>

   [!code-csharp[declarations where the initializer isn't const](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#InitializerNotConstant "a declaration where the initializer is not a compile-time constant should not raise the diagnostic")]

<span data-ttu-id="d3456-323">Puede ser incluso más complicado, porque C# admite varias declaraciones como una instrucción.</span><span class="sxs-lookup"><span data-stu-id="d3456-323">It can be even more complicated because C# allows multiple declarations as one statement.</span></span> <span data-ttu-id="d3456-324">Considere la siguiente constante de cadena de caso de prueba:</span><span class="sxs-lookup"><span data-stu-id="d3456-324">Consider the following test case string constant:</span></span>

[!code-csharp[multiple initializers](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#MultipleInitializers "A declaration can be made constant only if all variables in that statement can be made constant")]

<span data-ttu-id="d3456-325">La variable `i` puede convertirse en constante, pero la variable `j` no puede.</span><span class="sxs-lookup"><span data-stu-id="d3456-325">The variable `i` can be made constant, but the variable `j` cannot.</span></span> <span data-ttu-id="d3456-326">Por tanto, esta instrucción no puede convertirse en una declaración de constante.</span><span class="sxs-lookup"><span data-stu-id="d3456-326">Therefore, this statement cannot be made a const declaration.</span></span> <span data-ttu-id="d3456-327">Agregue las declaraciones `DataRow` para todas estas pruebas:</span><span class="sxs-lookup"><span data-stu-id="d3456-327">Add the `DataRow` declarations for all these tests:</span></span>

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

<span data-ttu-id="d3456-328">Vuelva a ejecutar las pruebas y, después, observará que estos nuevos casos de prueba generarán errores.</span><span class="sxs-lookup"><span data-stu-id="d3456-328">Run your tests again, and you'll see these new test cases fail.</span></span>

## <a name="update-your-analyzer-to-ignore-correct-declarations"></a><span data-ttu-id="d3456-329">Actualización del analizador para ignorar declaraciones correctas</span><span class="sxs-lookup"><span data-stu-id="d3456-329">Update your analyzer to ignore correct declarations</span></span>

<span data-ttu-id="d3456-330">Necesita algunas mejoras en el método `AnalyzeNode` del analizador para filtrar el código que cumple estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="d3456-330">You need some enhancements to your analyzer's `AnalyzeNode` method to filter out code that matches these conditions.</span></span> <span data-ttu-id="d3456-331">Son todas condiciones relacionadas, por lo que los cambios similares corregirán todas estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="d3456-331">They are all related conditions, so similar changes will fix all these conditions.</span></span> <span data-ttu-id="d3456-332">Realice los siguientes cambios en `AnalyzeNode`:</span><span class="sxs-lookup"><span data-stu-id="d3456-332">Make the following changes to `AnalyzeNode`:</span></span>

- <span data-ttu-id="d3456-333">El análisis semántico analizó una única declaración de variable.</span><span class="sxs-lookup"><span data-stu-id="d3456-333">Your semantic analysis examined a single variable declaration.</span></span> <span data-ttu-id="d3456-334">Este código necesita estar en un bucle `foreach` que examina todas las variables declaradas en la misma instrucción.</span><span class="sxs-lookup"><span data-stu-id="d3456-334">This code needs to be in a `foreach` loop that examines all the variables declared in the same statement.</span></span>
- <span data-ttu-id="d3456-335">Cada variable declarada necesita tener un inicializador.</span><span class="sxs-lookup"><span data-stu-id="d3456-335">Each declared variable needs to have an initializer.</span></span>
- <span data-ttu-id="d3456-336">El inicializador de cada variable declarada debe ser una constante de tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="d3456-336">Each declared variable's initializer must be a compile-time constant.</span></span>

<span data-ttu-id="d3456-337">En el método `AnalyzeNode`, reemplace el análisis semántico original:</span><span class="sxs-lookup"><span data-stu-id="d3456-337">In your `AnalyzeNode` method, replace the original semantic analysis:</span></span>

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

<span data-ttu-id="d3456-338">por el siguiente fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="d3456-338">with the following code snippet:</span></span>

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

<span data-ttu-id="d3456-339">El primer bucle `foreach` examina cada declaración de variable con análisis sintácticos</span><span class="sxs-lookup"><span data-stu-id="d3456-339">The first `foreach` loop examines each variable declaration using syntactic analysis.</span></span> <span data-ttu-id="d3456-340">La primera comprobación garantiza que la variable tiene un inicializador.</span><span class="sxs-lookup"><span data-stu-id="d3456-340">The first check guarantees that the variable has an initializer.</span></span> <span data-ttu-id="d3456-341">La segunda comprobación garantiza que el inicializador es una constante.</span><span class="sxs-lookup"><span data-stu-id="d3456-341">The second check guarantees that the initializer is a constant.</span></span> <span data-ttu-id="d3456-342">El segundo bucle tiene el análisis semántico original.</span><span class="sxs-lookup"><span data-stu-id="d3456-342">The second loop has the original semantic analysis.</span></span> <span data-ttu-id="d3456-343">Las comprobaciones semánticas se encuentran en un bucle independiente porque afectan más al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d3456-343">The semantic checks are in a separate loop because it has a greater impact on performance.</span></span> <span data-ttu-id="d3456-344">Vuelva a ejecutar las pruebas y observará que todas pasan.</span><span class="sxs-lookup"><span data-stu-id="d3456-344">Run your tests again, and you should see them all pass.</span></span>

## <a name="add-the-final-polish"></a><span data-ttu-id="d3456-345">Adición de un retoque final</span><span class="sxs-lookup"><span data-stu-id="d3456-345">Add the final polish</span></span>

<span data-ttu-id="d3456-346">Casi ha terminado.</span><span class="sxs-lookup"><span data-stu-id="d3456-346">You're almost done.</span></span> <span data-ttu-id="d3456-347">Hay algunas condiciones más que el analizador tiene que cumplir.</span><span class="sxs-lookup"><span data-stu-id="d3456-347">There are a few more conditions for your analyzer to handle.</span></span> <span data-ttu-id="d3456-348">Visual Studio llama a los analizadores mientras el usuario escribe el código.</span><span class="sxs-lookup"><span data-stu-id="d3456-348">Visual Studio calls analyzers while the user is writing code.</span></span> <span data-ttu-id="d3456-349">Suele darse el caso de que se llama al analizador para código que no compila.</span><span class="sxs-lookup"><span data-stu-id="d3456-349">It's often the case that your analyzer will be called for code that doesn't compile.</span></span> <span data-ttu-id="d3456-350">El método `AnalyzeNode` del analizador de diagnóstico no comprueba si el valor de constante se puede convertir al tipo de variable.</span><span class="sxs-lookup"><span data-stu-id="d3456-350">The diagnostic analyzer's `AnalyzeNode` method does not check to see if the constant value is convertible to the variable type.</span></span> <span data-ttu-id="d3456-351">Por tanto, la implementación actual convertirá correctamente una declaración incorrecta, como int i = "abc"', en una constante local.</span><span class="sxs-lookup"><span data-stu-id="d3456-351">So, the current implementation will happily convert an incorrect declaration such as int i = "abc"' to a local constant.</span></span> <span data-ttu-id="d3456-352">Agregue una constante de cadena de origen para esa condición:</span><span class="sxs-lookup"><span data-stu-id="d3456-352">Add a source string constant for that condition:</span></span>

[!code-csharp[Mismatched types don't raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsInvalid "When the variable type and the constant type don't match, there's no diagnostic")]

<span data-ttu-id="d3456-353">Además, los tipos de referencia no se controlan correctamente.</span><span class="sxs-lookup"><span data-stu-id="d3456-353">In addition, reference types are not handled properly.</span></span> <span data-ttu-id="d3456-354">El único valor de constante permitido para un tipo de referencia es `null`, excepto en este caso de <xref:System.String?displayProperty=nameWithType>, que admite los literales de cadena.</span><span class="sxs-lookup"><span data-stu-id="d3456-354">The only constant value allowed for a reference type is `null`, except in this case of <xref:System.String?displayProperty=nameWithType>, which allows string literals.</span></span> <span data-ttu-id="d3456-355">En otras palabras, `const string s = "abc"` es legal, pero `const object s = "abc"` no lo es.</span><span class="sxs-lookup"><span data-stu-id="d3456-355">In other words, `const string s = "abc"` is legal, but `const object s = "abc"` is not.</span></span> <span data-ttu-id="d3456-356">Este fragmento de código comprueba esa condición:</span><span class="sxs-lookup"><span data-stu-id="d3456-356">This code snippet verifies that condition:</span></span>

[!code-csharp[Reference types don't raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsntString "When the variable type is a reference type other than string, there's no diagnostic")]

<span data-ttu-id="d3456-357">Para ser exhaustivo, debe agregar otra prueba para asegurarse de que puede crear una declaración de constante para una cadena.</span><span class="sxs-lookup"><span data-stu-id="d3456-357">To be thorough, you need to add another test to make sure that you can create a constant declaration for a string.</span></span> <span data-ttu-id="d3456-358">El fragmento de código siguiente define el código que genera el diagnóstico y el código después de haber aplicado la corrección:</span><span class="sxs-lookup"><span data-stu-id="d3456-358">The following snippet defines both the code that raises the diagnostic, and the code after the fix has been applied:</span></span>

[!code-csharp[string reference types raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#ConstantIsString "When the variable type is string, it can be constant")]

<span data-ttu-id="d3456-359">Por último, si una variable se declara con la palabra clave `var`, la corrección de código hace una función incorrecta y genera una declaración `const var`, que el lenguaje C# no admite.</span><span class="sxs-lookup"><span data-stu-id="d3456-359">Finally, if a variable is declared with the `var` keyword, the code fix does the wrong thing and generates a `const var` declaration, which is not supported by the C# language.</span></span> <span data-ttu-id="d3456-360">Para corregir este error, la corrección de código debe reemplazar la palabra clave `var` por el nombre del tipo deducido:</span><span class="sxs-lookup"><span data-stu-id="d3456-360">To fix this bug, the code fix must replace the `var` keyword with the inferred type's name:</span></span>

[!code-csharp[var references need to use the inferred types](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VarDeclarations "Declarations made using var must have the type replaced with the inferred type")]

<span data-ttu-id="d3456-361">Estos cambios actualizan las declaraciones de la fila de datos en ambas pruebas.</span><span class="sxs-lookup"><span data-stu-id="d3456-361">These changes update the data row declarations for both tests.</span></span> <span data-ttu-id="d3456-362">El código siguiente muestra estas pruebas con todos los atributos de la fila de datos:</span><span class="sxs-lookup"><span data-stu-id="d3456-362">The following code shows these tests with all data row attributes:</span></span>

[!code-csharp[The finished tests](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FinishedTests "The finished tests for the make const analyzer")]

<span data-ttu-id="d3456-363">Afortunadamente, todos los errores anteriores se pueden tratar con las mismas técnicas que acaba de aprender.</span><span class="sxs-lookup"><span data-stu-id="d3456-363">Fortunately, all of the above bugs can be addressed using the same techniques that you just learned.</span></span>

<span data-ttu-id="d3456-364">Para corregir el primer error, primero abra **DiagnosticAnalyzer.cs** y busque el bucle foreach donde cada uno de los inicializadores de la declaración local se comprueba para asegurarse de que se les asignan valores constantes.</span><span class="sxs-lookup"><span data-stu-id="d3456-364">To fix the first bug, first open **DiagnosticAnalyzer.cs** and locate the foreach loop where each of the local declaration's initializers are checked to ensure that they're assigned with constant values.</span></span> <span data-ttu-id="d3456-365">Inmediatamente _antes_ del primer bucle foreach, llame a `context.SemanticModel.GetTypeInfo()` para recuperar información detallada sobre el tipo declarado de la declaración local:</span><span class="sxs-lookup"><span data-stu-id="d3456-365">Immediately _before_ the first foreach loop, call `context.SemanticModel.GetTypeInfo()` to retrieve detailed information about the declared type of the local declaration:</span></span>

```csharp
var variableTypeName = localDeclaration.Declaration.Type;
var variableType = context.SemanticModel.GetTypeInfo(variableTypeName).ConvertedType;
```

<span data-ttu-id="d3456-366">Después, dentro del bucle `foreach`, compruebe cada inicializador para asegurarse de que se puede convertir al tipo de variable.</span><span class="sxs-lookup"><span data-stu-id="d3456-366">Then, inside your `foreach` loop, check each initializer to make sure it's convertible to the variable type.</span></span> <span data-ttu-id="d3456-367">Agregue la siguiente comprobación después de asegurarse de que el inicializador es una constante:</span><span class="sxs-lookup"><span data-stu-id="d3456-367">Add the following check after ensuring that the initializer is a constant:</span></span>

```csharp
// Ensure that the initializer value can be converted to the type of the
// local declaration without a user-defined conversion.
var conversion = context.SemanticModel.ClassifyConversion(initializer.Value, variableType);
if (!conversion.Exists || conversion.IsUserDefined)
{
    return;
}
```

<span data-ttu-id="d3456-368">El siguiente cambio se basa en el último.</span><span class="sxs-lookup"><span data-stu-id="d3456-368">The next change builds upon the last one.</span></span> <span data-ttu-id="d3456-369">Antes de cerrar la llave del primer bucle foreach, agregue el código siguiente para comprobar el tipo de declaración local cuando la constante es una cadena o null.</span><span class="sxs-lookup"><span data-stu-id="d3456-369">Before the closing curly brace of the first foreach loop, add the following code to check the type of the local declaration when the constant is a string or null.</span></span>

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

<span data-ttu-id="d3456-370">Debe escribir algo más de código en el proveedor de corrección de código para reemplazar la palabra clave `var` por el nombre de tipo correcto.</span><span class="sxs-lookup"><span data-stu-id="d3456-370">You must write a bit more code in your code fix provider to replace the `var` keyword with the correct type name.</span></span> <span data-ttu-id="d3456-371">Vuelva a **CodeFixProvider.cs**.</span><span class="sxs-lookup"><span data-stu-id="d3456-371">Return to **CodeFixProvider.cs**.</span></span> <span data-ttu-id="d3456-372">El código que se va a agregar realiza los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d3456-372">The code you'll add does the following steps:</span></span>

- <span data-ttu-id="d3456-373">Compruebe si la declaración es una declaración `var` y, en su caso:</span><span class="sxs-lookup"><span data-stu-id="d3456-373">Check if the declaration is a `var` declaration, and if it is:</span></span>
- <span data-ttu-id="d3456-374">Cree un tipo para el tipo deducido.</span><span class="sxs-lookup"><span data-stu-id="d3456-374">Create a new type for the inferred type.</span></span>
- <span data-ttu-id="d3456-375">Asegúrese de que la declaración de tipo no es un alias.</span><span class="sxs-lookup"><span data-stu-id="d3456-375">Make sure the type declaration is not an alias.</span></span> <span data-ttu-id="d3456-376">Si es así, es válido declarar `const var`.</span><span class="sxs-lookup"><span data-stu-id="d3456-376">If so, it is legal to declare `const var`.</span></span>
- <span data-ttu-id="d3456-377">Asegúrese de que `var` no es un nombre de tipo en este programa.</span><span class="sxs-lookup"><span data-stu-id="d3456-377">Make sure that `var` isn't a type name in this program.</span></span> <span data-ttu-id="d3456-378">(Si es así, `const var` es válido).</span><span class="sxs-lookup"><span data-stu-id="d3456-378">(If so, `const var` is legal).</span></span>
- <span data-ttu-id="d3456-379">Simplificación del nombre de tipo completo</span><span class="sxs-lookup"><span data-stu-id="d3456-379">Simplify the full type name</span></span>

<span data-ttu-id="d3456-380">Parece mucho código.</span><span class="sxs-lookup"><span data-stu-id="d3456-380">That sounds like a lot of code.</span></span> <span data-ttu-id="d3456-381">Pero no lo es.</span><span class="sxs-lookup"><span data-stu-id="d3456-381">It's not.</span></span> <span data-ttu-id="d3456-382">Reemplace la línea que declara e inicializa `newLocal` con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d3456-382">Replace the line that declares and initializes `newLocal` with the following code.</span></span> <span data-ttu-id="d3456-383">Va inmediatamente después de la inicialización de `newModifiers`:</span><span class="sxs-lookup"><span data-stu-id="d3456-383">It goes immediately after the initialization of `newModifiers`:</span></span>

[!code-csharp[Replace Var designations](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceVar "Replace a var designation with the explicit type")]

<span data-ttu-id="d3456-384">Deberá agregar una directiva `using` para usar el tipo <xref:Microsoft.CodeAnalysis.Simplification.Simplifier>:</span><span class="sxs-lookup"><span data-stu-id="d3456-384">You'll need to add one `using` directive to use the <xref:Microsoft.CodeAnalysis.Simplification.Simplifier> type:</span></span>

```csharp
using Microsoft.CodeAnalysis.Simplification;
```

<span data-ttu-id="d3456-385">Ejecute las pruebas, y todas deberían pasar.</span><span class="sxs-lookup"><span data-stu-id="d3456-385">Run your tests, and they should all pass.</span></span> <span data-ttu-id="d3456-386">Felicítese por ejecutar el analizador terminado.</span><span class="sxs-lookup"><span data-stu-id="d3456-386">Congratulate yourself by running your finished analyzer.</span></span> <span data-ttu-id="d3456-387">Presione <kbd>Ctrl</kbd>+<kbd>F5</kbd> para ejecutar el proyecto de analizador en una segunda instancia de Visual Studio con la extensión de la versión preliminar de Roslyn cargada.</span><span class="sxs-lookup"><span data-stu-id="d3456-387">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to run the analyzer project in a second instance of Visual Studio with the Roslyn Preview extension loaded.</span></span>

- <span data-ttu-id="d3456-388">En la segunda instancia de Visual Studio, cree un proyecto de aplicación de consola de C# y agregue `int x = "abc";` al método Main.</span><span class="sxs-lookup"><span data-stu-id="d3456-388">In the second Visual Studio instance, create a new C# Console Application project and add `int x = "abc";` to the Main method.</span></span> <span data-ttu-id="d3456-389">Gracias a la primera corrección de errores, no se debe notificar ninguna advertencia para esta declaración de variable local (aunque hay un error del compilador según lo esperado).</span><span class="sxs-lookup"><span data-stu-id="d3456-389">Thanks to the first bug fix, no warning should be reported for this local variable declaration (though there's a compiler error as expected).</span></span>
- <span data-ttu-id="d3456-390">A continuación, agregue `object s = "abc";` al método Main.</span><span class="sxs-lookup"><span data-stu-id="d3456-390">Next, add `object s = "abc";` to the Main method.</span></span> <span data-ttu-id="d3456-391">Debido a la segunda corrección de errores, no se debe notificar ninguna advertencia.</span><span class="sxs-lookup"><span data-stu-id="d3456-391">Because of the second bug fix, no warning should be reported.</span></span>
- <span data-ttu-id="d3456-392">Por último, agregue otra variable local que usa la palabra clave `var`.</span><span class="sxs-lookup"><span data-stu-id="d3456-392">Finally, add another local variable that uses the `var` keyword.</span></span> <span data-ttu-id="d3456-393">Observará que se notifica una advertencia y que aparece una sugerencia debajo a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="d3456-393">You'll see that a warning is reported and a suggestion appears beneath to the left.</span></span>
- <span data-ttu-id="d3456-394">Mueva el símbolo de intercalación del editor sobre el subrayado ondulado y presione <kbd>Ctrl</kbd>+<kbd>.</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d3456-394">Move the editor caret over the squiggly underline and press <kbd>Ctrl</kbd>+<kbd>.</kbd>.</span></span> <span data-ttu-id="d3456-395">para mostrar la corrección de código sugerida.</span><span class="sxs-lookup"><span data-stu-id="d3456-395">to display the suggested code fix.</span></span> <span data-ttu-id="d3456-396">Al seleccionar la corrección de código, tenga en cuenta que la palabra clave `var` ahora se trata correctamente.</span><span class="sxs-lookup"><span data-stu-id="d3456-396">Upon selecting your code fix, note that the `var` keyword is now handled correctly.</span></span>

<span data-ttu-id="d3456-397">Por último, agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d3456-397">Finally, add the following code:</span></span>

```csharp
int i = 2;
int j = 32;
int k = i + j;
```

<span data-ttu-id="d3456-398">Después de estos cambios, obtendrá un subrayado ondulado rojo solo en las dos primeras variables.</span><span class="sxs-lookup"><span data-stu-id="d3456-398">After these changes, you get red squiggles only on the first two variables.</span></span> <span data-ttu-id="d3456-399">Agregue `const` a `i` y `j`, y obtendrá una nueva advertencia sobre `k` porque ahora puede ser `const`.</span><span class="sxs-lookup"><span data-stu-id="d3456-399">Add `const` to both `i` and `j`, and you get a new warning on `k` because it can now be `const`.</span></span>

<span data-ttu-id="d3456-400">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="d3456-400">Congratulations!</span></span> <span data-ttu-id="d3456-401">Ha creado su primera extensión de .NET Compiler Platform que realiza un análisis de código sobre la marcha para detectar un problema y proporciona una solución rápida para corregirlo.</span><span class="sxs-lookup"><span data-stu-id="d3456-401">You've created your first .NET Compiler Platform extension that performs on-the-fly code analysis to detect an issue and provides a quick fix to correct it.</span></span> <span data-ttu-id="d3456-402">Durante el proceso, ha aprendido muchas de las API de código que forman parte del SDK de .NET Compiler Platform (API de Roslyn).</span><span class="sxs-lookup"><span data-stu-id="d3456-402">Along the way, you've learned many of the code APIs that are part of the .NET Compiler Platform SDK (Roslyn APIs).</span></span> <span data-ttu-id="d3456-403">Puede comprobar su trabajo con el [ejemplo completo](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/Tutorials/MakeConst) en nuestro repositorio de ejemplos de GitHub.</span><span class="sxs-lookup"><span data-stu-id="d3456-403">You can check your work against the [completed sample](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/Tutorials/MakeConst) in our samples GitHub repository.</span></span>

## <a name="other-resources"></a><span data-ttu-id="d3456-404">Otros recursos</span><span class="sxs-lookup"><span data-stu-id="d3456-404">Other resources</span></span>

- [<span data-ttu-id="d3456-405">Introducción al análisis de sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3456-405">Get started with syntax analysis</span></span>](../get-started/syntax-analysis.md)
- [<span data-ttu-id="d3456-406">Introducción al análisis semántico</span><span class="sxs-lookup"><span data-stu-id="d3456-406">Get started with semantic analysis</span></span>](../get-started/semantic-analysis.md)
