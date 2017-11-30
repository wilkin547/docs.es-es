---
title: Narrowing (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 50116c6212e919d4b9b35fc933d80dee14bd4ecf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="narrowing-visual-basic"></a><span data-ttu-id="57747-102">Narrowing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57747-102">Narrowing (Visual Basic)</span></span>
<span data-ttu-id="57747-103">Indica que un operador de conversión (`CType`) convierte una clase o estructura a un tipo que no pueda mantener algunos de los valores posibles de la clase o estructura original.</span><span class="sxs-lookup"><span data-stu-id="57747-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that might not be able to hold some of the possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-narrowing-keyword"></a><span data-ttu-id="57747-104">Convertir con la palabra clave Narrowing</span><span class="sxs-lookup"><span data-stu-id="57747-104">Converting with the Narrowing Keyword</span></span>  
 <span data-ttu-id="57747-105">El procedimiento de conversión debe especificar `Public Shared` además `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="57747-105">The conversion procedure must specify `Public Shared` in addition to `Narrowing`.</span></span>  
  
 <span data-ttu-id="57747-106">Conversiones de restricción no siempre sea correcta en tiempo de ejecución y pueden producir errores o provocar la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="57747-106">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="57747-107">Algunos ejemplos son `Long` a `Integer`, `String` a `Date`y un tipo base para un tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="57747-107">Examples are `Long` to `Integer`, `String` to `Date`, and a base type to a derived type.</span></span> <span data-ttu-id="57747-108">Esta última conversión es de restricción porque el tipo base no puede contener a todos los miembros del tipo derivado y, por tanto, no es una instancia del tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="57747-108">This last conversion is narrowing because the base type might not contain all the members of the derived type and thus is not an instance of the derived type.</span></span>  
  
 <span data-ttu-id="57747-109">Si `Option Strict` es `On`, el código usado debe usar `CType` para todas las conversiones de restricción.</span><span class="sxs-lookup"><span data-stu-id="57747-109">If `Option Strict` is `On`, the consuming code must use `CType` for all narrowing conversions.</span></span>  
  
 <span data-ttu-id="57747-110">El `Narrowing` palabra clave se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="57747-110">The `Narrowing` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="57747-111">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="57747-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="57747-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="57747-112">See Also</span></span>  
 [<span data-ttu-id="57747-113">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="57747-113">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="57747-114">Widening</span><span class="sxs-lookup"><span data-stu-id="57747-114">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="57747-115">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="57747-115">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="57747-116">Definir un operador</span><span class="sxs-lookup"><span data-stu-id="57747-116">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="57747-117">Función CType</span><span class="sxs-lookup"><span data-stu-id="57747-117">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)  
 [<span data-ttu-id="57747-118">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="57747-118">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
