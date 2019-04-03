---
title: El nombre de miembro de tipo anónimo sólo se puede inferir a partir de un nombre simple o completo sin argumentos
ms.date: 07/20/2015
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords:
- BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
ms.openlocfilehash: b798f296b62b51de34a7ec5ce5a8b608273f5748
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819234"
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="6ef97-102">El nombre de miembro de tipo anónimo sólo se puede inferir a partir de un nombre simple o completo sin argumentos</span><span class="sxs-lookup"><span data-stu-id="6ef97-102">Anonymous type member name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="6ef97-103">No se puede inferir un nombre de miembro de tipo anónimo en una expresión compleja.</span><span class="sxs-lookup"><span data-stu-id="6ef97-103">You cannot infer an anonymous type member name from a complex expression.</span></span>  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 <span data-ttu-id="6ef97-104">Para obtener más información acerca de los orígenes desde el que los tipos anónimos pueden y no pueden deducir tipos y nombres de miembro, vea [Cómo: Deducir tipos y nombres de propiedad en declaraciones de tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span><span class="sxs-lookup"><span data-stu-id="6ef97-104">For more information about sources from which anonymous types can and cannot infer member names and types, see [How to: Infer Property Names and Types in Anonymous Type Declarations](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span></span>  
  
 <span data-ttu-id="6ef97-105">**Identificador de error:** BC36556</span><span class="sxs-lookup"><span data-stu-id="6ef97-105">**Error ID:** BC36556</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6ef97-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="6ef97-106">To correct this error</span></span>  
  
-   <span data-ttu-id="6ef97-107">Asigne la expresión a un nombre de miembro, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ef97-107">Assign the expression to a member name, as shown in the following code:</span></span>  
  
    ```  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6ef97-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ef97-108">See also</span></span>

- [<span data-ttu-id="6ef97-109">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="6ef97-109">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="6ef97-110">Cómo: Deducir tipos y nombres de propiedad en declaraciones de tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="6ef97-110">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
