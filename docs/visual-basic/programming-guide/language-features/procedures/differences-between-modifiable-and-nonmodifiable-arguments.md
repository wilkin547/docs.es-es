---
title: Diferencias entre argumentos modificables y no modificables
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
ms.openlocfilehash: 989795ee2cdd3a78b71bad4d95cf9b384c2719bd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74341393"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a><span data-ttu-id="4de92-102">Diferencias entre argumentos modificables y no modificables (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4de92-102">Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic)</span></span>
<span data-ttu-id="4de92-103">Cuando se llama a un procedimiento, normalmente se pasan uno o más argumentos.</span><span class="sxs-lookup"><span data-stu-id="4de92-103">When you call a procedure, you typically pass one or more arguments to it.</span></span> <span data-ttu-id="4de92-104">Cada argumento corresponde a un elemento de programación subyacente.</span><span class="sxs-lookup"><span data-stu-id="4de92-104">Each argument corresponds to an underlying programming element.</span></span> <span data-ttu-id="4de92-105">Tanto los elementos subyacentes como los argumentos pueden ser modificables o no modificables.</span><span class="sxs-lookup"><span data-stu-id="4de92-105">Both the underlying elements and the arguments themselves can be either modifiable or nonmodifiable.</span></span>  
  
## <a name="modifiable-and-nonmodifiable-elements"></a><span data-ttu-id="4de92-106">Elementos modificables y no modificables</span><span class="sxs-lookup"><span data-stu-id="4de92-106">Modifiable and Nonmodifiable Elements</span></span>  
 <span data-ttu-id="4de92-107">Un elemento de programación puede ser un *elemento modificable*, cuyo valor se puede cambiar o un elemento no *modificable*, que tiene un valor fijo una vez que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="4de92-107">A programming element can be either a *modifiable element*, which can have its value changed, or a *nonmodifiable element*, which has a fixed value once it has been created.</span></span>  
  
 <span data-ttu-id="4de92-108">En la tabla siguiente se enumeran los elementos de programación modificables y no modificables.</span><span class="sxs-lookup"><span data-stu-id="4de92-108">The following table lists modifiable and nonmodifiable programming elements.</span></span>  
  
|<span data-ttu-id="4de92-109">Elementos modificables</span><span class="sxs-lookup"><span data-stu-id="4de92-109">Modifiable elements</span></span>|<span data-ttu-id="4de92-110">Elementos no modificables</span><span class="sxs-lookup"><span data-stu-id="4de92-110">Nonmodifiable elements</span></span>|  
|-------------------------|----------------------------|  
|<span data-ttu-id="4de92-111">Variables locales (declaradas dentro de los procedimientos), incluidas las variables de objeto, excepto para solo lectura</span><span class="sxs-lookup"><span data-stu-id="4de92-111">Local variables (declared inside procedures), including object variables, except for read-only</span></span>|<span data-ttu-id="4de92-112">Variables, campos y propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="4de92-112">Read-only variables, fields, and properties</span></span>|  
|<span data-ttu-id="4de92-113">Campos (variables miembro de módulos, clases y estructuras), excepto para solo lectura</span><span class="sxs-lookup"><span data-stu-id="4de92-113">Fields (member variables of modules, classes, and structures), except for read-only</span></span>|<span data-ttu-id="4de92-114">Constantes y literales</span><span class="sxs-lookup"><span data-stu-id="4de92-114">Constants and literals</span></span>|  
|<span data-ttu-id="4de92-115">Propiedades, excepto para solo lectura</span><span class="sxs-lookup"><span data-stu-id="4de92-115">Properties, except for read-only</span></span>|<span data-ttu-id="4de92-116">Miembros de enumeración</span><span class="sxs-lookup"><span data-stu-id="4de92-116">Enumeration members</span></span>|  
|<span data-ttu-id="4de92-117">Elementos de matriz</span><span class="sxs-lookup"><span data-stu-id="4de92-117">Array elements</span></span>|<span data-ttu-id="4de92-118">Expresiones (incluso si sus elementos son modificables)</span><span class="sxs-lookup"><span data-stu-id="4de92-118">Expressions (even if their elements are modifiable)</span></span>|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a><span data-ttu-id="4de92-119">Argumentos modificables y no modificables</span><span class="sxs-lookup"><span data-stu-id="4de92-119">Modifiable and Nonmodifiable Arguments</span></span>  
 <span data-ttu-id="4de92-120">Un *argumento modificable* es uno con un elemento subyacente modificable.</span><span class="sxs-lookup"><span data-stu-id="4de92-120">A *modifiable argument* is one with a modifiable underlying element.</span></span> <span data-ttu-id="4de92-121">El código de llamada puede almacenar un nuevo valor en cualquier momento y, si se pasa el argumento [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), el código del procedimiento también puede modificar el elemento subyacente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="4de92-121">The calling code can store a new value at any time, and if you pass the argument [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the code in the procedure can also modify the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="4de92-122">Un *argumento no modificable* tiene un elemento subyacente no modificable o se pasa [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="4de92-122">A *nonmodifiable argument* either has a nonmodifiable underlying element or is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="4de92-123">El procedimiento no puede modificar el elemento subyacente en el código de llamada, aunque sea un elemento modificable.</span><span class="sxs-lookup"><span data-stu-id="4de92-123">The procedure cannot modify the underlying element in the calling code, even if it is a modifiable element.</span></span> <span data-ttu-id="4de92-124">Si es un elemento no modificable, el propio código de llamada no puede modificarlo.</span><span class="sxs-lookup"><span data-stu-id="4de92-124">If it is a nonmodifiable element, the calling code itself cannot modify it.</span></span>  
  
 <span data-ttu-id="4de92-125">El procedimiento llamado podría modificar su copia local de un argumento no modificable, pero esa modificación no afecta al elemento subyacente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="4de92-125">The called procedure might modify its local copy of a nonmodifiable argument, but that modification does not affect the underlying element in the calling code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4de92-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="4de92-126">See also</span></span>

- [<span data-ttu-id="4de92-127">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="4de92-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="4de92-128">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="4de92-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="4de92-129">Pasar argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="4de92-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="4de92-130">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="4de92-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="4de92-131">Diferencias entre pasar un argumento por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="4de92-131">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="4de92-132">Cambiar el valor de un argumento de procedimiento</span><span class="sxs-lookup"><span data-stu-id="4de92-132">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="4de92-133">Proteger un argumento de procedimiento para que no se realicen cambios de valor</span><span class="sxs-lookup"><span data-stu-id="4de92-133">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="4de92-134">Forzar un argumento para que pase como un valor</span><span class="sxs-lookup"><span data-stu-id="4de92-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="4de92-135">Paso de argumentos por posición o por nombre</span><span class="sxs-lookup"><span data-stu-id="4de92-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="4de92-136">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="4de92-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
