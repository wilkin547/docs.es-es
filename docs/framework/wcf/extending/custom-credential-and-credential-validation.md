---
description: 'Más información sobre: credenciales personalizadas y validación de credenciales'
title: Credencial personalizada y validación de la credencial
ms.date: 03/30/2017
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
ms.openlocfilehash: f1ceb8cf46cca01ac31faeb9485cbeb6c8663d31
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735314"
---
# <a name="custom-credential-and-credential-validation"></a>Credencial personalizada y validación de la credencial

La seguridad en Windows Communication Foundation (WCF) se basa en el intercambio de credenciales entre servicios y clientes. La mayoría de los escenarios de seguridad se pueden cumplir utilizando tipos de credencial comunes, como Windows (Kerberos), el nombre de usuario y contraseñas y certificados. Sin embargo, si se exige un nuevo tipo de credencial, los temas en esta sección explican cómo administrar y validar los nuevos tipos.  
  
## <a name="in-this-section"></a>En esta sección  

 [Procedimiento para crear un servicio que emplee un validador de certificado personalizado](how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 Explica cómo personalizar la validación de WCF heredando de la <xref:System.IdentityModel.Selectors.X509CertificateValidator> clase.  
  
 [Tutorial: Crear credenciales de cliente y servicio personalizadas](walkthrough-creating-custom-client-and-service-credentials.md)  
 Muestra cómo extender las <xref:System.ServiceModel.Description.ClientCredentials> clases y <xref:System.ServiceModel.Description.ServiceCredentials> para alojar nuevos tipos de credenciales. Esto es lo primero en una serie de temas que habilitan la creación de tipos de credencial personalizados.  
  
 [Procedimiento para crear un proveedor de tokens de seguridad personalizado](how-to-create-a-custom-security-token-provider.md)  
 Explica cómo crear un proveedor de token de seguridad para administrar nuevos tipos de credencial y devolver nuevos tokens para la credencial. Este es el segundo tema en la serie.  
  
 [Procedimiento para crear un autenticador de tokens de seguridad personalizado](how-to-create-a-custom-security-token-authenticator.md)  
 Explica cómo crear un autenticador personalizado para autenticar un nuevo tipo de credencial. Este es el tercer tema en la serie.  
  
## <a name="reference"></a>Referencia  

 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Autenticación](../feature-details/authentication-in-wcf.md)  
  
 [Federación y tokens emitidos](../feature-details/federation-and-issued-tokens.md)  
  
 [Autorización](../feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a>Vea también

- [Seguridad](../feature-details/security.md)
