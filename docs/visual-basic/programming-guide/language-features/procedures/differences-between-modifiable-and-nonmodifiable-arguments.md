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
ms.openlocfilehash: 733f92cc2cdaa6e923c57649774ceb64de172c18
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403348"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a><span data-ttu-id="9c77a-102">Diferencias entre argumentos modificables y no modificables (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c77a-102">Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic)</span></span>
<span data-ttu-id="9c77a-103">Cuando se llama a un procedimiento, normalmente se pasan uno o más argumentos.</span><span class="sxs-lookup"><span data-stu-id="9c77a-103">When you call a procedure, you typically pass one or more arguments to it.</span></span> <span data-ttu-id="9c77a-104">Cada argumento corresponde a un elemento de programación subyacente.</span><span class="sxs-lookup"><span data-stu-id="9c77a-104">Each argument corresponds to an underlying programming element.</span></span> <span data-ttu-id="9c77a-105">Tanto los elementos subyacentes como los argumentos pueden ser modificables o no modificables.</span><span class="sxs-lookup"><span data-stu-id="9c77a-105">Both the underlying elements and the arguments themselves can be either modifiable or nonmodifiable.</span></span>  
  
## <a name="modifiable-and-nonmodifiable-elements"></a><span data-ttu-id="9c77a-106">Elementos modificables y no modificables</span><span class="sxs-lookup"><span data-stu-id="9c77a-106">Modifiable and Nonmodifiable Elements</span></span>  
 <span data-ttu-id="9c77a-107">Un elemento de programación puede ser un *elemento modificable*, cuyo valor se puede cambiar o un elemento no *modificable*, que tiene un valor fijo una vez que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="9c77a-107">A programming element can be either a *modifiable element*, which can have its value changed, or a *nonmodifiable element*, which has a fixed value once it has been created.</span></span>  
  
 <span data-ttu-id="9c77a-108">En la tabla siguiente se enumeran los elementos de programación modificables y no modificables.</span><span class="sxs-lookup"><span data-stu-id="9c77a-108">The following table lists modifiable and nonmodifiable programming elements.</span></span>  
  
|<span data-ttu-id="9c77a-109">Elementos modificables</span><span class="sxs-lookup"><span data-stu-id="9c77a-109">Modifiable elements</span></span>|<span data-ttu-id="9c77a-110">Elementos no modificables</span><span class="sxs-lookup"><span data-stu-id="9c77a-110">Nonmodifiable elements</span></span>|  
|-------------------------|----------------------------|  
|<span data-ttu-id="9c77a-111">Variables locales (declaradas dentro de los procedimientos), incluidas las variables de objeto, excepto para solo lectura</span><span class="sxs-lookup"><span data-stu-id="9c77a-111">Local variables (declared inside procedures), including object variables, except for read-only</span></span>|<span data-ttu-id="9c77a-112">Variables, campos y propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="9c77a-112">Read-only variables, fields, and properties</span></span>|  
|<span data-ttu-id="9c77a-113">Campos (variables miembro de módulos, clases y estructuras), excepto para solo lectura</span><span class="sxs-lookup"><span data-stu-id="9c77a-113">Fields (member variables of modules, classes, and structures), except for read-only</span></span>|<span data-ttu-id="9c77a-114">Constantes y literales</span><span class="sxs-lookup"><span data-stu-id="9c77a-114">Constants and literals</span></span>|  
|<span data-ttu-id="9c77a-115">Propiedades, excepto para solo lectura</span><span class="sxs-lookup"><span data-stu-id="9c77a-115">Properties, except for read-only</span></span>|<span data-ttu-id="9c77a-116">Miembros de enumeración</span><span class="sxs-lookup"><span data-stu-id="9c77a-116">Enumeration members</span></span>|  
|<span data-ttu-id="9c77a-117">Elementos de matriz</span><span class="sxs-lookup"><span data-stu-id="9c77a-117">Array elements</span></span>|<span data-ttu-id="9c77a-118">Expresiones (incluso si sus elementos son modificables)</span><span class="sxs-lookup"><span data-stu-id="9c77a-118">Expressions (even if their elements are modifiable)</span></span>|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a><span data-ttu-id="9c77a-119">Argumentos modificables y no modificables</span><span class="sxs-lookup"><span data-stu-id="9c77a-119">Modifiable and Nonmodifiable Arguments</span></span>  
 <span data-ttu-id="9c77a-120">Un *argumento modificable* es uno con un elemento subyacente modificable.</span><span class="sxs-lookup"><span data-stu-id="9c77a-120">A *modifiable argument* is one with a modifiable underlying element.</span></span> <span data-ttu-id="9c77a-121">El código de llamada puede almacenar un nuevo valor en cualquier momento y, si se pasa el argumento [ByRef](../../../language-reference/modifiers/byref.md), el código del procedimiento también puede modificar el elemento subyacente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="9c77a-121">The calling code can store a new value at any time, and if you pass the argument [ByRef](../../../language-reference/modifiers/byref.md), the code in the procedure can also modify the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="9c77a-122">Un *argumento no modificable* tiene un elemento subyacente no modificable o se pasa [ByVal](../../../language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="9c77a-122">A *nonmodifiable argument* either has a nonmodifiable underlying element or is passed [ByVal](../../../language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="9c77a-123">El procedimiento no puede modificar el elemento subyacente en el código de llamada, aunque sea un elemento modificable.</span><span class="sxs-lookup"><span data-stu-id="9c77a-123">The procedure cannot modify the underlying element in the calling code, even if it is a modifiable element.</span></span> <span data-ttu-id="9c77a-124">Si es un elemento no modificable, el propio código de llamada no puede modificarlo.</span><span class="sxs-lookup"><span data-stu-id="9c77a-124">If it is a nonmodifiable element, the calling code itself cannot modify it.</span></span>  
  
 <span data-ttu-id="9c77a-125">El procedimiento llamado podría modificar su copia local de un argumento no modificable, pero esa modificación no afecta al elemento subyacente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="9c77a-125">The called procedure might modify its local copy of a nonmodifiable argument, but that modification does not affect the underlying element in the calling code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c77a-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9c77a-126">See also</span></span>

- [<span data-ttu-id="9c77a-127">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="9c77a-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="9c77a-128">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="9c77a-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="9c77a-129">Procedimiento para pasar argumentos a un procedimiento</span><span class="sxs-lookup"><span data-stu-id="9c77a-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="9c77a-130">Pasar argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="9c77a-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="9c77a-131">Diferencias entre pasar un argumento por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="9c77a-131">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="9c77a-132">Procedimiento para cambiar el valor de un argumento de procedimiento</span><span class="sxs-lookup"><span data-stu-id="9c77a-132">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="9c77a-133">Procedimiento para proteger un argumento de procedimiento para que no se realicen cambios de valor</span><span class="sxs-lookup"><span data-stu-id="9c77a-133">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="9c77a-134">Procedimiento para forzar un argumento para que pase como un valor</span><span class="sxs-lookup"><span data-stu-id="9c77a-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="9c77a-135">Pasar argumentos por posición o por nombre</span><span class="sxs-lookup"><span data-stu-id="9c77a-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="9c77a-136">Tipos de valor y tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="9c77a-136">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
