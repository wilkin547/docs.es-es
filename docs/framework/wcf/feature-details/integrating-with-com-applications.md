---
title: "Integración en aplicaciones COM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a0e625beaf20f6445099d8fb15cb175d3d71a860
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="integrating-with-com-applications"></a>Integración en aplicaciones COM
Los servicios [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se pueden integrar directamente en su código existente mediante el moniker del servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. El moniker de servicio se puede utilizar a partir de una gama amplia de entornos de desarrollo basados en COM, como Office VBA, Visual Basic 6.0 o Visual C++ 6.0.  
  
## <a name="in-this-section"></a>En esta sección  
 [Integración con la introducción a las aplicaciones COM](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 Proporciona información general de las partes principales del proceso de la integración.  
  
 [Cómo: registrar y configurar un Moniker de servicio](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 Para utilizar el moniker del servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dentro de una aplicación COM, registre los tipos de atributos necesarios con COM y configure la aplicación COM y el moniker con la configuración de enlace necesaria.  
  
 [Cómo: utilizar el Moniker de servicio de Windows Communication Foundation sin registro](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 Explica cómo obtener la definición del contrato en forma de un documento de Lenguaje de Definición de servicios Web (WSDL) o de un punto de conexión de WS-MetadataExchange.  
  
 [Cómo: utilizar un Moniker de servicio con contratos WSDL](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 Describe cómo llamar a un ejemplo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante un moniker de WSDL [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Cómo: utilizar un Moniker de servicio con contratos de intercambio de metadatos](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 Describe cómo llamar a un ejemplo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante un moniker [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que especifica un extremo de Mex.  
  
 [Cómo: especificar las credenciales de seguridad del canal](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 El moniker del servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite la interfaz `IChannelCredentials` que permite una serie de métodos alternativos para especificar las credenciales del canal.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a>Vea también  
 [Integración con aplicaciones COM +](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
