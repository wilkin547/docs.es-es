---
title: "'<typename>' es un tipo delegado"
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 45dc0403468fa40888a6c5e6bdfe6ca782e98325
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664191"
---
# <a name="typename-is-a-delegate-type"></a><span data-ttu-id="238c3-102">'\<typename >' es un tipo delegado</span><span class="sxs-lookup"><span data-stu-id="238c3-102">'\<typename>' is a delegate type</span></span>
<span data-ttu-id="238c3-103">'\<typename >' es un tipo delegado.</span><span class="sxs-lookup"><span data-stu-id="238c3-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="238c3-104">Construcción de delegado permite una única expresión AddressOf como una lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="238c3-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="238c3-105">A menudo se puede usar una expresión de AddressOf en lugar de una construcción de delegado.</span><span class="sxs-lookup"><span data-stu-id="238c3-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="238c3-106">Un `New` cláusula crea una instancia de una clase de delegado proporciona una lista de argumentos no válido al constructor de delegado.</span><span class="sxs-lookup"><span data-stu-id="238c3-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="238c3-107">Puede proporcionar una sola `AddressOf` expresión al crear una nueva instancia de delegado.</span><span class="sxs-lookup"><span data-stu-id="238c3-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="238c3-108">Este error puede producirse si no pasa ningún argumento al constructor de delegado, si se pasa más de un argumento, o si se pasa un único argumento que no es válido `AddressOf` expresión.</span><span class="sxs-lookup"><span data-stu-id="238c3-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="238c3-109">**Identificador de error:** BC32008</span><span class="sxs-lookup"><span data-stu-id="238c3-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="238c3-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="238c3-110">To correct this error</span></span>  
  
- <span data-ttu-id="238c3-111">Usar una sola `AddressOf` expresión en la lista de argumentos para la clase de delegado en el `New` cláusula.</span><span class="sxs-lookup"><span data-stu-id="238c3-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="238c3-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="238c3-112">See also</span></span>

- [<span data-ttu-id="238c3-113">New (operador)</span><span class="sxs-lookup"><span data-stu-id="238c3-113">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="238c3-114">AddressOf (operador)</span><span class="sxs-lookup"><span data-stu-id="238c3-114">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="238c3-115">Delegados</span><span class="sxs-lookup"><span data-stu-id="238c3-115">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="238c3-116">Cómo: Invocar un método delegado</span><span class="sxs-lookup"><span data-stu-id="238c3-116">How to: Invoke a Delegate Method</span></span>](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
