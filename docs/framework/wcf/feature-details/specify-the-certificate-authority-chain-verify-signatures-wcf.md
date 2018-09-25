---
title: 'Cómo: Especificar la cadena de certificados de la entidad de certificación utilizada para comprobar las firmas (WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], specifying the certificate authority certificate chain
- certificates [WCF], verifying signatures
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
ms.openlocfilehash: 9e2ba9f3550442602cab217fec329e6c19efd3b3
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47080830"
---
# <a name="how-to-specify-the-certificate-authority-certificate-chain-used-to-verify-signatures-wcf"></a>Cómo: Especificar la cadena de certificados de la entidad de certificación utilizada para comprobar las firmas (WCF)
Cuando Windows Communication Foundation (WCF) recibe un mensaje SOAP firmado utilizando un certificado X.509, de forma predeterminada comprueba que una entidad de certificación de confianza emitió el certificado X.509. Esto se hace consultando un almacén de certificados y determinando si el certificado para esa entidad de certificación se ha designado como de confianza. En el orden de WCF facilitar esta determinación, la cadena de certificados de entidad de certificación debe instalarse en el almacén de certificados correcto.  
  
### <a name="to-install-a-certification-authority-certificate-chain"></a>Para instalar una cadena de certificados de la entidad de certificación  
  
-   Para cada entidad de certificación que un destinatario del mensaje SOAP piensa confiar en certificados X.509 emitidos, instale la cadena de certificados de entidad de certificación en el almacén de certificados que WCF está configurado para recuperar los certificados X.509 de.  
  
     Por ejemplo, si un destinatario del mensaje SOAP piensa confiar en certificados X.509 emitidos por Microsoft, la cadena de certificados de entidad de certificación de Microsoft debe instalarse en el almacén de certificados que WCF está configurado para buscar los certificados X.509 de. El almacén de certificados en el que WCF busca los certificados X.509 se puede especificar en código o configuración. Por ejemplo, esto puede especificarse en el código mediante el <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> método o en configuración de varias maneras, incluido el [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .  
  
     Dado que Windows distribuye con un conjunto de cadenas de certificados predeterminadas para entidades de certificación de confianza, quizás no sea necesario instalar la cadena de certificados para todas las entidades de certificación.  
  
    1.  Exporte la cadena de certificados de la entidad de certificación.  
  
         Cómo hacerlo exactamente depende de la entidad de certificación. Si la entidad de certificación está ejecutando servicios de Certificate Server de Microsoft, seleccione **descargar un certificado de CA, cadena de certificados o CRL**y, a continuación, elija **Descargar certificado de CA**.  
  
    2.  Importe la cadena de certificados de la entidad de certificación.  
  
         En la Microsoft Management Console (MMC), abra el complemento Certificados. Para el almacén de certificados que WCF está configurado para recuperar los certificados X.509 en, seleccione el **raíz de confianza** **emisoras** carpeta. En el **entidades emisoras raíz de confianza** carpeta, haga clic en el **certificados** carpeta, seleccione **todas las tareas**y, a continuación, haga clic en **importación** . Proporcione el archivo exportado en el paso a.  
  
         Para obtener más información sobre cómo usar el complemento de certificados con MMC, consulte [Cómo: ver certificados con el complemento de MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
## <a name="see-also"></a>Vea también  
 [Trabajo con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
