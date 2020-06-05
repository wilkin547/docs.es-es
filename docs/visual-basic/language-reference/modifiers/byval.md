---
title: ByVal
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: c4cdafafa6bae3246c0512e28f94fde7e88d230b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373029"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="474f0-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="474f0-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="474f0-103">Especifica que un argumento se pasa [por valor](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), de modo que el procedimiento o la propiedad a los que se ha llamado no pueden cambiar el valor de una variable subyacente del argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="474f0-103">Specifies that an argument is passed [by value](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), so that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span> <span data-ttu-id="474f0-104">Si no se especifica ningún modificador, ByVal es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="474f0-104">If no modifier is specified, ByVal is the default.</span></span>

> [!NOTE]
> <span data-ttu-id="474f0-105">Dado que es el valor predeterminado, no es necesario especificar explícitamente la `ByVal` palabra clave en las firmas de método.</span><span class="sxs-lookup"><span data-stu-id="474f0-105">Because it is the default, you do not have to explicitly specify the `ByVal` keyword in method signatures.</span></span> <span data-ttu-id="474f0-106">Tiende a generar código ruidoso y a menudo conduce a que la `ByRef` palabra clave no predeterminada se desechara.</span><span class="sxs-lookup"><span data-stu-id="474f0-106">It tends to produce noisy code and often leads to the non-default `ByRef` keyword being overlooked.</span></span>

## <a name="remarks"></a><span data-ttu-id="474f0-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="474f0-107">Remarks</span></span>
 <span data-ttu-id="474f0-108">El modificador `ByVal` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="474f0-108">The `ByVal` modifier can be used in these contexts:</span></span>

 [<span data-ttu-id="474f0-109">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="474f0-109">Declare Statement</span></span>](../statements/declare-statement.md)

 [<span data-ttu-id="474f0-110">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="474f0-110">Function Statement</span></span>](../statements/function-statement.md)
  
 [<span data-ttu-id="474f0-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="474f0-111">Operator Statement</span></span>](../statements/operator-statement.md)
  
 [<span data-ttu-id="474f0-112">Property Statement</span><span class="sxs-lookup"><span data-stu-id="474f0-112">Property Statement</span></span>](../statements/property-statement.md)
  
 [<span data-ttu-id="474f0-113">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="474f0-113">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="example"></a><span data-ttu-id="474f0-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="474f0-114">Example</span></span>
 <span data-ttu-id="474f0-115">En el ejemplo siguiente se muestra el uso del `ByVal` mecanismo de paso de parámetros con un argumento de tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="474f0-115">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="474f0-116">En el ejemplo, el argumento es `c1` , una instancia de clase `Class1` .</span><span class="sxs-lookup"><span data-stu-id="474f0-116">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="474f0-117">`ByVal`evita que el código de los procedimientos cambie el valor subyacente del argumento de referencia, `c1` , pero no protege los campos y propiedades accesibles de `c1` .</span><span class="sxs-lookup"><span data-stu-id="474f0-117">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a><span data-ttu-id="474f0-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="474f0-118">See also</span></span>

- [<span data-ttu-id="474f0-119">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="474f0-119">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="474f0-120">Pasar argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="474f0-120">Passing Arguments by Value and by Reference</span></span>](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
