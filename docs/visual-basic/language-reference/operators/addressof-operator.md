---
title: AddressOf (Operador)
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: e88520bd7e731a35b98c1d40c5210dc5d1314911
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350281"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="db821-102">AddressOf (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db821-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="db821-103">Crea una instancia de delegado que hace referencia al procedimiento específico.</span><span class="sxs-lookup"><span data-stu-id="db821-103">Creates a delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db821-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db821-104">Syntax</span></span>  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="db821-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="db821-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="db821-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="db821-106">Required.</span></span> <span data-ttu-id="db821-107">Especifica el procedimiento al que debe hacer referencia el delegado recién creado.</span><span class="sxs-lookup"><span data-stu-id="db821-107">Specifies the procedure to be referenced by the newly created delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db821-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db821-108">Remarks</span></span>  
 <span data-ttu-id="db821-109">El operador `AddressOf` crea un delegado que apunta a la función Sub o especificada por `procedurename`.</span><span class="sxs-lookup"><span data-stu-id="db821-109">The `AddressOf` operator creates a delegate that points to the sub or function specified by `procedurename`.</span></span> <span data-ttu-id="db821-110">Cuando el procedimiento especificado es un método de instancia, el delegado hace referencia tanto a la instancia como al método.</span><span class="sxs-lookup"><span data-stu-id="db821-110">When the specified procedure is an instance method then the delegate refers to both the instance and the method.</span></span> <span data-ttu-id="db821-111">A continuación, cuando se invoca al delegado, se llama al método especificado de la instancia especificada.</span><span class="sxs-lookup"><span data-stu-id="db821-111">Then, when the  delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="db821-112">El operador `AddressOf` se puede usar como operando de un constructor delegado o se puede usar en un contexto en el que el compilador puede determinar el tipo del delegado.</span><span class="sxs-lookup"><span data-stu-id="db821-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db821-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="db821-113">Example</span></span>  
 <span data-ttu-id="db821-114">En este ejemplo se usa el operador `AddressOf` para designar un delegado que controle el evento de `Click` de un botón.</span><span class="sxs-lookup"><span data-stu-id="db821-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="db821-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="db821-115">Example</span></span>  
 <span data-ttu-id="db821-116">En el ejemplo siguiente se usa el operador `AddressOf` para designar la función de inicio de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="db821-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="db821-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="db821-117">See also</span></span>

- [<span data-ttu-id="db821-118">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="db821-118">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="db821-119">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="db821-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="db821-120">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="db821-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="db821-121">Delegados</span><span class="sxs-lookup"><span data-stu-id="db821-121">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
