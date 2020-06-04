---
title: Los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: fc163c1069aa6f41766664e0fa5f5a9c34a1f73d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409574"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a><span data-ttu-id="2e8a8-102">Los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas</span><span class="sxs-lookup"><span data-stu-id="2e8a8-102">Events of shared WithEvents variables cannot be handled by non-shared methods</span></span>
<span data-ttu-id="2e8a8-103">Una variable declarada con el `Shared` modificador es una variable compartida.</span><span class="sxs-lookup"><span data-stu-id="2e8a8-103">A variable declared with the `Shared` modifier is a shared variable.</span></span> <span data-ttu-id="2e8a8-104">Una variable compartida identifica exactamente una ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="2e8a8-104">A shared variable identifies exactly one storage location.</span></span> <span data-ttu-id="2e8a8-105">Una variable declarada con el `WithEvents` modificador valida que el tipo al que pertenece la variable controla el conjunto de eventos que genera la variable.</span><span class="sxs-lookup"><span data-stu-id="2e8a8-105">A variable declared with the `WithEvents` modifier asserts that the type to which the variable belongs handles the set of events the variable raises.</span></span> <span data-ttu-id="2e8a8-106">Cuando se asigna un valor a la variable, la propiedad creada por la `WithEvents` declaración desenlaza cualquier controlador de eventos existente y enlaza el nuevo controlador de eventos a través del `Add` método.</span><span class="sxs-lookup"><span data-stu-id="2e8a8-106">When a value is assigned to the variable, the property created by the `WithEvents` declaration unhooks any existing event handler and hooks up the new event handler via the `Add` method.</span></span>  
  
 <span data-ttu-id="2e8a8-107">**Identificador de error:** BC30594</span><span class="sxs-lookup"><span data-stu-id="2e8a8-107">**Error ID:** BC30594</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2e8a8-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="2e8a8-108">To correct this error</span></span>  
  
- <span data-ttu-id="2e8a8-109">Declare el controlador de eventos `Shared` .</span><span class="sxs-lookup"><span data-stu-id="2e8a8-109">Declare your event handler `Shared`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e8a8-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2e8a8-110">See also</span></span>

- [<span data-ttu-id="2e8a8-111">Compartido</span><span class="sxs-lookup"><span data-stu-id="2e8a8-111">Shared</span></span>](../modifiers/shared.md)
- [<span data-ttu-id="2e8a8-112">WithEvents</span><span class="sxs-lookup"><span data-stu-id="2e8a8-112">WithEvents</span></span>](../modifiers/withevents.md)
