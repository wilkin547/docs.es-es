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
ms.openlocfilehash: 0e8ec5877cba5f5cf97e1677460da06fd87cce1c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587559"
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="0db5f-102">New (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0db5f-102">New Operator (Visual Basic)</span></span>
<span data-ttu-id="0db5f-103">Presenta un `New` cláusula para crear una nueva instancia de objeto, especifica una restricción de constructor en un parámetro de tipo, o identifica una `Sub` procedimiento como un constructor de clase.</span><span class="sxs-lookup"><span data-stu-id="0db5f-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0db5f-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0db5f-104">Remarks</span></span>  
 <span data-ttu-id="0db5f-105">En una declaración o instrucción de asignación, un `New` cláusula debe especificar una clase definida desde la que se puede crear la instancia.</span><span class="sxs-lookup"><span data-stu-id="0db5f-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="0db5f-106">Esto significa que la clase debe exponer uno o más constructores que puede tener acceso el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="0db5f-106">This means that the class must expose one or more constructors that the calling code can access.</span></span>  
  
 <span data-ttu-id="0db5f-107">Puede usar un `New` cláusula en una instrucción de declaración o en una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="0db5f-107">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="0db5f-108">Cuando se ejecuta la instrucción, llama al constructor apropiado de la clase especificada, pasando los argumentos que hayan proporcionado.</span><span class="sxs-lookup"><span data-stu-id="0db5f-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="0db5f-109">El ejemplo siguiente muestra mediante la creación de instancias de un `Customer` clase que tiene dos constructores, uno que no toma ningún parámetro y otro que toma un parámetro de cadena.</span><span class="sxs-lookup"><span data-stu-id="0db5f-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter.</span></span>  
  
 [!code-vb[VbVbalrKeywords#11](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_1.vb)]  
  
 <span data-ttu-id="0db5f-110">Dado que las matrices son clases, `New` puede crear una nueva instancia de matriz, como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="0db5f-110">Since arrays are classes, `New` can create a new array instance, as shown in the following examples.</span></span>  
  
 [!code-vb[VbVbalrKeywords#12](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_2.vb)]  
  
 <span data-ttu-id="0db5f-111">Common language runtime (CLR) produce una <xref:System.OutOfMemoryException> error si no hay memoria suficiente para crear la nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="0db5f-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0db5f-112">El `New` palabra clave también se usa en las listas de parámetros de tipo para especificar que el tipo proporcionado debe exponer un constructor sin parámetros accesible.</span><span class="sxs-lookup"><span data-stu-id="0db5f-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="0db5f-113">Para obtener más información sobre los parámetros de tipo y restricciones, vea [lista tipo](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="0db5f-113">For more information about type parameters and constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
 <span data-ttu-id="0db5f-114">Para crear un procedimiento de constructor para una clase, establezca el nombre de un `Sub` procedimiento a la `New` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="0db5f-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="0db5f-115">Para obtener más información, consulte [duración del objeto: ¿Cómo se crean y destruyen objetos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="0db5f-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
 <span data-ttu-id="0db5f-116">La palabra clave `New` se puede usar en los siguientes contextos:</span><span class="sxs-lookup"><span data-stu-id="0db5f-116">The `New` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="0db5f-117">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="0db5f-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="0db5f-118">Of</span><span class="sxs-lookup"><span data-stu-id="0db5f-118">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [<span data-ttu-id="0db5f-119">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="0db5f-119">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="0db5f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="0db5f-120">See also</span></span>
- <xref:System.OutOfMemoryException>
- [<span data-ttu-id="0db5f-121">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0db5f-121">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="0db5f-122">Lista de tipos</span><span class="sxs-lookup"><span data-stu-id="0db5f-122">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="0db5f-123">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0db5f-123">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="0db5f-124">Duración del objeto: ¿Cómo se crean y destruyen objetos</span><span class="sxs-lookup"><span data-stu-id="0db5f-124">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
