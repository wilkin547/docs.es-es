---
title: "C&#243;mo utilizar ChannelFactory | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# C&#243;mo utilizar ChannelFactory
La clase <xref:System.ServiceModel.ChannelFactory%601> genérica se usa en escenarios avanzados que requieren la creación de un generador de canal que se puede utilizar para crear más de un canal.  
  
### Crear y utilizar la clase ChannelFactory  
  
1.  Compile y ejecute un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Diseño e implementación de servicios](../../../../docs/framework/wcf/designing-and-implementing-services.md), [Configuración de servicios](../../../../docs/framework/wcf/configuring-services.md) y [Servicios de hospedaje](../../../../docs/framework/wcf/hosting-services.md).  
  
2.  Utilice [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para generar el contrato \(interfaz\) para el cliente.  
  
3.  En el código de cliente, utilice la clase <xref:System.ServiceModel.ChannelFactory%601> para crear varios agentes de escucha de extremo.  
  
## Ejemplo  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]