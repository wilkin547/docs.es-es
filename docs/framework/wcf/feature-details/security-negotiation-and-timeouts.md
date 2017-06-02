---
title: "Negociaci&#243;n de seguridad y tiempos de espera | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# Negociaci&#243;n de seguridad y tiempos de espera
Cuando los clientes y servicios autentican, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] admite un modo donde la credencial de servicio se negocia como parte de la autenticación.En tales escenarios, se produce un intercambio potencial de autenticación mutua entre el cliente y el servicio para propagar la credencial del servicio al cliente.La propiedad <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> controla cuánto tiempo puede tardar en completarse el intercambio de autenticación mutua.Sin embargo, este tiempo de espera solo se aplica si el intercambio realmente tarda más que una sola solicitud\-respuesta.En casos donde la negociación se completa en un viaje de ida y vuelta \(round trip\) único, el tiempo de espera no se aplica.  
  
## Vea también  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>   
 [Cómo: Establecer un sesgo de reloj máximo](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)