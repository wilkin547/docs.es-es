---
title: '&#39;&lt;TypeName&gt; &#39; es un tipo delegado'
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: c6d4244ce72dedee50b65ba19978149ce86b9e87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595653"
---
# <a name="39lttypenamegt39-is-a-delegate-type"></a><span data-ttu-id="9659d-102">&#39;&lt;TypeName&gt; &#39; es un tipo delegado</span><span class="sxs-lookup"><span data-stu-id="9659d-102">&#39;&lt;typename&gt;&#39; is a delegate type</span></span>
<span data-ttu-id="9659d-103">'\<typename >' es un tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="9659d-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="9659d-104">Construcción de delegado permite una única expresión AddressOf como una lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="9659d-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="9659d-105">A menudo se puede utilizar una expresión AddressOf en lugar de una construcción de delegado.</span><span class="sxs-lookup"><span data-stu-id="9659d-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="9659d-106">Un `New` cláusula que crea una instancia de una clase de delegado proporciona una lista de argumentos no válido al constructor de delegado.</span><span class="sxs-lookup"><span data-stu-id="9659d-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="9659d-107">Puede proporcionar un solo `AddressOf` expresión al crear una nueva instancia de delegado.</span><span class="sxs-lookup"><span data-stu-id="9659d-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="9659d-108">Este error puede producirse si no pasa ningún argumento al constructor de delegado, si se pasa más de un argumento, o si se pasa un argumento único que no es válido `AddressOf` expresión.</span><span class="sxs-lookup"><span data-stu-id="9659d-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="9659d-109">**Id. de error:** BC32008</span><span class="sxs-lookup"><span data-stu-id="9659d-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9659d-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="9659d-110">To correct this error</span></span>  
  
-   <span data-ttu-id="9659d-111">Usar un solo `AddressOf` expresión en la lista de argumentos para la clase de delegado en el `New` cláusula.</span><span class="sxs-lookup"><span data-stu-id="9659d-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9659d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9659d-112">See Also</span></span>  
 [<span data-ttu-id="9659d-113">New (operador)</span><span class="sxs-lookup"><span data-stu-id="9659d-113">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)  
 [<span data-ttu-id="9659d-114">AddressOf (operador)</span><span class="sxs-lookup"><span data-stu-id="9659d-114">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="9659d-115">Delegados</span><span class="sxs-lookup"><span data-stu-id="9659d-115">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="9659d-116">Invocar un método delegado</span><span class="sxs-lookup"><span data-stu-id="9659d-116">How to: Invoke a Delegate Method</span></span>](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
