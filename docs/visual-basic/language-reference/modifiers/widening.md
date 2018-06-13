---
title: Widening (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
ms.openlocfilehash: 2323aa38c81ce4e027f256d0e29c069f7ec77c00
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595318"
---
# <a name="widening-visual-basic"></a><span data-ttu-id="619d6-102">Widening (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="619d6-102">Widening (Visual Basic)</span></span>
<span data-ttu-id="619d6-103">Indica que un operador de conversión (`CType`) convierte una clase o estructura en un tipo que puede contener todos los valores posibles de la clase o estructura original.</span><span class="sxs-lookup"><span data-stu-id="619d6-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-widening-keyword"></a><span data-ttu-id="619d6-104">Convertir con la palabra clave Widening</span><span class="sxs-lookup"><span data-stu-id="619d6-104">Converting with the Widening Keyword</span></span>  
 <span data-ttu-id="619d6-105">El procedimiento de conversión debe especificar `Public Shared` además `Widening`.</span><span class="sxs-lookup"><span data-stu-id="619d6-105">The conversion procedure must specify `Public Shared` in addition to `Widening`.</span></span>  
  
 <span data-ttu-id="619d6-106">Conversiones de ampliación siempre se ejecute correctamente en tiempo de ejecución y nunca provocar la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="619d6-106">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="619d6-107">Algunos ejemplos son `Single` a `Double`, `Char` a `String`y un tipo derivado a su tipo base.</span><span class="sxs-lookup"><span data-stu-id="619d6-107">Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type.</span></span> <span data-ttu-id="619d6-108">Esta última conversión es de ampliación porque el tipo derivado contiene a todos los miembros del tipo base y, por tanto, es una instancia del tipo base.</span><span class="sxs-lookup"><span data-stu-id="619d6-108">This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.</span></span>  
  
 <span data-ttu-id="619d6-109">El código usado no tiene que usar `CType` para conversiones de ampliación, incluso si `Option Strict` es `On`.</span><span class="sxs-lookup"><span data-stu-id="619d6-109">The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="619d6-110">El `Widening` palabra clave se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="619d6-110">The `Widening` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="619d6-111">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="619d6-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 <span data-ttu-id="619d6-112">Por ejemplo ver definiciones de los operadores de conversión de restricción y ampliación [Cómo: definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="619d6-112">For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="619d6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="619d6-113">See Also</span></span>  
 [<span data-ttu-id="619d6-114">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="619d6-114">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="619d6-115">Narrowing</span><span class="sxs-lookup"><span data-stu-id="619d6-115">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="619d6-116">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="619d6-116">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="619d6-117">Definir un operador</span><span class="sxs-lookup"><span data-stu-id="619d6-117">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="619d6-118">Función CType</span><span class="sxs-lookup"><span data-stu-id="619d6-118">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)  
 [<span data-ttu-id="619d6-119">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="619d6-119">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="619d6-120">Definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="619d6-120">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
