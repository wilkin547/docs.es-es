---
description: 'Más información acerca de: estructura de un programa de Visual Basic'
title: Estructura de un programa de Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], Visual Basic
- program structure [Visual Basic], Visual Basic
- procedures [Visual Basic], structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
ms.openlocfilehash: e5941b1cbdfdc460e3e860a5449e8ccae0673612
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468205"
---
# <a name="structure-of-a-visual-basic-program"></a><span data-ttu-id="1cf87-103">Estructura de un programa de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1cf87-103">Structure of a Visual Basic Program</span></span>

<span data-ttu-id="1cf87-104">Un programa de Visual Basic se crea a partir de los bloques de creación estándar.</span><span class="sxs-lookup"><span data-stu-id="1cf87-104">A Visual Basic program is built up from standard building blocks.</span></span> <span data-ttu-id="1cf87-105">Una *solución* consta de uno o varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="1cf87-105">A *solution* comprises one or more projects.</span></span> <span data-ttu-id="1cf87-106">Un *proyecto* A su vez puede contener uno o más ensamblados.</span><span class="sxs-lookup"><span data-stu-id="1cf87-106">A *project* in turn can contain one or more assemblies.</span></span> <span data-ttu-id="1cf87-107">Cada *ensamblado* se compila a partir de uno o más archivos de código fuente.</span><span class="sxs-lookup"><span data-stu-id="1cf87-107">Each *assembly* is compiled from one or more source files.</span></span> <span data-ttu-id="1cf87-108">Un *archivo de código fuente* proporciona la definición y la implementación de clases, estructuras, módulos e interfaces, que en última instancia contienen todo el código.</span><span class="sxs-lookup"><span data-stu-id="1cf87-108">A *source file* provides the definition and implementation of classes, structures, modules, and interfaces, which ultimately contain all your code.</span></span>  
  
 <span data-ttu-id="1cf87-109">Para obtener más información sobre estos bloques de creación de un programa de Visual Basic, vea [soluciones y proyectos](/visualstudio/ide/solutions-and-projects-in-visual-studio) y [ensamblados en .net](../../../standard/assembly/index.md).</span><span class="sxs-lookup"><span data-stu-id="1cf87-109">For more information about these building blocks of a Visual Basic program, see [Solutions and Projects](/visualstudio/ide/solutions-and-projects-in-visual-studio) and [Assemblies in .NET](../../../standard/assembly/index.md).</span></span>  
  
## <a name="file-level-programming-elements"></a><span data-ttu-id="1cf87-110">File-Level elementos de programación</span><span class="sxs-lookup"><span data-stu-id="1cf87-110">File-Level Programming Elements</span></span>  

 <span data-ttu-id="1cf87-111">Al iniciar un proyecto o un archivo y abrir el editor de código, verá que ya hay código en su lugar y en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="1cf87-111">When you start a project or file and open the code editor, you see some code already in place and in the correct order.</span></span> <span data-ttu-id="1cf87-112">Cualquier código que escriba debe seguir la siguiente secuencia:</span><span class="sxs-lookup"><span data-stu-id="1cf87-112">Any code that you write should follow the following sequence:</span></span>  
  
1. <span data-ttu-id="1cf87-113">`Option` afirma</span><span class="sxs-lookup"><span data-stu-id="1cf87-113">`Option` statements</span></span>  
  
2. <span data-ttu-id="1cf87-114">`Imports` afirma</span><span class="sxs-lookup"><span data-stu-id="1cf87-114">`Imports` statements</span></span>  
  
3. <span data-ttu-id="1cf87-115">`Namespace` instrucciones y elementos de nivel de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="1cf87-115">`Namespace` statements and namespace-level elements</span></span>  
  
 <span data-ttu-id="1cf87-116">Si escribe instrucciones en un orden diferente, pueden producirse errores de compilación.</span><span class="sxs-lookup"><span data-stu-id="1cf87-116">If you enter statements in a different order, compilation errors can result.</span></span>  
  
 <span data-ttu-id="1cf87-117">Un programa también puede contener instrucciones de compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="1cf87-117">A program can also contain conditional compilation statements.</span></span> <span data-ttu-id="1cf87-118">Puede entremezclarlos en el archivo de código fuente entre las instrucciones de la secuencia anterior.</span><span class="sxs-lookup"><span data-stu-id="1cf87-118">You can intersperse these in the source file among the statements of the preceding sequence.</span></span>  
  
