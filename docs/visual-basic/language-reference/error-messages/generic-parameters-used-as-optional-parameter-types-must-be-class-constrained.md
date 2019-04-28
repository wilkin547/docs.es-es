---
title: Los parámetros genéricos utilizados como tipos de parámetros opcionales deben tener restricción de clase
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 9b0293472f5eda74c2bf8fb215e15ae5cf8d8b98
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802336"
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a><span data-ttu-id="56abd-102">Los parámetros genéricos utilizados como tipos de parámetros opcionales deben tener restricción de clase</span><span class="sxs-lookup"><span data-stu-id="56abd-102">Generic parameters used as optional parameter types must be class constrained</span></span>
<span data-ttu-id="56abd-103">Se declara un procedimiento con un parámetro opcional que se utiliza un parámetro de tipo que no esté restringido a ser un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="56abd-103">A procedure is declared with an optional parameter that uses a type parameter that is not constrained to be a reference type.</span></span>  
  
 <span data-ttu-id="56abd-104">Siempre debe proporcionar un valor predeterminado para cada parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="56abd-104">You must always supply a default value for each optional parameter.</span></span> <span data-ttu-id="56abd-105">Si el parámetro es de un tipo de referencia, el valor opcional debe ser `Nothing`, que es un valor válido para cualquier tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="56abd-105">If the parameter is of a reference type, the optional value must be `Nothing`, which is a valid value for any reference type.</span></span> <span data-ttu-id="56abd-106">Sin embargo, si el parámetro es de un tipo de valor, ese tipo debe ser un tipo de datos básico predefinido por Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="56abd-106">However, if the parameter is of a value type, that type must be an elementary data type predefined by Visual Basic.</span></span> <span data-ttu-id="56abd-107">Esto es porque un tipo de valor compuesto, como una estructura definida por el usuario, no tiene ningún valor predeterminado válido.</span><span class="sxs-lookup"><span data-stu-id="56abd-107">This is because a composite value type, such as a user-defined structure, has no valid default value.</span></span>  
  
 <span data-ttu-id="56abd-108">Cuando se usa un parámetro de tipo para un parámetro opcional, debe garantizar que es de un tipo de referencia para evitar la posibilidad de un tipo de valor no tiene ningún valor predeterminado válido.</span><span class="sxs-lookup"><span data-stu-id="56abd-108">When you use a type parameter for an optional parameter, you must guarantee that it is of a reference type to avoid the possibility of a value type with no valid default value.</span></span> <span data-ttu-id="56abd-109">Esto significa que debe restringir el parámetro de tipo con el `Class` palabra clave o con el nombre de una clase específica.</span><span class="sxs-lookup"><span data-stu-id="56abd-109">This means you must constrain the type parameter either with the `Class` keyword or with the name of a specific class.</span></span>  
  
 <span data-ttu-id="56abd-110">**Identificador de error:** BC32124</span><span class="sxs-lookup"><span data-stu-id="56abd-110">**Error ID:** BC32124</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="56abd-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="56abd-111">To correct this error</span></span>  
  
- <span data-ttu-id="56abd-112">Restringir el parámetro de tipo para aceptar sólo un tipo de referencia o no lo utilice para el parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="56abd-112">Constrain the type parameter to accept only a reference type, or do not use it for the optional parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56abd-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="56abd-113">See also</span></span>

- [<span data-ttu-id="56abd-114">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="56abd-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="56abd-115">Lista de tipos</span><span class="sxs-lookup"><span data-stu-id="56abd-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="56abd-116">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="56abd-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="56abd-117">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="56abd-117">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="56abd-118">Estructuras</span><span class="sxs-lookup"><span data-stu-id="56abd-118">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="56abd-119">Nothing</span><span class="sxs-lookup"><span data-stu-id="56abd-119">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
