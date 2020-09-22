---
title: "'<expression>' no se puede utilizar como restricción de tipo"
ms.date: 07/20/2015
f1_keywords:
- bc32061
- vbc32061
helpviewer_keywords:
- BC32061
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
ms.openlocfilehash: 4f1db6bdbe6f25d0362b55acd95e716fbc2417ed
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874283"
---
# <a name="expression-cannot-be-used-as-a-type-constraint"></a><span data-ttu-id="cb8e8-102">'\<expression>' no se puede utilizar como restricción de tipo</span><span class="sxs-lookup"><span data-stu-id="cb8e8-102">'\<expression>' cannot be used as a type constraint</span></span>

<span data-ttu-id="cb8e8-103">Una lista de restricciones incluye una expresión que no representa una restricción válida en un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="cb8e8-103">A constraint list includes an expression that does not represent a valid constraint on a type parameter.</span></span>  
  
 <span data-ttu-id="cb8e8-104">Una lista de restricciones impone requisitos al argumento de tipo pasado al parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="cb8e8-104">A constraint list imposes requirements on the type argument passed to the type parameter.</span></span> <span data-ttu-id="cb8e8-105">Puede especificar los requisitos siguientes en cualquier combinación:</span><span class="sxs-lookup"><span data-stu-id="cb8e8-105">You can specify the following requirements in any combination:</span></span>  
  
- <span data-ttu-id="cb8e8-106">El argumento de tipo debe implementar una o varias interfaces</span><span class="sxs-lookup"><span data-stu-id="cb8e8-106">The type argument must implement one or more interfaces</span></span>  
  
- <span data-ttu-id="cb8e8-107">El argumento de tipo debe heredar de al menos una clase</span><span class="sxs-lookup"><span data-stu-id="cb8e8-107">The type argument must inherit from at most one class</span></span>  
  
- <span data-ttu-id="cb8e8-108">El argumento de tipo debe exponer un constructor sin parámetros al que el código de creación pueda acceder (incluya la restricción `New` ).</span><span class="sxs-lookup"><span data-stu-id="cb8e8-108">The type argument must expose a parameterless constructor that the creating code can access (include the `New` constraint)</span></span>  
  
 <span data-ttu-id="cb8e8-109">Si no incluye ninguna clase o interfaz específica en la lista de restricciones, puede imponer un requisito más general especificando uno de los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="cb8e8-109">If you do not include any specific class or interface in the constraint list, you can impose a more general requirement by specifying one of the following:</span></span>  
  
- <span data-ttu-id="cb8e8-110">El argumento de tipo debe ser un tipo de valor (incluya la restricción `Structure` ).</span><span class="sxs-lookup"><span data-stu-id="cb8e8-110">The type argument must be a value type (include the `Structure` constraint)</span></span>  
  
- <span data-ttu-id="cb8e8-111">El argumento de tipo debe ser un tipo de referencia (incluya la restricción `Class` ).</span><span class="sxs-lookup"><span data-stu-id="cb8e8-111">The type argument must be a reference type (include the `Class` constraint)</span></span>  
  
 <span data-ttu-id="cb8e8-112">No es posible especificar `Structure` y `Class` para el mismo parámetro de tipo y no se pueden especificar estas restricciones más de una vez.</span><span class="sxs-lookup"><span data-stu-id="cb8e8-112">You cannot specify both `Structure` and `Class` for the same type parameter, and you cannot specify either one more than once.</span></span>  
  
 <span data-ttu-id="cb8e8-113">**Identificador de error:** BC32061</span><span class="sxs-lookup"><span data-stu-id="cb8e8-113">**Error ID:** BC32061</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cb8e8-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="cb8e8-114">To correct this error</span></span>  
  
- <span data-ttu-id="cb8e8-115">Compruebe que la expresión y sus elementos estén escritos correctamente.</span><span class="sxs-lookup"><span data-stu-id="cb8e8-115">Verify that the expression and its elements are spelled correctly.</span></span>  
  
- <span data-ttu-id="cb8e8-116">Si la expresión no cumple los requisitos de la lista de requisitos anterior, quítela de la lista de restricciones.</span><span class="sxs-lookup"><span data-stu-id="cb8e8-116">If the expression does not qualify for the preceding list of requirements, remove it from the constraint list.</span></span>  
  
- <span data-ttu-id="cb8e8-117">Si la expresión hace referencia a una interfaz o una clase, compruebe que el compilador tenga acceso a dicha interfaz o clase.</span><span class="sxs-lookup"><span data-stu-id="cb8e8-117">If the expression refers to an interface or class, verify that the compiler has access to that interface or class.</span></span> <span data-ttu-id="cb8e8-118">Puede que deba calificar su nombre y quizás tenga que agregar una referencia al proyecto.</span><span class="sxs-lookup"><span data-stu-id="cb8e8-118">You might need to qualify its name, and you might need to add a reference to your project.</span></span> <span data-ttu-id="cb8e8-119">Para obtener más información, vea "referencias a proyectos" en [referencias a elementos declarados](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="cb8e8-119">For more information, see "References to Projects" in [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb8e8-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cb8e8-120">See also</span></span>

- [<span data-ttu-id="cb8e8-121">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cb8e8-121">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="cb8e8-122">Tipos de valor y tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="cb8e8-122">Value Types and Reference Types</span></span>](../../programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="cb8e8-123">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="cb8e8-123">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
