---
title: "Compilación condicional en Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 559380dc9baceb2fba4dca782e83f335f1bcd92d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="conditional-compilation-in-visual-basic"></a><span data-ttu-id="9f903-102">Compilación condicional en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f903-102">Conditional Compilation in Visual Basic</span></span>
<span data-ttu-id="9f903-103">En *compilación condicional*, bloques concretos de código en un programa se compilan de forma selectiva mientras que otros se omiten.</span><span class="sxs-lookup"><span data-stu-id="9f903-103">In *conditional compilation*, particular blocks of code in a program are compiled selectively while others are ignored.</span></span>  
  
 <span data-ttu-id="9f903-104">Por ejemplo, puede que desee escribir instrucciones de depuración que comparen la velocidad de enfoques diferentes en la misma tarea de programación, o bien puede adaptar una aplicación para varios idiomas.</span><span class="sxs-lookup"><span data-stu-id="9f903-104">For example, you may want to write debugging statements that compare the speed of different approaches to the same programming task, or you may want to localize an application for multiple languages.</span></span> <span data-ttu-id="9f903-105">Instrucciones de compilación condicional están diseñadas para ejecutarse durante el tiempo de compilación, no en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9f903-105">Conditional compilation statements are designed to run during compile time, not at run time.</span></span>  
  
 <span data-ttu-id="9f903-106">Denota bloques de código que se compilarán con la `#If...Then...#Else` directiva.</span><span class="sxs-lookup"><span data-stu-id="9f903-106">You denote blocks of code to be conditionally compiled with the `#If...Then...#Else` directive.</span></span> <span data-ttu-id="9f903-107">Por ejemplo, para crear francés y alemán versiones de la misma aplicación desde el mismo código fuente, incruste segmentos de código específico de plataforma en `#If...Then` instrucciones mediante las constantes predefinidas `FrenchVersion` y `GermanVersion`.</span><span class="sxs-lookup"><span data-stu-id="9f903-107">For example, to create French- and German-language versions of the same application from the same source code, you embed platform-specific code segments in `#If...Then` statements using the predefined constants `FrenchVersion` and `GermanVersion`.</span></span> <span data-ttu-id="9f903-108">En el ejemplo siguiente se muestra cómo:</span><span class="sxs-lookup"><span data-stu-id="9f903-108">The following example demonstrates how:</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#5](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/conditional-compilation_1.vb)]  
  
 <span data-ttu-id="9f903-109">Si establece el valor de la `FrenchVersion` constante de compilación condicional para `True` en tiempo de compilación, se compila el código condicional de la versión en francés.</span><span class="sxs-lookup"><span data-stu-id="9f903-109">If you set the value of the `FrenchVersion` conditional compilation constant to `True` at compile time, the conditional code for the French version is compiled.</span></span> <span data-ttu-id="9f903-110">Si establece el valor de la `GermanVersion` constante a `True`, el compilador usa la versión en alemán.</span><span class="sxs-lookup"><span data-stu-id="9f903-110">If you set the value of the `GermanVersion` constant to `True`, the compiler uses the German version.</span></span> <span data-ttu-id="9f903-111">Si no está establecida `True`, el código en los últimos `Else` bloquear ejecuciones.</span><span class="sxs-lookup"><span data-stu-id="9f903-111">If neither is set to `True`, the code in the last `Else` block runs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f903-112">Autocompletar serán no funcionará al editar código y utiliza directivas de compilación condicional si el código no forma parte de la rama actual.</span><span class="sxs-lookup"><span data-stu-id="9f903-112">Autocompletion will not function when editing code and using conditional compilation directives if the code is not part of the current branch.</span></span>  
  
## <a name="declaring-conditional-compilation-constants"></a><span data-ttu-id="9f903-113">Declarar constantes de compilación condicional</span><span class="sxs-lookup"><span data-stu-id="9f903-113">Declaring Conditional Compilation Constants</span></span>  
 <span data-ttu-id="9f903-114">Puede establecer las constantes de compilación condicional en una de estas tres maneras:</span><span class="sxs-lookup"><span data-stu-id="9f903-114">You can set conditional compilation constants in one of three ways:</span></span>  
  
-   <span data-ttu-id="9f903-115">En el **Diseñador de proyectos**</span><span class="sxs-lookup"><span data-stu-id="9f903-115">In the **Project Designer**</span></span>  
  
-   <span data-ttu-id="9f903-116">En la línea de comandos cuando se usa el compilador de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="9f903-116">At the command line when using the command-line compiler</span></span>  
  
-   <span data-ttu-id="9f903-117">En el código</span><span class="sxs-lookup"><span data-stu-id="9f903-117">In your code</span></span>  
  
 <span data-ttu-id="9f903-118">Constantes de compilación condicional tienen un ámbito especial y no se pueden tener acceso desde el código estándar.</span><span class="sxs-lookup"><span data-stu-id="9f903-118">Conditional compilation constants have a special scope and cannot be accessed from standard code.</span></span> <span data-ttu-id="9f903-119">El ámbito de una constante de compilación condicional es dependiente de la manera en que se establece.</span><span class="sxs-lookup"><span data-stu-id="9f903-119">The scope of a conditional compilation constant is dependent on the way it is set.</span></span> <span data-ttu-id="9f903-120">En la tabla siguiente muestra el ámbito de las constantes declaradas con cada uno de los tres métodos mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9f903-120">The following table lists the scope of constants declared using each of the three ways mentioned above.</span></span>  
  
