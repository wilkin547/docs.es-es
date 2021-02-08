---
description: 'Más información acerca de: operador AddressOf (Visual Basic)'
title: Operador AddressOf
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 2aba8c26aa9581fe1070574b8c408e09bf063d1f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774387"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="df636-103">AddressOf (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df636-103">AddressOf Operator (Visual Basic)</span></span>

<span data-ttu-id="df636-104">Crea una instancia de delegado que hace referencia al procedimiento específico.</span><span class="sxs-lookup"><span data-stu-id="df636-104">Creates a delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df636-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df636-105">Syntax</span></span>  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="df636-106">Partes</span><span class="sxs-lookup"><span data-stu-id="df636-106">Parts</span></span>  

 `procedurename`  
 <span data-ttu-id="df636-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="df636-107">Required.</span></span> <span data-ttu-id="df636-108">Especifica el procedimiento al que debe hacer referencia el delegado recién creado.</span><span class="sxs-lookup"><span data-stu-id="df636-108">Specifies the procedure to be referenced by the newly created delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df636-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="df636-109">Remarks</span></span>  

 <span data-ttu-id="df636-110">El `AddressOf` operador crea un delegado que apunta a la función Sub o especificada por `procedurename` .</span><span class="sxs-lookup"><span data-stu-id="df636-110">The `AddressOf` operator creates a delegate that points to the sub or function specified by `procedurename`.</span></span> <span data-ttu-id="df636-111">Cuando el procedimiento especificado es un método de instancia, el delegado hace referencia tanto a la instancia como al método.</span><span class="sxs-lookup"><span data-stu-id="df636-111">When the specified procedure is an instance method then the delegate refers to both the instance and the method.</span></span> <span data-ttu-id="df636-112">A continuación, cuando se invoca al delegado, se llama al método especificado de la instancia especificada.</span><span class="sxs-lookup"><span data-stu-id="df636-112">Then, when the  delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="df636-113">El `AddressOf` operador se puede usar como operando de un constructor de delegado o en un contexto en el que el compilador puede determinar el tipo del delegado.</span><span class="sxs-lookup"><span data-stu-id="df636-113">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df636-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df636-114">Example</span></span>  

 <span data-ttu-id="df636-115">En este ejemplo se usa el `AddressOf` operador para designar un delegado para controlar el `Click` evento de un botón.</span><span class="sxs-lookup"><span data-stu-id="df636-115">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="df636-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df636-116">Example</span></span>  

 <span data-ttu-id="df636-117">En el ejemplo siguiente se usa el `AddressOf` operador para designar la función de inicio de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="df636-117">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="df636-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="df636-118">See also</span></span>

- [<span data-ttu-id="df636-119">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="df636-119">Declare Statement</span></span>](../statements/declare-statement.md)
- [<span data-ttu-id="df636-120">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="df636-120">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="df636-121">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="df636-121">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="df636-122">Delegados</span><span class="sxs-lookup"><span data-stu-id="df636-122">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
