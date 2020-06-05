---
title: Operador AddressOf
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 3e7db8e7329ce8d21b6e07863e6f1673a6389608
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372069"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="db9ea-102">AddressOf (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db9ea-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="db9ea-103">Crea una instancia de delegado que hace referencia al procedimiento específico.</span><span class="sxs-lookup"><span data-stu-id="db9ea-103">Creates a delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db9ea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db9ea-104">Syntax</span></span>  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="db9ea-105">Partes</span><span class="sxs-lookup"><span data-stu-id="db9ea-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="db9ea-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="db9ea-106">Required.</span></span> <span data-ttu-id="db9ea-107">Especifica el procedimiento al que debe hacer referencia el delegado recién creado.</span><span class="sxs-lookup"><span data-stu-id="db9ea-107">Specifies the procedure to be referenced by the newly created delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db9ea-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="db9ea-108">Remarks</span></span>  
 <span data-ttu-id="db9ea-109">El `AddressOf` operador crea un delegado que apunta a la función Sub o especificada por `procedurename` .</span><span class="sxs-lookup"><span data-stu-id="db9ea-109">The `AddressOf` operator creates a delegate that points to the sub or function specified by `procedurename`.</span></span> <span data-ttu-id="db9ea-110">Cuando el procedimiento especificado es un método de instancia, el delegado hace referencia tanto a la instancia como al método.</span><span class="sxs-lookup"><span data-stu-id="db9ea-110">When the specified procedure is an instance method then the delegate refers to both the instance and the method.</span></span> <span data-ttu-id="db9ea-111">A continuación, cuando se invoca al delegado, se llama al método especificado de la instancia especificada.</span><span class="sxs-lookup"><span data-stu-id="db9ea-111">Then, when the  delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="db9ea-112">El `AddressOf` operador se puede usar como operando de un constructor de delegado o en un contexto en el que el compilador puede determinar el tipo del delegado.</span><span class="sxs-lookup"><span data-stu-id="db9ea-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db9ea-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="db9ea-113">Example</span></span>  
 <span data-ttu-id="db9ea-114">En este ejemplo se usa el `AddressOf` operador para designar un delegado para controlar el `Click` evento de un botón.</span><span class="sxs-lookup"><span data-stu-id="db9ea-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="db9ea-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="db9ea-115">Example</span></span>  
 <span data-ttu-id="db9ea-116">En el ejemplo siguiente se usa el `AddressOf` operador para designar la función de inicio de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="db9ea-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="db9ea-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db9ea-117">See also</span></span>

- [<span data-ttu-id="db9ea-118">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="db9ea-118">Declare Statement</span></span>](../statements/declare-statement.md)
- [<span data-ttu-id="db9ea-119">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="db9ea-119">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="db9ea-120">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="db9ea-120">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="db9ea-121">Delegados</span><span class="sxs-lookup"><span data-stu-id="db9ea-121">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
