---
description: 'Más información sobre: ampliación (Visual Basic)'
title: Widening
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
ms.openlocfilehash: de290296ba2b7716ba992c6bed46443053048282
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700707"
---
# <a name="widening-visual-basic"></a><span data-ttu-id="80154-103">Widening (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80154-103">Widening (Visual Basic)</span></span>

<span data-ttu-id="80154-104">Indica que un operador de conversión ( `CType` ) convierte una clase o estructura en un tipo que puede contener todos los valores posibles de la clase o estructura original.</span><span class="sxs-lookup"><span data-stu-id="80154-104">Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-widening-keyword"></a><span data-ttu-id="80154-105">Convertir con la palabra clave Widening</span><span class="sxs-lookup"><span data-stu-id="80154-105">Converting with the Widening Keyword</span></span>  

 <span data-ttu-id="80154-106">El procedimiento de conversión debe especificar además `Public Shared` de `Widening` .</span><span class="sxs-lookup"><span data-stu-id="80154-106">The conversion procedure must specify `Public Shared` in addition to `Widening`.</span></span>  
  
 <span data-ttu-id="80154-107">Las conversiones de ampliación siempre se realizan correctamente en tiempo de ejecución y nunca provocan pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="80154-107">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="80154-108">Por ejemplo `Single` , para, `Double` `Char` `String` y un tipo derivado a su tipo base.</span><span class="sxs-lookup"><span data-stu-id="80154-108">Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type.</span></span> <span data-ttu-id="80154-109">Esta última conversión es ampliable porque el tipo derivado contiene todos los miembros del tipo base y, por tanto, es una instancia del tipo base.</span><span class="sxs-lookup"><span data-stu-id="80154-109">This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.</span></span>  
  
 <span data-ttu-id="80154-110">El código utilizado no tiene que usar para las `CType` conversiones de ampliación, incluso si `Option Strict` es `On` .</span><span class="sxs-lookup"><span data-stu-id="80154-110">The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="80154-111">La `Widening` palabra clave se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="80154-111">The `Widening` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="80154-112">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="80154-112">Operator Statement</span></span>](../statements/operator-statement.md)  
  
 <span data-ttu-id="80154-113">Para obtener definiciones de ejemplo de operadores de conversión de ampliación y de restricción, vea [Cómo: definir un operador de conversión](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="80154-113">For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80154-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="80154-114">See also</span></span>

- [<span data-ttu-id="80154-115">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="80154-115">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="80154-116">Narrowing</span><span class="sxs-lookup"><span data-stu-id="80154-116">Narrowing</span></span>](narrowing.md)
- [<span data-ttu-id="80154-117">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="80154-117">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="80154-118">Procedimiento para definir un operador</span><span class="sxs-lookup"><span data-stu-id="80154-118">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="80154-119">CType Function</span><span class="sxs-lookup"><span data-stu-id="80154-119">CType Function</span></span>](../functions/ctype-function.md)
- [<span data-ttu-id="80154-120">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="80154-120">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
- [<span data-ttu-id="80154-121">Procedimiento para definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="80154-121">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
