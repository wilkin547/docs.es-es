---
title: "Extensi&#243;n de WCF | Microsoft Docs"
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
  - "extensibilidad [WCF]"
  - "WCF, extensibilidad"
  - "Windows Communication Foundation, extensibilidad"
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Extensi&#243;n de WCF
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] le permite modificar y extender los componentes en tiempo de ejecución para controlar y extender precisamente las aplicaciones basadas en servicio.  Los temas de esta sección hacen profundizan en la arquitectura de la extensibilidad.  Para obtener más información acerca de la programación básica, consulte [Programación básica de WCF](../../../../docs/framework/wcf/basic-wcf-programming.md).  
  
## En esta sección  
 [Extensión de ServiceHost y la capa de modelos de servicios](../../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md)  
 El nivel de modelo de servicio es responsable de extraer los mensajes entrantes de los canales subyacentes, de modo que los traduce en código de aplicación en las invocaciones de método y devuelve los resultados al agente de llamada.  Las extensiones de modelo de servicio modifican o implementan la ejecución o comportamiento de la comunicación y características implicadas en la funcionalidad del distribuidor, comportamientos personalizados, interceptación de mensaje y parámetro, y otra funcionalidad de extensibilidad.  
  
 [Extensión de enlaces](../../../../docs/framework/wcf/extending/extending-bindings.md)  
 Los enlaces son los objetos que describen los datos de comunicación exigidos para conectar a un extremo.  Las extensiones de enlace o enlaces personalizados implementan la funcionalidad de la comunicación personalizada exigida para admitir las características de la aplicación.  
  
 [Extensión de la capa de canales](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)  
 El nivel del canal se encuentra bajo el nivel de modelo de servicio y es responsable para el intercambio de mensajes entre los clientes y servicios.  Las extensiones de canal pueden implementar la nueva funcionalidad de protocolo, como la seguridad.  Las extensiones del canal también transportan la funcionalidad, como implementar un nuevo transporte de red para llevar los mensajes SOAP.  
  
 [Extensión de la seguridad](../../../../docs/framework/wcf/extending/extending-security.md)  
 La seguridad en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consiste en transferir seguridad \(integridad, confidencialidad y autenticación\), control de acceso \(autorización\) y auditoría.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza las clases situadas en el espacio de nombres `IdentityModel` para el control de acceso.  Entender la arquitectura de seguridad le permite crear tipos de notificación personalizados para alojar los sistemas de control de acceso personalizados.  
  
 [Extensión del sistema de metadatos](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)  
 El sistema de metadatos [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] es un grupo de clases e interfaces que representan los metadatos requeridos para implementar las aplicaciones basadas en el servicio.  Modifique o extienda las clases o implemente y configure las interfaces para exportar e importar metadatos personalizados, como las extensiones de Lenguaje de descripción de servicios Web \(WSDL\) o las aserciones personalizadas de WS\-PolicyAttachments.  
  
 [Extensión de codificadores y serializadores](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
 Los codificadores y serializadores traducen los datos de un formulario a otro.  Los temas de esta sección exponen cómo extender las clases proporcionadas para cumplir los requisitos especiales.  
  
## Referencia  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Tokens>  
  
## Secciones relacionadas  
 [Programación básica de WCF](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [Detalles de las características de WCF](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [Instrucciones y procedimientos recomendados](../../../../docs/framework/wcf/guidelines-and-best-practices.md)