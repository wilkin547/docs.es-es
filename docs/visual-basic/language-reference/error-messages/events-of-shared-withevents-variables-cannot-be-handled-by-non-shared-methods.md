---
title: Los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: 2b32043898986b3e3e68fab18c5f907843d7691c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838656"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a><span data-ttu-id="2d040-102">Los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas</span><span class="sxs-lookup"><span data-stu-id="2d040-102">Events of shared WithEvents variables cannot be handled by non-shared methods</span></span>
<span data-ttu-id="2d040-103">Una variable declarada con el `Shared` modificador es una variable compartida.</span><span class="sxs-lookup"><span data-stu-id="2d040-103">A variable declared with the `Shared` modifier is a shared variable.</span></span> <span data-ttu-id="2d040-104">Una variable compartida identifica exactamente una ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="2d040-104">A shared variable identifies exactly one storage location.</span></span> <span data-ttu-id="2d040-105">Una variable declarada con el `WithEvents` modificador afirma que el tipo al que pertenece la variable controla el conjunto de eventos que provoca la variable.</span><span class="sxs-lookup"><span data-stu-id="2d040-105">A variable declared with the `WithEvents` modifier asserts that the type to which the variable belongs handles the set of events the variable raises.</span></span> <span data-ttu-id="2d040-106">Cuando se asigna un valor a la variable, la propiedad creada por el `WithEvents` declaración modo se desenlaza cualquier controlador de eventos existente y enlaza el nuevo controlador de eventos a través de la `Add` método.</span><span class="sxs-lookup"><span data-stu-id="2d040-106">When a value is assigned to the variable, the property created by the `WithEvents` declaration unhooks any existing event handler and hooks up the new event handler via the `Add` method.</span></span>  
  
 <span data-ttu-id="2d040-107">**Identificador de error:** BC30594</span><span class="sxs-lookup"><span data-stu-id="2d040-107">**Error ID:** BC30594</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2d040-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="2d040-108">To correct this error</span></span>  
  
-   <span data-ttu-id="2d040-109">Declare el controlador de eventos `Shared`.</span><span class="sxs-lookup"><span data-stu-id="2d040-109">Declare your event handler `Shared`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d040-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d040-110">See also</span></span>

- [<span data-ttu-id="2d040-111">Shared</span><span class="sxs-lookup"><span data-stu-id="2d040-111">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="2d040-112">WithEvents</span><span class="sxs-lookup"><span data-stu-id="2d040-112">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