### <a name="option-statements"></a><span data-ttu-id="1cf87-119">Instrucciones Option</span><span class="sxs-lookup"><span data-stu-id="1cf87-119">Option Statements</span></span>  

 <span data-ttu-id="1cf87-120">`Option` las instrucciones establecen reglas de la base para el código subsiguiente, lo que ayuda a evitar errores de sintaxis y lógica.</span><span class="sxs-lookup"><span data-stu-id="1cf87-120">`Option` statements establish ground rules for subsequent code, helping prevent syntax and logic errors.</span></span> <span data-ttu-id="1cf87-121">La [instrucción Option Explicit](../../language-reference/statements/option-explicit-statement.md) garantiza que todas las variables se declaran y se escriben correctamente, lo que reduce el tiempo de depuración.</span><span class="sxs-lookup"><span data-stu-id="1cf87-121">The [Option Explicit Statement](../../language-reference/statements/option-explicit-statement.md) ensures that all variables are declared and spelled correctly, which reduces debugging time.</span></span> <span data-ttu-id="1cf87-122">La [instrucción Option Strict](../../language-reference/statements/option-strict-statement.md) ayuda a minimizar los errores lógicos y la pérdida de datos que se pueden producir al trabajar entre variables de tipos de datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="1cf87-122">The [Option Strict Statement](../../language-reference/statements/option-strict-statement.md) helps to minimize logic errors and data loss that can occur when you work between variables of different data types.</span></span> <span data-ttu-id="1cf87-123">La [instrucción Option Compare](../../language-reference/statements/option-compare-statement.md) especifica el modo en que se comparan las cadenas entre sí, en función de sus `Binary` `Text` valores o.</span><span class="sxs-lookup"><span data-stu-id="1cf87-123">The [Option Compare Statement](../../language-reference/statements/option-compare-statement.md) specifies the way strings are compared to each other, based on either their `Binary` or `Text` values.</span></span>  
  
### <a name="imports-statements"></a><span data-ttu-id="1cf87-124">Instrucciones Imports</span><span class="sxs-lookup"><span data-stu-id="1cf87-124">Imports Statements</span></span>  

 <span data-ttu-id="1cf87-125">Puede incluir una [instrucción Imports (espacio de nombres y tipo .net)](../../language-reference/statements/imports-statement-net-namespace-and-type.md) para importar nombres definidos fuera del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1cf87-125">You can include an [Imports Statement (.NET Namespace and Type)](../../language-reference/statements/imports-statement-net-namespace-and-type.md) to import names defined outside your project.</span></span> <span data-ttu-id="1cf87-126">Una `Imports` instrucción permite que el código haga referencia a clases y otros tipos definidos en el espacio de nombres importado, sin tener que calificarlos.</span><span class="sxs-lookup"><span data-stu-id="1cf87-126">An `Imports` statement allows your code to refer to classes and other types defined within the imported namespace, without having to qualify them.</span></span> <span data-ttu-id="1cf87-127">Puede utilizar tantas `Imports` instrucciones como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="1cf87-127">You can use as many `Imports` statements as appropriate.</span></span> <span data-ttu-id="1cf87-128">Para obtener más información, vea [referencias y la instrucción Imports](references-and-the-imports-statement.md).</span><span class="sxs-lookup"><span data-stu-id="1cf87-128">For more information, see [References and the Imports Statement](references-and-the-imports-statement.md).</span></span>  
  
