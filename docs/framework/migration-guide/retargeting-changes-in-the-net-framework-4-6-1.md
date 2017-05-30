---
title: "Cambios de redestinación en .NET Framework 4.6.1 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes, .NET Framework
- retargeting changes, .NET Framework 4.6.1
- application compatibility
ms.assetid: 411ad548-30fa-43da-8716-10eccfc839e6
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0adc4a6cae566b6a15c5fa492620abb74b47335b
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="retargeting-changes-in-the-net-framework-461"></a>Cambios de redestinación en .NET Framework 4.6.1
En algunos pocos casos, los cambios de redestinación pueden afectar a las aplicaciones que se vuelven a compilar para [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. A menos que se especifique lo contrario, estos cambios no afectan a los archivos binarios que tienen como destino una versión anterior de .NET Framework pero que se ejecutan en [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].  
  
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] incluye cambios de redestinación en las áreas siguientes:  
  
-   [Principal](#Core)  
  
-   [Contratos de código](#Contracts)  
  
-   [Windows Communication Foundation](#WCF)  
  
-   [Windows Forms](#WinForms)  
  
<a name="Core"></a>   
## <a name="core"></a>Principal  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|<xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=fullName>|Para aplicaciones destinadas a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] y versiones posteriores, el carácter separador de la ruta de acceso ha cambiado de una barra diagonal inversa ("\\") a una barra diagonal ("/") en la propiedad <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A> de los objetos <xref:System.IO.Compression.ZipArchiveEntry> creados por sobrecargas del método <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=fullName>.|El cambio trae la implementación de .NET en conformidad con la sección 4.4.17.1 de la [Especificación de formato de archivo .ZIP](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) y permite que los archivos ZIP se descompriman en sistemas distintos de Windows.<br /><br /> Sin embargo, es posible que las aplicaciones que tienen como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] y versiones posteriores no formen parte de este comportamiento. Para más información, consulte [Mitigación: separador de ruta de acceso de ZipArchiveEntry.FullName](../../../docs/framework/migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md).|Borde|  
  
<a name="Contracts"></a>   
## <a name="code-contracts"></a>Contratos de código  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|<xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=fullName> y <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=fullName>, y llama a <xref:System.String.IsNullOrEmpty%2A?displayProperty=fullName>|Para las aplicaciones que tienen como destino .NET Framework 4.6.1, el sistema de reescritura emite la advertencia del compilador CC1036: "Se detectó llamada al método 'System.String.IsNullOrWhiteSpace(System.String)' sin [Pure] en el método...".|Se trata de una advertencia del compilador en lugar de un error del compilador.<br /><br /> Este comportamiento se solucionó en [Problema de GitHub #339](https://github.com/Microsoft/CodeContracts/issues/339). Para eliminar esta advertencia, puede descargar y compilar una versión actualizada del código fuente para las herramientas de Contratos de código de [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md). La información de descarga se encuentra en la parte inferior de la página.|Secundaria|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation"></a>Windows Communication Foundation  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName><br /><br /> (Espacio de nombres <xref:System.IdentityModel.Claims>)|En aplicaciones destinadas a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], si un conjunto de notificaciones X509 se inicia desde un certificado que tenga varias entradas DNS en su campo SAN, el método <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A> intenta hacer coincidir el argumento `claimType` con todas las entradas DNS.<br /><br /> Para aquellas aplicaciones destinadas a versiones anteriores de .NET Framework, el método <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A> intenta hacer coincidir el argumento `claimType` solo con la última entrada DNS.|Este cambio afecta a todas las aplicaciones que tienen como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Aquellas aplicaciones que tengan como destino versiones anteriores de .NET Framework, no se verán afectadas.<br /><br /> Sin embargo, es posible que las aplicaciones que tienen como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] no formen parte de este comportamiento. Además, también es posible que las aplicaciones que tienen como destino versiones anteriores de .NET Framework y que se ejecutan con [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], no formen parte de este comportamiento. Para más información, consulte [Mitigación: Método X509CertificateClaimSet.FindClaims](../../../docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|Secundaria|  
  
<a name="WinForms"></a>   
## <a name="windows-forms"></a>Windows Forms  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|Método <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> (espacio de nombres <xref:System.Windows.Forms>)|En las aplicaciones de Windows Forms destinadas a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], una implementación <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> personalizada puede filtrar mensajes de forma segura cuando se llama al método <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> si la implementación <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName>:<br /><br /> <ul><li>Realiza una o dos de las siguientes acciones:<br /><br /> <ul><li>Agregar un filtro de mensajes al llamar al método <xref:System.Windows.Forms.Application.AddMessageFilter%2A>.</li><li>Quitar un filtro de mensajes al llamar al método <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>. .</li></ul></li><li>El elemento **And** proporciona mensajes mediante una llamada al método <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName>.</li></ul><br /> En algunos casos, tales implementaciones en las aplicaciones de Windows Forms destinadas a las versiones anteriores de .NET Framework inician una excepción <xref:System.IndexOutOfRangeException> cuando se llama al método <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>.|Este cambio afecta a todas las aplicaciones que tienen como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Aquellas aplicaciones que tengan como destino versiones anteriores de .NET Framework, no se verán afectadas.<br /><br /> Sin embargo, es posible que las aplicaciones que tienen como destino a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] no formen parte de este comportamiento. Además, también es posible que las aplicaciones que tienen como destino versiones anteriores de .NET Framework y que se ejecutan con [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], no formen parte de este comportamiento. Para más información, consulte [Mitigación: personalizar implementaciones de IMessageFilter.PreFilterMessage](../../../docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|Borde|  
  
## <a name="see-also"></a>Vea también  
 [Compatibilidad de aplicaciones en 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)
