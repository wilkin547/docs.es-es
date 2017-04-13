---
title: "Comparaci&#243;n de los servicios web ASP.NET con WCF basado en el prop&#243;sito y las normas utilizadas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d3890278-fa9b-4902-91ea-8da73b7143cc
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Comparaci&#243;n de los servicios web ASP.NET con WCF basado en el prop&#243;sito y las normas utilizadas
Los servicios web ASP.NET desarrollados para crear aplicaciones que envían y reciben mensajes mediante el Protocolo simple de acceso a objetos \(SOAP\) sobre HTTP.  La estructura de los mensajes se puede definir mediante un Esquema XML y una herramienta se proporciona para facilitar la serialización de los mensajes a y desde los objetos de .NET Framework.  La tecnología puede generar automáticamente los metadatos para describir los servicio web en el Lenguaje de descripción de servicios Web \(WSDL\) y se proporciona una segunda herramienta para generar clientes para los servicios web desde WSDL.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] es para permitir a las aplicaciones .NET Framework intercambiar los mensajes con otras entidades del software.  Se utiliza SOAP de forma predeterminada, pero los mensajes pueden estar en cualquier formato y se pueden transmitir con cualquier protocolo de transporte.  La estructura de los mensajes se puede definir mediante un Esquema XML y hay varios opciones para serializar los mensajes a y desde objetos de .NET Framework.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede generar automáticamente metadatos para describir aplicaciones compiladas con tecnología de WSDL, y también proporciona una herramienta para generar clientes para esas aplicaciones desde WSDL.  
  
 Las reglas que admiten los servicios web ASP.NET se documentan en el tema sobre [servicios web XML creados con ASP.NET](http://go.microsoft.com/fwlink/?LinkId=94872).  La lista más extensa de reglas admitidas por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se encuentra en [Protocolos de servicios Web compatibles con los enlaces de interoperabilidad proporcionados por el sistema](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).  
  
## Vea también  
 [Comparación de los servicios web ASP.NET con el WCF basado en desarrollo](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)