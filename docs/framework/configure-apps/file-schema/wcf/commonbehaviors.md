---
title: <commonBehaviors>
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: 73bf759fd3dfa87398aa74de93160a4ffce08eba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704367"
---
# <a name="commonbehaviors"></a><span data-ttu-id="f952b-101">\<commonBehaviors></span><span class="sxs-lookup"><span data-stu-id="f952b-101">\<commonBehaviors></span></span>
<span data-ttu-id="f952b-102">La sección `commonBehaviors` sólo se puede definir en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="f952b-102">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="f952b-103">Define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="f952b-103">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="f952b-104">Cada colección define elementos de comportamiento utilizados respectivamente por todos los extremos WCF y servicios en el equipo.</span><span class="sxs-lookup"><span data-stu-id="f952b-104">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span> <span data-ttu-id="f952b-105">Los comportamientos definidos en `endpointBehaviors` sólo se aplican a los clientes y los comportamientos definidos en `serviceBehaviors` sólo se aplican a los servicios.</span><span class="sxs-lookup"><span data-stu-id="f952b-105">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="f952b-106">Si un comportamiento se define en las secciones `commonBehaviors` y `behaviors`, el comportamiento en la sección `behaviors` tendrá preferencia.</span><span class="sxs-lookup"><span data-stu-id="f952b-106">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>
