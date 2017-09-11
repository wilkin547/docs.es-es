---
title: Variables en Visual Basic
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2fdc670bf4f17000809e75e32c32edb39abf0fed
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="variables-in-visual-basic"></a><span data-ttu-id="8bd81-102">Variables en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8bd81-102">Variables in Visual Basic</span></span>
<span data-ttu-id="8bd81-103">A menudo tiene que almacenar valores al realizar cálculos con [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bd81-103">You often have to store values when you perform calculations with [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="8bd81-104">Por ejemplo, tal vez le interese calcular varios valores, compararlos y realizar diversas operaciones con ellos, según el resultado de la comparación.</span><span class="sxs-lookup"><span data-stu-id="8bd81-104">For example, you might want to calculate several values, compare them, and perform different operations on them, depending on the result of the comparison.</span></span> <span data-ttu-id="8bd81-105">Para poder compararlos, debe conservar los valores.</span><span class="sxs-lookup"><span data-stu-id="8bd81-105">You have to retain the values if you want to compare them.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="8bd81-106">Uso</span><span class="sxs-lookup"><span data-stu-id="8bd81-106">Usage</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="8bd81-107">, al igual que la mayoría de los lenguajes de programación, usa variables para almacenar valores.</span><span class="sxs-lookup"><span data-stu-id="8bd81-107">, just like most programming languages, uses variables for storing values.</span></span> <span data-ttu-id="8bd81-108">Las *variables* tienen un nombre (la palabra que se usa para hacer referencia al valor contenido por la variable).</span><span class="sxs-lookup"><span data-stu-id="8bd81-108">A *variable* has a name (the word that you use to refer to the value that the variable contains).</span></span> <span data-ttu-id="8bd81-109">Las variables también tienen un tipo de datos (que determina el tipo de datos que puede almacenar la variable).</span><span class="sxs-lookup"><span data-stu-id="8bd81-109">A variable also has a data type (which determines the kind of data that the variable can store).</span></span> <span data-ttu-id="8bd81-110">Las variables pueden representar una matriz si tienen que almacenar un conjunto indexado de elementos de datos estrechamente relacionados.</span><span class="sxs-lookup"><span data-stu-id="8bd81-110">A variable can represent an array if it has to store an indexed set of closely related data items.</span></span>  
  
 <span data-ttu-id="8bd81-111">La inferencia de tipo de variable local permite declarar variables sin especificar explícitamente un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="8bd81-111">Local type inference enables you to declare variables without explicitly stating a data type.</span></span> <span data-ttu-id="8bd81-112">En su lugar, el compilador deduce el tipo de la variable a partir del tipo de la expresión de inicialización.</span><span class="sxs-lookup"><span data-stu-id="8bd81-112">Instead, the compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="8bd81-113">Para obtener más información, vea [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) (Inferencia de tipo de variable local) y [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) (Instrucción Option Infer).</span><span class="sxs-lookup"><span data-stu-id="8bd81-113">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) and [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="assigning-values"></a><span data-ttu-id="8bd81-114">Asignar valores</span><span class="sxs-lookup"><span data-stu-id="8bd81-114">Assigning Values</span></span>  
 <span data-ttu-id="8bd81-115">Para realizar cálculos y asignar el resultado a una variable debe usar instrucciones de asignación, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="8bd81-115">You use assignment statements to perform calculations and assign the result to a variable, as the following example shows.</span></span>  
  
 <span data-ttu-id="8bd81-116">[!code-vb[VbVbalrVariables#1](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/index_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8bd81-116">[!code-vb[VbVbalrVariables#1](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/index_1.vb)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8bd81-117">El signo igual (`=`) de este ejemplo es un operador de asignación, no un operador de igualdad.</span><span class="sxs-lookup"><span data-stu-id="8bd81-117">The equal sign (`=`) in this example is an assignment operator, not an equality operator.</span></span> <span data-ttu-id="8bd81-118">El valor se asigna a la variable `applesSold`.</span><span class="sxs-lookup"><span data-stu-id="8bd81-118">The value is being assigned to the variable `applesSold`.</span></span>  
  
 <span data-ttu-id="8bd81-119">Para obtener más información, vea [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) (Cómo: Introducir y extraer los datos de una variable).</span><span class="sxs-lookup"><span data-stu-id="8bd81-119">For more information, see [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).</span></span>  
  
## <a name="variables-and-properties"></a><span data-ttu-id="8bd81-120">Variables y propiedades</span><span class="sxs-lookup"><span data-stu-id="8bd81-120">Variables and Properties</span></span>  
 <span data-ttu-id="8bd81-121">Al igual que una variable, una *propiedad* representa un valor al que se puede tener acceso,</span><span class="sxs-lookup"><span data-stu-id="8bd81-121">Like a variable, a *property* represents a value that you can access.</span></span> <span data-ttu-id="8bd81-122">pero es más compleja que una variable.</span><span class="sxs-lookup"><span data-stu-id="8bd81-122">However, it is more complex than a variable.</span></span> <span data-ttu-id="8bd81-123">Una propiedad usa bloques de código que controlan cómo establecer y recuperar su valor.</span><span class="sxs-lookup"><span data-stu-id="8bd81-123">A property uses code blocks that control how to set and retrieve its value.</span></span> <span data-ttu-id="8bd81-124">Para obtener más información, vea [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md) (Diferencias entre propiedades y variables en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="8bd81-124">For more information, see [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd81-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bd81-125">See Also</span></span>  
 <span data-ttu-id="8bd81-126">[Declaración de variable](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="8bd81-126">[Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
 <span data-ttu-id="8bd81-127">[Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span><span class="sxs-lookup"><span data-stu-id="8bd81-127">[Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span></span>  
 <span data-ttu-id="8bd81-128">[Solución de problemas de variables](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md) </span><span class="sxs-lookup"><span data-stu-id="8bd81-128">[Troubleshooting Variables](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md) </span></span>  
 <span data-ttu-id="8bd81-129">[Cómo: Introducir y extraer los datos de una variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) </span><span class="sxs-lookup"><span data-stu-id="8bd81-129">[How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) </span></span>  
 <span data-ttu-id="8bd81-130">[Diferencias entre propiedades y variables en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="8bd81-130">[Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md) </span></span>  
 [<span data-ttu-id="8bd81-131">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="8bd81-131">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)

