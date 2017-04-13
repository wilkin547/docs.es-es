---
title: "Formatos de metadatos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Formatos de metadatos
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] admite los formatos de metadatos que se encuentran en la siguiente tabla.  
  
## Uso y especificaciones de los metadatos  
  
|Protocolo|Especificación y uso|  
|---------------|--------------------------|  
|WSDL 1.1|[Lenguaje de descripción de servicios Web \(WSDL\) 1.1](http://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza el lenguaje de descripción de servicios Web \(WSDL\) para describir servicios.|  
|esquema XML|[XML Schema, parte 2: tipos de datos, segunda edición](http://go.microsoft.com/fwlink/?LinkId=94861) and [XML Schema, parte1: estructuras, segunda edición](http://go.microsoft.com/fwlink/?LinkId=94862)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza el esquema XML para describir los tipos de datos utilizados en los mensajes.|  
|Directiva WS|[Directiva 1.2 de Web Services: marco de trabajo \(WS\-Policy\)](http://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [Directiva 1.5 de Web Services: marco de trabajo](http://go.microsoft.com/fwlink/?LinkId=94865)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza la especificación WS\-Policy 1.2 ó 1.5 con las aserciones específicas del dominio para describir requisitos y funciones del servicio.|  
|Datos adjuntos de directivas WS|[Directiva 1.2 de Web Services: datos adjuntos \(WS\-PolicyAttachment\)](http://go.microsoft.com/fwlink/?LinkId=94866)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa Datos adjuntos de directivas WS para adjuntar expresiones de directivas en varios ámbitos de WSDL.|  
|Intercambio de metadatos WS|[Intercambio de metadatos de Web Services \(WS\-MetadataExchange\), versión 1.1](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa WS\-MetadataExchange para recuperar el esquema XML, WSDL y WS\-Policy.|  
|Enlace de direccionamiento de WS para WSDL|[Web Services Addressing 1.0: WSDL Binding](http://go.microsoft.com/fwlink/?LinkId=94869)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa WS\-Addressing Binding para que WSDL adjunte información del direccionamiento en WSDL.|  
  
## Vea también  
 [Protocolos de servicios Web compatibles con los enlaces de interoperabilidad proporcionados por el sistema](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)   
 [WSDL y directivas](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)