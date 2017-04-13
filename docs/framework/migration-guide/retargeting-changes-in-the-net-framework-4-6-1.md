---
title: "Cambios de redestinaci&#243;n en .NET Framework 4.6.1 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 411ad548-30fa-43da-8716-10eccfc839e6
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# Cambios de redestinaci&#243;n en .NET Framework 4.6.1
En algunos pocos casos, los cambios de redestinación pueden afectar a las aplicaciones que se vuelven a compilar para [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. A menos que se especifique lo contrario, estos cambios no afectan a los archivos binarios que tienen como destino una versión anterior de .NET Framework pero que se ejecutan en [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].  
  
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] incluye cambios de redestinación en las áreas siguientes:  
  
-   [Windows Communication Foundation](#WCF)  
  
-   [Windows Forms](#WinForms)  
  
<a name="WCF"></a>   
## Windows Communication Foundation  
  
|Característica|Cambio|Impacto|Ámbito|  
|--------------------|------------|-------------|------------|  
|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName><br /><br /> \(Espacio de nombres <xref:System.IdentityModel.Claims>\)|En aplicaciones destinadas a la [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], si un conjunto de notificaciones X509 se inicia desde un certificado que tenga varias entradas DNS en su campo SAN, el método <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A> intentará hacer coincidir el argumento `claimType` con todas las entradas DNS.<br /><br /> Para aquellas aplicaciones destinadas a versiones anteriores de .NET Framework, el método <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A> intenta hacer coincidir el argumento `claimType` solo con la última entrada DNS.|Este cambio afecta a todas las aplicaciones que tienen como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Aquellas aplicaciones que tengan como destino versiones anteriores de .NET Framework, no se verán afectadas.<br /><br /> Sin embargo, es posible que las aplicaciones destinadas a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] no formen parte de este comportamiento. Además, también es posible que las aplicaciones que tienen como destino versiones anteriores de .NET Framework y que se ejecutan con [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], no formen parte de este comportamiento Para obtener más información, consulta [Mitigación: X509CertificiateClaimSet.FindClaims \(método\)](../../../docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|Secundaria|  
  
<a name="WinForms"></a>   
## Windows Forms  
  
|Característica|Cambio|Impacto|Ámbito|  
|--------------------|------------|-------------|------------|  
|método <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> \(espacio de nombres <xref:System.Windows.Forms>\)|En las aplicaciones de Windows Forms destinadas a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], una implementación <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> personalizada puede filtrar mensajes de forma segura cuando se llama al método <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> si la implementación <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName>:<br /><br /> <ul><li>Realiza una o dos de las siguientes acciones:<br /><br /> <ul><li>Agregar un filtro de mensajes al llamar al método <xref:System.Windows.Forms.Application.AddMessageFilter%2A>.</li><li>Quitar un filtro de mensajes al llamar al método <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>. .</li></ul></li><li>El elemento **And** proporciona mensajes mediante una llamada al método <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName>.</li></ul><br /> En algunos casos, tales implementaciones en las aplicaciones de Windows Forms destinadas a las versiones anteriores de .NET Framework inician una excepción <xref:System.IndexOutOfRangeException> cuando se llama al método <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>.|Este cambio afecta a todas las aplicaciones que tienen como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Aquellas aplicaciones que tengan como destino versiones anteriores de .NET Framework, no se verán afectadas.<br /><br /> Sin embargo, es posible que las aplicaciones destinadas a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] no formen parte de este comportamiento. Además, también es posible que las aplicaciones que tienen como destino versiones anteriores de .NET Framework y que se ejecutan con [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], no formen parte de este comportamiento Para obtener más información, consulta [Mitigación: personalizar implementaciones de IMessageFilter.PreFilterMessage](../../../docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|Borde|  
  
## Vea también  
 [Compatibilidad de aplicaciones en 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)