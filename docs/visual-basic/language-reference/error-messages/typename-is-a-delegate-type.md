---
title: "'<typename>' es un tipo delegado"
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 4cc0a1221dcf65aa2a16fd7d82568c8544f27fdb
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875081"
---
# <a name="typename-is-a-delegate-type"></a><span data-ttu-id="37f06-102">'\<typename>' es un tipo delegado</span><span class="sxs-lookup"><span data-stu-id="37f06-102">'\<typename>' is a delegate type</span></span>

<span data-ttu-id="37f06-103">' \<typename> ' es un tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="37f06-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="37f06-104">La construcción de delegado solo permite una expresión AddressOf como una lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="37f06-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="37f06-105">A menudo se puede usar una expresión AddressOf en lugar de una construcción de delegado.</span><span class="sxs-lookup"><span data-stu-id="37f06-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="37f06-106">Una `New` cláusula que crea una instancia de una clase delegada proporciona una lista de argumentos no válidos al constructor delegado.</span><span class="sxs-lookup"><span data-stu-id="37f06-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="37f06-107">Solo se puede proporcionar una `AddressOf` expresión cuando se crea una nueva instancia de delegado.</span><span class="sxs-lookup"><span data-stu-id="37f06-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="37f06-108">Este error puede producirse si no se pasan argumentos al constructor delegado, si se pasa más de un argumento, o si se pasa un solo argumento que no es una `AddressOf` expresión válida.</span><span class="sxs-lookup"><span data-stu-id="37f06-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="37f06-109">**Identificador de error:** BC32008</span><span class="sxs-lookup"><span data-stu-id="37f06-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="37f06-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="37f06-110">To correct this error</span></span>  
  
- <span data-ttu-id="37f06-111">Use una sola `AddressOf` expresión en la lista de argumentos para la clase Delegate en la `New` cláusula.</span><span class="sxs-lookup"><span data-stu-id="37f06-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37f06-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37f06-112">See also</span></span>

- [<span data-ttu-id="37f06-113">New (operador)</span><span class="sxs-lookup"><span data-stu-id="37f06-113">New Operator</span></span>](../operators/new-operator.md)
- [<span data-ttu-id="37f06-114">Operador AddressOf</span><span class="sxs-lookup"><span data-stu-id="37f06-114">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="37f06-115">Delegados</span><span class="sxs-lookup"><span data-stu-id="37f06-115">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="37f06-116">Procedimiento para invocar un método delegado</span><span class="sxs-lookup"><span data-stu-id="37f06-116">How to: Invoke a Delegate Method</span></span>](../../programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
