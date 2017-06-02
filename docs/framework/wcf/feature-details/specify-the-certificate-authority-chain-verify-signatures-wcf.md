---
title: "C&#243;mo: Especificar la cadena de certificados de la entidad de certificaci&#243;n utilizada para comprobar las firmas (WCF) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "certificados [WCF], especificar la cadena de certificados de la entidad de certificación"
  - "certificados [WCF], verificar firmas"
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# C&#243;mo: Especificar la cadena de certificados de la entidad de certificaci&#243;n utilizada para comprobar las firmas (WCF)
Cuando [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] recibe un mensaje SOAP firmado mediante un certificado X.509, de forma predeterminada comprueba que una entidad de certificación de confianza haya emitido el certificado X.509.Esto se hace consultando un almacén de certificados y determinando si el certificado para esa entidad de certificación se ha designado como de confianza.Para que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] realice esta determinación, la cadena de certificados de la entidad de certificación debe estar instalada en el almacén de certificados correcto.  
  
### Para instalar una cadena de certificados de la entidad de certificación  
  
-   Para cada entidad de certificación en cuyos certificados X.509 emitidos piense confiar un destinatario del mensaje SOAP, instale la cadena de certificados de la entidad de certificación en el almacén de certificados del que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] recupera los certificados X.509 de acuerdo con la configuración.  
  
     Por ejemplo, si un destinatario del mensaje SOAP piensa confiar en los certificados X.509 emitidos por Microsoft, la cadena de certificados de la entidad de certificación para Microsoft se debe instalar en el almacén de certificados en el que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] busca los certificados X.509 de acuerdo con la configuración.El almacén de certificados en el que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] busca los certificados X.509 se puede especificar en código o configuración.Por ejemplo, se puede especificar en código utilizando el método <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> o en configuración de algunas maneras, incluyendo [\<serviceCertificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).  
  
     Dado que Windows distribuye con un conjunto de cadenas de certificados predeterminadas para entidades de certificación de confianza, quizás no sea necesario instalar la cadena de certificados para todas las entidades de certificación.  
  
    1.  Exporte la cadena de certificados de la entidad de certificación.  
  
         Cómo hacerlo exactamente depende de la entidad de certificación.Si la entidad de certificación está ejecutando Servicios de servidor de certificados de Microsoft, seleccione **Descargar certificado de CA, cadena de certificados o CRL** y a continuación elija **Descargar certificado de CA**.  
  
    2.  Importe la cadena de certificados de la entidad de certificación.  
  
         En la Microsoft Management Console \(MMC\), abra el complemento Certificados.Para el almacén de certificados del que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] recupera los certificados X.509 de acuerdo con la configuración, seleccione la carpeta **Raíz de confianza** **Entidades de certificación**.En la carpeta **Entidades de certificación raíz de confianza**, haga clic con el botón secundario del mouse en la carpeta **Certificados**, seleccione **Todas las tareas**y, a continuación, haga clic en **Importar**.Proporcione el archivo exportado en el paso a.  
  
         [!INCLUDE[crabout](../../../../includes/crabout-md.md)] utilizando el complemento Certificados con MMC, vea [Cómo: Ver certificados con el complemento de MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
## Vea también  
 [Trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)