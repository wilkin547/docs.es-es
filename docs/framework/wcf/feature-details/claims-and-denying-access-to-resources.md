---
title: "Notificaciones y denegación de acceso a los recursos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: claims [WCF], denying access to resources
ms.assetid: 145ebb41-680e-4256-b14c-1efb4af1e982
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 156856ddd1a4c3b1d8f77a8a61f7e0336f993839
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="claims-and-denying-access-to-resources"></a>Notificaciones y denegación de acceso a los recursos
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] admite un mecanismo de autorización basado en notificaciones. Además de permitir el acceso a recursos basados en la presencia de notificaciones, los sistemas deniegan el acceso con frecuencia a los recursos basados en la presencia de notificaciones. Tales sistemas deberían examinar <xref:System.IdentityModel.Policy.AuthorizationContext> para notificaciones a las que se les deniega el acceso antes de buscar notificaciones a las que sí se les permite.  
  
 Por ejemplo, un sistema podría denegar el acceso a un recurso a cualquiera que tenga una notificación con un tipo de `Age`, un derecho de <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> y un valor de recurso de `Under 21` solo cuando esa identidad también tiene una notificación de tipo `Name`, un derecho de <xref:System.IdentityModel.Claims.Rights.Identity%2A> y un valor de recurso de `Mallory`. Dicho de otro modo, el sistema deniega el acceso a cualquiera que tenga menos de 21 años y lo otorga cuando el nombre es Mallory. Para implementar correctamente esta semántica, es importante buscar primero la notificación `Age` y determinar si la edad es inferior a los 21 años. De lo contrario, si Mallory tiene menos de 21, solo se concederá acceso al recurso según lo especificado en la notificación `Name`.  
  
## <a name="see-also"></a>Vea también  
 [Administración de notificaciones y autorización con el modelo de identidad](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [Notificaciones y tokens](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)
