---
description: 'Más información sobre: compilación condicional en Visual Basic'
title: Compilación condicional
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: e9cb8a5af4dfbf2ffadef8edd8f6583614188391
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476142"
---
# <a name="conditional-compilation-in-visual-basic"></a><span data-ttu-id="e71d0-103">Compilación condicional en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e71d0-103">Conditional Compilation in Visual Basic</span></span>

<span data-ttu-id="e71d0-104">En la *compilación condicional*, determinados bloques de código de un programa se compilan de forma selectiva mientras que otros se omiten.</span><span class="sxs-lookup"><span data-stu-id="e71d0-104">In *conditional compilation*, particular blocks of code in a program are compiled selectively while others are ignored.</span></span>  
  
 <span data-ttu-id="e71d0-105">Por ejemplo, puede que desee escribir instrucciones de depuración que comparen la velocidad de los distintos enfoques para la misma tarea de programación, o puede que desee localizar una aplicación para varios idiomas.</span><span class="sxs-lookup"><span data-stu-id="e71d0-105">For example, you may want to write debugging statements that compare the speed of different approaches to the same programming task, or you may want to localize an application for multiple languages.</span></span> <span data-ttu-id="e71d0-106">Las instrucciones de compilación condicional están diseñadas para ejecutarse durante el tiempo de compilación, no en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e71d0-106">Conditional compilation statements are designed to run during compile time, not at run time.</span></span>  
  
 <span data-ttu-id="e71d0-107">Se denotan los bloques de código que se van a compilar condicionalmente con la `#If...Then...#Else` Directiva.</span><span class="sxs-lookup"><span data-stu-id="e71d0-107">You denote blocks of code to be conditionally compiled with the `#If...Then...#Else` directive.</span></span> <span data-ttu-id="e71d0-108">Por ejemplo, para crear versiones en francés y en alemán de la misma aplicación desde el mismo código fuente, se insertan segmentos de código específicos de la plataforma en las `#If...Then` instrucciones usando las constantes predefinidas `FrenchVersion` y `GermanVersion` .</span><span class="sxs-lookup"><span data-stu-id="e71d0-108">For example, to create French- and German-language versions of the same application from the same source code, you embed platform-specific code segments in `#If...Then` statements using the predefined constants `FrenchVersion` and `GermanVersion`.</span></span> <span data-ttu-id="e71d0-109">En el ejemplo siguiente se muestra cómo:</span><span class="sxs-lookup"><span data-stu-id="e71d0-109">The following example demonstrates how:</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 <span data-ttu-id="e71d0-110">Si establece el valor de la `FrenchVersion` constante de compilación condicional en `True` en tiempo de compilación, se compila el código condicional de la versión en francés.</span><span class="sxs-lookup"><span data-stu-id="e71d0-110">If you set the value of the `FrenchVersion` conditional compilation constant to `True` at compile time, the conditional code for the French version is compiled.</span></span> <span data-ttu-id="e71d0-111">Si establece el valor de la `GermanVersion` constante en `True` , el compilador usa la versión en alemán.</span><span class="sxs-lookup"><span data-stu-id="e71d0-111">If you set the value of the `GermanVersion` constant to `True`, the compiler uses the German version.</span></span> <span data-ttu-id="e71d0-112">Si no se establece ninguno en `True` , se ejecuta el código del último `Else` bloque.</span><span class="sxs-lookup"><span data-stu-id="e71d0-112">If neither is set to `True`, the code in the last `Else` block runs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e71d0-113">La finalización automática no funcionará al editar código y utilizar directivas de compilación condicional si el código no forma parte de la rama actual.</span><span class="sxs-lookup"><span data-stu-id="e71d0-113">Autocompletion will not function when editing code and using conditional compilation directives if the code is not part of the current branch.</span></span>  
  
