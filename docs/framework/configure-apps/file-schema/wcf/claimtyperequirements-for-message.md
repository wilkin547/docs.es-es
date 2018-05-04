---
title: '&lt;claimTypeRequirements&gt; para &lt;message&gt;'
ms.date: 03/30/2017
ms.assetid: f95c5ecd-abb6-4b77-a6d7-a38727f4a142
ms.openlocfilehash: f4460311f5478f441b819bc8a48540d6feea69b1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimtyperequirementsgt-for-ltmessagegt"></a>&lt;claimTypeRequirements&gt; para &lt;message&gt;
Especifica una colección de tipos de notificación requeridos.  
  
 El servicio usa la colección para especificar cualquier notificación necesaria y opcional que debe estar en el token emitido que el cliente utiliza para tener acceso al servicio. El servicio expone los tipos de notificación necesarios en metadatos si se habilita la publicación de WSDL pero WCF no requiere que el token emitido contenga los tipos de notificación especificados. Los servicios que desean exigir tipos de notificación necesarios están presentes y deberían hacerlo con la directiva de autorización.  
  
 En los clientes federados, esta colección contiene la lista de notificaciones necesarias y opcionales que se envían al servicio del token de seguridad en la solicitud del cliente para un token emitido.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
