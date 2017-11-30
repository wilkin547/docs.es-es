---
title: "Convenciones de código y estructura de programas (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
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
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b38ba9623a20dcd1be4bc96f4aff1eb646b0a053
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="program-structure-and-code-conventions-visual-basic"></a><span data-ttu-id="b8dda-102">Convenciones de código y estructura de programas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8dda-102">Program Structure and Code Conventions (Visual Basic)</span></span>
<span data-ttu-id="b8dda-103">Esta sección presentan típica [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] estructura del programa, proporciona un sencillo [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] de programa, "¡Hello, World" y se explican [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] convenciones de código.</span><span class="sxs-lookup"><span data-stu-id="b8dda-103">This section introduces the typical [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program structure, provides a simple [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program, "Hello, World", and discusses [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code conventions.</span></span> <span data-ttu-id="b8dda-104">Convenciones de código son sugerencias que se centran no en la lógica de un programa, pero en su estructura física y apariencia.</span><span class="sxs-lookup"><span data-stu-id="b8dda-104">Code conventions are suggestions that focus not on a program's logic but on its physical structure and appearance.</span></span> <span data-ttu-id="b8dda-105">A continuación de ellos, el código será más fácil de leer, comprender y mantener.</span><span class="sxs-lookup"><span data-stu-id="b8dda-105">Following them makes your code easier to read, understand, and maintain.</span></span> <span data-ttu-id="b8dda-106">Convenciones de código pueden incluir, entre otros:</span><span class="sxs-lookup"><span data-stu-id="b8dda-106">Code conventions can include, among others:</span></span>  
  
-   <span data-ttu-id="b8dda-107">Formatos estandarizados para etiquetar y comentar código.</span><span class="sxs-lookup"><span data-stu-id="b8dda-107">Standardized formats for labeling and commenting code.</span></span>  
  
-   <span data-ttu-id="b8dda-108">Directrices para el espaciado, el formato y aplicar sangría al código.</span><span class="sxs-lookup"><span data-stu-id="b8dda-108">Guidelines for spacing, formatting, and indenting code.</span></span>  
  
-   <span data-ttu-id="b8dda-109">Convenciones de nomenclatura para objetos, variables y procedimientos.</span><span class="sxs-lookup"><span data-stu-id="b8dda-109">Naming conventions for objects, variables, and procedures.</span></span>  
  
 <span data-ttu-id="b8dda-110">Los temas siguientes presentan un conjunto de programación directrices para [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programas, junto con ejemplos de uso correcto.</span><span class="sxs-lookup"><span data-stu-id="b8dda-110">The following topics present a set of programming guidelines for [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programs, along with examples of good usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b8dda-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b8dda-111">In This Section</span></span>  
 [<span data-ttu-id="b8dda-112">Estructura de un programa de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b8dda-112">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 <span data-ttu-id="b8dda-113">Proporciona información general de los elementos que componen un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programa.</span><span class="sxs-lookup"><span data-stu-id="b8dda-113">Provides an overview of the elements that make up a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 [<span data-ttu-id="b8dda-114">Procedimiento Main en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b8dda-114">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 <span data-ttu-id="b8dda-115">Describe el procedimiento que actúa como el inicio, elija y control general de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b8dda-115">Discusses the procedure that serves as the starting point and overall control for your application.</span></span>  
  
 [<span data-ttu-id="b8dda-116">Referencias y la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="b8dda-116">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 <span data-ttu-id="b8dda-117">Describe cómo hacer referencia a objetos de otros ensamblados.</span><span class="sxs-lookup"><span data-stu-id="b8dda-117">Discusses how to reference objects in other assemblies.</span></span>  
  
 [<span data-ttu-id="b8dda-118">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b8dda-118">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 <span data-ttu-id="b8dda-119">Describe cómo organizan objetos en los ensamblados de los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="b8dda-119">Describes how namespaces organize objects within assemblies.</span></span>  
  
 [<span data-ttu-id="b8dda-120">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b8dda-120">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 <span data-ttu-id="b8dda-121">Incluye directrices generales para asignar nombres a los procedimientos, constantes, variables, argumentos y objetos.</span><span class="sxs-lookup"><span data-stu-id="b8dda-121">Includes general guidelines for naming procedures, constants, variables, arguments, and objects.</span></span>  
  
 [<span data-ttu-id="b8dda-122">Convenciones de código de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b8dda-122">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 <span data-ttu-id="b8dda-123">Revisa las directrices utilizadas para desarrollar los ejemplos de esta documentación.</span><span class="sxs-lookup"><span data-stu-id="b8dda-123">Reviews the guidelines used in developing the samples in this documentation.</span></span>  
  
 [<span data-ttu-id="b8dda-124">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="b8dda-124">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="b8dda-125">Describe cómo compilación selectiva de bloques concretos de código mientras se indica al compilador que pase por alto otros.</span><span class="sxs-lookup"><span data-stu-id="b8dda-125">Describes how to compile particular blocks of code selectively while directing the compiler to ignore others.</span></span>  
  
 [<span data-ttu-id="b8dda-126">Interrumpir y combinar instrucciones en código</span><span class="sxs-lookup"><span data-stu-id="b8dda-126">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 <span data-ttu-id="b8dda-127">Muestra cómo dividir instrucciones largas en varias líneas y combinar instrucciones cortas en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="b8dda-127">Shows how to divide long statements into multiple lines and combine short statements on one line.</span></span>  
  
 [<span data-ttu-id="b8dda-128">Contraer y ocultar secciones de código</span><span class="sxs-lookup"><span data-stu-id="b8dda-128">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 <span data-ttu-id="b8dda-129">Muestra cómo contraer y ocultar secciones de código en el [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] editor de código.</span><span class="sxs-lookup"><span data-stu-id="b8dda-129">Shows how to collapse and hide sections of code in the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code editor.</span></span>  
  
 [<span data-ttu-id="b8dda-130">Aplicar etiquetas a las instrucciones</span><span class="sxs-lookup"><span data-stu-id="b8dda-130">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 <span data-ttu-id="b8dda-131">Muestra cómo marcar una línea de código que se identifique para su uso con instrucciones como `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="b8dda-131">Shows how to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 [<span data-ttu-id="b8dda-132">Caracteres especiales en el código</span><span class="sxs-lookup"><span data-stu-id="b8dda-132">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 <span data-ttu-id="b8dda-133">Muestra cómo y dónde utilizar caracteres no numéricos y no alfabéticos.</span><span class="sxs-lookup"><span data-stu-id="b8dda-133">Shows how and where to use non-numeric and non-alphabetic characters.</span></span>  
  
 [<span data-ttu-id="b8dda-134">Comentarios en código</span><span class="sxs-lookup"><span data-stu-id="b8dda-134">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 <span data-ttu-id="b8dda-135">Describe cómo agregar comentarios descriptivos al código.</span><span class="sxs-lookup"><span data-stu-id="b8dda-135">Discusses how to add descriptive comments to your code.</span></span>  
  
 [<span data-ttu-id="b8dda-136">Palabras clave como nombres de elementos en código</span><span class="sxs-lookup"><span data-stu-id="b8dda-136">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 <span data-ttu-id="b8dda-137">Describe cómo usar corchetes (`[]`) para delimitar nombres de variable que también son [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] palabras clave.</span><span class="sxs-lookup"><span data-stu-id="b8dda-137">Describes how to use brackets (`[]`) to delimit variable names that are also [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] keywords.</span></span>  
  
 [<span data-ttu-id="b8dda-138">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="b8dda-138">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 <span data-ttu-id="b8dda-139">Describe varias maneras de hacer referencia a los elementos de un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programa.</span><span class="sxs-lookup"><span data-stu-id="b8dda-139">Describes various ways to refer to elements of a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 [<span data-ttu-id="b8dda-140">Limitaciones de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b8dda-140">Visual Basic Limitations</span></span>](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 <span data-ttu-id="b8dda-141">Explica la eliminación de limitaciones conocidas de codificación en [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8dda-141">Discusses the removal of known coding limits within [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b8dda-142">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="b8dda-142">Related Sections</span></span>  
 [<span data-ttu-id="b8dda-143">Convenciones tipográficas y de código</span><span class="sxs-lookup"><span data-stu-id="b8dda-143">Typographic and Code Conventions</span></span>](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 <span data-ttu-id="b8dda-144">Proporciona convenciones de codificación estándares para [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8dda-144">Provides standard coding conventions for [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 [<span data-ttu-id="b8dda-145">Escribir código</span><span class="sxs-lookup"><span data-stu-id="b8dda-145">Writing Code</span></span>](/visualstudio/ide/writing-code-in-the-code-and-text-editor)  
 <span data-ttu-id="b8dda-146">Describe las características que facilitan la escritura y administración del código.</span><span class="sxs-lookup"><span data-stu-id="b8dda-146">Describes features that make it easier for you to write and manage your code.</span></span>
