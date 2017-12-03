---
title: "Cómo: Especificar la cadena de certificados de la entidad de certificación utilizada para comprobar las firmas (WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates [WCF], specifying the certificate authority certificate chain
- certificates [WCF], verifying signatures
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6cba37a82174ab255cb6814e296154485fbdd54c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-specify-the-certificate-authority-certificate-chain-used-to-verify-signatures-wcf"></a>Cómo: Especificar la cadena de certificados de la entidad de certificación utilizada para comprobar las firmas (WCF)
Cuando [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] recibe un mensaje SOAP firmado usando un certificado X.509, de forma predeterminada comprueba que una entidad de certificación de confianza haya emitido el certificado X.509. Esto se hace consultando un almacén de certificados y determinando si el certificado para esa entidad de certificación se ha designado como de confianza. Para que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] realice esta determinación, la cadena de certificados de la entidad de certificación debe estar instalada en el almacén de certificados correcto.  
  
### <a name="to-install-a-certification-authority-certificate-chain"></a>Para instalar una cadena de certificados de la entidad de certificación  
  
-   Para cada entidad de certificación en cuyos certificados X.509 emitidos piense confiar un destinatario del mensaje SOAP, instale la cadena de certificados de la entidad de certificación en el almacén de certificados del que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] recupera los certificados X.509 de acuerdo con la configuración.  
  
     Por ejemplo, si un destinatario del mensaje SOAP piensa confiar en los certificados X.509 emitidos por Microsoft, la cadena de certificados de la entidad de certificación para Microsoft se debe instalar en el almacén de certificados en el que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] busca los certificados X.509 de acuerdo con la configuración. El almacén de certificados en el que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] busca los certificados X.509 se puede especificar en código o configuración. Por ejemplo, esto puede especificarse en el código mediante el <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> método o en la configuración de varias maneras, incluido el [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .  
  
     Dado que Windows distribuye con un conjunto de cadenas de certificados predeterminadas para entidades de certificación de confianza, quizás no sea necesario instalar la cadena de certificados para todas las entidades de certificación.  
  
    1.  Exporte la cadena de certificados de la entidad de certificación.  
  
         Cómo hacerlo exactamente depende de la entidad de certificación. Si la entidad de certificación está ejecutando servicios de Certificate Server de Microsoft, seleccione **descargar un certificado de CA, cadena de certificados o CRL**y, a continuación, elija **Descargar certificado de CA**.  
  
    2.  Importe la cadena de certificados de la entidad de certificación.  
  
         En la Microsoft Management Console (MMC), abra el complemento Certificados. Para el certificado de almacén que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] está configurado para recuperar los certificados X.509 en, seleccione la **raíz de confianza** **entidades emisoras de certificados**carpeta. En el **entidades de certificación raíz de confianza** carpeta, haga clic en el **certificados**carpeta, seleccione **todas las tareas**y, a continuación, haga clic en **importación** . Proporcione el archivo exportado en el paso a.  
  
         [!INCLUDE[crabout](../../../../includes/crabout-md.md)]mediante el complemento certificados a MMC, consulte [Cómo: ver certificados con el complemento de MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
