---
description: 'Más información acerca de: convenciones de código y estructura de programas (Visual Basic)'
title: Convenciones de código y estructura de programas
ms.date: 07/20/2015
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
ms.openlocfilehash: 7d4202ead0550cf54a80eac89c4a4274a22d0315
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468491"
---
# <a name="program-structure-and-code-conventions-visual-basic"></a><span data-ttu-id="b183e-103">Convenciones de código y estructura de programas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b183e-103">Program Structure and Code Conventions (Visual Basic)</span></span>

<span data-ttu-id="b183e-104">En esta sección se presenta la estructura de programas de Visual Basic típica, se proporciona un sencillo programa de Visual Basic, "Hello, World", y se explican las convenciones de código Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b183e-104">This section introduces the typical Visual Basic program structure, provides a simple Visual Basic program, "Hello, World", and discusses Visual Basic code conventions.</span></span> <span data-ttu-id="b183e-105">Las convenciones de código son sugerencias que no se centran en la lógica de un programa, sino en su estructura y apariencia física.</span><span class="sxs-lookup"><span data-stu-id="b183e-105">Code conventions are suggestions that focus not on a program's logic but on its physical structure and appearance.</span></span> <span data-ttu-id="b183e-106">Después, hace que el código sea más fácil de leer, comprender y mantener.</span><span class="sxs-lookup"><span data-stu-id="b183e-106">Following them makes your code easier to read, understand, and maintain.</span></span> <span data-ttu-id="b183e-107">Las convenciones de código pueden incluir, entre otras:</span><span class="sxs-lookup"><span data-stu-id="b183e-107">Code conventions can include, among others:</span></span>  
  
- <span data-ttu-id="b183e-108">Formatos normalizados para etiquetar y comentar código.</span><span class="sxs-lookup"><span data-stu-id="b183e-108">Standardized formats for labeling and commenting code.</span></span>  
  
- <span data-ttu-id="b183e-109">Instrucciones para el espaciado, el formato y la sangría del código.</span><span class="sxs-lookup"><span data-stu-id="b183e-109">Guidelines for spacing, formatting, and indenting code.</span></span>  
  
