---
title: Diferencias en la validación de certificados entre HTTPS, SSL a través de TCP, y seguridad SOAP
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF], validation differences
ms.assetid: 953a219f-4745-4019-9894-c70704f352e6
ms.openlocfilehash: dcde7bb4cc193d18737d26facbbd69ccd597d66b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599339"
---
# <a name="certificate-validation-differences-between-https-ssl-over-tcp-and-soap-security"></a>Diferencias en la validación de certificados entre HTTPS, SSL a través de TCP, y seguridad SOAP
Puede usar certificados en Windows Communication Foundation (WCF) con seguridad de nivel de mensaje (SOAP) además de la seguridad de capa de transporte (TLS) sobre HTTP (HTTPS) o TCP. En este tema se describen las diferencias en la manera como se validan tales certificados.  
  
## <a name="validation-of-https-client-certificates"></a>Validación de certificados de cliente HTTPS  
 Al utilizar HTTPS para comunicarse entre un cliente y un servicio, el certificado que el cliente utiliza para autenticar al servicio debe soportar la confianza de la cadena. Es decir, debe encadenar a una entidad de certificación raíz de confianza. Si no, el nivel HTTP inicia una excepción <xref:System.Net.WebException> con el mensaje "Error en el servidor remoto: (403) Prohibido". WCF expone esta excepción como <xref:System.ServiceModel.Security.MessageSecurityException> .  
  
## <a name="validation-of-https-service-certificates"></a>Validación de certificados de servicio HTTPS  
 Al utilizar HTTPS para comunicarse entre un cliente y un servicio, el certificado con el que se autentica el servidor debe soportar la confianza de la cadena. Es decir, debe encadenar a una entidad de certificación raíz de confianza. No se realiza ninguna comprobación para ver si se ha revocado el certificado. Puede invalidar este comportamiento registrando una devolución de llamada <xref:System.Net.Security.RemoteCertificateValidationCallback>, como se muestra en el código siguiente.  
  
 [!code-csharp[c_CertificateValidationDifferences#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#1)]
 [!code-vb[c_CertificateValidationDifferences#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#1)]  
  
 donde la firma para `ValidateServerCertificate` es como sigue:  
  
 [!code-csharp[c_CertificateValidationDifferences#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#2)]
 [!code-vb[c_CertificateValidationDifferences#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#2)]  
  
 Al implementar `ValidateServerCertificate`, se puede realizar cualquier comprobación que el programador de la aplicación cliente juzgue necesaria para validar el certificado del servicio.  
  
## <a name="validation-of-client-certificates-in-ssl-over-tcp-or-soap-security"></a>La validación de certificados de cliente en SSL a través TCP o seguridad SOAP  
 Al utilizar Capa de sockets seguros (SSL) a través TCP o seguridad de mensajes (SOAP), los certificados de cliente se validan según el valor de propiedad <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> de la clase <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>. La propiedad está establecida en uno de los valores <xref:System.ServiceModel.Security.X509CertificateValidationMode>. La comprobación de la revocación se realiza según los valores del valor de propiedad <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.RevocationMode%2A> de la clase <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>. La propiedad está establecida en uno de los valores <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.  
  
 [!code-csharp[c_CertificateValidationDifferences#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#3)]
 [!code-vb[c_CertificateValidationDifferences#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#3)]  
  
## <a name="validation-of-service-certificate-in-ssl-over-tcp-and-soap-security"></a>La validación del certificado de servicio en SSL a través TCP y seguridad SOAP  
 Al utilizar SSL a través de TCP o seguridad de mensajes (SOAP), los certificados de servicio se validan de acuerdo con el valor de propiedad <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> de la clase <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>. La propiedad está establecida en uno de los valores <xref:System.ServiceModel.Security.X509CertificateValidationMode>.  
  
 La comprobación de la revocación se realiza según los valores del valor de propiedad <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.RevocationMode%2A> de la clase <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>. La propiedad está establecida en uno de los valores <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.  
  
 [!code-csharp[c_CertificateValidationDifferences#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#4)]
 [!code-vb[c_CertificateValidationDifferences#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#4)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.Security.RemoteCertificateValidationCallback>
- [Trabajar con certificados](working-with-certificates.md)
