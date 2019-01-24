---
title: Static (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: 1205d620fb5b6ec6af14cdeb7c6d78439f9e6b97
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627634"
---
# <a name="static-visual-basic"></a><span data-ttu-id="4a56e-102">Static (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a56e-102">Static (Visual Basic)</span></span>
<span data-ttu-id="4a56e-103">Especifica uno o más variables locales declaradas deben seguir existiendo y conservar sus últimos valores tras la finalización del procedimiento en el que se declaran.</span><span class="sxs-lookup"><span data-stu-id="4a56e-103">Specifies that one or more declared local variables are to continue to exist and retain their latest values after termination of the procedure in which they are declared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a56e-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4a56e-104">Remarks</span></span>  
 <span data-ttu-id="4a56e-105">Normalmente, una variable local en un procedimiento deja de existir en cuanto se detiene el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4a56e-105">Normally, a local variable in a procedure ceases to exist as soon as the procedure stops.</span></span> <span data-ttu-id="4a56e-106">Una variable estática sigue existiendo y conserva su valor más reciente.</span><span class="sxs-lookup"><span data-stu-id="4a56e-106">A static variable continues to exist and retains its most recent value.</span></span> <span data-ttu-id="4a56e-107">La próxima vez que el código llama al procedimiento, no se reinicializa la variable y todavía contiene el valor más reciente que asignó a él.</span><span class="sxs-lookup"><span data-stu-id="4a56e-107">The next time your code calls the procedure, the variable is not reinitialized, and it still holds the latest value that you assigned to it.</span></span> <span data-ttu-id="4a56e-108">Sigue existiendo durante la vigencia de la clase o módulo que está definido en una variable estática.</span><span class="sxs-lookup"><span data-stu-id="4a56e-108">A static variable continues to exist for the lifetime of the class or module that it is defined in.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="4a56e-109">Reglas</span><span class="sxs-lookup"><span data-stu-id="4a56e-109">Rules</span></span>  
  
-   <span data-ttu-id="4a56e-110">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="4a56e-110">**Declaration Context.**</span></span> <span data-ttu-id="4a56e-111">Puede usar `Static` solo en las variables locales.</span><span class="sxs-lookup"><span data-stu-id="4a56e-111">You can use `Static` only on local variables.</span></span> <span data-ttu-id="4a56e-112">Esto significa que el contexto de declaración de un `Static` variable debe ser un procedimiento o un bloque en un procedimiento y no puede ser el archivo de código fuente, espacio de nombres, clase, estructura o módulo.</span><span class="sxs-lookup"><span data-stu-id="4a56e-112">This means the declaration context for a `Static` variable must be a procedure or a block in a procedure, and it cannot be a source file, namespace, class, structure, or module.</span></span>  
  
     <span data-ttu-id="4a56e-113">No puede usar `Static` dentro de un procedimiento de estructura.</span><span class="sxs-lookup"><span data-stu-id="4a56e-113">You cannot use `Static` inside a structure procedure.</span></span>  
  
-   <span data-ttu-id="4a56e-114">Los tipos de datos de `Static` las variables locales no se puede inferir.</span><span class="sxs-lookup"><span data-stu-id="4a56e-114">The data types of `Static` local variables cannot be inferred.</span></span> <span data-ttu-id="4a56e-115">Para obtener más información, consulte [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="4a56e-115">For more information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
-   <span data-ttu-id="4a56e-116">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="4a56e-116">**Combined Modifiers.**</span></span> <span data-ttu-id="4a56e-117">No puede especificar `Static` junto con `ReadOnly`, `Shadows`, o `Shared` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="4a56e-117">You cannot specify `Static` together with `ReadOnly`, `Shadows`, or `Shared` in the same declaration.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="4a56e-118">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="4a56e-118">Behavior</span></span>  
 <span data-ttu-id="4a56e-119">Cuando se declara una variable estática en un `Shared` procedimiento, solo una copia de la variable estática está disponible para toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4a56e-119">When you declare a static variable in a `Shared` procedure, only one copy of the static variable is available for the whole application.</span></span> <span data-ttu-id="4a56e-120">Se llama a un `Shared` nombre de este procedimiento mediante el uso de la clase, no una variable que señala a una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="4a56e-120">You call a `Shared` procedure by using the class name, not a variable that points to an instance of the class.</span></span>  
  
 <span data-ttu-id="4a56e-121">Cuando se declara una variable estática en un procedimiento que no sea `Shared`, solo una copia de la variable está disponible para cada instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="4a56e-121">When you declare a static variable in a procedure that isn't `Shared`, only one copy of the variable is available for each instance of the class.</span></span> <span data-ttu-id="4a56e-122">Llame a un procedimiento no compartido mediante una variable que señala a una instancia específica de la clase.</span><span class="sxs-lookup"><span data-stu-id="4a56e-122">You call a non-shared procedure by using a variable that points to a specific instance of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a56e-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4a56e-123">Example</span></span>  
 <span data-ttu-id="4a56e-124">El siguiente ejemplo muestra el uso de `Static`.</span><span class="sxs-lookup"><span data-stu-id="4a56e-124">The following example demonstrates the use of `Static`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#5](../../../visual-basic/language-reference/codesnippet/VisualBasic/static_1.vb)]  
  
 <span data-ttu-id="4a56e-125">El `Static` variable `totalSales` se inicializa en 0, solo una vez.</span><span class="sxs-lookup"><span data-stu-id="4a56e-125">The `Static` variable `totalSales` is initialized to 0 only one time.</span></span> <span data-ttu-id="4a56e-126">Cada vez que escriba `updateSales`, `totalSales` sigue teniendo el valor más reciente que se ha calculado para él.</span><span class="sxs-lookup"><span data-stu-id="4a56e-126">Each time that you enter `updateSales`, `totalSales` still has the most recent value that you calculated for it.</span></span>  
  
 <span data-ttu-id="4a56e-127">El `Static` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="4a56e-127">The `Static` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="4a56e-128">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4a56e-128">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="4a56e-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a56e-129">See also</span></span>
- [<span data-ttu-id="4a56e-130">Shadows</span><span class="sxs-lookup"><span data-stu-id="4a56e-130">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="4a56e-131">Shared</span><span class="sxs-lookup"><span data-stu-id="4a56e-131">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="4a56e-132">Duración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4a56e-132">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="4a56e-133">Declaración de variables</span><span class="sxs-lookup"><span data-stu-id="4a56e-133">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="4a56e-134">Estructuras</span><span class="sxs-lookup"><span data-stu-id="4a56e-134">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="4a56e-135">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="4a56e-135">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="4a56e-136">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="4a56e-136">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
