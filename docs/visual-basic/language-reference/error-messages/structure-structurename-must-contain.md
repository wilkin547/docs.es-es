---
description: "Más información sobre: BC30941: la estructura ' <structurename> ' debe contener al menos una variable miembro de instancia o una declaración de evento de instancia que no esté marcada como ' Custom '"
title: La estructura '<structurename>' debe contener al menos una variable miembro de instancia o una declaración de evento de instancia que no esté marcada como 'Custom'
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 08596997decd9d739ac95ad3e4191cb126b3efb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641452"
---
# <a name="bc30941-structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a><span data-ttu-id="07bce-103">BC30941: la estructura ' \<structurename> ' debe contener al menos una variable miembro de instancia o una declaración de evento de instancia que no esté marcada como ' Custom '</span><span class="sxs-lookup"><span data-stu-id="07bce-103">BC30941: Structure '\<structurename>' must contain at least one instance member variable or at least one instance event declaration not marked 'Custom'</span></span>

<span data-ttu-id="07bce-104">Una definición de estructura no incluye variables no compartidas ni eventos no personalizados no compartidos.</span><span class="sxs-lookup"><span data-stu-id="07bce-104">A structure definition does not include any nonshared variables or nonshared noncustom events.</span></span>

 <span data-ttu-id="07bce-105">Cada estructura debe tener una variable o un evento que se aplique a cada instancia específica (no compartida) en lugar de a todas las instancias colectivas ([compartidas](../modifiers/shared.md)).</span><span class="sxs-lookup"><span data-stu-id="07bce-105">Every structure must have either a variable or an event that applies to each specific instance (nonshared) instead of to all instances collectively ([Shared](../modifiers/shared.md)).</span></span> <span data-ttu-id="07bce-106">Las constantes, propiedades y procedimientos no compartidos no satisfacen este requisito.</span><span class="sxs-lookup"><span data-stu-id="07bce-106">Nonshared constants, properties, and procedures do not satisfy this requirement.</span></span> <span data-ttu-id="07bce-107">Además, si no hay ninguna variable no compartida y solo un evento no compartido, ese evento no puede ser un `Custom` evento.</span><span class="sxs-lookup"><span data-stu-id="07bce-107">In addition, if there are no nonshared variables and only one nonshared event, that event cannot be a `Custom` event.</span></span>

 <span data-ttu-id="07bce-108">**Identificador de error:** BC30941</span><span class="sxs-lookup"><span data-stu-id="07bce-108">**Error ID:** BC30941</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="07bce-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="07bce-109">To correct this error</span></span>

- <span data-ttu-id="07bce-110">Defina al menos una variable o un evento que no sea `Shared` .</span><span class="sxs-lookup"><span data-stu-id="07bce-110">Define at least one variable or event that is not `Shared`.</span></span> <span data-ttu-id="07bce-111">Si solo se define un evento, debe ser no personalizado, así como no compartido.</span><span class="sxs-lookup"><span data-stu-id="07bce-111">If you define only one event, it must be noncustom as well as nonshared.</span></span>

## <a name="see-also"></a><span data-ttu-id="07bce-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="07bce-112">See also</span></span>

- [<span data-ttu-id="07bce-113">Estructuras</span><span class="sxs-lookup"><span data-stu-id="07bce-113">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="07bce-114">Procedimiento Declaración de estructuras</span><span class="sxs-lookup"><span data-stu-id="07bce-114">How to: Declare a Structure</span></span>](../../programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="07bce-115">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="07bce-115">Structure Statement</span></span>](../statements/structure-statement.md)
