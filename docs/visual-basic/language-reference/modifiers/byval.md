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
ms.openlocfilehash: 5e534eac2300327d4c54c5ce93d8b2c6c538e794
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801671"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="2ae3e-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ae3e-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="2ae3e-103">Especifica que un argumento se pasa de manera que la propiedad o procedimiento llamado no puede cambiar el valor de una variable subyacente del argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="2ae3e-103">Specifies that an argument is passed in such a way that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ae3e-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2ae3e-104">Remarks</span></span>  
 <span data-ttu-id="2ae3e-105">El modificador `ByVal` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2ae3e-105">The `ByVal` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="2ae3e-106">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2ae3e-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="2ae3e-107">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2ae3e-107">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="2ae3e-108">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2ae3e-108">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="2ae3e-109">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2ae3e-109">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="2ae3e-110">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2ae3e-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a><span data-ttu-id="2ae3e-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2ae3e-111">Example</span></span>  
 <span data-ttu-id="2ae3e-112">En el ejemplo siguiente se muestra el uso de la `ByVal` mecanismo con un argumento de tipo de referencia que pasa los parámetros.</span><span class="sxs-lookup"><span data-stu-id="2ae3e-112">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="2ae3e-113">En el ejemplo, el argumento es `c1`, una instancia de clase `Class1`.</span><span class="sxs-lookup"><span data-stu-id="2ae3e-113">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="2ae3e-114">`ByVal` impide que el código en los procedimientos de cambiar el valor subyacente del argumento de referencia, `c1`, pero no protege los campos accesibles y propiedades de `c1`.</span><span class="sxs-lookup"><span data-stu-id="2ae3e-114">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="2ae3e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ae3e-115">See also</span></span>

- [<span data-ttu-id="2ae3e-116">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2ae3e-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="2ae3e-117">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="2ae3e-117">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
