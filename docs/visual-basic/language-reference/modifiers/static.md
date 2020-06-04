---
title: estática
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: 3b323d5fb1c4f1357b9f476213793c69d29b7208
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402699"
---
# <a name="static-visual-basic"></a><span data-ttu-id="694d5-102">Static (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="694d5-102">Static (Visual Basic)</span></span>
<span data-ttu-id="694d5-103">Especifica que una o varias variables locales declaradas deben seguir existiendo y conservar sus valores más recientes después de la finalización del procedimiento en el que se declaran.</span><span class="sxs-lookup"><span data-stu-id="694d5-103">Specifies that one or more declared local variables are to continue to exist and retain their latest values after termination of the procedure in which they are declared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="694d5-104">Observaciones</span><span class="sxs-lookup"><span data-stu-id="694d5-104">Remarks</span></span>  
 <span data-ttu-id="694d5-105">Normalmente, una variable local de un procedimiento deja de existir en cuanto se detiene el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="694d5-105">Normally, a local variable in a procedure ceases to exist as soon as the procedure stops.</span></span> <span data-ttu-id="694d5-106">Una variable estática sigue existiendo y conserva su valor más reciente.</span><span class="sxs-lookup"><span data-stu-id="694d5-106">A static variable continues to exist and retains its most recent value.</span></span> <span data-ttu-id="694d5-107">La próxima vez que el código llame al procedimiento, no se reinicializará la variable y se conservará el valor más reciente que le haya asignado.</span><span class="sxs-lookup"><span data-stu-id="694d5-107">The next time your code calls the procedure, the variable is not reinitialized, and it still holds the latest value that you assigned to it.</span></span> <span data-ttu-id="694d5-108">Una variable estática sigue existiendo mientras dure la clase o el módulo en el que se define.</span><span class="sxs-lookup"><span data-stu-id="694d5-108">A static variable continues to exist for the lifetime of the class or module that it is defined in.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="694d5-109">Reglas</span><span class="sxs-lookup"><span data-stu-id="694d5-109">Rules</span></span>  
  
- <span data-ttu-id="694d5-110">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="694d5-110">**Declaration Context.**</span></span> <span data-ttu-id="694d5-111">Solo se puede usar `Static` en variables locales.</span><span class="sxs-lookup"><span data-stu-id="694d5-111">You can use `Static` only on local variables.</span></span> <span data-ttu-id="694d5-112">Esto significa que el contexto de la declaración de una `Static` variable debe ser un procedimiento o un bloque de un procedimiento, y no puede ser un archivo de código fuente, un espacio de nombres, una clase, una estructura o un módulo.</span><span class="sxs-lookup"><span data-stu-id="694d5-112">This means the declaration context for a `Static` variable must be a procedure or a block in a procedure, and it cannot be a source file, namespace, class, structure, or module.</span></span>  
  
     <span data-ttu-id="694d5-113">No se puede usar `Static` dentro de un procedimiento de estructura.</span><span class="sxs-lookup"><span data-stu-id="694d5-113">You cannot use `Static` inside a structure procedure.</span></span>  
  
- <span data-ttu-id="694d5-114">No se pueden inferir los tipos de datos de `Static` las variables locales.</span><span class="sxs-lookup"><span data-stu-id="694d5-114">The data types of `Static` local variables cannot be inferred.</span></span> <span data-ttu-id="694d5-115">Para obtener más información, vea [inferencia de tipo local](../../programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="694d5-115">For more information, see [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
- <span data-ttu-id="694d5-116">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="694d5-116">**Combined Modifiers.**</span></span> <span data-ttu-id="694d5-117">No se puede especificar `Static` junto con `ReadOnly` , `Shadows` o `Shared` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="694d5-117">You cannot specify `Static` together with `ReadOnly`, `Shadows`, or `Shared` in the same declaration.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="694d5-118">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="694d5-118">Behavior</span></span>  
 <span data-ttu-id="694d5-119">Cuando se declara una variable estática en un `Shared` procedimiento, solo hay una copia de la variable estática disponible para toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="694d5-119">When you declare a static variable in a `Shared` procedure, only one copy of the static variable is available for the whole application.</span></span> <span data-ttu-id="694d5-120">Se llama a un `Shared` procedimiento mediante el nombre de clase, no una variable que apunta a una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="694d5-120">You call a `Shared` procedure by using the class name, not a variable that points to an instance of the class.</span></span>  
  
 <span data-ttu-id="694d5-121">Cuando se declara una variable estática en un procedimiento que no es `Shared` , solo está disponible una copia de la variable para cada instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="694d5-121">When you declare a static variable in a procedure that isn't `Shared`, only one copy of the variable is available for each instance of the class.</span></span> <span data-ttu-id="694d5-122">Se llama a un procedimiento no compartido mediante una variable que apunta a una instancia específica de la clase.</span><span class="sxs-lookup"><span data-stu-id="694d5-122">You call a non-shared procedure by using a variable that points to a specific instance of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="694d5-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="694d5-123">Example</span></span>  
 <span data-ttu-id="694d5-124">El siguiente ejemplo muestra el uso de `Static`.</span><span class="sxs-lookup"><span data-stu-id="694d5-124">The following example demonstrates the use of `Static`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 <span data-ttu-id="694d5-125">La `Static` variable `totalSales` se inicializa en 0 solo una vez.</span><span class="sxs-lookup"><span data-stu-id="694d5-125">The `Static` variable `totalSales` is initialized to 0 only one time.</span></span> <span data-ttu-id="694d5-126">Cada vez que escriba `updateSales` , `totalSales` seguirá teniendo el valor más reciente que calculó para él.</span><span class="sxs-lookup"><span data-stu-id="694d5-126">Each time that you enter `updateSales`, `totalSales` still has the most recent value that you calculated for it.</span></span>  
  
 <span data-ttu-id="694d5-127">El `Static` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="694d5-127">The `Static` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="694d5-128">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="694d5-128">Dim Statement</span></span>](../statements/dim-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="694d5-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="694d5-129">See also</span></span>

- [<span data-ttu-id="694d5-130">Shadows</span><span class="sxs-lookup"><span data-stu-id="694d5-130">Shadows</span></span>](shadows.md)
- [<span data-ttu-id="694d5-131">Compartido</span><span class="sxs-lookup"><span data-stu-id="694d5-131">Shared</span></span>](shared.md)
- [<span data-ttu-id="694d5-132">Período de duración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="694d5-132">Lifetime in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="694d5-133">Declaración de variable</span><span class="sxs-lookup"><span data-stu-id="694d5-133">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="694d5-134">Estructuras</span><span class="sxs-lookup"><span data-stu-id="694d5-134">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="694d5-135">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="694d5-135">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="694d5-136">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="694d5-136">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
