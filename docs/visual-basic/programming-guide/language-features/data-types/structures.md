---
title: Estructuras (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- structures [Visual Basic]
- user-defined data types [Visual Basic], structures
- user-defined types [Visual Basic], about user-defined types
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], about user-defined data types
- types [Visual Basic], user-defined
ms.assetid: 55e86462-5e99-4d33-8018-6d097ca491b2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: de99d67ee31d8fb8e92e0a351142b30f622bf5f0
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="structures-visual-basic"></a><span data-ttu-id="a1ee5-102">Estructuras (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1ee5-102">Structures (Visual Basic)</span></span>
<span data-ttu-id="a1ee5-103">A *estructura* es una generalización del tipo definido por el usuario (UDT) compatible con versiones anteriores de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1ee5-103">A *structure* is a generalization of the user-defined type (UDT) supported by previous versions of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="a1ee5-104">Además de campos, las estructuras pueden exponer propiedades, métodos y eventos.</span><span class="sxs-lookup"><span data-stu-id="a1ee5-104">In addition to fields, structures can expose properties, methods, and events.</span></span> <span data-ttu-id="a1ee5-105">Una estructura puede implementar una o más interfaces, y se pueden declarar niveles de acceso individuales para cada campo.</span><span class="sxs-lookup"><span data-stu-id="a1ee5-105">A structure can implement one or more interfaces, and you can declare individual access levels for each field.</span></span>  
  
 <span data-ttu-id="a1ee5-106">Puede combinar elementos de datos de distintos tipos para crear una estructura.</span><span class="sxs-lookup"><span data-stu-id="a1ee5-106">You can combine data items of different types to create a structure.</span></span> <span data-ttu-id="a1ee5-107">Una estructura asocia uno o varios *elementos* entre sí y con la propia estructura.</span><span class="sxs-lookup"><span data-stu-id="a1ee5-107">A structure associates one or more *elements* with each other and with the structure itself.</span></span> <span data-ttu-id="a1ee5-108">Al declarar una estructura, se convierte en una *tipo de datos compuesto*, y se pueden declarar variables de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="a1ee5-108">When you declare a structure, it becomes a *composite data type*, and you can declare variables of that type.</span></span>  
  
 <span data-ttu-id="a1ee5-109">Las estructuras son útiles si desea que una única variable que contenga varias piezas relacionadas de información.</span><span class="sxs-lookup"><span data-stu-id="a1ee5-109">Structures are useful when you want a single variable to hold several related pieces of information.</span></span> <span data-ttu-id="a1ee5-110">Por ejemplo, puede mantener el nombre de un empleado, una extensión de teléfono y salario juntos.</span><span class="sxs-lookup"><span data-stu-id="a1ee5-110">For example, you might want to keep an employee's name, telephone extension, and salary together.</span></span> <span data-ttu-id="a1ee5-111">Podría utilizar varias variables para esta información, o puede definir una estructura y utilizarla para una única variable de empleado.</span><span class="sxs-lookup"><span data-stu-id="a1ee5-111">You could use several variables for this information, or you could define a structure and use it for a single employee variable.</span></span> <span data-ttu-id="a1ee5-112">La ventaja de la estructura queda patente cuando tiene muchos empleados y, por tanto, muchas instancias de la variable.</span><span class="sxs-lookup"><span data-stu-id="a1ee5-112">The advantage of the structure becomes apparent when you have many employees and therefore many instances of the variable.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a1ee5-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a1ee5-113">In This Section</span></span>  
 [<span data-ttu-id="a1ee5-114">Declarar una estructura</span><span class="sxs-lookup"><span data-stu-id="a1ee5-114">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 <span data-ttu-id="a1ee5-115">Muestra cómo declarar una estructura y sus elementos.</span><span class="sxs-lookup"><span data-stu-id="a1ee5-115">Shows how to declare a structure and its elements.</span></span>  
  
 [<span data-ttu-id="a1ee5-116">Variables de estructura</span><span class="sxs-lookup"><span data-stu-id="a1ee5-116">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 <span data-ttu-id="a1ee5-117">Explica la asignación de una estructura a una variable y tener acceso a sus elementos.</span><span class="sxs-lookup"><span data-stu-id="a1ee5-117">Covers assigning a structure to a variable and accessing its elements.</span></span>  
  
 [<span data-ttu-id="a1ee5-118">Estructuras y otros elementos de programación</span><span class="sxs-lookup"><span data-stu-id="a1ee5-118">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 <span data-ttu-id="a1ee5-119">Resume cómo interactúan las estructuras con matrices, objetos, procedimientos y entre sí.</span><span class="sxs-lookup"><span data-stu-id="a1ee5-119">Summarizes how structures interact with arrays, objects, procedures, and each other.</span></span>  
  
 [<span data-ttu-id="a1ee5-120">Estructuras y clases</span><span class="sxs-lookup"><span data-stu-id="a1ee5-120">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 <span data-ttu-id="a1ee5-121">Describe las similitudes y diferencias entre las estructuras y clases.</span><span class="sxs-lookup"><span data-stu-id="a1ee5-121">Describes the similarities and differences between structures and classes.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a1ee5-122">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="a1ee5-122">Related Sections</span></span>  
 [<span data-ttu-id="a1ee5-123">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="a1ee5-123">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="a1ee5-124">Presenta el [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] tipos de datos y describe cómo utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="a1ee5-124">Introduces the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="a1ee5-125">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="a1ee5-125">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="a1ee5-126">Enumera los tipos de datos básicos proporcionados por [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1ee5-126">Lists the elementary data types supplied by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>
