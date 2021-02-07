---
description: 'Más información acerca de: diferencias entre la validación de certificados de servicio realizada por Internet Explorer y WCF'
title: Diferencias entre la validación de certificados de servicio realizada por Internet Explorer y WCF
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: 2d635aec0949ec4e65cd965089206bbf6d6815a6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756362"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a><span data-ttu-id="d835f-103">Diferencias entre la validación de certificados de servicio realizada por Internet Explorer y WCF</span><span class="sxs-lookup"><span data-stu-id="d835f-103">Differences Between Service Certificate Validation Done by Internet Explorer and WCF</span></span>

<span data-ttu-id="d835f-104">Debido a la diferencia entre la forma en que Internet Explorer y Windows Communication Foundation (WCF) validan los certificados de servicio cuando se usa HTTPS, es posible que Internet Explorer no pueda tener acceso a la página de ayuda o el lenguaje de descripción de servicios web (WSDL) de un servicio aunque un cliente de WCF pueda enviar mensajes correctamente a los extremos de servicio.</span><span class="sxs-lookup"><span data-stu-id="d835f-104">Because of difference between the way Internet Explorer and Windows Communication Foundation (WCF) validate service certificates when HTTPS is used, it is possible that Internet Explorer will not be able to access the Help page or Web Services Description Language (WSDL) of a service even though a WCF client is able to successfully send messages to the service endpoints.</span></span> <span data-ttu-id="d835f-105">Esto se debe a que Internet Explorer comprueba si el certificado del servicio tiene los `ServerAuthentication` identificadores de objeto (OID) en las marcas de uso mejoradas, mientras que WCF no exige este tipo de restricción.</span><span class="sxs-lookup"><span data-stu-id="d835f-105">This is because Internet Explorer checks whether the service certificate has the `ServerAuthentication` object identifiers (OID) in the enhanced usage flags, whereas WCF does not enforce such a constraint.</span></span> <span data-ttu-id="d835f-106">Si Internet Explorer no puede tener acceso a la página de ayuda del servicio o al WSDL para el servicio, use la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para tener acceso a los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="d835f-106">If Internet Explorer is unable to access the service Help page or the WSDL for the service, use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to access the service metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d835f-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="d835f-107">See also</span></span>

- [<span data-ttu-id="d835f-108">Diferencias en la validación de certificados entre HTTPS, SSL a través de TCP, y seguridad SOAP</span><span class="sxs-lookup"><span data-stu-id="d835f-108">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>](cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [<span data-ttu-id="d835f-109">Procedimiento para recuperar metadatos e implementar un servicio conforme</span><span class="sxs-lookup"><span data-stu-id="d835f-109">How to: Retrieve Metadata and Implement a Compliant Service</span></span>](how-to-retrieve-metadata-and-implement-a-compliant-service.md)
