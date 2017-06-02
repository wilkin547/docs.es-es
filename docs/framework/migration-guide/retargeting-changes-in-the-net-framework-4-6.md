---
title: "Cambios de redestinación en .NET Framework 4.6 | Microsoft Docs"
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
- retargeting changes, .NET Framework 4.6
- application compatibility
ms.assetid: fa849255-f90f-4bf1-b0ff-b173c12110d7
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 19ad80233a79a4fdef89550696c1c3d33e14b355
ms.lasthandoff: 04/18/2017

---
# <a name="retargeting-changes-in-the-net-framework-46"></a>Cambios de redestinación en .NET Framework 4.6
En algunos pocos casos, los cambios de redestinación pueden afectar a las aplicaciones que se vuelven a compilar para [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]. A menos que se especifique lo contrario, estos cambios no afectan a los archivos binarios que tienen como destino una versión anterior de .NET Framework pero que se ejecutan en [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].  
  
 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] incluye cambios de redestinación en las áreas siguientes:  
  
-   [Principal](#Core)  
  
-   [ASP.NET](#ASP)  
  
-   [Redes](#Net)  
  
-   [Windows Communications Foundation (WCF)](#WCF)  
  
-   [Windows Forms](#WinForms)  
  
-   [Windows Presentation Foundation (WPF)](#WPF)  
  
-   [XML](#XML)  
  
<a name="Core"></a>   
## <a name="core"></a>Principal  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|<xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName>, <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> y operaciones asincrónicas basadas en tareas con <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601>|Para las aplicaciones que tienen como destino [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] y versiones posteriores, <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> se almacenan en <xref:System.Threading.ExecutionContext> de un subproceso, que fluye a través de operaciones asincrónicas.|Los cambios en las propiedades <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> se reflejarán en las tareas asincrónicas que se inicien posteriormente. Para más información, consulte [Mitigación: referencia cultural y operaciones asincrónicas](../../../docs/framework/migration-guide/mitigation-culture-and-asynchronous-operations.md).|Secundaria|  
  
<a name="ASP"></a>   
## <a name="aspnet"></a>ASP.NET  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|<xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName> con un valor `tagKey` de <xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName>|En conformidad con el estándar HTML, el método <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName> ahora representa <xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName> como una etiqueta que no es de cierre en una respuesta HTML.|La etiqueta BR ahora genera un salto de línea. Anteriormente, generaba dos saltos de línea.<br /><br /> Las aplicaciones que dependen de la etiqueta `<BR>` para generar dos saltos de línea pueden restaurar el comportamiento anterior agregando una llamada adicional al método <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName> con el argumento <xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName>.|Secundaria|  
  
<a name="Net"></a>   
## <a name="networking"></a>Redes  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|<xref:System.Net.ServicePointManager?displayProperty=fullName> y <xref:System.Net.Security.SslStream?displayProperty=fullName>|A partir de las aplicaciones que tienen como destino .NET Framework 4.6, las clases <xref:System.Net.ServicePointManager?displayProperty=fullName> y <xref:System.Net.Security.SslStream?displayProperty=fullName> pueden usar uno de los siguientes tres protocolos: Tls1.0, Tls1.1 o Tls 1.2.<br /><br /> Las aplicaciones destinadas a una versión anterior de .NET Framework, incluso si se ejecutan en .NET Framework 4.6, no se ven afectadas.|Este cambio afecta a cualquier aplicación que tenga como destino .NET Framework 4.6 y que use SSL para comunicarse con un servidor HTTPS o un servidor de socket mediante cualquiera de los siguientes tipos: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> y <xref:System.Net.Security.SslStream>.  Para más información, consulte [Mitigación: protocolos TLS](../../../docs/framework/migration-guide/mitigation-tls-protocols.md).|Secundaria|  
  
<a name="WCF"></a>   
## <a name="windows-communications-foundation-wcf"></a>Windows Communications Foundation (WCF)  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|<xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%2A?displayProperty=fullName>|La implementación de <xref:System.IdentityModel.Policy.AuthorizationContext> devuelta por una llamada a <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29> con un argumento `null``authorizationPolicies` ha cambiado su implementación en [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].|En raras ocasiones, las aplicaciones WCF que usan la autenticación personalizada pueden sufrir diferencias de comportamiento. Si se necesita el comportamiento anterior, consulte [Mitigación: AuthorizationContext predeterminado](../../../docs/framework/migration-guide/mitigation-default-authorizationcontext.md).|Secundaria|  
  
<a name="WinForms"></a>   
## <a name="windows-forms"></a>Windows Forms  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|<xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName>|A partir de las aplicaciones que tienen como destino .NET Framework 4.6, el método <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> convierte correctamente iconos con marcos PNG en objetos <xref:System.Drawing.Bitmap>.<br /><br /> En las aplicaciones que tienen como destino .NET Framework 4.5.2 y versiones anteriores, el método <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> genera una excepción <xref:System.ArgumentOutOfRangeException> si el objeto <xref:System.Drawing.Icon> tiene marcos PNG.|Este cambio afecta a las aplicaciones que se vuelven a compilar para tener como destino .NET Framework 4.6 y que proporcionan un control especial para la excepción <xref:System.ArgumentOutOfRangeException> que se produce si un objeto <xref:System.Drawing.Icon> tiene marcos PNG. Si no desea este comportamiento, un modificador de configuración restaura el comportamiento anterior. Para más información, consulte [Mitigación: marcos PNG en objetos de icono](../../../docs/framework/migration-guide/mitigation-png-frames-in-icon-objects.md).|Secundaria|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|<xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>|En las aplicaciones que tienen como destino .NET Framework 4.6 y .NET Framework 4.6.1, los cambios en las propiedades <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> que se realizan dentro de un <xref:System.Windows.Threading.Dispatcher> se pierden al final de esa operación del distribuidor. De igual forma, es posible que los cambios en <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> realizados fuera de la operación del distribuidor no se reflejen cuando se ejecute la operación.|Es posible que los cambios en las propiedades <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> no fluyan entre las devoluciones de llamada de la UI de WPF y otro código en una aplicación WPF. Para más información, consulte [Mitigación: referencia cultural y operaciones del distribuidor en aplicaciones WPF](../../../docs/framework/migration-guide/mitigation-culture-and-dispatcher-operations-in-wpf-apps.md).|Secundaria|  
|Redondeo del diseño con valores altos de PPP|Ha cambiado la manera en la que se redondean los márgenes, así como los bordes y el fondo de estos.|El diseño de los controles WPF puede cambiar ligeramente. Para más información, consulte [Mitigación: diseño de WPF](../../../docs/framework/migration-guide/mitigation-wpf-layout.md).|Secundaria|  
  
<a name="XML"></a>   
## <a name="xml"></a>XML  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|Validación de esquemas XSD|A partir de .NET Framework 4.6, la validación de esquemas XSD detecta la infracción de la restricción única si se usa una clave compuesta y una clave está vacía.|Consulte [Mitigación: validación de esquema XML](../../../docs/framework/migration-guide/mitigation-xml-schema-validation.md)|Secundaria|  
|<xref:System.Xml.XmlWriter>|Para las aplicaciones destinadas a .NET Framework 4.5.2 o versiones anteriores, el procedimiento de escribir un par suplente no válido usando el control de reserva de excepción no siempre produce una excepción.<br /><br /> Para las aplicaciones que tienen como destino [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], si se intenta escribir un par suplente no válido se genera una excepción <xref:System.ArgumentException>.|Las aplicaciones que se vuelven a compilar teniendo como destino [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] y que escriben pares suplentes no válidos producirán una excepción en los casos en que anteriormente no lo hicieron.|Borde|
