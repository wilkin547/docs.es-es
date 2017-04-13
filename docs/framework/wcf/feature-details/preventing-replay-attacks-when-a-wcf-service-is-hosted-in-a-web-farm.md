---
title: "Prevenir ataques por repetici&#243;n cuando un servicio WCF est&#225; hospedado en una granja web | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1c2ed695-7a31-4257-92bd-9e9731b886a5
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Prevenir ataques por repetici&#243;n cuando un servicio WCF est&#225; hospedado en una granja web
Cuando se usa seguridad de mensajes, WCF impide los ataques por repetición creando un NONCE a partir del mensaje entrante y comprobando la `InMemoryNonceCache` interna para ver si el NONCE generado está presente.Si lo está, el mensaje se descarta como respuesta.Cuando un servicio de WCF se hospeda en una granja de servidores web, como `InMemoryNonceCache` no se comparte entre los nodos de la granja de servidores web, el servicio es vulnerable a ataques mediante repetición.Para mitigar este escenario WCF 4.5 proporciona un punto de extensibilidad que le permite implementar su propia memoria caché compartida de NONCE derivando una clase de la clase abstracta <xref:System.ServiceModel.Security.NoneCache>.  
  
## Implementación de NoneCache  
 Para implementar su propia caché compartida de NONCE, derive una clase de <xref:System.ServiceModel.Security.NoneCache> y reemplace los métodos [M:System.ServiceModel.Security.NoneCache.CheckNonce\(System.Byte\<xref:System.ServiceModel.Security.NoneCache.CheckNonce%2A> y [M:System.ServiceModel.Security.NoneCache.TryAddNonce\(System.Byte\<xref:System.ServiceModel.Security.NoneCache.TryAddNonce%2A>.[M:System.ServiceModel.Security.NoneCache.CheckNonce\(System.Byte\<xref:System.ServiceModel.Security.NoneCache.CheckNonce%2A> comprobará para ver si el NONCE especificado existe en la memoria caché.[M:System.ServiceModel.Security.NoneCache.TryAddNonce\(System.Byte\<xref:System.ServiceModel.Security.NoneCache.TryAddNonce%2A> intentará agregar un NONCE a la memoria caché.Una vez implementada la clase, puede enlazarla creando una instancia y asignándola a <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSecuritySettings.NonceCache%2A> para la detección de reproducción del lado cliente y a <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSecuritySettings.NonceCache%2A> para la detección de reproducción del lado servidor.No hay compatibilidad con la configuración lista para usar para esta característica.  
  
## Vea también  
 [Seguridad de los mensajes](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)   
 [SymmetricSecurityBindingElement](../../../../docs/framework/wcf/diagnostics/wmi/symmetricsecuritybindingelement.md)