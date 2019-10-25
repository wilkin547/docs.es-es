---
title: New (Operador, Visual Basic)
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
ms.openlocfilehash: c0870f4b056658a22928769c369024cdda24f354
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799040"
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="d884a-102">New (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d884a-102">New Operator (Visual Basic)</span></span>

<span data-ttu-id="d884a-103">Presenta una cláusula `New` para crear una nueva instancia de objeto, especifica una restricción de constructor en un parámetro de tipo o identifica un procedimiento `Sub` como un constructor de clase.</span><span class="sxs-lookup"><span data-stu-id="d884a-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>

## <a name="remarks"></a><span data-ttu-id="d884a-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d884a-104">Remarks</span></span>

<span data-ttu-id="d884a-105">En una declaración o una instrucción de asignación, una cláusula `New` debe especificar una clase definida a partir de la cual se pueda crear la instancia.</span><span class="sxs-lookup"><span data-stu-id="d884a-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="d884a-106">Esto significa que la clase debe exponer uno o más constructores a los que puede tener acceso el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="d884a-106">This means that the class must expose one or more constructors that the calling code can access.</span></span>

<span data-ttu-id="d884a-107">Puede usar una cláusula `New` en una instrucción de declaración o una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="d884a-107">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="d884a-108">Cuando se ejecuta la instrucción, llama al constructor adecuado de la clase especificada, pasando los argumentos que ha proporcionado.</span><span class="sxs-lookup"><span data-stu-id="d884a-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="d884a-109">En el siguiente ejemplo se muestra la creación de instancias de una clase `Customer` que tiene dos constructores, uno que no toma parámetros y otro que toma un parámetro de cadena:</span><span class="sxs-lookup"><span data-stu-id="d884a-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter:</span></span>

[!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]

<span data-ttu-id="d884a-110">Dado que las matrices son clases, `New` puede crear una nueva instancia de la matriz, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d884a-110">Since arrays are classes, `New` can create a new array instance, as shown in the following example:</span></span>

[!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]

<span data-ttu-id="d884a-111">El Common Language Runtime (CLR) produce un error de <xref:System.OutOfMemoryException> si no hay suficiente memoria para crear la nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="d884a-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>

> [!NOTE]
> <span data-ttu-id="d884a-112">La palabra clave `New` también se usa en las listas de parámetros de tipo para especificar que el tipo proporcionado debe exponer un constructor sin parámetros accesible.</span><span class="sxs-lookup"><span data-stu-id="d884a-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="d884a-113">Para obtener más información sobre los parámetros de tipo y las restricciones, vea [Type List](../statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="d884a-113">For more information about type parameters and constraints, see [Type List](../statements/type-list.md).</span></span>

<span data-ttu-id="d884a-114">Para crear un procedimiento de constructor para una clase, establezca el nombre de una `Sub` procedimiento en la palabra clave `New`.</span><span class="sxs-lookup"><span data-stu-id="d884a-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="d884a-115">Para obtener más información, vea [duración del objeto: cómo se crean y destruyen los objetos](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="d884a-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

<span data-ttu-id="d884a-116">La palabra clave `New` se puede usar en los siguientes contextos:</span><span class="sxs-lookup"><span data-stu-id="d884a-116">The `New` keyword can be used in these contexts:</span></span>

- [<span data-ttu-id="d884a-117">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d884a-117">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="d884a-118">Of</span><span class="sxs-lookup"><span data-stu-id="d884a-118">Of</span></span>](../statements/of-clause.md)
- [<span data-ttu-id="d884a-119">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d884a-119">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="d884a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d884a-120">See also</span></span>

- <xref:System.OutOfMemoryException>
- [<span data-ttu-id="d884a-121">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d884a-121">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="d884a-122">Lista de tipos</span><span class="sxs-lookup"><span data-stu-id="d884a-122">Type List</span></span>](../statements/type-list.md)
- [<span data-ttu-id="d884a-123">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d884a-123">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="d884a-124">Duración de los objetos: cómo se crean y destruyen</span><span class="sxs-lookup"><span data-stu-id="d884a-124">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
