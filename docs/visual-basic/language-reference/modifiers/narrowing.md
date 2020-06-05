---
title: Narrowing
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: f7724053e3732c909523e4e2d3b65bb1918c29d3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84362364"
---
# <a name="narrowing-visual-basic"></a><span data-ttu-id="b60ca-102">Narrowing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b60ca-102">Narrowing (Visual Basic)</span></span>
<span data-ttu-id="b60ca-103">Indica que un operador de conversión ( `CType` ) convierte una clase o estructura en un tipo que podría no contener algunos de los valores posibles de la clase o estructura original.</span><span class="sxs-lookup"><span data-stu-id="b60ca-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that might not be able to hold some of the possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-narrowing-keyword"></a><span data-ttu-id="b60ca-104">Convertir con la palabra clave narrowing</span><span class="sxs-lookup"><span data-stu-id="b60ca-104">Converting with the Narrowing Keyword</span></span>  
 <span data-ttu-id="b60ca-105">El procedimiento de conversión debe especificar además `Public Shared` de `Narrowing` .</span><span class="sxs-lookup"><span data-stu-id="b60ca-105">The conversion procedure must specify `Public Shared` in addition to `Narrowing`.</span></span>  
  
 <span data-ttu-id="b60ca-106">Las conversiones de restricción no siempre se realizan correctamente en tiempo de ejecución y pueden producir un error o provocar la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="b60ca-106">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="b60ca-107">Por ejemplo `Long` , para, `Integer` `String` `Date` y un tipo base para un tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="b60ca-107">Examples are `Long` to `Integer`, `String` to `Date`, and a base type to a derived type.</span></span> <span data-ttu-id="b60ca-108">Esta última conversión está restringida porque el tipo base no puede contener todos los miembros del tipo derivado y, por tanto, no es una instancia del tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="b60ca-108">This last conversion is narrowing because the base type might not contain all the members of the derived type and thus is not an instance of the derived type.</span></span>  
  
 <span data-ttu-id="b60ca-109">Si `Option Strict` es `On` , el código utilizado debe usar `CType` para todas las conversiones de restricción.</span><span class="sxs-lookup"><span data-stu-id="b60ca-109">If `Option Strict` is `On`, the consuming code must use `CType` for all narrowing conversions.</span></span>  
  
 <span data-ttu-id="b60ca-110">La `Narrowing` palabra clave se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="b60ca-110">The `Narrowing` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="b60ca-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="b60ca-111">Operator Statement</span></span>](../statements/operator-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="b60ca-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b60ca-112">See also</span></span>

- [<span data-ttu-id="b60ca-113">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="b60ca-113">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="b60ca-114">Widening</span><span class="sxs-lookup"><span data-stu-id="b60ca-114">Widening</span></span>](widening.md)
- [<span data-ttu-id="b60ca-115">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="b60ca-115">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="b60ca-116">Procedimiento para definir un operador</span><span class="sxs-lookup"><span data-stu-id="b60ca-116">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="b60ca-117">CType Function</span><span class="sxs-lookup"><span data-stu-id="b60ca-117">CType Function</span></span>](../functions/ctype-function.md)
- [<span data-ttu-id="b60ca-118">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b60ca-118">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
