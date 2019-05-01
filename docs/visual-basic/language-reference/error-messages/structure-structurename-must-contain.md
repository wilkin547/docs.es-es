---
title: La estructura '<structurename>' debe contener al menos una variable miembro de instancia o una declaración de evento de instancia que no esté marcada como 'Custom'
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 598aef3943a53ee6eb97064819c9128de1839f52
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62055113"
---
# <a name="structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a><span data-ttu-id="76989-102">Estructura '\<structurename >' debe contener al menos una variable miembro de instancia o declaración de evento de al menos una instancia no esté marcada como 'Custom'</span><span class="sxs-lookup"><span data-stu-id="76989-102">Structure '\<structurename>' must contain at least one instance member variable or at least one instance event declaration not marked 'Custom'</span></span>
<span data-ttu-id="76989-103">Una definición de estructura no incluye las variables no compartidas o eventos no personalizados no compartidos.</span><span class="sxs-lookup"><span data-stu-id="76989-103">A structure definition does not include any nonshared variables or nonshared noncustom events.</span></span>  
  
 <span data-ttu-id="76989-104">Cada estructura debe tener una variable o un evento que se aplica a cada instancia concreta (no compartida) en lugar de a todas las instancias colectivamente ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span><span class="sxs-lookup"><span data-stu-id="76989-104">Every structure must have either a variable or an event that applies to each specific instance (nonshared) instead of to all instances collectively ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span></span> <span data-ttu-id="76989-105">Procedimientos, propiedades y constantes no compartidas no cumplen este requisito.</span><span class="sxs-lookup"><span data-stu-id="76989-105">Nonshared constants, properties, and procedures do not satisfy this requirement.</span></span> <span data-ttu-id="76989-106">Además, si no hay ninguna variable no compartida y un solo evento no compartido, ese evento no puede ser un `Custom` eventos.</span><span class="sxs-lookup"><span data-stu-id="76989-106">In addition, if there are no nonshared variables and only one nonshared event, that event cannot be a `Custom` event.</span></span>  
  
 <span data-ttu-id="76989-107">**Identificador de error:** BC30941</span><span class="sxs-lookup"><span data-stu-id="76989-107">**Error ID:** BC30941</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="76989-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="76989-108">To correct this error</span></span>  
  
- <span data-ttu-id="76989-109">Definir al menos una variable o evento que no es `Shared`.</span><span class="sxs-lookup"><span data-stu-id="76989-109">Define at least one variable or event that is not `Shared`.</span></span> <span data-ttu-id="76989-110">Si define un solo evento, debe ser compartidas, así como no compartidos.</span><span class="sxs-lookup"><span data-stu-id="76989-110">If you define only one event, it must be noncustom as well as nonshared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76989-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="76989-111">See also</span></span>

- [<span data-ttu-id="76989-112">Estructuras</span><span class="sxs-lookup"><span data-stu-id="76989-112">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="76989-113">Cómo: Declarar una estructura</span><span class="sxs-lookup"><span data-stu-id="76989-113">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="76989-114">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="76989-114">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
