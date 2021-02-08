---
description: 'Más información sobre: BC30594: los eventos de variables WithEvents compartidas no se pueden controlar mediante métodos no compartidos'
title: Los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: f9e8bf6e0d365c4ee747deb6be0e809904d87117
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796423"
---
# <a name="bc30594-events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a><span data-ttu-id="14d83-103">BC30594: los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas</span><span class="sxs-lookup"><span data-stu-id="14d83-103">BC30594: Events of shared WithEvents variables cannot be handled by non-shared methods</span></span>

<span data-ttu-id="14d83-104">Una variable declarada con el `Shared` modificador es una variable compartida.</span><span class="sxs-lookup"><span data-stu-id="14d83-104">A variable declared with the `Shared` modifier is a shared variable.</span></span> <span data-ttu-id="14d83-105">Una variable compartida identifica exactamente una ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="14d83-105">A shared variable identifies exactly one storage location.</span></span> <span data-ttu-id="14d83-106">Una variable declarada con el `WithEvents` modificador valida que el tipo al que pertenece la variable controla el conjunto de eventos que genera la variable.</span><span class="sxs-lookup"><span data-stu-id="14d83-106">A variable declared with the `WithEvents` modifier asserts that the type to which the variable belongs handles the set of events the variable raises.</span></span> <span data-ttu-id="14d83-107">Cuando se asigna un valor a la variable, la propiedad creada por la `WithEvents` declaración desenlaza cualquier controlador de eventos existente y enlaza el nuevo controlador de eventos a través del `Add` método.</span><span class="sxs-lookup"><span data-stu-id="14d83-107">When a value is assigned to the variable, the property created by the `WithEvents` declaration unhooks any existing event handler and hooks up the new event handler via the `Add` method.</span></span>

 <span data-ttu-id="14d83-108">**Identificador de error:** BC30594</span><span class="sxs-lookup"><span data-stu-id="14d83-108">**Error ID:** BC30594</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="14d83-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="14d83-109">To correct this error</span></span>

- <span data-ttu-id="14d83-110">Declare el controlador de eventos `Shared` .</span><span class="sxs-lookup"><span data-stu-id="14d83-110">Declare your event handler `Shared`.</span></span>

## <a name="see-also"></a><span data-ttu-id="14d83-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="14d83-111">See also</span></span>

- [<span data-ttu-id="14d83-112">Compartido</span><span class="sxs-lookup"><span data-stu-id="14d83-112">Shared</span></span>](../modifiers/shared.md)
- [<span data-ttu-id="14d83-113">WithEvents</span><span class="sxs-lookup"><span data-stu-id="14d83-113">WithEvents</span></span>](../modifiers/withevents.md)
