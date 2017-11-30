---
title: Widening (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 034099397c1d296a42712b8c202e2ac99a0fb43b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="widening-visual-basic"></a><span data-ttu-id="f12a4-102">Widening (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f12a4-102">Widening (Visual Basic)</span></span>
<span data-ttu-id="f12a4-103">Indica que un operador de conversión (`CType`) convierte una clase o estructura en un tipo que puede contener todos los valores posibles de la clase o estructura original.</span><span class="sxs-lookup"><span data-stu-id="f12a4-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-widening-keyword"></a><span data-ttu-id="f12a4-104">Convertir con la palabra clave Widening</span><span class="sxs-lookup"><span data-stu-id="f12a4-104">Converting with the Widening Keyword</span></span>  
 <span data-ttu-id="f12a4-105">El procedimiento de conversión debe especificar `Public Shared` además `Widening`.</span><span class="sxs-lookup"><span data-stu-id="f12a4-105">The conversion procedure must specify `Public Shared` in addition to `Widening`.</span></span>  
  
 <span data-ttu-id="f12a4-106">Conversiones de ampliación siempre se ejecute correctamente en tiempo de ejecución y nunca provocar la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="f12a4-106">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="f12a4-107">Algunos ejemplos son `Single` a `Double`, `Char` a `String`y un tipo derivado a su tipo base.</span><span class="sxs-lookup"><span data-stu-id="f12a4-107">Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type.</span></span> <span data-ttu-id="f12a4-108">Esta última conversión es de ampliación porque el tipo derivado contiene a todos los miembros del tipo base y, por tanto, es una instancia del tipo base.</span><span class="sxs-lookup"><span data-stu-id="f12a4-108">This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.</span></span>  
  
 <span data-ttu-id="f12a4-109">El código usado no tiene que usar `CType` para conversiones de ampliación, incluso si `Option Strict` es `On`.</span><span class="sxs-lookup"><span data-stu-id="f12a4-109">The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="f12a4-110">El `Widening` palabra clave se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="f12a4-110">The `Widening` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="f12a4-111">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f12a4-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 <span data-ttu-id="f12a4-112">Por ejemplo ver definiciones de los operadores de conversión de restricción y ampliación [Cómo: definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="f12a4-112">For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f12a4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f12a4-113">See Also</span></span>  
 [<span data-ttu-id="f12a4-114">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f12a4-114">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="f12a4-115">Narrowing</span><span class="sxs-lookup"><span data-stu-id="f12a4-115">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="f12a4-116">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="f12a4-116">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="f12a4-117">Definir un operador</span><span class="sxs-lookup"><span data-stu-id="f12a4-117">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="f12a4-118">Función CType</span><span class="sxs-lookup"><span data-stu-id="f12a4-118">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)  
 [<span data-ttu-id="f12a4-119">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f12a4-119">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="f12a4-120">Definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="f12a4-120">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
