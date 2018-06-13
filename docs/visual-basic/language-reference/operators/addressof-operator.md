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
ms.openlocfilehash: 7c229c32a3b295b4dbfe50ca2abc60d4ad5f2145
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597792"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="e5c1e-102">AddressOf (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5c1e-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="e5c1e-103">Crea una instancia de delegado de procedimiento que hace referencia el procedimiento específico.</span><span class="sxs-lookup"><span data-stu-id="e5c1e-103">Creates a procedure delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5c1e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5c1e-104">Syntax</span></span>  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="e5c1e-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="e5c1e-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="e5c1e-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="e5c1e-106">Required.</span></span> <span data-ttu-id="e5c1e-107">Especifica el procedimiento que hace referencia el delegado de procedimiento recién creado.</span><span class="sxs-lookup"><span data-stu-id="e5c1e-107">Specifies the procedure to be referenced by the newly created procedure delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5c1e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e5c1e-108">Remarks</span></span>  
 <span data-ttu-id="e5c1e-109">El `AddressOf` operador crea un delegado de función que apunta a la función especificada por `procedurename`.</span><span class="sxs-lookup"><span data-stu-id="e5c1e-109">The `AddressOf` operator creates a function delegate that points to the function specified by `procedurename`.</span></span> <span data-ttu-id="e5c1e-110">Cuando el procedimiento especificado es que un método de instancia, a continuación, el delegado de función hace referencia a la instancia y el método.</span><span class="sxs-lookup"><span data-stu-id="e5c1e-110">When the specified procedure is an instance method then the function delegate refers to both the instance and the method.</span></span> <span data-ttu-id="e5c1e-111">A continuación, cuando se invoca el delegado de función se llama al método especificado de la instancia especificada.</span><span class="sxs-lookup"><span data-stu-id="e5c1e-111">Then, when the function delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="e5c1e-112">El `AddressOf` operador puede utilizarse como operando de un constructor de delegado o se puede utilizar en un contexto en el que se puede determinar el tipo de delegado por el compilador.</span><span class="sxs-lookup"><span data-stu-id="e5c1e-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5c1e-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5c1e-113">Example</span></span>  
 <span data-ttu-id="e5c1e-114">Este ejemplo se utiliza la `AddressOf` operador para designar un delegado para controlar el `Click` eventos de un botón.</span><span class="sxs-lookup"><span data-stu-id="e5c1e-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="e5c1e-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5c1e-115">Example</span></span>  
 <span data-ttu-id="e5c1e-116">En el ejemplo siguiente se usa el `AddressOf` operador para designar la función de inicio para un subproceso.</span><span class="sxs-lookup"><span data-stu-id="e5c1e-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e5c1e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5c1e-117">See Also</span></span>  
 [<span data-ttu-id="e5c1e-118">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e5c1e-118">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="e5c1e-119">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e5c1e-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="e5c1e-120">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e5c1e-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="e5c1e-121">Delegados</span><span class="sxs-lookup"><span data-stu-id="e5c1e-121">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
