---
title: AddressOf (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 9d8515b6d5b0caf3552ed05a7e0cd4a271efaf54
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830349"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="9a468-102">AddressOf (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a468-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="9a468-103">Crea una instancia de delegado de procedimiento que hace referencia el procedimiento específico.</span><span class="sxs-lookup"><span data-stu-id="9a468-103">Creates a procedure delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a468-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a468-104">Syntax</span></span>  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="9a468-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="9a468-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="9a468-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="9a468-106">Required.</span></span> <span data-ttu-id="9a468-107">Especifica el procedimiento que hace referencia el delegado de procedimiento recién creado.</span><span class="sxs-lookup"><span data-stu-id="9a468-107">Specifies the procedure to be referenced by the newly created procedure delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a468-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9a468-108">Remarks</span></span>  
 <span data-ttu-id="9a468-109">El `AddressOf` operador crea un delegado de función que apunta a la función especificada por `procedurename`.</span><span class="sxs-lookup"><span data-stu-id="9a468-109">The `AddressOf` operator creates a function delegate that points to the function specified by `procedurename`.</span></span> <span data-ttu-id="9a468-110">Cuando el procedimiento especificado es que un método de instancia, a continuación, el delegado de función hace referencia a la instancia y el método.</span><span class="sxs-lookup"><span data-stu-id="9a468-110">When the specified procedure is an instance method then the function delegate refers to both the instance and the method.</span></span> <span data-ttu-id="9a468-111">A continuación, cuando se invoca el delegado de función se llama al método especificado de la instancia especificada.</span><span class="sxs-lookup"><span data-stu-id="9a468-111">Then, when the function delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="9a468-112">El `AddressOf` operador puede utilizarse como operando de un constructor de delegado o se puede usar en un contexto en el que se puede determinar el tipo del delegado por el compilador.</span><span class="sxs-lookup"><span data-stu-id="9a468-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a468-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9a468-113">Example</span></span>  
 <span data-ttu-id="9a468-114">Este ejemplo se usa el `AddressOf` operador para designar un delegado para controlar el `Click` eventos de un botón.</span><span class="sxs-lookup"><span data-stu-id="9a468-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="9a468-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9a468-115">Example</span></span>  
 <span data-ttu-id="9a468-116">En el ejemplo siguiente se usa el `AddressOf` operador para designar la función de inicio de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="9a468-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="9a468-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a468-117">See also</span></span>

- [<span data-ttu-id="9a468-118">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="9a468-118">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="9a468-119">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="9a468-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="9a468-120">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="9a468-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="9a468-121">Delegados</span><span class="sxs-lookup"><span data-stu-id="9a468-121">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
