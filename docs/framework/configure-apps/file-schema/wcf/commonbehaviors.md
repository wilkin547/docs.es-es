---
description: 'Más información acerca de: <commonBehaviors>'
title: <commonBehaviors>
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: 2fa7397a2833623728bcca286682178d1cf3e1df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802325"
---
# \<commonBehaviors>

<span data-ttu-id="9f76d-102">La sección `commonBehaviors` sólo se puede definir en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="9f76d-102">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="9f76d-103">Define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="9f76d-103">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="9f76d-104">Cada colección define los elementos de comportamiento utilizados por todos los puntos de conexión y servicios de WCF en el equipo, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9f76d-104">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span> <span data-ttu-id="9f76d-105">Los comportamientos definidos en `endpointBehaviors` sólo se aplican a los clientes y los comportamientos definidos en `serviceBehaviors` sólo se aplican a los servicios.</span><span class="sxs-lookup"><span data-stu-id="9f76d-105">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="9f76d-106">Si un comportamiento se define en las secciones `commonBehaviors` y `behaviors`, el comportamiento en la sección `behaviors` tendrá preferencia.</span><span class="sxs-lookup"><span data-stu-id="9f76d-106">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>
