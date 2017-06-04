---
title: "C&#243;mo obtener un certificado (WCF) | Microsoft Docs"
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
  - "certificados [WCF], obtener"
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# C&#243;mo obtener un certificado (WCF)
Para usar cualquiera de las características de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] que usan certificados X.509, ha de obtener primero los certificados.  
  
### Para obtener un certificado X.509.  
  
1.  Elija una de las siguientes opciones:  
  
    -   Adquiera un certificado de una entidad emisora de certificados, como VeriSign, Inc.  
  
    -   Configure su propio servicio de certificados y haga que una entidad de certificación los firme.  [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], Windows 2000 Server, Windows 2000 Server Datacenter y Windows 2000 Datacenter Server incluyen servicios de servidor de certificados que admiten la infraestructura de clave pública \(PKI\).  En Windows Server 2008, use la función [Servicios de certificados de Active Directory](http://go.microsoft.com/fwlink/?LinkID=15348) para administrar una entidad de certificación.  
  
    -   Configure su propio servicio de certificados y asegúrese de que los certificados no estén firmados.  
  
    > [!NOTE]
    >  Elija el método que elija, el destinatario de la solicitud SOAP que contiene el certificado X.509 debe confiar en el certificado X.509.  Esto significa que el certificado X.509 o un emisor en la cadena de certificados está en el almacén de certificados de gente de confianza y que el certificado X.509 no está en el almacén de certificados que no son de confianza.  
  
## Vea también  
 [Trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Cómo: Crear certificados temporales que puedan utilizarse durante las operaciones de desarrollo](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)