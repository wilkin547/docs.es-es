---
title: "Cambios en tiempo de ejecución en .NET Framework 4.6.2 | Microsoft Docs"
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
- runtime changes, .NET Framework
- runtime changes, .NET Framework 4.6.2
- application compatibility
ms.assetid: 23bf3a87-6fa1-4b5e-b92c-a39867a06e7f
caps.latest.revision: 16
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: da809955776b5a5cd3776898ecc4c97db74ceb0e
ms.contentlocale: es-es
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-462"></a>Cambios en tiempo de ejecución en .NET Framework 4.6.2
En casos poco frecuentes, los cambios en tiempo de ejecución pueden afectar a las aplicaciones existentes que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en una versión posterior del tiempo de ejecución de .NET Framework. También conllevan comportamientos diferentes en las aplicaciones que se ejecutan en distintos entornos en tiempo de ejecución de .NET Framework. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] incluye cambios en las áreas siguientes:  
  
-   [Principal](#Core)  
  
-   [ASP.NET](#ASP)

-   [Data](#Data)  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF)  
  
-   [Firma y validación de XML](#XML)  
  
<a name="Core"></a>   
## <a name="core"></a>Principal  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|<xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName><br /><br /> <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory%2A?displayProperty=fullName>|Las categorías de caracteres en [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] se basan en Unicode, versión 8.0. Las versiones de .NET Framework 4.5 hasta 4.6.1 clasificaban los caracteres Unicode según Unicode, versión 6.3.<br /><br /> La comparación y ordenación de caracteres no se ven afectados por este cambio. Para obtener más información, vea la sección "Las cadenas y el estándar Unicode" en el tema de la clase <xref:System.String>.|Las categorías de caracteres en [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] pueden no coincidir con las versiones anteriores de .NET Framework. Este cambio afecta principalmente a las sílabas cheroquis y a las marcas de tono y signos de vocal Nuevo Tai Lue.<br /><br /> Para abordar este cambio, debe revisar el código y quitar o cambiar la lógica que depende de categorías de caracteres Unicode codificados de forma rígida.|Secundaria|  
|<xref:System.Security.Cryptography.RSA.ImportParameters%2A?displayProperty=fullName>, <xref:System.Security.Cryptography.RSACng.ImportParameters%2A?displayProperty=fullName>, <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey%2A?displayProperty=fullName>, <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=fullName>|A partir de [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], estos métodos pueden obtener acceso a claves con tamaños de clave no estándar para certificados RSA. En [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] y versiones anteriores, el intento de acceso a estas claves provocaba un elemento <xref:System.Security.Cryptography.CryptographicException>.|Si una lógica de control de excepciones se basa en <xref:System.Security.Cryptography.CryptographicException> cuando se usa un tamaño de clave no estándar, debe quitarse.|Borde|  
|<xref:System.Security.Cryptography.RSACng.VerifyHash%2A?displayProperty=fullName>|A partir de [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], este método devuelve `false` si la propia firma tiene un formato incorrecto. Ahora devuelve `false` para cualquier error de verificación.<br /><br /> En [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] y 4.6.1,  el método genera un elemento <xref:System.Security.Cryptography.CryptographicException> si la propia firma tiene un formato incorrecto.|Debe ejecutarse cualquier código cuya ejecución dependa de <xref:System.Security.Cryptography.CryptographicException> en lugar de ejecutarse si se produce un error en la validación y el método devuelve `false`.|Secundaria|  
  
## <a name="a-nameasp--aspnet"></a><a name="ASP" /> ASP.NET

|Característica|Cambio|Impacto|Ámbito| 
|-------------|------------|------------|-----------|  
| <xref:System.Web.HttpRuntime.AppDomainApopPath%2A> | En .NET Framework 4.6.2, el tiempo de ejecución muestra un elemento  <xref:System.NullReferenceException> cuando se recupera un valor <xref:System.Web.HttpRuntime.AppDomainAppPath%2A> que incluye caracteres nulos. En .NET Framework 4.6.1 y versiones anteriores, genera un elemento <xref:System.ArgumentNullException>.  | Puede hacer lo siguiente para dar respuesta a este cambio: <br/> - Controlar el elemento  <xref:System.NullReferenceException> si la aplicación se ejecuta en .NET Framework 4.6.2. <br /> - Actualizar a .NET Framework 4.7, que restaura el comportamiento anterior y genera el elemento <xref:System.ArgumentNullException>. | Borde |

<a name="Data"></a>   
## <a name="data"></a>Datos  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|Período de bloqueo del grupo de conexión de bases de datos SQL de Azure|Para que las solicitudes abiertas de conexión reconozcan las bases de datos SQL de Azure, se ha quitado el período de bloqueo del grupo de conexión.|Se llevarán a cabo intentos por recuperar solicitudes abiertas de conexión casi inmediatamente después de los errores de conexión transitorios. Para más información, vea [Mitigación: Período de bloqueo del grupo](~/docs/framework/migration-guide/mitigation-pool-blocking-period.md).|Secundaria|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=fullName> <br /> <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=fullName>|Al usar NetTcp con seguridad de transporte y un tipo de credencial de certificado, el protocolo SSL 3 ya no es el protocolo predeterminado para negociar una conexión segura.|En la mayoría de los casos, esto no debería afectar a las aplicaciones existentes, porque TLS 1.0 siempre ha estado incluido en la lista de protocolos para NetTcp. Todos los clientes deberían poder negociar una conexión usando como mínimo TLS 0.<br /><br /> Si se requiere Ssl3, puede usar uno de los siguientes mecanismos de configuración para agregarlo a la lista de protocolos negociados.<br /><br /> -   La propiedad <xref:System.ServiceModel.TcpTransportSecurity?displayProperty=fullName><br />-   La propiedad <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=fullName><br />-   La sección [\<transport>](~/docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md) de [\<netTcpBinding>](~/docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)<br />-   La sección [\<sslStreamSecurity>](~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) de [\<customBinding>](~/docs/framework/configure-apps/file-schema/wcf/custombinding.md)|Borde|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|La propiedad `IsEnabled` del control <xref:System.Windows.Controls.TextBlock> principal|A partir de [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], el cambio de la propiedad `IsEnabled` del control <xref:System.Windows.Controls.TextBlock> principal afecta a los controles secundarios (como hipervínculos y botones) del control <xref:System.Windows.Controls.TextBlock>.<br /><br /> En [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] y versiones anteriores de .NET Framework, los controles dentro de <xref:System.Windows.Controls.TextBlock> no siempre reflejaban el estado de la propiedad `IsEnabled` del elemento <xref:System.Windows.Controls.TextBlock> principal.|Este cambio se ajusta al comportamiento esperado de los controles dentro de un control < xref:System.Windows.Controls.TextBlock >.|Secundaria|  
|Desplazamiento horizontal, virtualización y <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName>|El comportamiento de la operación de desplazamiento para <xref:System.Windows.Controls.ItemsControl> que realiza su propia virtualización en la dirección ortogonal hacia la dirección de desplazamiento principal.|El cambio produce una experiencia más predecible e intuitiva para el usuario final, pero podría afecta a cualquier aplicación que dependa del valor exacto de <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName> después de un desplazamiento horizontal. Para más información, vea [Mitigación: Virtualización y desplazamiento horizontal](~/docs/framework/migration-guide/mitigation-horizontal-scrolling-and-virtualization.md).|Secundaria|  
|Corrector ortográfico de WPF (clase <xref:System.Windows.Controls.SpellCheck?displayProperty=fullName>)|Se han detectado tres problemas en el corrector ortográfico de WPF cuando se ejecuta en [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] en [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]:<br /><br /> -   En [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], el corrector ortográfico a veces genera un elemento <xref:System.Runtime.InteropServices.COMException> cuando se invocan los métodos [ISpellChecker](https://msdn.microsoft.com/library/windows/desktop/hh869767\(v=vs.85\).aspx) o [ISpellCheckerFactory](https://msdn.microsoft.com/library/windows/desktop/hh869770\(v=vs.85\).aspx). En [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], se han eliminado estas excepciones.<br />-  En [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], el corrector ortográfico identifica incorrectamente errores ortográficos en palabras compuestas, como "Hausnummer" en alemán. En [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], el corrector ortográfico controla correctamente las palabras compuestas.<br />-  En [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], el corrector ortográfico genera un elemento <xref:System.UnauthorizedAccessException> cuando se inicia una aplicación mediante "Ejecutar como otro usuario". En [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], este escenario no es compatible y el corrector ortográfico se deshabilita de forma silenciosa.|Estos cambios mejoran la solidez del corrector ortográfico.  No deben afectar negativamente a la aplicación a no ser que el código de la aplicación dependa de una excepción generada.|Borde|  
| Método [DataGridCellsPanel.BringIndexIntoView](xref:System.Windows.Controls.DataGridCellsPanel.BringIndexInfoView(System.Int32)) | En .NET Framework 4.6.2, el método **BringIndexIntoView** se ejecutará de forma asíncrona cuando se habilite la virtualización de columnas, pero el ancho de las columnas no se haya determinado. Sin embargo, si se quitan las columnas antes de que se complete la operación asíncrona, puede producirse un elemento [ArgumentOutOfRangeException](xref:System.ArgumentOutOfRangeException).<br/></br>A partir de .NET Framework 4.7, no se genera la excepción en este escenario. | Puede realizar cualquiera de los procedimientos para evitar que aparezca la excepción: <br/> - Actualizar a .NET Framework 4.7. <br/> 1 Instalar la revisión de reparación más reciente para .NET Framework 4.6.2. <br/> - Evitar quitar las columnas hasta que se haya completado la respuesta asíncrona para el método [DataGrid.ScrollIntoView](xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)). | Borde | 
  
<a name="XML"></a>   
## <a name="signed-xml-verification-requirements"></a>Requisitos de verificación de XML firmado  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|<xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> and <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName>|La carga del recurso externo está deshabilitada y los destinos de identificadores ambiguos se consideran no válidos.|Se genera una excepción en un número de casos, incluidos los siguientes:<br /><br /> -  Identificación de un elemento por atributo de identificador, y definición de un segundo elemento con el mismo identificador.<br />-   Definición de un identificador que no sea un valor `NCName` legal.<br />-  Referencia a identificadores URI externos.<br /><br /> <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A?displayProperty=fullName> always returns `false` for documents:<br /><br /> -   Que utilice la transformación de la referencia XPath<br />-   Que utilice la transformación de la referencia XSLT<br /><br /> Los desarrolladores deben revisar el uso de <xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=fullName> y  <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform>, así como los tipos derivados de <xref:System.Security.Cryptography.Xml.Transform?displayProperty=fullName>, puesto que es posible que el receptor del documento no pueda realizar el procesamiento.<br /><br /> Para más información, vea [Después de aplicar la actualización de seguridad 3141780, las aplicaciones de .NET Framework detectan errores de excepción o errores inesperados al procesar archivos que contienen SignedXml](https://support.microsoft.com/en-us/kb/3148821).|Secundaria|  
  
## <a name="see-also"></a>Vea también  
 [Compatibilidad de aplicaciones en 4.6.2](~/docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)