## <a name="declaring-conditional-compilation-constants"></a><span data-ttu-id="e71d0-114">Declarar constantes de compilación condicional</span><span class="sxs-lookup"><span data-stu-id="e71d0-114">Declaring Conditional Compilation Constants</span></span>  

 <span data-ttu-id="e71d0-115">Puede establecer constantes de compilación condicional de una de estas tres maneras:</span><span class="sxs-lookup"><span data-stu-id="e71d0-115">You can set conditional compilation constants in one of three ways:</span></span>  
  
- <span data-ttu-id="e71d0-116">En el **Diseñador de proyectos**</span><span class="sxs-lookup"><span data-stu-id="e71d0-116">In the **Project Designer**</span></span>  
  
- <span data-ttu-id="e71d0-117">En la línea de comandos cuando se usa el compilador de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="e71d0-117">At the command line when using the command-line compiler</span></span>  
  
- <span data-ttu-id="e71d0-118">En el código</span><span class="sxs-lookup"><span data-stu-id="e71d0-118">In your code</span></span>  
  
 <span data-ttu-id="e71d0-119">Las constantes de compilación condicional tienen un ámbito especial y no se puede tener acceso a ellas desde el código estándar.</span><span class="sxs-lookup"><span data-stu-id="e71d0-119">Conditional compilation constants have a special scope and cannot be accessed from standard code.</span></span> <span data-ttu-id="e71d0-120">El ámbito de una constante de compilación condicional depende de la forma en que se establece.</span><span class="sxs-lookup"><span data-stu-id="e71d0-120">The scope of a conditional compilation constant is dependent on the way it is set.</span></span> <span data-ttu-id="e71d0-121">En la tabla siguiente se muestra el ámbito de las constantes declaradas con cada una de las tres maneras mencionadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e71d0-121">The following table lists the scope of constants declared using each of the three ways mentioned above.</span></span>  
  
|<span data-ttu-id="e71d0-122">Cómo se establece Constant</span><span class="sxs-lookup"><span data-stu-id="e71d0-122">How constant is set</span></span>|<span data-ttu-id="e71d0-123">Ámbito de Constant</span><span class="sxs-lookup"><span data-stu-id="e71d0-123">Scope of constant</span></span>|  
|---|---|  
|<span data-ttu-id="e71d0-124">**Diseñador de proyectos**</span><span class="sxs-lookup"><span data-stu-id="e71d0-124">**Project Designer**</span></span>|<span data-ttu-id="e71d0-125">Público a todos los archivos del proyecto</span><span class="sxs-lookup"><span data-stu-id="e71d0-125">Public to all files in the project</span></span>|  
|<span data-ttu-id="e71d0-126">Línea de comandos</span><span class="sxs-lookup"><span data-stu-id="e71d0-126">Command line</span></span>|<span data-ttu-id="e71d0-127">Público a todos los archivos pasados al compilador de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="e71d0-127">Public to all files passed to the command-line compiler</span></span>|  
|<span data-ttu-id="e71d0-128">`#Const` instrucción en el código</span><span class="sxs-lookup"><span data-stu-id="e71d0-128">`#Const` statement in code</span></span>|<span data-ttu-id="e71d0-129">Privado del archivo en el que se declara</span><span class="sxs-lookup"><span data-stu-id="e71d0-129">Private to the file in which it is declared</span></span>|  
  
|<span data-ttu-id="e71d0-130">Para establecer constantes en el diseñador de proyectos</span><span class="sxs-lookup"><span data-stu-id="e71d0-130">To set constants in the Project Designer</span></span>|  
|---|  
|<span data-ttu-id="e71d0-131">-Antes de crear el archivo ejecutable, establezca las constantes en el **Diseñador de proyectos** siguiendo los pasos que se indican en [Administración de propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties).</span><span class="sxs-lookup"><span data-stu-id="e71d0-131">-   Before creating your executable file, set constants in the **Project Designer** by following the steps provided in [Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties).</span></span>|  
  
