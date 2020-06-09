---
title: Diferencias entre la validación de certificados de servicio realizada por Internet Explorer y WCF
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: 151075f2894b895ab90418748df9face3aa70252
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599196"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a>Diferencias entre la validación de certificados de servicio realizada por Internet Explorer y WCF
Debido a la diferencia entre la forma en que Internet Explorer y Windows Communication Foundation (WCF) validan los certificados de servicio cuando se usa HTTPS, es posible que Internet Explorer no pueda tener acceso a la página de ayuda o el lenguaje de descripción de servicios web (WSDL) de un servicio aunque un cliente de WCF pueda enviar mensajes correctamente a los extremos de servicio. Esto se debe a que Internet Explorer comprueba si el certificado del servicio tiene los `ServerAuthentication` identificadores de objeto (OID) en las marcas de uso mejoradas, mientras que WCF no exige este tipo de restricción. Si Internet Explorer no puede obtener acceso a la página de ayuda del servicio o al WSDL para el servicio, use la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para tener acceso a los metadatos del servicio.  
  
## <a name="see-also"></a>Vea también

- [Diferencias en la validación de certificados entre HTTPS, SSL a través de TCP, y seguridad SOAP](cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [Procedimiento para recuperar metadatos e implementar un servicio conforme](how-to-retrieve-metadata-and-implement-a-compliant-service.md)
