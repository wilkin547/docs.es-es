---
description: 'Más información sobre: variables en Visual Basic'
title: Variables
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
ms.openlocfilehash: d00907e451fa09c6e9b6be990a24a4d39b386622
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481719"
---
# <a name="variables-in-visual-basic"></a><span data-ttu-id="1a9c5-103">Variables en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1a9c5-103">Variables in Visual Basic</span></span>

<span data-ttu-id="1a9c5-104">A menudo tiene que almacenar valores al realizar cálculos con Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1a9c5-104">You often have to store values when you perform calculations with Visual Basic.</span></span> <span data-ttu-id="1a9c5-105">Por ejemplo, tal vez le interese calcular varios valores, compararlos y realizar diversas operaciones con ellos, según el resultado de la comparación.</span><span class="sxs-lookup"><span data-stu-id="1a9c5-105">For example, you might want to calculate several values, compare them, and perform different operations on them, depending on the result of the comparison.</span></span> <span data-ttu-id="1a9c5-106">Para poder compararlos, debe conservar los valores.</span><span class="sxs-lookup"><span data-stu-id="1a9c5-106">You have to retain the values if you want to compare them.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="1a9c5-107">Uso</span><span class="sxs-lookup"><span data-stu-id="1a9c5-107">Usage</span></span>  

 <span data-ttu-id="1a9c5-108">Visual Basic, al igual que la mayoría de los lenguajes de programación, utiliza variables para almacenar valores.</span><span class="sxs-lookup"><span data-stu-id="1a9c5-108">Visual Basic, just like most programming languages, uses variables for storing values.</span></span> <span data-ttu-id="1a9c5-109">Las *variables* tienen un nombre (la palabra que se usa para hacer referencia al valor contenido por la variable).</span><span class="sxs-lookup"><span data-stu-id="1a9c5-109">A *variable* has a name (the word that you use to refer to the value that the variable contains).</span></span> <span data-ttu-id="1a9c5-110">Las variables también tienen un tipo de datos (que determina el tipo de datos que puede almacenar la variable).</span><span class="sxs-lookup"><span data-stu-id="1a9c5-110">A variable also has a data type (which determines the kind of data that the variable can store).</span></span> <span data-ttu-id="1a9c5-111">Las variables pueden representar una matriz si tienen que almacenar un conjunto indexado de elementos de datos estrechamente relacionados.</span><span class="sxs-lookup"><span data-stu-id="1a9c5-111">A variable can represent an array if it has to store an indexed set of closely related data items.</span></span>  
  
 <span data-ttu-id="1a9c5-112">La inferencia de tipo de variable local permite declarar variables sin especificar explícitamente un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="1a9c5-112">Local type inference enables you to declare variables without explicitly stating a data type.</span></span> <span data-ttu-id="1a9c5-113">En su lugar, el compilador deduce el tipo de la variable a partir del tipo de la expresión de inicialización.</span><span class="sxs-lookup"><span data-stu-id="1a9c5-113">Instead, the compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="1a9c5-114">Para obtener más información, vea [Local Type Inference](local-type-inference.md) (Inferencia de tipo de variable local) y [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md) (Instrucción Option Infer).</span><span class="sxs-lookup"><span data-stu-id="1a9c5-114">For more information, see [Local Type Inference](local-type-inference.md) and [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="assigning-values"></a><span data-ttu-id="1a9c5-115">Asignar valores</span><span class="sxs-lookup"><span data-stu-id="1a9c5-115">Assigning Values</span></span>  

 <span data-ttu-id="1a9c5-116">Para realizar cálculos y asignar el resultado a una variable debe usar instrucciones de asignación, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="1a9c5-116">You use assignment statements to perform calculations and assign the result to a variable, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrVariables#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrVariables/VB/Class1.vb#1)]  
  
> [!NOTE]
> <span data-ttu-id="1a9c5-117">El signo igual (`=`) de este ejemplo es un operador de asignación, no un operador de igualdad.</span><span class="sxs-lookup"><span data-stu-id="1a9c5-117">The equal sign (`=`) in this example is an assignment operator, not an equality operator.</span></span> <span data-ttu-id="1a9c5-118">El valor se asigna a la variable `applesSold`.</span><span class="sxs-lookup"><span data-stu-id="1a9c5-118">The value is being assigned to the variable `applesSold`.</span></span>  
  
 <span data-ttu-id="1a9c5-119">Para obtener más información, vea [How to: Move Data Into and Out of a Variable](how-to-move-data-into-and-out-of-a-variable.md) (Cómo: Introducir y extraer los datos de una variable).</span><span class="sxs-lookup"><span data-stu-id="1a9c5-119">For more information, see [How to: Move Data Into and Out of a Variable](how-to-move-data-into-and-out-of-a-variable.md).</span></span>  
  
## <a name="variables-and-properties"></a><span data-ttu-id="1a9c5-120">Variables y propiedades</span><span class="sxs-lookup"><span data-stu-id="1a9c5-120">Variables and Properties</span></span>  

 <span data-ttu-id="1a9c5-121">Al igual que una variable, una *propiedad* representa un valor al que se puede tener acceso,</span><span class="sxs-lookup"><span data-stu-id="1a9c5-121">Like a variable, a *property* represents a value that you can access.</span></span> <span data-ttu-id="1a9c5-122">pero es más compleja que una variable.</span><span class="sxs-lookup"><span data-stu-id="1a9c5-122">However, it is more complex than a variable.</span></span> <span data-ttu-id="1a9c5-123">Una propiedad usa bloques de código que controlan cómo establecer y recuperar su valor.</span><span class="sxs-lookup"><span data-stu-id="1a9c5-123">A property uses code blocks that control how to set and retrieve its value.</span></span> <span data-ttu-id="1a9c5-124">Para obtener más información, vea [Differences Between Properties and Variables in Visual Basic](../procedures/differences-between-properties-and-variables.md) (Diferencias entre propiedades y variables en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="1a9c5-124">For more information, see [Differences Between Properties and Variables in Visual Basic](../procedures/differences-between-properties-and-variables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a9c5-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1a9c5-125">See also</span></span>

- [<span data-ttu-id="1a9c5-126">Declaración de variable</span><span class="sxs-lookup"><span data-stu-id="1a9c5-126">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="1a9c5-127">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="1a9c5-127">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="1a9c5-128">Solución de problemas de variables</span><span class="sxs-lookup"><span data-stu-id="1a9c5-128">Troubleshooting Variables</span></span>](troubleshooting-variables.md)
- [<span data-ttu-id="1a9c5-129">Procedimiento para introducir y extraer los datos de una variable</span><span class="sxs-lookup"><span data-stu-id="1a9c5-129">How to: Move Data Into and Out of a Variable</span></span>](how-to-move-data-into-and-out-of-a-variable.md)
- [<span data-ttu-id="1a9c5-130">Diferencias entre propiedades y variables en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1a9c5-130">Differences Between Properties and Variables in Visual Basic</span></span>](../procedures/differences-between-properties-and-variables.md)
- [<span data-ttu-id="1a9c5-131">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="1a9c5-131">Local Type Inference</span></span>](local-type-inference.md)
