---
title: <commonBehaviors>
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: 55f70157b6759c5e1cb45da20eed928fa1d4a183
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176063"
---
# \<commonBehaviors>

<span data-ttu-id="12a36-101">La sección `commonBehaviors` sólo se puede definir en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="12a36-101">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="12a36-102">Define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="12a36-102">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="12a36-103">Cada colección define los elementos de comportamiento utilizados por todos los puntos de conexión y servicios de WCF en el equipo, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="12a36-103">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span> <span data-ttu-id="12a36-104">Los comportamientos definidos en `endpointBehaviors` sólo se aplican a los clientes y los comportamientos definidos en `serviceBehaviors` sólo se aplican a los servicios.</span><span class="sxs-lookup"><span data-stu-id="12a36-104">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="12a36-105">Si un comportamiento se define en las secciones `commonBehaviors` y `behaviors`, el comportamiento en la sección `behaviors` tendrá preferencia.</span><span class="sxs-lookup"><span data-stu-id="12a36-105">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>
