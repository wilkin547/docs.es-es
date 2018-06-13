---
title: Los parámetros genéricos utilizados como tipos de parámetros opcionales deben tener restricción de clase
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 7e2b59f758ef236717a912694576b514e2ae8a60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590044"
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a><span data-ttu-id="264fd-102">Los parámetros genéricos utilizados como tipos de parámetros opcionales deben tener restricción de clase</span><span class="sxs-lookup"><span data-stu-id="264fd-102">Generic parameters used as optional parameter types must be class constrained</span></span>
<span data-ttu-id="264fd-103">Se declara un procedimiento con un parámetro opcional que utiliza un parámetro de tipo que no está restringido a ser un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="264fd-103">A procedure is declared with an optional parameter that uses a type parameter that is not constrained to be a reference type.</span></span>  
  
 <span data-ttu-id="264fd-104">Siempre debe proporcionar un valor predeterminado para cada parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="264fd-104">You must always supply a default value for each optional parameter.</span></span> <span data-ttu-id="264fd-105">Si el parámetro es de un tipo de referencia, el valor opcional debe ser `Nothing`, que es un valor válido para cualquier tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="264fd-105">If the parameter is of a reference type, the optional value must be `Nothing`, which is a valid value for any reference type.</span></span> <span data-ttu-id="264fd-106">Sin embargo, si el parámetro es de un tipo de valor, ese tipo debe ser un tipo de datos básico predefinido por Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="264fd-106">However, if the parameter is of a value type, that type must be an elementary data type predefined by Visual Basic.</span></span> <span data-ttu-id="264fd-107">Esto es porque un tipo de valor compuesto, como una estructura definida por el usuario, no tiene ningún valor predeterminado válido.</span><span class="sxs-lookup"><span data-stu-id="264fd-107">This is because a composite value type, such as a user-defined structure, has no valid default value.</span></span>  
  
 <span data-ttu-id="264fd-108">Cuando se usa un parámetro de tipo para un parámetro opcional, debe garantizar que es de un tipo de referencia para evitar la posibilidad de un tipo de valor no tiene ningún valor predeterminado válido.</span><span class="sxs-lookup"><span data-stu-id="264fd-108">When you use a type parameter for an optional parameter, you must guarantee that it is of a reference type to avoid the possibility of a value type with no valid default value.</span></span> <span data-ttu-id="264fd-109">Esto significa que debe restringir el parámetro de tipo con el `Class` palabra clave o con el nombre de una clase específica.</span><span class="sxs-lookup"><span data-stu-id="264fd-109">This means you must constrain the type parameter either with the `Class` keyword or with the name of a specific class.</span></span>  
  
 <span data-ttu-id="264fd-110">**Id. de error:** BC32124</span><span class="sxs-lookup"><span data-stu-id="264fd-110">**Error ID:** BC32124</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="264fd-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="264fd-111">To correct this error</span></span>  
  
-   <span data-ttu-id="264fd-112">Restringir el parámetro de tipo para aceptar sólo un tipo de referencia o no lo use para el parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="264fd-112">Constrain the type parameter to accept only a reference type, or do not use it for the optional parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="264fd-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="264fd-113">See Also</span></span>  
 [<span data-ttu-id="264fd-114">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="264fd-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="264fd-115">Lista de tipos</span><span class="sxs-lookup"><span data-stu-id="264fd-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="264fd-116">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="264fd-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="264fd-117">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="264fd-117">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [<span data-ttu-id="264fd-118">Estructuras</span><span class="sxs-lookup"><span data-stu-id="264fd-118">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="264fd-119">Nothing</span><span class="sxs-lookup"><span data-stu-id="264fd-119">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
