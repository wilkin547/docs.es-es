---
title: "Diferencias en la validaci&#243;n de certificados entre HTTPS, SSL a trav&#233;s de TCP, y seguridad SOAP | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "certificados [WCF], diferencias de la validación"
ms.assetid: 953a219f-4745-4019-9894-c70704f352e6
caps.latest.revision: 14
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 14
---
# Diferencias en la validaci&#243;n de certificados entre HTTPS, SSL a trav&#233;s de TCP, y seguridad SOAP
Puede utilizar los certificados en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] con seguridad de la capa del mensaje \(SOAP\) además de la seguridad de la capa de transporte \(TLS\) a través de HTTP \(HTTPS\) o TCP.En este tema se describen las diferencias en la manera como se validan tales certificados.  
  
## Validación de certificados de cliente HTTPS  
 Al utilizar HTTPS para comunicarse entre un cliente y un servicio, el certificado que el cliente utiliza para autenticar al servicio debe soportar la confianza de la cadena.Es decir, debe encadenar a una entidad de certificación raíz de confianza.Si no, el nivel HTTP inicia una excepción <xref:System.Net.WebException> con el mensaje "Error en el servidor remoto: \(403\) Prohibido". [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] manifiesta esta excepción como <xref:System.ServiceModel.Security.MessageSecurityException>.  
  
## Validación de certificados de servicio HTTPS  
 Al utilizar HTTPS para comunicarse entre un cliente y un servicio, el certificado con el que se autentica el servidor debe soportar la confianza de la cadena.Es decir, debe encadenar a una entidad de certificación raíz de confianza.No se realiza ninguna comprobación para ver si se ha revocado el certificado.Puede invalidar este comportamiento registrando una devolución de llamada <xref:System.Net.Security.RemoteCertificateValidationCallback>, como se muestra en el código siguiente.  
  
 [!code-csharp[c_CertificateValidationDifferences#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#1)]
 <!-- TODO: review snippet reference [!code-vb[c_CertificateValidationDifferences#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#1)]  -->  
  
 donde la firma para `ValidateServerCertificate` es como sigue:  
  
 [!code-csharp[c_CertificateValidationDifferences#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#2)]
 [!code-vb[c_CertificateValidationDifferences#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#2)]  
  
 Al implementar `ValidateServerCertificate`, se puede realizar cualquier comprobación que el programador de la aplicación cliente juzgue necesaria para validar el certificado del servicio.  
  
## La validación de certificados de cliente en SSL a través TCP o seguridad SOAP  
 Al utilizar Capa de sockets seguros \(SSL\) a través TCP o seguridad de mensajes \(SOAP\), los certificados de cliente se validan según el valor de propiedad <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> de la clase <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>.La propiedad está establecida en uno de los valores <xref:System.ServiceModel.Security.X509CertificateValidationMode>.La comprobación de la revocación se realiza según los valores del valor de propiedad <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.RevocationMode%2A> de la clase <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>.La propiedad está establecida en uno de los valores <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.  
  
 [!code-csharp[c_CertificateValidationDifferences#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#3)]
 [!code-vb[c_CertificateValidationDifferences#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#3)]  
  
## La validación del certificado de servicio en SSL a través TCP y seguridad SOAP  
 Al utilizar SSL a través de TCP o seguridad de mensajes \(SOAP\), los certificados de servicio se validan de acuerdo con el valor de propiedad <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> de la clase <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>.La propiedad está establecida en uno de los valores <xref:System.ServiceModel.Security.X509CertificateValidationMode>.  
  
 La comprobación de la revocación se realiza según los valores del valor de propiedad <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.RevocationMode%2A> de la clase <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>.La propiedad está establecida en uno de los valores <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.  
  
 [!code-csharp[c_CertificateValidationDifferences#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#4)]
 [!code-vb[c_CertificateValidationDifferences#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#4)]  
  
## Vea también  
 <xref:System.Net.Security.RemoteCertificateValidationCallback>   
 [Trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)