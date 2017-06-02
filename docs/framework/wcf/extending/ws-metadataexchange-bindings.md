---
title: "Enlaces de WS-MetadataExchange | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Enlaces de WS-MetadataExchange
En este tema se describe cómo se construyen los enlaces de intercambio de metadatos predeterminados para varios transportes.  
  
## Los enlaces predeterminados  
  
|Nombre de enlace predeterminado|Cómo se construye el enlace|  
|-------------------------------------|---------------------------------|  
|MexHttpBinding|Un <xref:System.ServiceModel.WSHttpBinding> con la seguridad de nivel de transporte deshabilitada.|  
|MexHttpsBinding|<xref:System.ServiceModel.WSHttpBinding> que admite la seguridad de nivel de transporte.|  
|MexNamedPipeBinding|<xref:System.ServiceModel.Channels.CustomBinding> con <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> que utiliza los valores predeterminados.|  
|MexTcpBinding|<xref:System.ServiceModel.Channels.CustomBinding> con <xref:System.ServiceModel.Channels.TcpTransportBindingElement> que utiliza los valores predeterminados.|