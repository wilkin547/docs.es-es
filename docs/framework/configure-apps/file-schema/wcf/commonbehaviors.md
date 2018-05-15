---
title: '&lt;commonBehaviors&gt;'
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: aaf89f73b6de250aaa572b8fef31e5a1ebd5482b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltcommonbehaviorsgt"></a><span data-ttu-id="31c3d-102">&lt;commonBehaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="31c3d-102">&lt;commonBehaviors&gt;</span></span>
<span data-ttu-id="31c3d-103">La sección `commonBehaviors` sólo se puede definir en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="31c3d-103">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="31c3d-104">Define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="31c3d-104">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="31c3d-105">Cada colección define elementos de comportamiento utilizados respectivamente por todos los extremos [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] y servicios del equipo.</span><span class="sxs-lookup"><span data-stu-id="31c3d-105">Each collection defines behavior elements consumed by all [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] endpoints and services on the machine respectively.</span></span> <span data-ttu-id="31c3d-106">Los comportamientos definidos en `endpointBehaviors` sólo se aplican a los clientes y los comportamientos definidos en `serviceBehaviors` sólo se aplican a los servicios.</span><span class="sxs-lookup"><span data-stu-id="31c3d-106">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="31c3d-107">Si un comportamiento se define en las secciones `commonBehaviors` y `behaviors`, el comportamiento en la sección `behaviors` tendrá preferencia.</span><span class="sxs-lookup"><span data-stu-id="31c3d-107">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>
