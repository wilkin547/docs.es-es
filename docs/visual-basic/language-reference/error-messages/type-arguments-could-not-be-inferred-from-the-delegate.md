---
title: No se pudieron inferir los argumentos de tipo a partir del delegado
ms.date: 07/20/2015
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords:
- BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
ms.openlocfilehash: 757483f1e88276dd9db82de1c2a7e47b5c975b0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598246"
---
# <a name="type-arguments-could-not-be-inferred-from-the-delegate"></a><span data-ttu-id="7fa4a-102">No se pudieron inferir los argumentos de tipo a partir del delegado</span><span class="sxs-lookup"><span data-stu-id="7fa4a-102">Type arguments could not be inferred from the delegate</span></span>
<span data-ttu-id="7fa4a-103">Una instrucción de asignación usa `AddressOf` para asignar la dirección de un procedimiento genérico a un delegado, pero no proporciona ningún argumento de tipo al procedimiento genérico.</span><span class="sxs-lookup"><span data-stu-id="7fa4a-103">An assignment statement uses `AddressOf` to assign the address of a generic procedure to a delegate, but it does not supply any type arguments to the generic procedure.</span></span>  
  
 <span data-ttu-id="7fa4a-104">Normalmente, cuando se invoca un tipo genérico, se facilita un argumento de tipo para cada parámetro de tipo definido por el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="7fa4a-104">Normally, when you invoke a generic type, you supply a type argument for each type parameter that the generic type defines.</span></span> <span data-ttu-id="7fa4a-105">Si no se facilita ningún argumento de tipo, el compilador intenta inferir los tipos que se deben pasar a los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="7fa4a-105">If you do not supply any type arguments, the compiler attempts to infer the types to be passed to the type parameters.</span></span> <span data-ttu-id="7fa4a-106">Si el contexto no proporciona suficiente información para que el compilador infiera los tipos, se genera un error.</span><span class="sxs-lookup"><span data-stu-id="7fa4a-106">If the context does not provide enough information for the compiler to infer the types, an error is generated.</span></span>  
  
 <span data-ttu-id="7fa4a-107">**Id. de error:** BC36564</span><span class="sxs-lookup"><span data-stu-id="7fa4a-107">**Error ID:** BC36564</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7fa4a-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="7fa4a-108">To correct this error</span></span>  
  
-   <span data-ttu-id="7fa4a-109">Especifique los argumentos de tipo para el procedimiento genérico en la expresión `AddressOf` .</span><span class="sxs-lookup"><span data-stu-id="7fa4a-109">Specify the type arguments for the generic procedure in the `AddressOf` expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fa4a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fa4a-110">See Also</span></span>  
 [<span data-ttu-id="7fa4a-111">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7fa4a-111">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="7fa4a-112">AddressOf (operador)</span><span class="sxs-lookup"><span data-stu-id="7fa4a-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="7fa4a-113">Procedimientos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7fa4a-113">Generic Procedures in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)  
 [<span data-ttu-id="7fa4a-114">Lista de tipos</span><span class="sxs-lookup"><span data-stu-id="7fa4a-114">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="7fa4a-115">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="7fa4a-115">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