- <span data-ttu-id="b183e-110">Convenciones de nomenclatura para objetos, variables y procedimientos.</span><span class="sxs-lookup"><span data-stu-id="b183e-110">Naming conventions for objects, variables, and procedures.</span></span>  
  
 <span data-ttu-id="b183e-111">En los siguientes temas se presenta un conjunto de directrices de programación para Visual Basic programas, junto con ejemplos de uso correcto.</span><span class="sxs-lookup"><span data-stu-id="b183e-111">The following topics present a set of programming guidelines for Visual Basic programs, along with examples of good usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b183e-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b183e-112">In This Section</span></span>  

 [<span data-ttu-id="b183e-113">Estructura de un programa de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b183e-113">Structure of a Visual Basic Program</span></span>](structure-of-a-visual-basic-program.md)  
 <span data-ttu-id="b183e-114">Proporciona información general sobre los elementos que componen un programa Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b183e-114">Provides an overview of the elements that make up a Visual Basic program.</span></span>  
  
 [<span data-ttu-id="b183e-115">Procedimiento Main en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b183e-115">Main Procedure in Visual Basic</span></span>](main-procedure.md)  
 <span data-ttu-id="b183e-116">Describe el procedimiento que sirve como punto de partida y control general de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b183e-116">Discusses the procedure that serves as the starting point and overall control for your application.</span></span>  
  
 [<span data-ttu-id="b183e-117">Referencias y la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="b183e-117">References and the Imports Statement</span></span>](references-and-the-imports-statement.md)  
 <span data-ttu-id="b183e-118">Describe cómo hacer referencia a objetos de otros ensamblados.</span><span class="sxs-lookup"><span data-stu-id="b183e-118">Discusses how to reference objects in other assemblies.</span></span>  
  
 [<span data-ttu-id="b183e-119">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b183e-119">Namespaces in Visual Basic</span></span>](namespaces.md)  
 <span data-ttu-id="b183e-120">Describe cómo los espacios de nombres organizan los objetos dentro de los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="b183e-120">Describes how namespaces organize objects within assemblies.</span></span>  
  
 [<span data-ttu-id="b183e-121">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b183e-121">Visual Basic Naming Conventions</span></span>](naming-conventions.md)  
 <span data-ttu-id="b183e-122">Incluye directrices generales para asignar nombres a procedimientos, constantes, variables, argumentos y objetos.</span><span class="sxs-lookup"><span data-stu-id="b183e-122">Includes general guidelines for naming procedures, constants, variables, arguments, and objects.</span></span>  
  
 [<span data-ttu-id="b183e-123">Convenciones de código de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b183e-123">Visual Basic Coding Conventions</span></span>](coding-conventions.md)  
 <span data-ttu-id="b183e-124">Revisa las instrucciones usadas en el desarrollo de los ejemplos de esta documentación.</span><span class="sxs-lookup"><span data-stu-id="b183e-124">Reviews the guidelines used in developing the samples in this documentation.</span></span>  
  
 [<span data-ttu-id="b183e-125">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="b183e-125">Conditional Compilation</span></span>](conditional-compilation.md)  
 <span data-ttu-id="b183e-126">Describe cómo compilar de forma selectiva bloques concretos de código mientras se indica al compilador que omita otros.</span><span class="sxs-lookup"><span data-stu-id="b183e-126">Describes how to compile particular blocks of code selectively while directing the compiler to ignore others.</span></span>  
  
 [<span data-ttu-id="b183e-127">Procedimiento Interrupción y combinación de instrucciones en código</span><span class="sxs-lookup"><span data-stu-id="b183e-127">How to: Break and Combine Statements in Code</span></span>](how-to-break-and-combine-statements-in-code.md)  
 <span data-ttu-id="b183e-128">Muestra cómo dividir instrucciones largas en varias líneas y combinar instrucciones cortas en una sola línea.</span><span class="sxs-lookup"><span data-stu-id="b183e-128">Shows how to divide long statements into multiple lines and combine short statements on one line.</span></span>  
  
 [<span data-ttu-id="b183e-129">Procedimiento Contracción y ocultación de secciones de código</span><span class="sxs-lookup"><span data-stu-id="b183e-129">How to: Collapse and Hide Sections of Code</span></span>](how-to-collapse-and-hide-sections-of-code.md)  
 <span data-ttu-id="b183e-130">Muestra cómo contraer y ocultar secciones de código en el editor de código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b183e-130">Shows how to collapse and hide sections of code in the Visual Basic code editor.</span></span>  
  
 [<span data-ttu-id="b183e-131">Procedimiento Instrucciones de etiquetas</span><span class="sxs-lookup"><span data-stu-id="b183e-131">How to: Label Statements</span></span>](how-to-label-statements.md)  
 <span data-ttu-id="b183e-132">Muestra cómo marcar una línea de código para identificarla para su uso con instrucciones como `On Error Goto` .</span><span class="sxs-lookup"><span data-stu-id="b183e-132">Shows how to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 [<span data-ttu-id="b183e-133">Caracteres especiales en el código</span><span class="sxs-lookup"><span data-stu-id="b183e-133">Special Characters in Code</span></span>](special-characters-in-code.md)  
 <span data-ttu-id="b183e-134">Muestra cómo y dónde utilizar caracteres no numéricos y no alfabéticos.</span><span class="sxs-lookup"><span data-stu-id="b183e-134">Shows how and where to use non-numeric and non-alphabetic characters.</span></span>  
  
 [<span data-ttu-id="b183e-135">Comentarios en código</span><span class="sxs-lookup"><span data-stu-id="b183e-135">Comments in Code</span></span>](comments-in-code.md)  
 <span data-ttu-id="b183e-136">Describe cómo agregar comentarios descriptivos al código.</span><span class="sxs-lookup"><span data-stu-id="b183e-136">Discusses how to add descriptive comments to your code.</span></span>  
  
 [<span data-ttu-id="b183e-137">Palabras clave como nombres de elementos en el código</span><span class="sxs-lookup"><span data-stu-id="b183e-137">Keywords as Element Names in Code</span></span>](keywords-as-element-names-in-code.md)  
 <span data-ttu-id="b183e-138">Describe cómo usar corchetes ( `[]` ) para delimitar nombres de variable que también Visual Basic palabras clave.</span><span class="sxs-lookup"><span data-stu-id="b183e-138">Describes how to use brackets (`[]`) to delimit variable names that are also Visual Basic keywords.</span></span>  
  
 [<span data-ttu-id="b183e-139">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="b183e-139">Me, My, MyBase, and MyClass</span></span>](me-my-mybase-and-myclass.md)  
 <span data-ttu-id="b183e-140">Describe varias maneras de hacer referencia a los elementos de un programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b183e-140">Describes various ways to refer to elements of a Visual Basic program.</span></span>  
  
 [<span data-ttu-id="b183e-141">Limitaciones de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b183e-141">Visual Basic Limitations</span></span>](limitations.md)  
 <span data-ttu-id="b183e-142">Describe la eliminación de los límites de código conocidos en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b183e-142">Discusses the removal of known coding limits within Visual Basic.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b183e-143">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="b183e-143">Related Sections</span></span>  

 [<span data-ttu-id="b183e-144">Convenciones tipográficas y de código</span><span class="sxs-lookup"><span data-stu-id="b183e-144">Typographic and Code Conventions</span></span>](../../language-reference/typographic-and-code-conventions.md)  
 <span data-ttu-id="b183e-145">Proporciona convenciones de codificación estándar para Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b183e-145">Provides standard coding conventions for Visual Basic.</span></span>  
  
 [<span data-ttu-id="b183e-146">Escribir código</span><span class="sxs-lookup"><span data-stu-id="b183e-146">Writing Code</span></span>](/visualstudio/ide/writing-code-in-the-code-and-text-editor)  
 <span data-ttu-id="b183e-147">Describe las características que facilitan la escritura y administración del código.</span><span class="sxs-lookup"><span data-stu-id="b183e-147">Describes features that make it easier for you to write and manage your code.</span></span>