|<span data-ttu-id="9f903-121">¿Cómo se establece (constante)</span><span class="sxs-lookup"><span data-stu-id="9f903-121">How constant is set</span></span>|<span data-ttu-id="9f903-122">Ámbito de constante</span><span class="sxs-lookup"><span data-stu-id="9f903-122">Scope of constant</span></span>|  
|---|---|  
|<span data-ttu-id="9f903-123">**Diseñador de proyectos**</span><span class="sxs-lookup"><span data-stu-id="9f903-123">**Project Designer**</span></span>|<span data-ttu-id="9f903-124">Público para todos los archivos en el proyecto</span><span class="sxs-lookup"><span data-stu-id="9f903-124">Public to all files in the project</span></span>|  
|<span data-ttu-id="9f903-125">Línea de comandos</span><span class="sxs-lookup"><span data-stu-id="9f903-125">Command line</span></span>|<span data-ttu-id="9f903-126">Público para todos los archivos que se pasó al compilador de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="9f903-126">Public to all files passed to the command-line compiler</span></span>|  
|<span data-ttu-id="9f903-127">`#Const`instrucción de código</span><span class="sxs-lookup"><span data-stu-id="9f903-127">`#Const` statement in code</span></span>|<span data-ttu-id="9f903-128">Privado para el archivo en el que se declara</span><span class="sxs-lookup"><span data-stu-id="9f903-128">Private to the file in which it is declared</span></span>|  
  
|<span data-ttu-id="9f903-129">Para definir constantes en el Diseñador de proyectos</span><span class="sxs-lookup"><span data-stu-id="9f903-129">To set constants in the Project Designer</span></span>|  
|---|  
|<span data-ttu-id="9f903-130">-Antes de crear el archivo ejecutable, defina las constantes en el **Diseñador de proyectos** siguiendo los pasos indicados en [administrar proyecto y propiedades de la solución](/visualstudio/ide/managing-project-and-solution-properties).</span><span class="sxs-lookup"><span data-stu-id="9f903-130">-   Before creating your executable file, set constants in the **Project Designer** by following the steps provided in [Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties).</span></span>|  
  
|<span data-ttu-id="9f903-131">Para definir constantes en la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="9f903-131">To set constants at the command line</span></span>|  
|---|  
|<span data-ttu-id="9f903-132">-Use el **/d** conmutador para especificar constantes de compilación condicional, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9f903-132">-   Use the **/d** switch to enter conditional compilation constants, as in the following example:</span></span><br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     <span data-ttu-id="9f903-133">No se requiere ningún espacio entre el **/d** conmutador y la primera constante.</span><span class="sxs-lookup"><span data-stu-id="9f903-133">No space is required between the **/d** switch and the first constant.</span></span> <span data-ttu-id="9f903-134">Para obtener más información, consulte [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span><span class="sxs-lookup"><span data-stu-id="9f903-134">For more information, see [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span></span><br />     <span data-ttu-id="9f903-135">Las declaraciones de la línea de comandos reemplazan a las especificadas en el **Diseñador de proyectos**, pero no las borran.</span><span class="sxs-lookup"><span data-stu-id="9f903-135">Command-line declarations override declarations entered in the **Project Designer**, but do not erase them.</span></span> <span data-ttu-id="9f903-136">Argumentos que se establecen **Diseñador de proyectos** siguen en vigor para las compilaciones subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="9f903-136">Arguments set in **Project Designer** remain in effect for subsequent compilations.</span></span><br />     <span data-ttu-id="9f903-137">Al escribir constantes en el propio código, no hay ninguna regla estricta en cuanto a su ubicación, puesto que su ámbito es el módulo completo en el que se declaran.</span><span class="sxs-lookup"><span data-stu-id="9f903-137">When writing constants in the code itself, there are no strict rules as to their placement, since their scope is the entire module in which they are declared.</span></span>|  
  
|<span data-ttu-id="9f903-138">Para definir constantes en el código</span><span class="sxs-lookup"><span data-stu-id="9f903-138">To set constants in your code</span></span>|  
|---|  
|<span data-ttu-id="9f903-139">-Coloque las constantes en el bloque de declaración del módulo en el que se utilizan.</span><span class="sxs-lookup"><span data-stu-id="9f903-139">-   Place the constants in the declaration block of the module in which they are used.</span></span> <span data-ttu-id="9f903-140">Esto ayuda a mantener el código organizada y fáciles de leer.</span><span class="sxs-lookup"><span data-stu-id="9f903-140">This helps keep your code organized and easier to read.</span></span>|  
  
## <a name="related-topics"></a><span data-ttu-id="9f903-141">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="9f903-141">Related Topics</span></span>  
  
|<span data-ttu-id="9f903-142">Título</span><span class="sxs-lookup"><span data-stu-id="9f903-142">Title</span></span>|<span data-ttu-id="9f903-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f903-143">Description</span></span>|  
|---|---|  
|[<span data-ttu-id="9f903-144">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="9f903-144">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|<span data-ttu-id="9f903-145">Proporciona sugerencias para hacer que su código sea fácil de leer y mantener.</span><span class="sxs-lookup"><span data-stu-id="9f903-145">Provides suggestions for making your code easy to read and maintain.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="9f903-146">Referencia</span><span class="sxs-lookup"><span data-stu-id="9f903-146">Reference</span></span>  
 [<span data-ttu-id="9f903-147">#Const (directiva)</span><span class="sxs-lookup"><span data-stu-id="9f903-147">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [<span data-ttu-id="9f903-148">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="9f903-148">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [<span data-ttu-id="9f903-149">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f903-149">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)
