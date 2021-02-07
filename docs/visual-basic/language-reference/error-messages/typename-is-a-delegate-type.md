---
description: "Más información acerca de: BC32008: ' <typename> ' es un tipo delegado"
title: "'<typename>' es un tipo delegado"
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 72aac48038c433b7938c54e7f1138a5b91bf7689
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99675031"
---
# <a name="bc32008-typename-is-a-delegate-type"></a><span data-ttu-id="ef747-103">BC32008: ' \<typename> ' es un tipo delegado</span><span class="sxs-lookup"><span data-stu-id="ef747-103">BC32008: '\<typename>' is a delegate type</span></span>

<span data-ttu-id="ef747-104">' \<typename> ' es un tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="ef747-104">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="ef747-105">La construcción de delegado solo permite una expresión AddressOf como una lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="ef747-105">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="ef747-106">A menudo se puede usar una expresión AddressOf en lugar de una construcción de delegado.</span><span class="sxs-lookup"><span data-stu-id="ef747-106">Often an AddressOf expression can be used instead of a delegate construction.</span></span>

 <span data-ttu-id="ef747-107">Una `New` cláusula que crea una instancia de una clase delegada proporciona una lista de argumentos no válidos al constructor delegado.</span><span class="sxs-lookup"><span data-stu-id="ef747-107">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>

 <span data-ttu-id="ef747-108">Solo se puede proporcionar una `AddressOf` expresión cuando se crea una nueva instancia de delegado.</span><span class="sxs-lookup"><span data-stu-id="ef747-108">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>

 <span data-ttu-id="ef747-109">Este error puede producirse si no se pasan argumentos al constructor delegado, si se pasa más de un argumento, o si se pasa un solo argumento que no es una `AddressOf` expresión válida.</span><span class="sxs-lookup"><span data-stu-id="ef747-109">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>

 <span data-ttu-id="ef747-110">**Identificador de error:** BC32008</span><span class="sxs-lookup"><span data-stu-id="ef747-110">**Error ID:** BC32008</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="ef747-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ef747-111">To correct this error</span></span>

- <span data-ttu-id="ef747-112">Use una sola `AddressOf` expresión en la lista de argumentos para la clase Delegate en la `New` cláusula.</span><span class="sxs-lookup"><span data-stu-id="ef747-112">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef747-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef747-113">See also</span></span>

- [<span data-ttu-id="ef747-114">New Operator (Nuevo operador)</span><span class="sxs-lookup"><span data-stu-id="ef747-114">New Operator</span></span>](../operators/new-operator.md)
- [<span data-ttu-id="ef747-115">Operador AddressOf</span><span class="sxs-lookup"><span data-stu-id="ef747-115">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="ef747-116">Delegados</span><span class="sxs-lookup"><span data-stu-id="ef747-116">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="ef747-117">Procedimiento para invocar un método delegado</span><span class="sxs-lookup"><span data-stu-id="ef747-117">How to: Invoke a Delegate Method</span></span>](../../programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
