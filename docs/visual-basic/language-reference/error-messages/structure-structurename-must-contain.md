---
title: Estructura &#39; &lt;structurename&gt; &#39; debe contener al menos una variable miembro de instancia o declaración de evento de al menos una instancia no esté marcada como &#39;personalizada&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 85a4babc808e274a99f2c9faf08a02abf8aa4e93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594505"
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a><span data-ttu-id="f5543-102">Estructura &#39; &lt;structurename&gt; &#39; debe contener al menos una variable miembro de instancia o declaración de evento de al menos una instancia no esté marcada como &#39;personalizada&#39;</span><span class="sxs-lookup"><span data-stu-id="f5543-102">Structure &#39;&lt;structurename&gt;&#39; must contain at least one instance member variable or at least one instance event declaration not marked &#39;Custom&#39;</span></span>
<span data-ttu-id="f5543-103">Una definición de estructura no incluye las variables no compartidas o eventos no personalizados no compartidos.</span><span class="sxs-lookup"><span data-stu-id="f5543-103">A structure definition does not include any nonshared variables or nonshared noncustom events.</span></span>  
  
 <span data-ttu-id="f5543-104">Cada estructura debe tener una variable o un evento que se aplica a cada instancia concreta (no compartida) en lugar de a todas las instancias colectivamente ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span><span class="sxs-lookup"><span data-stu-id="f5543-104">Every structure must have either a variable or an event that applies to each specific instance (nonshared) instead of to all instances collectively ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span></span> <span data-ttu-id="f5543-105">Procedimientos, propiedades y constantes no compartidos no cumplen este requisito.</span><span class="sxs-lookup"><span data-stu-id="f5543-105">Nonshared constants, properties, and procedures do not satisfy this requirement.</span></span> <span data-ttu-id="f5543-106">Además, si no hay ninguna variable no compartida y un solo evento no compartido, ese evento no puede ser un `Custom` eventos.</span><span class="sxs-lookup"><span data-stu-id="f5543-106">In addition, if there are no nonshared variables and only one nonshared event, that event cannot be a `Custom` event.</span></span>  
  
 <span data-ttu-id="f5543-107">**Id. de error:** BC30941</span><span class="sxs-lookup"><span data-stu-id="f5543-107">**Error ID:** BC30941</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f5543-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f5543-108">To correct this error</span></span>  
  
-   <span data-ttu-id="f5543-109">Definir al menos una variable o evento que no es `Shared`.</span><span class="sxs-lookup"><span data-stu-id="f5543-109">Define at least one variable or event that is not `Shared`.</span></span> <span data-ttu-id="f5543-110">Si define un solo evento, debe ser no personalizados, así como no compartido.</span><span class="sxs-lookup"><span data-stu-id="f5543-110">If you define only one event, it must be noncustom as well as nonshared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5543-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5543-111">See Also</span></span>  
 [<span data-ttu-id="f5543-112">Estructuras</span><span class="sxs-lookup"><span data-stu-id="f5543-112">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="f5543-113">Declarar una estructura</span><span class="sxs-lookup"><span data-stu-id="f5543-113">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="f5543-114">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f5543-114">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
