---
title: '&#39;&lt;expresión&gt; &#39; no se puede usar como una restricción de tipo'
ms.date: 07/20/2015
f1_keywords:
- bc32061
- vbc32061
helpviewer_keywords:
- BC32061
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
ms.openlocfilehash: 8e9aad2ec65e037b15e19ca2e624fdc8f28bc94e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588179"
---
# <a name="39ltexpressiongt39-cannot-be-used-as-a-type-constraint"></a><span data-ttu-id="136ec-102">&#39;&lt;expresión&gt; &#39; no se puede usar como una restricción de tipo</span><span class="sxs-lookup"><span data-stu-id="136ec-102">&#39;&lt;expression&gt;&#39; cannot be used as a type constraint</span></span>
<span data-ttu-id="136ec-103">Una lista de restricciones incluye una expresión que no representa una restricción válida en un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="136ec-103">A constraint list includes an expression that does not represent a valid constraint on a type parameter.</span></span>  
  
 <span data-ttu-id="136ec-104">Una lista de restricciones impone requisitos al argumento de tipo pasado al parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="136ec-104">A constraint list imposes requirements on the type argument passed to the type parameter.</span></span> <span data-ttu-id="136ec-105">Puede especificar los requisitos siguientes en cualquier combinación:</span><span class="sxs-lookup"><span data-stu-id="136ec-105">You can specify the following requirements in any combination:</span></span>  
  
-   <span data-ttu-id="136ec-106">El argumento de tipo debe implementar una o varias interfaces</span><span class="sxs-lookup"><span data-stu-id="136ec-106">The type argument must implement one or more interfaces</span></span>  
  
-   <span data-ttu-id="136ec-107">El argumento de tipo debe heredar de al menos una clase</span><span class="sxs-lookup"><span data-stu-id="136ec-107">The type argument must inherit from at most one class</span></span>  
  
-   <span data-ttu-id="136ec-108">El argumento de tipo debe exponer un constructor sin parámetros al que el código de creación pueda acceder (incluya la restricción `New` ).</span><span class="sxs-lookup"><span data-stu-id="136ec-108">The type argument must expose a parameterless constructor that the creating code can access (include the `New` constraint)</span></span>  
  
 <span data-ttu-id="136ec-109">Si no incluye ninguna clase o interfaz específica en la lista de restricciones, puede imponer un requisito más general especificando uno de los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="136ec-109">If you do not include any specific class or interface in the constraint list, you can impose a more general requirement by specifying one of the following:</span></span>  
  
-   <span data-ttu-id="136ec-110">El argumento de tipo debe ser un tipo de valor (incluya la restricción `Structure` ).</span><span class="sxs-lookup"><span data-stu-id="136ec-110">The type argument must be a value type (include the `Structure` constraint)</span></span>  
  
-   <span data-ttu-id="136ec-111">El argumento de tipo debe ser un tipo de referencia (incluya la restricción `Class` ).</span><span class="sxs-lookup"><span data-stu-id="136ec-111">The type argument must be a reference type (include the `Class` constraint)</span></span>  
  
 <span data-ttu-id="136ec-112">No es posible especificar `Structure` y `Class` para el mismo parámetro de tipo ni se pueden especificar estas restricciones más de una vez.</span><span class="sxs-lookup"><span data-stu-id="136ec-112">You cannot specify both `Structure` and `Class` for the same type parameter, and you cannot specify either one more than once.</span></span>  
  
 <span data-ttu-id="136ec-113">**Id. de error:** BC32061</span><span class="sxs-lookup"><span data-stu-id="136ec-113">**Error ID:** BC32061</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="136ec-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="136ec-114">To correct this error</span></span>  
  
-   <span data-ttu-id="136ec-115">Compruebe que la expresión y sus elementos estén escritos correctamente.</span><span class="sxs-lookup"><span data-stu-id="136ec-115">Verify that the expression and its elements are spelled correctly.</span></span>  
  
-   <span data-ttu-id="136ec-116">Si la expresión no cumple los requisitos de la lista de requisitos anterior, quítela de la lista de restricciones.</span><span class="sxs-lookup"><span data-stu-id="136ec-116">If the expression does not qualify for the preceding list of requirements, remove it from the constraint list.</span></span>  
  
-   <span data-ttu-id="136ec-117">Si la expresión hace referencia a una interfaz o una clase, compruebe que el compilador tenga acceso a dicha interfaz o clase.</span><span class="sxs-lookup"><span data-stu-id="136ec-117">If the expression refers to an interface or class, verify that the compiler has access to that interface or class.</span></span> <span data-ttu-id="136ec-118">Puede que deba calificar su nombre y quizás tenga que agregar una referencia al proyecto.</span><span class="sxs-lookup"><span data-stu-id="136ec-118">You might need to qualify its name, and you might need to add a reference to your project.</span></span> <span data-ttu-id="136ec-119">Para obtener más información, vea "Referencias a proyectos" en [referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="136ec-119">For more information, see "References to Projects" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="136ec-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="136ec-120">See Also</span></span>  
 [<span data-ttu-id="136ec-121">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="136ec-121">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="136ec-122">Tipos de valores y tipos de referencias</span><span class="sxs-lookup"><span data-stu-id="136ec-122">Value Types and Reference Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="136ec-123">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="136ec-123">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 
