---
description: 'Más información acerca de: Static (Visual Basic)'
title: estática
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: 03c2e3f64ac9052a0c604b8bc34782af16edbf34
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700746"
---
# <a name="static-visual-basic"></a><span data-ttu-id="63d4b-103">Static (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63d4b-103">Static (Visual Basic)</span></span>

<span data-ttu-id="63d4b-104">Especifica que una o varias variables locales declaradas deben seguir existiendo y conservar sus valores más recientes después de la finalización del procedimiento en el que se declaran.</span><span class="sxs-lookup"><span data-stu-id="63d4b-104">Specifies that one or more declared local variables are to continue to exist and retain their latest values after termination of the procedure in which they are declared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63d4b-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="63d4b-105">Remarks</span></span>  

 <span data-ttu-id="63d4b-106">Normalmente, una variable local de un procedimiento deja de existir en cuanto se detiene el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="63d4b-106">Normally, a local variable in a procedure ceases to exist as soon as the procedure stops.</span></span> <span data-ttu-id="63d4b-107">Una variable estática sigue existiendo y conserva su valor más reciente.</span><span class="sxs-lookup"><span data-stu-id="63d4b-107">A static variable continues to exist and retains its most recent value.</span></span> <span data-ttu-id="63d4b-108">La próxima vez que el código llame al procedimiento, no se reinicializará la variable y se conservará el valor más reciente que le haya asignado.</span><span class="sxs-lookup"><span data-stu-id="63d4b-108">The next time your code calls the procedure, the variable is not reinitialized, and it still holds the latest value that you assigned to it.</span></span> <span data-ttu-id="63d4b-109">Una variable estática sigue existiendo mientras dure la clase o el módulo en el que se define.</span><span class="sxs-lookup"><span data-stu-id="63d4b-109">A static variable continues to exist for the lifetime of the class or module that it is defined in.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="63d4b-110">Reglas</span><span class="sxs-lookup"><span data-stu-id="63d4b-110">Rules</span></span>  
  
- <span data-ttu-id="63d4b-111">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="63d4b-111">**Declaration Context.**</span></span> <span data-ttu-id="63d4b-112">Solo se puede usar `Static` en variables locales.</span><span class="sxs-lookup"><span data-stu-id="63d4b-112">You can use `Static` only on local variables.</span></span> <span data-ttu-id="63d4b-113">Esto significa que el contexto de la declaración de una `Static` variable debe ser un procedimiento o un bloque de un procedimiento, y no puede ser un archivo de código fuente, un espacio de nombres, una clase, una estructura o un módulo.</span><span class="sxs-lookup"><span data-stu-id="63d4b-113">This means the declaration context for a `Static` variable must be a procedure or a block in a procedure, and it cannot be a source file, namespace, class, structure, or module.</span></span>  
  
     <span data-ttu-id="63d4b-114">No se puede usar `Static` dentro de un procedimiento de estructura.</span><span class="sxs-lookup"><span data-stu-id="63d4b-114">You cannot use `Static` inside a structure procedure.</span></span>  
  
- <span data-ttu-id="63d4b-115">No se pueden inferir los tipos de datos de `Static` las variables locales.</span><span class="sxs-lookup"><span data-stu-id="63d4b-115">The data types of `Static` local variables cannot be inferred.</span></span> <span data-ttu-id="63d4b-116">Para obtener más información, vea [inferencia de tipo local](../../programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="63d4b-116">For more information, see [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
- <span data-ttu-id="63d4b-117">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="63d4b-117">**Combined Modifiers.**</span></span> <span data-ttu-id="63d4b-118">No se puede especificar `Static` junto con `ReadOnly` , `Shadows` o `Shared` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="63d4b-118">You cannot specify `Static` together with `ReadOnly`, `Shadows`, or `Shared` in the same declaration.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="63d4b-119">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="63d4b-119">Behavior</span></span>  

 <span data-ttu-id="63d4b-120">Cuando se declara una variable estática en un `Shared` procedimiento, solo hay una copia de la variable estática disponible para toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="63d4b-120">When you declare a static variable in a `Shared` procedure, only one copy of the static variable is available for the whole application.</span></span> <span data-ttu-id="63d4b-121">Se llama a un `Shared` procedimiento mediante el nombre de clase, no una variable que apunta a una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="63d4b-121">You call a `Shared` procedure by using the class name, not a variable that points to an instance of the class.</span></span>  
  
 <span data-ttu-id="63d4b-122">Cuando se declara una variable estática en un procedimiento que no es `Shared` , solo está disponible una copia de la variable para cada instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="63d4b-122">When you declare a static variable in a procedure that isn't `Shared`, only one copy of the variable is available for each instance of the class.</span></span> <span data-ttu-id="63d4b-123">Se llama a un procedimiento no compartido mediante una variable que apunta a una instancia específica de la clase.</span><span class="sxs-lookup"><span data-stu-id="63d4b-123">You call a non-shared procedure by using a variable that points to a specific instance of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63d4b-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="63d4b-124">Example</span></span>  

 <span data-ttu-id="63d4b-125">El siguiente ejemplo muestra el uso de `Static`.</span><span class="sxs-lookup"><span data-stu-id="63d4b-125">The following example demonstrates the use of `Static`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 <span data-ttu-id="63d4b-126">La `Static` variable `totalSales` se inicializa en 0 solo una vez.</span><span class="sxs-lookup"><span data-stu-id="63d4b-126">The `Static` variable `totalSales` is initialized to 0 only one time.</span></span> <span data-ttu-id="63d4b-127">Cada vez que escriba `updateSales` , `totalSales` seguirá teniendo el valor más reciente que calculó para él.</span><span class="sxs-lookup"><span data-stu-id="63d4b-127">Each time that you enter `updateSales`, `totalSales` still has the most recent value that you calculated for it.</span></span>  
  
 <span data-ttu-id="63d4b-128">El `Static` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="63d4b-128">The `Static` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="63d4b-129">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="63d4b-129">Dim Statement</span></span>](../statements/dim-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="63d4b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="63d4b-130">See also</span></span>

- [<span data-ttu-id="63d4b-131">Shadows</span><span class="sxs-lookup"><span data-stu-id="63d4b-131">Shadows</span></span>](shadows.md)
- [<span data-ttu-id="63d4b-132">Compartido</span><span class="sxs-lookup"><span data-stu-id="63d4b-132">Shared</span></span>](shared.md)
- [<span data-ttu-id="63d4b-133">Período de duración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="63d4b-133">Lifetime in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="63d4b-134">Declaración de variable</span><span class="sxs-lookup"><span data-stu-id="63d4b-134">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="63d4b-135">Estructuras</span><span class="sxs-lookup"><span data-stu-id="63d4b-135">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="63d4b-136">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="63d4b-136">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="63d4b-137">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="63d4b-137">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
