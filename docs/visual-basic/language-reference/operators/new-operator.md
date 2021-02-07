---
description: 'Más información acerca de: nuevo operador (Visual Basic)'
title: New (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.new
- vb.NewConstraint
helpviewer_keywords:
- constraints, Visual Basic generic types
- generics [Visual Basic], constraints
- constraints, New keyword [Visual Basic]
- New constraint
- New keyword [Visual Basic]
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
ms.openlocfilehash: f52dd7606127c7587173de8a78e618ceb3e4681d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665385"
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="6eb61-103">New (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6eb61-103">New Operator (Visual Basic)</span></span>

<span data-ttu-id="6eb61-104">Introduce una `New` cláusula para crear una nueva instancia de objeto, especifica una restricción de constructor en un parámetro de tipo o identifica un `Sub` procedimiento como un constructor de clase.</span><span class="sxs-lookup"><span data-stu-id="6eb61-104">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>

## <a name="remarks"></a><span data-ttu-id="6eb61-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6eb61-105">Remarks</span></span>

<span data-ttu-id="6eb61-106">En una declaración o una instrucción de asignación, una `New` cláusula debe especificar una clase definida a partir de la cual se pueda crear la instancia.</span><span class="sxs-lookup"><span data-stu-id="6eb61-106">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="6eb61-107">Esto significa que la clase debe exponer uno o más constructores a los que puede tener acceso el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="6eb61-107">This means that the class must expose one or more constructors that the calling code can access.</span></span>

<span data-ttu-id="6eb61-108">Puede utilizar una `New` cláusula en una instrucción de declaración o una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="6eb61-108">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="6eb61-109">Cuando se ejecuta la instrucción, llama al constructor adecuado de la clase especificada, pasando los argumentos que ha proporcionado.</span><span class="sxs-lookup"><span data-stu-id="6eb61-109">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="6eb61-110">En el siguiente ejemplo se muestra la creación de instancias de una `Customer` clase que tiene dos constructores, uno que no toma parámetros y otro que toma un parámetro de cadena:</span><span class="sxs-lookup"><span data-stu-id="6eb61-110">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter:</span></span>

[!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]

<span data-ttu-id="6eb61-111">Puesto que las matrices son clases, `New` pueden crear una nueva instancia de la matriz, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6eb61-111">Since arrays are classes, `New` can create a new array instance, as shown in the following example:</span></span>

[!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]

<span data-ttu-id="6eb61-112">El Common Language Runtime (CLR) produce un <xref:System.OutOfMemoryException> error si no hay memoria suficiente para crear la nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="6eb61-112">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>

> [!NOTE]
> <span data-ttu-id="6eb61-113">La `New` palabra clave también se usa en las listas de parámetros de tipo para especificar que el tipo proporcionado debe exponer un constructor sin parámetros accesible.</span><span class="sxs-lookup"><span data-stu-id="6eb61-113">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="6eb61-114">Para obtener más información sobre los parámetros de tipo y las restricciones, vea [Type List](../statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="6eb61-114">For more information about type parameters and constraints, see [Type List](../statements/type-list.md).</span></span>

<span data-ttu-id="6eb61-115">Para crear un procedimiento de constructor para una clase, establezca el nombre de un `Sub` procedimiento en la `New` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="6eb61-115">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="6eb61-116">Para obtener más información, vea [duración del objeto: cómo se crean y destruyen los objetos](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="6eb61-116">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

<span data-ttu-id="6eb61-117">La palabra clave `New` se puede usar en los siguientes contextos:</span><span class="sxs-lookup"><span data-stu-id="6eb61-117">The `New` keyword can be used in these contexts:</span></span>

- [<span data-ttu-id="6eb61-118">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="6eb61-118">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="6eb61-119">De</span><span class="sxs-lookup"><span data-stu-id="6eb61-119">Of</span></span>](../statements/of-clause.md)
- [<span data-ttu-id="6eb61-120">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="6eb61-120">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="6eb61-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="6eb61-121">See also</span></span>

- <xref:System.OutOfMemoryException>
- [<span data-ttu-id="6eb61-122">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6eb61-122">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="6eb61-123">Type List</span><span class="sxs-lookup"><span data-stu-id="6eb61-123">Type List</span></span>](../statements/type-list.md)
- [<span data-ttu-id="6eb61-124">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6eb61-124">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="6eb61-125">Duración de los objetos: cómo se crean y destruyen</span><span class="sxs-lookup"><span data-stu-id="6eb61-125">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
