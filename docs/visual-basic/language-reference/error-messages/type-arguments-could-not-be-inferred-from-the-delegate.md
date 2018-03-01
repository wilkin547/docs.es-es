---
title: No se pudieron inferir los argumentos de tipo a partir del delegado
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords:
- BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 57a3a24af32d9eb85a0f905aa3a73a956723b6d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="type-arguments-could-not-be-inferred-from-the-delegate"></a><span data-ttu-id="0d18e-102">No se pudieron inferir los argumentos de tipo a partir del delegado</span><span class="sxs-lookup"><span data-stu-id="0d18e-102">Type arguments could not be inferred from the delegate</span></span>
<span data-ttu-id="0d18e-103">Una instrucción de asignación usa `AddressOf` para asignar la dirección de un procedimiento genérico a un delegado, pero no proporciona ningún argumento de tipo al procedimiento genérico.</span><span class="sxs-lookup"><span data-stu-id="0d18e-103">An assignment statement uses `AddressOf` to assign the address of a generic procedure to a delegate, but it does not supply any type arguments to the generic procedure.</span></span>  
  
 <span data-ttu-id="0d18e-104">Normalmente, cuando se invoca un tipo genérico, se facilita un argumento de tipo para cada parámetro de tipo definido por el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="0d18e-104">Normally, when you invoke a generic type, you supply a type argument for each type parameter that the generic type defines.</span></span> <span data-ttu-id="0d18e-105">Si no se facilita ningún argumento de tipo, el compilador intenta inferir los tipos que se deben pasar a los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="0d18e-105">If you do not supply any type arguments, the compiler attempts to infer the types to be passed to the type parameters.</span></span> <span data-ttu-id="0d18e-106">Si el contexto no proporciona suficiente información para que el compilador infiera los tipos, se genera un error.</span><span class="sxs-lookup"><span data-stu-id="0d18e-106">If the context does not provide enough information for the compiler to infer the types, an error is generated.</span></span>  
  
 <span data-ttu-id="0d18e-107">**Id. de error:** BC36564</span><span class="sxs-lookup"><span data-stu-id="0d18e-107">**Error ID:** BC36564</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0d18e-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="0d18e-108">To correct this error</span></span>  
  
-   <span data-ttu-id="0d18e-109">Especifique los argumentos de tipo para el procedimiento genérico en la expresión `AddressOf` .</span><span class="sxs-lookup"><span data-stu-id="0d18e-109">Specify the type arguments for the generic procedure in the `AddressOf` expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d18e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d18e-110">See Also</span></span>  
 [<span data-ttu-id="0d18e-111">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0d18e-111">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="0d18e-112">AddressOf (operador)</span><span class="sxs-lookup"><span data-stu-id="0d18e-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="0d18e-113">Procedimientos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0d18e-113">Generic Procedures in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)  
 [<span data-ttu-id="0d18e-114">Lista de tipos</span><span class="sxs-lookup"><span data-stu-id="0d18e-114">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="0d18e-115">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="0d18e-115">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
