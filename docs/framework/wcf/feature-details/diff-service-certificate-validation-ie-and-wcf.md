---
title: Diferencias entre la validación de certificados de servicio realizada por Internet Explorer y WCF
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: 0bced548cdc9423d1907de09e8b52ebe078d7c19
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857706"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a><span data-ttu-id="dd872-102">Diferencias entre la validación de certificados de servicio realizada por Internet Explorer y WCF</span><span class="sxs-lookup"><span data-stu-id="dd872-102">Differences Between Service Certificate Validation Done by Internet Explorer and WCF</span></span>
<span data-ttu-id="dd872-103">Debido a la diferencia entre el modo Internet Explorer y Windows Communication Foundation (WCF) validan los certificados de servicio cuando se usa HTTPS, es posible que Internet Explorer no pueda obtener acceso a la página de ayuda o lenguaje de descripción de servicios Web (WSDL) de un servicio aunque un cliente WCF correctamente es capaz de enviar mensajes a los puntos de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="dd872-103">Because of difference between the way Internet Explorer and Windows Communication Foundation (WCF) validate service certificates when HTTPS is used, it is possible that Internet Explorer will not be able to access the Help page or Web Services Description Language (WSDL) of a service even though a WCF client is able to successfully send messages to the service endpoints.</span></span> <span data-ttu-id="dd872-104">Esto es porque Internet Explorer comprueba si el certificado de servicio tiene la `ServerAuthentication` objeto (OID) de los identificadores en las marcas de uso mejoradas, mientras que WCF no aplica este tipo de restricción.</span><span class="sxs-lookup"><span data-stu-id="dd872-104">This is because Internet Explorer checks whether the service certificate has the `ServerAuthentication` object identifiers (OID) in the enhanced usage flags, whereas WCF does not enforce such a constraint.</span></span> <span data-ttu-id="dd872-105">Si no puede tener acceso a la página de Ayuda del servicio o el WSDL para el servicio de Internet Explorer, use el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para tener acceso a los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="dd872-105">If Internet Explorer is unable to access the service Help page or the WSDL for the service, use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to access the service metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd872-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd872-106">See also</span></span>

- [<span data-ttu-id="dd872-107">Diferencias en la validación de certificados entre HTTPS, SSL a través de TCP, y seguridad SOAP</span><span class="sxs-lookup"><span data-stu-id="dd872-107">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [<span data-ttu-id="dd872-108">Cómo: Recuperar metadatos e implementar un servicio conforme</span><span class="sxs-lookup"><span data-stu-id="dd872-108">How to: Retrieve Metadata and Implement a Compliant Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
