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
ms.openlocfilehash: 8daf6600f59cea343e0d02b99632b92ce4bf3183
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875472"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="0ca23-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ca23-102">ByVal (Visual Basic)</span></span>

<span data-ttu-id="0ca23-103">Especifica que un argumento se pasa [por valor](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), de modo que el procedimiento o la propiedad a los que se ha llamado no pueden cambiar el valor de una variable subyacente del argumento en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="0ca23-103">Specifies that an argument is passed [by value](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), so that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span> <span data-ttu-id="0ca23-104">Si no se especifica ningún modificador, ByVal es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0ca23-104">If no modifier is specified, ByVal is the default.</span></span>

> [!NOTE]
> <span data-ttu-id="0ca23-105">Dado que es el valor predeterminado, no es necesario especificar explícitamente la `ByVal` palabra clave en las firmas de método.</span><span class="sxs-lookup"><span data-stu-id="0ca23-105">Because it is the default, you do not have to explicitly specify the `ByVal` keyword in method signatures.</span></span> <span data-ttu-id="0ca23-106">Tiende a generar código ruidoso y a menudo conduce a que la `ByRef` palabra clave no predeterminada se desechara.</span><span class="sxs-lookup"><span data-stu-id="0ca23-106">It tends to produce noisy code and often leads to the non-default `ByRef` keyword being overlooked.</span></span>

## <a name="remarks"></a><span data-ttu-id="0ca23-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0ca23-107">Remarks</span></span>

 <span data-ttu-id="0ca23-108">El modificador `ByVal` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0ca23-108">The `ByVal` modifier can be used in these contexts:</span></span>

 [<span data-ttu-id="0ca23-109">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="0ca23-109">Declare Statement</span></span>](../statements/declare-statement.md)

 [<span data-ttu-id="0ca23-110">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="0ca23-110">Function Statement</span></span>](../statements/function-statement.md)
  
 [<span data-ttu-id="0ca23-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="0ca23-111">Operator Statement</span></span>](../statements/operator-statement.md)
  
 [<span data-ttu-id="0ca23-112">Property Statement</span><span class="sxs-lookup"><span data-stu-id="0ca23-112">Property Statement</span></span>](../statements/property-statement.md)
  
 [<span data-ttu-id="0ca23-113">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="0ca23-113">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="example"></a><span data-ttu-id="0ca23-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ca23-114">Example</span></span>

 <span data-ttu-id="0ca23-115">En el ejemplo siguiente se muestra el uso del `ByVal` mecanismo de paso de parámetros con un argumento de tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="0ca23-115">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="0ca23-116">En el ejemplo, el argumento es `c1` , una instancia de clase `Class1` .</span><span class="sxs-lookup"><span data-stu-id="0ca23-116">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="0ca23-117">`ByVal` evita que el código de los procedimientos cambie el valor subyacente del argumento de referencia, `c1` , pero no protege los campos y propiedades accesibles de `c1` .</span><span class="sxs-lookup"><span data-stu-id="0ca23-117">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a><span data-ttu-id="0ca23-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ca23-118">See also</span></span>

- [<span data-ttu-id="0ca23-119">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0ca23-119">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="0ca23-120">Pasar argumentos por valor y por referencia</span><span class="sxs-lookup"><span data-stu-id="0ca23-120">Passing Arguments by Value and by Reference</span></span>](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
