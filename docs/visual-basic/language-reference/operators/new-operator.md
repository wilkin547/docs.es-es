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
ms.openlocfilehash: 36cf71529b1f81c27881638d788117222c37171d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955877"
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="09bb2-102">New (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09bb2-102">New Operator (Visual Basic)</span></span>
<span data-ttu-id="09bb2-103">Introduce una `New` cláusula para crear una nueva instancia de objeto, especifica una restricción de constructor en un parámetro de tipo o `Sub` identifica un procedimiento como un constructor de clase.</span><span class="sxs-lookup"><span data-stu-id="09bb2-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09bb2-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="09bb2-104">Remarks</span></span>  
 <span data-ttu-id="09bb2-105">En una declaración o una instrucción de asignación `New` , una cláusula debe especificar una clase definida a partir de la cual se pueda crear la instancia.</span><span class="sxs-lookup"><span data-stu-id="09bb2-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="09bb2-106">Esto significa que la clase debe exponer uno o más constructores a los que puede tener acceso el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="09bb2-106">This means that the class must expose one or more constructors that the calling code can access.</span></span>  
  
 <span data-ttu-id="09bb2-107">Puede utilizar una `New` cláusula en una instrucción de declaración o una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="09bb2-107">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="09bb2-108">Cuando se ejecuta la instrucción, llama al constructor adecuado de la clase especificada, pasando los argumentos que ha proporcionado.</span><span class="sxs-lookup"><span data-stu-id="09bb2-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="09bb2-109">En el siguiente ejemplo se muestra la creación de instancias `Customer` de una clase que tiene dos constructores, uno que no toma parámetros y otro que toma un parámetro de cadena.</span><span class="sxs-lookup"><span data-stu-id="09bb2-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter.</span></span>  
  
 [!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]  
  
 <span data-ttu-id="09bb2-110">Puesto que las matrices son clases `New` , pueden crear una nueva instancia de la matriz, como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="09bb2-110">Since arrays are classes, `New` can create a new array instance, as shown in the following examples.</span></span>  
  
 [!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]  
  
 <span data-ttu-id="09bb2-111">El Common Language Runtime (CLR) produce un <xref:System.OutOfMemoryException> error si no hay memoria suficiente para crear la nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="09bb2-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="09bb2-112">La `New` palabra clave también se usa en las listas de parámetros de tipo para especificar que el tipo proporcionado debe exponer un constructor sin parámetros accesible.</span><span class="sxs-lookup"><span data-stu-id="09bb2-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="09bb2-113">Para obtener más información sobre los parámetros de tipo y las restricciones, vea [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="09bb2-113">For more information about type parameters and constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
 <span data-ttu-id="09bb2-114">Para crear un procedimiento de constructor para una clase, establezca el nombre de `Sub` un procedimiento en `New` la palabra clave.</span><span class="sxs-lookup"><span data-stu-id="09bb2-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="09bb2-115">Para obtener más información, [consulte duración de los objetos: Cómo se crean y destruyen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)los objetos.</span><span class="sxs-lookup"><span data-stu-id="09bb2-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
 <span data-ttu-id="09bb2-116">La palabra clave `New` se puede usar en los siguientes contextos:</span><span class="sxs-lookup"><span data-stu-id="09bb2-116">The `New` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="09bb2-117">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="09bb2-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="09bb2-118">Of</span><span class="sxs-lookup"><span data-stu-id="09bb2-118">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [<span data-ttu-id="09bb2-119">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="09bb2-119">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="09bb2-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="09bb2-120">See also</span></span>

- <xref:System.OutOfMemoryException>
- [<span data-ttu-id="09bb2-121">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="09bb2-121">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="09bb2-122">Lista de tipos</span><span class="sxs-lookup"><span data-stu-id="09bb2-122">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="09bb2-123">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="09bb2-123">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="09bb2-124">Duración del objeto: Cómo se crean y destruyen los objetos</span><span class="sxs-lookup"><span data-stu-id="09bb2-124">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
