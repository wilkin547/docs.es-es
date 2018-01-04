---
title: "Diferencias entre la validación de certificados de servicio realizada por Internet Explorer y WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 12e30d9df9d6bb0a9f8776099951e4354d302ebf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a><span data-ttu-id="3f634-102">Diferencias entre la validación de certificados de servicio realizada por Internet Explorer y WCF</span><span class="sxs-lookup"><span data-stu-id="3f634-102">Differences Between Service Certificate Validation Done by Internet Explorer and WCF</span></span>
<span data-ttu-id="3f634-103">Debido a la diferencia entre las maneras en que Internet Explorer e [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] validan los certificados del servicio cuando se utilizan HTTPS, es posible que Internet Explorer no pueda tener acceso a la página de Ayuda o el Lenguaje de descripción de servicios Web (WSDL) de un servicio aunque un cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pueda enviar correctamente los mensajes a los extremos de servicio.</span><span class="sxs-lookup"><span data-stu-id="3f634-103">Because of difference between the way Internet Explorer and [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] validate service certificates when HTTPS is used, it is possible that Internet Explorer will not be able to access the Help page or Web Services Description Language (WSDL) of a service even though a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client is able to successfully send messages to the service endpoints.</span></span> <span data-ttu-id="3f634-104">Esto es porque Internet Explorer comprueba si el certificado del servicio tiene los identificadores de objetos `ServerAuthentication` (OID) en las marcas de uso mejoradas, mientras que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no exige este tipo de restricción.</span><span class="sxs-lookup"><span data-stu-id="3f634-104">This is because Internet Explorer checks whether the service certificate has the `ServerAuthentication` object identifiers (OID) in the enhanced usage flags, whereas [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not enforce such a constraint.</span></span> <span data-ttu-id="3f634-105">Si Internet Explorer no puede tener acceso a la página de Ayuda del servicio o el WSDL para el servicio, use la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para tener acceso a los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="3f634-105">If Internet Explorer is unable to access the service Help page or the WSDL for the service, use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to access the service metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f634-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f634-106">See Also</span></span>  
 [<span data-ttu-id="3f634-107">Diferencias en la validación de certificados entre HTTPS, SSL a través de TCP, y seguridad SOAP</span><span class="sxs-lookup"><span data-stu-id="3f634-107">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)  
 [<span data-ttu-id="3f634-108">Recuperación de los metadatos e implementación de un servicio conforme</span><span class="sxs-lookup"><span data-stu-id="3f634-108">How to: Retrieve Metadata and Implement a Compliant Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
