---
description: Más información acerca de cómo especificar la cadena de certificados de la entidad de certificación utilizada para comprobar las firmas (WCF).
title: 'Cómo: Especificar la cadena de certificados de la entidad de certificación utilizada para comprobar las firmas (WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], specifying the certificate authority certificate chain
- certificates [WCF], verifying signatures
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
ms.openlocfilehash: f3bfcb378641db2a4bdba054f25042a5e7e9be07
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793459"
---
# <a name="how-to-specify-the-certificate-authority-certificate-chain-used-to-verify-signatures-wcf"></a>Cómo: Especificar la cadena de certificados de la entidad de certificación utilizada para comprobar las firmas (WCF)

Cuando Windows Communication Foundation (WCF) recibe un mensaje SOAP firmado con un certificado X. 509, de forma predeterminada comprueba que una entidad de certificación de confianza haya emitido el certificado X. 509. Esto se hace consultando un almacén de certificados y determinando si el certificado para esa entidad de certificación se ha designado como de confianza. Para que WCF realice esta determinación, la cadena de certificados de la entidad de certificación debe estar instalada en el almacén de certificados correcto.  
  
### <a name="to-install-a-certification-authority-certificate-chain"></a>Para instalar una cadena de certificados de la entidad de certificación  
  
- Para cada entidad de certificación en la que un destinatario del mensaje SOAP piensa confiar en los certificados X. 509 emitidos por, instale la cadena de certificados de la entidad de certificación en el almacén de certificados en el que se configuró WCF para recuperar los certificados X. 509.  
  
     Por ejemplo, si un destinatario del mensaje SOAP piensa confiar en los certificados X. 509 emitidos por Microsoft, la cadena de certificados de la entidad de certificación para Microsoft debe estar instalada en el almacén de certificados en el que se haya configurado WCF para buscar certificados X. 509 desde. El almacén de certificados en el que WCF busca los certificados X. 509 se puede especificar en el código o en la configuración. Por ejemplo, esto se puede especificar en el código mediante el <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> método o en la configuración de varias maneras, incluido [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .  
  
     Dado que Windows distribuye con un conjunto de cadenas de certificados predeterminadas para entidades de certificación de confianza, quizás no sea necesario instalar la cadena de certificados para todas las entidades de certificación.  
  
    1. Exporte la cadena de certificados de la entidad de certificación.  
  
         Cómo hacerlo exactamente depende de la entidad de certificación. Si la entidad de certificación está ejecutando servicios de Certificate Server de Microsoft, seleccione **descargar un certificado de CA, cadena de certificados o CRL** y, a continuación, elija **Descargar certificado de CA**.  
  
    2. Importe la cadena de certificados de la entidad de certificación.  
  
         En la Microsoft Management Console (MMC), abra el complemento Certificados. En el almacén de certificados en el que WCF está configurado para recuperar los certificados X. 509, seleccione la carpeta **entidades de certificación** **raíz de confianza** . En la carpeta **entidades de certificación raíz de confianza** , haga clic con el botón secundario en la carpeta **certificados** , seleccione **todas las tareas** y, a continuación, haga clic en **importar**. Proporcione el archivo exportado en el paso a.  
  
         Para obtener más información acerca del uso del complemento certificados con MMC, consulte [Cómo: ver certificados con el complemento MMC](how-to-view-certificates-with-the-mmc-snap-in.md).  
  
## <a name="see-also"></a>Vea también

- [Trabajar con certificados](working-with-certificates.md)
