---
title: '&lt;commonBehaviors&gt;'
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: 0a9fab68ce240fc37d27c42d9feff969b97f93a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350327"
---
# <a name="ltcommonbehaviorsgt"></a><span data-ttu-id="4a2ab-102">&lt;commonBehaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="4a2ab-102">&lt;commonBehaviors&gt;</span></span>
<span data-ttu-id="4a2ab-103">La sección `commonBehaviors` sólo se puede definir en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="4a2ab-103">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="4a2ab-104">Define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="4a2ab-104">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="4a2ab-105">Cada colección define elementos de comportamiento utilizados respectivamente por todos los extremos WCF y servicios en el equipo.</span><span class="sxs-lookup"><span data-stu-id="4a2ab-105">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span> <span data-ttu-id="4a2ab-106">Los comportamientos definidos en `endpointBehaviors` sólo se aplican a los clientes y los comportamientos definidos en `serviceBehaviors` sólo se aplican a los servicios.</span><span class="sxs-lookup"><span data-stu-id="4a2ab-106">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="4a2ab-107">Si un comportamiento se define en las secciones `commonBehaviors` y `behaviors`, el comportamiento en la sección `behaviors` tendrá preferencia.</span><span class="sxs-lookup"><span data-stu-id="4a2ab-107">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>