### <a name="namespace-statements"></a><span data-ttu-id="1cf87-129">Instrucciones de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="1cf87-129">Namespace Statements</span></span>  

 <span data-ttu-id="1cf87-130">Los espacios de nombres ayudan a organizar y clasificar los elementos de programación para facilitar la agrupación y el acceso.</span><span class="sxs-lookup"><span data-stu-id="1cf87-130">Namespaces help you organize and classify your programming elements for ease of grouping and accessing.</span></span> <span data-ttu-id="1cf87-131">Use la [instrucción namespace](../../language-reference/statements/namespace-statement.md) para clasificar las siguientes instrucciones dentro de un espacio de nombres determinado.</span><span class="sxs-lookup"><span data-stu-id="1cf87-131">You use the [Namespace Statement](../../language-reference/statements/namespace-statement.md) to classify the following statements within a particular namespace.</span></span> <span data-ttu-id="1cf87-132">Para más información, consulte [Espacios de nombres en Visual Basic](namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="1cf87-132">For more information, see [Namespaces in Visual Basic](namespaces.md).</span></span>  
  
### <a name="conditional-compilation-statements"></a><span data-ttu-id="1cf87-133">Instrucciones de compilación condicional</span><span class="sxs-lookup"><span data-stu-id="1cf87-133">Conditional Compilation Statements</span></span>  

 <span data-ttu-id="1cf87-134">Las instrucciones de compilación condicional pueden aparecer prácticamente en cualquier parte del archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="1cf87-134">Conditional compilation statements can appear almost anywhere in your source file.</span></span> <span data-ttu-id="1cf87-135">Hacen que las partes del código se incluyan o excluyan en tiempo de compilación en función de ciertas condiciones.</span><span class="sxs-lookup"><span data-stu-id="1cf87-135">They cause parts of your code to be included or excluded at compile time depending on certain conditions.</span></span> <span data-ttu-id="1cf87-136">También puede usarlos para depurar la aplicación, ya que el código condicional solo se ejecuta en modo de depuración.</span><span class="sxs-lookup"><span data-stu-id="1cf87-136">You can also use them for debugging your application, because conditional code runs in debugging mode only.</span></span> <span data-ttu-id="1cf87-137">Para obtener más información, vea [compilación condicional](conditional-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="1cf87-137">For more information, see [Conditional Compilation](conditional-compilation.md).</span></span>  
  
## <a name="namespace-level-programming-elements"></a><span data-ttu-id="1cf87-138">Namespace-Level elementos de programación</span><span class="sxs-lookup"><span data-stu-id="1cf87-138">Namespace-Level Programming Elements</span></span>  

 <span data-ttu-id="1cf87-139">Las clases, las estructuras y los módulos contienen todo el código del archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="1cf87-139">Classes, structures, and modules contain all the code in your source file.</span></span> <span data-ttu-id="1cf87-140">Son elementos *de nivel de espacio de nombres* , que pueden aparecer dentro de un espacio de nombres o en el nivel de archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="1cf87-140">They are *namespace-level* elements, which can appear within a namespace or at the source file level.</span></span> <span data-ttu-id="1cf87-141">Contienen las declaraciones de todos los demás elementos de programación.</span><span class="sxs-lookup"><span data-stu-id="1cf87-141">They hold the declarations of all other programming elements.</span></span> <span data-ttu-id="1cf87-142">Las interfaces, que definen las signaturas de los elementos, pero no proporcionan ninguna implementación, también aparecen en el nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="1cf87-142">Interfaces, which define element signatures but provide no implementation, also appear at module level.</span></span> <span data-ttu-id="1cf87-143">Para obtener más información sobre los elementos de nivel de módulo, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1cf87-143">For more information on the module-level elements, see the following:</span></span>  
  
- [<span data-ttu-id="1cf87-144">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="1cf87-144">Class Statement</span></span>](../../language-reference/statements/class-statement.md)  
  
- [<span data-ttu-id="1cf87-145">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="1cf87-145">Structure Statement</span></span>](../../language-reference/statements/structure-statement.md)  
  
- [<span data-ttu-id="1cf87-146">Module (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="1cf87-146">Module Statement</span></span>](../../language-reference/statements/module-statement.md)  
  
- [<span data-ttu-id="1cf87-147">Instrucción Interface</span><span class="sxs-lookup"><span data-stu-id="1cf87-147">Interface Statement</span></span>](../../language-reference/statements/interface-statement.md)  
  
 <span data-ttu-id="1cf87-148">Los elementos de datos en el nivel de espacio de nombres son enumeraciones y delegados.</span><span class="sxs-lookup"><span data-stu-id="1cf87-148">Data elements at namespace level are enumerations and delegates.</span></span>  
  
## <a name="module-level-programming-elements"></a><span data-ttu-id="1cf87-149">Module-Level elementos de programación</span><span class="sxs-lookup"><span data-stu-id="1cf87-149">Module-Level Programming Elements</span></span>  

 <span data-ttu-id="1cf87-150">Los procedimientos, operadores, propiedades y eventos son los únicos elementos de programación que pueden contener código ejecutable (instrucciones que realizan acciones en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="1cf87-150">Procedures, operators, properties, and events are the only programming elements that can hold executable code (statements that perform actions at run time).</span></span> <span data-ttu-id="1cf87-151">Son los elementos de *nivel de módulo* del programa.</span><span class="sxs-lookup"><span data-stu-id="1cf87-151">They are the *module-level* elements of your program.</span></span> <span data-ttu-id="1cf87-152">Para obtener más información sobre los elementos de nivel de procedimiento, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1cf87-152">For more information on the procedure-level elements, see the following:</span></span>  
  
- [<span data-ttu-id="1cf87-153">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="1cf87-153">Function Statement</span></span>](../../language-reference/statements/function-statement.md)  
  
- [<span data-ttu-id="1cf87-154">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="1cf87-154">Sub Statement</span></span>](../../language-reference/statements/sub-statement.md)  
  
- [<span data-ttu-id="1cf87-155">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="1cf87-155">Declare Statement</span></span>](../../language-reference/statements/declare-statement.md)  
  
- [<span data-ttu-id="1cf87-156">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="1cf87-156">Operator Statement</span></span>](../../language-reference/statements/operator-statement.md)  
  
- [<span data-ttu-id="1cf87-157">Property Statement</span><span class="sxs-lookup"><span data-stu-id="1cf87-157">Property Statement</span></span>](../../language-reference/statements/property-statement.md)  
  
- [<span data-ttu-id="1cf87-158">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="1cf87-158">Event Statement</span></span>](../../language-reference/statements/event-statement.md)  
  
 <span data-ttu-id="1cf87-159">Los elementos de datos en el nivel de módulo son variables, constantes, enumeraciones y delegados.</span><span class="sxs-lookup"><span data-stu-id="1cf87-159">Data elements at module level are variables, constants, enumerations, and delegates.</span></span>  
  
## <a name="procedure-level-programming-elements"></a><span data-ttu-id="1cf87-160">Procedure-Level elementos de programación</span><span class="sxs-lookup"><span data-stu-id="1cf87-160">Procedure-Level Programming Elements</span></span>  

 <span data-ttu-id="1cf87-161">La mayor parte del contenido de los elementos de *nivel de procedimiento* son instrucciones ejecutables, que constituyen el código en tiempo de ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="1cf87-161">Most of the contents of *procedure-level* elements are executable statements, which constitute the run-time code of your program.</span></span> <span data-ttu-id="1cf87-162">Todo el código ejecutable debe estar en algún procedimiento ( `Function` , `Sub` , `Operator` , `Get` , `Set` , `AddHandler` , `RemoveHandler` , `RaiseEvent` ).</span><span class="sxs-lookup"><span data-stu-id="1cf87-162">All executable code must be in some procedure (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`).</span></span> <span data-ttu-id="1cf87-163">Para más información, vea [Statements](../language-features/statements.md) (Instrucciones).</span><span class="sxs-lookup"><span data-stu-id="1cf87-163">For more information, see [Statements](../language-features/statements.md).</span></span>  
  
 <span data-ttu-id="1cf87-164">Los elementos de datos en el nivel de procedimiento se limitan a las variables locales y a las constantes.</span><span class="sxs-lookup"><span data-stu-id="1cf87-164">Data elements at procedure level are limited to local variables and constants.</span></span>  
  
## <a name="the-main-procedure"></a><span data-ttu-id="1cf87-165">El procedimiento Main</span><span class="sxs-lookup"><span data-stu-id="1cf87-165">The Main Procedure</span></span>  

 <span data-ttu-id="1cf87-166">El `Main` procedimiento es el primer código que se ejecuta cuando se carga la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1cf87-166">The `Main` procedure is the first code to run when your application has been loaded.</span></span> <span data-ttu-id="1cf87-167">`Main` sirve como punto de partida y control general de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1cf87-167">`Main` serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="1cf87-168">Hay cuatro variedades de `Main` :</span><span class="sxs-lookup"><span data-stu-id="1cf87-168">There are four varieties of `Main`:</span></span>  
  
- `Sub Main()`  
  
- `Sub Main(ByVal cmdArgs() As String)`  
  
- `Function Main() As Integer`  
  
- `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 <span data-ttu-id="1cf87-169">La variedad más común de este procedimiento es `Sub Main()` .</span><span class="sxs-lookup"><span data-stu-id="1cf87-169">The most common variety of this procedure is `Sub Main()`.</span></span> <span data-ttu-id="1cf87-170">Para obtener más información, vea el [procedimiento Main en Visual Basic](main-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="1cf87-170">For more information, see [Main Procedure in Visual Basic](main-procedure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cf87-171">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1cf87-171">See also</span></span>

- [<span data-ttu-id="1cf87-172">Procedimiento Main en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1cf87-172">Main Procedure in Visual Basic</span></span>](main-procedure.md)
- [<span data-ttu-id="1cf87-173">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1cf87-173">Visual Basic Naming Conventions</span></span>](naming-conventions.md)
- [<span data-ttu-id="1cf87-174">Limitaciones de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1cf87-174">Visual Basic Limitations</span></span>](limitations.md)
