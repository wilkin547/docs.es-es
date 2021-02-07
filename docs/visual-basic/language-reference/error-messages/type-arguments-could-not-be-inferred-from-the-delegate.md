---
description: 'Más información sobre: BC36564: no se pudieron inferir los argumentos de tipo del delegado'
title: No se pudieron inferir los argumentos de tipo a partir del delegado
ms.date: 07/20/2015
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords:
- BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
ms.openlocfilehash: 1a83ee64df4523cee87d0d677ddafaeadfe5543d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666269"
---
# <a name="bc36564-type-arguments-could-not-be-inferred-from-the-delegate"></a><span data-ttu-id="5a703-103">BC36564: no se pudieron inferir los argumentos de tipo del delegado</span><span class="sxs-lookup"><span data-stu-id="5a703-103">BC36564: Type arguments could not be inferred from the delegate</span></span>

<span data-ttu-id="5a703-104">Una instrucción de asignación usa `AddressOf` para asignar la dirección de un procedimiento genérico a un delegado, pero no proporciona ningún argumento de tipo al procedimiento genérico.</span><span class="sxs-lookup"><span data-stu-id="5a703-104">An assignment statement uses `AddressOf` to assign the address of a generic procedure to a delegate, but it does not supply any type arguments to the generic procedure.</span></span>

 <span data-ttu-id="5a703-105">Normalmente, cuando se invoca un tipo genérico, se facilita un argumento de tipo para cada parámetro de tipo que define el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="5a703-105">Normally, when you invoke a generic type, you supply a type argument for each type parameter that the generic type defines.</span></span> <span data-ttu-id="5a703-106">Si no se facilita ningún argumento de tipo, el compilador intenta inferir los tipos que se deben pasar a los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="5a703-106">If you do not supply any type arguments, the compiler attempts to infer the types to be passed to the type parameters.</span></span> <span data-ttu-id="5a703-107">Si el contexto no proporciona suficiente información para que el compilador infiera los tipos, se genera un error.</span><span class="sxs-lookup"><span data-stu-id="5a703-107">If the context does not provide enough information for the compiler to infer the types, an error is generated.</span></span>

 <span data-ttu-id="5a703-108">**Identificador de error:** BC36564</span><span class="sxs-lookup"><span data-stu-id="5a703-108">**Error ID:** BC36564</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="5a703-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="5a703-109">To correct this error</span></span>

- <span data-ttu-id="5a703-110">Especifique los argumentos de tipo para el procedimiento genérico en la expresión `AddressOf` .</span><span class="sxs-lookup"><span data-stu-id="5a703-110">Specify the type arguments for the generic procedure in the `AddressOf` expression.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a703-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a703-111">See also</span></span>

- [<span data-ttu-id="5a703-112">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5a703-112">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="5a703-113">Operador AddressOf</span><span class="sxs-lookup"><span data-stu-id="5a703-113">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="5a703-114">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5a703-114">Generic Procedures in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-procedures.md)
- [<span data-ttu-id="5a703-115">Type List</span><span class="sxs-lookup"><span data-stu-id="5a703-115">Type List</span></span>](../statements/type-list.md)
- [<span data-ttu-id="5a703-116">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="5a703-116">Extension Methods</span></span>](../../programming-guide/language-features/procedures/extension-methods.md)
