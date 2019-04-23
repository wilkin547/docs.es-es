---
title: Diferencias entre la validación de certificados de servicio realizada por Internet Explorer y WCF
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: 0bced548cdc9423d1907de09e8b52ebe078d7c19
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225928"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a>Diferencias entre la validación de certificados de servicio realizada por Internet Explorer y WCF
Debido a la diferencia entre el modo Internet Explorer y Windows Communication Foundation (WCF) validan los certificados de servicio cuando se usa HTTPS, es posible que Internet Explorer no pueda obtener acceso a la página de ayuda o lenguaje de descripción de servicios Web (WSDL) de un servicio aunque un cliente WCF correctamente es capaz de enviar mensajes a los puntos de conexión de servicio. Esto es porque Internet Explorer comprueba si el certificado de servicio tiene la `ServerAuthentication` objeto (OID) de los identificadores en las marcas de uso mejoradas, mientras que WCF no aplica este tipo de restricción. Si no puede tener acceso a la página de Ayuda del servicio o el WSDL para el servicio de Internet Explorer, use el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para tener acceso a los metadatos del servicio.  
  
## <a name="see-also"></a>Vea también

- [Diferencias en la validación de certificados entre HTTPS, SSL a través de TCP, y seguridad SOAP](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [Cómo: Recuperar metadatos e implementar un servicio conforme](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
