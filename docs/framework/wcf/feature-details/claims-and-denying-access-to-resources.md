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
# <a name="claims-and-denying-access-to-resources"></a>Notificaciones y denegación de acceso a los recursos

Windows Communication Foundation (WCF) admite un mecanismo de autorización basado en notificaciones. Además de permitir el acceso a recursos basados en la presencia de notificaciones, los sistemas deniegan el acceso con frecuencia a los recursos basados en la presencia de notificaciones. Tales sistemas deberían examinar <xref:System.IdentityModel.Policy.AuthorizationContext> para notificaciones a las que se les deniega el acceso antes de buscar notificaciones a las que sí se les permite.  
  
 Por ejemplo, un sistema podría denegar el acceso a un recurso a cualquiera que tenga una notificación con un tipo de `Age`, un derecho de <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> y un valor de recurso de `Under 21` solo cuando esa identidad también tiene una notificación de tipo `Name`, un derecho de <xref:System.IdentityModel.Claims.Rights.Identity%2A> y un valor de recurso de `Mallory`. Dicho de otro modo, el sistema deniega el acceso a cualquiera que tenga menos de 21 años y lo otorga cuando el nombre es Mallory. Para implementar correctamente esta semántica, es importante buscar primero la notificación `Age` y determinar si la edad es inferior a los 21 años. De lo contrario, si Mallory tiene menos de 21, solo se concederá acceso al recurso según lo especificado en la notificación `Name`.  
  
## <a name="see-also"></a>Vea también

- [Administración de notificaciones y autorización con el modelo de identidad](managing-claims-and-authorization-with-the-identity-model.md)
- [Notificaciones y tokens](claims-and-tokens.md)