|<span data-ttu-id="e71d0-132">Para establecer constantes en la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="e71d0-132">To set constants at the command line</span></span>|  
|---|  
|<span data-ttu-id="e71d0-133">-Use el modificador **-d** para especificar constantes de compilación condicional, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e71d0-133">-   Use the **-d** switch to enter conditional compilation constants, as in the following example:</span></span><br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     <span data-ttu-id="e71d0-134">No se requiere espacio entre el modificador **-d** y la primera constante.</span><span class="sxs-lookup"><span data-stu-id="e71d0-134">No space is required between the **-d** switch and the first constant.</span></span> <span data-ttu-id="e71d0-135">Para obtener más información, vea [-define (Visual Basic)](../../reference/command-line-compiler/define.md).</span><span class="sxs-lookup"><span data-stu-id="e71d0-135">For more information, see [-define (Visual Basic)](../../reference/command-line-compiler/define.md).</span></span><br />     <span data-ttu-id="e71d0-136">Las declaraciones de línea de comandos invalidan las declaraciones especificadas en el **Diseñador de proyectos**, pero no las borran.</span><span class="sxs-lookup"><span data-stu-id="e71d0-136">Command-line declarations override declarations entered in the **Project Designer**, but do not erase them.</span></span> <span data-ttu-id="e71d0-137">Los argumentos establecidos en el **Diseñador de proyectos** permanecen en vigor para las compilaciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="e71d0-137">Arguments set in **Project Designer** remain in effect for subsequent compilations.</span></span><br />     <span data-ttu-id="e71d0-138">Al escribir constantes en el propio código, no hay ninguna regla estricta en cuanto a su ubicación, ya que su ámbito es todo el módulo en el que se declaran.</span><span class="sxs-lookup"><span data-stu-id="e71d0-138">When writing constants in the code itself, there are no strict rules as to their placement, since their scope is the entire module in which they are declared.</span></span>|  
  
|<span data-ttu-id="e71d0-139">Para establecer constantes en el código</span><span class="sxs-lookup"><span data-stu-id="e71d0-139">To set constants in your code</span></span>|  
|---|  
|<span data-ttu-id="e71d0-140">-Coloque las constantes en el bloque de declaración del módulo en el que se usan.</span><span class="sxs-lookup"><span data-stu-id="e71d0-140">-   Place the constants in the declaration block of the module in which they are used.</span></span> <span data-ttu-id="e71d0-141">Esto ayuda a mantener el código organizado y más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="e71d0-141">This helps keep your code organized and easier to read.</span></span>|  
  
## <a name="related-topics"></a><span data-ttu-id="e71d0-142">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e71d0-142">Related Topics</span></span>  
  
|<span data-ttu-id="e71d0-143">Title</span><span class="sxs-lookup"><span data-stu-id="e71d0-143">Title</span></span>|<span data-ttu-id="e71d0-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="e71d0-144">Description</span></span>|  
|---|---|  
|[<span data-ttu-id="e71d0-145">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="e71d0-145">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)|<span data-ttu-id="e71d0-146">Proporciona sugerencias para facilitar la lectura y el mantenimiento del código.</span><span class="sxs-lookup"><span data-stu-id="e71d0-146">Provides suggestions for making your code easy to read and maintain.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="e71d0-147">Referencia</span><span class="sxs-lookup"><span data-stu-id="e71d0-147">Reference</span></span>  

 [<span data-ttu-id="e71d0-148">#Const (directiva)</span><span class="sxs-lookup"><span data-stu-id="e71d0-148">#Const Directive</span></span>](../../language-reference/directives/const-directive.md)  
  
 [<span data-ttu-id="e71d0-149">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="e71d0-149">#If...Then...#Else Directives</span></span>](../../language-reference/directives/if-then-else-directives.md)  
  
 [<span data-ttu-id="e71d0-150">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e71d0-150">-define (Visual Basic)</span></span>](../../reference/command-line-compiler/define.md)
