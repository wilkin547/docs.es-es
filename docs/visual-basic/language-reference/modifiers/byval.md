---
title: ByVal (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c192cdb4ac43ad614fbfb663079c03ddc6c358c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="byval-visual-basic"></a><span data-ttu-id="e4a3e-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4a3e-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="e4a3e-103">Especifica que un argumento se pasa de tal manera que el procedimiento que se llama o la propiedad no se puede cambiar el valor de una variable subyacente del argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="e4a3e-103">Specifies that an argument is passed in such a way that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4a3e-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4a3e-104">Remarks</span></span>  
 <span data-ttu-id="e4a3e-105">El modificador `ByVal` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e4a3e-105">The `ByVal` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="e4a3e-106">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e4a3e-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="e4a3e-107">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e4a3e-107">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="e4a3e-108">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e4a3e-108">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="e4a3e-109">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e4a3e-109">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="e4a3e-110">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e4a3e-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a><span data-ttu-id="e4a3e-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e4a3e-111">Example</span></span>  
 <span data-ttu-id="e4a3e-112">En el ejemplo siguiente se muestra el uso de la `ByVal` mecanismo con un argumento de tipo de referencia que pasa el parámetro.</span><span class="sxs-lookup"><span data-stu-id="e4a3e-112">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="e4a3e-113">En el ejemplo, el argumento es `c1`, una instancia de clase `Class1`.</span><span class="sxs-lookup"><span data-stu-id="e4a3e-113">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="e4a3e-114">`ByVal`impide que el código en los procedimientos cambie el valor subyacente del argumento de referencia, `c1`, pero no protege los campos accesibles y las propiedades de `c1`.</span><span class="sxs-lookup"><span data-stu-id="e4a3e-114">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#10](../../../visual-basic/language-reference/codesnippet/VisualBasic/byval_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e4a3e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4a3e-115">See Also</span></span>  
 [<span data-ttu-id="e4a3e-116">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="e4a3e-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="e4a3e-117">Paso de argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="e4a3e-117">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
