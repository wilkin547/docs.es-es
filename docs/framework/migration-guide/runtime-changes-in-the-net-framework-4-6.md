---
title: "Cambios en tiempo de ejecuci&#243;n en .NET Framework 4.6 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5262bcfa-6e48-416b-8972-69cb4002d386
caps.latest.revision: 34
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Cambios en tiempo de ejecuci&#243;n en .NET Framework 4.6
En casos poco frecuentes, los cambios en tiempo de ejecución pueden afectar a las aplicaciones existentes que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en una versión posterior del tiempo de ejecución de .NET Framework. También conllevan comportamientos diferentes en las aplicaciones que se ejecutan en distintos entornos en tiempo de ejecución de .NET Framework. Incluyen cambios en las áreas siguientes:  
  
-   [Principal](#Core)  
  
-   [Redes](#Networking)  
  
-   [Windows Presentation Foundation \(WPF\)](#WPF)  
  
-   [Instalación e implementación](#Setup)  
  
-   [ClickOnce](#ClickOnce)  
  
-   [El nuevo compilador JIT de 64 bits](#RyuJIT)  
  
<a name="Core"></a>   
## Principal  
  
|Característica|Cambio|Impacto|Ámbito|  
|--------------------|------------|-------------|------------|  
|<xref:System.Globalization.PersianCalendar?displayProperty=fullName>|A partir de [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], la clase <xref:System.Globalization.PersianCalendar> utiliza el algoritmo Hijri solar.|El algoritmo Hijri solar produce resultados idénticos al calendario persa actualmente en uso en Irán y Afganistán. También produce resultados que son idénticos al algoritmo anterior para las fechas de 1800 en el calendario gregoriano a 2023 en el calendario gregoriano. Las fechas que están fuera de ese intervalo pueden verse afectadas si la clase <xref:System.Globalization.PersianCalendar> se utiliza para realizar conversiones de fecha \(por ejemplo, entre las fechas del calendario gregoriano y las fechas del calendario persa\) o para determinar si un determinado año es un año bisiesto.<br /><br /> Debido al cambio, el valor de la propiedad <xref:System.Globalization.PersianCalendar.MinSupportedDateTime%2A?displayProperty=fullName> ha cambiado de 21 de marzo de 0622 a 22 de marzo de 0622 para sistemas en los que está instalado [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].<br /><br /> Para obtener más información, vea el tema <xref:System.Globalization.PersianCalendar>.|Secundaria|  
|<xref:System.Runtime.Versioning.TargetFrameworkAttribute>|Para el dominio de aplicación predeterminado, el valor de la propiedad <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> se deriva de <xref:System.Runtime.Versioning.TargetFrameworkAttribute>, si la hay, a menos que se defina explícitamente asignando un nombre a la propiedad <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>.  En versiones anteriores de .NET Framework, el valor del atributo <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> es `null`, a menos que se ejecute una serie de rutas de acceso de código especial o se cree un dominio de aplicación no predeterminado sin especificar explícitamente su marco de trabajo de destino en la propiedad <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>.<br /><br /> En los dominios de aplicación no predeterminados, no se produce ningún cambio en la forma en que se determina el valor de la propiedad <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>. Si no se asigna explícitamente ningún valor a la propiedad <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>, el dominio de aplicación no predeterminado hereda del dominio de aplicación predeterminado el nombre del marco de trabajo de destino.|Para el dominio de aplicación predeterminado, <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> puede devolver un valor distinto de null cuando antes devolvía `null`. Este es el comportamiento deseable.|Borde|  
|<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString%28System.Boolean%29?displayProperty=fullName>|Si los certificados instalados en el sistema no son compatibles con .NET Framework, cuando se pasa un valor de `True` para el argumento `verbose` se devuelve una cadena válida. En versiones anteriores de .NET Framework, si se intenta acceder a la información de clave pública para los certificados no admitidos, en algunos casos se produce una excepción.|Este método es solo informativo; las notas de documentación que se generan pueden no ser coherentes entre las versiones de .NET Framework. Este cambio solo afecta a las aplicaciones que llaman al método `ToString(True)` y que tienen instalados certificados no compatibles con .NET Framework. Al devolver una cadena en lugar de producir una excepción, este cambio hace que el método sea más sólido.|Borde|  
|Reflexión y COM distribuido \(DCOM\)|Los objetos de reflexión ya no se pueden pasar desde el código administrado a los clientes DCOM fuera de proceso. Se ven afectados los siguientes tipos: <xref:System.Reflection.Assembly>; <xref:System.Reflection.MemberInfo> y sus tipos derivados, incluidos <xref:System.Reflection.FieldInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Type> y <xref:System.Reflection.TypeInfo>; <xref:System.Reflection.MethodBody>; <xref:System.Reflection.Module>; y <xref:System.Reflection.ParameterInfo>.|Las llamadas a [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707.aspx) para el objeto devuelven `E_NOINTERFACE`.|Secundaria|  
  
<a name="Networking"></a>   
## Redes  
  
|Característica|Cambio|Impacto|Ámbito|  
|--------------------|------------|-------------|------------|  
|Valores de fecha y hora en la clase <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName>|Para cumplir con [RFC822](http://www.ietf.org/rfc/rfc0822.txt) y [RFC2822](http://www.ietf.org/rfc/rfc2822.txt), ahora un valor con formato de fecha y hora tiene una hora de dos dígitos. Antes la hora tenía un solo dígito para los valores anteriores a las 10:00 AM.|Este cambio afecta a los siguientes escenarios de uso:<br /><br /> -   Comparar las longitudes o códigos hash de objetos <xref:System.Net.Mime.ContentDisposition> serializados en diferentes versiones de .NET Framework.<br />-   Comparar el valor devuelto del método <xref:System.Net.Mime.ContentDisposition.ToString%2A> o la representación de cadena de los valores de la propiedad de fecha y hora de <xref:System.Net.Mime.ContentDisposition> en las versiones de .NET Framework.|Secundaria|  
  
<a name="WPF"></a>   
## Windows Presentation Foundation \(WPF\)  
  
|Característica|Cambio|Impacto|Ámbito|  
|--------------------|------------|-------------|------------|  
|Representación de la ventana en un escenario de varios monitores|La ventana en su totalidad se representa sin recortes al extenderse más allá de una pantalla en un escenario de varios monitores.|Vea [Mitigación: representación de ventanas de WPF](../../../docs/framework/migration-guide/mitigation-wpf-window-rendering.md).|Secundaria|  
|El corrector ortográfico en los controles de WPF habilitados para texto|Al ejecutarse en Windows 10, es posible que el corrector ortográfico no funcione, puesto que las funciones de revisión ortográfica de la plataforma solo están disponibles en los idiomas que aparecen en la lista de idiomas de entrada.|En Windows 10, al agregar un idioma a la lista de teclados disponibles, Windows descarga e instala automáticamente un paquete de características previa petición \(Feature on Demand, FOD\) que proporciona funciones de revisión ortográfica. Al agregar el idioma a la lista de idiomas de entrada, se admitirá el corrector ortográfico.|Secundaria|  
  
<a name="Setup"></a>   
## Instalación e implementación  
  
|Característica|Cambio|Impacto|Ámbito|  
|--------------------|------------|-------------|------------|  
|Control de versiones de producto|Control de versiones del producto ha cambiado desde las versiones anteriores de .NET Framework y especialmente .NET Framework 4, 4.5, 4.5.1 y 4.5.2. Para obtener más información, consulta [Mitigación: Control de versiones de producto](../../../docs/framework/migration-guide/mitigation-product-versioning.md).|Vea [Mitigación: Control de versiones de producto](../../../docs/framework/migration-guide/mitigation-product-versioning.md).|Medium|  
  
<a name="ClickOnce"></a>   
## ClickOnce  
  
|Característica|Cambio|Impacto|Ámbito|  
|--------------------|------------|-------------|------------|  
|Aplicaciones publicadas con ClickOnce que usan un certificado de firma de código SHA\-256.|Las aplicaciones ClickOnce que tienen como destino [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] o versiones anteriores y que están firmadas con un certificado SHA\-256 ya no tienen una dependencia en tiempo de ejecución en [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o versiones posteriores.|Antes, para firmar una aplicación ClickOnce que tenía como destino [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] o versiones anteriores con un certificado de SHA\-256, se requería la presencia de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o una versión posterior en el sistema de destino. Esto producía errores en los casos en que no estaba presente. Este cambio elimina esa dependencia y permite usar certificados de SHA\-256 para firmar las aplicaciones ClickOnce que tienen como destino [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] y versiones anteriores.|Secundaria|  
  
<a name="RyuJIT"></a>   
## El nuevo compilador JIT de 64 bits  
  
|Característica|Cambio|Impacto|Ámbito|  
|--------------------|------------|-------------|------------|  
|Control de excepciones \(devolución desde una región `try`\)|A diferencia del compilador just\-in\-time JIT64 anterior, el nuevo compilador JIT de 64 bits no admite una instrucción [ret](http://msdn.microsoft.com/library/system.reflection.emit.opcodes.ret.aspx) de nivel de integridad en una región `try`.|La especificación ECMA\-335 no permite devolver desde una región `try`, y ningún compilador administrado conocido genera tal IL. Sin embargo, el compilador JIT64 ejecutará dicho IL si se genera mediante la emisión de reflexión.|Borde|