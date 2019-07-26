---
title: ByVal (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: abfe1489cb7e0d06b03c308e0704ce6f69ee55da
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433800"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="ef604-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef604-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="ef604-103">Especifica que un argumento se pasa [por valor](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), de modo que el procedimiento o la propiedad a los que se ha llamado no pueden cambiar el valor de una variable subyacente del argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="ef604-103">Specifies that an argument is passed [by value](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), so that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span> <span data-ttu-id="ef604-104">Si no se especifica ningún modificador, ByVal es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ef604-104">If no modifier is specified, ByVal is the default.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ef604-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ef604-105">Remarks</span></span>  
 <span data-ttu-id="ef604-106">El modificador `ByVal` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ef604-106">The `ByVal` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="ef604-107">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ef604-107">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="ef604-108">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ef604-108">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="ef604-109">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ef604-109">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="ef604-110">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ef604-110">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="ef604-111">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ef604-111">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a><span data-ttu-id="ef604-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef604-112">Example</span></span>  
 <span data-ttu-id="ef604-113">En el ejemplo siguiente se muestra el uso `ByVal` del mecanismo de paso de parámetros con un argumento de tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="ef604-113">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="ef604-114">En el ejemplo, el argumento es `c1`, una instancia de clase `Class1`.</span><span class="sxs-lookup"><span data-stu-id="ef604-114">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="ef604-115">`ByVal`evita que el código de los procedimientos cambie el valor subyacente del argumento de referencia, `c1`, pero no protege los campos y propiedades accesibles de. `c1`</span><span class="sxs-lookup"><span data-stu-id="ef604-115">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="ef604-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef604-116">See also</span></span>

- [<span data-ttu-id="ef604-117">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="ef604-117">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="ef604-118">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="ef604-118">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
