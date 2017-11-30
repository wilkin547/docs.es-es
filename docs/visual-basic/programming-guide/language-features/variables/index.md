---
title: Variables en Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a7a47ad7e4ade9f15159c27ac672aeb937a05493
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="variables-in-visual-basic"></a><span data-ttu-id="8a031-102">Variables en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8a031-102">Variables in Visual Basic</span></span>
<span data-ttu-id="8a031-103">A menudo tiene que almacenar valores al realizar cálculos con [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a031-103">You often have to store values when you perform calculations with [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="8a031-104">Por ejemplo, tal vez le interese calcular varios valores, compararlos y realizar diversas operaciones con ellos, según el resultado de la comparación.</span><span class="sxs-lookup"><span data-stu-id="8a031-104">For example, you might want to calculate several values, compare them, and perform different operations on them, depending on the result of the comparison.</span></span> <span data-ttu-id="8a031-105">Para poder compararlos, debe conservar los valores.</span><span class="sxs-lookup"><span data-stu-id="8a031-105">You have to retain the values if you want to compare them.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="8a031-106">Uso</span><span class="sxs-lookup"><span data-stu-id="8a031-106">Usage</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="8a031-107">, al igual que la mayoría de los lenguajes de programación, usa variables para almacenar valores.</span><span class="sxs-lookup"><span data-stu-id="8a031-107">, just like most programming languages, uses variables for storing values.</span></span> <span data-ttu-id="8a031-108">Las *variables* tienen un nombre (la palabra que se usa para hacer referencia al valor contenido por la variable).</span><span class="sxs-lookup"><span data-stu-id="8a031-108">A *variable* has a name (the word that you use to refer to the value that the variable contains).</span></span> <span data-ttu-id="8a031-109">Las variables también tienen un tipo de datos (que determina el tipo de datos que puede almacenar la variable).</span><span class="sxs-lookup"><span data-stu-id="8a031-109">A variable also has a data type (which determines the kind of data that the variable can store).</span></span> <span data-ttu-id="8a031-110">Las variables pueden representar una matriz si tienen que almacenar un conjunto indexado de elementos de datos estrechamente relacionados.</span><span class="sxs-lookup"><span data-stu-id="8a031-110">A variable can represent an array if it has to store an indexed set of closely related data items.</span></span>  
  
 <span data-ttu-id="8a031-111">La inferencia de tipo de variable local permite declarar variables sin especificar explícitamente un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="8a031-111">Local type inference enables you to declare variables without explicitly stating a data type.</span></span> <span data-ttu-id="8a031-112">En su lugar, el compilador deduce el tipo de la variable a partir del tipo de la expresión de inicialización.</span><span class="sxs-lookup"><span data-stu-id="8a031-112">Instead, the compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="8a031-113">Para obtener más información, vea [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) (Inferencia de tipo de variable local) y [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) (Instrucción Option Infer).</span><span class="sxs-lookup"><span data-stu-id="8a031-113">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) and [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="assigning-values"></a><span data-ttu-id="8a031-114">Asignar valores</span><span class="sxs-lookup"><span data-stu-id="8a031-114">Assigning Values</span></span>  
 <span data-ttu-id="8a031-115">Para realizar cálculos y asignar el resultado a una variable debe usar instrucciones de asignación, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="8a031-115">You use assignment statements to perform calculations and assign the result to a variable, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrVariables#1](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/index_1.vb)]  
  
> [!NOTE]
>  <span data-ttu-id="8a031-116">El signo igual (`=`) de este ejemplo es un operador de asignación, no un operador de igualdad.</span><span class="sxs-lookup"><span data-stu-id="8a031-116">The equal sign (`=`) in this example is an assignment operator, not an equality operator.</span></span> <span data-ttu-id="8a031-117">El valor se asigna a la variable `applesSold`.</span><span class="sxs-lookup"><span data-stu-id="8a031-117">The value is being assigned to the variable `applesSold`.</span></span>  
  
 <span data-ttu-id="8a031-118">Para obtener más información, vea [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) (Cómo: Introducir y extraer los datos de una variable).</span><span class="sxs-lookup"><span data-stu-id="8a031-118">For more information, see [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).</span></span>  
  
## <a name="variables-and-properties"></a><span data-ttu-id="8a031-119">Variables y propiedades</span><span class="sxs-lookup"><span data-stu-id="8a031-119">Variables and Properties</span></span>  
 <span data-ttu-id="8a031-120">Al igual que una variable, una *propiedad* representa un valor al que se puede tener acceso,</span><span class="sxs-lookup"><span data-stu-id="8a031-120">Like a variable, a *property* represents a value that you can access.</span></span> <span data-ttu-id="8a031-121">pero es más compleja que una variable.</span><span class="sxs-lookup"><span data-stu-id="8a031-121">However, it is more complex than a variable.</span></span> <span data-ttu-id="8a031-122">Una propiedad usa bloques de código que controlan cómo establecer y recuperar su valor.</span><span class="sxs-lookup"><span data-stu-id="8a031-122">A property uses code blocks that control how to set and retrieve its value.</span></span> <span data-ttu-id="8a031-123">Para obtener más información, vea [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md) (Diferencias entre propiedades y variables en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="8a031-123">For more information, see [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a031-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a031-124">See Also</span></span>  
 [<span data-ttu-id="8a031-125">Declaración de variables</span><span class="sxs-lookup"><span data-stu-id="8a031-125">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="8a031-126">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="8a031-126">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="8a031-127">Solución de problemas de variables</span><span class="sxs-lookup"><span data-stu-id="8a031-127">Troubleshooting Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)  
 [<span data-ttu-id="8a031-128">Introducir y extraer los datos de una variable</span><span class="sxs-lookup"><span data-stu-id="8a031-128">How to: Move Data Into and Out of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)  
 [<span data-ttu-id="8a031-129">Diferencias entre propiedades y Variables en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8a031-129">Differences Between Properties and Variables in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)  
 [<span data-ttu-id="8a031-130">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="8a031-130">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
