---
description: Más información acerca de las notificaciones y denegación de acceso a los recursos
title: Notificaciones y denegación de acceso a los recursos
ms.date: 03/30/2017
helpviewer_keywords:
- claims [WCF], denying access to resources
ms.assetid: 145ebb41-680e-4256-b14c-1efb4af1e982
ms.openlocfilehash: 0bbef26b0df06305db4ce460da4ba6177c79f56a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734976"
---
# <a name="claims-and-denying-access-to-resources"></a><span data-ttu-id="dfeb3-103">Notificaciones y denegación de acceso a los recursos</span><span class="sxs-lookup"><span data-stu-id="dfeb3-103">Claims and Denying Access to Resources</span></span>

<span data-ttu-id="dfeb3-104">Windows Communication Foundation (WCF) admite un mecanismo de autorización basado en notificaciones.</span><span class="sxs-lookup"><span data-stu-id="dfeb3-104">Windows Communication Foundation (WCF) supports a claims-based authorization mechanism.</span></span> <span data-ttu-id="dfeb3-105">Además de permitir el acceso a recursos basados en la presencia de notificaciones, los sistemas deniegan el acceso con frecuencia a los recursos basados en la presencia de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="dfeb3-105">As well as allowing access to resources based on the presence of claims, systems often deny access to resources based on the presence of claims.</span></span> <span data-ttu-id="dfeb3-106">Tales sistemas deberían examinar <xref:System.IdentityModel.Policy.AuthorizationContext> para notificaciones a las que se les deniega el acceso antes de buscar notificaciones a las que sí se les permite.</span><span class="sxs-lookup"><span data-stu-id="dfeb3-106">Such systems should examine the <xref:System.IdentityModel.Policy.AuthorizationContext> for claims that result in access being denied before looking for claims that result in access being allowed.</span></span>  
  
 <span data-ttu-id="dfeb3-107">Por ejemplo, un sistema podría denegar el acceso a un recurso a cualquiera que tenga una notificación con un tipo de `Age`, un derecho de <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> y un valor de recurso de `Under 21` solo cuando esa identidad también tiene una notificación de tipo `Name`, un derecho de <xref:System.IdentityModel.Claims.Rights.Identity%2A> y un valor de recurso de `Mallory`.</span><span class="sxs-lookup"><span data-stu-id="dfeb3-107">For example, a system might deny access to a resource to anyone who has a claim with a type of `Age`, a right of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>, and a resource value of `Under 21` only when that identity also has a claim of type `Name`, a right of <xref:System.IdentityModel.Claims.Rights.Identity%2A>, and a resource value of `Mallory`.</span></span> <span data-ttu-id="dfeb3-108">Dicho de otro modo, el sistema deniega el acceso a cualquiera que tenga menos de 21 años y lo otorga cuando el nombre es Mallory.</span><span class="sxs-lookup"><span data-stu-id="dfeb3-108">Put another way, the system denies access to anyone who is under 21 years old and grants access when the name is Mallory.</span></span> <span data-ttu-id="dfeb3-109">Para implementar correctamente esta semántica, es importante buscar primero la notificación `Age` y determinar si la edad es inferior a los 21 años.</span><span class="sxs-lookup"><span data-stu-id="dfeb3-109">To correctly implement this semantic, it is important to look for the `Age` claim first and determine whether the age is under 21 years old.</span></span> <span data-ttu-id="dfeb3-110">De lo contrario, si Mallory tiene menos de 21, solo se concederá acceso al recurso según lo especificado en la notificación `Name`.</span><span class="sxs-lookup"><span data-stu-id="dfeb3-110">Otherwise, if Mallory is under 21, then the resource may be granted access solely on the basis of the `Name` claim.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfeb3-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfeb3-111">See also</span></span>

- [<span data-ttu-id="dfeb3-112">Administración de notificaciones y autorización con el modelo de identidad</span><span class="sxs-lookup"><span data-stu-id="dfeb3-112">Managing Claims and Authorization with the Identity Model</span></span>](managing-claims-and-authorization-with-the-identity-model.md)
- [<span data-ttu-id="dfeb3-113">Notificaciones y tokens</span><span class="sxs-lookup"><span data-stu-id="dfeb3-113">Claims and Tokens</span></span>](claims-and-tokens.md)
