---
title: Diferencias entre la validación de certificados de servicio realizada por Internet Explorer y WCF
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: ecc2b16eae5428e305f5f6096d6d7994256d86c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488691"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a>Diferencias entre la validación de certificados de servicio realizada por Internet Explorer y WCF
Debido a la diferencia entre la forma en que Internet Explorer y Windows Communication Foundation (WCF) validan certificados de servicio cuando se utiliza HTTPS, es posible que Internet Explorer no pueda tener acceso a la página de ayuda o el lenguaje de descripción de servicios Web (WSDL) de un servicio aunque un cliente de WCF correctamente es capaz de enviar mensajes a los extremos de servicio. Esto es porque Internet Explorer comprueba si el certificado de servicio tiene la `ServerAuthentication` (OID) de identificadores de objetos en los indicadores de uso mejoradas, mientras que WCF no exige este tipo de restricción. Si Internet Explorer no puede tener acceso a la página de Ayuda del servicio o el WSDL para el servicio, use la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para tener acceso a los metadatos del servicio.  
  
## <a name="see-also"></a>Vea también  
 [Diferencias en la validación de certificados entre HTTPS, SSL a través de TCP, y seguridad SOAP](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)  
 [Recuperación de los metadatos e implementación de un servicio conforme](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
