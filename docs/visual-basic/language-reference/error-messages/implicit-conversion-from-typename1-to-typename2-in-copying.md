---
title: Conversión implícita de '<typename1>' a '<typename2>' al copiar de nuevo el valor del parámetro 'ByRef' '<parametername>' en el argumento correspondiente
ms.date: 07/20/2015
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
ms.openlocfilehash: fced95fe24d42d4af2118706bcaf3337429fea91
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873988"
---
# <a name="implicit-conversion-from-typename1-to-typename2-in-copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument"></a><span data-ttu-id="ad96c-102">Conversión implícita de '\<typename1>' a '\<typename2>' al copiar de nuevo el valor del parámetro 'ByRef' '\<parametername>' en el argumento correspondiente</span><span class="sxs-lookup"><span data-stu-id="ad96c-102">Implicit conversion from '\<typename1>' to '\<typename2>' in copying the value of 'ByRef' parameter '\<parametername>' back to the matching argument.</span></span>

<span data-ttu-id="ad96c-103">Se llama a un procedimiento con un argumento [ByRef](../modifiers/byref.md) de un tipo diferente al de su parámetro correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ad96c-103">A procedure is called with a [ByRef](../modifiers/byref.md) argument of a different type than that of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="ad96c-104">Si se pasa un argumento `ByRef` , Visual Basic a veces copia el valor del argumento en una variable local en el procedimiento en lugar de pasar una referencia.</span><span class="sxs-lookup"><span data-stu-id="ad96c-104">If you pass an argument `ByRef`, Visual Basic sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="ad96c-105">En tal caso, cuando el procedimiento vuelve, Visual Basic debe copiar de nuevo el valor de la variable local en el argumento del código de llamada.</span><span class="sxs-lookup"><span data-stu-id="ad96c-105">In such a case, when the procedure returns, Visual Basic must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="ad96c-106">Si un valor de argumento `ByRef` se copia en el procedimiento y el argumento y el parámetro son del mismo tipo, no es necesario realizar ninguna conversión.</span><span class="sxs-lookup"><span data-stu-id="ad96c-106">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="ad96c-107">Pero si los tipos son diferentes, Visual Basic debe convertir en ambas direcciones.</span><span class="sxs-lookup"><span data-stu-id="ad96c-107">But if the types are different, Visual Basic must convert in both directions.</span></span> <span data-ttu-id="ad96c-108">Dado que no se puede usar `CType` ni ninguna de las otras palabras clave de conversión en un argumento de procedimiento o parámetro, esta conversión siempre es implícita.</span><span class="sxs-lookup"><span data-stu-id="ad96c-108">Because you cannot use `CType` or any of the other conversion keywords on a procedure argument or parameter, such a conversion is always implicit.</span></span>  
  
 <span data-ttu-id="ad96c-109">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="ad96c-109">By default, this message is a warning.</span></span> <span data-ttu-id="ad96c-110">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="ad96c-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="ad96c-111">**Identificador de error:** BC41999</span><span class="sxs-lookup"><span data-stu-id="ad96c-111">**Error ID:** BC41999</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ad96c-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ad96c-112">To correct this error</span></span>  
  
- <span data-ttu-id="ad96c-113">Si es posible, use un argumento de llamada del mismo tipo que el parámetro de procedimiento, por lo que Visual Basic no necesita realizar ninguna conversión.</span><span class="sxs-lookup"><span data-stu-id="ad96c-113">If possible, use a calling argument of the same type as the procedure parameter, so Visual Basic does not need to do any conversion.</span></span>  
  
- <span data-ttu-id="ad96c-114">Si necesita llamar al procedimiento con un argumento de tipo diferente del tipo de parámetro pero no es necesario devolver un valor al argumento de llamada, defina el parámetro para que sea [ByVal](../modifiers/byval.md) en lugar de `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="ad96c-114">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../modifiers/byval.md) instead of `ByRef`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad96c-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ad96c-115">See also</span></span>

- [<span data-ttu-id="ad96c-116">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="ad96c-116">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="ad96c-117">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="ad96c-117">Procedure Parameters and Arguments</span></span>](../../programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="ad96c-118">Pasar argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="ad96c-118">Passing Arguments by Value and by Reference</span></span>](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="ad96c-119">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="ad96c-119">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
