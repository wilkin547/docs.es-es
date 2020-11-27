---
title: Integración en aplicaciones COM
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
ms.openlocfilehash: bc58e22b64284d66367302d55b5c9554c9ec0d72
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268240"
---
# <a name="integrating-with-com-applications"></a>Integración en aplicaciones COM

Los servicios Windows Communication Foundation (WCF) se pueden integrar directamente en el código existente mediante el moniker de servicio WCF. El moniker de servicio se puede utilizar a partir de una gama amplia de entornos de desarrollo basados en COM, como Office VBA, Visual Basic 6.0 o Visual C++ 6.0.  
  
## <a name="in-this-section"></a>En esta sección  

 [Integración con la información general de las aplicaciones COM](integrating-with-com-applications-overview.md)  
 Proporciona información general de las partes principales del proceso de la integración.  
  
 [Procedimiento para registrar y configurar un moniker de servicio](how-to-register-and-configure-a-service-moniker.md)  
 Para utilizar el moniker de servicio de WCF en una aplicación COM, registre los tipos con atributos necesarios en COM y configure la aplicación COM y el moniker con la configuración de enlace necesaria.  
  
 [Procedimiento para usar el moniker de servicio de Windows Communication Foundation sin registrarse](use-the-wcf-service-moniker-without-registration.md)  
 Explica cómo obtener la definición del contrato en forma de un documento de Lenguaje de Definición de servicios Web (WSDL) o de un extremo de WS-MetadataExchange.  
  
 [Procedimiento para usar un moniker de servicio con contratos WSDL](how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 Describe cómo llamar a un ejemplo WCF con un moniker WSDL de WCF.  
  
 [Procedimiento para usar un moniker de servicio con contratos de intercambio de metadatos](how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 Describe cómo llamar a un ejemplo de WCF con un moniker de WCF que especifica un extremo de Mex.  
  
 [Procedimiento para especificar las credenciales de seguridad de los canales](how-to-specify-channel-security-credentials.md)  
 El moniker de servicio de WCF admite la `IChannelCredentials` interfaz que permite una variedad de métodos alternativos para especificar las credenciales del canal.  
  
## <a name="reference"></a>Referencia  

 <xref:System.ServiceModel>  
  
## <a name="see-also"></a>Vea también

- [Integración con aplicaciones COM+](integrating-with-com-plus-applications.md)
