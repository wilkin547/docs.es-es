---
title: "Estructura &#39; &lt;structurename&gt;&#39; debe contener la variable de miembro de al menos una instancia o declaración de evento de al menos una instancia no esté marcada como &#39; Personalizar &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b28dd59271bdaca52072710ea797fae6e9168eab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a><span data-ttu-id="28b3a-102">Estructura &#39; &lt;structurename&gt;&#39; debe contener la variable de miembro de al menos una instancia o declaración de evento de al menos una instancia no esté marcada como &#39; Personalizar &#39;</span><span class="sxs-lookup"><span data-stu-id="28b3a-102">Structure &#39;&lt;structurename&gt;&#39; must contain at least one instance member variable or at least one instance event declaration not marked &#39;Custom&#39;</span></span>
<span data-ttu-id="28b3a-103">Una definición de estructura no incluye las variables no compartidas o eventos no personalizados no compartidos.</span><span class="sxs-lookup"><span data-stu-id="28b3a-103">A structure definition does not include any nonshared variables or nonshared noncustom events.</span></span>  
  
 <span data-ttu-id="28b3a-104">Cada estructura debe tener una variable o un evento que se aplica a cada instancia concreta (no compartida) en lugar de a todas las instancias colectivamente ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span><span class="sxs-lookup"><span data-stu-id="28b3a-104">Every structure must have either a variable or an event that applies to each specific instance (nonshared) instead of to all instances collectively ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span></span> <span data-ttu-id="28b3a-105">Procedimientos, propiedades y constantes no compartidos no cumplen este requisito.</span><span class="sxs-lookup"><span data-stu-id="28b3a-105">Nonshared constants, properties, and procedures do not satisfy this requirement.</span></span> <span data-ttu-id="28b3a-106">Además, si no hay ninguna variable no compartida y un solo evento no compartido, ese evento no puede ser un `Custom` eventos.</span><span class="sxs-lookup"><span data-stu-id="28b3a-106">In addition, if there are no nonshared variables and only one nonshared event, that event cannot be a `Custom` event.</span></span>  
  
 <span data-ttu-id="28b3a-107">**Id. de error:** BC30941</span><span class="sxs-lookup"><span data-stu-id="28b3a-107">**Error ID:** BC30941</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="28b3a-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="28b3a-108">To correct this error</span></span>  
  
-   <span data-ttu-id="28b3a-109">Definir al menos una variable o evento que no es `Shared`.</span><span class="sxs-lookup"><span data-stu-id="28b3a-109">Define at least one variable or event that is not `Shared`.</span></span> <span data-ttu-id="28b3a-110">Si define un solo evento, debe ser no personalizados, así como no compartido.</span><span class="sxs-lookup"><span data-stu-id="28b3a-110">If you define only one event, it must be noncustom as well as nonshared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28b3a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="28b3a-111">See Also</span></span>  
 [<span data-ttu-id="28b3a-112">Estructuras</span><span class="sxs-lookup"><span data-stu-id="28b3a-112">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="28b3a-113">Declarar una estructura</span><span class="sxs-lookup"><span data-stu-id="28b3a-113">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="28b3a-114">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="28b3a-114">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
