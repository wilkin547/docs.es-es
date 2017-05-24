---
title: "Cambios de redestinación en .NET Framework 4.6.2 | Microsoft Docs"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes, .NET Framework
- retargeting changes, .NET Framework 4.6.2
- application compatibility
ms.assetid: 76dc6849-8210-4e41-8731-20828c98b282
caps.latest.revision: 26
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 229ccf3fa4ff1029334641da350cfd040e4b286e
ms.lasthandoff: 04/18/2017

---
# <a name="retargeting-changes-in-the-net-framework-462"></a>Cambios de redestinación en .NET Framework 4.6.2
En algunos pocos casos, los cambios de redestinación pueden afectar a las aplicaciones que se vuelven a compilar para [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]. No afectan a los binarios que tienen como destino una versión anterior de .NET Framework pero que se ejecutan en la versión 4.6.2. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] incluye cambios de redestinación en las áreas siguientes:  
  
-   [Principal](#Core)  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
-   [Windows Forms](#WinForms)  
  
 La columna de ámbito de las tablas siguientes especifica la importancia de cada cambio:  
  
-   Principal. Cambio significativo que afecta a un gran número de aplicaciones o que requiere una modificación sustancial del código. Observe que ninguno de los cambios de redestinación pertenecen a esta categoría.  
  
-   Secundario. Cambio que afecta a un pequeño número de aplicaciones o que requiere ligeras modificaciones en el código.  
  
-   Avanzado. Cambio que afecta a aplicaciones de escenarios muy concretos que no son frecuentes.  
  
-   Transparente. Cambio que no tiene ningún efecto apreciable en el programador o el usuario de la aplicación. No es necesario modificar la aplicación debido a este cambio.  
  
<a name="Core"></a>   
## <a name="core"></a>Principal  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|Compatibilidad con rutas de acceso con formato largo|A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], son compatibles las rutas de acceso con formato largo (de hasta 32 000 caracteres) y se ha quitado la limitación de 260 caracteres (o `MAX_PATH`) en longitudes de rutas de acceso.|Para las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], las rutas de acceso de código que anteriormente generaban el elemento <xref:System.IO.PathTooLongException> ya no generan una excepción. Para más información, vea [Mitigación: Compatibilidad con la ruta de acceso de formato largo](~/docs/framework/migration-guide/mitigation-long-path-support.md).|Secundaria|  
|Normalización de la ruta de acceso|A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], la forma en la que se normalizan las rutas de acceso han cambiado para aplazar el sistema operativo y proporcionar un mejor acceso a las rutas de acceso del dispositivo DOS.|Los cambios hacen posible obtener acceso a rutas de acceso del dispositivo válidas que no eran compatibles anteriormente. Para obtener más información, vea [Mitigación: Normalización de la ruta de acceso](~/docs/framework/migration-guide/mitigation-path-normalization.md).|Secundaria|  
|<xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName>|A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], se han realizado una serie de cambios para admitir rutas de acceso que anteriormente no eran compatibles (en términos de longitud y formato). En concreto, las comprobaciones de la sintaxis de separador de la unidad correspondiente (dos puntos) se realizan de manera más correcta.|Estos cambios bloquean algunas rutas del identificador URI que estos dos métodos admitían anteriormente. Para más información, vea [Mitigación: Comprobaciones de dos puntos de la ruta de acceso](~/docs/framework/migration-guide/mitigation-path-colon-checks.md).|Borde|  
|<xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> constructor|A partir de [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> creada por una llamada al método <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> es una nueva instancia <xref:System.Security.Claims.ClaimsIdentity>. En versones anteriores de .NET Framework, el elemento <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> es una referencia existente.|En algunos casos, la comparación de la propiedad  <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> con la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> del constructor <xref:System.Security.Principal.IIdentity> devuelve distintos resultados.<br /><br /> Para más información, vea [Mitigation: Constructor ClaimsIdentity](~/docs/framework/migration-guide/mitigation-claimsidentity-constructor.md).|Borde|  
|<xref:System.Security.Cryptography.AesCryptoServiceProvider.CreateDecryptor%2A?displayProperty=fullName>|A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], el descriptor <xref:System.Security.Cryptography.AesCryptoServiceProvider> proporciona una transformación que puede volver a usarse.   Después de llamar a <xref:System.Security.Cryptography.ICryptoTransform.TransformFinalBlock%2A>, la transformación se vuelve a iniciar y puede volver a usarse.<br /><br /> Para aplicaciones que tienen como destino versiones anteriores de .NET Framework, el intento de volver a usar el descriptor llamando a  <xref:System.Security.Cryptography.ICryptoTransform.TransformBlock%2A> después de una llamada a <xref:System.Security.Cryptography.ICryptoTransform.TransformFinalBlock%2A> genera un elemento  <xref:System.Security.Cryptography.CryptographicException> o provoca datos dañados.|La repercusión debe ser mínima, ya que este es el comportamiento esperado.<br /><br /> Las aplicaciones que dependen del comportamiento anterior pueden rechazar su uso agregando el siguiente ajuste de configuración en la sección [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:<br /><br /> `<runtime>    <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=true"/> </runtime>`<br /><br /> Además, las aplicaciones que tienen como destino versiones anteriores de .NET Framework pero que se ejecutan en una versión de .NET Framework a partir de [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] pueden incluirse en este comportamiento agregando el siguiente ajuste de configuración a la sección [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:<br /><br /> `<runtime>    <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=false"/> </runtime>`|Secundaria|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|Compatibilidad con la seguridad de transporte de WCF para los certificados almacenados con CNG|A partir de las aplicaciones que tienen como destino  [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], la seguridad de transporte de WCF es compatible con los certificados almacenados mediante la biblioteca de criptografía (CNG) de Windows. Esta compatibilidad está limitada a los certificados con una clave pública que tengan un exponente con una longitud no superior a 32 bits. Cuando una aplicación tiene [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] como destino, esta característica está activada de forma predeterminada.<br /><br /> En versiones anteriores de .NET Framework, el intento de usar certificados X509 con un proveedor de almacenamiento de claves CSG genera una excepción.|Las aplicaciones que tienen como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] y versiones anteriores, pero que se ejecutan en [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] pueden habilitar la compatibilidad para los certificados CNG agregando la siguiente línea a la sección runtime del archivo app.config o web.config.<br /><br /> `<AppContextSwitchOverrides     value="Switch.System.ServiceModel.DisableCngCertificates=false" />`<br /><br /> Esto también puede realizarse mediante programación con el siguiente código:<br /><br /> `private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificate"; AppContext.SetSwitch(disableCngCertificates, false);`<br /><br /> `Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates" AppContext.SetSwitch(disableCngCertificates, False)`<br /><br /> Tenga en cuenta que, debido a este cambio, cualquier código erróneo de control de excepciones que dependa del intento de iniciar una comunicación segura con un certificado CNG dejará de ejecutarse.|Secundaria|  
  
<a name="WinForms"></a>   
## <a name="windows-forms"></a>Windows Forms  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|<xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>, `System.ComponentModel.EventDescriptor.Equals` y  `System.ComponentModel.PropertyDescriptor.Equals`|A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], ha cambiado el método de la clase base <xref:System.ComponentModel.MemberDescriptor.Equals%2A>.|Puesto que la prueba de igualdad ahora genera los resultados esperados, este cambio debe tener una repercusión mínima.<br /><br /> Sin embargo, las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] y dependen del comportamiento anterior puede rechazar este cambio. De forma similar, las aplicaciones que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], pueden incluir este cambio. Para más información, vea [Mitigación: MemberDescriptor.Equals](~/docs/framework/migration-guide/mitigation-memberdescriptor-equals.md).|Borde|  
  
## <a name="see-also"></a>Vea también  
 [Compatibilidad de aplicaciones en 4.6.2](~/docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)
