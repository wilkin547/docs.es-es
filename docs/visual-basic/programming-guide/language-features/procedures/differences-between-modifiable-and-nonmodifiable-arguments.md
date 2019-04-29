---
title: Diferencias entre argumentos modificables y no modificables (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
ms.openlocfilehash: a880ae8c13eebd5d9d325468098e058f58d3fa71
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665954"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a><span data-ttu-id="fe6ce-102">Diferencias entre argumentos modificables y no modificables (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe6ce-102">Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic)</span></span>
<span data-ttu-id="fe6ce-103">Cuando se llama a un procedimiento, normalmente pass uno o más argumentos a él.</span><span class="sxs-lookup"><span data-stu-id="fe6ce-103">When you call a procedure, you typically pass one or more arguments to it.</span></span> <span data-ttu-id="fe6ce-104">Cada argumento corresponde a un elemento de programación subyacente.</span><span class="sxs-lookup"><span data-stu-id="fe6ce-104">Each argument corresponds to an underlying programming element.</span></span> <span data-ttu-id="fe6ce-105">Los elementos subyacentes y los argumentos pueden ser modificable o no modificable.</span><span class="sxs-lookup"><span data-stu-id="fe6ce-105">Both the underlying elements and the arguments themselves can be either modifiable or nonmodifiable.</span></span>  
  
## <a name="modifiable-and-nonmodifiable-elements"></a><span data-ttu-id="fe6ce-106">Elementos modificables y no modificables</span><span class="sxs-lookup"><span data-stu-id="fe6ce-106">Modifiable and Nonmodifiable Elements</span></span>  
 <span data-ttu-id="fe6ce-107">Un elemento de programación puede ser un *elemento modificable*, que puede tener su valor cambiado, o un *elemento no modificable*, que tiene un valor fijo, una vez que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="fe6ce-107">A programming element can be either a *modifiable element*, which can have its value changed, or a *nonmodifiable element*, which has a fixed value once it has been created.</span></span>  
  
 <span data-ttu-id="fe6ce-108">En la tabla siguiente enumera los elementos de programación modificables y no modificables.</span><span class="sxs-lookup"><span data-stu-id="fe6ce-108">The following table lists modifiable and nonmodifiable programming elements.</span></span>  
  
|<span data-ttu-id="fe6ce-109">Puede modificables elementos</span><span class="sxs-lookup"><span data-stu-id="fe6ce-109">Modifiable elements</span></span>|<span data-ttu-id="fe6ce-110">Elementos no modificables</span><span class="sxs-lookup"><span data-stu-id="fe6ce-110">Nonmodifiable elements</span></span>|  
|-------------------------|----------------------------|  
|<span data-ttu-id="fe6ce-111">Las variables locales (declaradas dentro de procedimientos), incluidas las variables de objeto, excepto de solo lectura</span><span class="sxs-lookup"><span data-stu-id="fe6ce-111">Local variables (declared inside procedures), including object variables, except for read-only</span></span>|<span data-ttu-id="fe6ce-112">Propiedades, campos y variables de solo lectura</span><span class="sxs-lookup"><span data-stu-id="fe6ce-112">Read-only variables, fields, and properties</span></span>|  
|<span data-ttu-id="fe6ce-113">Campos (variables de miembro de los módulos, clases y estructuras), excepto los de solo lectura</span><span class="sxs-lookup"><span data-stu-id="fe6ce-113">Fields (member variables of modules, classes, and structures), except for read-only</span></span>|<span data-ttu-id="fe6ce-114">Constantes y literales</span><span class="sxs-lookup"><span data-stu-id="fe6ce-114">Constants and literals</span></span>|  
|<span data-ttu-id="fe6ce-115">Propiedades, excepto de solo lectura</span><span class="sxs-lookup"><span data-stu-id="fe6ce-115">Properties, except for read-only</span></span>|<span data-ttu-id="fe6ce-116">Miembros de enumeración</span><span class="sxs-lookup"><span data-stu-id="fe6ce-116">Enumeration members</span></span>|  
|<span data-ttu-id="fe6ce-117">Elementos de matriz</span><span class="sxs-lookup"><span data-stu-id="fe6ce-117">Array elements</span></span>|<span data-ttu-id="fe6ce-118">Expresiones (incluso si sus elementos son modificables)</span><span class="sxs-lookup"><span data-stu-id="fe6ce-118">Expressions (even if their elements are modifiable)</span></span>|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a><span data-ttu-id="fe6ce-119">Argumentos modificables y no modificables</span><span class="sxs-lookup"><span data-stu-id="fe6ce-119">Modifiable and Nonmodifiable Arguments</span></span>  
 <span data-ttu-id="fe6ce-120">Un *argumento modificable* es uno con un elemento subyacente modificable.</span><span class="sxs-lookup"><span data-stu-id="fe6ce-120">A *modifiable argument* is one with a modifiable underlying element.</span></span> <span data-ttu-id="fe6ce-121">El código de llamada puede almacenar un nuevo valor en cualquier momento, y si se pasa el argumento [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), el código en el procedimiento también puede modificar el elemento subyacente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="fe6ce-121">The calling code can store a new value at any time, and if you pass the argument [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the code in the procedure can also modify the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="fe6ce-122">Un *argumento no es modificable* tiene un elemento subyacente no modificable o se pasa [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="fe6ce-122">A *nonmodifiable argument* either has a nonmodifiable underlying element or is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="fe6ce-123">El procedimiento no puede modificar el elemento subyacente en el código que realiza la llamada, incluso si es un elemento modificable.</span><span class="sxs-lookup"><span data-stu-id="fe6ce-123">The procedure cannot modify the underlying element in the calling code, even if it is a modifiable element.</span></span> <span data-ttu-id="fe6ce-124">Si es un elemento no modificable, el código de llamada no puede modificarla.</span><span class="sxs-lookup"><span data-stu-id="fe6ce-124">If it is a nonmodifiable element, the calling code itself cannot modify it.</span></span>  
  
 <span data-ttu-id="fe6ce-125">El procedimiento llamado podría modificar su copia local de un argumento no es modificable, pero esa modificación no afecta el elemento subyacente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="fe6ce-125">The called procedure might modify its local copy of a nonmodifiable argument, but that modification does not affect the underlying element in the calling code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe6ce-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe6ce-126">See also</span></span>

- [<span data-ttu-id="fe6ce-127">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="fe6ce-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="fe6ce-128">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="fe6ce-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="fe6ce-129">Cómo: Pasar argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="fe6ce-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="fe6ce-130">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="fe6ce-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="fe6ce-131">Diferencias entre pasar un argumento por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="fe6ce-131">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="fe6ce-132">Cómo: Cambie el valor de un argumento de procedimiento</span><span class="sxs-lookup"><span data-stu-id="fe6ce-132">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="fe6ce-133">Cómo: Proteger un argumento de procedimiento contra cambios de valor</span><span class="sxs-lookup"><span data-stu-id="fe6ce-133">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="fe6ce-134">Cómo: Forzar un argumento para pasar por valor</span><span class="sxs-lookup"><span data-stu-id="fe6ce-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="fe6ce-135">Paso de argumentos por posición o por nombre</span><span class="sxs-lookup"><span data-stu-id="fe6ce-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="fe6ce-136">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="fe6ce-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
