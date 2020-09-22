---
title: La estructura '<structurename>' debe contener al menos una variable miembro de instancia o una declaración de evento de instancia que no esté marcada como 'Custom'
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: a350940cf052aa8fbee4a1e3c61cbeaa4e37408a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870589"
---
# <a name="structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a><span data-ttu-id="3f3c1-102">La estructura '\<structurename>' debe contener al menos una variable miembro de instancia o una declaración de evento de instancia que no esté marcada como 'Custom'</span><span class="sxs-lookup"><span data-stu-id="3f3c1-102">Structure '\<structurename>' must contain at least one instance member variable or at least one instance event declaration not marked 'Custom'</span></span>

<span data-ttu-id="3f3c1-103">Una definición de estructura no incluye variables no compartidas ni eventos no personalizados no compartidos.</span><span class="sxs-lookup"><span data-stu-id="3f3c1-103">A structure definition does not include any nonshared variables or nonshared noncustom events.</span></span>  
  
 <span data-ttu-id="3f3c1-104">Cada estructura debe tener una variable o un evento que se aplique a cada instancia específica (no compartida) en lugar de a todas las instancias colectivas ([compartidas](../modifiers/shared.md)).</span><span class="sxs-lookup"><span data-stu-id="3f3c1-104">Every structure must have either a variable or an event that applies to each specific instance (nonshared) instead of to all instances collectively ([Shared](../modifiers/shared.md)).</span></span> <span data-ttu-id="3f3c1-105">Las constantes, propiedades y procedimientos no compartidos no satisfacen este requisito.</span><span class="sxs-lookup"><span data-stu-id="3f3c1-105">Nonshared constants, properties, and procedures do not satisfy this requirement.</span></span> <span data-ttu-id="3f3c1-106">Además, si no hay ninguna variable no compartida y solo un evento no compartido, ese evento no puede ser un `Custom` evento.</span><span class="sxs-lookup"><span data-stu-id="3f3c1-106">In addition, if there are no nonshared variables and only one nonshared event, that event cannot be a `Custom` event.</span></span>  
  
 <span data-ttu-id="3f3c1-107">**Identificador de error:** BC30941</span><span class="sxs-lookup"><span data-stu-id="3f3c1-107">**Error ID:** BC30941</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3f3c1-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="3f3c1-108">To correct this error</span></span>  
  
- <span data-ttu-id="3f3c1-109">Defina al menos una variable o un evento que no sea `Shared` .</span><span class="sxs-lookup"><span data-stu-id="3f3c1-109">Define at least one variable or event that is not `Shared`.</span></span> <span data-ttu-id="3f3c1-110">Si solo se define un evento, debe ser no personalizado, así como no compartido.</span><span class="sxs-lookup"><span data-stu-id="3f3c1-110">If you define only one event, it must be noncustom as well as nonshared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f3c1-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3f3c1-111">See also</span></span>

- [<span data-ttu-id="3f3c1-112">Estructuras</span><span class="sxs-lookup"><span data-stu-id="3f3c1-112">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="3f3c1-113">Procedimiento Declaración de estructuras</span><span class="sxs-lookup"><span data-stu-id="3f3c1-113">How to: Declare a Structure</span></span>](../../programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="3f3c1-114">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="3f3c1-114">Structure Statement</span></span>](../statements/structure-statement.md)
