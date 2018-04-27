---
title: Convenciones de código y estructura de programas (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- coding conventions
- Visual Basic code, coding conventions
- coding conventions [Visual Basic], Visual Basic
- programs [Visual Basic], structure
- program structure [Visual Basic]
- naming conventions [Visual Basic], Visual Basic
- best practices [Visual Basic], coding conventions
- conventions [Visual Basic], Visual Basic coding
- Visual Basic code
- programming [Visual Basic], Visual Basic coding conventions
ms.assetid: dd9be76f-6944-4e78-ad72-0b6084a3fc13
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9980a815d83b21214f1be441d641c3da38c1b541
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="program-structure-and-code-conventions-visual-basic"></a><span data-ttu-id="3db41-102">Convenciones de código y estructura de programas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3db41-102">Program Structure and Code Conventions (Visual Basic)</span></span>
<span data-ttu-id="3db41-103">Esta sección presenta la estructura de programa típica de Visual Basic, proporciona un programa sencillo de Visual Basic, "Hello, World" y describe las convenciones de código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3db41-103">This section introduces the typical Visual Basic program structure, provides a simple Visual Basic program, "Hello, World", and discusses Visual Basic code conventions.</span></span> <span data-ttu-id="3db41-104">Convenciones de código son sugerencias que se centran no en la lógica de un programa, pero en su estructura física y apariencia.</span><span class="sxs-lookup"><span data-stu-id="3db41-104">Code conventions are suggestions that focus not on a program's logic but on its physical structure and appearance.</span></span> <span data-ttu-id="3db41-105">A continuación de ellos, el código será más fácil de leer, comprender y mantener.</span><span class="sxs-lookup"><span data-stu-id="3db41-105">Following them makes your code easier to read, understand, and maintain.</span></span> <span data-ttu-id="3db41-106">Convenciones de código pueden incluir, entre otros:</span><span class="sxs-lookup"><span data-stu-id="3db41-106">Code conventions can include, among others:</span></span>  
  
-   <span data-ttu-id="3db41-107">Formatos estandarizados para etiquetar y comentar código.</span><span class="sxs-lookup"><span data-stu-id="3db41-107">Standardized formats for labeling and commenting code.</span></span>  
  
-   <span data-ttu-id="3db41-108">Directrices para el espaciado, el formato y aplicar sangría al código.</span><span class="sxs-lookup"><span data-stu-id="3db41-108">Guidelines for spacing, formatting, and indenting code.</span></span>  
  
-   <span data-ttu-id="3db41-109">Convenciones de nomenclatura para objetos, variables y procedimientos.</span><span class="sxs-lookup"><span data-stu-id="3db41-109">Naming conventions for objects, variables, and procedures.</span></span>  
  
 <span data-ttu-id="3db41-110">Los siguientes temas proporciona un conjunto de instrucciones de programación para los programas de Visual Basic, junto con ejemplos de uso correcto.</span><span class="sxs-lookup"><span data-stu-id="3db41-110">The following topics present a set of programming guidelines for Visual Basic programs, along with examples of good usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3db41-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3db41-111">In This Section</span></span>  
 [<span data-ttu-id="3db41-112">Estructura de un programa de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3db41-112">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 <span data-ttu-id="3db41-113">Proporciona información general de los elementos que componen un programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3db41-113">Provides an overview of the elements that make up a Visual Basic program.</span></span>  
  
 [<span data-ttu-id="3db41-114">Procedimiento Main en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3db41-114">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 <span data-ttu-id="3db41-115">Describe el procedimiento que actúa como el inicio, elija y control general de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3db41-115">Discusses the procedure that serves as the starting point and overall control for your application.</span></span>  
  
 [<span data-ttu-id="3db41-116">Referencias y la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="3db41-116">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 <span data-ttu-id="3db41-117">Describe cómo hacer referencia a objetos de otros ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3db41-117">Discusses how to reference objects in other assemblies.</span></span>  
  
 [<span data-ttu-id="3db41-118">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3db41-118">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 <span data-ttu-id="3db41-119">Describe cómo organizan objetos en los ensamblados de los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="3db41-119">Describes how namespaces organize objects within assemblies.</span></span>  
  
 [<span data-ttu-id="3db41-120">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3db41-120">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 <span data-ttu-id="3db41-121">Incluye directrices generales para asignar nombres a los procedimientos, constantes, variables, argumentos y objetos.</span><span class="sxs-lookup"><span data-stu-id="3db41-121">Includes general guidelines for naming procedures, constants, variables, arguments, and objects.</span></span>  
  
 [<span data-ttu-id="3db41-122">Convenciones de código de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3db41-122">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 <span data-ttu-id="3db41-123">Revisa las directrices utilizadas para desarrollar los ejemplos de esta documentación.</span><span class="sxs-lookup"><span data-stu-id="3db41-123">Reviews the guidelines used in developing the samples in this documentation.</span></span>  
  
 [<span data-ttu-id="3db41-124">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="3db41-124">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="3db41-125">Describe cómo compilación selectiva de bloques concretos de código mientras se indica al compilador que pase por alto otros.</span><span class="sxs-lookup"><span data-stu-id="3db41-125">Describes how to compile particular blocks of code selectively while directing the compiler to ignore others.</span></span>  
  
 [<span data-ttu-id="3db41-126">Interrumpir y combinar instrucciones en código</span><span class="sxs-lookup"><span data-stu-id="3db41-126">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 <span data-ttu-id="3db41-127">Muestra cómo dividir instrucciones largas en varias líneas y combinar instrucciones cortas en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="3db41-127">Shows how to divide long statements into multiple lines and combine short statements on one line.</span></span>  
  
 [<span data-ttu-id="3db41-128">Contraer y ocultar secciones de código</span><span class="sxs-lookup"><span data-stu-id="3db41-128">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 <span data-ttu-id="3db41-129">Muestra cómo contraer y ocultar secciones de código en Visual Basic en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="3db41-129">Shows how to collapse and hide sections of code in the Visual Basic code editor.</span></span>  
  
 [<span data-ttu-id="3db41-130">Aplicar etiquetas a las instrucciones</span><span class="sxs-lookup"><span data-stu-id="3db41-130">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 <span data-ttu-id="3db41-131">Muestra cómo marcar una línea de código que se identifique para su uso con instrucciones como `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="3db41-131">Shows how to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 [<span data-ttu-id="3db41-132">Caracteres especiales en el código</span><span class="sxs-lookup"><span data-stu-id="3db41-132">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 <span data-ttu-id="3db41-133">Muestra cómo y dónde utilizar caracteres no numéricos y no alfabéticos.</span><span class="sxs-lookup"><span data-stu-id="3db41-133">Shows how and where to use non-numeric and non-alphabetic characters.</span></span>  
  
 [<span data-ttu-id="3db41-134">Comentarios en código</span><span class="sxs-lookup"><span data-stu-id="3db41-134">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 <span data-ttu-id="3db41-135">Describe cómo agregar comentarios descriptivos al código.</span><span class="sxs-lookup"><span data-stu-id="3db41-135">Discusses how to add descriptive comments to your code.</span></span>  
  
 [<span data-ttu-id="3db41-136">Palabras clave como nombres de elementos en código</span><span class="sxs-lookup"><span data-stu-id="3db41-136">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 <span data-ttu-id="3db41-137">Describe cómo usar corchetes (`[]`) para delimitar nombres de variable que también son palabras clave de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3db41-137">Describes how to use brackets (`[]`) to delimit variable names that are also Visual Basic keywords.</span></span>  
  
 [<span data-ttu-id="3db41-138">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="3db41-138">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 <span data-ttu-id="3db41-139">Describe varias maneras para hacer referencia a los elementos de un programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3db41-139">Describes various ways to refer to elements of a Visual Basic program.</span></span>  
  
 [<span data-ttu-id="3db41-140">Limitaciones de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3db41-140">Visual Basic Limitations</span></span>](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 <span data-ttu-id="3db41-141">Explica la eliminación de las limitaciones de código conocidas en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3db41-141">Discusses the removal of known coding limits within Visual Basic.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3db41-142">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="3db41-142">Related Sections</span></span>  
 [<span data-ttu-id="3db41-143">Convenciones tipográficas y de código</span><span class="sxs-lookup"><span data-stu-id="3db41-143">Typographic and Code Conventions</span></span>](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 <span data-ttu-id="3db41-144">Proporciona convenciones de codificación estándares de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3db41-144">Provides standard coding conventions for Visual Basic.</span></span>  
  
 [<span data-ttu-id="3db41-145">Escribir código</span><span class="sxs-lookup"><span data-stu-id="3db41-145">Writing Code</span></span>](/visualstudio/ide/writing-code-in-the-code-and-text-editor)  
 <span data-ttu-id="3db41-146">Describe las características que facilitan la escritura y administración del código.</span><span class="sxs-lookup"><span data-stu-id="3db41-146">Describes features that make it easier for you to write and manage your code.</span></span>
